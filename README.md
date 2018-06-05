## Introducton to Cryptography

- Hashes
- Symmetric Encryption
- Asymmetric Encryption
- Padding
- Message Authentication Codes
- Signatures
- Secure Channels

---

### Hashes

#### Common Hashing Alogrithms

- Historical (insecure)
- Modern (Secure)
- Key stretching

#### Historic Hashing Algorithms

- MD5
	- Message Digest 5
	- Known to be susceptible to collision attack since 2004
- SHA1
	- Secure Hashing Algorithm 1
	- Majority of companies migrated away by the end of 2017
	- Collision attack proved by Google in 2018

#### Modern Hashing Algorithms

- SHA2
	- Secure Hashing Algorithm 2
	- Still considered secure, as of mid 2018
- SHA3
	- Released in 2015

#### Key Stretching

- PBKDF2
	- Password-based Key Derivation Function 2
	- Adjustable CPU cost
	- Can be implemented on ASIC chips
- BCRYPT
	- Adjustable CPU cost
	- High memory cost
- SCRYPT
	- Adjustable CPU cost
	- Adjustable memory cost

---

### Symmetric Encryption

- Block Ciphers
	- DESkPBKDF2
	- Blowfish
	- AES (128/192/256)
- AES Encryption Modes
	- ECB
	- CTR
	- CBC
- IVs
- Padding

#### AES ECB
- Electronic Codebook Mode
- Block cipher
- INSECURE
- Each block is encrypted independenly
- Matching plaintext blocks produce matching ciphertext blocks
- <i>C<sub>i</sub> = E( K, P<sub>i</sub> ) for i = 1,...,k</i>

#### AES CBC
- Cipher Block Chaining
- Block cipher
- Secure
- IV or ciphertext is XORed with plaintext prior to AES encryption
- <i>C<sub>1</sub> = E( K, P<sub>1</sub> XOR IV )</i>
- <i>C<sub>i</sub> = E( K, P<sub>i</sub> XOR C<sub>i-1</sub> ) for i = 2,...,k</i>

#### AES CTR
- Counter mode
- Stream cipher
- Secure
- Each bit is XORed with a stream produced by CTR-DRNG
- Parallelizable; Catastrophic when reusing IV
- <i>K<sub>i</sub> = E( K, IV || i )</i> for i = 1,...,k</i>
- <i>C<sub>i</sub> = P<sub>i</sub> XOR K<sub>i</sub> for i = 1,...,k</i>

#### IVs

| IV      | Secure | Description |
|---------|--------|-------------|
| Fixed   | FALSE  |             |
| Counter | FALSE  |             |
| Random  | TRUE   |             |
| Nonce   | TRUE   |             |

#### Padding
- Not explicitly needed for stream ciphers
- Zero padding
	- ... | DD DD DD DD DD DD DD DD | DD DD DD DD 00 00 00 00 |
- ANSI X.923
	- ... | DD DD DD DD DD DD DD DD | DD DD DD DD 00 00 00 04 |
- PKCS#7
	- ... | DD DD DD DD DD DD DD DD | DD DD DD DD 04 04 04 04 |
- ISO/IEC 7816-4
	- ... | DD DD DD DD DD DD DD DD | DD DD DD DD 80 00 00 00 |

#### Other Symmetric Ciphers

- DES
- Blowfish

---

### Asymmetric Encryption

- RSA

#### RSA

- Private key
	- Decryption
	- Signatures
- Public key
	- Encryption
	- Signature verification

---

### Message Authentication Codes

- Message  Authentication Code
- Encryption vs HASH vs MAC
	- Encryption: The message hasn't been read
	- Hash: The message hasn't been corrupted
	- MAC: The message hasn't been tampered with
- HMAC
	- "Hash with a key"
	- MAC with a Hash

---

### Signatures...


- 

---

### Secure Channels

- Symmetric
- Asymmetric

#### Symmetric
INSERT DIAGRAM

#### Asymmetric
INSERT DIAGRAM

---

## JavaScript Crypography Libraries

- Libraries
	- Node Forge
	- CryptoJS
	- NodeJS Crypto Module (Server only)
	- Web Standards
- Can I use?
- Features / Limitations
	- Supported algorithms
	- Ease of use
	- Quirks
- Audit reports

###  

## Demo

- Written in Anuglar + TypeScript
- Code on GitHub /microupoad

### Application Logic

### 

## Resources

| Title | Author | URL |
|---|---|---|
| Evaluation of Some Blockcipher Modes of Operation | Phillip Rogaway University of California | http://web.cs.ucdavis.edu/~rogaway/papers/modes.pdf |
