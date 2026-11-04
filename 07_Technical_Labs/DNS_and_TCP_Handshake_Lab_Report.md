# Lab Report: DNS Resolution and TCP Three-Way Handshake Analysis

## 1. DNS Resolution Explanation

The DNS capture shows the client at **10.206.174.204** sending queries to its configured DNS resolver at **10.206.174.176** so that domain names can be translated into IP addresses. DNS normally uses **UDP destination port 53** because UDP has low communication overhead and does not require a TCP connection to be established before a small request and response can be exchanged. TCP port 53 can also be used when required, such as for responses that cannot be handled adequately in a normal UDP exchange. In **Figure 1**, packet **6** shows a UDP DNS query from source port **58491** to destination port **53** requesting an **A record** for `www.apple.com`.

A DNS question contains several important fields. **QNAME** contains the domain name being requested, which in packet 6 is `www.apple.com`. **QTYPE** identifies the type of information requested; an **A** query requests an IPv4 address. **QCLASS** normally has the value **IN**, meaning the Internet class. The DNS message also contains a transaction identifier that allows the response to be associated with the corresponding outstanding query.

The DNS response contains one or more **resource records (RRs)**. A resource record can include the domain name, record type, class, **TTL (Time to Live)** and the actual record data. Packet **8** in Figure 1 is the response from `10.206.174.176` to the client and includes a **CNAME record** for `www.apple.com`. A CNAME, or Canonical Name record, states that one hostname is an alias for another canonical hostname. The resolver can then use the returned DNS information, including any associated address records, to determine the IP address to which the client's application should connect.

The screenshot therefore provides evidence of the DNS process:

**Client → DNS query → Resolver → DNS response → Client**

The capture proves that the client sent DNS requests and received corresponding responses from its configured resolver. It does not, by itself, prove who operates `10.206.174.176` or that every returned DNS record is necessarily trustworthy.

**Figure 1:** Wireshark DNS capture showing queries from `10.206.174.204` to DNS resolver `10.206.174.176` using UDP port 53 and corresponding DNS responses.


# 2. TCP Three-Way Handshake Explanation

The TCP capture in **Figure 2** shows a successful TCP three-way handshake between the client at **10.206.174.204** and the remote server at **105.255.3.16** on HTTPS port **443**. Packet **14** is the first step of the handshake. The client sends a **SYN** from source port `59113` to destination port `443`, indicating that it wants to establish a TCP connection. Wireshark displays a relative sequence number of **Seq=0** for this packet.

Packet **16** is the server's **SYN-ACK** response. The server sends its own SYN while acknowledging the client's SYN with **Ack=1**. A SYN consumes one position in TCP's sequence-number space, which is why a SYN displayed as sequence number 0 is acknowledged with 1. Packet **17** is the client's final **ACK**, with approximately **Seq=1, Ack=1**, acknowledging the server's SYN and completing the three-way handshake.

Each packet provides different evidence. The SYN proves that the client attempted to establish a TCP connection. The SYN-ACK proves that the remote TCP endpoint received the request and was willing to establish the connection. The final ACK proves that the client received the server's SYN-ACK and acknowledged it. After the handshake, packet **19** contains a **TLS Client Hello**, showing that the client proceeded to negotiate TLS over the newly established TCP connection.

The handshake can therefore be represented as:

```text
10.206.174.204                     105.255.3.16:443

      SYN, Seq=0
          ────────────────────────→

                         SYN-ACK, Seq=0, Ack=1
          ←────────────────────────

      ACK, Seq=1, Ack=1
          ────────────────────────→

      TCP CONNECTION ESTABLISHED
```

Sequence numbers allow TCP to track the position and ordering of transmitted data, while acknowledgment numbers tell the sender which sequence information has successfully been received.

**Figure 2:** Wireshark TCP capture showing packet 14 as SYN, packet 16 as SYN-ACK and packet 17 as the final ACK between `10.206.174.204` and `105.255.3.16:443`.

---

# 3. Security Implications

## 3.1 DNS Spoofing and Cache Poisoning

