# Module 08 – Brute Force Detection
---

## 1. What is a Brute Force Attack?

A brute force attack is a type of authentication attack where an attacker attempts multiple password combinations repeatedly to gain unauthorized access to a system.

The attacker tries:

- Different passwords
- Username/password combinations
- Password dictionaries
- Automated login attempts

Until the correct credentials are found.

---

## 2. Objective of a Brute Force Attack

The main objective of brute force attacks is to:

- Gain unauthorized system access
- Compromise user accounts
- Escalate privileges
- Access sensitive data
- Move laterally inside the network

---

## 3. Types of Brute Force Attacks

### a) Simple Brute Force

Attacker tries all possible password combinations manually or automatically.

---

### b) Dictionary Attack

Uses a predefined list of common passwords.

Example:

- admin123
- password123
- welcome@123

---

### c) Credential Stuffing

Uses previously leaked username/password combinations from data breaches.

---

### d) Password Spraying

Attempts a single common password across multiple user accounts.

Example:

Trying "Company@123" for many users.

---

## 4. Indicators of Brute Force Attack

SOC analysts should look for:

- Multiple failed login attempts
- Repeated authentication failures
- Account lockouts
- Login attempts from unknown IP address
- Login attempts at unusual time
- Multiple users targeted from same IP
- Sudden successful login after many failures

---

## 5. Authentication Logs Used for Detection

Brute force attacks are detected using:

- Login failure logs
- Account lockout logs
- Successful login logs
- Remote access logs
- VPN authentication logs

SOC analysts monitor authentication-related events continuously.

---

## 6. Brute Force Attack Pattern in Logs

Typical attack pattern includes:

1. Multiple failed login attempts
2. Account lockout (optional)
3. Successful login
4. Privilege usage or system access

This sequence may indicate account compromise.

---

## 7. Detection Based on Failed Login Attempts

SOC analysts detect brute force attacks by:

Counting failed login attempts from:

- Same source IP address
- Same username
- Same system

If failures exceed threshold:

Alert is triggered.

Example:

More than 5 failed login attempts within 5 minutes.

---

## 8. Detection Based on Multiple Targeted Accounts

Brute force may target:

- One user repeatedly  
OR  
- Multiple users from same IP

This may indicate password spraying attack.

SOC analysts must identify:

Single IP targeting many accounts.

---

## 9. Detection Based on Login Time

Login attempts during:

- Non-working hours
- Late night hours
- Weekends

May indicate suspicious activity.

---

## 10. Detection Based on Geo Location

Login attempt from:

- Foreign country
- Unknown location
- New geographic region

May indicate unauthorized access attempt.

---

## 11. Account Lockout Detection

Repeated failed login attempts may cause:

User account lockout.

Frequent lockouts may indicate:

Possible brute-force attack activity.

---

## 12. Successful Login After Failures

If a successful login occurs after:

Multiple failed attempts,

It may indicate:

Attacker has guessed the correct password.

SOC analysts must investigate such events.

---

## 13. SOC Investigation Steps

After receiving brute force alert:

1. Check targeted username
2. Identify source IP address
3. Count failed login attempts
4. Check successful login
5. Check login time
6. Verify user activity after login
7. Identify suspicious behavior

---

## 14. Post Login Activity Monitoring

After successful login, SOC analysts must check:

- Privilege usage
- File access
- System changes
- New user creation
- Process execution
- Network connections

---

## 15. False Positive Scenario

False alert may occur when:

- User forgets password
- Multiple login attempts made accidentally
- System login issues

SOC analyst must validate alert before escalation.

---

## 16. True Positive Scenario

True alert occurs when:

- Automated login attempts detected
- Unknown IP involved
- Successful login after failures
- Suspicious activity observed

---

## 17. SOC Response Actions

If brute force attack confirmed:

SOC team may:

- Lock affected account
- Reset password
- Block attacker IP
- Enable MFA
- Notify user
- Escalate to Incident Response team

---

## 18. Importance of Brute Force Detection

Helps SOC analysts:

- Prevent unauthorized access
- Protect user accounts
- Stop lateral movement
- Detect credential compromise early
- Reduce data breach risk

---

## 19. Preventive Security Measures

Organizations should implement:

- Strong password policy
- Account lockout policy
- Multi-Factor Authentication
- Login attempt monitoring
- IP blocking
- Security awareness training

---

## 20. SOC Use Case Example

Alert Triggered:

Multiple failed login attempts from same IP address.

SOC Analyst Actions:

- Verify username targeted
- Check source IP address
- Look for successful login
- Monitor post-login activity
- Confirm compromise
- Escalate incident if required

---