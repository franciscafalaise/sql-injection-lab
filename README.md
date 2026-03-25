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
I tested the payload:
OR 1=1  

➡️ Result:
The application returned unintended data

➡️ Explanation:
This condition always evaluates to TRUE, bypassing query restrictions

---

### Step 5: Command Injection
I tested:
&& whoami  

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

---

## Screenshots
(Add your screenshots here showing your lab results and score)<img width="1451" height="776" alt="Screenshot 2026-03-24 at 11 41 56 PM" src="https://github.com/user-attachments/assets/9480ce3b-2c63-44c8-acdc-0604087a98b1" />
<img width="1457" height="780" alt="Screenshot 2026-03-24 at 11 42 13 PM" src="https://github.com/user-attachments/assets/617c58a3-2f8e-40b1-bf26-21111509c1fc" />
<img width="1429" height="762" alt="Screenshot 2026-03-24 at 11 42 26 PM" src="https://github.com/user-attachments/assets/eda57624-6628-449f-8525-869c4dea7abd" />


  
