نبدأ واحدة واحدة زي ما طلبت
هفصصلك أول قسمين حاليًا (Windows Server + Virtualization) بشكل بسيط باللهجة المصرية
نقسم الشرح لأجزاء قصيرة تمشي معاك خطوة بخطوة
وأظبطلك روابط مفيدة في الآخر

---

----------

## 🌳 **Active Directory - Windows Server**

### 🌟 **Main Role**

**🔑 Centralized Identity and Access Management**

#### ✅ المعنى:

Active Directory (AD) مسؤولة عن إدارة وتحديد هُوية كل الأجهزة والمستخدمين اللي في الشبكة  
يعني هي "العقل المدبر" اللي بيقرر:

-   مين المستخدمين اللي موجودين؟
    
-   كل مستخدم مسموح له يعمل إيه؟
    
-   كل جهاز مكانه فين ووظيفته إيه؟
    

----------

### 🧠 **شرح مختصر بالمصري**

> AD هي المكان اللي بيخزن فيه السيرفر كل البيانات الخاصة بالمستخدمين (زي الاسم والباسورد والصلاحيات)  
> وبتخلي مدير الشبكة يقدر يتحكم في الدخول على الأجهزة والملفات والطابعات وكل حاجة من مكان واحد  
> يعني لو عايز تمنع حد من الدخول أو تضيف يوزر جديد أو تتحكم في الصلاحيات، كله من AD

----------

### 🔍 **تفصيل شجري للمميزات**

```
Active Directory
│
├── 🎯 الهدف الرئيسي: Centralized Identity & Access Management
│
├── 👥 Users Management
│   ├── إنشاء يوزرات
│   ├── تحديد الباسورد
│   └── تعيين صلاحيات الوصول
│
├── 🖥️ Devices Management
│   ├── تسجيل الأجهزة
│   ├── ربط الأجهزة بالدومين
│   └── تحديد استخدام كل جهاز
│
├── 📂 Access Control
│   ├── مين يقدر يدخل على إيه؟
│   ├── تحديد الصلاحيات للملفات والفولدرات
│   └── التحكم في الوصول عن بعد
│
└── 🛡️ Security & Policies
    ├── تطبيق Group Policy
    ├── منع الاختراقات
    └── متابعة الـ Logs والأحداث

```

----------

### 🤔 سؤال يراجعك:

ليه Active Directory مهمة لأي شركة فيها أكتر من جهاز أو يوزر؟

🎯 الإجابة:  
علشان بتخلي الإدارة مركزية وسهلة، بدل ما تروح على كل جهاز تعدل صلاحيات أو تضيف يوزر، بتعمل كل حاجة من مكان واحد

----------
تمام يا زين  
نكمل بنفس الطريقة المنظمة والشكل الشجري

----------

## 🌳 **Authentication in Active Directory**

### ❓ **السؤال**

**Which component is responsible for authenticating users in a domain?**

✅ **الإجابة**:  
**🖥️ Domain Controller (DC)**

----------

### 🧠 **يعني إيه؟**

> Domain Controller هو السيرفر اللي بيشغل نسخة من Active Directory  
> يعني هو اللي بيشيك على اليوزر والباسورد  
> لما أي حد يحاول يدخل على الجهاز أو الشبكة، الـ DC هو اللي بيقوله "أهلاً" أو "ممنوع الدخول"

----------

### 🔍 **تفصيل شجري لمهمة Domain Controller**

```
Domain Controller (DC)
│
├── 🧾 Holds the Active Directory Database
│   └── فيه كل بيانات المستخدمين والأجهزة
│
├── ✅ Authenticates Users
│   ├── يشيك على اليوزر والباسورد
│   ├── يقرر إذا كان الشخص ده يقدر يدخل
│   └── بيرجع صلاحياته من الـ AD
│
├── 🔐 Issues Security Tokens
│   └── بعد ما يتأكد إنك يوزر صح، يديك Token عشان تدخل على باقي الشبكة
│
└── 🔄 Replicates Data to Other DCs
    └── لو في أكتر من DC في الشبكة، كلهم بيحدثوا بياناتهم مع بعض تلقائيًا

```

----------

### 👁️‍🗨️ **معلومة مهمة**

لو الـ Domain Controller وقع أو مش شغال، المستخدمين مش هيقدروا يدخلوا على الشبكة أو يستخدموا الـ resources  
عشان كده لازم يكون فيه أكتر من DC في الشبكة (واحد رئيسي وواحد Backup)

----------

### 🤔 سؤال يراجعك

لو عندك شبكة فيها 100 موظف، وكلهم بيدخلوا باستخدام اسم مستخدم وباسورد  
إيه السيرفر اللي بيتأكد من هويتهم؟

🎯 الإجابة: Domain Controller

----------

تحب أكمل على باقي المكونات زي DNS - DHCP - OU بنفس الطريقة؟

تمام يا زين  
نكمل الشرح في نفس الشكل الشجري وبطريقة بسيطة تساعدك تراجع وتحفظ بسرعة

----------

## 🌳 **Organizational Unit (OU) - Active Directory**

### ❓ **السؤال**

**What is a logical container for users and groups in Active Directory?**

✅ **الإجابة**:  
**📂 Organizational Unit (OU)**

----------

### 🧠 **يعني إيه؟**

> الـ OU هو فولدر منطقي جوا الـ Active Directory  
> بتقسم فيه المستخدمين والجروبات والأجهزة حسب القسم أو الوظيفة  
> زي ما تعمل فولدر اسمه "IT" وواحد تاني اسمه "HR" وتحط فيهم الناس اللي شغالين في الأقسام دي

----------

### 🔍 **تفصيل شجري لمهام OU**

```
Organizational Unit (OU)
│
├── 📁 Logical Container
│   └── بيجمع المستخدمين والجروبات والأجهزة تحت تصنيف معين
│
├── 🧑‍🤝‍🧑 Users & Groups
│   ├── ممكن تحط يوزرات
│   └── ممكن تحط جروبات أو أجهزة
│
├── 🛠️ Apply Group Policies
│   ├── تقدر تطبق سياسة معينة (Policy) على OU كامل
│   └── زي تحديد صلاحيات أو منع الوصول لحاجات معينة
│
└── 👮 Delegation of Control
    └── ممكن تدي صلاحيات لحد يدير الـ OU ده بس من غير ما يدير كل الشبكة

```

----------

### 🧠 مثال بالمصري

> لو الشركة فيها 3 أقسام: IT, HR, Finance  
> تعمل لكل قسم OU وتحط جواه الناس اللي شغالين فيه  
> وتقدر تطبق على كل OU صلاحيات مختلفة حسب طبيعة شغل القسم

----------

### 🤔 سؤال يراجعك

إزاي تقدر تنظم المستخدمين جوا Active Directory من غير ما تلغبط نفسك؟

🎯 الإجابة: باستخدام OU وتقسمهم حسب الأقسام أو الوظايف أو الفروع

----------

