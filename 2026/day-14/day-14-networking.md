# Day 14 – Networking Fundamentals & Hands-on Checks

# OSI vs TCP/IP Models

- OSI has 7 layers (Physical, Data Link, Network, Transport, Session, Presentation, Application) but it is a conceptual model.
- TCP/IP has 4 layers (Link, Internet, Transport, Application) and it is used in real networks.

---

# Where protocols sit

- IP → Internet layer (routing packets between hosts).
- TCP/UDP → Transport layer (reliable vs fast communication).
- HTTP/HTTPS → Application layer (web communication).
- DNS → Application layer (domain name to IP resolution).

---

# Hands-on Checklist (run these; add 1–2 line observations)

- **Identity:** `hostname -I` (or `ip addr show`) — To check my private ip address.
- **Reachability:** `ping <target>` — mention latency and packet loss.
- **Path:** `traceroute <target>` (or `tracepath`) — note any long hops/timeouts.
- **Ports:** `ss -tulpn` (or `netstat -tulpn`) — list one listening service and its port.
- **Name resolution:** `dig <domain>` or `nslookup <domain>` — record the resolved IP.
- **HTTP check:** `curl -I <http/https-url>` — note the HTTP status code.
- **Connections snapshot:** `netstat -an | head` — count ESTABLISHED vs LISTEN (rough).
