# 🛠️ Module 1: Password Auditing with John the Ripper (JTR) & Johnny

## 📌 Overview
This module documents the practical implementation of **Week 3 — Project Module 1** from the Networkwalks Cybersecurity & Ethical Hacking lab series[cite: 17, 18]. The objective was to evaluate the credential strength of a password-protected sample document (`My Locked PDF1.pdf`) on Windows using **John the Ripper (JTR)** alongside its graphical interface, **Johnny**[cite: 18].

---

## 🧰 Tools & Environment
* **John the Ripper (`1.9.0-jumbo-1`):** An open-source, cross-platform password auditing utility (available for Windows, Linux, and macOS, and pre-installed on Kali Linux) capable of analyzing multiple hash formats and protected files such as PDF, ZIP, and Office documents[cite: 18, 19].
* **Johnny GUI (`v2.2`):** A desktop graphical frontend for JTR that simplifies session configuration, hash loading, and audit monitoring without requiring complex CLI flags[cite: 18, 19].
* **Target Sample:** `My Locked PDF1.pdf` (Authorized educational lab file)[cite: 18].

---

## 🔄 Lab Workflow Summary
1. **Backend Engine Integration:** Linked the Johnny GUI configuration directly to the `john.exe` binary (`1.9.0-jumbo-1 OMP [cygwin 64-bit x86_64 AVX2 AC]`) inside the JTR `run` directory[cite: 20, 21].
2. **Cryptographic Hash Extraction:** Converted the encrypted PDF metadata into a `pdf2john` / `pdf2hashcat`-compatible hash string starting with `$pdf$` and saved it as a clean UTF-8 text file (`hash1.txt`)[cite: 22, 23, 25].
3. **Offline Audit Execution:** Imported the `PASSWD`-formatted hash file into Johnny (`Format=PDF`) and executed an offline password audit session[cite: 26, 27].
4. **Access Verification:** Verified the recovered credential against the locked PDF document (`networkwalks_flag1.pdf`) to complete the lab challenge and capture the completion flag[cite: 29, 30].

---

## 🧠 Key Technical Concepts
* **Encryption vs. Hashing:** Encryption is a reversible two-way function that protects sensitive data and restores plaintext using the proper decryption key, whereas hashing is a one-way mathematical function that transforms input data into a fixed, unique message digest[cite: 30].
* **Offline Hash Auditing:** Password-protected PDFs store encryption metadata inside the file header. Once extracted into a compatible hash format (`$pdf$`), auditing tools can test candidate passwords locally against that digest[cite: 22, 27].

---

## 📸 Lab Evidence & Screenshots
* `screenshots/01-johnny-setup.png` — Configuring `john.exe` path inside Johnny GUI settings[cite: 21].
* `screenshots/02-pdf-hash-extracted.png` — Extracted `$pdf$` hash string formatted in UTF-8[cite: 23, 25].
* `screenshots/03-password-cracked.png` — Completed audit status (`100%`) inside Johnny[cite: 28].
* `screenshots/04-flag-captured.png` — Unlocked target PDF displaying the lab completion flag[cite: 30].
