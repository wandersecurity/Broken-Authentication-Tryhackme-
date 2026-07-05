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

## Questions

1. What is the username starting with `si***`?

Run the enumeration command and look for the matching username beginning with **si**.

**Answer:** `sim**`

2. What is the username starting with `st***`?

Run the enumeration command and identify the username beginning with **st**.

**Answer:** `ste**`

3. What is the username starting with `ro****`?

**Answer:** `robe**`

---
# Task 4: Brute Forcing a Login Form

## Objective
Learn how to perform a credential brute-force attack against a login form using **ffuf** and identify valid login credentials by detecting successful authentication responses.
## Key Takeaways

- Brute-force attacks systematically test username/password combinations.
- Username enumeration significantly reduces the number of login attempts required.
- Success is identified by changes in the application's response (such as HTTP status codes).
- **ffuf** supports multiple wordlists using custom placeholders (`W1`, `W2`).
- Filtering failed responses (`-fc 200`) makes successful credentials easy to identify.

## Question

1. What is the valid username and password (format: `username/password`)?

**Answer:** `steve/thun**`

---
# Task 5: Logic Flaws

## Objective
Understand how business logic flaws can allow attackers to bypass security controls by manipulating valid application input, and exploit a password reset workflow vulnerable to **parameter pollution**.

## Key Takeaways

- Logic flaws exploit mistakes in application workflows rather than malformed input.
- Automated vulnerability scanners rarely detect business logic vulnerabilities.
- Different application components must interpret input consistently.
- PHP's `$_REQUEST` merges query parameters, POST data, and cookies into a single array.
- Duplicate parameters can override one another, leading to **HTTP Parameter Pollution**.
- Password reset workflows are common targets for logic flaw exploitation.

## Question

1. What is the flag from Robert's support ticket?

**Answer:** `THM{AUTH_BYPASS_******}`

---

# Task 6: Cookie Manipulation

## Objective
Understand how insecure cookies can be manipulated to bypass authentication and privilege checks by modifying **plain text**, **hashed**, and **encoded** cookie values.

## Key Takeaways

- Cookies maintain authenticated sessions.
- Plain text cookies can be modified directly.
- Hashes do **not** prevent cookie tampering.
- Base64 encoding is easily reversible and provides no security.
- Sensitive cookie data should always be cryptographically signed or stored server-side.

## Questions

1.  What is the flag from changing the plain text cookie values?

**Answer:** `THM{COOKIE_TAMPERING}`

2. What is the value of the MD5 hash `3b2a1053e3270077456a79192070aa78`?

**Answer:** `463***`

3. What is the Base64 decoded value of `VEhNe0JBU0U2NF9FTkNPRElOR30=`?

**Answer: `**THM{BASE64_******}`

4. Encode the following value using Base64

**Answer:** `eyJpZCI6MSwiYWRtaW4iOnRydWV9`
