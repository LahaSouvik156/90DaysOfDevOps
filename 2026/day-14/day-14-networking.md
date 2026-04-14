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

1. **Identity:** `hostname -i (or `ip addr show`) — To check my private ip address.

   **Output:** 172.31.17.96
      
2. **Reachability:** `ping google.com` — mention latency and packet loss.

   **Observation:**

       Avg latency: ~10019 ms
       Packet loss: 0%

3. **Path:** `traceroute google.com` (or `tracepath`) — note any long hops/timeouts.

   **Observation:**

       Around 30 hops
    
4. **Ports:** `ss -tulpn` (or `netstat -tulpn`) — list one listening service and its port.

   **Observation:**

       SSH service listening on port 22.
       NGINX service listening on port 80.
    
5. **Name resolution:** `dig google.com` or `nslookup <domain>` — record the resolved IP.

   **Resolved ip** - 142.250.195.110
   
6. **HTTP check:** `curl -I https://google.com` — note the HTTP status code.

   **Output:** HTTP/2 301
   
7. **Connections snapshot:** `netstat -an | head` — count ESTABLISHED vs LISTEN (rough).

   **Observation:**

       LISTEN: ~5 ports
       ESTABLISHED: ~2 connections

---

## Mini Task: Port Probe & Interpret

1) Identify one listening port from `ss -tulpn` (e.g., SSH on 22 or a local web app).

   SSH running on port 22
   
2) From the same machine, test it: `nc -zv localhost <port>` (or `curl -I http://localhost:<port>`).

       Command: nc -zv localhost 22
       Output: Connection to localhost (127.0.0.1) 22 port [tcp/ssh] succeeded!
   
4) Write one line: is it reachable? If not, what’s the next check? (e.g., service status, firewall).

       port is searchable.
       If not reachable, next checks: systemctal status ssh
   
