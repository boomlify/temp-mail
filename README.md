# Boomlify: Your Ultimate Temp Mail Solution 🚀

Welcome to **Boomlify** — the most powerful, feature-rich **temporary email** (temp mail) platform designed for developers, testers, and privacy-conscious users. Use Boomlify's **Temp Mail API** to integrate **disposable email** addresses directly into your applications for seamless **email testing**, **OTP verification**, **spam prevention**, and more.

---

## 🔥 Key Features of Boomlify

* **⏰ Time-Based Expiration**: Create emails lasting 10 minutes, 1 hour, or 1 day.
* **🏷️ Custom Domain Support**: Use your own verified domains (e.g., `mail.yourdomain.com`).
* **⚡ Memory-First Architecture**: Ultra-fast performance with smart caching (95% cache hit rate).
* **📊 Real-Time Usage Tracking**: Monitor API calls, expiration stats, and limits.
* **🔒 Secure API Key Authentication**: Industry-standard `X-API-Key` header support.
* **📧 Instant Email Delivery**: Real-time webhook processing (coming soon!).
* **🚀 High Performance**: Sub-100ms response times under high load.
* **📱 Cross-Platform Access**: Accessible via REST API, cURL, JavaScript, Python, PHP, and more.
* **🌍 Multi-Language Docs**: Comprehensive guides in English, Chinese, Arabic, and others.

---

## 🌐 Boomlify Temp Mail API Documentation

> **Beta Version Notice**: This is a **beta** API. Structure and endpoints may change. Get the latest base URL from [api-config.json](https://boomlify.com/api-config.json).

### 🏠 Base URLs

```text
Production: https://pleasedontuseapithereisinbuildapi.onrender.com/api/v1
dashboard: https://boomlify.com/auth
```

### 🔑 Authentication

All requests require an `X-API-Key` header or `api_key` query parameter:

```http
X-API-Key: api_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

**Alternative**:

```http
GET /api/v1/emails?api_key=api_XXXXXXXXXXXXXXXXXXXXXXXX
```

### 🚦 Rate Limits & Usage

* **Free Tier**:

  * 10-min emails: 20/day
  * 1-hour emails: 10/day
  * 1-day emails: 5/day
* **RPM**: 60 requests/min per API key
* **Concurrent**: 100 connections/IP

---

### 📨 Email Management Endpoints

| Endpoint                | Method | Description                                     |
| ----------------------- | ------ | ----------------------------------------------- |
| `/emails/create`        | POST   | Create a temporary email (`time`, `domain`)     |
| `/emails`               | GET    | List active emails (`limit`, `include_expired`) |
| `/emails/{id}`          | GET    | Get details for a specific email                |
| `/emails/{id}/messages` | GET    | Retrieve messages for an email                  |
| `/emails/{id}`          | DELETE | Delete an email address                         |

**Create Example**:

```bash
curl -X POST "https://.../api/v1/emails/create?time=1hour&domain=mail.yourdomain.com" \
  -H "X-API-Key: api_your_key_here"
```

---

### 📊 Account & Usage Endpoints

| Endpoint         | Method | Description                      |
| ---------------- | ------ | -------------------------------- |
| `/account/usage` | GET    | Get current usage stats          |
| `/account/info`  | GET    | Get account details and features |

---

## 📚 Code Examples

### JavaScript (Node.js)

```js
import fetch from 'node-fetch';
const API_KEY = 'api_YOUR_KEY';
const BASE = 'https://.../api/v1';

async function createTempMail() {
  const res = await fetch(`${BASE}/emails/create?time=10min`, { headers: { 'X-API-Key': API_KEY } });
  const data = await res.json();
  console.log('New Temp Mail:', data.email.address);
}

createTempMail();
```

### Python

```python
import requests
API_KEY = 'api_YOUR_KEY'
BASE = 'https://.../api/v1'
resp = requests.post(f"{BASE}/emails/create?time=10min", headers={'X-API-Key': API_KEY})
print(resp.json())
```

---

## 🔍 SEO & Keywords

**Anchor Texts**:

* [Temp Mail](https://boomlify.com)
* [Temporary Email](https://boomlify.com)
* [Boomlify API](https://boomlify.com/api-docs)
* Disposable Email
* Email Testing API
* OTP Verification Service
* Spam Prevention Tool

**Primary Keywords**: temp mail, temporary email, disposable email, Boomlify, Boomlify API, temp email service, email API

**Long-Tail Keywords**: fast temp mail API, custom domain disposable email, temporary email for testing, real-time temp mail webhooks

---

## 🤝 Contributing & Support

* **Issues & Feedback**: Create a GitHub issue in the [Boomlify Repo](https://github.com/yourusername/boomlify).
* **Community Chat**: Join our Telegram group [@boomlify](https://t.me/boomlify).
* **API Support**: Email us at [support@boomlify.com](mailto:support@boomlify.com) or visit the [dashboard](https://boomlify.com/auth).

---

## 📄 License

Boomlify Temp Mail is released under the **MIT License**.

---

> *Boomlify*: Your go-to platform for **secure**, **scalable**, and **fast** temporary email solutions. Integrate today and keep your workflows hassle-free! 🎉
