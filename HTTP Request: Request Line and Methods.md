# 🚀 Task 5: HTTP Request: Request Line and Methods | طلب HTTP: سطر الطلب والأساليب

## 🇬🇧 English Documentation

### 📌 Overview

Every interaction initiated by a client begins with an **HTTP Request**. The very first line of this message—known as the **Request Line**—tells the web server *what action* to perform, *which resource* to target, and *which protocol version* is being used. Understanding HTTP methods is vital for analyzing application logic, mapping APIs, and uncovering access control vulnerabilities.

### 🧩 Anatomy of the Request Line

A standard HTTP Request Line consists of three space-separated elements:

```
GET /profile/settings HTTP/1.1

```

1. **HTTP Method (`GET`):** Defines the desired action to be performed on the target resource.

2. **Request Target / Path (`/profile/settings`):** Specifies the exact endpoint, file, or resource path on the server (optionally including a query string).

3. **HTTP Version (`HTTP/1.1`):** Indicates the version of the HTTP protocol used for formatting the message (commonly `HTTP/1.1` or `HTTP/2`).

### 🛠️ Common HTTP Request Methods

| Method | Purpose | Has Request Body? | Safe & Idempotent? | 
| ----- | ----- | ----- | ----- | 
| **`GET`** | Retrieves data or resources from the server without modifying them (e.g., loading a webpage or searching). | No (parameters sent via URL query string) | Yes (Safe & Idempotent) | 
| **`POST`** | Submits new data to the server for processing (e.g., login forms, uploading files, creating records). | Yes | No | 
| **`PUT`** | Updates or completely replaces an existing resource at a specific URI on the server. | Yes | Idempotent (not Safe) | 
| **`PATCH`** | Applies partial modifications to an existing resource rather than replacing the entire entity. | Yes | No | 
| **`DELETE`** | Removes a specified resource from the server. | Optional | Idempotent (not Safe) | 
| **`HEAD`** | Identical to `GET`, but instructs the server to return **only the headers** without the response body (useful for checking resource existence or size). | No | Yes (Safe & Idempotent) | 
| **`OPTIONS`** | Queries the server for the communication options and HTTP methods supported by a specific endpoint (commonly used in CORS). | No | Yes (Safe & Idempotent) | 

### 🛡️ Security Considerations

* **Sensitive Data in `GET` Requests:** Because `GET` appends parameters directly to the URL, sensitive data (like passwords or API tokens) should **never** be sent via `GET`, as URLs are logged in browser history, proxy servers, and web server access logs.

* **Insecure HTTP Methods:** Dangerous methods like `PUT`, `DELETE`, or `TRACE` should be strictly disabled if not required, as misconfigurations can allow attackers to upload malicious files or delete critical data.

* **HTTP Method Tampering (Verb Tampering):** Security controls configured only for specific methods (e.g., blocking `POST` to an admin endpoint) can sometimes be bypassed by switching the request method to `HEAD`, `GET`, or `PUT`.

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

يبدأ كل تفاعل يُطلقه العميل بـ **طلب HTTP (HTTP Request)**. يُحدّد السطر الأول من هذه الرسالة—والمعروف باسم **سطر الطلب (Request Line)**—*نوع الإجراء* المطلوب تنفيذه، و*المورد* المستهدف، و*إصدار البروتوكول* المستخدم. يُعد فهم أساليب HTTP أمراً حيوياً لتحليل منطق التطبيقات، واستكشاف نقاط النهاية (APIs)، واكتشاف ثغرات التحكم في الوصول.

### 🧩 بنية سطر الطلب (Request Line)

يتكون سطر الطلب القياسي من ثلاثة عناصر مفصولة بمسافات:

```
GET /profile/settings HTTP/1.1

```

1. **أسلوب HTTP (`GET`):** يُحدّد الإجراء المطلوب تنفيذه على المورد المستهدف.

2. **مسار المورد المطلوب (`/profile/settings`):** يُحدّد نقطة النهاية أو الملف أو المسار الدقيق على الخادم (وقد يتضمن سلسلة استعلام).

3. **إصدار HTTP (`HTTP/1.1`):** يُشير إلى إصدار بروتوكول HTTP المستخدم لتنسيق الرسالة (الأكثر شيوعاً `HTTP/1.1` أو `HTTP/2`).

### 🛠️ أشهر أساليب طلب HTTP (HTTP Methods)

| الأسلوب | الوظيفة والغرض | يحتوي على جسم (Body)؟ | آمن ومتكرر النتيجة (Idempotent)؟ | 
| ----- | ----- | ----- | ----- | 
| **`GET`** | جلب البيانات أو الموارد من الخادم دون تعديلها (مثل فتح صفحة ويب أو إجراء بحث). | لا (تُمرر البيانات عبر الرابط) | نعم (آمن ومتكرر النتيجة) | 
| **`POST`** | إرسال بيانات جديدة إلى الخادم لمعالجتها (مثل نماذج تسجيل الدخول، رفع الملفات، إنشاء حساب). | نعم | لا | 
| **`PUT`** | تحديث أو استبدال مورد موجود بالكامل في مسار محدد على الخادم. | نعم | متكرر النتيجة (غير آمن) | 
| **`PATCH`** | إجراء تعديلات جزئية على مورد موجود بدلاً من استبداله بالكامل. | نعم | لا | 
| **`DELETE`** | حذف مورد محدد من الخادم. | اختياري | متكرر النتيجة (غير آمن) | 
| **`HEAD`** | مطابق لأسلوب `GET`، لكنه يطلب من الخادم إعادة **الرؤوس فقط** دون جسم الاستجابة (مفيد للتحقق من وجود الملف أو حجمه). | لا | نعم (آمن ومتكرر النتيجة) | 
| **`OPTIONS`** | الاستعلام من الخادم عن خيارات الاتصال وأساليب HTTP المدعومة لنقطة نهاية معينة (يُستخدم بكثرة في CORS). | لا | نعم (آمن ومتكرر النتيجة) | 

### 🛡️ الاعتبارات الأمنية

* **تجنب إرسال البيانات الحساسة عبر `GET`:** نظراً لأن `GET` يُرفق المعاملات مباشرة في عنوان URL، يجب **عدم** إرسال كلمات المرور أو الرموز السرية عبره أبداً، لأن الروابط تُحفظ في سجل المتصفح وسجلات الخادم.

* **تعطيل الأساليب غير الضرورية:** يجب تعطيل الأساليب الحساسة مثل `PUT` و`DELETE` و`TRACE` إذا لم تكن مطلوبة، لأن سوء إعدادها قد يسمح للمهاجمين برفع ملفات خبيثة أو حذف بيانات مهمة.

* **التلاعب بأساليب الطلب (HTTP Verb Tampering):** قد يتمكن المهاجمون أحياناً من تجاوز قيود الحماية المفروضة على أسلوب معين (مثل حظر `POST`) عن طريق تغيير الأسلوب في سطر الطلب إلى `HEAD` أو `GET` أو `PUT`.
