# SQL Injection Lab (CompTIA A+)

## Overview
In this lab, I explored SQL injection vulnerabilities by interacting with a simulated banking web application. The goal was to understand how improper input validation can lead to unauthorized data access.

## Tools Used
- Web browser (Google Chrome)
- CompTIA CertMaster Lab Environment

## Key Tasks Performed
- Accessed a simulated online banking system
- Tested input validation by entering different account number formats
- Identified minimum input requirements (5 digits or more)
- Observed how additional characters were accepted beyond expected input
- Performed basic SQL injection techniques to retrieve unintended data
- Used command injection (`whoami`) to identify the web server user

## Key Findings
- The application did not properly validate user input beyond the first five digits
- Additional characters (e.g., text) were still processed by the system
- SQL injection (`OR 1=1`) allowed bypassing intended query restrictions
- Command injection revealed the web server user as `www-user`

## Security Implications
This lab demonstrated how improper input validation can lead to:
- Unauthorized access to sensitive data
- Exposure of system-level information
- Increased risk of exploitation in real-world applications

## What I Learned
- The importance of input validation and sanitization
- How SQL injection attacks manipulate backend queries
- How attackers can extract sensitive information from vulnerable systems
- Basic awareness of command injection risks

## Real-World Application
Understanding SQL injection is critical for both IT support and security roles. Help desk professionals may encounter compromised systems, while SOC analysts must detect and respond to these types of attacks.

## Screenshots
(Add your screenshots here showing your lab results and score)<img width="1451" height="776" alt="Screenshot 2026-03-24 at 11 41 56 PM" src="https://github.com/user-attachments/assets/9480ce3b-2c63-44c8-acdc-0604087a98b1" />
<img width="1457" height="780" alt="Screenshot 2026-03-24 at 11 42 13 PM" src="https://github.com/user-attachments/assets/617c58a3-2f8e-40b1-bf26-21111509c1fc" />
<img width="1429" height="762" alt="Screenshot 2026-03-24 at 11 42 26 PM" src="https://github.com/user-attachments/assets/eda57624-6628-449f-8525-869c4dea7abd" />
