# SQL Injection Lab (CompTIA A+)

## Overview
In this lab, I investigated how a web application handles user input and identified a SQL injection vulnerability that allowed unauthorized access to sensitive data.

Instead of just following steps, I focused on understanding how the system responded to different inputs and why it was vulnerable.

---

## Environment
- CompTIA CertMaster Lab
- Web-based banking simulation
- Google Chrome

---

## Investigation Process

### Step 1: Baseline Testing
I started by entering valid account numbers to understand expected behavior.

- Valid input returned correct account data
- Short inputs returned errors

---

### Step 2: Input Validation Testing
I tested different input lengths:

- 1–4 digits → invalid
- 5+ digits → accepted

➡️ Observation:
The system only validated the **minimum length**, not the full input.

---

### Step 3: Input Manipulation
I entered:
90639 dog  
90639 cat  

➡️ Result:
The system still returned valid account data

➡️ Conclusion:
The application does not properly sanitize input beyond the required digits

---

### Step 4: SQL Injection Exploit
I tested the payload: `OR 1=1`


➡️ Result:
The application returned unintended data

➡️ Explanation:
This condition always evaluates to TRUE, bypassing query restrictions

---

### Step 5: Command Injection
I tested: `&& whoami`

➡️ Result:
The system returned:
www-user  

➡️ Conclusion:
The application is vulnerable to command execution

---

## Key Findings
- Weak input validation
- No sanitization of user input
- SQL injection vulnerability present
- Command injection possible
- Sensitive system information exposed

## Attacker Perspective
If I were an attacker, I could:
- Enumerate account data using SQL injection
- Extract sensitive financial information
- Identify system-level users for further exploitation
- Potentially escalate access depending on system configuration
---

## What I Learned
- How attackers test and manipulate input fields
- How SQL queries can be bypassed using simple logic
- The importance of validating and sanitizing all user input
- How small validation gaps lead to major vulnerabilities

---

## How This Applies to Real Work
- Help Desk: Recognizing abnormal application behavior
- SOC Analyst: Identifying suspicious input patterns
- Security: Understanding how vulnerabilities are exploited

---

## How to Prevent This
- Use parameterized queries (prepared statements)
- Validate input length AND content
- Sanitize all user inputs
- Apply least privilege access controls

## Detection & Monitoring

Indicators of this attack may include:

- Unusual input patterns (e.g., `OR 1=1`)
- Multiple failed or abnormal queries
- Unexpected command execution attempts
- Logs showing injection-like syntax

Monitoring tools such as SIEM solutions could detect these anomalies.

## How I Would Handle This in a Real Environment

- Escalate the vulnerability to the security team
- Document the issue in a ticketing system
- Recommend input validation fixes
- Monitor logs for repeated exploitation attempts
- Assist in containment if the system is compromised

## Screenshots

Below are screenshots from the completed lab, including the final score and key results.
<img width="1451" height="776" alt="Screenshot 2026-03-24 at 11 41 56 PM" src="https://github.com/user-attachments/assets/9480ce3b-2c63-44c8-acdc-0604087a98b1" />
<img width="1457" height="780" alt="Screenshot 2026-03-24 at 11 42 13 PM" src="https://github.com/user-attachments/assets/617c58a3-2f8e-40b1-bf26-21111509c1fc" />
<img width="1429" height="762" alt="Screenshot 2026-03-24 at 11 42 26 PM" src="https://github.com/user-attachments/assets/eda57624-6628-449f-8525-869c4dea7abd" />

## Reflection (My Thought Process)
While completing this lab, I started thinking less about just getting the correct answers and more about how an attacker would approach the system.

I noticed that once the application accepted five digits, it stopped properly validating the rest of the input. That immediately stood out as a weakness, because it meant additional input could be injected and processed.

When testing inputs like `OR 1=1`, I recognized that the system was not properly handling query logic, which allowed me to bypass restrictions and retrieve unintended data.

This lab helped me understand how small validation issues can lead to serious vulnerabilities, and how important it is to think critically about how systems handle user input.
  
