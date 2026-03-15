# Common Networking Ports – Quick Revision

1️. FTP – File Transfer Protocol
Port: 21
Purpose: Used to transfer files between client and server.
Example:
You upload website files from your computer to a server.
⚠️ Security note:
FTP does not encrypt data
Attackers can sniff usernames and passwords.

2️. SSH – Secure Shell
Port: 22
Purpose: Secure remote login to a system
Example:
Admin connects to a Linux server remotely.
⚠️ Security note:
Often targeted by brute force attacks.

3️. Telnet
Port: 23
Purpose: Remote login to devices.
⚠️ Problem:
No encryption
Credentials sent in plain text
Because of this, SSH replaced Telnet.

4️. SMTP – Simple Mail Transfer Protocol
Port: 25
Purpose: Sending emails between mail servers.
Example:
Gmail sending mail to Outlook server.

5️. DNS – Domain Name System
Port: 53
Purpose: Converts domain names → IP addresses
Example:
google.com → 142.250.x.x
Without DNS we would need to remember IP addresses for every website.

6️. HTTP – HyperText Transfer Protocol
Port: 80
Purpose: Used to load websites
Example:
http://example.com
⚠️ Problem:
Data not encrypted

7️. HTTPS – Secure HTTP
Port: 443
Purpose: Secure web browsing
Example:
https://google.com
Uses:
SSL/TLS encryption
So attackers cannot easily read the data.

8️. POP3 – Post Office Protocol
Port: 110
Purpose: Download emails from server to client
Example:
Outlook downloading mail to your laptop.

9️. IMAP – Internet Message Access Protocol
Port: 143
Purpose: Access emails directly from server
Difference from POP3:
Emails stay on the server.
Example:
Gmail on phone + laptop simultaneously.

10. RDP
Port: 3389
Service: Remote Desktop Protocol
Use:Remotely control Windows systems
⚠️ Security Risk:
Brute force attacks
Stolen credentials
Very common in corporate network breaches.

12. SMB
Port: 445
Service: Server Message Block
Use: File sharing in Windows
⚠️ Very famous attack:
WannaCry ransomware
Because it exploited SMB vulnerability.

🧠 Super Fast Memory Trick
Port	Protocol	Function
21	FTP	File transfer
22	SSH	Secure remote login
23	Telnet	Remote login (insecure)
25	SMTP	Send email
53	DNS	Domain → IP
80	HTTP	Web browsing
110	POP3	Download email
143	IMAP	Access email
443	HTTPS	Secure web
445	SMB	File sharing
3389	RDP	Remote desktop
3306	MySQL	Database

📊 Port Categories (important concept)
Range	Type
0 – 1023	Well-known ports
1024 – 49151	Registered ports
49152 – 65535	Dynamic / private ports

ex: Port 12345 falls in → Registered ports.

# Ports Commonly Used by Malware / Backdoors
1️⃣ Port 12345
Malware: NetBus
Purpose: Remote control of infected system
Attacker abilities:
Control keyboard/mouse
Open programs
Access files

2️⃣ Port 27374
Malware: SubSeven Trojan
Capabilities:
Remote control of victim machine
Webcam access
File stealing

3️⃣ Port 31337
Malware: Back Orifice
Interesting fact:
31337 = "elite" in hacker slang (leet)
Used for:
Backdoor access to Windows systems.

4️⃣ Port 4444
Often used by:
Metasploit payloads
Example:
When attackers exploit a system, they sometimes create a reverse shell on port 4444.

5️⃣ Port 5555
Used by some Android debugging services
Sometimes abused by malware to communicate with infected devices.

6️⃣ Port 6667
IRC communication port
Many botnets use IRC servers for command and control (C2).

7️⃣ Port 8080
Alternative HTTP port
Attackers may run:
malicious web servers
phishing pages
hidden admin panels

8️⃣ Port 9001
Used by Tor network
Sometimes attackers hide traffic through Tor nodes.

Port	Malware / Use
12345	NetBus
27374	SubSeven
31337	Back Orifice
4444	Metasploit shell
5555	Android debug abuse
6667	IRC botnet control
8080	Alternative web server
9001	Tor communication

# TCP vs UDP – Quick Revision
1️⃣ TCP (Transmission Control Protocol)
TCP is a connection-oriented protocol.
That means a connection must be established before sending data.
Key Features
Reliable communication
Data arrives in correct order
Error checking
Packet retransmission if lost

Example Uses
Application	Why TCP
Web browsing (HTTP/HTTPS)	Needs reliable delivery
Email (SMTP, IMAP)	Data must arrive correctly
File transfer (FTP)	Cannot lose files

How TCP Works (Simple Steps)
Connection established
Data sent
Receiver confirms receipt
This is called the 3-way handshake:
SYN
SYN-ACK
ACK
So TCP = Reliable communication.