تحب دلوقتي أظبطهم كلهم في شجرة كبيرة واحدة؟  
ولا نكمل باقي المكونات زي DNS و DHCP؟
تمام يا زين  
نكمل بنفس الأسلوب الشجري السهل

----------

## 🌳 **Joining a Computer to a Domain**

### ❓ **السؤال**

**What is the purpose of joining a computer to a domain?**

✅ **الإجابة**:  
**🔐 Apply Centralized Security Policies**

----------

### 🧠 **يعني إيه؟**

> لما جهاز بينضم للدومين، بيبقى تحت تحكم الـ Domain Controller  
> يعني السيكيورتي بوليسي اللي بتتطبق من الـ AD بتتطبق عليه تلقائي  
> وبتقدر تدير الجهاز ده من السيرفر زي ما تدير أي يوزر أو جهاز تاني

----------

### 🔍 **تفصيل شجري للفكرة**

```
Joining a Computer to a Domain
│
├── 🧠 Purpose: Centralized Management
│
├── 🔐 Apply Group Policies
│   ├── زي إغلاق USB، منع تثبيت برامج، تغيير خلفية
│   └── والسياسات بتتطبق تلقائي عند تشغيل الجهاز
│
├── ✅ Enable User Logon with Domain Credentials
│   └── المستخدم يقدر يسجل الدخول على أي جهاز في الدومين باستخدام نفس اليوزر
│
├── 📦 Centralized Updates and Security
│   └── الجهاز بياخد تحديثات وبرامج من الـ server بشكل منظم
│
└── 📊 Monitoring & Auditing
    └── تقدر تتابع كل جهاز مين دخل عليه ومتى وإيه اللي حصل

```

----------

### 🧠 مثال بالمصري

> لو عندك 50 جهاز في الشركة  
> بدل ما تعدي على كل جهاز واحد واحد عشان تمنع تثبيت البرامج أو تغير الخلفية  
> تربطهم بالدومين، وتعمل بوليسي واحدة تطبق على الكل من السيرفر بضغطة زر

----------

### 🤔 سؤال يراجعك

لو جهاز مش متضمّن في الدومين، تقدر تطبق عليه سياسات الشبكة من السيرفر؟

🎯 الإجابة: لا، لازم الجهاز ينضم للدومين علشان يبقى تحت تحكم الـ Active Directory

----------

تحب أرتب لك كل اللي خدناه لحد دلوقتي في صورة واحدة شاملة؟
تمام يا زين  
نكمّل بنفس التنسيق 👇

----------

## 🌳 **Protocol Used by Active Directory to Query User and Group Info**

### ❓ **السؤال**

**Which protocol is used by Active Directory to query user and group information?**

✅ **الإجابة**:  
**📡 LDAP (Lightweight Directory Access Protocol)**

----------

### 🧠 **يعني إيه؟**

> LDAP هو البروتوكول اللي بيستخدمه الـ Active Directory علشان يسأل أو يبحث عن معلومات في قاعدة بيانات الـ AD  
> زي مثلًا: "هاتلي بيانات المستخدم ده" أو "مين في الجروب ده؟"

----------

### 🔍 **تفصيل شجري لوظيفة LDAP**

```
LDAP (Lightweight Directory Access Protocol)
│
├── 🔎 Query Protocol
│   └── بيستخدم للاستعلام عن بيانات في Active Directory
│
├── 🧑‍🤝‍🧑 يستخدم في جلب معلومات مثل:
│   ├── أسماء المستخدمين
│   ├── الجروبات
│   └── الأجهزة
│
├── ⚙️ يعمل على بورت:
│   ├── 389 (غير مشفر)
│   └── 636 (LDAPS - مشفر)
│
└── 📦 يستخدمه:
    ├── Windows Services
    ├── Authentication Systems
    └── Third-Party Apps للبحث أو التحقق من الهوية

```

----------

### 🧠 مثال بالمصري

> لما تسجل دخولك على جهاز في دومين، الـ DC بيستخدم LDAP علشان يدور على يوزرك ويشوف الباسورد صح ولا لأ  
> كأنك بتقول للسيرفر: "أنا فلان، فتشلي على بياناتي"، فيرد عليك باستخدام LDAP

----------

### 🤔 سؤال يراجعك

لو برنامج عايز يجيب لستة بكل اليوزرات من الـ Active Directory، هيستخدم إيه؟

🎯 الإجابة: بروتوكول LDAP

----------

تحب أعمل لك دلوقتي شجرة كاملة شاملة كل الأسئلة اللي راجعناها في شكل واحد؟
تمام يا زين  
نختم آخر سؤال في السلسلة دي ونجمعهم في الآخر على هيئة شجرة كاملة

----------

## 🌳 **Role Installed on Windows Server to Enable Active Directory**

### ❓ **السؤال**

**Which role is installed on Windows Server to enable Active Directory features?**

✅ **الإجابة**:  
**🧩 Active Directory Domain Services (AD DS)**

----------

### 🧠 **يعني إيه؟**

> AD DS هو الرول اللي بتنزّله على السيرفر علشان تحوّله لـ Domain Controller  
> ومن اللحظة دي، السيرفر يقدر يتحكم في المستخدمين والأجهزة ويطبق سياسات الشبكة

----------

### 🔍 **تفصيل شجري لـ AD DS Role**

```
Active Directory Domain Services (AD DS)
│
├── 📦 Role on Windows Server
│   └── لازم يتسطب علشان تبدأ تستخدم Active Directory
│
├── 🏢 Creates the Domain Controller
│   └── يحول السيرفر من عادي لـ DC مسؤول عن الـ Domain
│
├── 🧑‍💼 Manages:
│   ├── Users
│   ├── Groups
│   ├── Devices
│   └── Organizational Units (OUs)
│
├── 🛠️ Enables:
│   ├── Authentication
│   ├── Authorization
│   └── Group Policy Management
│
└── 🔁 Supports:
    ├── LDAP
    ├── Kerberos
    └── DNS Integration

```

----------

### 🧠 بالمصري

> لو معاك Windows Server جديد وعايز تبني شبكة بدومين  
> أول حاجة تعملها: تنزل رول اسمها "Active Directory Domain Services"  
> دي اللي بتخلي السيرفر هو اللي يوزع الصلاحيات ويدير الشبكة كلها

----------

### 🤔 سؤال يراجعك

من غير ما تنزل الرول دي، تقدر تعمل دومين؟

🎯 الإجابة: لأ، لازم السيرفر يكون عليه AD DS علشان يبقى Domain Controller

----------

### 🔄 ملخص شامل على شكل شجرة معرفة

