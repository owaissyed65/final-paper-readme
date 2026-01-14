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

# Intrusion Detection System (IDS)

## Overview
An Intrusion Detection System (IDS) is a **security mechanism** used to **monitor networks or systems** for malicious activities or policy violations. It helps organizations detect unauthorized access attempts and potential attacks.

---

## 1. Intruder

### 1.1 Definition
An **intruder** is a person who attempts to **gain unauthorized access** to a system or network.

### 1.2 Purpose of an Intruder
- Steal data
- Damage systems
- Disrupt services
- Gain illegal control

---

## 2. Intrusion

### 2.1 Definition
An **intrusion** is:
> Any set of activities that attempt to compromise the **confidentiality**, **integrity**, or **availability** of a system or resource.

### 2.2 CIA Triad Impact
- **Confidentiality** → Unauthorized data access
- **Integrity** → Data modification
- **Availability** → Service disruption

---

## 3. Intrusion Detection System (IDS)

### 3.1 Definition
An **Intrusion Detection System (IDS)** is a **hardware device or software application** that monitors network or system activity to detect malicious behavior or security policy violations.

### 3.2 How IDS Works
- Monitors inbound and outbound traffic
- Analyzes network packets
- Classifies traffic as **normal or malicious**
- Generates alerts for suspicious activity

### 3.3 IDS Function
- Detect attacks
- Log events
- Notify administrators

IDS **does not block attacks**, it only **detects and reports** them.

---

## 4. Intrusion Prevention System (IPS)

### 4.1 Definition
An **Intrusion Prevention System (IPS)** is similar to IDS but has the **ability to block or stop attacks**.

### 4.2 Functions of IPS
- Detect malicious activity
- Log security events
- Alert administrators
- **Prevent or block attacks in real time**

### 4.3 IDS vs IPS
| Feature | IDS | IPS |
|------|-----|-----|
| Detection | Yes | Yes |
| Alerting | Yes | Yes |
| Blocking | No | Yes |

---

## 5. Types of Intrusion Detection Systems

---

## 5.1 Network-Based Intrusion Detection System (NIDS)

### 5.1.1 Definition
NIDS is deployed at **strategic points in a network** to monitor traffic flowing between devices.

### 5.1.2 Features
- Monitors entire network
- Analyzes protocol activity
- Matches traffic against known attack signatures

### 5.1.3 Advantages
- Protects multiple systems
- Centralized monitoring

### 5.1.4 Limitation
- Cannot analyze encrypted traffic deeply

---

## 5.2 Host-Based Intrusion Detection System (HIDS)

### 5.2.1 Definition
HIDS is a **software installed on a single host** that monitors inbound and outbound traffic of that system.

### 5.2.2 Features
- Monitors system logs
- Detects suspicious host activity
- Alerts administrator or user

### 5.2.3 Advantages
- Detailed host-level monitoring
- Detects insider attacks

### 5.2.4 Limitation
- Only protects the host it is installed on

---

## 6. Detection Methods in IDS

---

## 6.1 Signature-Based Detection

### 6.1.1 Definition
Signature-based IDS detects attacks by **matching network traffic** against a **database of known attack patterns (signatures)**.

### 6.1.2 How It Works
- Predefined attack patterns are stored
- Incoming traffic is compared to these patterns
- Alerts are generated if a match is found

### 6.1.3 Advantages
- Highly accurate for known attacks
- Low false positives

### 6.1.4 Disadvantages
- Cannot detect new or unknown attacks
- Requires frequent signature updates

---

## 6.2 Anomaly-Based Detection

### 6.2.1 Definition
An anomaly-based IDS detects intrusions by comparing current activity to a **baseline of normal behavior**.

### 6.2.2 How It Works
- Establishes normal network behavior
- Flags deviations as suspicious

### 6.2.3 Advantages
- Detects new and unknown attacks
- Adaptive to changing behavior

### 6.2.4 Disadvantages
- Higher false positives
- Requires training time to build baseline

---

## 7. Importance of IDS

### 7.1 Benefits
- Early attack detection
- Improved network visibility
- Supports forensic analysis
- Enhances overall security posture

---

## Conclusion
Intrusion Detection Systems (IDS) play a **critical role in cybersecurity** by detecting unauthorized access and suspicious activities. When combined with IPS, they provide a **strong defense mechanism** against modern cyber threats.


