### 1. **General Cryptography Principles**

1.  **Differences between symmetric and asymmetric encryption?**

    - Symmetric encryption uses a single key for both encryption and decryption (e.g., AES), while asymmetric encryption uses a pair of keys (public and private) for encryption and decryption (e.g., RSA). Symmetric encryption is faster and used for bulk data, whereas asymmetric is used for key exchange and digital signatures.
2.  **How does Public Key Infrastructure (PKI) work?**

    - PKI uses a hierarchy of digital certificates, issued by Certificate Authorities (CAs), to validate identities and facilitate secure communication through the use of public and private key pairs.
3.  **Difference between encryption, hashing, and encoding?**

    - Encryption ensures confidentiality and can be reversed with a key. Hashing ensures data integrity and cannot be reversed (e.g., SHA-256). Encoding transforms data for transport without security considerations (e.g., Base64).
4.  **What is a digital signature?**

    - A digital signature is created using a private key to sign data, providing integrity, authenticity, and non-repudiation. It is verified using the corresponding public key.
5.  **Common cryptographic attacks and defenses?**

    - Attacks like man-in-the-middle can be prevented using TLS. Replay attacks can be mitigated using nonces and timestamps. Brute force attacks can be reduced using strong keys and rate limiting.

### 2. **Encryption & Hashing Algorithms**

1.  **Secure encryption algorithms for modern applications?**

    - Use AES (Advanced Encryption Standard) for symmetric encryption and RSA or ECC for asymmetric encryption. AES is generally preferred for its balance of security and performance.
2.  **How to generate a secure key in Node.js?**

    - Use `crypto.randomBytes()` for secure random key generation. Store keys in secure locations like environment variables or dedicated key management services (e.g., AWS KMS).
3.  **What is a salt and why is it used?**

    - A salt is a random value added to passwords before hashing to ensure that even identical passwords have unique hashes. This prevents rainbow table attacks.
4.  **Implementing and validating HMAC in Node.js?**

    - Use the `crypto.createHmac()` method. Generate an HMAC using a secret key and validate it by comparing the received HMAC with one generated server-side.
5.  **Explain AES and its modes of operation?**

    - AES is a symmetric encryption algorithm. Modes like CBC (Cipher Block Chaining) and GCM (Galois/Counter Mode) define how data is split, encrypted, and chained. GCM also provides integrity checks.

### 3. **Node.js Security Practices**

1.  **Secure communication between microservices in Node.js?**

    - Use TLS for encrypted communication and implement mutual TLS if needed. Secure headers and token-based authentication (JWT) should also be used.
2.  **Implementing JWT authentication and security considerations?**

    - Use the `jsonwebtoken` library to sign and verify tokens. Ensure tokens are short-lived, use a strong secret/key, and validate the `aud`, `iss`, and `exp` claims.
3.  **Mitigating vulnerabilities in Node.js apps?**

    - Use input validation, parameterized queries, escaping user inputs, and libraries like `helmet` for HTTP headers security. Implement CSP (Content Security Policy) to prevent XSS.
4.  **Protecting sensitive data in transit and at rest?**

    - Use TLS for data in transit and encryption (e.g., AES) for data at rest. Consider using secure libraries like `crypto` in Node.js and external tools like HashiCorp Vault for sensitive data management.
5.  **Cryptographic libraries in Node.js?**

    - Use `crypto` for hashing, encryption, and decryption. Libraries like `jsonwebtoken` for JWT, and `bcrypt` or `argon2` for secure password hashing.

### 4. **Identity and Authentication**

1.  **Implementing OAuth2.0 and OpenID Connect in Node.js?**

    - Use libraries like `passport` or `node-oidc-provider`. Implement different OAuth2 flows (e.g., authorization code flow) depending on use cases, and handle tokens securely (e.g., validate scopes and claims).
2.  **Securing password-based authentication?**

    - Use strong hashing algorithms like bcrypt or Argon2, rate limiting, and account lockout mechanisms. Implement MFA for additional security.
3.  **Implementing secure refresh tokens?**

    - Store refresh tokens in httpOnly, secure, and same-site cookies. Rotate refresh tokens upon use to reduce risk if compromised.
4.  **How does the OAuth2 authorization code flow work?**

    - The client gets an authorization code from the authorization server after the user grants permission, then exchanges the code for an access token to access resources.

### 5. **Advanced Topics**

1.  **How does a Diffie-Hellman key exchange work?**

    - Two parties share public values and use their private values to compute a shared secret key, which is never transmitted directly. It's used to establish a secure channel.
2.  **Difference between ECC and RSA?**

    - ECC offers similar security to RSA but with smaller key sizes, making it faster and more efficient. ECC is generally recommended over RSA for modern applications.
3.  **Implementing secure key rotation strategy?**

    - Use key versioning, periodically update keys, and ensure backwards compatibility. Automate key rotation using cloud services like AWS KMS or HashiCorp Vault.
4.  **End-to-end encryption in a messaging app?**

    - Use public key cryptography for initial key exchange and symmetric keys (e.g., AES) for message encryption. Implement forward secrecy by frequently rotating keys.
5.  **Zero-knowledge proof and a practical example?**

    - A zero-knowledge proof allows one party to prove knowledge of a secret without revealing it. Example: proving you know a password without sending the actual password.

### 6. **Practical Implementation & Troubleshooting**

1.  **Troubleshooting decryption failures?**

    - Check for mismatched keys, incorrect initialization vectors (IVs), or corrupted ciphertext. Validate that the same algorithm and padding are used for both encryption and decryption.
2.  **Common mistakes when using cryptographic libraries?**

    - Using weak or default keys, reusing nonces, not handling exceptions correctly, or failing to securely delete sensitive data from memory.
3.  **Handling secure storage of credentials?**

    - Use environment variables or secrets management services like AWS Secrets Manager. Avoid hardcoding credentials in the source code.
