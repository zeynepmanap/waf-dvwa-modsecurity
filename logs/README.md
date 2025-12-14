# ModSecurity WAF Logları

Bu klasörde, OWASP ModSecurity Core Rule Set (CRS) tarafından
tespit edilen ve engellenen saldırılara ait örnek log kayıtları yer almaktadır.

Loglar, WAF’ın SQL Injection, XSS ve Command Injection saldırılarını
nasıl algıladığını göstermek amacıyla eklenmiştir.

---

## 🔐 SQL Injection Log Örneği

```log
Message: SQL Injection Attack Detected
Rule ID: 942100
Severity: CRITICAL
Request URI: /vulnerabilities/sqli/
Action: Blocked (403 Forbidden)

# ModSecurity WAF Logları

Bu klasörde, OWASP ModSecurity Core Rule Set (CRS) tarafından
tespit edilen ve engellenen saldırılara ait örnek log kayıtları yer almaktadır.

Loglar, WAF’ın SQL Injection, XSS ve Command Injection saldırılarını
nasıl algıladığını göstermek amacıyla eklenmiştir.

---

🔐 XSS Log Örneği
Message: Cross Site Scripting (XSS) Attack Detected
Rule ID: 941100
Severity: HIGH
Request URI: /vulnerabilities/xss_r/
Action: Blocked (403 Forbidden)


🔐 Command Injection Log Örneği
Message: Command Injection Attempt Detected
Rule ID: 932100
Severity: CRITICAL
Request URI: /vulnerabilities/exec/
Action: Blocked (403 Forbidden)
