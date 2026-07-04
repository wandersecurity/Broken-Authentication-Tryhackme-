# Task 2: Broken Authentication

## Objective
Understand the most common authentication weaknesses that can lead to authentication bypass and identify how attackers exploit them to gain unauthorized access.

## Key Takeaways

- Username enumeration identifies valid accounts.
- Brute force attacks guess passwords for known usernames.
- Logic flaws in password recovery can bypass authentication.
- Unsigned or weakly protected cookies can be modified by attackers.
- Administrative account compromise can lead to complete application takeover.
- Reusing passwords across multiple services increases the impact of compromised credentials.
- Credential stuffing exploits reused passwords across different applications.


## Question

**Q:** What is the name for the practice of reusing credentials recovered from one application against unrelated applications?

**Answer:** `Credential *****`

---
# Task 3: Username Enumeration

## Objective
Learn how attackers enumerate valid usernames by identifying differences in application responses and automate the process using **ffuf**.

## Key Takeaways

- Username enumeration identifies valid user accounts.
- Different application responses reveal whether an account exists.
- Enumeration can use differences in:
  - Error messages
  - Response length
  - Status codes
  - Redirects
  - Response timing
- `ffuf` automates enumeration using a wordlist.
- The discovered usernames are used in later password attacks.
