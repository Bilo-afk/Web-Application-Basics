# 🔗 Task 3: Uniform Resource Locator (URL) | محدد موقع الموارد الموحد

## 🇬🇧 English Documentation

### 📌 Overview

A **Uniform Resource Locator (URL)** is a standardized web address that enables users and web browsers to locate and access various types of resources across the internet—such as webpages, videos, images, APIs, and documents. Understanding the exact anatomy of a URL is critical for web navigation, application debugging, and identifying web-based security threats.

### 🧩 Anatomy of a URL

Consider the following complete URL structure:

```text
http://user:password@tryhackme.com:80/view-room?id=1#task3
```

| Component | Example | Description & Security Considerations |
| :--- | :--- | :--- |
| **Scheme** | `http` | Specifies the communication protocol used to access the resource (`HTTP` or `HTTPS`). **HTTPS** is strongly recommended because it encrypts traffic in transit, preventing eavesdropping and tampering. |
| **User** | `user:password` | Optional authentication credentials embedded directly in the URL. This practice is deprecated and insecure because credentials can be exposed in browser histories, server logs, and network traffic. |
| **Host / Domain** | `tryhackme.com` | Identifies the target web server or registered domain name. Attackers often register lookalike domains with slight misspellings—a technique known as **Typosquatting**—to launch **Phishing** attacks. |
| **Port** | `80` | Specifies the network gate/service on the web server (ranging from `1` to `65535`). Standard default ports are `80` for `HTTP` and `443` for `HTTPS`. |
| **Path** | `/view-room` | Points to the specific file, directory, or endpoint on the server. Web applications must enforce strict access controls on paths to prevent unauthorized access to sensitive resources. |
| **Query String** | `?id=1` | Begins with a question mark (`?`) and passes key-value parameters (such as search terms or form inputs) to the server. Because users can freely modify query parameters, improper sanitization can lead to injection attacks (e.g., **SQLi**, **XSS**). |
| **Fragment** | `#task3` | Begins with a hash symbol (`#`) and directs the browser to a specific section or anchor within the loaded webpage. Handled primarily on the client side, though insecure JavaScript handling can expose **DOM-based XSS** vulnerabilities. |

### 🛡️ Key Security Takeaways

* **Enforce HTTPS:** Always prioritize encrypted connections (`HTTPS` over port `443`) to protect data confidentiality and integrity.
* **Never Embed Credentials in URLs:** Authentication tokens or passwords should never be passed in the `User` component or `Query String`.
* **Beware of Typosquatting:** Carefully inspect domain names for subtle spelling variations designed to deceive users into revealing sensitive information.
* **Sanitize User-Controlled Inputs:** Both `Query Strings` and `Fragments` can be manipulated by attackers and must be strictly validated and sanitized.

---

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

**محدد موقع الموارد الموحد (URL)** هو عنوان ويب قياسي يتيح للمستخدمين ومتصفحات الويب تحديد مواقع مختلف أنواع الموارد والوصول إليها عبر الإنترنت—مثل صفحات الويب، ومقاطع الفيديو، والصور، وواجهات البرمجة، والمستندات. يُعد فهم البنية الدقيقة لعنوان URL أمراً أساسياً للتنقل عبر الويب، وتشخيص أعطال التطبيقات، واكتشاف التهديدات الأمنية.

### 🧩 مكونات وبنية عنوان URL

لنتأمل المثال الكامل التالي لبنية عنوان URL:

```text
http://user:password@tryhackme.com:80/view-room?id=1#task3
```

| المكون | المثال | الوصف والاعتبارات الأمنية |
| :--- | :--- | :--- |
| **المخطط (Scheme)** | `http` | يُحدد بروتوكول الاتصال المستخدم للوصول إلى المورد (`HTTP` أو `HTTPS`). يُوصى دائماً باستخدام **HTTPS** لأنه يُشفّر البيانات أثناء النقل ويحميها من التنصت والتلاعب. |
| **المستخدم (User)** | `user:password` | بيانات تسجيل دخول اختيارية (اسم المستخدم وكلمة المرور) مُضمّنة داخل الرابط. أصبحت هذه الممارسة نادرة وغير آمنة لأنها قد تكشف البيانات الحساسة في سجل المتصفح وسجلات الخادم. |
| **المضيف / النطاق (Host / Domain)** | `tryhackme.com` | يُحدد اسم النطاق أو الخادم المستهدف. يستغل المهاجمون أخطاء الكتابة عبر تسجيل نطاقات مشابهة باختلافات طفيفة—وهو ما يُعرف بـ **انتحال الأحرف (Typosquatting)**—لتنفيذ هجمات **التصيد الاحتيالي (Phishing)**. |
| **المنفذ (Port)** | `80` | يُحدد البوابة أو الخدمة الشبكية على خادم الويب (تتراوح أرقام المنافذ من `1` إلى `65535`). المنافذ القياسية الأكثر شيوعاً هي `80` لبروتوكول `HTTP` و`443` لبروتوكول `HTTPS`. |
| **المسار (Path)** | `/view-room` | يُشير إلى الملف أو الصفحة أو نقطة النهاية المحددة على الخادم. يجب تأمين المسارات بصلاحيات صارمة لضمان وصول المستخدمين المصرح لهم فقط إلى الموارد الحساسة. |
| **سلسلة الاستعلام (Query String)** | `?id=1` | تبدأ بعلامة استفهام (`?`) وتُستخدم لتمرير بيانات ومعاملات إضافية (مثل كلمات البحث أو حقول النماذج). نظراً لإمكانية تعديلها من قبل المستخدم، فإن عدم تنظيفها وفحصها قد يؤدي إلى ثغرات الحقن (مثل **SQLi** و**XSS**). |
| **الجزء (Fragment)** | `#task3` | يبدأ برمز المربع (`#`) ويُوجّه المتصفح للانتقال مباشرة إلى قسم أو عنوان محدد داخل الصفحة. يُعالج غالباً من جانب العميل، ولكن التعامل غير الآمن معه عبر JavaScript قد يفتح ثغرات **DOM-based XSS**. |

### 🛡️ أبرز الخلاصات الأمنية

* **تفعيل HTTPS دائماً:** الاعتماد على الاتصال المشفر (`HTTPS` عبر المنفذ `443`) لحماية سرية البيانات وسلامتها.
* **عدم تضمين بيانات الاعتماد في الروابط:** تجنب وضع كلمات المرور أو الرموز السرية داخل جزء `User` أو `Query String`.
* **الحذر من انتحال الأحرف (Typosquatting):** التحقق الدقيق من أسماء النطاقات لتجنب المواقع المزيفة التي تحاكي المواقع الشهيرة.
* **فحص وتنظيف المدخلات:** التعامل بحذر مع `سلسلة الاستعلام` و`الجزء` باعتبارهما مدخلات قابلة للتعديل من المستخدم ويجب تعقيمها لمنع هجمات الحقن.
