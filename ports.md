PORTS

Perhaps aptly titled by their name, ports are an essential point in which data can be exchanged. 
Think of a harbour and port. Ships wishing to dock at the harbour will have to go to a port compatible with the dimensions and the facilities located on the ship. 
When the ship lines up, it will connect to a port at the harbour. Take, for instance, that a cruise liner cannot dock at a port made for a fishing vessel and vice versa.

 

These ports enforce what can park and where — if it isn't compatible, it cannot park here. 
Networking devices also use ports to enforce strict rules when communicating with one another. 
When a connection has been established (recalling from the OSI model's room), any data sent or received by a device will be sent through these ports. 
In computing, ports are a numerical value between 0 and 65535 (65,535).

 

Because ports can range from anywhere between 0-65535, there quickly runs the risk of losing track of what application is using what port. 
A busy harbour is chaos! Thankfully, we associate applications, software and behaviours with a standard set of rules. 
For example, by enforcing that any web browser data is sent over port 80, software developers can design a web browser such as Google Chrome or Firefox to interpret the data the same way as one another.

 

This means that all web browsers now share one common rule: data is sent over port 80. How the browsers look, feel and easy to use is up to the designer or the user's decision.

 

While the standard rule for web data is port 80, a few other protocols have been allocated a standard rule. 
Any port that is within 0 and 1024 (1,024) is known as a common port. Let's explore some of these other protocols below:


Protocol	                                              Port Number	               Description

File Transfer Protocol (FTP)	                             21	                     This protocol is used by a file-sharing application built on a client-server model, meaning you can download files from a central location.

Secure Shell (SSH)	                                       22	                     This protocol is used to securely login to systems via a text-based interface for management.

HyperText Transfer Protocol (HTTP)	                       80	                     This protocol powers the World Wide Web (WWW)! Your browser uses this to download text, images and videos of web pages.

HyperText Transfer Protocol Secure (HTTPS) 	               443	                   This protocol does the exact same as above; however, securely using encryption.

Server Message Block (SMB)	                               445	                   This protocol is similar to the File Transfer Protocol (FTP); however, as well as files, SMB allows you to share devices like printers.

Remote Desktop Protocol (RDP)	                             3389                  	 This protocol is a secure means of logging in to a system using a visual desktop interface (as opposed to the text-based limitations of the SSH protocol).



- nc 192.162.1.1 80

  The command nc 192.162.1.1 80 uses the Netcat utility to attempt a direct TCP connection to the IP address 192.162.1.1 on port 80 (HTTP).



  Expected Outcomes & Meanings
  
  Blank cursor / No error: The connection is successful. The remote web server is open and waiting for input. You can manually type an HTTP request (e.g., GET / HTTP/1.1) to fetch data.
  
  Connection refused: The target host is online, but no web server or service is listening on port 80.
  
  Connection timed out: The host is offline, the IP does not exist, or a firewall is silently dropping your connection packets.
