### Internet

The internet is a global network of interconnected computers and servers that allows people to communicate, share information, and access resources from anywhere in the world.

It was created in the 1960s by the US Department of Defense as a way to connect computers and share information between researchers and scientists.

In simplest terms, the Internet is a global network comprised of smaller networks that are interconnected using standardized communication protocols.

- **Application layer (highest)** – concerned with the data(URL, type, etc.). This is where HTTP/HTTPS (used for web browsing), SMTP (email transmission), FTP (file transfers), DNS (domain name resolution).
 
- **Transport layer** – responsible for end-to-end communication over a network. TCP (Transmission Control Protocol, ensures reliable data delivery), UDP (User Datagram Protocol, used for faster, connectionless communication).

- **Network layer** – provides data route.IP (Internet Protocol for routing data), ICMP (used for diagnostic tools like ping), OSPF (Open Shortest Path First for routing).

### World Wide Web

The Web is a major means of access information on the Internet. The documents are formatted in a markup language called HTML, or “HyperText Markup Language”, which supports a number of features including links and multimedia

To link hypertext to the Internet, we need: 

    The markup language, i.e., HTML.
    The transfer protocol, e.g., HTTP.
    Uniform Resource Locator (URL), the address of the resource.

Internet |	Web|
---------|------------|
The Internet is the network of networks and the network allows to exchange of data between two or more computers.  |    The Web is a way to access information through the Internet.                                                                                                                                            	The Web is a way to access information through the Internet.
It is also known as the Network of Networks.| 	The Web is a model for sharing information using the Internet.                                                                                                                                                                                                                  
The Internet is a way of transporting information between devices.| 	The protocol used by the web is HTTP.
Accessible in a variety of ways. |	The Web is accessed by the Web Browser.
Network protocols are used to transport data. |	Accesses documents and online sites through browsers.
 Global network of networks |	Collection of interconnected websites
Access Can be accessed using various devices |	Accessed through a web browser
Connectivity Network of networks that allows devices to communicate and exchange data |	Connectivity Allows users to access and view web pages, multimedia content, and other resources over the Internet
Protocols TCP/IP, FTP, SMTP, POP3, etc. |	Protocols HTTP, HTTPS, FTP, SMTP, etc.
Infrastructure Consists of routers, switches, servers, and other networking hardware 	|Infrastructure Consists of web servers, web browsers, and other software and hardware
 Used for communication, sharing of resources, and accessing information from around the world 	|Used for publishing and accessing web pages, multimedia content, and other resources on the Internet
No single creator |	Creator Tim Berners-Lee
Provides the underlying infrastructure for the Web, email, and other online services 	|Provides a platform for publishing and accessing information and resources on the Internet

### URI

 URI stands for ‘Uniform Resource Identifier’.
 
 A URI can be a **name, locator, or both for an online resource** whereas a URL is just the **locator**. 
 
 URLs are a subset of URIs. 
 
 A URL is a human-readable text that was designed to replace the numbers (IP addresses) that computers use to communicate with servers.

A URL consists of a protocol, domain name, and path (which includes the specific subfolder structure where a page is located) like-

       protocol://WebSiteName.topLevelDomain/path

1.Protocol – HTTP or HTTPS.

2.WebSiteName – geeksforgeeks, google etc.

3.topLevelDomain- .com, .edu, .in etc.

4.path- specific folders and/or subfolders that are on a given website.

## Internet

### Client side

when we type a URL like www.google.com, the browser converts it into a file containing
    GET /HTTP/1.1
    1. GET means we are requesting some data from the server
    
    2. HTTP refers to a protocol 
    
    3. 1.1 refers to the version of the HTTP request
    
    Host: www.google.com
### Server side

the server receives the binary code and decodes it and sends the response
    HTTP/1.1 200 ok (where 200 ok is the status)
    Content-type:type/HTML
    Body of page

### Protocols

**HTTP (Hypertext Transfer Protocol)** is the primary protocol used for communication on the web. Clients send HTTP requests to servers, which respond with HTTP responses. 

**HTTPS (HTTP Secure)** is a secure version of HTTP that encrypts data transferred between the client and server.

## Web programming

### Client side

1. HTML (Hypertext Markup Language)

2. CSS (Cascading Style Sheets)

3. JavaScript

4. Web APIs (e.g., DOM, Canvas, Web Storage)

5. Frameworks and Libraries:

6. TypeScript

### Server side

1. PHP (Hypertext Preprocessor)

2. Node.js (JavaScript Runtime)

3. Python, perl, Ruby

4. Swift, Rust

5. Java

6. C# (C-Sharp)

7. Go (Golang)

8. SQL (Structured Query Language),PostgreSQL, MongoDB,

9. Server environment -  Apache, Nginx, or Microsoft IIS
