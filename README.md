# Secure-Hashing-and-Encryption

## Overview
This application demonstrates fundamental cryptographic concepts: file/string hashing, symmetric encryption, and asymmetric digital signatures. It was built using Python to fulfill the requirements of the Cryptography Foundations assignment.

## How to Run the Code
1. Ensure you have Python 3 installed on your machine.
2. Install the required cryptography library by running: `pip install cryptography`
3. Navigate to the directory containing the file in your terminal.
4. Run the script using the command: `python crypto_app.py`
5. The console will output a step-by-step demonstration of hashing, encryption/decryption, and digital signatures.

## Cryptographic Methods Explained

### 1. SHA-256 Hashing (Integrity)
**How it works:** SHA-256 (Secure Hash Algorithm 256-bit) is a cryptographic hashing function that takes an input (string or file) and produces a fixed-size 256-bit (32-byte) hash value. 
**App Functionality:** The app reads a string or a file block-by-block and passes it through Python's `hashlib` library. It demonstrates file integrity because even a single altered character in the input will result in a completely different output hash.

### 2. Caesar Cipher (Confidentiality)
**How it works:** This is a simple substitution cipher that replaces each letter in a text with a letter a fixed number of positions down the alphabet. 
**App Functionality:** The application takes an input string and a "shift" integer. During encryption, it shifts characters forward in the ASCII table (wrapping around at 'Z'). During decryption, it shifts them backward by the same amount, restoring the original text. It safely ignores spaces and punctuation.

### 3. Digital Signatures (Authentication & Non-Repudiation)
**How it works:** Digital signatures use asymmetric cryptography (a public/private key pair). A sender hashes a message and encrypts that hash with their *private key*. The receiver decrypts the signature with the sender's *public key* and compares the hash to verify the sender's identity and ensure the message wasn't altered.
**App Functionality:** The app generates a 2048-bit RSA key pair. It signs a string message with the private key. It then verifies the signature twice: once against the original message (which passes) and once against an altered message (which fails), proving the mechanism works.