```
Active Directory - Windows Server
│
├── 🎯 Main Role: Centralized Identity & Access Management
│
├── 🖥️ Domain Controller (DC)
│   ├── مسؤول عن تسجيل الدخول (Authentication)
│   └── فيه نسخة من قاعدة بيانات AD
│
├── 📂 Organizational Unit (OU)
│   ├── تقسيم منطقي للمستخدمين والجروبات
│   └── تقدر تطبق GPO مختلفة على كل OU
│
├── 💻 Join Computer to Domain
│   ├── علشان تطبق السياسات المركزية
│   └── وتخلي الأجهزة تحت تحكم السيرفر
│
├── 📡 Protocol: LDAP
│   ├── بيستخدم للاستعلام عن المستخدمين والجروبات
│   └── بيشتغل على بورت 389 أو 636 (لو مشفر)
│
└── 🧩 Role: Active Directory Domain Services (AD DS)
    ├── بيتسطب على Windows Server
    ├── بيحوّل السيرفر لـ Domain Controller
    └── بيفعّل كل خصائص AD

```

----------
تمام يا زين  
ده فرق مهم وأساسي في فهم Active Directory  
أهو الشرح بالشكل اللي بتحبه: بسيط، شجري، وبالمصري

----------

## 🌳 **Domain vs Domain Controller**

### ❓ **السؤال**

**What is the difference between a domain and a domain controller?**

✅ **الإجابة المختصرة**  
**🏢 Domain = Group of objects (users, computers, etc.)**  
**🖥️ Domain Controller = Server that manages that domain**

----------

### 🧠 **بالمصري**

> **الدومين** هو الكيان أو "الشبكة المنظمة" اللي فيها يوزرات وأجهزة وسياسات  
> **الـ Domain Controller** هو السيرفر اللي ماسك إدارة الدومين ده وبيتحكم فيه

زي بالظبط:

🔸 **الدومين = الشركة**  
🔸 **الـ DC = المدير العام اللي بيدير كل اللي في الشركة**

----------

### 🔍 **تفصيل شجري للفرق**

```
Domain
│
├── 💼 تعريف:
│   └── مجموعة من الـ objects (يوزرات - أجهزة - جروبات)
│
├── 🌐 مثال:
│   └── company.local
│
└── 🔐 بيشتغل جواه:
    ├── سياسات (GPOs)
    └── تنظيم حسب OUs

---

Domain Controller (DC)
│
├── 🖥️ تعريف:
│   └── سيرفر مثبت عليه AD DS
│
├── 🎯 مسؤولياته:
│   ├── تسجيل الدخول (Authentication)
│   ├── التحقق من الصلاحيات (Authorization)
│   ├── تطبيق السياسات (Policies)
│   └── إدارة المستخدمين والأجهزة
│
└── 🔁 فيه نسخة من:
    └── قاعدة بيانات Active Directory

```

----------

### 🧠 مثال عملي

> الشركة عندها دومين اسمه `company.local`  
> وجوا الدومين ده 100 موظف و50 جهاز  
> السيرفر اللي بيأكد إن الموظف ده له صلاحية يدخل هو الـ **Domain Controller**

----------

### 🤔 سؤال يراجعك

هل ممكن يبقى فيه دومين من غير Domain Controller؟

🎯 الإجابة: لا، لازم يبقى فيه DC واحد على الأقل علشان يدير الدومين

----------

تحب أضيف المقارنة دي على الشجرة اللي عملناها قبل كده؟  
ولا نكمل على باقي مكونات Active Directory؟

تمام يا زين  
هظبطهولك بنفس التنسيق التعليمي اللي بتحبه

----------

## ❓ **Which port does LDAP typically use?**

### ✅ **الإجابة الصح**:

**C) 389**

----------

### 💡 **الشرح بالمصري**

> بروتوكول LDAP هو اللي بيستخدمه Active Directory علشان يتواصل مع الأجهزة والبرامج  
> وبيشتغل على البورت رقم **389** لما يكون الاتصال **غير مشفر**

لو عايز الاتصال يكون مشفر (Secure)، بيستخدم بورت **636** وبيبقى اسمه **LDAPS**

----------

### 🔍 جدول سريع يقارن:

البروتوكول

الاسم الكامل

بورت

مشفر؟

LDAP

Lightweight Directory Access Protocol

389

❌ لأ

LDAPS

LDAP Secure

636

✅ آه

----------


## 🪟 Windows Server & Active Directory

### 1. إيه هو Windows Server؟

نسخة من ويندوز معمولة عشان تدير شبكة
مش زي ويندوز اللي على اللابتوب
ممكن تسطب عليه خدمات زي Active Directory - DNS - DHCP - File Sharing

---

### 2. Active Directory

ده نظام لإدارة المستخدمين والأجهزة في شبكة
تقدر تتحكم مين يدخل ومين لأ
تعمل جروب للـ HR وجروب للـ IT وتدي كل واحد صلاحياته
تسهل الـ login وتفرض policies

---

### 3. Domain vs Domain Controller

* **Domain**: الشبكة المركزية اللي كل حاجة ماشية تحتها
  مثال: الشركة اسمها `company.local` وكل الناس join عليها
* **Domain Controller (DC)**: السيرفر اللي بيشغل الـ Active Directory
  هو اللي بيأكّد إن الشخص ده ليه access ولا لأ
  لو وقع.. الدنيا بتبوظ

---

### 4. DNS + DHCP

* **DNS**: يحوللك الاسم لـ IP
  مثال: google.com ← 142.250.186.206
  مهم عشان الأجهزة تفهم بعض
* **DHCP**: يوزع IPs أوتوماتيك
  بدل ما تكتب IP يدوي لكل جهاز، هو بيعملها

---

### 5. OU (Organizational Unit)

أقسام داخل الـ Domain
زي فولدرات تحط فيها الـ users
مثال: OU للـ HR – OU للـ IT
وتطبق على كل OU سياسات مختلفة

---

### 6. LDAP

بروتوكول بيسهّل الوصول للبيانات من الـ Active Directory
لو عندك 1000 يوزر، تقدر تجيب يوزر معين عن طريق LDAP Query
بيستخدم في حاجات زي الـ Authentication

---

### 7. Join Domain

يعني جهاز يدخل ضمن الشبكة
عشان يورث السياسات ويقدر يتفاعل مع باقي الأجهزة
بتدخل على الكمبيوتر – تغير الـ domain – تكتب اسم الـ domain – تدخل يوزر ليه صلاحية

---

🎥 **مصادر Windows Server و AD**