2️⃣ UDP (User Datagram Protocol)
UDP is a connectionless protocol.
That means data is sent directly without establishing a connection.
Key Features
Faster than TCP
No connection setup
No guaranteed delivery
No packet ordering

Example Uses
Application	Why UDP
Video streaming	Speed matters more than perfection
Online gaming	Low latency needed
DNS	Quick responses

Example:
If a video packet is lost, the video just skips that frame instead of waiting.

⚡ Simple Difference Table
Feature	TCP	UDP
Connection	Connection-oriented	Connectionless
Reliability	Reliable	Unreliable
Speed	Slower	Faster
Error checking	Yes	Minimal
Packet order	Maintained	Not guaranteed

🧠 Easy Memory Trick
TCP → “Trust & Check Protocol”
Reliable
Confirmed delivery
UDP → “Ultra-fast Data Protocol”
Fast
No guarantee

# What is HTTP?
HTTP (HyperText Transfer Protocol) is the protocol used for communication between a client and a web server.

Example flow:
Browser sends request
Server processes it
Server sends response

Example:
Client (browser) → HTTP Request → Server
Server → HTTP Response → Client
Common port:
HTTP → 80
HTTPS → 443
📩 HTTP Request Structure
A basic HTTP request contains:
1️⃣ Method (GET / POST)
2️⃣ URL
3️⃣ Headers
4️⃣ Body (optional)

Example request:
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Chrome
📥 GET Request
GET is used to retrieve data from the server.
Example: opening a webpage.
Example
GET /products?id=10 HTTP/1.1
Host: example.com
Here:
/products → resource
id=10 → query parameter
Characteristics
Used for fetching data
Parameters appear in URL
Can be cached
Has length limits

Example URL:
https://example.com/search?q=shoes

📤 POST Request
POST is used to send data to the server.
Example:
Login
Form submission
Uploading files
Example
POST /login HTTP/1.1
Host: example.com
Content-Type: application/json

{
 "username":"indu",
 "password":"12345"
}
Characteristics
Data sent in request body
Not visible in URL
Used for creating or updating data
Supports large data

⚡ GET vs POST (Quick Table)
Feature	GET	POST
Purpose	Retrieve data	Send data
Data location	URL	Request body
Data visible in URL	Yes	No
Cacheable	Yes	Usually no
Data size	Limited	Large

# HTTP Status
HTTP status codes are super easy once you see the pattern. They tell the browser what happened to the request.

Whenever a browser sends a request, the server replies with a status code.

Example response:
HTTP/1.1 200 OK
Here 200 is the status code.
🌐 Categories of HTTP Status Codes
Status codes are grouped by the first digit.
Code Range	Meaning
1xx	Informational
2xx	Success
3xx	Redirection
4xx	Client error
5xx	Server error

✅ 2xx — Success
These mean the request worked successfully.
200 — OK
Most common response.
Example:
You open a webpage and it loads successfully.
200 OK
201 — Created
Used when new data is created.
Example:
Creating a new user account
Uploading a file via API

🔄 3xx — Redirection
The client must go somewhere else.
301 — Moved Permanently
The page has permanently moved.
Example:
http://site.com → https://site.com
Search engines update the URL.
302 — Found (Temporary Redirect)
Temporary redirection.
Example:
Login redirect
Temporary maintenance page

❌ 4xx — Client Errors
These mean the problem is on the client side.
400 — Bad Request
The server cannot understand the request.
Example:
Invalid parameters
Broken request format
401 — Unauthorized
Authentication is required.
Example:
Accessing a protected API without login.
403 — Forbidden
The server understands the request but refuses access.
Example:
Trying to access admin page without permission.
404 — Not Found
The resource does not exist.
Example:
example.com/randompage
Very common error.

💥 5xx — Server Errors
These mean the server failed.
500 — Internal Server Error
Generic server failure.
Example:
Application crash
Backend code error
502 — Bad Gateway
One server received an invalid response from another server.
Often seen with reverse proxies.
503 — Service Unavailable
Server cannot handle the request.
Example:
Server overload
Maintenance.

🧠 Quick Memory Trick
Think:
200 → Good
300 → Go somewhere else
400 → Your mistake
500 → Server mistake

🎯 Most Important Codes (Remember These)
Code	Meaning
200	OK
201	Created
301	Permanent redirect
302	Temporary redirect
400	Bad request
401	Unauthorized
403	Forbidden
404	Not found
500	Server error 
503	Service unavailable
🔐 Cybersecurity Tip
Security testers look carefully at status codes.
Example:
403 → admin page exists but blocked
404 → page does not exist
This helps attackers discover hidden endpoints.

505 — HTTP Version Not Supported

Meaning:
The server does not support the HTTP version used in the request.

Example response:
HTTP/1.1 505 HTTP Version Not Supported
Example Situation
If a client sends a request using an unsupported HTTP version, the server rejects it.

