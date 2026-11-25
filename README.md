# 🌐 Web Application Basics | أساسيات تطبيقات الويب

## 🇬🇧 English Documentation

### 📌 Overview

This repository provides comprehensive, structured notes and practical documentation covering **Web Application Basics**. It is designed to build a solid foundation in understanding how web applications operate under the hood, how clients and servers communicate via HTTP, and the core security mechanisms involved in protecting web technologies.

### 🎯 Learning Objectives

By going through this documentation, you will understand:

* What a web application is and how it runs inside a web browser.
* How to dissect **URL** components and how they facilitate access to web resources.
* How **HTTP Requests and Responses** work and their internal structure.
* The different types of **HTTP Request Methods** (e.g., `GET`, `POST`, `PUT`, `DELETE`).
* The meaning and significance of various **HTTP Status Codes** (e.g., `200`, `404`, `500`).
* How **HTTP Headers** and **Security Headers** function and why they are critical for web security.
* How to practically craft and analyze **HTTP Requests**.

### 🗂️ Course Syllabus & Tasks

| Task | Title | Summary |
| :--- | :--- | :--- |
| **Task 1** | **Introduction** | Introductory overview of web application fundamentals and core learning goals. |
| **Task 2** | **Web Application Overview** | Architecture of web applications, frontend vs. backend, and the roles of the Web Browser, Web Server, and WAF. |
| **Task 3** | **Uniform Resource Locator (URL)** | Detailed breakdown of URL structure (`Scheme`, `User`, `Host`, `Port`, `Path`, `Query String`, `Fragment`) and associated security risks like Typosquatting. |
| **Task 4** | **HTTP Messages** | Deep dive into data packets exchanged between client and server (`Requests` & `Responses`) and their four parts (`Start Line`, `Headers`, `Empty Line`, `Body`). |
| **Task 5** | **HTTP Request: Request Line and Methods** | Understanding the HTTP request line structure and exploring common HTTP methods (`GET`, `POST`, `PUT`, `DELETE`, etc.). |
| **Task 6** | **HTTP Request: Headers and Body** | Exploring request headers for metadata transmission and how payloads are structured in the request body. |
| **Task 7** | **HTTP Response: Status Line and Status Codes** | Analyzing the server's response status line and categorizing HTTP status codes (`1xx` to `5xx`). |
| **Task 8** | **HTTP Response: Headers and Body** | Understanding response headers sent by the server and how requested content (HTML, JSON, etc.) is delivered in the body. |
| **Task 9** | **Security Headers** | Implementing and analyzing essential HTTP security headers (`CSP`, `HSTS`, `X-Frame-Options`, `X-Content-Type-Options`) to mitigate web attacks. |
| **Task 10** | **Practical Task: Making HTTP Requests** | Hands-on practice crafting, sending, and inspecting HTTP requests and responses. |
| **Task 11** | **Conclusion** | Final wrap-up and summary of key concepts covered throughout the module. |

### 🛠️ Key Concepts Covered

* **Protocols:** `HTTP` / `HTTPS`
* **Web Architecture:** `Web Browser`, `Web Server`, `Web Application Firewall (WAF)`
* **HTTP Mechanics:** `Request Methods`, `Status Codes`, `Request/Response Headers`, `Payloads`
* **Web Security:** `Security Headers`, `Typosquatting`, `Phishing`, `Input Validation`

---

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

يُقدم هذا المستودع توثيقاً شاملاً ومُنظماً لأساسيات **تطبيقات الويب (Web Application Basics)**. يهدف هذا المحتوى إلى بناء قاعدة معرفية متينة لفهم آلية عمل تطبيقات الويب من الداخل، وكيفية التواصل بين العميل (المتصفح) والخادم (Server) عبر بروتوكول HTTP، بالإضافة إلى آليات الحماية الأساسية لتأمين تقنيات الويب.

### 🎯 أهداف التعلم

من خلال هذا التوثيق، ستتمكن من فهم:

