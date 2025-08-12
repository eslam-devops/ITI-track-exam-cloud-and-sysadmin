تمام نخش على **Storage** بطريقة منظمة وسهلة تخليك تفهم وتشرح لأي حد تاني

---

## 🔹 يعني إيه Storage؟

Storage = التخزين
هو المكان اللي بنحط فيه الـ data
بس مش مجرد هارد وخلاص
فيه أنواع وطبقات ومفاهيم لازم تبقى فاهمها كويس

---

## 🔹 أنواع التخزين الرئيسية:

### 1. **Block Storage**

• بيديك access على مستوى البلوك
• كأنك بتتعامل مع هارد خام (زي ما بتتعامل مع C:/ و D:/)
• تقدر تركب عليه file system زي NTFS أو EXT4
• أسرع وأكتر مرونة، مناسب لقواعد البيانات وVMs

✅ مثال: iSCSI – FC – Local Disks – Amazon EBS

---

### 2. **File Storage**

• access على مستوى الملفات والمجلدات
• بيظهرلك Folder Network
• سهل في الاستخدام لكن مش مرن زي البلوك

✅ مثال: NFS – SMB – Windows Shared Folder – Amazon EFS

---

### 3. **Object Storage**

• بنخزن فيه ملفات كـ "Objects" وكل Object ليه Metadata وID
• مفيش File System
• مش مناسب لقواعد البيانات
• مناسب للـ Backup والـ Archiving
• تقدر توصله بـ API مش Mount

✅ مثال: Amazon S3 – Azure Blob – MinIO

---

## 🔹 الفرق بين SAN و NAS و DAS

| النوع   | شرح بسيط                                                   | يوصل ازاي      | يستخدم في ايه |
| ------- | ---------------------------------------------------------- | -------------- | ------------- |
| **DAS** | Direct Attached Storage – الهارد راكب في السيرفر نفسه      | SATA/SAS Cable | basic storage |
| **NAS** | Network Attached Storage – الجهاز بيتوصل بالنت ويوزع ملفات | Ethernet / IP  | File Storage  |
| **SAN** | Storage Area Network – شبكة متخصصة للتخزين                 | Fiber / iSCSI  | Block Storage |

---

## 🔹 RAID Levels

RAID = Redundant Array of Independent Disks
يعني بنركب أكتر من هارد ونظبطهم سوا علشان نوصل:

• إما لأداء أعلى
• أو حماية من الفقد

### أشهر أنواع RAID:

| النوع   | شرح                                  | مميزاته                      | عيوبه                                      |
| ------- | ------------------------------------ | ---------------------------- | ------------------------------------------ |
| RAID 0  | توزيع الداتا على أكتر من هارد        | أداء عالي                    | مفيش حماية – لو هارد راح الداتا راحت       |
| RAID 1  | Mirror – كل داتا تتنسخ على هارد تاني | حماية ممتازة                 | نص المساحة ضايعة                           |
| RAID 5  | توزيع + parity                       | حماية + كفاءة                | محتاج 3 هارد على الأقل – Performance متوسط |
| RAID 10 | Combination of RAID 1 + 0            | High speed + High protection | محتاج 4 هاردات على الأقل                   |

---

## 🔹 Protocols مرتبطة بالتخزين

| البروتوكول        | استخدامه                 | يشتغل مع            |
| ----------------- | ------------------------ | ------------------- |
| **NFS**           | File sharing             | Linux, Unix, VMware |
| **SMB**           | File sharing             | Windows             |
| **iSCSI**         | Block access over IP     | Windows/Linux/VMs   |
| **Fibre Channel** | High-speed Block storage | SANs كبيرة          |
| **NTFS**          | File System              | Windows             |
| **EXT4**          | File System              | Linux               |

---

## 🔹 Backup Types

| النوع            | شرح                                            |
| ---------------- | ---------------------------------------------- |
| **Full Backup**  | نسخة كاملة من الداتا                           |
| **Incremental**  | بياخد بس اللي اتغير من آخر Backup              |
| **Differential** | بياخد التغييرات من آخر Full Backup             |
| **Snapshot**     | لقطة سريعة من حالة الجهاز/الديسك في لحظة معينة |
| **Image Backup** | نسخة كاملة من النظام بكل إعداداته              |

