# Protecting Against Rainbow Tables

Rainbow tables are precomputed tables used to reverse cryptographic hash functions, primarily for cracking password hashes. To effectively protect against rainbow table attacks, **salting** is essential.

## What is a Salt?

A **salt** is a randomly generated value added to a password before hashing. This ensures that even if two users have the same password, their final hashed values will be different.

- The salt should be **unique per user**.
- It is stored in the database **alongside the hash**.
- It does **not need to be kept secret**.

Although using the same salt for all users might seem simpler, it defeats the purpose: duplicate passwords would still result in identical hashes, enabling targeted rainbow table generation.

## How Does Salting Work?

The salt is usually:
- Appended or prepended to the password string.
- Combined with the password before applying the hash function.
- Automatically handled by modern hashing algorithms like **Bcrypt**, **Scrypt**, and **Argon2**.

### Benefits of Salting:
- Defeats precomputed rainbow tables.
- Makes brute-force attacks significantly more expensive and slower.
- Ensures **unique hashes for identical passwords**.

---

## Example: Securely Storing Passwords

To securely store passwords, follow these best practices:

1. **Choose a secure hash function**:
   - `Argon2`, `Scrypt`, `Bcrypt`, or `PBKDF2`.

2. **Generate a unique salt** for each user:
   ```text
   Salt: Y4UV*^(=go_!

3. **Concatenate the password with the salt**:
```text
Password: AL4RMc10k  
Combined: AL4RMc10kY4UV*^(=go_!
```

4. **Hash the combined string using your chosen secure algorithm**

Store the hash and the salt in your database:
```text
{
  "salt": "Y4UV*^(=go_!",
  "hash": "<calculated_hash_value>"
}

```

🔐 Always check your industry or compliance standards (e.g., NIST, GDPR) for storing passwords securely.
