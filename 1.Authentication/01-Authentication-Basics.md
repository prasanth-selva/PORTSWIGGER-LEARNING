# Authentication Vulnerabilities

## Overview

Authentication is the process of verifying a user's identity before granting access to an application. Most websites use a username and password to authenticate users.

If an attacker is able to obtain or guess a user's credentials, they can gain unauthorized access to the victim's account.

---

# Username Enumeration

## Definition

Username enumeration is the process of identifying valid usernames by observing differences in the application's responses.

## Indicators

- Different HTTP Status Codes
- Different Error Messages
- Different Response Times
- Response Length Differences

## Risk

Once valid usernames are identified, attackers only need to brute-force the password, making attacks much easier.

## Prevention

- Use generic error messages.
- Return the same HTTP status code.
- Keep response times consistent.
- Avoid revealing whether a username exists.

---

# Brute Force Attack

## Definition

A brute-force attack is an attack where an attacker repeatedly tries different passwords until the correct one is found.

## Common Targets

- Login Pages
- Admin Panels
- VPN Portals
- Email Services

## Prevention

- Account Lockout
- Rate Limiting
- Multi-Factor Authentication (MFA)
- CAPTCHA
- Strong Password Policy

---

# Flawed Brute-Force Protection

## Definition

Flawed brute-force protection occurs when the application's protection mechanism contains logic flaws that allow attackers to bypass account lockout or IP blocking.

## Example

Some websites reset the failed login counter after any successful login.

An attacker can:

1. Attempt multiple passwords for the victim account.
2. Log in to their own account successfully.
3. Reset the failed login counter.
4. Continue brute-forcing the victim account.

## Risk

The attacker can continue brute-force attacks without triggering account lockout or IP blocking.

## Prevention

- Track failed attempts per target account.
- Track failed attempts per IP address.
- Do not reset counters because another account logged in successfully.
- Implement proper rate limiting and MFA.

---

# Labs Completed

- Username Enumeration via Different Responses ✅
- Username Enumeration via Subtly Different Responses ✅
- Username Enumeration via Response Timing ✅

---

# Key Interview Points

- Authentication verifies a user's identity.
- Authorization determines what a user is allowed to access.
- Username enumeration helps attackers discover valid usernames.
- Brute-force attacks try many passwords until one succeeds.
- Poorly implemented brute-force protection can be bypassed using logic flaws.