* [شرح شامل Active Directory وDNS بالعربي](https://youtu.be/RoI9RVU_Hu0)
* [فيديو مختصر ممتاز](https://youtube.com/shorts/kTDfCl-4pNo?si=Jz6meDBf-TuECUPU)
* [Playlist منظمة للمبتدئين](https://youtube.com/playlist?list=PLoP_aS_FoPQc5C72Q0VAp_4RFsyFS19Nh)
* [شرح إضافي مفيد](https://youtube.com/playlist?list=PLDxVq3TlR9y2sMXaL_yLp-r6pUpevgC-w)

---

## 3️⃣ Virtualization (أهم نقطة 🧠)

### 1. يعني إيه Virtualization؟

تشغيل كذا جهاز وهمي (VM) على سيرفر حقيقي واحد
بتوفر فلوس وهاردوير وكهرباء
بدل ما تشتري 5 سيرفرات، تشغلهم كلهم على سيرفر واحد

---

### 2. إيه فايدته في الكلاود؟

الكلاود كلها مبنية على Virtualization
AWS - Azure - GCP بيشغلوا الآلاف من الـ VMs على سيرفرات فعلية
من غير Virtualization، مفيش كلاود

---

### 3. إيه هو Hypervisor؟

البرنامج أو النظام اللي بيشغل الـ VMs
بيتحكم في توزيع الموارد (RAM - CPU - Storage)

---

### 4. الفرق بين Hypervisor Type 1 و Type 2

* **Type 1 (Bare Metal)**: متسطب مباشرة على الهارد
  زي: VMware ESXi – Hyper-V Server – XenServer
  أداء أعلى – بيستخدم في الداتا سنتر
* **Type 2 (Hosted)**: بيتسطب فوق ويندوز أو لينوكس
  زي: VMware Workstation – VirtualBox
  للتجربة والتدريب

---

### 5. شركات بتقدم حلول Virtualization

* **VMware ESXi**: الأشهر في السوق
* **Microsoft Hyper-V**: مدمج في Windows Server
* **Citrix XenServer**: بيستخدموه في الـ VDI أكتر

---

### 6. إيه هو vCenter؟

أداة من VMware
بتدير كذا سيرفر ESXi من مكان واحد
بتقدر تعمل:

* Create/Delete VMs
* Migration
* Templates
* Monitoring
* Clustering و High Availability
تمام نبدأ بأساسيات **Virtualization** بشكل واقعي ومصري يخليك تحل أي سؤال بعد كده وانت فاهم مش حافظ

----------

## 🔹 يعني إيه Virtualization؟

**الـ Virtualization** هو إنك تستخدم جهاز حقيقي (physical server) وتشغل عليه أكتر من جهاز وهمي (VMs – Virtual Machines)  
كل VM شغال كأنه جهاز مستقل له نظام تشغيل وموارد خاصة بيه (RAM – CPU – Storage)  
بس في الحقيقة كلهم مشاركين نفس الهاردوير

✅ كأنك عامل تقسيمات وهمية لجهاز واحد وكل تقسيمة تعتبر جهاز كامل

----------

## 🔹 ليه نستخدم Virtualization؟

لأن زمان كنا بنشغّل كل تطبيق على سيرفر مستقل  
وده كان بيضيع موارد كتير وبيكلفك:

• فلوس أجهزة  
• مساحة في الداتا سنتر  
• كهرباء وتبريد  
• وقت إدارة

دلوقتي تقدر تشغل 10 تطبيقات على سيرفر واحد وتديرهم بسهولة من مكان واحد

----------

## 🔹 أنواع الـ Virtualization

1.  **Server Virtualization**  
    أشهر نوع، بتشغل كذا VM على سيرفر واحد
    
2.  **Desktop Virtualization**  
    المستخدم يشتغل على نظام تشغيل وهمي من أي مكان (زي VDI)
    
3.  **Application Virtualization**  
    تشغل برامج على جهاز من غير ما تتثبت فعليًا عليه
    
4.  **Storage Virtualization**  
    تدمج أكتر من وحدة تخزين وتعرضهم كأنهم وحدة واحدة
    
5.  **Network Virtualization**  
    تفصل الشبكات باستخدام Software (زي NSX)
    

----------

## 🔹 إيه هو Hypervisor؟

ده هو البرنامج/الطبقة اللي بتدير الـ VMs وتشغلهم فوق الهاردوير  
بيتعامل مع المعالج والرام ويقسّمهم بين الأجهزة الوهمية

### أنواع Hypervisor:

🔸 **Type 1 – Bare Metal**  
بيشتغل مباشرة على السيرفر الحقيقي  
زي: VMware ESXi – Microsoft Hyper-V Server – Xen  
✅ قوي ومستقر ومناسب للداتا سنتر

🔸 **Type 2 – Hosted**  
بيشتغل جوا نظام تشغيل زي برنامج  
زي: VMware Workstation – VirtualBox  
✅ مناسب للتجارب والتعليم

----------

## 🔹 شركات مشهورة بتعمل Hypervisors:

• **VMware** – أقوى شركة في السوق (ESXi – vSphere – vCenter)  
• **Microsoft** – Hyper-V  
• **Citrix** – XenServer  
• **Red Hat** – KVM

----------

## 🔹 إيه هو vSphere؟

vSphere هو اسم الـ Platform أو Suite اللي بتقدمه VMware وبيشمل:

• **ESXi**: الـ hypervisor اللي بيشغل الـ VMs  
• **vCenter**: برنامج لإدارة كل الـ ESXi Hosts وVMs من مكان مركزي  
• **vMotion – DRS – HA – vSAN**: أدوات مساعدة متقدمة

----------

## 🔹 إيه الفرق بين vCenter وESXi؟

الحاجة

ESXi

vCenter

نوعه

Hypervisor

Management Tool

مكانه

على السيرفر مباشرة

على VM أو سيرفر خارجي

استخدامه

لتشغيل VMs

لإدارة كل الـ ESXi من مكان واحد

إمكانياته

محدودة

كبيرة (HA, DRS, Monitoring, Templates)

----------

## 🔹 ليه الـ Virtualization مهم للكلاود؟

لأن الكلاود نفسها مبنية على فكرة إن الأجهزة مش مخصصة لك وحدك  
بل بتشارك الهاردوير مع غيرك  
فلو مش فاهم Virtualization كويس مش هتفهم الـ Cloud

⛅ الـ Cloud Providers زي AWS – Azure – GCP بيشتغلوا على مزارع سيرفرات ضخمة بتستخدم Virtualization علشان:

• توفر في الموارد  
• تدير الحمل  
• تعمل Scale بسهولة  
• تعزل المستخدمين عن بعض

----------

## 🔹 فايدة الـ Virtualization في الشغل الحقيقي

1.  توفير فلوس وهاردوير
    
2.  سهولة في النسخ الاحتياطي والريستور
    
3.  إدارة أفضل
    
4.  سرعة في التجربة والنشر
    
5.  High availability
    

----------

لو فهمت الكلام ده هتعرف تجاوب أي سؤال في الامتحان بسهولة  
تحب دلوقتي نبدأ في جزء الشرح الخاص بـ **Storage**؟  
ولا نعمل امتحان تاني للـ Virtualization؟

---
---
تمام
هعملك امتحان MCQ فيه 30 سؤال إنجليزي
يغطي:

* Windows Server & Active Directory
* Virtualization
* Storage Basics

كل سؤال تحتيه:

* الإجابة الصح ✅
* الشرح بالعربي ليه هي دي الصح

نبدأ:


تمام نخش على **Storage** بطريقة منظمة وسهلة تخليك تفهم وتشرح لأي حد تاني

----------

## 🔹 يعني إيه Storage؟

Storage = التخزين  
هو المكان اللي بنحط فيه الـ data  
بس مش مجرد هارد وخلاص  
فيه أنواع وطبقات ومفاهيم لازم تبقى فاهمها كويس

----------

## 🔹 أنواع التخزين الرئيسية:

### 1. **Block Storage**

• بيديك access على مستوى البلوك  
• كأنك بتتعامل مع هارد خام (زي ما بتتعامل مع C:/ و D:/)  
• تقدر تركب عليه file system زي NTFS أو EXT4  
• أسرع وأكتر مرونة، مناسب لقواعد البيانات وVMs

✅ مثال: iSCSI – FC – Local Disks – Amazon EBS

----------

### 2. **File Storage**

• access على مستوى الملفات والمجلدات  
• بيظهرلك Folder Network  
• سهل في الاستخدام لكن مش مرن زي البلوك

✅ مثال: NFS – SMB – Windows Shared Folder – Amazon EFS

----------

### 3. **Object Storage**

• بنخزن فيه ملفات كـ "Objects" وكل Object ليه Metadata وID  
• مفيش File System  
• مش مناسب لقواعد البيانات  
• مناسب للـ Backup والـ Archiving  
• تقدر توصله بـ API مش Mount

✅ مثال: Amazon S3 – Azure Blob – MinIO

----------

## 🔹 الفرق بين SAN و NAS و DAS

النوع

شرح بسيط

يوصل ازاي

يستخدم في ايه

**DAS**

Direct Attached Storage – الهارد راكب في السيرفر نفسه

SATA/SAS Cable

basic storage

**NAS**

Network Attached Storage – الجهاز بيتوصل بالنت ويوزع ملفات

Ethernet / IP

File Storage

**SAN**

Storage Area Network – شبكة متخصصة للتخزين

Fiber / iSCSI

Block Storage

----------

## 🔹 RAID Levels

RAID = Redundant Array of Independent Disks  
يعني بنركب أكتر من هارد ونظبطهم سوا علشان نوصل:

• إما لأداء أعلى  
• أو حماية من الفقد

### أشهر أنواع RAID:

النوع

شرح

مميزاته

عيوبه

RAID 0

توزيع الداتا على أكتر من هارد

أداء عالي

مفيش حماية – لو هارد راح الداتا راحت

RAID 1

Mirror – كل داتا تتنسخ على هارد تاني

حماية ممتازة

نص المساحة ضايعة

RAID 5

توزيع + parity

حماية + كفاءة

محتاج 3 هارد على الأقل – Performance متوسط

RAID 10

Combination of RAID 1 + 0

High speed + High protection

محتاج 4 هاردات على الأقل

----------

## 🔹 Protocols مرتبطة بالتخزين

البروتوكول

استخدامه

يشتغل مع

**NFS**

File sharing

Linux, Unix, VMware

**SMB**

File sharing

Windows

**iSCSI**

Block access over IP

Windows/Linux/VMs

**Fibre Channel**

High-speed Block storage

SANs كبيرة

**NTFS**

File System

Windows

**EXT4**

File System

Linux

----------

## 🔹 Backup Types

النوع

شرح

**Full Backup**

نسخة كاملة من الداتا

**Incremental**

بياخد بس اللي اتغير من آخر Backup

**Differential**

بياخد التغييرات من آخر Full Backup

**Snapshot**

لقطة سريعة من حالة الجهاز/الديسك في لحظة معينة

**Image Backup**

نسخة كاملة من النظام بكل إعداداته

----------

دي كده أهم المفاهيم الأساسية اللي لازم تبقى عارفها في التخزين  
لو جاهز نعمل عليها امتحان MCQ من 30 سؤال قولي  
ولو حابب ننتقل بعدها على جزء Networking أو Cloud قول وابدألك فيه
---

### ✅ **Windows Server & Active Directory** (10 أسئلة)

**1. What is the main role of Active Directory in a Windows Server environment?**
A) File sharing
B) Print management
C) Centralized identity and access management
D) Backup scheduling
✅ **Answer:** C
**شرح:** Active Directory بتدير كل المستخدمين والأجهزة في الشبكة، وبتحدد مين يقدر يعمل إيه