* ماهية تطبيق الويب وكيفية عمله وتشغيله داخل متصفح الويب.
* تحليل مكونات عنوان **URL** بالتفصيل ودور كل جزء في الوصول إلى موارد الويب.
* آلية عمل **طلبات واستجابات HTTP (HTTP Requests & Responses)** وبنيتها الداخلية.
* الأنواع المختلفة لأساليب طلب HTTP (**HTTP Request Methods** مثل `GET`, `POST`, `PUT`, `DELETE`).
* معاني **رموز استجابة HTTP (HTTP Status Codes)** ودلالاتها (مثل `200`, `404`, `500`).
* كيفية عمل **رؤوس HTTP (HTTP Headers)** و**رؤوس الأمان (Security Headers)** وأهميتها القصوى في تأمين الاتصال.
* التطبيق العملي لإنشاء وتحليل **طلبات HTTP**.

### 🗂️ هيكل ومحتوى الكورس

| المهمة | العنوان | الوصف |
| :--- | :--- | :--- |
| **Task 1** | **مقدمة (Introduction)** | نظرة تمهيدية حول أساسيات تطبيقات الويب والأهداف الرئيسية للكورس. |
| **Task 2** | **نظرة عامة على تطبيق الويب (Web Application Overview)** | بنية تطبيقات الويب، الفرق بين الواجهة الأمامية والخلفية، ودور المتصفح وخادم الويب وجدار الحماية (WAF). |
| **Task 3** | **محدد موقع الموارد الموحد (URL)** | تفكيك بنية الرابط (`Scheme`, `User`, `Host`, `Port`, `Path`, `Query String`, `Fragment`) والمخاطر الأمنية مثل انتحال الأحرف (Typosquatting). |
| **Task 4** | **رسائل HTTP (HTTP Messages)** | شرح حزم البيانات المتبادلة بين العميل والخادم (`Requests` & `Responses`) وأجزائها الأربعة (`Start Line`, `Headers`, `Empty Line`, `Body`). |
| **Task 5** | **طلب HTTP: سطر الطلب والأساليب (Request Line & Methods)** | فهم بنية سطر الطلب واستكشاف أساليب طلب HTTP الشائعة (`GET`, `POST`, `PUT`, `DELETE` وغيرها). |
| **Task 6** | **طلب HTTP: الرؤوس والجسم (Headers and Body)** | استكشاف رؤوس الطلب لنقل البيانات الوصفية وكيفية هيكلة البيانات المرسلة في جسم الطلب. |
| **Task 7** | **استجابة HTTP: سطر الحالة ورموز الحالة (Status Line & Codes)** | تحليل سطر حالة الاستجابة من الخادم وتصنيف رموز حالة HTTP من `1xx` إلى `5xx`. |
| **Task 8** | **استجابة HTTP: الرؤوس والجسم (Headers and Body)** | فهم رؤوس الاستجابة المرسلة من الخادم وكيفية تسليم المحتوى المطلوب (HTML, JSON وغيرها) في الجسم. |
| **Task 9** | **رؤوس الأمان (Security Headers)** | تطبيق وتحليل رؤوس أمان HTTP الأساسية (`CSP`, `HSTS`, `X-Frame-Options`, `X-Content-Type-Options`) للحد من هجمات الويب. |
| **Task 10** | **مهمة عملية: إجراء طلبات HTTP (Making HTTP Requests)** | تطبيق عملي لإنشاء وإرسال وفحص طلبات واستجابات HTTP. |
| **Task 11** | **خاتمة (Conclusion)** | ملخص ختامي لأبرز المفاهيم التي تمت تغطيتها خلال الوحدة. |

### 🛠️ المفاهيم الأساسية المغطاة

* **البروتوكولات:** `HTTP` / `HTTPS`
* **البنية التحتية للويب:** `Web Browser`, `Web Server`, `Web Application Firewall (WAF)`
* **آليات HTTP:** `Request Methods`, `Status Codes`, `Request/Response Headers`, `Payloads`
* **أمن الويب:** `Security Headers`, `Typosquatting`, `Phishing`, `Input Validation`
