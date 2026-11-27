# 🛡️ Task 9: Security Headers | رؤوس الأمان

## 🇬🇧 English Documentation

### 📌 Overview

**HTTP Security Headers** are specialized response headers sent by a web server to instruct the client's web browser on how to behave when handling site content. Acting as a critical defense-in-depth layer, these headers mitigate common client-side vulnerabilities—such as **Cross-Site Scripting (XSS)**, **Clickjacking**, **Man-in-the-Middle (MitM)** protocol downgrades, and **MIME-type sniffing**—without requiring changes to the underlying application logic.

### 🔐 Essential HTTP Security Headers

| Security Header | Purpose & Protection Mechanism | Recommended Configuration Example |
| :--- | :--- | :--- |
| **`Content-Security-Policy` (`CSP`)** | Controls which trusted sources (domains) the browser is allowed to load executable resources from (scripts, styles, images, frames). Serves as the primary browser-level defense against **XSS** and data injection attacks. | `Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted.cdn.com` |
| **`Strict-Transport-Security` (`HSTS`)** | Forces the browser to communicate with the web server exclusively over encrypted **HTTPS** for a specified duration (`max-age`), blocking HTTP downgrade attacks and certificate warnings bypass. | `Strict-Transport-Security: max-age=31536000; includeSubDomains; preload` |
| **`X-Frame-Options`** | Dictates whether the webpage is permitted to be embedded inside `<frame>`, `<iframe>`, `<embed>`, or `<object>` tags on external sites, preventing **Clickjacking** (UI redressing) attacks. | `X-Frame-Options: DENY` or `X-Frame-Options: SAMEORIGIN` |
| **`X-Content-Type-Options`** | Prevents the browser from performing **MIME-type sniffing** (guessing a file's content type instead of strictly obeying the declared `Content-Type` header), mitigating script execution via disguised uploads. | `X-Content-Type-Options: nosniff` |
| **`Referrer-Policy`** | Controls how much referrer URL information is shared in the `Referer` header when navigating away from the site, protecting sensitive tokens or paths in URLs from leaking to third parties. | `Referrer-Policy: strict-origin-when-cross-origin` |
| **`Permissions-Policy`** | Restricts which browser features and hardware APIs (such as camera, microphone, geolocation, or payment APIs) the webpage and embedded iframes are permitted to access. | `Permissions-Policy: geolocation=(), camera=(), microphone=()` |

### 💻 Example Secure HTTP Response

```http
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
Content-Security-Policy: default-src 'self'
X-Frame-Options: DENY
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: camera=(), microphone=(), geolocation=()
```

### 🛡️ Security Considerations & Best Practices

* **Defense-in-Depth, Not a Silver Bullet:** Security headers like `CSP` significantly reduce the impact of vulnerabilities, but they do not replace proper server-side input validation and output encoding.
* **Avoid Unsafe CSP Directives:** Using `'unsafe-inline'` or `'unsafe-eval'` inside `script-src` severely weakens `Content-Security-Policy` and allows attackers to execute injected JavaScript payloads.
* **Header Auditing Tools:** Security analysts routinely inspect HTTP responses using browser DevTools, `curl -I`, or automated scanners to identify missing security headers during web application assessments.

---

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

**رؤوس أمان HTTP (HTTP Security Headers)** هي رؤوس استجابة متخصصة يُرسلها خادم الويب لتوجيه متصفح العميل حول كيفية التعامل الآمن مع محتوى الموقع. وتُشكّل هذه الرؤوس طبقة دفاع إضافية بالغة الأهمية للحد من الثغرات الشائعة من جانب العميل—مثل **البرمجة عبر المواقع (XSS)**، و**اختطاف النقرات (Clickjacking)**، وهجمات **الوسيط (MitM)** لخفض مستوى التشفير، و**استنتاج نوع الملفات (MIME Sniffing)**—دون الحاجة لتعديل الكود البرمجي الأساسي للتطبيق.

### 🔐 أبرز رؤوس أمان HTTP الأساسية

| رأس الأمان (Header) | الوظيفة وآلية الحماية | مثال على الإعداد الموصى به |
| :--- | :--- | :--- |
| **`Content-Security-Policy` (`CSP`)** | يُحدّد المصادر الموثوقة (النطاقات) التي يُسمح للمتصفح بتحميل الموارد التنفيذية منها (مثل ملفات JavaScript والتنسيقات والصور). يُعد خط الدفاع الأول على مستوى المتصفح ضد هجمات **XSS** وحقن البيانات. | `Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted.cdn.com` |
| **`Strict-Transport-Security` (`HSTS`)** | يُجبر المتصفح على التواصل مع خادم الويب حصرياً عبر اتصال **HTTPS** مشفر لفترة زمنية محددة (`max-age`)، مما يمنع هجمات الرجوع إلى بروتوكول HTTP غير المشفر. | `Strict-Transport-Security: max-age=31536000; includeSubDomains; preload` |
| **`X-Frame-Options`** | يُحدّد ما إذا كان يُسمح بتضمين صفحة الويب داخل إطارات (`<iframe>` أو `<frame>`) في مواقع خارجية، مما يحمي المستخدمين من هجمات **اختطاف النقرات (Clickjacking)**. | `X-Frame-Options: DENY` أو `X-Frame-Options: SAMEORIGIN` |
| **`X-Content-Type-Options`** | يمنع المتصفح من تخمين نوع الملف (**MIME-type sniffing**) ويُلزمه بالالتزام الصارم بنوع المحتوى المُعلن في رأس `Content-Type`، مما يمنع تنفيذ ملفات مرفوعة كأكواد برمجية. | `X-Content-Type-Options: nosniff` |
| **`Referrer-Policy`** | يتحكم في مقدار معلومات رابط الصفحة السابقة المُرسلة في رأس `Referer` عند الانتقال إلى مواقع أخرى، لحماية البيانات الحساسة الموجودة في الروابط من التسرب. | `Referrer-Policy: strict-origin-when-cross-origin` |
| **`Permissions-Policy`** | يُقيّد صلاحيات وصول صفحة الويب والإطارات المضمنة إلى ميزات المتصفح وأجهزة المستخدم (مثل الكاميرا، الميكروفون، وتحديد الموقع الجغرافي). | `Permissions-Policy: geolocation=(), camera=(), microphone=()` |

### 💻 مثال على استجابة HTTP محصّنة برؤوس الأمان

```http
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
Content-Security-Policy: default-src 'self'
X-Frame-Options: DENY
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: camera=(), microphone=(), geolocation=()
```

### 🛡️ الاعتبارات الأمنية وأفضل الممارسات

* **طبقة دفاع إضافية وليست بديلاً عن تأمين الكود:** رؤوس الأمان مثل `CSP` تُقلل بشكل كبير من خطورة الثغرات، لكنها لا تُغني عن التحقق الصارم من المدخلات وتشفير المخرجات على الخادم.
* **تجنب التوجيهات غير الآمنة في CSP:** استخدام قيم مثل `'unsafe-inline'` أو `'unsafe-eval'` داخل `script-src` يُضعف حماية سياسة أمان المحتوى ويسمح للمهاجمين بتنفيذ أكواد JavaScript خبيثة.
* **فحص رؤوس الأمان:** يعتمد محللو الأمن السيبراني على أدوات المطور في المتصفح أو أمر `curl -I` لفحص استجابات الخادم واكتشاف رؤوس الأمان المفقودة أثناء تقييم تطبيقات الويب.
