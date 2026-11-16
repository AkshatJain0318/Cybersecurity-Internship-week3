# 🔐 Week 3: Password Security Auditing & Hash Analysis Labs

This repository documents the completed practical lab modules for **Week 3 (Project Modules 1 & 2)** in Cybersecurity & Ethical Hacking, focusing on password hash extraction, dictionary-based auditing, and credential strength analysis[cite: 17, 18, 32, 33].

---

## 📂 Repository Structure

- **`Module-1-JTR-and-Johnny/`** — Local password auditing on Windows using **John the Ripper (JTR)** CLI and **Johnny GUI**[cite: 18].
- **`Module-2-Networkwalks-Browser-Tools/`** — Browser-based local hash extraction and dictionary analysis using **Networkwalks Hash Calculator** and **Password Cracker**[cite: 33].

---

## 🛠️ Module 1: Password Auditing with John the Ripper (JTR) & Johnny

### Objective
Audit the password strength of a protected sample PDF (`My Locked PDF1.pdf`) on Windows using John the Ripper (`1.9.0-jumbo-1`) paired with the Johnny graphical interface (`v2.2`)[cite: 18, 19, 21].

### Key Workflow & Concepts
1. **Environment Setup:** Configured `john.exe` inside Johnny GUI settings to link the backend cracking engine with the graphical interface[cite: 18, 20, 21].
2. **Hash Extraction:** Converted the encrypted PDF metadata into a `pdf2john`-compatible hash string (starting with `$pdf$`)[cite: 22, 23].
3. **Dictionary / Rule-Based Audit:** Loaded the extracted hash file into Johnny GUI and executed an audit session to recover the weak credential and verify access to the target document (`networkwalks_flag1.pdf`)[cite: 26, 27, 29, 30].

---

## 🌐 Module 2: Browser-Based Hash Extraction & Dictionary Analysis

### Objective
Perform client-side PDF hash extraction and dictionary-based password testing without local tool installation using Networkwalks web utilities[cite: 33].

### Key Workflow & Concepts
1. **Client-Side Hash Extraction:** Parsed `My Locked PDF1.pdf` locally in the browser using the **Networkwalks Hash Calculator** to extract the `$pdf$` hash (`Revision: R4`, `128-bit` key length) without uploading the file to an external server[cite: 34, 35].
2. **Dictionary Attack Simulation:** Tested the extracted hash against a built-in wordlist using the **Networkwalks Password Cracker** to demonstrate how common dictionary words are matched rapidly[cite: 36, 37].
3. **Verification:** Unlocked the protected PDF using the recovered credential to capture the lab completion flag[cite: 37, 38].

---

## 🛡️ Core Security Takeaways

- **Encryption vs. Hashing:** Encryption is a reversible two-way function requiring a decryption key to restore plaintext, whereas hashing is a one-way cryptographic function that produces a fixed message digest[cite: 30].
- **Password Entropy Matters:** Simple 8-character lowercase passwords or common dictionary words can be cracked within minutes, whereas strong 12+ character passwords mixing uppercase, lowercase, numbers, and symbols significantly resist offline attacks[cite: 38].

---

## ⚠️ Disclaimer
All exercises and artifacts in this repository were performed strictly within an authorized educational lab environment using sample training files (`My Locked PDF1.pdf`) for defensive learning and security awareness[cite: 18, 33].