---

دي كده أهم المفاهيم الأساسية اللي لازم تبقى عارفها في التخزين
لو جاهز نعمل عليها امتحان MCQ من 30 سؤال قولي
ولو حابب ننتقل بعدها على جزء Networking أو Cloud قول وابدألك فيه




==============================================================================================================================================================================================================





تمام
هنبدأ بـ **30 سؤال MCQ بالإنجليزي** عن جزء **Storage**
كل سؤال معاه الإجابة الصح والشرح بالعربي

---

### 🧠 Storage MCQ – 30 سؤال

---

**1. What is the main purpose of RAID 1?**
A) Increase performance only
B) Distribute data randomly
C) Mirror data for redundancy
D) Split data across disks

✅ **Correct Answer: C**
RAID 1 بيعمل نسخ طبق الأصل من الداتا على هارد تاني لحمايتها لو الأول باز

---

**2. Which storage type stores data as objects with metadata and ID?**
A) Block Storage
B) File Storage
C) Object Storage
D) Cloud Storage

✅ **Correct Answer: C**
Object Storage بيخزن الملفات كـ Object ومعاها Metadata وID بدون File System

---

**3. Which protocol is commonly used for Linux file sharing?**
A) SMB
B) NFS
C) iSCSI
D) HTTP

✅ **Correct Answer: B**
NFS بيستخدم غالبًا في أنظمة Linux وVMware للـ File Sharing

---

**4. What is a common use case for Block Storage?**
A) Hosting websites only
B) Database and VM storage
C) Archiving logs
D) File sharing

✅ **Correct Answer: B**
Block Storage مناسب لقواعد البيانات والـ Virtual Machines عشان الأداء العالي

---

**5. Which RAID level provides both striping and mirroring?**
A) RAID 0
B) RAID 1
C) RAID 5
D) RAID 10

✅ **Correct Answer: D**
RAID 10 بيجمع ما بين RAID 0 (أداء عالي) وRAID 1 (حماية)

---

**6. Which of the following is a file system used by Linux?**
A) NTFS
B) EXT4
C) FAT32
D) SMB

✅ **Correct Answer: B**
EXT4 هو File System مشهور في Linux

---

**7. What does SAN stand for?**
A) Software Attached Network
B) Storage Area Network
C) Storage Active Node
D) System Area Network

✅ **Correct Answer: B**
SAN = شبكة مخصصة للتخزين وتتعامل غالبًا مع Block Storage

---

**8. Which protocol is used for block-level storage over IP networks?**
A) SMB
B) FTP
C) iSCSI
D) HTTP

✅ **Correct Answer: C**
iSCSI بيستخدم IP عادي لكن بيوصل للتخزين كأنه هارد مباشر

---

**9. Which storage type connects directly to a single server?**
A) NAS
B) SAN
C) DAS
D) Cloud

✅ **Correct Answer: C**
DAS = Direct Attached Storage، زي الهارد راكب على نفس السيرفر

---

**10. RAID 5 needs a minimum of how many disks?**
A) 2
B) 3
C) 4
D) 1

✅ **Correct Answer: B**
RAID 5 لازم 3 هاردات عشان يوزع الداتا ويخزن Parity

---

**11. Which of the following is used for object storage in AWS?**
A) EFS
B) EBS
C) S3
D) Glacier

✅ **Correct Answer: C**
Amazon S3 = Object Storage بتقدر توصله بـ API

---

**12. What is a Snapshot in backup terms?**
A) Full copy of all data
B) Real-time virus scan
C) Point-in-time image of data
D) Log file backup

✅ **Correct Answer: C**
Snapshot = صورة من حالة السيستم/الداتا في لحظة معينة، مش نسخة كاملة

---

**13. What file protocol is used for Windows file sharing?**
A) iSCSI
B) NFS
C) SMB
D) HTTP

✅ **Correct Answer: C**
SMB هو البروتوكول الأساسي لمشاركة الملفات في Windows

---

**14. Which type of storage is best for archiving large unstructured data?**
A) Block
B) File
C) Object
D) SAN

