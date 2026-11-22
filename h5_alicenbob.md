## x) Summary
- Schneier 2015: [Applied Cryptography](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/)
  - Chapter 1 - Foundations
    - 1.1 Terminology
      - Sender and Receiver: a sender wants to send a securely message to a receiver.
      - Messages and Encryption: 
        ```mermaid
        ---
        title: Encryption and Decryption
        ---
        flowchart LR
            A[Plaintext] --> B[Encryption]
            B --> C[Ciphertext]
            C --> D[Decryption]
            D --> E[Plaintext]
        ```
        Plaintext is binary data i.e bits, text file, bitmap, audio, video etc. ISO 7498-2 standard uses the terms “encipher” and “decipher, “encrypt” and “decrypt” refer to dead bodies in some cultures.
        - Encryption converts message to ciphertext E(M) = C
        - Decryption converts ciphertext back to message D(C) = M
        - Correct encryption or decryption satisfies D(E(M)) = M
          - C: ciphertext
          - D: decryption function
          - E: encryption function
          - M: message or plaintext (P)
      - Authentication, Integrity, and Nonrepudiation:
        - Authentication: verifies the origin of a message.
        - Integrity: verifies that a message was not modified.
        - Nonrepudiation: prevents a sender from falsely denying sending a message.
      - Algorithms and Keys
        ```mermaid
        ---
        title: Encryption and Decryption with a Key
        ---
        flowchart LR
            K1["Key K"] --> E["Encryption"]
            M["Plaintext M"] --> E
            E --> C["Ciphertext C"]
            C --> D["Decryption"]
            K2["Key K"] --> D
            D --> M2["Plaintext M"]
        ```
        
        Modern cryptography should rely on the secrecy of the **key**, not secrecy of the algorithm.
     
        ```mermaid
        ---
        title: Encryption and Decryption with Two Different Keys
        ---
        flowchart LR
            K1["Encryption Key K₁"] --> E["Encryption"]
            M["Plaintext M"] --> E
            E --> C["Ciphertext C"]
            C --> D["Decryption"]
            K2["Decryption Key K₂"] --> D
            D --> M2["Plaintext M"]
        ```
        
        - E<sub>K</sub>(M) = C
        - D<sub>K</sub>(C) = M
        - D<sub>K</sub>(E<sub>K</sub>(M)) = M

      - Symmetric Algorithms
      - Public-Key Algorithms (From start until the end of Algorithms; not Cryptoanalysis and onwards)
  - Chapter 2 - Protocol Building Blocks, sections
    - 2.5 Communications Using Public-Key Cryptography (From the start of "Communications using Public Key" until the start of "Digital signatures with encryption")
- Karvinen 2023: [PGP - Send Encrypted and Signed Message - gpg](https://terokarvinen.com/2023/pgp-encrypt-sign-verify/)

## a) Pubkey today
Explain how you have used public key cryptography today or yesterday, outside of this homework. In addition to naming the system, identify how different parties use keys in different steps of the system

## b) Encrypt and decrypt a message
Explain how different parties use different keys at different stages of operation. Evaluate the security of the tool you've chosen.

## c) Password management
Demonstrate use of a password manager. What kind of attacks take advantage of people not using password managers.

## d) Voluntary: Details of PGP
Send an encrypted and signed message using PGP, then verify and decrypt it. (You can use folders to simulate users, or use two computers or two different OS users).

## e) Voluntary
[Cryptopals: Challenge Set 1](https://www.cryptopals.com/sets/1)
1. Convert hex to base64 (feel free to use a library for base64)
2. Fixed XOR
3. Single-byte XOR cipher
4. [Detect single-character XOR](https://www.cryptopals.com/sets/1/challenges/4)
