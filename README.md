# PIHASH---Password-Manager
A secure Java-based password manager with AES encryption. Features user authentication, encrypted vaults, password generation, search, import/export, and a Swing GUI. Passwords are stored securely and revealed on click using the master password.
# 🔐 PIHASH – Java Password Manager with AES Encryption and GUI

PIHASH is a secure, GUI-based password manager built in Java. It lets users register and authenticate with a master password, then store and manage site credentials (site, username, password) securely. All passwords are AES-encrypted using the master password as the encryption key.

## 🎯 Features

- 🔑 **User Authentication**
  - Signup and login system using master password
  - User details stored securely in `users.txt`
  
- 🔐 **Encrypted Password Vault**
  - Vaults are saved in the `/vaults/` directory
  - AES encryption using the master password ensures data confidentiality

- 🧠 **Password Reveal**
  - Click on the hidden password to toggle visibility
  - Auto-masked (`********`) display on load for privacy

- ✏️ **Vault Management**
  - Add, edit, delete credentials
  - Entries include Site, Username, and Encrypted Password
  - Strong password generation (16 characters)

- 🔍 **Search Function**
  - Search by site name or username
  - Automatically highlights matching entry

- 📥📤 **Import/Export Support**
  - Easily import/export vaults as `.txt` files

- 🖼️ **Graphical UI**
  - Custom background (`vault.png`, `sign.png`)
  - Java Swing-based GUI with styled buttons, labels, and text fields

---

## 🛠️ Technologies Used

| Technology | Description |
|------------|-------------|
| Java       | Core language |
| Swing      | GUI interface |
| AES (Java Cryptography API) | Password encryption/decryption |
| File I/O   | Read/write user and vault files |

---

## 🗂️ File Structure

PIHASH/
│
├── vaults/ # Vault storage (username.txt files)
├── PIHASH.java # Entry point: Login + Signup GUI
├── VaultFrame.java # Main Vault GUI interface
├── users.txt # Stores registered users
├── sign.png # Signup/Login background
└── vault.png # Vault interface background

---

## 🔐 How It Works

1. **Signup:**
   - User provides personal info, email, username, and master password.
   - User is saved in `users.txt` with SHA-256 hashed password.
   - Vault file is created at `vaults/username.txt`.

2. **Login:**
   - User enters email and master password.
   - Master password is hashed and checked against stored hash.

3. **VaultFrame GUI:**
   - Loads encrypted vault file on login.
   - Passwords are shown as `********`.
   - Clicking on a password reveals the decrypted text.
   - Edits are saved back encrypted using AES and the master password.

---

## 🧪 Example Entry in vaults/username.txt

example.com,myusername,Bs3ldfKJE1h38fasdj== (AES Encrypted)

---

## 🚧 Requirements

- Java 8 or higher
- JDK properly installed and configured

---

## 🧭 How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/pihash.git
   cd pihash
2. Compile the code:
   javac PIHASH.java VaultFrame.java
   
4. Run the application:
   java PIHASH
