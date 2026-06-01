HTTP

What is HTTP? (HyperText Transfer Protocol)

HTTP is what's used whenever you view a website, developed by Tim Berners-Lee and his team between 1989-1991.
HTTP is the set of rules used for communicating with web servers for the transmitting of webpage data, whether that is HTML, Images, Videos, etc.

What is HTTPS? (HyperText Transfer Protocol Secure)

HTTPS is the secure version of HTTP. 

HTTPS data is encrypted so it not only stops people from seeing the data you are receiving and sending, but it also gives you assurances that you're talking to the correct web server and not something impersonating it.

 
REQUEST AND RESPONSES

When we access a website, your browser will need to make requests to a web server for assets such as HTML, Images, and download the responses. Before that, you need to tell the browser specifically how and where to access these resources, this is where URLs will help.

What is a URL? (Uniform Resource Locator)

If you’ve used the internet, you’ve used a URL before. A URL is predominantly an instruction on how to access a resource on the internet. The below image shows what a URL looks like with all of its features (it does not use all features in every request).


Scheme: This instructs on what protocol to use for accessing the resource such as HTTP, HTTPS, FTP (File Transfer Protocol).

User: Some services require authentication to log in, you can put a username and password into the URL to log in.

Host: The domain name or IP address of the server you wish to access.

Port: The Port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS, but this can be hosted on any port between 1 - 65535.

Path: The file name or location of the resource you are trying to access.

Query String: Extra bits of information that can be sent to the requested path. For example, /blog?id=1 would tell the blog path that you wish to receive the blog article with the id of 1.

Fragment: This is a reference to a location on the actual page requested. This is commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.


HTTP METHOD

HTTP methods are a way for the client to show their intended action when making an HTTP request. There are a lot of HTTP methods but we'll cover the most common ones, although mostly you'll deal with the GET and POST method.

GET Request

This is used for getting information from a web server.

POST Request

This is used for submitting data to the web server and potentially creating new records

PUT Request

This is used for submitting data to a web server to update information

DELETE Request

This is used for deleting information/records from a web server.




HTTP Status Codes:

In the previous task, you learnt that when a HTTP server responds, the first line always contains a status code informing the client of the outcome of their request and also potentially how to handle it. These status codes can be broken down into 5 different ranges:


100-199      -         Information Response	These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. 
                       These codes are no longer very common.
                       
200-299      -         Success	This range of status codes is used to tell the client their request was successful.

300-399      -         Redirection	These are used to redirect the client's request to another resource. This can be either to a different webpage or a different website altogether.

400-499      -         Client Errors	Used to inform the client that there was an error with their request.

500-599      -         Server Errors	This is reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request.





Common HTTP Status Codes:

There are a lot of different HTTP status codes and that's not including the fact that applications can even define their own, we'll go over the most common HTTP responses you are likely to come across:

200 - OK	                           The request was completed successfully.

201 - Created	                      A resource has been created (for example a new user or new blog post).

301 - Moved Permanently	            This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead.

302 - Found	                        Similar to the above permanent redirect, but as the name suggests, this is only a temporary change and it may change again in the near future.

400 - Bad Request	                  This tells the browser that something was either wrong or missing in their request. 
                                    This could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didn't send.
      
401 - Not Authorised               	You are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password.

403 - Forbidden                    	You do not have permission to view this resource whether you are logged in or not.

405 - Method Not Allowed	           The resource does not allow this method request, for example, you send a GET request to the resource /create-account when it was expecting a POST request instead.

404 - Page Not Found	               The page/resource you requested does not exist.

500 - Internal Service Error	       The server has encountered some kind of error with your request that it doesn't know how to handle properly.

503 - Service Unavailable	          This server cannot handle your request as it's either overloaded or down for maintenance.




HEADERS

Headers are additional bits of data you can send to the web server when making requests.

Although no headers are strictly required when making a HTTP request, you’ll find it difficult to view a website properly.

1. Host: Some web servers host multiple websites so by providing the host headers you can tell it which one you require, otherwise you'll just receive the default website for the server.


a. The HTTP Request (What the Browser Sends)Imagine one server with the IP address 192.0.2.1 hosts both cats.com and dogs.com.When you type cats.com into your browser, the browser resolves the domain to             192.0.2.1 via DNS and sends this exact text over the network:httpGET /index.html HTTP/1.1
      
   Host: cats.com
   User-Agent: Mozilla/5.0
   Accept: text/html
   
   If you type dogs.com, it goes to the exact same IP address, but the text changes:httpGET /index.html HTTP/1.1
   
   Host: dogs.com
   User-Agent: Mozilla/5.0



