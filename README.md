# Satyam Shiv 🚀
### Offensive Security Intern @ ComplyStrike | BCA Student @ JIMS Vasant Kunj

Welcome to my security portfolio. This space is dedicated to tracking my daily VAPT workflows, core vulnerability research, and hands-on laboratory milestones.

---

## 🛠️ Technical Focus & Tooling
* **Frameworks:** OWASP Top 10, VAPT Methodologies
* **Web Security:** SQL Injection (In-Band, Inferential), Cross-Site Scripting (XSS), IDOR
* **Tools:** Burp Suite Community Edition, Nmap, Git

---

## 📈 Current Cybersecurity Lab Log
*Currently working through active tracks assigned by the ComplyStrike engineering team.*

### 🧼 OWASP Juice Shop
*   [ ] **Challenge 1:** Locate the hidden Score Board (`/#/score-board`) — *Status: In Progress*
*   [ ] **Challenge 2:** Admin login via SQL Injection bypass — *Status: Pending*

### 🏰 PortSwigger Web Security Academy
### 🏰 PortSwigger Web Security Academy — SQL Injection Track

*   [x] **Lab 1: SQLi vulnerability in WHERE clause allowing retrieval of hidden data**
    *   **Technical Summary:** Exploited a vulnerability in a product category filter where user input was concatenated directly into a SQL query. 
    *   **Learning & Payload:** Used the classic `' OR 1=1--` payload to force the conditional `WHERE` evaluation to always return `TRUE`. This successfully bypassed the standard logic constraints, forcing the database to output hidden, unreleased products alongside the visible ones.

*   [x] **Lab 2: SQLi vulnerability allowing login bypass**
    *   **Technical Summary:** Targeted an insecure authentication form where the application failed to sanitize user inputs before checking the user credentials table.
    *   **Learning & Payload:** Injected `administrator'--` into the username field. This broke out of the string literal and added a SQL comment operator (`--`), completely cutting off the remaining password validation check in the backend backend query. Allowed direct authentication into the high-privilege account without a password.

*   [x] **Lab 3: SQL injection UNION attack, determining the number of columns returned by the query**
    *   **Technical Summary:** Leveraged a `UNION` based injection technique to map the underlying database structure. A successful `UNION` attack requires the injected query to return the exact same number of columns as the original application query.
    *   **Learning & Payload:** Systematically executed an enumeration strategy using `ORDER BY 1--`, `ORDER BY 2--`, etc., until an error was triggered, mapping the precise column count. Verified the structure using a balanced payload: `' UNION SELECT NULL, NULL, NULL--`.

*   [x] **Lab 4: SQL injection UNION attack, finding a column containing text**
    *   **Technical Summary:** Built upon column-count enumeration to identify compatible data types. For a `UNION` attack to exfiltrate meaningful data, the attacker must find a column capable of holding string data types (`VARCHAR`).
    *   **Learning & Payload:** Placed a specific string literal (e.g., `'a'`) into different positions within the null array: `' UNION SELECT 'a', NULL, NULL--`. Monitored HTTP response codes (seeking a `200 OK`) to identify exactly which column positions could securely accept and display text payloads.

*   [x] **Lab 5: SQL injection UNION attack, retrieving data from other tables**
    *   **Technical Summary:** Executed cross-table data exfiltration after mapping both the column counts and compatible data types of the vulnerable endpoint.
    *   **Learning & Payload:** Injected a `UNION SELECT` query to directly query the `users` database table: `' UNION SELECT username, password FROM users--`. This appended the administrative credentials directly into the visible application interface response, demonstrating full database read capabilities.

---

### 💡 Core Engineering Key Takeaways
*   **Burp Suite Proficiency:** Utilized **Burp Proxy** and **Repeater** to capture, isolate, tweak, and resend payloads efficiently without filling local system event logs or causing interface layout breaks.
*   **Database Mechanics:** Mastered the foundational mechanics of string escaping, comment syntax variations, and database structural fingerprinting.
*   **Remediation Insight:** Understood that the root cause across all 5 labs is unsafe dynamic query concatenation. The strict secure coding fix for these flaws is moving away from raw string interpolation and enforcing **Parametrized Queries (Prepared Statements)**.

---

## 👥 Campus Leadership
* **Vice President** – Entrepreneurship Cell (E-Cell), JIMS Vasant Kunj
* Managing core operations, operational strategies, and high-pressure team workflows.
