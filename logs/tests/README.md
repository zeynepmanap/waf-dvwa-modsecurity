# WAF Test Senaryoları

Bu klasörde, DVWA uygulaması üzerinde gerçekleştirilen
saldırı testlerine ait örnek komutlar yer almaktadır.

Testler, WAF bulunmadan ve WAF aktifken olacak şekilde
iki farklı senaryo üzerinden gerçekleştirilmiştir.

---

## 🧪 Test Ortamı
- DVWA: http://localhost:8080
- WAF (ModSecurity): http://localhost:8081
- Test aracı: curl (terminal)

---

## 🔴 WAF OLMADAN (Doğrudan DVWA)

### SQL Injection Testi
```bash
curl "http://localhost:8080/vulnerabilities/sqli/?id=1 OR 1=1"

XSS Testi
curl "http://localhost:8080/vulnerabilities/xss_r/?name=<script>alert(1)</script>"


Command Injection Testi
curl "http://localhost:8080/vulnerabilities/exec/?ip=8.8.8.8;ls"

📌 Beklenen Sonuç:
Saldırı istekleri başarılı şekilde çalışır.

🛡 WAF AKTİF (ModSecurity Üzerinden)

SQL Injection Testi
curl "http://localhost:8081/vulnerabilities/sqli/?id=1 OR 1=1"

XSS Testi
curl "http://localhost:8081/vulnerabilities/xss_r/?name=<script>alert(1)</script>"

Command Injection Testi
curl "http://localhost:8081/vulnerabilities/exec/?ip=8.8.8.8;ls"

📌 Beklenen Sonuç:
İstekler ModSecurity WAF tarafından engellenir (403 Forbidden).

📊 Değerlendirme
Test sonuçları incelendiğinde, OWASP ModSecurity CRS’in
yaygın web saldırılarını başarıyla tespit edip engellediği
gözlemlenmiştir.
