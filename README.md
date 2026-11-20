# 🔐 Week 3 – Password Cracking & Security Auditing

A hands-on cybersecurity project documenting two password auditing practicals completed as part of the NetworkWalks Cybersecurity & Ethical Hacking training program.

The project explores password recovery techniques using **John the Ripper (JTR)** and **NetworkWalks online tools**, demonstrating how password-protected PDF files can be audited through hash extraction and dictionary attacks.

---

## 🛠️ Technologies & Tools

- Kali Linux
- John the Ripper (Jumbo)
- pdf2john.pl
- RockYou Wordlist
- NetworkWalks Hash Calculator
- NetworkWalks Password Cracker
- Web Browser
- Linux Terminal

---

## 🔹 W3-PM1: Password Cracking with John the Ripper

### Objective
To recover the password of an authorized password-protected PDF file using John the Ripper through hash extraction and a dictionary attack.

### Practical Workflow

**1. Verify John the Ripper installation**

```bash
john
```

**2. Locate PDF hash extraction scripts**

```bash
find /usr/share/john /usr/lib -iname '*pdf2john*' 2>/dev/null
```

**3. Create a working directory**

```bash
mkdir -p ~/JTR_Lab
cd ~/JTR_Lab
```

**4. Extract the PDF hash**

```bash
perl /usr/share/john/pdf2john.pl ~/Desktop/My-Locked-PDF1.pdf > hash1.txt
```

**5. Verify the extracted hash**

```bash
cat hash1.txt
```

**6. Prepare the RockYou wordlist**

```bash
sudo gzip -dk /usr/share/wordlists/rockyou.txt.gz
```

**7. Perform a dictionary attack**

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt
```

**8. Display the recovered password**

```bash
john --show hash1.txt
```

### Result

Successfully extracted the PDF hash and recovered the password using John the Ripper and the RockYou wordlist.

### Key Concepts Learned

- Password hash extraction
- Dictionary-based password attacks
- Wordlist usage
- John the Ripper commands
- PDF password auditing

---

## 🔹 W3-PM2: Password Cracking with NetworkWalks Tools

### Objective
To recover the password of a protected PDF using two free browser-based tools provided by NetworkWalks.

### Tools Used

1. **Hash Calculator:** Extracts the password hash from an encrypted PDF.
2. **Password Cracker:** Performs a dictionary attack on the extracted hash to identify the matching password.

### Practical Workflow

**Step 1: Download the encrypted PDF**

Obtain the lab PDF from the NetworkWalks project page.

[Download Lab Instructions](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/)

**Step 2: Open NetworkWalks Hash Calculator**

[Hash Calculator](https://networkwalks.com/hash-calculator/)

**Step 3: Upload the protected PDF**

Upload the PDF using the File option. The tool extracts the PDF hash.

**Step 4: Copy the complete hash**

Copy the entire hash value beginning with `$pdf$`.

**Step 5: Open NetworkWalks Password Cracker**

[Password Cracker](https://networkwalks.com/password-cracker/)

**Step 6: Paste the hash and start the attack**

Paste the extracted hash into the Password Cracker and start the dictionary attack.

**Step 7: Wait for the result**

The tool tests password candidates and displays the recovered password when a match is found.

**Step 8: Enter the recovered password**

Open the protected PDF and enter the recovered password.

**Step 9: Verify successful access**

The PDF opens successfully, confirming completion of the practical.

### Result

Successfully extracted the PDF hash using NetworkWalks Hash Calculator and recovered the password using NetworkWalks Password Cracker.

### Key Concepts Learned

- Online hash extraction
- Dictionary attacks
- PDF password recovery
- Browser-based cybersecurity tools
- Password security awareness

---

## 📸 Practical Evidence

Screenshots documenting the practical implementations:

### W3-PM1 – John the Ripper
- JTR installation and version verification
- PDF hash extraction
- RockYou wordlist preparation
- Dictionary attack execution
- Password recovery verification

### W3-PM2 – NetworkWalks Tools
- Hash Calculator interface
- PDF hash extraction
- Password Cracker interface
- Dictionary attack execution
- Successful password recovery
- Successfully opened PDF

*Add your practical screenshots to the repository's evidence folder.*

---

## 📚 Key Learnings

Through these practicals, I gained hands-on experience with:

- Understanding password hashes and password recovery.
- Extracting hashes from encrypted PDF documents.
- Performing dictionary attacks using John the Ripper.
- Working with RockYou wordlists in Kali Linux.
- Using browser-based password auditing tools.
- Understanding the importance of strong and complex passwords.

## 🔒 Ethical Considerations

These techniques were performed for educational purposes in a controlled lab environment using authorized sample files.

Password auditing tools should only be used on files and systems that you own or have explicit permission to test.

Sensitive files, extracted hashes, and recovered passwords should not be published in public repositories.

---

**Focus:** Password Auditing 
