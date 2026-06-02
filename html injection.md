HTML INJECTION
HTML Injection is a client-side security vulnerability that occurs when a web application accepts user input and renders it directly onto a webpage without proper validation or escaping. 
This allows attackers to manipulate the visible structure and layout of the page by introducing arbitrary HTML tags



HTML Injection vs. Cross-Site Scripting (XSS)
While HTML injection and Cross-Site Scripting (XSS) share identical delivery pathways and exploit the same lack of input handling, they differ in execution capabilities:

HTML Injection: 
Limited strictly to injecting markup tags (such as <h1>, <div>, <img>, or <a>) to change the visual interface or redirect users.
Cross-Site Scripting (XSS): Focuses on inserting executable JavaScript code to hijack sessions, read cookies, or steal direct browser permissions.
