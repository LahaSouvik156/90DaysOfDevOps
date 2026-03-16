# Day 12 – Breather & Revision (Days 01–11)- Mini Self-Check

## Goal
Take a **one-day pause** to consolidate everything from Days 01–11 so you don’t forget the fundamentals you just built.

**1. Which 3 commands save you the most time right now, and why?**  
- `top` & `htop` → To check all the running processes
- `systemctl status <service>` → To checks if a particular service is running.  
- `chmod` / `chown` → To change the file/directory permission and ownership.  

**2. How do you check if a service is healthy? List the exact 2–3 commands you’d run first.**  
- `systemctl status <service>` → Check if the service is active and running.  
- `journalctl -u <service> -n 50` → View the latest logs for errors or warnings.  
- `curl -I localhost` → This confirms the service is actually responding to requests.

**3. How do you safely change ownership and permissions without breaking access? Give one example command.**  
- Example: `sudo chown -R professor:planners heist-project/`, `sudo chmod 755 plans.pdf` 

**4. What will you focus on improving in the next 3 days?**  
- Better troubleshooting with logs (`journalctl`) and system monitoring with `top` & `htop`.  
- Will take in-depth knowledge of Linux commands for manage the system errors.
