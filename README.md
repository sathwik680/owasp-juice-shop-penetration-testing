# owasp-juice-shop-penetration-testing
Manual web application security testing on OWASP Juice Shop using Burp Suite. Identified vulnerabilities including user enumeration, stack trace disclosure, and access control testing.

# OWASP Juice Shop - Web Application Penetration Testing

## 📌 Project Overview

This project demonstrates manual web application security testing performed on OWASP Juice Shop using Burp Suite Community Edition.

The objective of this project is to identify common web vulnerabilities based on the OWASP Top 10 methodology.

---

## 🛠 Tools Used

- Kali Linux
- Burp Suite Community Edition
- OWASP Juice Shop
- Chromium Browser

---

## 🎯 Target Application

- Application: OWASP Juice Shop
- Local URL: http://localhost:3000
- Purpose: Intentionally vulnerable web application for security training

---

## 🔍 Testing Methodology

- Intercepted HTTP requests using Burp Proxy
- Modified and replayed requests using Burp Repeater
- Tested input validation mechanisms
- Analyzed server responses
- Checked authentication and access control behavior

---

## 🧪 Vulnerabilities Identified

### 1️⃣ User Enumeration via Registration API

**Endpoint Tested:**
POST /api/Users/

**Finding:**
Application reveals whether an email address is already registered.

**Impact:**
Allows attackers to determine valid user accounts.

**OWASP Category:**
A01 – Broken Access Control

---

### 2️⃣ Stack Trace Disclosure

**Endpoint Tested:**
POST /api/Users/1

**Finding:**
Application exposes internal server file paths and framework details when invalid routes are accessed.

**Impact:**
Reveals backend implementation details that may help attackers craft targeted attacks.

**OWASP Category:**
A05 – Security Misconfiguration

---

### 3️⃣ Access Control Testing on User Endpoint

**Endpoint Tested:**
GET /api/Users/1

**Result:**
401 Unauthorized – Authorization header required.

**Conclusion:**
Endpoint is protected by JWT-based authentication.
No unauthenticated IDOR detected at this stage.

---

## 📊 Key Observations

- Sequential user IDs are exposed in API responses.
- Registration endpoint enforces unique email validation.
- JWT authentication is required for protected routes.
- Detailed error messages may lead to information disclosure.

---

## 🚀 Future Testing Plan

- SQL Injection testing on login endpoint
- Privilege escalation attempts
- JWT manipulation testing
- XSS vulnerability testing
- CSRF testing

---

## 📚 Learning Outcome

This project helped in understanding:

- HTTP request manipulation
- API security testing
- Authentication and authorization mechanisms
- OWASP Top 10 vulnerability categories
- Real-world penetration testing workflow

---

## ⚠ Disclaimer

This project is performed on a deliberately vulnerable application in a controlled lab environment for educational purposes only.