---

**2. Which component is responsible for authenticating users in a domain?**
A) DNS Server
B) DHCP Server
C) Domain Controller
D) OU
✅ **Answer:** C
**شرح:** الـ Domain Controller هو السيرفر اللي بيشغل Active Directory وبيتحقق من بيانات الدخول

---

**3. What does DNS do in a network?**
A) Assign IP addresses
B) Share files
C) Translate domain names to IP addresses
D) Manage print services
✅ **Answer:** C
**شرح:** DNS بيحول اسم الموقع لـ IP عشان الجهاز يقدر يوصل ليه

---

**4. What is the function of DHCP?**
A) Control user access
B) Assign IP addresses automatically
C) Create user accounts
D) Encrypt network traffic
✅ **Answer:** B
**شرح:** DHCP بيوزع IPs تلقائي لأي جهاز جديد يدخل الشبكة

---

**5. Which of the following is a logical container for users and groups in Active Directory?**
A) Domain
B) DHCP
C) OU (Organizational Unit)
D) Subnet
✅ **Answer:** C
**شرح:** الـ OU زي فولدر بننظم فيه المستخدمين ونجمعهم عشان نطبق عليهم سياسات معينة

---

**6. What is the purpose of joining a computer to a domain?**
A) Increase disk space
B) Allow shared printing
C) Apply centralized security policies
D) Boost internet speed
✅ **Answer:** C
**شرح:** الجهاز لما يدخل الدومين، بيبدأ يطبق سياسات الشركة ويتحكم فيه الأدمن

---

**7. What protocol is used by AD to query user and group information?**
A) SMB
B) FTP
C) LDAP
D) NFS
✅ **Answer:** C
**شرح:** LDAP هو البروتوكول اللي بيستخدمه AD عشان يسحب بيانات من الـ database بتاعته

---

**8. Which one is a role installed on Windows Server?**
A) Adobe Reader
B) Active Directory Domain Services (ADDS)
C) VLC Player
D) DNS Benchmark
✅ **Answer:** B
**شرح:** ADDS هو اللي بيخلي السيرفر يبقى Domain Controller

---

**9. A user cannot log in to the domain. Which server should you check first?**
A) File Server
B) DHCP Server
C) Domain Controller
D) Print Server
✅ **Answer:** C
**شرح:** لو المستخدم مش قادر يدخل الدومين، يبقى لازم تتأكد إن الـ DC شغال

---

**10. What’s the difference between a domain and a domain controller?**
A) Domain is software; DC is hardware
B) Domain is a group; DC manages that group
C) Domain is internet; DC is local
D) No difference
✅ **Answer:** B
**شرح:** الـ Domain هو الكيان اللي بيضم كل الأجهزة، والـ Domain Controller هو الجهاز اللي بيشغله

---
تمام
هبدأ دلوقتي أكتبلك 30 سؤال MCQ بالإنجليزي عن جزء
**🪟 Windows Server & Active Directory**
كل سؤال معاه الشرح بالعربي وموضح الإجابة الصح

