# 🏗️ Task 2: Web Application Overview | نظرة عامة على تطبيق الويب

## 🇬🇧 English Documentation

### 📌 Overview

A web application relies on several core components working together seamlessly to deliver content, process user interactions, and protect sensitive data. Understanding these components and their roles in the communication pipeline is essential for analyzing web architecture and identifying potential attack surfaces.

### 🧩 Core Components of a Web Application

#### 1. Web Browser (Client)
* **Role:** The primary tool used by end-users to access, render, and interact with web applications (e.g., Chrome, Firefox, Edge, Safari).
* **Functionality:** Translates user actions into HTTP/HTTPS requests, parses server responses (`HTML`, `CSS`, `JavaScript`), and executes client-side scripts locally.

#### 2. Web Server
* **Role:** The software or hardware component hosted on a computer/server responsible for storing, processing, and delivering web application content to clients.
* **Functionality:** Listens for incoming network requests on specific ports (typically `80` or `443`), serves static files directly, or forwards dynamic requests to backend application logic and databases (e.g., Apache, Nginx, IIS).

#### 3. Web Application Firewall (WAF)
* **Role:** A dedicated security layer positioned between the client and the web server that monitors, filters, and blocks malicious HTTP/HTTPS traffic.
* **Functionality:** Inspects incoming requests for common web attack patterns—such as **SQL Injection (SQLi)**, **Cross-Site Scripting (XSS)**, and **Cross-Site Request Forgery (CSRF)**—ensuring only legitimate traffic reaches the application.

### 🔄 Architectural Flow

```text
[ User / Web Browser ]  --->  [ Web Application Firewall (WAF) ]  --->  [ Web Server & Backend ]
       (Client)                       (Security Filtering)                 (Hosting & Content)
```

1. **Client Initiation:** The user interacts with the **Web Browser**, which sends a request toward the application's domain.
2. **Traffic Inspection:** The **WAF** intercepts the incoming traffic, analyzes payloads and headers against security rules, and drops malicious packets.
3. **Content Delivery:** Clean traffic reaches the **Web Server**, which processes the request and returns the appropriate response back to the browser.

### 🛡️ Security Perspective

Each component introduces specific security considerations:
* **Client-Side:** Vulnerable to script manipulation, session hijacking, and malicious browser extensions.
* **Network & Perimeter:** Requires strong encryption (`HTTPS`) and properly configured **WAF** rules to filter automated bots and exploit attempts.
* **Server-Side:** Must be hardened against misconfigurations, unauthorized file access, and backend injection flaws.

---

## 🇸🇦 التوثيق باللغة العربية

### 📌 نظرة عامة

يعتمد تطبيق الويب على مجموعة من المكونات الأساسية التي تعمل معاً بتناغم لتقديم المحتوى، ومعالجة تفاعلات المستخدمين، وحماية البيانات الحساسة. إن فهم هذه المكونات ودور كل منها في سلسلة الاتصال يُعد أمراً جوهرياً لتحليل بنية الويب وتحديد نقاط الضعف المحتملة.

### 🧩 المكونات الأساسية لتطبيق الويب

#### 1. متصفح الويب (Web Browser - العميل)
* **الدور:** الأداة الرئيسية التي يستخدمها المستخدم للوصول إلى تطبيقات الويب وعرضها والتفاعل معها (مثل Chrome وFirefox وEdge وSafari).
* **الوظيفة:** يُحوّل إجراءات المستخدم إلى طلبات HTTP/HTTPS، ويُفسّر استجابات الخادم (`HTML` و`CSS` و`JavaScript`)، ويُنفّذ البرامج النصية من جانب العميل.

#### 2. خادم الويب (Web Server)
* **الدور:** المكون البرمجي أو المادي الموجود على جهاز الكمبيوتر/الخادم والمسؤول عن استضافة وتقديم محتوى تطبيقات الويب للعملاء.
* **الوظيفة:** يستمع للطلبات الواردة عبر منافذ محددة (عادةً `80` أو `443`)، ويُقدّم الملفات الثابتة مباشرة، أو يُمرّر الطلبات الديناميكية إلى منطق التطبيق الخلفي وقواعد البيانات (مثل Apache وNginx وIIS).

#### 3. جدار حماية تطبيقات الويب (Web Application Firewall - WAF)
* **الدور:** طبقة حماية مخصصة تقع بين العميل وخادم الويب، وتعمل على مراقبة وتصفية حركة المرور الواردة لمنع الهجمات الخبيثة وضمان أمان التطبيق.
* **الوظيفة:** يفحص الطلبات الواردة للكشف عن أنماط هجمات الويب الشائعة—مثل **حقن قواعد البيانات (SQL Injection)** و**البرمجة عبر المواقع (XSS)**—لضمان وصول حركة المرور السليمة فقط إلى التطبيق.

### 🔄 مسار العمل المعماري

```text
[ المستخدم / متصفح الويب ]  --->  [ جدار حماية تطبيقات الويب (WAF) ]  --->  [ خادم الويب والواجهة الخلفية ]
         (العميل)                         (تصفية وحماية)                      (الاستضافة وتقديم المحتوى)
```

1. **بدء الاتصال:** يتفاعل المستخدم مع **متصفح الويب**، الذي يُرسل طلباً نحو نطاق التطبيق.
2. **فحص حركة المرور:** يعترض **جدار الحماية (WAF)** حركة المرور الواردة، ويُحلل البيانات والرؤوس وفق قواعد الأمان، ويحظر الحزم الخبيثة.
3. **تقديم المحتوى:** تصل الطلبات السليمة إلى **خادم الويب**، الذي يُعالج الطلب ويُعيد الاستجابة المناسبة إلى المتصفح.

### 🛡️ المنظور الأمني

يتطلب كل مكون من هذه المكونات اعتبارات أمنية محددة:
* **جانب العميل (Client-Side):** عُرضة للتلاعب بالمدخلات، واختطاف الجلسات، والإضافات الخبيثة.
* **محيط الشبكة (Perimeter):** يتطلب تشفيراً قوياً (`HTTPS`) وإعدادات دقيقة لجدار الحماية (**WAF**) لصد الهجمات الآلية ومحاولات الاستغلال.
* **جانب الخادم (Server-Side):** يجب تحصينه ضد أخطاء الإعداد، والوصول غير المصرح به للملفات، وثغرات الحقن الخلفية.
