# 📦 Task 6: HTTP Request: Headers and Body | طلب HTTP: الرؤوس والجسم

## 🇬🇧 English Documentation

### 📌 Overview

Beyond the initial Request Line, an **HTTP Request** carries crucial metadata inside its **Headers** and—when applicable—transmits actual payload data inside its **Body**. Mastering how headers and request bodies work is essential for analyzing API communications, managing authentication sessions, and detecting injection or header manipulation attacks.

### 🏷️ HTTP Request Headers

**Request Headers** are case-insensitive `Key: Value` pairs sent immediately after the Request Line. They give the web server context about the client, the expected response format, authentication credentials, and payload specifications.

#### Common Request Headers

| Header | Purpose & Example |
| :--- | :--- |
| **`Host`** | Specifies the domain name (and optional port) of the target web server. Mandatory in `HTTP/1.1` (e.g., `Host: tryhackme.com`). |
| **`User-Agent`** | Identifies the client software, browser type, and operating system making the request (e.g., `User-Agent: Mozilla/5.0...`). |
| **`Cookie`** | Sends stored session identifiers or tracking tokens back to the server to maintain authenticated user state (e.g., `Cookie: session_id=xyz123`). |
| **`Authorization`** | Carries authentication credentials or tokens (such as Bearer JWTs or Basic auth) to access protected resources (e.g., `Authorization: Bearer <token>`). |
| **`Content-Type`** | Indicates the media format (MIME type) of the data inside the request body so the server knows how to parse it (e.g., `application/json`). |
| **`Content-Length`** | Specifies the exact size of the request body in bytes, ensuring the server reads the complete payload accurately. |
| **`Accept`** | Informs the server which content formats the client can process (e.g., `Accept: text/html, application/json`). |
| **`Referer`** | Indicates the URL of the previous webpage from which the request originated. |

### 📄 HTTP Request Body

Separated from the headers by a mandatory **Empty Line**, the **Request Body** contains the actual data payload sent to the server (primarily used with `POST`, `PUT`, and `PATCH` requests).

#### Common Payload Formats

1. **URL-Encoded Form Data (`application/x-www-form-urlencoded`):**
   Used by standard HTML forms; encodes key-value pairs separated by `&`.
   ```http
   POST /login HTTP/1.1
   Host: tryhackme.com
   Content-Type: application/x-www-form-urlencoded
   Content-Length: 31

   username=admin&password=secret1
   ```

2. **JSON Data (`application/json`):**
   Widely used in modern web applications and REST APIs for structured data exchange.
   ```http
   POST /api/v1/users HTTP/1.1
   Host: tryhackme.com
   Content-Type: application/json
   Content-Length: 48

   {
     "username": "admin",
     "role": "analyst"
   }
   ```

3. **Multipart Form Data (`multipart/form-data`):**
   Used when uploading binary files (such as images or documents) alongside standard text fields, separating each part with a unique boundary string.

### 🛡️ Security Considerations

* **Header Spoofing & Manipulation:** Headers like `User-Agent`, `Referer`, and `X-Forwarded-For` are entirely client-controlled and must never be trusted for security or access control decisions without validation.
* **Session Hijacking via Cookies:** If `Cookie` headers are transmitted over unencrypted HTTP or lack protective flags (`HttpOnly`, `Secure`), attackers can steal session tokens to impersonate legitimate users.
* **Payload Injection:** Unsanitized data inside the **Request Body** (whether JSON, XML, or form fields) is a primary vector for **SQL Injection (SQLi)**, **Command Injection**, and **Server-Side Request Forgery (SSRF)**.

---

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

بعد سطر الطلب الأول، يحمل **طلب HTTP** معلومات وصفية بالغة الأهمية داخل **الرؤوس (Headers)**، وعند الحاجة ينقل البيانات الفعلية داخل **الجسم (Body)**. يُعد إتقان آلية عمل الرؤوس وجسم الطلب أمراً أساسياً لتحليل اتصالات واجهات البرمجة (APIs)، وإدارة جلسات المصادقة، واكتشاف هجمات الحقن والتلاعب بالرؤوس.

### 🏷️ رؤوس طلب HTTP (Request Headers)

