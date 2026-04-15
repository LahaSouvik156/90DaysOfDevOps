# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

### Task 1: DNS – How Names Become IPs
1. Explain in 3–4 lines: what happens when you type `google.com` in a browser?
   
   - The browser sends a request to the DNS server to find the IP address of google.com.
   - The DNS server looks into its records or asks other DNS servers.
   - It returns the IP address of google.com.
   - The browser then connects to that IP and loads the website.

2. What are these record types? Write one line each:

   ```bash
   A record - Maps a domain name to an IPv4 address.
   AAAA record - Maps a domain name to an IPv6 address.
   CNAME record - Points one domain name to another domain name.
   MX record - Specifies the mail server for a domain.
   NS record - Shows which DNS server is responsible for the domain.
   ```

3. Run: `dig google.com` — identify the A record and TTL from the output

   ```bash
   A Record (IP Address): 142.250.195.238 (This may vary depending on your location, e.g., 142.250.x.x).
   TTL (Time to Live): 92 (This number represents the time in seconds that the record can be cached before needing a refresh. It usually varies between 60 and   300 seconds for google.com).
   IN: Represents the Internet class.
   ```
---

### Task 2: IP Addressing
1. What is an IPv4 address? How is it structured? (e.g., `192.168.1.10`)

   IPv4 is a 32-bit number. It is written in four decimal parts separated by dots. Example: 142.250.195.238

2. Difference between **public** and **private** IPs — give one example of each

   **Public IP Address :**
   - What it is: The IP address assigned to your router by your ISP.
   - Function: It is the unique identifier for your entire home or business network on the internet. Every website you visit sees this address.
   - Example: 172.217.164.110 (A public Google server) or a common home external IP like 74.125.22.101. 

   **Private IP Address :**
   - What it is: The IP address assigned to individual devices (phones, computers, smart TVs) by your router.
   - Function: It allows devices within the same network to talk to each other without sending traffic to the internet (e.g., printing a document).
   - Example: 192.168.1.5 or 10.0.0.1.

3. What are the private IP ranges?
   `10.x.x.x`, `172.16.x.x – 172.31.x.x`, `192.168.x.x`

    ```
    10.0.0.0 – 10.255.255.255
    172.16.0.0 – 172.31.255.255
    192.168.0.0 – 192.168.255.255
    ```

4. Run: `ip addr show` — identify which of your IPs are private

   **Private IP :** 172.31.17.96

---

### Task 3: CIDR & Subnetting
1. What does `/24` mean in `192.168.1.0/24`?

   /24 means 24 bits are used for the network part. Remaining 8 bits are for hosts.

2. How many usable hosts in a `/24`? A `/16`? A `/28`?

   ```
   /24: 254 usable hosts (256 total - 2)
   /16: 65,534 usable hosts (65,536 total - 2)
   /28: 14 usable hosts (16 total - 2)
   ```

3. why do we subnet?

  - To divide large networks into smaller parts.
  - Improves security.
  - Reduces traffic.
  - Makes network management easier.

4. CIDR Table.

| CIDR |   Subnet Mask   | Total IPs | Usable Hosts |
|------|-----------------|-----------|--------------|
| /24  | 255.255.255.0   |  256      |  254         |
| /16  | 255.255.0.0     |  65,536   |  65,534      |
| /28  | 255.255.255.240 |  16       |  14          |

---

### Task 4: Ports – The Doors to Services
1. What is a port? Why do we need them?

   A port is a logical door on a computer. It allows multiple services to run on the same IP.

2. List of some common ports

   | Port  | Service |
   | ----- | ------- |
   | 22    | SSH     |
   | 80    | HTTP    |
   | 443   | HTTPS   |
   | 53    | DNS     |
   | 3306  | MySQL   |
   | 6379  | Redis   |
   | 27017 | MongoDB |

3. Run `ss -tulpn` — match at least 2 listening ports to their services

   Port 22 → SSH service
   Port 80 → The default network port used for transmitting unencrypted web content via HTTP

---

### Task 5: Putting It Together
1. You run `curl http://myapp.com:8080` — what networking concepts from today are involved?

   - DNS resolves myapp.com to IP.
   - TCP connects to port 8080.
   - HTTP request is sent to the server.

2. Your app can't reach a database at `10.0.1.50:3306` — what would you check first?

   **Things to check first:**

   - If the database is running or not.
   - If the port 3306 is enabled or not.
   - Also the Network connectivity needs to be checked.
   - Firewall or security group rules.


   