Example request:
GET /index.html HTTP/3.0
Host: example.com
If the server only supports HTTP/1.1, it may return:
505 HTTP Version Not Supported
Simple Explanation
Client used wrong or unsupported HTTP version
Server cannot process the request

Exam-Ready Definition
505 (HTTP Version Not Supported):
The server refuses the request because it does not support the HTTP protocol version used by the client.

🧠 Quick Context
Code	Meaning
500	Internal server error
502	Bad gateway
503	Service unavailable
504	Gateway timeout
505	HTTP version not supported

## What Are HTTP Headers?

HTTP headers are key–value pairs sent in a request or response that provide extra information about the communication.
They help the server and client understand:
who is sending the request
what type of data is expected
authentication details
cookies/session info
Example request:
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Chrome
Accept: text/html
Each line after the request line is a header.

📩 Important HTTP Request Headers
1️⃣ Host
Purpose: Specifies the domain name of the server.
Example:
Host: example.com
Why it matters:
A server can host multiple websites on the same IP.
The Host header tells which website you want.

2️⃣ User-Agent
Purpose: Identifies the client (browser or application) sending the request.
Example:
User-Agent: Mozilla/5.0 Chrome/120
Servers use this to:
detect device type
adjust webpage layout
⚠️ Security note:
Attackers sometimes fake User-Agent values.

3️⃣ Accept
Purpose: Tells the server what content types the client can receive.
Example:
Accept: text/html
Other examples:
application/json
image/png

4️⃣ Authorization
Purpose: Sends authentication credentials.
Example:
Authorization: Bearer token123
Used in:
APIs
login systems
secure services

5️⃣ Cookie
Purpose: Sends stored session data to the server.
Example:
Cookie: sessionid=abc123
Cookies help websites:
keep users logged in
track sessions
⚠️ In cybersecurity, stolen cookies can allow session hijacking.

📤 Important Response Headers
Content-Type
Tells the browser what type of data the server is sending.
Example:
Content-Type: text/html
Other examples:
application/json
image/jpeg
Set-Cookie
Server sends cookies to store in the browser.
Example:
Set-Cookie: sessionid=abc123
Server
Tells what web server software is running.
Example:
Server: Apache
⚠️ Attackers may use this info to find server vulnerabilities.

🧠 Quick Memory Table
Header	Purpose
Host	Domain of the server
User-Agent	Client information
Accept	Data format client accepts
Authorization	Authentication credentials
Cookie	Session data
Content-Type	Type of response data
Set-Cookie	Server sends cookie

Step-by-Step: How a Login Request Works
1️⃣ User Opens Login Page
When you open a login page, the browser sends a GET request to fetch the page.
Example:
GET /login HTTP/1.1
Host: example.com
User-Agent: Chrome
Accept: text/html

What the server does
Finds the login page
Sends it back to the browser.

Server response:
HTTP/1.1 200 OK
Content-Type: text/html
Meaning:
✅ Request successful
📄 Login page is returned.

2️⃣ User Enters Username and Password
You type:
username: sri
password: 12345

Then press Login.
The browser sends a POST request to submit the credentials.
Example:
POST /login HTTP/1.1
Host: example.com
Content-Type: application/x-www-form-urlencoded
username=indu&password=12345

Why POST?
Because sensitive data should not appear in the URL.

3️⃣ Server Verifies Credentials
The server checks the database:
username = sri
password = 12345
Two possible outcomes:
Correct credentials
Server sends:
HTTP/1.1 200 OK
Set-Cookie: sessionid=abc123
What happens:
Server creates a session
Sends a cookie to the browser.

4️⃣ Browser Stores Session Cookie
Browser saves:
sessionid = abc123
Now every request to the website includes:
Cookie: sessionid=abc123
This tells the server:
👉 "This user is already logged in."
So you don’t need to log in again.

5️⃣ Accessing Dashboard
Now browser sends:
GET /dashboard HTTP/1.1
Host: example.com
Cookie: sessionid=abc123
Server checks the session and replies:
HTTP/1.1 200 OK
Dashboard loads successfully.

🔐 Cybersecurity Angle
Attackers often target login flows.

Common attacks include:

1️⃣ Brute Force
Trying many passwords.
Example tools:
Hydra
Burp Intruder

2️⃣ SQL Injection
Example malicious login input:
username: admin' --
password: anything
This may bypass authentication if the system is vulnerable.

3️⃣ Session Hijacking
If attackers steal:
sessionid=abc123
They can impersonate the user.
That’s why security flags are used:
HttpOnly
Secure
SameSite

🧠 Full Flow Summary
1. GET /login → server returns login page
2. User enters credentials
3. POST /login → sends username & password
4. Server verifies user
5. Server sends session cookie
6. Browser sends cookie with future requests

# DNS (Domain Name System)
converts domain names → IP addresses.
Humans remember names like:
google.com
But computers communicate using IP addresses:
142.250.x.x
So DNS acts like the internet’s phonebook 📖.
