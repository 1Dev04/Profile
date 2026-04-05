<div id="header" align="center">
  <img src="https://media.giphy.com/media/ES9cAJlcxblRESzOH1/giphy.gif" width="100"/>
</div>

<h1 align="center">Profile</h1>

<div id="badges" align="center">
  <a href="https://www.linkedin.com/in/krittiphon-yoonaitham-a291482b1/?originalSubdomain=th">
    <img src="https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge"/>
  </a>
  <a href="https://www.youtube.com/@DEVDummy">
    <img src="https://img.shields.io/badge/YouTube-red?style=for-the-badge&logo=youtube&logoColor=white" alt="Youtube Badge"/>
  </a>

  <a href="https://krittiphon-portfolios.netlify.app/">
    <img src="https://img.shields.io/badge/Portfolios Web-brown?style=for-the-badge&logoColor=white" alt="TikTok Badge"/>
  </a>

  <div align="center">
  <img src="https://komarev.com/ghpvc/?username=profiledev&style=flat-square&color=green" alt=""/>
</div>
</div>

<h2>
  Hey there
  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="30px"/>
</h2>

<div align="center">
  <img src="https://media.giphy.com/media/NHvv0Bo3oGq1eTBDd1/giphy.gif" width="600" height="300"/>
</div>


## :woman_technologist: About Me : 
### I am a Full Stack Developer <img src="https://media.giphy.com/media/WUlplcMpOCEmTGBtBW/giphy.gif" width="30"> from Thailand.
specializing in building scalable web and mobile applications using React, Flutter, and FastAPI.

I have hands-on experience developing end-to-end systems, including frontend, backend APIs, database design, and deployment. I have worked with CI/CD pipelines, containerization (Docker/Podman), and cloud platforms such as Vercel and Render.

My recent project includes an AI-powered eCommerce platform with smart sizing analysis, where I designed RESTful APIs, implemented database architecture (PostgreSQL), and deployed production-ready applications.

I also completed an internship as a Full Stack Developer at ClickNext, where I contributed to enterprise internal systems and backend services.

I am passionate about building efficient, scalable systems and continuously improving my skills in modern web technologies.

Open to Full Stack Developer opportunities (New Grad 2026).

---

# 🛍️ ABCat Shop – AI-Powered Full Stack E-commerce

> Full-stack mobile eCommerce platform with AI-based analysis and production-ready deployment.

---

## 🏗️ System Architecture

mermaid
flowchart LR
    
    A[Flutter Mobile App] -->|HTTPS REST API| B[FastAPI Backend]
    B --> C[PostgreSQL Database]
    B --> D[AI Processing Layer]
    B --> E[Auth Service (JWT)]

flowchart TD
    
    U[User Mobile App] --> N[CDN]
    N --> S[Backend Server (Ubuntu)]
    S --> C[Podman Container]
    C --> API[FastAPI Service]
    API --> DB[(PostgreSQL)]

sequenceDiagram
    participant User
    participant App
    participant API
    participant DB

    User->>App: Login Request
    App->>API: POST /login
    API->>DB: Query user
    DB-->>API: Return data
    API-->>App: JWT Token
    App-->>User: Authenticated

## 🔗 API Example
POST /login

    {
      "email": "user@example.com",
      "password": "password123@"
    }

Flow:
Validate input
Query database
Generate JWT Token

    {  
      "access_token": "jwt_token_here",
      "token_type": "bearer"
    }

## 🧠 Tech Decisions

### 📱 Frontend
- Built a mobile application using **Flutter (Dart)**  
- Chosen for cross-platform development, enabling a single codebase for Android/iOS  
- Provides smooth UI performance and rapid development workflow  

---

### ⚙️ Backend
- Developed backend using **Python + FastAPI**  
- Chosen for:
  - High performance and async support  
  - Built-in API documentation (Swagger)  
  - Easy integration with AI/ML logic (Prompt-based processing, detection, analysis)  
- Handles business logic, data processing, and communication with database  

---

### 🗄️ Database
- Used **PostgreSQL**  
- Chosen for:
  - Strong relational structure and data consistency  
  - Scalable design for eCommerce data (users, orders, products)  
  - Efficient querying and future scalability  

---