✅ **Correct Answer: C**
Object Storage مناسب للتخزين الطويل المدى والبيانات غير المنظمة

---

**15. What does RAID stand for?**
A) Redundant Array of Inexpensive Disks
B) Remote Access Integrated Data
C) Rapid Access of Integrated Disks
D) Real-time Allocation of Independent Drives

✅ **Correct Answer: A**
RAID = Redundant Array of Inexpensive Disks

---

**16. Which type of storage uses folder and file hierarchy?**
A) Block
B) File
C) Object
D) SAN

✅ **Correct Answer: B**
File Storage هو اللي بيشتغل على مستوى الفولدرات والملفات

---

**17. What does NAS stand for?**
A) Network Area Storage
B) Network Attached Storage
C) New Access Storage
D) Node Access Storage

✅ **Correct Answer: B**
NAS = جهاز بيتوصل على الشبكة ويوزع ملفات للـ Users

---

**18. Which RAID level offers no redundancy?**
A) RAID 0
B) RAID 1
C) RAID 5
D) RAID 10

✅ **Correct Answer: A**
RAID 0 بيقسم الداتا فقط لأداء أعلى لكن مفيهوش حماية

---

**19. What is the main disadvantage of Object Storage?**
A) Expensive
B) No metadata
C) Not suitable for databases
D) Needs physical disks

✅ **Correct Answer: C**
Object Storage مش مناسب للـ Databases لأنه مش بيعتمد على file system

---

**20. What does iSCSI use for data transfer?**
A) Fiber Channel
B) Ethernet (IP Network)
C) USB
D) Serial Cable

✅ **Correct Answer: B**
iSCSI بيستخدم IP عادي للتوصيل بين السيرفر والستوريج

---

**21. Which file system supports large files and is common in Windows?**
A) EXT4
B) FAT32
C) SMB
D) NTFS

✅ **Correct Answer: D**
NTFS هو File System الأساسي في Windows ويدعم الملفات الكبيرة

---

**22. RAID 5 provides:**
A) No redundancy
B) Mirroring only
C) Striping with parity
D) Striping only

✅ **Correct Answer: C**
RAID 5 بيوزع الداتا وبيخزن Parity للـ Recovery

---

**23. What is one advantage of SAN over NAS?**
A) Slower performance
B) Cheaper
C) Block-level access
D) Only for Linux

✅ **Correct Answer: C**
SAN بيوفر Block-level access، أسرع وأنسب للـ VMs والـ DBs

---

**24. Which backup type stores only new or changed data?**
A) Full
B) Incremental
C) Differential
D) Snapshot

✅ **Correct Answer: B**
Incremental بياخد الجديد بس من آخر Backup

---

**25. Which protocol is not for storage?**
A) NFS
B) iSCSI
C) SMTP
D) SMB

✅ **Correct Answer: C**
SMTP خاص بالإيميلات، مش ستوريج

---

**26. EXT4 is a file system used in:**
A) Windows
B) Linux
C) MacOS
D) NAS

✅ **Correct Answer: B**
EXT4 مستخدم في توزيعات Linux زي Ubuntu وCentOS

---

**27. What does NTFS stand for?**
A) New Technology File System
B) Network Transfer File Storage
C) Native Transfer Format Service
D) None of the above

✅ **Correct Answer: A**
NTFS = New Technology File System

---

**28. RAID 10 is best when you need:**
A) High protection only
B) Lowest cost storage
C) High speed and high redundancy
D) Parity-based performance

✅ **Correct Answer: C**
RAID 10 بيجمع بين السرعة والحماية

---

**29. Which one is a cloud-based object storage?**
A) Azure VM
B) Amazon S3
C) iSCSI
D) EBS

✅ **Correct Answer: B**
Amazon S3 = Object Storage وبتوصله بـ API

---

**30. SAN is mostly used with:**
A) File storage
B) Object storage
C) Block storage
D) Cloud

✅ **Correct Answer: C**
SAN غالبًا بيستخدم Block-level Storage

---

لو جاهز نبدأ على جزء Networking أو Cloud قولي
ولو عايز نسخة PDF للأسئلة بلغني













