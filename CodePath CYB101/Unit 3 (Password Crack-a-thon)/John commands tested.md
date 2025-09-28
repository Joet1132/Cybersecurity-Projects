# John Commands tested 
```bash
john --wordlist=rockyou.txt --rules=Single --min-length=5 --max-length=5 --format=md5crypt-long cp_leak.txt #208 passwords cracked for this john variant
john --wordlist=lower.lst --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --format=md5crypt-long cp_leak.txt
john --wordlist=100k-most-used-passwords-NCSC.txt --format=md5crypt-long cp_leak.txt
john --mask=?d?d?d?d --min-length=1 --max-length=5 --format=md5crypt-long cp_leak.txt
john --mask=?1?1?1?1?1?1 --1=[a-zA-Z0-9] --min-length=1 --max-length=6 --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --rules=l33t --format=md5crypt-long cp_leak.txt
john --mask=?u?l?l?l?d --min-length=1 --max-length=5 --format=md5crypt-long cp_leak.txt
john --mask=?u?d?l?1 --1=[a-zA-Z0-9] --min-length=1 --max-length=4 --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --min-length=3 --max-length=3 --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --min-length=7 --max-length=8 --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --rules=Single --min-length=7 --max-length=8 --format=md5crypt-long cp_leak.txt
john --mask=?1?1?1?1?1?1?1?1 --1=[a-zA-Z0-9] --min-length=7 --max-length=8 --format=md5crypt-long cp_leak.txt
john --mask=?u?l?l?l?d --min-length=5 --max-length=5 --format=md5crypt-long cp_leak.txt
john --mask=?u?u?u?u?u --min-length=1 --max-length=5 --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --rules --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --rules=Jumbo --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --rules=Jumbo --min-length=1 --max-length=5 --format=md5crypt-long cp_leak.txt
john --mask=?1?1?1?1?1 --1=[A-Z] --min-length=5 --max-length=5 --format=md5crypt-long cp_leak.txt
john --mask=?s?s?s?s?s --min-length=1 --max-length=5 --format=md5crypt-long cp_leak.txt
john --mask=?u?l?l?s?d --min-length=4 --max-length=5 --format=md5crypt-long cp_leak.txt
john --wordlist=rockyou.txt --rules=Single --min-length=6 --max-length=6 --format=md5crypt-long cp_leak.txt
