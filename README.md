#Cybersecurity Web Portal Lab: Building and Investigating a Vulnerable Website
##Overview
To strengthen my hands-on cybersecurity skills, I built and analyzed a small intentionally vulnerable web application in a local environment. The goal was to experience both sides of web security: first as the developer building the application, then as the attacker identifying weaknesses. This project gave me the opportunity to practice and connect several concepts I’ve been learning throughout my self-directed cybersecurity journey, including: 
###Web & Networking
- HTTP request/response lifecycle
- Status codes (200, 404, etc.)
- Localhost (127.0.0.1) and port-based hosting
- Basic web server behavior
###Frontend Development
- HTML page structure
- JavaScript-based client-side logic
- Form handling and input validation
###Security Fundamentals
- CIA triad (confidentiality, integrity, availability)
- OWASP Top 10
- Authentication weaknesses (client-side authentication)
- Sensitive data exposure (comments, scripts, hidden files)
- Attack surface awareness
- Reconnaissance & Analysis
###Manual source code inspection
- Browser DevTools (network requests, headers)
- Hidden page discovery and enumeration concepts
- Basic directory brute forcing (Gobuster)
Project Setup
 Application: Static website (“The Cat Corner”)
 Languages: HTML, JavaScript
 Code Editor: Visual Studio Code
 Version Control: Git, GitHub
 Local Hosting: Python HTTP server (python3 -m http.server 8080)
 Accessed via: http://127.0.0.1:8080
Site Structure/Flow
Users start at the home page: index.html
Navigation is provided to a login page: login.html
Successful login redirects to a “success” page: success.html
Hidden page (secret.html) exists outside the normal navigation flow 
Key Design Characteristics
Fully static frontend (HTML + JavaScript only)
No backend or database authentication system
Login validation is hardcoded in client-side JavaScript
Includes intentionally hidden page for discovery testing
Security Investigation
After building the site, I shifted into an attacker mindset and analyzed it for common vulnerabilities.
1. HTTP Request Analysis
Procedure
Using the Browser Developer Tools (Network tab), I inspected the HTTP requests generated while interacting with the site. I disabled browser caching so each request would be fetched directly from the server, which allowed me to observe real-time responses instead of cached results. I also navigated through different pages, reloaded content, and modified URLs to see  how the server responded under valid and invalid inputs. This helped me better understand the request/response flow and how the application behaves from a network perspective. I used the Headers and Response panels to look beyond just page content since they provide additional context about how each request is handled and what the server returns.
Through this, I was able to generate and observe the following HTTP status codes:


