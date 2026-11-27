# 📨 Task 4: HTTP Messages | رسائل HTTP

## 🇬🇧 English Documentation

### 📌 Overview

**HTTP Messages** are structured packets of data exchanged between a client (user/browser) and a web server. Understanding how these messages are formatted and transmitted is fundamental to analyzing web application behavior, troubleshooting communication failures, and securing data in transit.

### 🔄 Types of HTTP Messages

1. **HTTP Requests:** Messages sent by the client to the web server to initiate an action, retrieve a resource, or submit data.
2. **HTTP Responses:** Messages returned by the web server to the client after processing a request, indicating the outcome and delivering the requested resource.

### 🧩 Structure of an HTTP Message

Every HTTP message—whether a request or a response—follows a strict four-part layout:

| Part | Description |
| :--- | :--- |
| **1. Start Line** | Introduces the message type. In a **Request**, it specifies the HTTP method, target path, and HTTP version. In a **Response**, it specifies the HTTP version and status code. |
| **2. Headers** | Key-value pairs (`Key: Value`) that provide metadata and instructions regarding content types, payload length, caching, authentication, and security policies. |
| **3. Empty Line** | A mandatory blank line (`CRLF`) separating the headers from the body. Without this divider, the client or server cannot distinguish metadata from actual payload data, causing parsing errors. |
| **4. Body** | Contains the actual data payload being transmitted—such as form credentials or JSON data in a request, or HTML pages and API responses from the server. |

### 💻 Practical Examples

#### HTTP Request Example
```http
POST /login HTTP/1.1
Host: tryhackme.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 43

username=aleksandra&password=securepassword
```

#### HTTP Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 56
Date: Wed, 29 Aug 2024 12:00:00 GMT

{
  "message": "Login successful!",
  "status": "success"
}
```

### 🛡️ Why Understanding HTTP Messages Matters

* **Core Communication:** Forms the foundation of how clients and web servers interact reliably.
* **Diagnostics & Debugging:** Enables developers and analysts to inspect traffic, pinpoint broken endpoints, and optimize performance.
* **Security Analysis:** Essential for detecting malformed requests, injection payloads, header manipulation, and ensuring sensitive data is protected during transmission.

---

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

**رسائل HTTP (HTTP Messages)** هي حزم بيانات منظمة يتم تبادلها بين العميل (المستخدم/المتصفح) وخادم الويب. يُعد فهم بنية هذه الرسائل وآلية إرسالها أمراً أساسياً لتحليل سلوك تطبيقات الويب، وتشخيص أعطال الاتصال، وتأمين البيانات أثناء النقل.

### 🔄 أنواع رسائل HTTP

1. **طلبات HTTP (HTTP Requests):** رسائل يُرسلها العميل إلى خادم الويب لبدء إجراء معين، أو طلب مورد، أو إرسال بيانات.
2. **استجابات HTTP (HTTP Responses):** رسائل يُعيدها خادم الويب إلى العميل بعد معالجة الطلب، وتُوضح نتيجة العملية وتُسلّم المحتوى المطلوب.

### 🧩 بنية رسالة HTTP

تتبع كل رسالة HTTP—سواء كانت طلباً أو استجابة—هيكلاً دقيقاً يتكون من أربعة أجزاء رئيسية:

| الجزء | الوصف |
| :--- | :--- |
| **1. سطر البداية (Start Line)** | يُحدد نوع الرسالة وتفاصيلها الأساسية؛ ففي **الطلب** يتضمن أسلوب الطلب والمسار وإصدار HTTP، وفي **الاستجابة** يتضمن إصدار HTTP ورمز الحالة. |
| **2. العناوين / الرؤوس (Headers)** | أزواج من المفاتيح والقيم (`Key: Value`) توفر معلومات وصفية وتعليمات إضافية حول نوع المحتوى، وحجمه، والتخزين المؤقت، والمصادقة، وسياسات الأمان. |
| **3. السطر الفارغ (Empty Line)** | فاصل إجباري يفصل بين الرؤوس وجسم الرسالة؛ وبدونه لا يستطيع الخادم أو العميل التمييز بين البيانات الوصفية والمحتوى الفعلي، مما يؤدي إلى أخطاء في المعالجة. |
| **4. الجسم / المحتوى (Body)** | يحتوي على البيانات الفعلية المنقولة—مثل بيانات تسجيل الدخول أو النماذج في الطلب، أو صفحات الويب وبيانات الـ API في الاستجابة. |

### 💻 أمثلة عملية

#### مثال على طلب HTTP (HTTP Request)
```http
POST /login HTTP/1.1
Host: tryhackme.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 43

username=aleksandra&password=securepassword
```

#### مثال على استجابة HTTP (HTTP Response)
```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 56
Date: Wed, 29 Aug 2024 12:00:00 GMT

{
  "message": "Login successful!",
  "status": "success"
}
```

### 🛡️ أهمية فهم رسائل HTTP

* **أساس التواصل:** تُشكّل الركيزة الأساسية لتفاعل العملاء وخوادم الويب بسلاسة.
* **التشخيص وحل المشكلات:** تُساعد المطورين والمحللين على فحص حركة البيانات، واكتشاف نقاط الخلل، وتحسين الأداء.
* **التحليل الأمني:** ضرورية لاكتشاف الطلبات المشوهة، وهجمات الحقن داخل جسم الرسالة، والتلاعب بالرؤوس، وضمان حماية البيانات الحساسة أثناء النقل.
