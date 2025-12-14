# DVWA + ModSecurity WAF Uygulaması (Docker)

## 📌 Proje Amacı
Bu proje kapsamında, kasıtlı olarak zafiyetli bir web uygulaması olan **DVWA (Damn Vulnerable Web Application)**,
**OWASP ModSecurity Core Rule Set (CRS)** kullanılarak bir **Web Application Firewall (WAF)** arkasına alınmıştır.

Amaç; SQL Injection, XSS ve Command Injection gibi yaygın web saldırılarının
WAF tarafından nasıl tespit edilip engellendiğini gözlemlemektir.

---

## 🛠 Kullanılan Teknolojiler
- Docker & Docker Compose
- DVWA (Damn Vulnerable Web Application)
- OWASP ModSecurity CRS (Nginx)
- curl (terminal üzerinden testler)
- macOS (ARM64)

---

## 📂 Proje Yapısı

# DVWA + ModSecurity WAF Uygulaması (Docker)

## 📌 Proje Amacı
Bu proje kapsamında, kasıtlı olarak zafiyetli bir web uygulaması olan **DVWA (Damn Vulnerable Web Application)**,
**OWASP ModSecurity Core Rule Set (CRS)** kullanılarak bir **Web Application Firewall (WAF)** arkasına alınmıştır.

Amaç; SQL Injection, XSS ve Command Injection gibi yaygın web saldırılarının
WAF tarafından nasıl tespit edilip engellendiğini gözlemlemektir.

---

## 🛠 Kullanılan Teknolojiler
- Docker & Docker Compose
- DVWA (Damn Vulnerable Web Application)
- OWASP ModSecurity CRS (Nginx)
- curl (terminal üzerinden testler)
- macOS (ARM64)

---

## 📂 Proje Yapısı
waf-dvwa-modsecurity
├── docker-compose.yml
├── README.md
├── screenshots/
├── logs/
└── tests/


---

## 🚀 Kurulum Adımları

### 1️⃣ Docker servislerini başlat
Proje dizininde aşağıdaki komut çalıştırılır:

```bash
docker compose up -d


---

2️⃣ DVWA arayüzüne eriş
Tarayıcıdan:
http://localhost:8080
Giriş bilgileri:
Kullanıcı adı: admin
Şifre: password

3️⃣ Veritabanını oluştur
Giriş yaptıktan sonra:
Setup / Reset Database
Create / Reset Database butonuna basılır

4️⃣ Güvenlik seviyesini ayarla
DVWA menüsünden:
DVWA Security → Security Level → Low → Submit

🧪 Test Senaryoları
🔴 WAF OLMADAN (Doğrudan DVWA)
curl "http://localhost:8080/vulnerabilities/sqli/?id=1 OR 1=1"
curl "http://localhost:8080/vulnerabilities/xss_r/?name=<script>alert(1)</script>"
curl "http://localhost:8080/vulnerabilities/exec/?ip=8.8.8.8;ls"
➡️ Bu saldırılar başarılı şekilde çalışır.

🧪 Test Senaryoları
🔴 WAF OLMADAN (Doğrudan DVWA)
curl "http://localhost:8080/vulnerabilities/sqli/?id=1 OR 1=1"
curl "http://localhost:8080/vulnerabilities/xss_r/?name=<script>alert(1)</script>"
curl "http://localhost:8080/vulnerabilities/exec/?ip=8.8.8.8;ls"
➡️ Bu saldırılar başarılı şekilde çalışır.

📊 Sonuç ve Değerlendirme
Bu çalışmada, OWASP ModSecurity CRS kullanılarak yaygın web saldırılarının
başarılı bir şekilde engellendiği gözlemlenmiştir.
WAF kullanımı sayesinde:
SQL Injection
Cross Site Scripting (XSS)
Command Injection
gibi saldırılar uygulamaya ulaşmadan durdurulmuştur.