---

### 🧪 Windows Server & Active Directory — 30 MCQ

1.

**What is the main purpose of Active Directory in a Windows Server environment?**
A) File compression
B) Email hosting
C) User and resource management
D) Antivirus deployment
✅ **Answer:** C
💡 **شرح:** Active Directory بتستخدم علشان تدير المستخدمين والـ resources زي الـ printers و الـ computers داخل الشبكة.

---

2.

**Which of the following is a key component of Active Directory?**
A) DNS
B) DHCP
C) Domain Controller
D) IIS
✅ **Answer:** C
💡 **شرح:** Domain Controller هو السيرفر اللي بيحتوي على نسخة من Active Directory وبيتحكم في صلاحيات الدخول.

---

3.

**What is the role of a Domain Controller?**
A) Provides IP addresses
B) Hosts websites
C) Authenticates users
D) Monitors network traffic
✅ **Answer:** C
💡 **شرح:** الـ Domain Controller بيأكد هوية المستخدم لما يحاول يدخل على الشبكة ويحدد صلاحياته.

---

4.

**In a Windows domain, what is the difference between a domain and a domain controller?**
A) No difference
B) Domain is the server, Domain Controller is the group
C) Domain is the network identity, Domain Controller manages authentication
D) Domain is hardware, Domain Controller is software
✅ **Answer:** C
💡 **شرح:** الـ Domain بيمثل الكيان أو الهوية بتاعة الشبكة، إنما الـ Domain Controller هو السيرفر المسؤول عن إدارة الدخول والـ policies.

---

5.

**What protocol does DNS use?**
A) FTP
B) TCP only
C) UDP only
D) Both TCP and UDP
✅ **Answer:** D
💡 **شرح:** DNS بيشتغل على TCP في zone transfers وUDP في الاستعلامات العادية.

---

6.

**What is the function of DHCP?**
A) Assign static IPs
B) Automatically assign IP addresses
C) Control access to websites
D) Encrypt data
✅ **Answer:** B
💡 **شرح:** DHCP بيوزع IP تلقائيًا على الأجهزة اللي بتتصل بالشبكة.

---

7.

**What is an Organizational Unit (OU) used for in Active Directory?**
A) Grouping servers
B) Dividing network bandwidth
C) Organizing users and policies
D) Encrypting user data
✅ **Answer:** C
💡 **شرح:** الـ OU بتستخدم لترتيب المستخدمين والـ groups والـ devices علشان نقدر نطبق عليهم سياسات معينة بسهولة.

---

8.

**Which port does LDAP typically use?**
A) 21
B) 25
C) 389
D) 443
✅ **Answer:** C
💡 **شرح:** LDAP اللي بيستخدم في الوصول لـ Active Directory بيشتغل على البورت 389.

---

9.

**What does LDAP stand for?**
A) Lightweight Directory Application Protocol
B) Local Directory Access Protocol
C) Lightweight Directory Access Protocol
D) Local Data Authentication Protocol
✅ **Answer:** C
💡 **شرح:** هو بروتوكول بيستخدمه الـ Active Directory للوصول للمعلومات الخاصة بالمستخدمين والـ objects.

---

10.

**You want to assign different policies to users in different departments. What AD feature would you use?**
A) DHCP
B) DNS
C) OU
D) NAT
✅ **Answer:** C
💡 **شرح:** نقدر نستخدم OU علشان نطبق policies مختلفة لكل قسم في الشركة.

---
تمام نكمل على طول

---

### 🧪 Windows Server & Active Directory — 30 MCQ (تكملة)

11.

**Which service allows Windows clients to locate domain controllers?**
A) DHCP
B) DNS
C) FTP
D) IIS
✅ **Answer:** B
💡 **شرح:** الـ DNS هو اللي بيحدد للـ clients فين الـ Domain Controller علشان يبدأ عملية الـ login.

---

12.

**What is the default name of the Active Directory database file?**
A) system32.dll
B) adlog.mdf
C) ntds.dit
D) activedir.sys
✅ **Answer:** C
💡 **شرح:** قاعدة بيانات Active Directory اسمها `ntds.dit` وهي اللي بيخزن فيها كل الـ objects بتاعة الدومين.

---

13.

**Which tool is used to manage Active Directory users and computers?**
A) DNS Manager
B) DHCP Console
C) ADUC
D) Group Policy Editor
✅ **Answer:** C
💡 **شرح:** ADUC = Active Directory Users and Computers ودي الـ console اللي بنستخدمها لإنشاء وتعديل users و OUs وغيره.

---

14.

**Which component is necessary for joining a Windows machine to a domain?**
A) IIS
B) FTP
C) DNS
D) Hyper-V
✅ **Answer:** C
💡 **شرح:** لازم DNS يكون شغال علشان الجهاز يعرف يلاقي الـ Domain Controller وينضم للدومين.

---

15.

**What is required to join a computer to a domain?**
A) Local account
B) Workgroup name
C) Network connectivity to Domain Controller
D) USB key
✅ **Answer:** C
💡 **شرح:** الجهاز لازم يكون شايف الـ Domain Controller على الشبكة علشان ينضم للدومين.

---

16.

**What happens when a user is disabled in Active Directory?**
A) The user is deleted
B) The user is locked forever
C) The user can't log in
D) The user gets admin privileges
✅ **Answer:** C
💡 **شرح:** لما الـ user يتعمله disable، مش هيقدر يدخل على الدومين بس حسابه لسه موجود.

---

17.

**Which of the following is NOT a valid object in Active Directory?**
A) User
B) Computer
C) Printer
D) Browser
✅ **Answer:** D
💡 **شرح:** الـ objects في AD بتشمل users, computers, printers... لكن مش حاجة اسمها browser كـ object.

---

18.

**What does GPO stand for in Active Directory?**
A) General Protocol Output
B) Group Policy Object
C) Global Policy Organization
D) General Permission Option
✅ **Answer:** B
💡 **شرح:** GPO هي السياسات اللي بتتطبق على users و OUs للتحكم في بيئة الجهاز والـ permissions.

---

19.

**Which protocol does LDAP use for secure communication?**
A) FTP
B) SMTP
C) LDAPS
D) HTTP
✅ **Answer:** C
💡 **شرح:** LDAPS هو LDAP مع تشفير SSL وبيشتغل غالبًا على البورت 636.

---

20.

**What is the primary function of Group Policy?**
A) Backup user data
B) Assign IP addresses
C) Enforce configurations and restrictions
D) Scan for viruses
✅ **Answer:** C
💡 **شرح:** Group Policy بتستخدم علشان تطبق إعدادات زي منع الـ USB أو إخفاء الـ control panel وهكذا.

---

21.

**Which command is used to force Group Policy update?**
A) gpedit.msc
B) ipconfig /flushdns
C) gpupdate /force
D) net user /add
✅ **Answer:** C
💡 **شرح:** `gpupdate /force` بيجبر الجهاز إنه يطبق كل السياسات الجديدة من الدومين فورًا.

