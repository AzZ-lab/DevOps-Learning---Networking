

# 🌐 **Comprehensive Networking & Cloud Learning Notes**



## 🟢 1️⃣ LAN vs. WAN

* **LAN (Local Area Network):**

  * Small area (home, office).
  * High speed.
  * E.g., office network.

* **WAN (Wide Area Network):**

  * Large area (city, country, Internet).
  * Interconnects LANs.
  * E.g., the Internet.

---

## 🟢 2️⃣ OSI Model

**OSI = 7-layer reference model describing how data moves through a network stack.**

**Layers (top to bottom):**

1. **Application**

   * User interaction.
   * Protocols: HTTP, FTP, SMTP.

2. **Presentation**

   * Data formatting & encryption.
   * Converts data formats.
   * Example: SSL/TLS encryption.

3. **Session**

   * Starts/stops connections.
   * Manages sessions between hosts.

4. **Transport**

   * End-to-end communication.
   * Reliable delivery.
   * Protocols: TCP, UDP.

5. **Network**

   * Logical addressing & routing.
   * Protocol: IP.

6. **Data Link**

   * Physical addressing (MAC).
   * Frames & error detection.
   * Protocols: Ethernet.

7. **Physical**

   * Cables, signals, bits.

✅ **Tip to remember:**
**All People Seem To Need Data Processing**

---

## 🟢 3️⃣ TCP/IP Model

**More practical model used in real-world networking.**

**Layers (top to bottom):**

1. **Application**

   * Combines Application, Presentation, Session (from OSI).
   * Protocols: HTTP, SMTP, DNS.

2. **Transport**

   * Reliable delivery.
   * Protocols: TCP, UDP.

3. **Internet**

   * Routing, addressing.
   * Protocol: IP.

4. **Network Access**

   * Data Link + Physical.
   * Ethernet, Wi-Fi.

---

## 🟢 4️⃣ OSI vs. TCP/IP

| OSI Model                              | TCP/IP Model                    |
| -------------------------------------- | ------------------------------- |
| 7 Layers                               | 4 Layers                        |
| Theoretical reference                  | Practical implementation        |
| Separate Presentation & Session layers | Combined into Application layer |

✅ **Key difference:**
TCP/IP is simpler and used in real networks.

---

## 🟢 5️⃣ TCP vs. UDP

* **TCP:**

  * Reliable.
  * Connection-oriented.
  * 3-way handshake.
  * Use cases: Web browsing, email.

* **UDP:**

  * Unreliable.
  * Connectionless.
  * Faster.
  * Use cases: Streaming, VoIP, DNS.

---

## 🟢 6️⃣ IP vs. MAC Address

* **IP Address:**

  * Logical.
  * Changes based on network.
  * Used by routers.

* **MAC Address:**

  * Physical.
  * Unique to hardware.
  * Used by switches.

---

## 🟢 7️⃣ Subnet Mask

* Defines which part of IP = network vs. host.
* E.g., 255.255.255.0 → /24 subnet.

---

## 🟢 8️⃣ Default Gateway

* Router forwarding traffic to other networks.

---

## 🟢 9️⃣ Routing Tables & Default Routes

* Routing Table = List of paths.
* Default Route (`0.0.0.0/0`) = used if no match.

---

## 🟢 🔟 Static vs. Dynamic Routing

* **Static:**

  * Manually set.
  * No automatic updates.

* **Dynamic:**

  * Learned via protocols.
  * Examples: OSPF, BGP.

✅ **OSPF (Open Shortest Path First):**

* Interior routing.
* Finds shortest path.

✅ **BGP (Border Gateway Protocol):**

* Exterior routing.
* Used on Internet.

---

## 🟢 1️⃣1️⃣ NAT & PAT

* **NAT:**

  * Maps private to public IPs.

* **PAT:**

  * Multiple private IPs share one public IP (with ports).

---

## 🟢 1️⃣2️⃣ VLANs

* Virtual networks on the same physical switch.
* Isolate traffic.

---

## 🟢 1️⃣3️⃣ DHCP

* Dynamically assigns IP addresses.

---

## 🟢 1️⃣4️⃣ DNS

* Resolves domain names to IPs.

---

## 🟢 1️⃣5️⃣ ARP

* Resolves IP addresses to MAC addresses.

---

## 🟢 1️⃣6️⃣ ICMP

* Control messages (ping, traceroute).

---

## 🟢 1️⃣7️⃣ MTU & Fragmentation

* **MTU:**

  * Max packet size (Ethernet = 1500 bytes).

* **Fragmentation:**

  * Splits big packets into smaller ones.

---

## 🟢 1️⃣8️⃣ TTL

* Limits packet lifetime.
* Decreases each hop.

---

## 🟢 1️⃣9️⃣ Firewalls

* Control inbound/outbound traffic.
* Types:

  * Packet-filtering
  * Stateful
  * Application-layer
  * Next-Gen

---

## 🟢 2️⃣0️⃣ NGINX

* Web server.
* Reverse proxy.
* Load balancer.
* SSL termination.

---

## 🟢 2️⃣1️⃣ Let’s Encrypt & Certbot

* Free TLS certificates.
* Automates HTTPS setup.

---



