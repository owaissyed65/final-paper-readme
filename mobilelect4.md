
---

## 📡 **What is Duplexing?**

➡ **Duplexing** means **sending and receiving signals** between two people or devices — like in a phone call, you talk and also hear the other person.

---

### 🟦 **1. Frequency Division Duplexing (FDD)**

🧠 **Simple words**:

* We use **two different frequencies**.
* One for **sending voice/data** (forward).
* One for **receiving voice/data** (reverse).
* Both happen **at the same time**.

📦 **Needs a device** called a **duplexer** to keep the two signals separate.

📱 **Example**: When you talk on the phone and hear the other person at the same time.

📊 **In the diagram**:

* One line is for **sending**
* Another line is for **receiving**
* Both go together, but on **different frequencies**

---

### 🟨 **2. Time Division Duplexing (TDD)**

🧠 **Simple words**:

* Uses **one frequency**.
* **Time is divided** into parts (slots).
* First you **send**, then you **receive** — like taking turns.

🛠️ **No duplexer needed** here.

📱 **Example**: Like using a walkie-talkie — first you speak, then you stop and listen.

📊 **In the diagram**:

* One time slot is used to **send**
* The next time slot is used to **receive**
* Both happen on the **same frequency**, just at **different times**

---

### 🧠 Easy way to remember:

| Type    | How it Works                        | Easy Example                                         |
| ------- | ----------------------------------- | ---------------------------------------------------- |
| **FDD** | Uses 2 different frequencies        | Talking and listening at the **same time**           |
| **TDD** | Uses same frequency but takes turns | Like a **walkie-talkie**, talk one time, listen next |

---

Here is the **entire content** you've shared — combined and rewritten in **very simple language** for **matric-level students**. It's clear, beginner-friendly, and exam-ready.

---

# 📡 Multiple Access Techniques (Simple Notes for Matric Students)

## ✅ What Are Multiple Access Techniques?

These are **methods to allow many users** (like phones or devices) to **share the same network** or signal without disturbing each other.

---

## 🔹 1. **Types of Multiple Access:**

| Type     | Full Form                          | Simple Idea                                                                           |
| -------- | ---------------------------------- | ------------------------------------------------------------------------------------- |
| **FDMA** | Frequency Division Multiple Access | Each user gets a different frequency (like a different radio station)                 |
| **TDMA** | Time Division Multiple Access      | Each user gets a turn to speak in time slots (like taking turns)                      |
| **CDMA** | Code Division Multiple Access      | All users talk together but in different secret codes                                 |
| **SDMA** | Space Division Multiple Access     | Users are separated by direction/space (like spotlights pointing to different people) |

---

## 🔸 Grouping:

### ✅ **Narrowband Systems**

– Uses **small frequency channels**
– Often use **FDD**
– Examples:

* Narrowband FDMA
* Narrowband TDMA
* FDMA/FDD
* FDMA/TDD
* TDMA/FDD
* TDMA/TDD

---

### ✅ **Wideband Systems**

– One **big frequency channel** shared by many users
– Can use:

* TDMA
* CDMA
  – Can also use:
* FDD or TDD
  – Examples:
* TDMA/FDD
* TDMA/TDD
* CDMA/FDD
* CDMA/TDD

---

## 📱 **Examples of Systems and Techniques**

| System Name                      | Technique Used |
| -------------------------------- | -------------- |
| AMPS (old analog phones)         | FDMA/FDD       |
| GSM (Global System for Mobile)   | TDMA/FDD       |
| USDC (US Digital Cellular)       | TDMA/FDD       |
| DECT (Cordless Phones in Europe) | FDMA/TDD       |
| IS-95 (CDMA in USA)              | CDMA/FDD       |

---

## 🔁 FDMA – Frequency Division Multiple Access

### 📌 Key Points:

* One **phone = one frequency channel**
* All users talk **at the same time**, but on **different frequencies**
* Example: AMPS used 30 kHz channels

### ✅ Pros and Cons:

✔ No waiting — always sending
✖ Needs more hardware (duplexers)
✖ More expensive for towers

---

### 🔢 FDMA Channel Formula:

$$
N = \frac{B_t - B_{guard}}{B_{channel}}
$$

Where:

* $B_t$: Total available frequency range
* $B_{guard}$: Space to avoid interference
* $B_{channel}$: One user's channel size

---

## 🕐 TDMA – Time Division Multiple Access

### 📌 Key Points:

* Uses **time slots** for each user
* **Only one user talks at a time**
* Sends **digital data** in **short bursts**

### ✅ Features:

✔ Saves battery
✔ Simple handoff between towers
✖ Needs synchronization
✖ Needs guard slots (time gaps)

---

## 📍 CDMA – Code Division Multiple Access

* All users **share the same frequency**
* Each uses a **different code**
* Used in **IS-95**

### 📌 Imagine:

Everyone speaks at the same time, but in different languages. You only understand the one in your code!

---

## 📡 SDMA – Space Division Multiple Access

* Uses **special antennas** (spot beams)
* Tracks the user's **position**
* Can **reuse the same frequency** in different areas

---

# 🌐 Propagation Modes – How Signals Travel

## ✅ 1. Ground-Wave Propagation

* Follows the **curve of the Earth**
* Works for **low frequencies** (below 2 MHz)
* 📻 **Example**: AM radio

---

## ✅ 2. Sky-Wave Propagation

* Signal **bounces off the ionosphere**
* Can travel **very far**
* 📡 Goes up → bounces → comes down

---

## ✅ 3. Line-of-Sight (LOS) Propagation

* Signal goes **straight from one antenna to another**
* Both antennas must **see each other**
* Used in **satellite and microwave** links

📌 Signals above 30 MHz **do not reflect** from the ionosphere

---

## 📏 Line-of-Sight Distance Formula:

$$
\text{Max Distance} = K(\sqrt{h_1} + \sqrt{h_2})
$$

Where:

* $h_1$: height of antenna 1
* $h_2$: height of antenna 2
* $K = \frac{4}{3}$: used to correct the Earth’s shape

---

# 🧠 Summary for Exam Revision

| Topic           | Easy Meaning                              |
| --------------- | ----------------------------------------- |
| **FDMA**        | Each user = different frequency           |
| **TDMA**        | Each user = different time slot           |
| **CDMA**        | Each user = different code                |
| **SDMA**        | Each user = different direction           |
| **FDD**         | Talk & listen on different frequencies    |
| **TDD**         | Talk & listen at different times          |
| **Ground wave** | Signal follows Earth                      |
| **Sky wave**    | Signal bounces in sky                     |
| **LOS**         | Signal goes straight (antenna to antenna) |

---



