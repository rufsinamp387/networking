HTML INJECTION
HTML Injection is a client-side security vulnerability that occurs when a web application accepts user input and renders it directly onto a webpage without proper validation or escaping. 
This allows attackers to manipulate the visible structure and layout of the page by introducing arbitrary HTML tags



HTML Injection vs. Cross-Site Scripting (XSS)
While HTML injection and Cross-Site Scripting (XSS) share identical delivery pathways and exploit the same lack of input handling, they differ in execution capabilities:

HTML Injection: 
Limited strictly to injecting markup tags (such as h1, div, img, or a) to change the visual interface or redirect users.
Cross-Site Scripting (XSS): Focuses on inserting executable JavaScript code to hijack sessions, read cookies, or steal direct browser permissions.



Types of HTML Injection

Reflected HTML Injection: The malicious payload is supplied via input components like a search box or a URL query parameter. It is immediately parsed by the browser and only visible to the user interacting with that exact link.

Stored HTML Injection: The injected code is saved directly into the application's database or permanent storage (e.g., a comment section or forum post). Every user who loads that page later will view the injected payload.

DOM-based HTML Injection: The injection occurs entirely client-side when the application's JavaScript unsafely modifies the Document Object Model (DOM) using dynamic inputs.