DNS spoofing attempts to cause a victim to accept false DNS information. One possible form is **DNS cache poisoning**, in which an attacker attempts to convince a resolver that an attacker-controlled DNS answer is the legitimate response to an outstanding query.

A simplified attack sequence is:

```text
1. Client requests example.com
             ↓
2. Resolver sends DNS query
             ↓
3. Attacker attempts forged DNS response
             ↓
4. Resolver incorrectly accepts forged record
             ↓
5. Malicious record enters resolver cache
             ↓
6. Later clients receive poisoned information
             ↓
7. Clients may connect to attacker-controlled address
```

For such an attack to succeed, the forged response must appear to belong to the resolver's outstanding DNS request. Traditional DNS messages do not provide cryptographic authentication of ordinary DNS responses. An attacker therefore attempts to construct a response containing values that match the outstanding request, including an appropriate DNS transaction ID and associated UDP communication information. If the malicious response is accepted before the legitimate answer, the resolver may cache the forged resource record for its specified TTL. Subsequent users asking the same resolver for the domain could then receive the poisoned result until the record expires or is removed.

Modern DNS implementations make blind spoofing substantially harder by randomizing transaction IDs and UDP source ports and by applying other protections.

**DNSSEC** provides stronger integrity protection. DNSSEC-enabled zones digitally sign sets of DNS resource records. A validating resolver can verify the signatures through a chain of trust. A valid digital signature provides evidence that the DNS data came from an authenticated source in the DNSSEC trust chain and that the signed data was not modified after it was signed. DNSSEC provides authenticity and integrity; it does **not encrypt DNS queries or responses**.

A firewall can also reduce exposure by allowing clients to send DNS traffic only to approved resolvers and by blocking unauthorized DNS services. However, firewall filtering alone cannot provide the cryptographic validation offered by DNSSEC.

---

## 3.2 TCP Session Hijacking

TCP hijacking involves an attacker attempting to inject packets into or interfere with an existing TCP connection. TCP sequence numbers are critical because the receiving host uses them to determine whether arriving data belongs at the expected position in the byte stream.

An attacker attempting packet injection must therefore generate sequence numbers that fall within a range acceptable to the receiver. If the attacker sends an invalid or unexpected sequence number, the receiving TCP implementation will normally reject or disregard the packet rather than treating it as legitimate application data.

A simplified attack would require the attacker to determine information about an active connection:

```text
Client ←──────── TCP session ────────→ Server
                     ↑
                  Attacker
                     │
       Attempts forged TCP packet
                     │
        Correct sequence information?
             /                 \
           NO                   YES
           ↓                     ↓
     Packet rejected      Injection may become
     or ignored           technically possible
```

Early TCP implementations sometimes generated initial sequence numbers in more predictable ways, making blind sequence-number prediction attacks more practical. Modern operating systems use substantially stronger sequence-number generation and other TCP protections, making blind prediction much more difficult.

However, an attacker who can **observe traffic directly**, such as an attacker positioned appropriately on a compromised or poorly protected network path, may be able to observe current sequence and acknowledgment information rather than guessing blindly. This illustrates why TCP sequence numbers themselves should not be considered cryptographic authentication.

A **stateful firewall** helps by maintaining information about legitimate TCP connections and rejecting traffic that does not correspond to an expected connection state. Anti-spoofing rules can additionally reject traffic using inappropriate source addresses. At the application layer, **TLS** provides much stronger protection by authenticating endpoints and protecting application data against unauthorized modification and disclosure when correctly configured.

---

# 4. Troubleshooting

## 4.1 DNS Server Unreachable

If a workstation could not communicate with DNS resolver `10.206.174.176`, I would first verify the client's basic configuration: IP address, subnet mask, DNS configuration, network interface and routing table. I would then use Wireshark to determine exactly where communication fails.

A useful display filter would be:

```text
dns
```

or more specifically:

```text
ip.addr == 10.206.174.176 && udp.port == 53
```

I would look for a packet similar to the DNS query seen in Figure 1:

```text
Source:       Client IP
Destination:  10.206.174.176
Protocol:     UDP
Dst Port:     53
```