### 🔗 API Design
- Designed **RESTful APIs** using FastAPI  
- Structured endpoints for clear frontend-backend communication  
- Ensures maintainability and scalability of the system  

---

### 🚀 Deployment
- Containerized application using **Podman (rootless containers)**  
- Chosen for:
  - Enhanced security (no root privileges required)  
  - Lightweight and efficient resource usage  
  - Easy integration with Ubuntu server environment  
- Supports scalable deployment and load balancing  

---

### 🔄 CI/CD Pipeline
- Implemented CI/CD using **Jenkins**  
- Automated build and deployment pipeline  
- Ensures backend service stays active and reduces downtime (prevents sleep state issues)  

---

### ⚡ Performance Optimization
- Optimized API response time for faster backend processing  
- Integrated CDN for faster delivery of static assets  
- Improved overall application responsiveness and user experience  

---
### .env.example
    DATABASE_URL=
    API_KEY=
    SECRET_KEY=

---
# 📊 Impact & Issue Analysis — ABCat Shop (Flutter Web)

---

## 🚀 Impact Analysis

### Home Page — Network Performance

| Metric | Value | Note |
|--------|-------|------|
| Total Requests | **14** | vs 1,378 on Profile page (-99%) |
| Data Transferred | **2.9 MB** | vs 4.4 MB on Profile page (-34%) |
| Page Finish | **~3 s** | All resources loaded |
| Auth Response | **304 ms** | signInWithPassword |

### Request Breakdown

| Type | Count |
|------|-------|
| Auth (Firebase) | 5 req |
| Images (PNG) | 4 req |
| API (Backend) | 3 req |
| Other | 2 req |

### Key API Response Times

| Endpoint | Time |
|----------|------|
| signInWithPassword | 324 ms |
| accounts.lookup | 302 ms |
| home-advertiment | 441 ms |
| token refresh | 310 ms |
| login | 56 ms |

### Image Payload

| File | Size | Status |
|------|------|--------|
| Gemini_Generated_Image 1 | 1,569 kB | ⚠️ Heavy |
| Gemini_Generated_Image 2 | 1,153 kB | ⚠️ Heavy |
| sizeCat.png | 102 kB | ✅ OK |
| **Total** | **~2.8 MB** | 96% of total payload |

### Status Summary

| Check | Result |
|-------|--------|
| HTTP Status | ✅ All 200 OK (14/14) |
| Auth Flow | ✅ Success |
| Backend API (Render) | ✅ Reachable |
| Console Errors | ⚠️ 1 issue found |

### ✅ What's Working Well

- Firebase Auth ดึง UID ได้ถูกต้อง
- POST Favourite → Backend ตอบ 200 ทุกครั้ง
- Request count ต่ำมาก (14 req) โครงสร้างหน้า Home clean
- Auth flow ไม่มี 4xx/5xx เลย

### ⚠️ Improvement Opportunities

- **รูปภาพหนักเกินไป** — Gemini images รวม ~2.7 MB (96% ของ payload)
  - แนะนำ: แปลงเป็น WebP + resize ก่อน upload → ลด load time ได้ ~60-70%
- **Backend บน Render (free tier)** — อาจ cold start ช้า 30-60 วิ หากไม่มีคนใช้งานนาน
- **Profile page** มี 1,378 requests, 147 MB resources — ควรตรวจสอบ asset/script ที่โหลดซ้ำ

---

## 🐛 Issue Analysis

### Summary

| Severity | Count |
|----------|-------|
| 🔴 Errors | 0 |
| 🟠 Warnings | 1 |
| 🔵 Info | 2 |

---

### 🟠 [Warning] Deprecated Feature — `Intl.v8BreakIterator`

**Source:** `dart_sdk.js:238432`

**Description:**  
`Intl.v8BreakIterator` ถูก deprecate ใน Chrome แล้ว มาจาก Dart SDK ที่ใช้ package `intl` เวอร์ชันเก่า

**Impact:** กลาง — Chrome อาจเอาออกในอนาคต ควรแก้ก่อน deploy production

**Fix:**
```bash
flutter upgrade
flutter pub upgrade intl
flutter clean
flutter pub get
```

