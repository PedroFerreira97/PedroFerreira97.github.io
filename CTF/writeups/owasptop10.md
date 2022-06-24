# Owasp top 10

## Introduction


Injection
Broken Authentication
Sensitive Data Exposure
XML External Entity
Broken Access Control
Security Misconfiguration
Cross-site Scripting
Insecure Deserializat
Components with Known Vulnerab
Insufficent Logging & Monitoring

## Injection

Injection flaws are very common in applications today. These flaws occur because user controlled input is interpreted as actual commands or parameters by the application.

## OS Command Injection

Command Injection occurs when server-side code (like PHP) in a web application makes a system call on the hosting machine.  It is a web vulnerability that allows an attacker to take advantage of that made system call to execute operating system commands on the server. 
 
1. ls
2. cat /etc/passwd
3. id
4. cat /etc/passwd (tip /X/sbin/X )
5. lsb_release -a command
6. ls /etc/update-motd.d
7. cat /etc/update-motd.d/00-header

## Broken Authentication

Authentication and session management constitute core components of modern web applications. Authentication allows users to gain access to web applications by verifying their identities. The most common form of authentication is using a username and password mechanism.

1. Register
2. Login
3. Check Cookie Token
4. log out
5. register with darren x2
6. login with darren you created x2
7. Now repear 5 and 6 with arthur

## Sensitive Data Exposure

When a webapp accidentally divulges sensitive data, we refer to it as "Sensitive Data Exposure". This is often data directly linked to customers (e.g. names, dates-of-birth, financial information, etc), but could also be more technical information, such as usernames and passwords. 

1. Go to /admin , check de source code
2. Go to the path
3. Download .db file
4. Can open with sqlitebrower if u prefer
5. Get admin hash
6. Got to crackstation to crack it
7. Just log with admin and password

## XML Eternal Entity

An XML External Entity (XXE) attack is a vulnerability that abuses features of XML parsers/data. It often allows an attacker to interact with any backend or external systems that the application itself can access and can allow the attacker to read the file on that system.

- XML -> Extensible Markup Language
- no
- yes
- xml prolog

1. DTD

- !ELEMENT
- !DOCTYPE
- !ENTITY

2. XEE payload
 
<!DOCTYPE replace [<!ENTITY name "feast"> ]>
 <userInfo>
   <firstName>falcon</firstName>
   <lastName>&name;</lastName>
  </userInfo>
  
<?xml version="1.0"?>
<!DOCTYPE root [<!ENTITY read SYSTEM 'file:///etc/passwd'>]>
<root>&read;</root>

3. Exploiting

- falcon
- /home/falcon/.ssh/id_rsa
- use the payload with the path os ssh key

## Broken Access Control

Websites have pages that are protected from regular visitors, for example only the site's admin user should be able to access a page to manage other users. If a website visitor is able to access the protected page/pages that they are not authorised to view, the access controls are broken.

1. IDOR

- login
- check note 0

## Security Misconfiguration

Security Misconfigurations are distinct from the other Top 10 vulnerabilities, because they occur when security could have been configured properly but was not.

- Try default credentialsi (Tip search PassiveNotes on a search engine)

## Cross-site Scripting

Cross-site scripting, also known as XSS is a security vulnerability typically found in web applications. It’s a type of injection which can allow an attacker to execute malicious scripts and have it execute on a victim’s machine.

    Stored XSS - the most dangerous type of XSS. This is where a malicious string originates from the website’s database. This often happens when a website allows user input that is not sanitised (remove the "bad parts" of a users input) when inserted into the database.
    Reflected XSS - the malicious payload is part of the victims request to the website. The website includes this payload in response back to the user. To summarise, an attacker needs to trick a victim into clicking a URL to execute their malicious payload.
    DOM-Based XSS - DOM stands for Document Object Model and is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style and content. A web page is a document and this document can be either displayed in the browser window or as the HTML source.

- <script>alert(“Hello World”)</script>
- <script>alert(window.location.hostname)</script>
- log in -> stored  xss -> <h1> hi </h1>
- <script>alert(document.cookies)</script>
- <script>document.querySelector('#thm-title').textContent = 'I am a hacker'</script>

## Insecure Deserialization

Insecure Deserialization is a vulnerability which occurs when untrusted data is used to abuse the logic of an application. (Acunetix., 2017)

- Google
- denial of service

1. objects -> A Behaviour
2. De(Serialization) -> binary
3. Cookies -> webapp.com/login , https

- Register -> Log in
- f12 -> Storage -> cookies
- decrypt cookie
- change user and usertype to admin

4. Code Execution

Follow the guide

## Components With Known Vulnerabilities

Occasionally, you may find that the company/entity that you're pen-testing is using a program that already has a well documented vulnerability.

Get component and version -> SearchSploit or other -> Get Exploit -> Run Exploit

- dirsearch -u MachineIp -w raft-large
- got to the index of /X
- search exploit  (tip: the exploit i used need to delete lines before comments)
- run exploit vs machine

## Insufficient Logging and Monitoring 

When web applications are set up, every action performed by the user should be logged. Logging is important because in the event of an incident, the attackers actions can be traced.

- check the unauthorised logs
- someone tried to brute force the login

#Done