### Query appears but no response appears

If Wireshark shows the query leaving the workstation but no corresponding response arriving, this proves that the client generated and transmitted the request. Possible causes include:

* DNS server unavailable;
* packet loss;
* routing failure farther along the network;
* firewall dropping the query;
* firewall dropping the response;
* DNS service not running;
* incorrect return route.

I would also look for repeated DNS queries because operating systems commonly retry failed DNS requests.

There is **no universal Wireshark waiting period** after which the server can automatically be declared unreachable. DNS retry intervals and timeout values depend on the operating system and resolver implementation. I would observe the client's retries and configured timeout before concluding that the request has failed.

### No DNS query appears

If the application attempts name resolution but Wireshark never shows a DNS query leaving the expected interface, the problem is more likely on the client side. Possible causes include:

* incorrect DNS configuration;
* client firewall;
* application problem;
* wrong capture interface;
* local resolver/cache behavior;
* routing or interface configuration problems.

### Response appears successfully

If the request and corresponding DNS response both appear in Wireshark, network communication with the resolver has succeeded. If the application still reports a timeout or failure, investigation should move toward:

* the local resolver;
* application configuration;
* interpretation of the DNS result;
* subsequent TCP/TLS/application communication.

This prevents incorrectly blaming DNS when the packet evidence shows that DNS resolution succeeded.

---

## 4.2 TCP Handshake Timeout

For a TCP connection problem, I would examine the expected three-way handshake:

```text
CLIENT                    SERVER

 SYN  ───────────────────→
      ←───────────────── SYN-ACK
 ACK  ───────────────────→
```

A useful Wireshark filter may include:

```text
tcp.flags.syn == 1
```

or a filter targeting the relevant host and port.

### SYN is sent but no SYN-ACK returns

If Wireshark shows:

```text
Client → Server    SYN
```

but no SYN-ACK returns, the client is attempting the connection but is not receiving the expected response. Possible causes include:

* server unavailable;
* firewall silently dropping packets;
* incorrect routing;
* packet loss;
* return-path failure;
* destination service unavailable.

The absence of a SYN-ACK alone does not identify which cause is responsible.

If the server instead responds with a **TCP RST**, that is different evidence: it generally indicates that the host was reachable but the connection was actively refused, commonly because nothing is listening on the requested TCP port or a device is actively rejecting the connection.

### No SYN leaves the client

If the application attempts to connect but no SYN appears in the packet capture, possible causes include:

* application failure;
* local firewall blocking communication;
* incorrect destination;
* local routing/configuration error;
* wrong network interface being captured.

The failure is therefore likely occurring before the expected TCP connection attempt reaches the network.

### SYN-ACK is received

If the client receives a SYN-ACK and sends the final ACK, the TCP three-way handshake has succeeded. If the application later times out, basic TCP connectivity to the remote service has already been demonstrated, so I would investigate higher layers such as:

* TLS negotiation;
* HTTP/application behavior;
* authentication;
* application server performance;
* application-layer firewall or proxy behavior.

The packet sequence therefore allows troubleshooting to move from guessing toward identifying **exactly which stage of communication failed**.

---

# Conclusion

The Wireshark captures demonstrate both DNS resolution and TCP connection establishment at the packet level. Figure 1 shows the client at `10.206.174.204` using UDP port 53 to query resolver `10.206.174.176`, including an A-record request for `www.apple.com` and a response containing DNS resource-record information including a CNAME. Figure 2 shows a complete TCP handshake between `10.206.174.204` and `105.255.3.16:443`, consisting of SYN, SYN-ACK and ACK packets followed by a TLS Client Hello.

From a security perspective, the captures illustrate why DNS response integrity, unpredictable TCP sequence information, stateful firewalling, DNSSEC and TLS are important protections. From a troubleshooting perspective, Wireshark makes it possible to determine whether communication failed before a request was transmitted, while waiting for a response, during TCP establishment, or later at the application layer. The correct security conclusion must therefore always be based on the packets actually observed rather than on assumptions about what should have occurred.
