# Password Cracking with John the Ripper & Johnny GUI

Penetration-testing style write-up for a Networkwalks Cybersecurity Internship module: recovering the password of protected PDF files using **John the Ripper (JTR)** and its GUI front-end **Johnny**.

## 📌 Overview
This project documents the full password-recovery workflow against three training PDF files, from hash extraction through to verified password recovery, following a formal pentest-reporting structure (scope, tools, methodology, findings, recommendations).

## 🎯 Objective
Recover the password protecting `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, and `My Locked PDF3.pdf` using JTR and Johnny on Windows, and verify the recovered password by opening each file.

## 🛠️ Tools Used
- John the Ripper — Jumbo build 1.9.0 (Win64)
- Johnny GUI 2.2
- Online PDF Hash Extractor (pdf2john-equivalent)
- Notepad
- Adobe Acrobat Reader DC

## 📝 Methodology

### Step 1: Download & Configure the Tools
John the Ripper and Johnny GUI were downloaded, and Johnny was pointed to John's executable.

![Tools Downloaded](images/01-jtr-johnny-downloaded.png)
![Johnny Configured](images/02-johnny-john-path-configured.png)

### Step 2: Extract the Hash from the Locked PDF
The protected PDF was uploaded to an online hash-extraction tool to generate a crackable hash.

![Browse PDF](images/03-browse-pdf-for-hash.png)
![Hash Extracted](images/04-hash-extracted.png)

### Step 3: Save the Hash
The extracted hash was saved as a plain text file for Johnny to load.

![Hash Saved](images/05-hash-saved-notepad.png)

### Step 4: Run the Attack
The hash file was loaded into Johnny and the attack was started.

![Password Cracked](images/06-password-cracked-johnny.png)

### Step 5: Verify by Opening the PDFs
The recovered password successfully unlocked all three test files.

![PDF Unlocked 1](images/07-pdf-unlocked-flag1.png)
![PDF Unlocked 2](images/08-pdf-unlocked-flag2.png)
![PDF Unlocked 3](images/09-pdf-unlocked-flag3.png)

## ✅ Result
All three protected PDFs were successfully unlocked using the password recovered by John the Ripper / Johnny, within seconds of starting the attack — indicating the test passwords were weak/predictable rather than long random passphrases.

## 💡 Key Takeaways
- Weak or common passwords can be cracked almost instantly with freely available tools.
- Converting a protected file into a crackable hash (`pdf2john` format) is the essential first step before any cracking attempt.
- PDF password protection (128-bit RC4/AES, revision 4) is far weaker than modern AES-256 (revision 6) encryption.
- Password protection is a deterrent, not a strong security control — an attacker with the file can make unlimited offline guesses.

## ⚠️ Disclaimer
This project was performed in a **controlled training environment** using test files supplied as part of a cybersecurity course module. Do not use password-cracking tools against any file or system without explicit authorization.

## 📚 References
- [John the Ripper – Openwall](https://www.openwall.com/john/)
- [Johnny GUI](https://openwall.info/wiki/john/johnny)

---
**Author:** Minakshee Mahendra Yadav
