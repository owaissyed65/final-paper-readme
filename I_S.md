# Week 5 – Information Security (Authentication & Risk Assessment)

## Overview
This week focuses on **authentication mechanisms**, **risk assessment**, **password protection techniques**, and **smart card–based authentication**. These concepts are essential for securing information systems against unauthorized access.

---

## 1. Authentication

### 1.1 What is Authentication?
Authentication is the process of **verifying the identity of a user** before granting access to a system or service.  
It ensures that the person requesting access is genuinely who they claim to be.

---

## 2. Authentication Factors

Authentication methods are based on different **factors**:

### 2.1 Something You Know
- Password
- PIN
- Security questions

### 2.2 Something You Have
- Smart card
- ATM card
- Mobile phone (OTP)

### 2.3 Something You Are
- Fingerprint
- Face recognition
- Iris scan

---

## 3. Multifactor Authentication (MFA)

### 3.1 Definition
**Multifactor Authentication (MFA)** uses **more than one authentication factor** to verify a user.

### 3.2 Strength of MFA
- **Single factor** → Weak security
- **Two factors** → Stronger security
- **Three factors** → Very strong security

Each additional factor **reduces the chance of unauthorized access** because an attacker must compromise multiple credentials :contentReference[oaicite:1]{index=1}.

### 3.3 Example
Login using:
- Password (something you know)
- OTP sent to phone (something you have)

---

## 4. Risk Assessment in Authentication

### 4.1 What is Risk Assessment?
Risk assessment helps an organization **analyze the impact of authentication failure** on its systems and services.

### 4.2 Purpose
- Identify possible risks
- Measure potential damage
- Decide the required security level

---

## 5. Assurance Levels

### 5.1 Definition
Assurance levels indicate **how confident** a system is that the authenticated user is genuine.

### 5.2 Higher Assurance Means
- Stronger authentication
- Lower risk of impersonation
- Higher implementation cost

---

## 6. Potential Risk

### 6.1 What is Potential Risk?
Potential risk is the **possible harm or loss** if authentication fails.

### 6.2 Examples
- Financial loss
- Data leakage
- System compromise
- Loss of trust

---

## 7. Risk

### 7.1 Definition
Risk is the **combination of potential impact and likelihood** of authentication failure

### 7.1 What is Risk?
Risk refers to the **expected loss or damage** that may occur if an authentication failure happens.  
It depends on **how severe the impact is** and **how likely the failure is to occur**.

---

### 7.2 Risk Formula
In information security, risk is commonly expressed using the following formula:
Risk = Impact × Likelihood


---

### 7.3 Explanation of the Formula

#### Impact
Impact represents the **severity of damage** if authentication fails.

Examples:
- Loss of sensitive data
- Financial loss
- System downtime
- Reputation damage

Impact can be:
- Low
- Medium
- High

---

#### Likelihood (Probability)
Likelihood represents **how often or how easily** an authentication failure can occur.

Examples:
- Weak passwords → High likelihood
- Multifactor authentication → Low likelihood

Likelihood can also be:
- Low
- Medium
- High

---

### 7.4 Simple Example
If:
- Impact = High (e.g., banking system breach)
- Likelihood = Medium

Then:
Risk = High × Medium = High Risk


---

### 7.5 Why This Formula is Important
- Helps organizations prioritize security controls
- Guides the choice of authentication methods
- Ensures proper risk mitigation strategies

---

## 8. Password Security Using Hashing and Salt

### 8.1 Hashing
Hashing converts a password into a **fixed-length hash value** using a mathematical algorithm.

### 8.2 Salt
A **salt** is a random value added to the password before hashing.

### 8.3 Why Salt is Important
- Prevents rainbow table attacks
- Makes identical passwords produce different hashes

### 8.4 Storage Process
1. User enters password
2. Password + salt are input to hash function
3. Hash output is stored
4. Salt is stored in plaintext

The hashing algorithm is intentionally **slow**, making brute-force attacks difficult :contentReference[oaicite:2]{index=2}.

---

## 9. Security Strength of Hashed Passwords

### 9.1 Advantages
- Passwords are never stored in plaintext
- Resistant to cryptanalytic attacks
- Safe even if database is leaked

---

## 10. Potential Drawbacks of Password Systems

### 10.1 Common Drawbacks
- Users choose weak passwords
- Password reuse across platforms
- Vulnerable to phishing
- Passwords can be forgotten

These drawbacks highlight the need for **MFA and stronger authentication mechanisms** :contentReference[oaicite:3]{index=3}.

---

## 11. Smart Card Authentication

### 11.1 What is a Smart Card?
A smart card is a **physical authentication device** containing an embedded microchip used for secure access.

---

## 12. Electronic Functions of a Smart Card

A smart card has **three separate electronic functions**, each with its own protected dataset:

### 12.1 Authentication Function
- Verifies the user’s identity

### 12.2 Digital Signature Function
- Ensures data integrity
- Confirms message authenticity

### 12.3 Confidentiality Function
- Encrypts sensitive data
- Protects information from unauthorized access :contentReference[oaicite:4]{index=4}.

---

## 13. Importance of Smart Cards

### 13.1 Benefits
- High security
- Difficult to clone
- Supports MFA
- Widely used in banking and government systems

---

## Conclusion
Week 5 emphasizes that **strong authentication** is a foundation of information security. By combining **multifactor authentication**, **risk assessment**, **secure password storage**, and **smart cards**, organizations can significantly reduce security threats and authentication failures.

