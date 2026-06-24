
# **VAPT workflow and testing ethics**

**VAPT - vulnerability assessment and penetration testing**
VA -> to find bugs , analyzing a site and reporting  extensive bugs
PT -> to perform  testing and find bugs , but as a attacker and analyzing the impact the bugs would create if not solved

-- in short , a systematic way to find security issues, misconfiguration, threats etc so that we can solve them

---
**Workflow**
According to industry standards , PTES(Penetration Testing Execution Standard), there are 7 phases - 
- **Pre-engagement:** Defining the scope, rules of engagement, and goals of the test with the client.
- **Intelligence Gathering:** Collecting public and private data about the target organization (e.g., employees, infrastructure, domains).
- **Threat Modeling:** Identifying potential threats, threat actors, and critical assets specific to the organization.
- **Vulnerability Analysis:** Finding flaws and weaknesses in the target's systems, networks, or applications.
- **Exploitation:** Actively attempting to bypass security controls to gain access or privileges.
- **Post-Exploitation:** Evaluating the impact of a successful breach, including data theft and pivoting to other systems.
- **Reporting:** Documenting the entire process, discovered vulnerabilities, and actionable recommendations for the client
----
**Testing Ethics**
 -- moral and legal framework that governs ethical hacking
 basically to ensure that we use our skills to identify and solve security issues without invading privacy and breaking laws. Core ethical principles are:
  - Explicit Authorization - written legal consent
  - Testing Within Scope - strictly operating within boundaries
  - Do no harm(Avoid disruption) - obj is to find vuln, not to crash servers or corrupt files
  - Confidentiality & Privacy - information and data must be protected
  - Transparency and Reporting - honest and unbiased reporting

## **- HTTP methods, headers, cookies, sessions and status codes**
# HTTP request methods

HTTP defines a set of **request methods** to indicate the purpose of the request and what is expected if the request is successful
 1. GET - Used to **fetch** data from the server without making any changes
 2. POST - **Sends** data to the server, usually to create or update something
 3. PUT - Replaces or **updates** something on the server
 4. DELETE - **Removes** something from the server.
 5. PATCH - Updates part of a resource. It’s useful for making small changes without replacing the whole thing
 6. HEAD - Works like GET but only retrieves headers, not the full content. It’s handy for checking metadata without downloading the full response.
 7. OPTIONS - Tells you what methods are available for a specific resource, helping clients understand what they can do with the server.
 8. TRACE - Similar to OPTIONS, it shows which methods are allowed, often for debugging. Many servers disable it for security reasons.

# HTTP Request Headers
Request Headers allow extra information to be conveyed to the web server about the request
![request headers](../../resources/ss1.png)
# HTTP Status Line and Status Codes

 ### Status Line - The first line in every HTTP response is called the **Status Line**. It gives you three key pieces of info:
 
1. **HTTP Version**: This tells  which version of HTTP is being used.
2. **Status Code**: A three-digit number showing the outcome of your request.
3. **Reason Phrase**: A short message explaining the status code in human-readable terms.

### Status Codes and Reason Phrases
The **Status Code** is the number that tells  if the request succeeded or failed, while the **Reason Phrase** explains what happened

![code](../../resources/ss2.png)
![code](../../resources/ss3.png)

