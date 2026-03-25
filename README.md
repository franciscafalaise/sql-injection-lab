# SQL Injection Lab (CompTIA A+)

## Overview
In this lab, I explored how SQL injection vulnerabilities can be used to bypass input validation and retrieve sensitive data from a web application.

The lab simulated a banking system where user input was not properly sanitized, allowing unauthorized access to account information.

---

## Objective
- Identify input validation weaknesses
- Test how the application handles different inputs
- Exploit vulnerabilities using SQL injection techniques
- Understand the security risks involved

---

## Tools Used
- CompTIA CertMaster Lab
- Web Browser (Chrome)

---

## Steps Performed

### 1. Tested Input Validation
- Entered different account number lengths
- Discovered that at least **5 digits** were required
- Found that input was **not restricted beyond 5 digits**

---

### 2. Manipulated User Input
- Added extra characters (e.g., `90639 dog`)
- Observed that the system still returned valid data
- Confirmed weak input validation

---

### 3. Performed SQL Injection
- Used payload:  

## Screenshots
(Add your screenshots here showing your lab results and score)<img width="1451" height="776" alt="Screenshot 2026-03-24 at 11 41 56 PM" src="https://github.com/user-attachments/assets/9480ce3b-2c63-44c8-acdc-0604087a98b1" />
<img width="1457" height="780" alt="Screenshot 2026-03-24 at 11 42 13 PM" src="https://github.com/user-attachments/assets/617c58a3-2f8e-40b1-bf26-21111509c1fc" />
<img width="1429" height="762" alt="Screenshot 2026-03-24 at 11 42 26 PM" src="https://github.com/user-attachments/assets/eda57624-6628-449f-8525-869c4dea7abd" />

- Result: Returned unintended account data (bypassed filtering)

---

### 4. Command Injection
- Used payload:

- Result: Identified web server user as:

  
---

## Key Findings
- Input validation was insufficient
- Application accepted unexpected characters
- SQL injection allowed unauthorized data access
- Command injection exposed system-level information

---

## What I Learned
- How attackers exploit poor input validation
- How SQL queries can be manipulated
- Why sanitization and validation are critical
- Real-world impact of insecure applications

---

## Real-World Relevance
This type of vulnerability is part of the OWASP Top 10 and is commonly exploited in real-world attacks.

Understanding this helps:
- IT Support → recognize compromised systems
- SOC Analysts → detect suspicious query behavior
- Security Teams → prevent vulnerabilities

---

## Screenshots

<img width="1451" height="776" alt="Screenshot 2026-03-24 at 11 41 56 PM" src="https://github.com/user-attachments/assets/335e7af2-b65a-48b4-ae54-4ff34c123b1b" />
<img width="1457" height="780" alt="Screenshot 2026-03-24 at 11 42 13 PM" src="https://github.com/user-attachments/assets/f836f0ca-5d71-4b4b-8ad1-edda04b45cc0" />
<img width="1429" height="762" alt="Screenshot 2026-03-24 at 11 42 26 PM" src="https://github.com/user-attachments/assets/da393732-21d7-4bd6-bf0c-d9d9fceef0de" />

## How to Prevent This
- Use parameterized queries (prepared statements)
- Validate and sanitize all user input
- Implement least privilege access
- Use web application firewalls (WAF)

  
