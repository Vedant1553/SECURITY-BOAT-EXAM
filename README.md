# SECURITY-BOAT-EXAM
Q.1.Explain the DOM XSS vulnerability.
Answer : 
DOM XSS,known as"type-0 XSS," is a type of Cross-Site Scripting (XSS) vulnerability that allows attackers to inject malicious code into a web page, but with a twist. Unlike other XSS vulnerabilities where the
code is sent to the server and reflected back, DOM XSS attacks happen entirely within the client's browser, manipulating the Document Object Model (DOM) instead.
An attacker may use several DOM objects to create a Cross-site Scripting attack. The most popular objects from this perspective are document.url, document.location, and document.referrer.

Q.2.What is the difference between session management, session hijacking, and session fixation?
Answer:
Session management:
It is the overall process of controlling a user's interaction with a website over time. It involves creating, maintaining, and terminating sessions.
It includes tasks like generating and assigning session IDs, storing user data securely, and invalidating sessions after inactivity or logout.
Secure session management is crucial to prevent unauthorized access and attacks like hijacking and fixation.

Session hijacking:
Session hijacking refers to the malicious act of taking control of a user’s web session. A session, in the context of web browsing, is a series of interactions between two communication endpoints, sharing a 
unique session token to ensure continuity and security.
This is an attack where someone steals a valid session ID and uses it to impersonate the legitimate user.
Attackers can steal session IDs through various means, like sniffing network traffic, phishing emails, or XSS vulnerabilities.
Once they have the ID, they can access the user's account and perform actions like stealing data, changing settings, or making purchases.

Session fixation:
This is another attack, but instead of stealing an existing session, the attacker forces the victim to use a specific session ID.
This often happens by sending the victim a malicious link or manipulating page elements to inject the desired session ID.
When the victim authenticates on the pre-determined session, the attacker can immediately take control, as the application already considers them logged in.

Q.3.While testing for XSS, an application is filtering 'alert' keywords and their encoded payloads. Explain how you would bypass this?
Answer:
XSS filter evasion refers to a variety of methods used by attackers to bypass cross-site scripting (XSS) filters. There are many ways to inject malicious JavaScript into web page code executed by the client, 
and with modern browsers, attackers must not only exploit an application vulnerability but also evade any input validation performed by the application and server, and fool complex browser filters.

Q.4.Explain JWT attacks.
Answer:JSON Web Tokens (JWTs) are a popular way to authenticate users and authorize access in web applications. While convenient, they are not without vulnerabilities. Attackers can exploit these 
vulnerabilities to gain unauthorized access, steal data, or impersonate users. 
JSON is less verbose than XML, so when it is encoded, a JWT is smaller than a SAML token. This makes JWT a good choice to be passed in HTML and HTTP environments.
JSON parsers are common in most programming languages because they map directly to objects. Conversely, XML doesn't have a natural document-to-object mapping. This makes it easier to work with JWT than SAML
assertions.

Q.5.How would you bypass the authorization schema on a login page?
Answer:Ethical bug bounty programs: Many companies offer bug bounty programs where you can earn rewards for finding and reporting vulnerabilities responsibly.
Capture the Flag (CTF) competitions: These are fun and challenging puzzles that test your security skills in a controlled environment.
Vulnerability research: You can delve into researching and understanding different types of vulnerabilities without exploiting them in real-world systems.
Penetration testing training: Enroll in courses or certifications that teach you the safe and legal methods of penetration testing with proper authorization and consent.

Q.6.What is the difference between brute forcing and rate-limiting?
Answer:A strongly secured web application sets password requirements that help mitigate brute force attacks, but large attacks can still consume many network resources. Rate limiting blocks these attacks to 
save system resources.

Q.7.What is Direct Object References? What is its use in web application security? Is it secure or insecure?
Answer:Direct Object References
In web applications, Direct Object References (DORs) refer to mechanisms that identify and access specific entities like user profiles, files, or database records. These references typically come in the form 
of unique identifiers (IDs), filenames, or other descriptive strings embedded within URLs, query parameters, or hidden form fields. While they can be convenient for developers, their use in security contexts 
requires careful consideration.
Application security
User Accounts: Managing individual user profiles often involves referencing them by ID in URLs or forms (e.g., "/profile/123").
Shopping Carts: Items might be referenced by ID for adding, removing, or editing them (e.g., "cart?item=456").
Content Management Systems: Accessing specific articles or pages might utilize IDs in URLs (e.g., "/news/article/987").
Secure vs. Insecure:
Insecure DOR: Any situation where predictable identifiers are directly exposed and used for access without proper authorization checks.
Secure DOR: When identifiers are combined with strong access control mechanisms, such as role-based access control (RBAC) or identity-based authorization, to ensure users only access authorized resources. 
Additionally, security practices like input validation and sanitization can mitigate vulnerabilities.

Q.8.What is the CSV injection vulnerability? If the macros are enabled, how do you perform CSV injection?
Answer:CSV Injection, also known as Formula Injection, occurs when websites embed untrusted input inside CSV files.
Hijacking the user’s computer by exploiting vulnerabilities in the spreadsheet software, such as CVE-2014-3524.
Hijacking the user’s computer by exploiting the user’s tendency to ignore security warnings in spreadsheets that they downloaded from their own website.
Exfiltrating contents from the spreadsheet, or other open spreadsheets.

Q.9.What are the requirements for a CSRF attack?
Answer:Authentication based solely on cookies: The application must rely solely on cookies to identify and authenticate users. If other factors like multi-factor authentication are present, it makes the attack
harder to exploit.
Unpredictable request parameters: Attackers need to be able to predict or guess the values of the parameters used in the request they want to forge. This is easier with predictable identifiers or repetitive 
patterns.
State-changing actions: The application must have actions that can be triggered with simple HTTP requests (e.g., GET, POST) and that don't require additional confirmation steps. These actions should also have 
a significant impact on the user or system.
Social engineering: The attacker needs to trick the victim into interacting with the malicious content that triggers the CSRF request. This often involves phishing emails, social media posts, or compromised 
websites.

Q.10.If HTTP only is enabled and we pass a XSS malicious script, can we fetch the session cookie? Justify your answer.
Answer:No, we cannot fetch the session cookie even if an XSS script is injected and executed on the victim's browser if the HttpOnly flag is enabled on the cookie. 
The HttpOnly flag is a security feature set on a cookie during its creation on the server.
When this flag is set, the cookie becomes inaccessible to client-side scripting languages like JavaScript in the victim's browser.
This prevents malicious scripts injected through XSS from accessing and stealing the cookie information, even if they run within the browser environment.
Even if the malicious script injected through XSS tries to access the HttpOnly cookie using methods like document.cookie, it will receive an empty string or fail entirely.
This restriction is enforced by the browser itself, following the HttpOnly flag instruction from the server.
