# 🌐 Module 2: Browser-Based Hash Extraction & Dictionary Analysis

## 📌 Overview
This module documents **Week 3 — Project Module 2**, demonstrating how client-side web utilities can extract encryption hashes from a protected PDF (`My Locked PDF1.pdf`) and test password resilience through dictionary-based analysis without installing local software[cite: 32, 33].

---

## 🧰 Utilities & Architecture
* **Networkwalks Hash Calculator:** A browser-based cryptographic tool that computes MD5, SHA-1, SHA-256, SHA-384, and SHA-512 digests locally (using the browser's Web Crypto API for SHA algorithms) and parses password-protected PDFs client-side to output `pdf2john` / `hashcat`-compatible hashes without uploading files to external servers[cite: 34, 35].
* **Networkwalks Password Cracker (Dictionary Attack Lab):** A browser-based auditing lab that hashes candidate words from a built-in 100-password dictionary or a custom `.txt` wordlist and compares them against a target `$pdf$` hash[cite: 36].

---

## 🔍 Analyzed Document & Hash Metadata
* **Target File:** `My Locked PDF1.pdf` (`65.2 KB`)[cite: 35]
* **Hash Format:** `pdf2john / hashcat` compatible (`$pdf$4*4*128*...`)[cite: 35]
* **PDF Encryption Specs:** Revision `R4` | Version `V4` | Key Length `128-bit`[cite: 35]

---

## 🔄 Lab Workflow Summary
1. **Local PDF Parsing:** Loaded `My Locked PDF1.pdf` into the Networkwalks Hash Calculator to inspect its encryption header and extract the complete `$pdf$` hash string[cite: 34, 35].
2. **Dictionary Analysis:** Supplied the extracted hash to the Networkwalks Password Cracker and ran a dictionary check using the built-in wordlist to observe real-time candidate matching[cite: 36, 37].
3. **Credential Verification:** Applied the matched password to unlock the sample PDF and verify lab completion[cite: 37, 38].

---

## 🛡️ Security Takeaways & Best Practices
* **Deprecated Hash Algorithms:** Legacy algorithms such as **MD5** and **SHA-1** are cryptographically broken for password security and should only be used for basic file checksums or non-security integrity checks[cite: 34].
* **Password Entropy & Length:** A simple 8-character lowercase password or common dictionary word (such as `"123456"` or `"password"`) can be recovered within minutes, whereas a 12+ character passphrase combining uppercase, lowercase, numbers, and symbols can resist cracking attempts for many years[cite: 38].
* **Credential Exposure Risks:** With over 24 billion username and password pairs circulating from historical data breaches, avoiding common dictionary words and reusing passwords across accounts is critical[cite: 38].

---

## 📸 Lab Evidence & Screenshots
* `screenshots/01-nw-hash-calculator.png` — Client-side extraction of the `128-bit` (`R4/V4`) PDF hash[cite: 35].
* `screenshots/02-nw-dictionary-attack.png` — Dictionary match result in the Networkwalks Password Cracker[cite: 37].
* `screenshots/03-flag-unlocked.png` — Successful decryption of the protected PDF document[cite: 38].