---

22.

**What is the SYSVOL folder used for?**
A) Email storage
B) DHCP settings
C) Store scripts and GPOs
D) Printer drivers
✅ **Answer:** C
💡 **شرح:** فولدر SYSVOL هو المكان اللي بيخزن فيه الـ Domain Controller السكربتات والسياسات علشان تتوزع على الأجهزة.

---

23.

**Which Windows Server role includes Active Directory?**
A) Web Server
B) File Services
C) Active Directory Domain Services (AD DS)
D) Remote Desktop Services
✅ **Answer:** C
💡 **شرح:** AD DS هو الدور أو الـ Role اللي بنضيفه في Windows Server علشان نبدأ نستخدم Active Directory.

---

24.

**Which MMC snap-in is used to manage Group Policies?**
A) gpupdate
B) gpmc.msc
C) dsa.msc
D) ipconfig
✅ **Answer:** B
💡 **شرح:** `gpmc.msc` هو الـ Group Policy Management Console وده اللي بندير منه كل السياسات.

---

25.

**What happens if DNS is not properly configured in a domain environment?**
A) Users will get more storage
B) Users can't join or log in to domain
C) Printers will stop working
D) Files will get deleted
✅ **Answer:** B
💡 **شرح:** من غير DNS مضبوط، الجهاز مش هيلاقي الـ Domain Controller ومش هيعرف يدخل على الدومين.

---

26.

**What is the Global Catalog in Active Directory?**
A) List of all IPs
B) Centralized printer driver
C) Index of all AD objects
D) DHCP backup
✅ **Answer:** C
💡 **شرح:** Global Catalog هو نسخة خفيفة من كل الـ objects في الدومين وبيساعد في تسريع عمليات البحث.

---

27.

**Which command shows IP configuration including DNS and DHCP?**
A) nslookup
B) netstat
C) ipconfig /all
D) ping
✅ **Answer:** C
💡 **شرح:** `ipconfig /all` بيطلعلك كل حاجة عن إعدادات الشبكة زي الـ IP و الـ DNS و DHCP.

---

28.

**What is the default port used by DHCP server to offer IP addresses?**
A) 53
B) 67
C) 389
D) 443
✅ **Answer:** B
💡 **شرح:** DHCP بيشتغل على البورت 67 علشان يبعث IP للجهاز اللي بيطلبه.

---

29.

**How are Active Directory domains logically grouped?**
A) VLANs
B) Workgroups
C) Forests and Trees
D) Routers
✅ **Answer:** C
💡 **شرح:** الـ Domains في AD بتترتب في Trees وجواها Forest علشان يبقى فيه تسلسل ومنطقية في الإدارة.

---

30.

**What does “OU delegation” allow?**
A) Encrypting traffic
B) Hiding users from each other
C) Assigning control of OU to specific users
D) Monitoring disk usage
✅ **Answer:** C
💡 **شرح:** نقدر ندي صلاحيات معينة لأشخاص يديروا OU معينة بس من غير ما نديلهم صلاحيات على باقي الدومين.

---
تمام نكمل على طول
دلوقتي هديلك 30 سؤال MCQ عن **Virtualization**
كل سؤال بالإنجليزي
الإجابة الصح ✅
مع شرح مبسّط بالعربي باللهجة المصرية

---

**1. What is virtualization?**
A) Physical server installation
B) Creating multiple OS environments on one physical machine
C) Installing software manually
D) Using multiple physical servers
✅ **Answer: B**
**الشرح:** Virtualization يعني تشغل أكتر من نظام تشغيل (VMs) على سيرفر واحد باستخدام software زي hypervisor

---

**2. What is the main advantage of virtualization?**
A) Higher electricity bills
B) More hardware
C) Better resource utilization
D) Complex networking
✅ **Answer: C**
**الشرح:** بتخلي استخدامك للهاردوير أحسن لأنك بتشغّل أكتر من VM على جهاز واحد بدل ما تشتري سيرفر لكل حاجة

---

**3. What is a hypervisor?**
A) A type of network switch
B) A protocol
C) A software that creates and manages virtual machines
D) A backup software
✅ **Answer: C**
**الشرح:** Hypervisor هو اللي بيخلينا نعمل وتشغّل VMs، هو الأساس في موضوع الـ virtualization

---

**4. Which of the following is a Type 1 hypervisor?**
A) VirtualBox
B) VMware Workstation
C) VMware ESXi
D) Oracle VM
✅ **Answer: C**
**الشرح:** Type 1 hypervisor زي ESXi بيشتغل على السيرفر مباشرة من غير نظام تشغيل

---

**5. What is a Type 2 hypervisor?**
A) Runs on top of an OS
B) Replaces the OS
C) Needs a firewall
D) Only works in cloud
✅ **Answer: A**
**الشرح:** Type 2 بيشتغل فوق نظام التشغيل زي VMware Workstation أو VirtualBox

---

**6. Which company develops Hyper-V?**
A) Citrix
B) VMware
C) Red Hat
D) Microsoft
✅ **Answer: D**
**الشرح:** Hyper-V من منتجات Microsoft وبيشتغل على Windows Server

---

**7. What is VMware ESXi?**
A) A backup tool
B) A Linux distro
C) A Type 1 hypervisor
D) A DNS server
✅ **Answer: C**
**الشرح:** ESXi من VMware وهو Type 1 hypervisor بيشتغل مباشرة على الهاردوير

---

**8. What is vCenter used for?**
A) Monitor internet speed
B) Manage multiple ESXi hosts
C) Create Word documents
D) Format hard drives
✅ **Answer: B**
**الشرح:** vCenter بيدير أكتر من host و VM من مكان واحد، مفيد في إدارة الـ infrastructure الكبيرة

---

**9. Which of the following is NOT a virtualization platform?**
A) Citrix XenServer
B) VMware Workstation
C) Microsoft Paint
D) Microsoft Hyper-V
✅ **Answer: C**
**الشرح:** Paint برنامج رسم، مالوش علاقة بـ virtualization

---

**10. What does a virtual machine (VM) need to run?**
A) Antivirus
B) Hypervisor
C) DNS server
D) DHCP scope
✅ **Answer: B**
**الشرح:** أي VM لازم يكون فيه Hypervisor شغّال عشان تتخلق وتشتغل

---

**11. Virtualization is a key part of which concept?**
A) Physical topology
B) Software updates
C) Software-defined data center
D) Excel formulas
✅ **Answer: C**
**الشرح:** الـ SDDC معتمد بالكامل على الـ virtualization سواء في compute أو network أو storage

---

**12. What is the purpose of snapshots in virtualization?**
A) Capture screen
B) Take backup of configuration
C) Save VM state to restore later
D) Increase VM speed
✅ **Answer: C**
**الشرح:** snapshot بياخد لقطة من حالة الـ VM لو حصل مشكلة تقدر ترجعه

---

