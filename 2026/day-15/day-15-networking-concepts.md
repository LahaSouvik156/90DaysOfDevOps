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

   ![image alt].(https://github.com/LahaSouvik156/90DaysOfDevOps/blob/master/2026/day-15/A%20record.PNG?raw=true)

   ```bash
   A Record (IP Address): 142.250.195.238 (This may vary depending on your location, e.g., 142.250.x.x).
   TTL (Time to Live): 92 (This number represents the time in seconds that the record can be cached before needing a refresh. It usually varies between 60 and   300 seconds for google.com).
   IN: Represents the Internet class.
   ```

   