**رؤوس الطلب** هي أزواج من المفاتيح والقيم (`Key: Value`) تُرسل مباشرة بعد سطر الطلب. تُزوّد هذه الرؤوس خادم الويب بسياق كامل حول العميل، وصيغة الاستجابة المتوقعة، وبيانات المصادقة، ومواصفات البيانات المرسلة.

#### أشهر رؤوس الطلب

| الرأس (Header) | الوظيفة والمثال |
| :--- | :--- |
| **`Host`** | يُحدّد اسم النطاق (والمنفذ اختيارياً) للخادم المستهدف. يُعد إلزامياً في `HTTP/1.1` (مثل: `Host: tryhackme.com`). |
| **`User-Agent`** | يُعرّف ببرنامج العميل ونوع المتصفح ونظام التشغيل الذي أرسل الطلب (مثل: `User-Agent: Mozilla/5.0...`). |
| **`Cookie`** | يُرسل مُعرّفات الجلسة المخزنة إلى الخادم للحفاظ على حالة تسجيل دخول المستخدم (مثل: `Cookie: session_id=xyz123`). |
| **`Authorization`** | يحمل بيانات الاعتماد أو رموز المصادقة (مثل رموز `Bearer JWT`) للوصول إلى الموارد المحمية. |
| **`Content-Type`** | يُحدّد نوع وصيغة البيانات داخل جسم الطلب لكي يتمكن الخادم من قراءتها بشكل صحيح (مثل: `application/json`). |
| **`Content-Length`** | يُحدّد الحجم الدقيق لجسم الطلب بالبايت، لضمان قراءة الخادم للبيانات كاملة بدقة. |
| **`Accept`** | يُخبر الخادم بصيغ المحتوى التي يستطيع العميل استقبالها ومعالجتها (مثل: `Accept: text/html, application/json`). |
| **`Referer`** | يُشير إلى عنوان الصفحة السابقة التي انتقل منها المستخدم لإرسال هذا الطلب. |

### 📄 جسم طلب HTTP (Request Body)

يُفصل **جسم الطلب** عن الرؤوس بـ **سطر فارغ (Empty Line)** إجباري، ويحتوي على البيانات الفعلية المرسلة إلى الخادم (ويُستخدم بشكل رئيسي مع أساليب `POST` و`PUT` و`PATCH`).

#### أشهر صيغ البيانات في جسم الطلب

1. **بيانات النماذج المشفرة بالرابط (`application/x-www-form-urlencoded`):**
   تُستخدم في نماذج HTML التقليدية؛ حيث تُرسل البيانات كأزواج مفصولة بعلامة `&`.
   ```http
   POST /login HTTP/1.1
   Host: tryhackme.com
   Content-Type: application/x-www-form-urlencoded
   Content-Length: 31

   username=admin&password=secret1
   ```

2. **بيانات JSON (`application/json`):**
   تُستخدم بكثرة في تطبيقات الويب الحديثة وواجهات REST APIs لتبادل البيانات المنظمة.
   ```http
   POST /api/v1/users HTTP/1.1
   Host: tryhackme.com
   Content-Type: application/json
   Content-Length: 48

   {
     "username": "admin",
     "role": "analyst"
   }
   ```

3. **بيانات النماذج متعددة الأجزاء (`multipart/form-data`):**
   تُستخدم عند رفع الملفات (مثل الصور أو المستندات) مع حقول نصية في نفس الطلب، حيث يُفصل كل جزء بفاصل نصي فريد (Boundary).

### 🛡️ الاعتبارات الأمنية

* **تزييف الرؤوس والتلاعب بها:** رؤوس مثل `User-Agent` و`Referer` و`X-Forwarded-For` تخضع لسيطرة العميل بالكامل، ويجب عدم الوثوق بها في قرارات الأمان أو التحقق من الصلاحيات دون فحص.
* **اختطاف الجلسات عبر ملفات تعريف الارتباط:** إذا أُرسل رأس `Cookie` عبر اتصال HTTP غير مشفر أو بدون خصائص الحماية (`HttpOnly` و`Secure`)، يمكن للمهاجمين سرقة رمز الجلسة وانتحال شخصية المستخدم.
* **الحقن عبر جسم الطلب:** تُعد البيانات غير المفحوصة داخل **جسم الطلب** (سواء كانت JSON أو حقول نماذج) مساراً رئيسياً لهجمات **حقن قواعد البيانات (SQLi)** و**حقن الأوامر (Command Injection)**.
