\# 🛠 Setup Guide – OWASP Juice Shop API Testing

## 📌 Project Overview
This project demonstrates API testing and security analysis on OWASP Juice Shop using:

- Kali Linux
- Burp Suite
- Browser Developer Tools
- Nmap (basic reconnaissance)

---

# 1️⃣ Environment Setup

## 🔹 Step 1: Install OWASP Juice Shop

### Option 1 – Using Docker (Recommended)

```bash
docker pull bkimminich/juice-shop
docker run -d -p 3000:3000 bkimminich/juice-shop

Access the application in your browser:
http://localhost:3000

Option 2 – Using Node.js
git clone https://github.com/juice-shop/juice-shop.git
cd juice-shop
npm install
npm start

2️⃣ Configure Burp Suite

Open Burp Suite

Go to Proxy → Intercept → Turn Intercept ON

Configure browser proxy:

IP: 127.0.0.1

Port: 8080

Install Burp CA certificate in browser

3️⃣ Capturing API Request

Open Juice Shop in browser

Register a new user

Intercept the request:

POST /api/Users/
Send request to Repeater

Modify the email parameter to test validation

4️⃣ Example Response Observed
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
  "message": "Validation error",
  "errors": [
    {
      "field": "email",
      "message": "email must be unique"
    }
  ]
}
5️⃣ What This Demonstrates

Server-side validation

Unique constraint enforcement

Proper HTTP status codes

Structured JSON error handling

6️⃣ Tools Used

Kali Linux

Burp Suite Community Edition

OWASP Juice Shop

Nmap

7️⃣ Learning Outcomes

Understanding API endpoints

Intercepting HTTP requests

Analyzing server responses

Identifying validation mechanisms

Practical exposure to OWASP Top 10 vulnerabilities