**13. Which is true about virtualization and cloud?**
A) Cloud doesn't use virtualization
B) Cloud fully depends on virtualization
C) Virtualization replaces the cloud
D) They're unrelated
✅ **Answer: B**
**الشرح:** Cloud infrastructure مبنية على virtualization عشان المرونة والتوفير

---

**14. What is a VM template?**
A) Graphic design
B) Pre-configured VM used to create new VMs
C) IP configuration
D) Password file
✅ **Answer: B**
**الشرح:** Template هي نسخة من VM معمولة جاهزة تقدر تعمل منها نسخ تانية بسرعة

---

**15. Citrix XenServer is used for?**
A) Web browsing
B) DNS resolution
C) Virtualization
D) File sharing
✅ **Answer: C**
**الشرح:** Citrix XenServer من أدوات الـ virtualization المشهورة وبيشتغل زي ESXi وHyper-V

---

نكمل الـ 15 سؤال الباقيين عن **Virtualization** ✅

---

**16. What is the main benefit of using vCenter Server?**
A) Configure USB ports
B) Manage multiple virtual switches
C) Centralized management of multiple ESXi hosts
D) Run antivirus
✅ **Answer: C**
**الشرح:** vCenter Server بيخلّيك تدير كل الـ hosts والـ VMs في مكان واحد بسهولة ومن غير تدخل مباشر في كل Host

---

**17. Which of the following best describes vMotion?**
A) Backup tool
B) Migration of a VM from one host to another without downtime
C) VM snapshotting
D) Internet filtering
✅ **Answer: B**
**الشرح:** vMotion بيسمح لك تنقل VM من Host للتاني من غير ما المستخدم يحس أو يحصل Downtime

---

**18. What is the difference between template and clone in virtualization?**
A) Template is permanent, clone is temporary
B) Clone needs DNS, template doesn't
C) Template is read-only base, clone is a VM copy
D) No difference
✅ **Answer: C**
**الشرح:** Template بنستخدمه كأساس لعمل VMs كتير، لكن Clone هو نسخة مستقلة تمامًا من VM شغال

---

**19. What is the minimum hardware requirement for running a hypervisor?**
A) Touchscreen
B) Multicore processor with virtualization support
C) External SSD
D) HDMI port
✅ **Answer: B**
**الشرح:** المعالج لازم يدعم virtualization technologies زي VT-x أو AMD-V عشان يشغل Hypervisor

---

**20. What is a resource pool in virtualization?**
A) Shared printer folder
B) Group of VMs using the same GPU
C) A logical group of resources (CPU, RAM)
D) Group of backup servers
✅ **Answer: C**
**الشرح:** resource pool هو وسيلة لتقسيم الموارد بين VMs عشان تديهم limits أو priorities

---

**21. Which of the following allows network virtualization in VMware?**
A) vSwitch
B) NAT
C) NIC teaming
D) vSAN
✅ **Answer: A**
**الشرح:** vSwitch هو Virtual Switch بيتعامل زي السويتش العادي لكن جوا الـ Hypervisor

---

**22. What is Thin Provisioning in virtual storage?**
A) Using HDDs instead of SSDs
B) Allocating full disk size immediately
C) Allocating storage space as needed
D) Encrypting VM disks
✅ **Answer: C**
**الشرح:** Thin Provisioning بيوفر مساحة لأنه مش بيحجز كل المساحة مرة واحدة، بيديها حسب الحاجة

---

**23. What does HA stand for in VMware environment?**
A) Hard Allocation
B) Host Authorization
C) High Availability
D) Hybrid Architecture
✅ **Answer: C**
**الشرح:** HA بتخلي الـ VMs تشتغل على Host تاني أوتوماتيك لو Host الأساسي وقع

---

**24. Which type of virtualization separates OS from hardware?**
A) Application virtualization
B) Desktop virtualization
C) Server virtualization
D) Network virtualization
✅ **Answer: C**
**الشرح:** Server virtualization هي اللي بتفصل نظام التشغيل عن الهاردوير وبتخلي كذا OS يشتغلوا على جهاز واحد

---

**25. Which technology enables multiple VMs to share physical storage efficiently?**
A) RAID
B) vSAN
C) BIOS
D) FTP
✅ **Answer: B**
**الشرح:** vSAN بتجمع أقراص Hosts مختلفة في pool واحد تقدر الـ VMs تشاركها

---

**26. What is nested virtualization?**
A) Using VM inside another VM
B) Dual-booting
C) Installing hypervisor in BIOS
D) Running Linux on Windows
✅ **Answer: A**
**الشرح:** Nested virtualization يعني تشغّل Hypervisor جوا VM، وده مفيد للتجربة والتعليم

---

**27. What is DRS in VMware?**
A) Disaster Recovery Storage
B) Dynamic RAM Scheduler
C) Distributed Resource Scheduler
D) DNS Resolution Service
✅ **Answer: C**
**الشرح:** DRS بيتابع استهلاك الموارد ويعمل balancing بين الـ Hosts

---

**28. What does “hot add” mean in virtualization?**
A) Adding VMs during shutdown
B) Adding storage after a backup
C) Adding CPU/RAM to VM while it's running
D) Adding IP addresses
✅ **Answer: C**
**الشرح:** Hot add بتسمح تضيف CPU أو RAM للـ VM من غير ما تطفيه

---

**29. What is meant by "overcommitment" in virtualization?**
A) Assigning more resources than available
B) Deleting extra files
C) Powering off VMs
D) Isolating VMs
✅ **Answer: A**
**الشرح:** ممكن تدي VMs موارد أكتر من المتاح فعليًا لأن مش كل VMs بتستخدمها في نفس الوقت

---

**30. What is “ballooning” in VM memory management?**
A) Compressing files
B) Expanding network interfaces
C) Forcing VM to give back unused memory
D) Increasing VM disk
✅ **Answer: C**
**الشرح:** Balloon driver بيخلي الـ VM تتنازل عن RAM مش بتستخدمها وترجعها للـ host لما يبقى في ضغط

---

كده خلصنا أول 30 سؤال في جزء **Virtualization**
تحب بعد كده نروح على جزء **Storage** بنفس الأسلوب؟
أو تجهزهم كـ PDF؟

---

**Q1: هل في علاقة مباشرة بين الهايبرفايزور والسيرفرات الحقيقية؟**
أيوه، الهايبرفايزور Type 1 بيشتغل على السيرفر مباشرة من غير أي OS، وده بيخليه سريع ومستقر في بيئة الإنتاج

**Q2: ليه بنستخدم vCenter بدل ما نشتغل على كل Host لوحده؟**
علشان إدارة مركزية، تقدر تعمل vMotion، تتابع الأداء، تعمل نسخ احتياطي ومراقبة من مكان واحد

**Q3: هل ممكن VM يبوظ باقي الـ VMs لو حصل فيه Crash؟**
لو البيئة معمولة صح (Isolation, Resource limits)، لأ، كل VM بيشتغل بمعزل عن الباقيين ومش بيأثر عليهم

===================================================================================================================





