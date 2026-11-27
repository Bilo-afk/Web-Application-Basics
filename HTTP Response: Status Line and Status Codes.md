# 📡 Task 7: HTTP Response: Status Line and Status Codes | استجابة HTTP: سطر الحالة ورموز الحالة

## 🇬🇧 English Documentation

### 📌 Overview

Once a web server receives and processes an HTTP request, it replies with an **HTTP Response**. The very first line of this response—known as the **Status Line**—immediately informs the client whether the request succeeded, redirected, failed due to a client error, or encountered a server-side issue. Mastering **HTTP Status Codes** is essential for troubleshooting web applications, enumerating endpoints, and analyzing server behavior during security assessments.

### 🧩 Anatomy of the Status Line

A standard HTTP Response Status Line consists of three space-separated elements:

```
HTTP/1.1 200 OK
```

1. **HTTP Version (`HTTP/1.1`):** Specifies the protocol version used by the server to format the response.
2. **Status Code (`200`):** A three-digit integer indicating the exact outcome of the request.
3. **Reason Phrase / Status Text (`OK`):** A brief, human-readable text description explaining the status code.

### 📊 HTTP Status Code Categories

HTTP status codes are grouped into five distinct classes based on their first digit:

| Category | Range | Meaning |
| :--- | :--- | :--- |
| **Informational** | `100 – 199` | The request was received, and the server is continuing the process. |
| **Success** | `200 – 299` | The request was successfully received, understood, and accepted. |
| **Redirection** | `300 – 399` | Further action (typically following a new URL) is required by the client to complete the request. |
| **Client Error** | `400 – 499` | The request contains invalid syntax, lacks authentication, or targets a restricted/non-existent resource. |
| **Server Error** | `500 – 599` | The server failed to fulfill an apparently valid request due to an internal error or misconfiguration. |

### 🔢 Essential HTTP Status Codes

| Code | Status Text | Category | Description |
| :--- | :--- | :--- | :--- |
| **`100`** | `Continue` | Informational | Indicates that the initial part of a request has been received and the client should proceed with sending the rest. |
| **`200`** | `OK` | Success | The standard response for successful HTTP requests (e.g., a webpage loaded or API data returned). |
| **`201`** | `Created` | Success | The request succeeded, and a new resource was created on the server (commonly returned after a `POST` request). |
| **`204`** | `No Content` | Success | The server successfully processed the request, but there is no content to return in the response body. |
| **`301`** | `Moved Permanently` | Redirection | The requested resource has been permanently assigned a new URI; future requests should use the new URL. |
| **`302`** | `Found` | Redirection | Temporarily redirects the client to a different URL (frequently used after login submissions). |
| **`400`** | `Bad Request` | Client Error | The server cannot process the request due to malformed syntax or invalid parameters. |
| **`401`** | `Unauthorized` | Client Error | Authentication is required and has either failed or not yet been provided. |
| **`403`** | `Forbidden` | Client Error | The server understood the request, but refuses to authorize it (the client lacks permission even if authenticated). |
| **`404`** | `Not Found` | Client Error | The requested resource or endpoint does not exist on the server. |
| **`405`** | `Method Not Allowed` | Client Error | The HTTP method used (e.g., `DELETE`) is not supported or permitted for the target resource. |
| **`500`** | `Internal Server Error` | Server Error | A generic error indicating an unexpected condition or crash occurred inside the server's backend code. |
| **`502`** | `Bad Gateway` | Server Error | A server acting as a gateway or proxy received an invalid response from an upstream server. |
| **`503`** | `Service Unavailable` | Server Error | The server is temporarily unable to handle the request due to maintenance or overload. |

### 🛡️ Security Considerations

* **Directory & Endpoint Enumeration:** Differences between `200`, `403`, and `404` responses allow penetration testers and attackers to map hidden files, admin panels, and restricted directories.
* **Information Leakage in `500` Errors:** Poorly configured error handling may cause `500 Internal Server Error` responses to expose verbose stack traces, database queries, or framework versions.
* **Open Redirect Vulnerabilities:** Unvalidated `301`/`302` redirection parameters can be abused by attackers to redirect victims from a trusted domain to a malicious phishing site.

---

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

بمجرد أن يستقبل خادم الويب طلب HTTP ويُعالجه، فإنه يرد بـ **استجابة HTTP (HTTP Response)**. يُخبر السطر الأول من هذه الاستجابة—والمعروف باسم **سطر الحالة (Status Line)**—العميل فوراً ما إذا كان الطلب قد نجح، أو تم توجيهه إلى رابط آخر، أو فشل بسبب خطأ من العميل، أو واجه مشكلة داخل الخادم. يُعد إتقان **رموز حالة HTTP** أمراً أساسياً لتشخيص أعطال التطبيقات، واستكشاف المسارات المخفية، وتحليل سلوك الخادم أثناء الفحص الأمني.

### 🧩 بنية سطر الحالة (Status Line)

يتكون سطر الحالة القياسي في استجابة HTTP من ثلاثة عناصر مفصولة بمسافات:

```
HTTP/1.1 200 OK
```