b. The Server Configuration (How it Decides)Inside the web server (like Nginx or Apache), the software is constantly listening for requests. It matches the Host header value against its configuration                blocks.Nginx Example (nginx.conf)nginx# Configuration for Site A

   server {
       listen 80;
       server_name cats.com; # <--- Matches Host: cats.com
       root /var/www/cats_site;
   }
   
   # Configuration for Site B
   server {
       listen 80;
       server_name dogs.com; # <--- Matches Host: dogs.com
       root /var/www/dogs_site;
   }
   
   # Default Fallback Configuration
   server {
       listen 80 default_server;
       server_name _;
       root /var/www/default_site; # <--- Sent if Host header is missing or wrong
   }
      Accept: text/html



c. How to Test it Yourself (Using cURL)You can manually see this behaviour using your computer's terminal. By using curl, you can explicitly change the Host header while targeting the exact same server              IP.

   Requesting Site A:
   curl -H "Host: cats.com" http://192.0.2.

   Server Action: Sees Host: cats.com, looks inside /var/www/cats_site, and returns the cat webpage.

   Requesting Site B:
   curl -H "Host: dogs.com" http://192.0.2 .
   
   Server Action:
   Sees Host: dogs.com, looks inside /var/www/dogs_site, and returns the dog webpage.

   Requesting without a match (or just using the IP):
   curl http://192.0.2 
   
   Server Action: Because the browser or tool sends Host: 192.0.2.1, it fails to match cats.com or dogs.com. The server falls back to its default_server configuration block.
   
2. User-Agent: This is your browser software and version number, telling the web server your browser software helps it format the website properly for your browser and also some elements of HTML, JavaScript and     CSS are only available in certain browsers.

3. Content-Length: When sending data to a web server such as in a form, the content length tells the web server how much data to expect in the web request. This way the server can ensure it isn't missing any        data.
  
4. Accept-Encoding: Tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet.


5. Cookies: A cookie (specifically an HTTP cookie) is a small piece of text data that a website stores on your computer or mobile device when you visit it.
   Because HTTP connections are "stateless"—meaning the web server completely forgets who you are after delivering a webpage—cookies act like a digital identity badge to help the website remember your actions       and preferences over time.

   How It Works (The 3-Step Lifecycle)
   1. The Handout: You visit a website (e.g., shopping online). The website's server sends a response back with a piece of data, using the Set-Cookie header.
      
   2. The Storage: Your web browser saves that small text file locally on your hard drive.
 
   3. The Presentation: Every time you click a new page or refresh that website, your browser automatically attaches that cookie data back to the server. The server reads it and says, "Ah, I remember you!".
      
Main Uses for Cookies

Session Management: Keeping you logged into your account, or remembering items inside your shopping cart as you browse.

Personalisation: Remembering your preferred settings, such as dark mode theme, volume levels, or language choice.

Tracking & Analytics: Recording what pages you clicked on, how long you spent on the site, or what products you looked at.



Common Response Headers

These are the headers that are returned to the client from the server after a request.

1. Set cookie
   
   To set a cookie, the web server includes a Set-Cookie header in its HTTP response to the browser. The browser reads this header and automatically stores the cookie data on the user's device.
   
   1. The HTTP Raw Header Structure
      
      When a user visits a site, the server responds with this exact text structure in the network background
      
      http
      HTTP/1.1 200 OK
      Content-Type: text/html
      Set-Cookie: user_id=98765; Max-Age=3600; Secure; HttpOnly; SameSite=Lax
   2. Setting Cookies via Code (Backend)

      Here is how you write the code to send that header using popular backend languages
      
      Node.js (Express)
      javascript
      
      res.cookie('user_id', '98765', {
      maxAge: 3600000, // Time in milliseconds (1 hour)
      secure: true,    // Sent only over HTTPS
      httpOnly: true,  // Prevents JavaScript access (XSS protection)
      sameSite: 'lax'  // Protects against CSRF attacks
    });


      Python (Flask)
      python

     response = make_response("Cookie is set")
     response.set_cookie(
     'user_id', 
     '98765', 
     max_age=3600,     # Time in seconds (1 hour)
     secure=True, 
     httponly=True, 
     samesite='Lax'
   )



2. Cache-Control: How long to store the content of the response in the browser's cache before it requests it again.

3. Content-Type: This tells the client what type of data is being returned, i.e., HTML, CSS, JavaScript, Images, PDF, Video, etc. Using the content-type header the browser then knows how to process the data.

4. Content-Encoding: What method has been used to compress the data to make it smaller when sending it over the internet.
