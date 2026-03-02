🛠 Setup Guide – OWASP Juice Shop API Testing
📌 Project Overview

This project demonstrates API testing and security analysis on OWASP Juice Shop using:

Kali Linux

Burp Suite

Browser Developer Tools

Nmap (basic recon)

1️⃣ Environment Setup
🔹 Step 1: Install OWASP Juice Shop
Option 1 – Using Docker (Recommended)
docker pull bkimminich/juice-shop
docker run -d -p 3000:3000 bkimminich/juice-shop

Access in browser:

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

Open Juice Shop

Register a new user

Intercept request:

POST /api/Users/

Forward request to Repeater

Modify email to test validation

4️⃣ Observed Response

Example response:

HTTP/1.1 400 Bad Request
{
  "message":"Validation error",
  "errors":[
     {
       "field":"email",
       "message":"email must be unique"
     }
  ]
}
5️⃣ What This Shows

Input validation is implemented

Unique constraint on email

Proper HTTP status code (400)

JSON error response structure

6️⃣ Tools Used

Kali Linux

Burp Suite Community Edition

OWASP Juice Shop

Nmap