หรือใน `pubspec.yaml`:
```yaml
intl: ^0.19.0  # หรือเวอร์ชัน stable ล่าสุด
```

---

### 🔵 [Info x4] Form Field Missing `id` or `name` Attribute

**Description:**  
มี input/field 4 จุดที่ไม่มี `id` หรือ `name` — ทำให้ accessibility tools และ form autofill ทำงานได้ไม่เต็มที่

**Impact:** ต่ำ — ไม่กระทบ logic แต่ควรแก้เพื่อ accessibility

**Fix:**
```dart
TextField(
  key: Key('email_field'),
  autofillHints: [AutofillHints.email],
  ...
)
```

---

### 🔵 [Info x1] Session History Item Has Been Marked Skippable

**Description:**  
Browser ทำ navigation entry บางรายการเป็น skippable อัตโนมัติ มักเกิดจาก `pushReplacement` ซ้อนกันหลายชั้น

**Impact:** ต่ำ — ไม่กระทบ user โดยตรง แต่ปุ่ม Back อาจข้ามบางหน้า

**Fix:**
```dart
// แทน pushReplacement ซ้อนกัน ให้ใช้
Navigator.of(context).pushAndRemoveUntil(
  MaterialPageRoute(builder: (context) => HomePage()),
  (route) => false,
);
```

---

## 📋 Action Items

| Priority | Issue | Action |
|----------|-------|--------|
| 🟠 Medium | `Intl.v8BreakIterator` deprecated | `flutter upgrade` + `pub upgrade intl` |
| 🟡 Medium | รูปภาพหนัก (2.7 MB) | แปลงเป็น WebP + resize ก่อน upload |
| 🟢 Low | Form field ไม่มี id/name | เพิ่ม `key` และ `autofillHints` |
| 🟢 Low | Session history skippable | ปรับ navigation ใช้ `pushAndRemoveUntil` |


### Planning Stucture
![Planning Structure](https://res.cloudinary.com/dag73dhpl/image/upload/v1775318744/%E0%B8%9C%E0%B8%B9%E0%B9%89%E0%B8%9E%E0%B8%B1%E0%B8%92%E0%B8%99%E0%B8%B2_2_f0wk5t.png)

---
### :hammer_and_wrench: Tech Stack :

#### Frontend:
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original-wordmark.svg" title="React" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-original.svg" title="HTML5" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/css3/css3-plain-wordmark.svg" title="CSS3" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" title="JavaScript" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/bootstrap/bootstrap-original-wordmark.svg" title="Bootstrap" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/tailwindcss/tailwindcss-original-wordmark.svg" title="TailwindCSS" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/nextjs/nextjs-original.svg" title="Next.js" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/nuxtjs/nuxtjs-original-wordmark.svg" title="Nuxt.js" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/flutter/flutter-original.svg" title="Flutter" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/vuejs/vuejs-original.svg" title="Vue" width="40"/>&nbsp;
</div>

#### Backend:
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/java/java-original-wordmark.svg" title="Java" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/go/go-original-wordmark.svg" title="Go" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/python/python-original-wordmark.svg" title="Python" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/nodejs/nodejs-original-wordmark.svg" title="Node.js" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/fastapi/fastapi-original-wordmark.svg" title="FastAPI" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/c/c-original.svg" title="C" width="40"/>&nbsp;
</div>

#### Database:
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/mysql/mysql-original-wordmark.svg" title="MySQL" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/postgresql/postgresql-original-wordmark.svg" title="PostgreSQL" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/mongodb/mongodb-original-wordmark.svg" title="MongoDB" width="40"/>&nbsp;
</div>

#### DevOps / Tools:
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/jenkins/jenkins-original.svg" title="Jenkins" width="40" />&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/docker/docker-original-wordmark.svg" title="Docker" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-original-wordmark.svg" title="Git" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/postman/postman-original-wordmark.svg" title="Postman" width="40"/>&nbsp;
</div>

#### Dev Tools
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/androidstudio/androidstudio-original.svg" title="Audio Studio" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/apache/apache-original-wordmark.svg" title="Apache" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/figma/figma-original.svg" title="Figma" width="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/npm/npm-original-wordmark.svg" title="NPM" width="40"/>&nbsp;
</div>
</div>

---