# Block Cipher Modes of Operation

## Overview
When a block cipher encrypts **multiple blocks of plaintext using the same key**, several security problems can occur, such as pattern leakage.  
To solve this, **modes of operation** are used.

A **mode of operation** is a technique that enhances the security and usability of a block cipher.  
The **National Institute of Standards and Technology (NIST)** has defined **five standard modes of operation** that work with symmetric block ciphers such as **DES, Triple DES, and AES**.

---

## 1. Why Modes of Operation Are Needed

### 1.1 Problem with Basic Block Cipher
- Encrypting identical plaintext blocks produces identical ciphertext blocks
- Patterns in data may be exposed
- Confidentiality can be compromised

### 1.2 Solution
Modes of operation:
- Hide data patterns
- Improve confidentiality
- Allow block ciphers to be used in different applications

---

## 2. Electronic Codebook (ECB) Mode

### 2.1 Definition
Electronic Codebook (ECB) mode is the **simplest block cipher mode**, where each plaintext block is encrypted **independently** using the same key.

### 2.2 How ECB Works
- Plaintext is divided into blocks
- Each block is encrypted separately
- No chaining between blocks

### 2.3 Advantages
- Simple and fast
- Best suited for **short data**, such as encryption keys

### 2.4 Disadvantages
- **Not secure for large or lengthy data**
- Does not hide data patterns
- Same plaintext blocks produce same ciphertext blocks
- Weak confidentiality

---

## 3. Cipher Block Chaining (CBC) Mode

### 3.1 Definition
Cipher Block Chaining (CBC) mode improves security by **chaining plaintext blocks together**.

### 3.2 How CBC Works
- Each plaintext block is XORed with the **previous ciphertext block**
- First block uses an **Initialization Vector (IV)**
- Then the result is encrypted

### 3.3 Advantages
- Hides data patterns
- More secure than ECB
- Widely used in practice

### 3.4 Disadvantages
- Encryption is sequential (slower)
- Error in one block affects the next block

---

## 4. Cipher Feedback (CFB) Mode

### 4.1 Definition
Cipher Feedback (CFB) mode converts a **block cipher into a stream cipher**.

### 4.2 How CFB Works
- Uses previous ciphertext as input to the encryption algorithm
- Output is XORed with plaintext
- Decryption process is similar to CBC

### 4.3 Key Feature
- **Encryption and decryption processes are almost identical**
- Encryption is performed in reverse order

### 4.4 Advantages
- Suitable for real-time data transmission
- No need for padding

### 4.5 Disadvantages
- Error propagation
- Slower than some other modes

---

## 5. Output Feedback (OFB) Mode

### 5.1 Definition
Output Feedback (OFB) mode also turns a block cipher into a **stream cipher**, but it feeds back the output of the encryption function.

### 5.2 How OFB Works
- Encryption output is fed back as input
- Output is XORed with plaintext
- Same process used for encryption and decryption

### 5.3 Important Property
Because of the **symmetry of XOR operation**, encryption and decryption are **exactly the same**.

### 5.4 Advantages
- No error propagation
- Suitable for noisy channels

### 5.5 Disadvantages
- Requires careful synchronization
- Not self-synchronizing

---

## 6. Counter (CTR) Mode

### 6.1 Definition
Counter (CTR) mode uses a **counter value** combined with a key to generate a keystream.

### 6.2 How CTR Works
- Counter value is encrypted
- Result is XORed with plaintext
- Counter increments for each block

### 6.3 Advantages
- High performance
- Allows parallel encryption and decryption
- No padding required

### 6.4 Disadvantages
- Counter values must never repeat
- Poor counter management can lead to security issues

---

## 7. Summary of Block Cipher Modes

| Mode | Security | Pattern Hiding | Speed | Use Case |
|----|----|----|----|----|
| ECB | Low | No | Fast | Very short data |
| CBC | High | Yes | Medium | General encryption |
| CFB | Medium | Yes | Medium | Stream data |
| OFB | Medium | Yes | Medium | Noisy channels |
| CTR | High | Yes | Very Fast | High-speed systems |

---

## Conclusion
Block cipher modes of operation are essential for secure encryption.  
Each mode provides different security and performance trade-offs, making them suitable for different applications. Choosing the correct mode is crucial for maintaining **data confidentiality and integrity**.


