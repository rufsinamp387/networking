PORT FORWARDING

port forwardingPort forwarding is a networking technique that directs external internet traffic to a specific device inside a private local network.


Why It Is Needed

The Problem: Your router has one public IP address, but your home has multiple devices with private IP addresses (e.g., 192.168.1.5). External internet traffic cannot see these private IPs.

The Solution: Port forwarding acts like an apartment building directory. It tells the router, "Any traffic hitting public port X must be sent straight to private device Y on port Z."

Standard Use Cases

- Hosting Servers: Running a web server (Port 80/443), media server (Plex, Port 32400), or file server (FTP, Port 21) at home.\
  
- Gaming: Hosting multiplayer servers (e.g., Minecraft on Port 25565) to let friends connect.

- Remote Access: Accessing a home computer or security camera via SSH (Port 22) or RDP (Port 3389).



  How to Configure Port Forwarding
  1. Assign a Static IP: Set a static IP on the target device so its network address never changes.
  
  2. Access Router Admin: Open a browser, type your router's gateway IP (e.g., 192.168.1.1), and log in.
  
  3. Locate the Settings: Look for a menu named Port Forwarding, NAT, or Virtual Server.
     
  4. Create a Rule: Enter the required details:
        1.Service Name: Custom label (e.g., MyWebServer).Protocol: TCP, UDP, or Both (HTTP uses TCP).
     
        2.External Port: The port the outside world will target (e.g., 80).
     
        3.Internal IP: The static IP of your local device (e.g., 192.168.1.20).
     
        4.Internal Port: The port the local service listens on (usually matches the external port, e.g., 80).
     
        5.Save and Apply: Save the settings and reboot the router if prompted