1. **إصدار HTTP (`HTTP/1.1`):** يُحدّد إصدار البروتوكول الذي استخدمه الخادم لتنسيق الاستجابة.
2. **رمز الحالة (`200`):** رقم مكون من ثلاث خانات يُشير إلى النتيجة الدقيقة لمعالجة الطلب.
3. **نص الحالة (`OK`):** وصف نصي موجز ومقروء يُوضح معنى رمز الحالة.

### 📊 تصنيفات رموز حالة HTTP

تُقسّم رموز حالة HTTP إلى خمس فئات رئيسية بناءً على الرقم الأول منها:

| الفئة | النطاق | المعنى والدلالة |
| :--- | :--- | :--- |
| **معلوماتية (Informational)** | `100 – 199` | تم استلام الطلب، والخادم مستمر في معالجة العملية. |
| **نجاح (Success)** | `200 – 299` | تم استلام الطلب وفهمه وقبوله ومعالجته بنجاح. |
| **إعادة توجيه (Redirection)** | `300 – 399` | يتطلب الأمر اتخاذ إجراء إضافي من العميل (غالباً الانتقال إلى رابط URL جديد) لإكمال الطلب. |
| **خطأ من العميل (Client Error)** | `400 – 499` | يحتوي الطلب على صيغة خاطئة، أو يفتقر للمصادقة، أو يطلب مورداً محظوراً أو غير موجود. |
| **خطأ من الخادم (Server Error)** | `500 – 599` | فشل الخادم في تنفيذ طلب يبدو صحيحاً بسبب خطأ برمجي داخلي أو سوء إعداد. |

### 🔢 أبرز رموز حالة HTTP الشائعة

| الرمز | نص الحالة | الفئة | الوصف |
| :--- | :--- | :--- | :--- |
| **`100`** | `Continue` | معلوماتية | يُشير إلى استلام الجزء الأولي من الطلب وأن على العميل الاستمرار في إرسال الباقي. |
| **`200`** | `OK` | نجاح | الاستجابة القياسية لنجاح طلب HTTP (مثل تحميل صفحة ويب بنجاح أو إرجاع بيانات API). |
| **`201`** | `Created` | نجاح | نجح الطلب وتم إنشاء مورد جديد على الخادم (يظهر غالباً بعد طلب `POST`). |
| **`204`** | `No Content` | نجاح | عالج الخادم الطلب بنجاح، ولكن لا يوجد محتوى لإرجاعه في جسم الاستجابة. |
| **`301`** | `Moved Permanently` | إعادة توجيه | تم نقل المورد المطلوب بشكل دائم إلى عنوان URL جديد؛ ويجب استخدام العنوان الجديد مستقبلاً. |
| **`302`** | `Found` | إعادة توجيه | إعادة توجيه مؤقتة للعميل إلى رابط مختلف (تُستخدم بكثرة بعد عمليات تسجيل الدخول). |
| **`400`** | `Bad Request` | خطأ من العميل | لا يستطيع الخادم معالجة الطلب بسبب خطأ في صياغته أو معاملات غير صالحة. |
| **`401`** | `Unauthorized` | خطأ من العميل | الوصول يتطلب مصادقة (تسجيل دخول)، وقد فشلت المصادقة أو لم يتم تقديمها بعد. |
| **`403`** | `Forbidden` | خطأ من العميل | فهم الخادم الطلب لكنه يرفض تنفيذه لعدم امتلاك العميل الصلاحية الكافية حتى مع تسجيل الدخول. |
| **`404`** | `Not Found` | خطأ من العميل | المورد أو الصفحة أو نقطة النهاية المطلوبة غير موجودة على الخادم. |
| **`405`** | `Method Not Allowed` | خطأ من العميل | أسلوب HTTP المستخدم (مثل `DELETE`) غير مدعوم أو غير مسموح به لهذا المورد. |
| **`500`** | `Internal Server Error` | خطأ من الخادم | خطأ عام يُشير إلى حدوث مشكلة غير متوقعة أو تعطل في الكود البرمجي داخل الخادم. |
| **`502`** | `Bad Gateway` | خطأ من الخادم | الخادم الذي يعمل كبوابة أو وسيط (Proxy) تلقى استجابة غير صالحة من خادم خلفي آخر. |
| **`503`** | `Service Unavailable` | خطأ من الخادم | الخادم غير قادر مؤقتاً على معالجة الطلب بسبب الصيانة أو الضغط الزائد. |

### 🛡️ الاعتبارات الأمنية

* **استكشاف المسارات والمجلدات (Enumeration):** تُساعد الفروقات بين استجابات `200` و`403` و`404` مختبري الاختراق والمهاجمين على اكتشاف الملفات المخفية ولوحات التحكم والمجلدات المقيدة.
* **تسريب المعلومات في أخطاء `500`:** قد يؤدي ضعف معالجة الأخطاء إلى عرض تفاصيل حساسة في استجابات `500 Internal Server Error` مثل تتبع الأخطاء البرمجية (Stack Traces) أو استعلامات قواعد البيانات وإصدارات الخادم.
* **ثغرات إعادة التوجيه المفتوحة (Open Redirect):** يمكن استغلال معاملات إعادة التوجيه غير المفحوصة (`301`/`302`) لتوجيه الضحايا من نطاق موثوق إلى موقع تصيد احتيالي خبيث.
