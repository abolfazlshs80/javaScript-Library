# قوانین کلی تولید محتوا

1. آموزش را کاملاً از سطح مبتدی شروع کن.
2. مطالب را از ساده به پیچیده مرتب کن.
3. هر مفهوم را ابتدا با زبان ساده توضیح بده.
4. سپس تعریف فنی همان مفهوم را ارائه کن.
5. برای مفاهیم مهم مثال روزمره و قابل‌درک بزن.
6. سپس مثال JavaScript ارائه کن.
7. کدها باید کامل، صحیح و قابل اجرا باشند.
8. برای هر مثال، کد را خط‌به‌خط توضیح بده.
9. اصطلاحات انگلیسی مهم را داخل پرانتز کنار معادل فارسی بنویس.
10. بین مفاهیم مشابه تفاوت دقیق ایجاد کن.
11. از ساده‌سازی اشتباه مفاهیم جلوگیری کن.
12. اگر رفتاری وابسته به JavaScript Engine است، این موضوع را صریحاً بیان کن.
13. بین رفتار استاندارد JavaScript و جزئیات موتورهایی مانند V8 تفاوت بگذار.
14. هیچ ادعایی درباره اجرای دقیق و قطعی Garbage Collection نکن، مگر اینکه استاندارد یا مستندات آن را تضمین کرده باشند.
15. از عبارت‌هایی مانند «GC دقیقاً در این لحظه اجرا می‌شود» بدون دلیل معتبر استفاده نکن.
16. مطالب را با Markdown مناسب GitHub بنویس.
17. Headingها باید منظم و دارای سلسله‌مراتب باشند.
18. در پایان آموزش، منابع معتبر را همراه با لینک مستقیم ارائه کن.
19. منابع ترجیحاً شامل MDN، ECMAScript Specification، V8 و Node.js Documentation باشند.
20. اگر برای یک موضوع منبع رسمی وجود دارد، از منبع رسمی استفاده کن.
21. از منابع وبلاگی ضعیف یا مطالب بدون اعتبار به‌عنوان منبع اصلی استفاده نکن.
22. هرجا لازم است، تفاوت Browser و Node.js را توضیح بده.
23. در پایان هر بخش یک خلاصه کوتاه قرار بده.
24. برای مباحث مهم تمرین عملی ارائه کن.
25. در پایان کل آموزش، یک پروژه عملی برای بررسی Memory Leak و Garbage Collection ارائه کن.

---


## 1. مقدمه‌ای بر Garbage Collection

### 1.1 Garbage Collector چیست؟

### 1.2 Garbage چیست؟

### 1.3 Garbage Collection چیست؟

### 1.4 چرا JavaScript به Garbage Collector نیاز دارد؟

### 1.5 آیا JavaScript خودش حافظه را مدیریت می‌کند؟

### 1.6 آیا برنامه‌نویس JavaScript اصلاً لازم نیست به Memory Management فکر کند؟

### 1.7 تفاوت Memory Management در زبان‌های سطح پایین و JavaScript

### 1.8 تفاوت مدیریت حافظه در C/C++ و JavaScript

### 1.9 مزایا و محدودیت‌های Garbage Collection

---

# 2. Memory Management در JavaScript

## 2.1 Memory چیست؟

## 2.2 Memory Allocation چیست؟

## 2.3 Memory Usage چیست؟

## 2.4 Memory Deallocation چیست؟

## 2.5 چرخه حیات حافظه

* Allocate
* Use
* Release

## 2.6 JavaScript چگونه حافظه اختصاص می‌دهد؟

## 2.7 JavaScript چگونه حافظه را آزاد می‌کند؟

## 2.8 Automatic Memory Management چیست؟

## 2.9 تفاوت Manual Memory Management و Automatic Memory Management

---

# 3. Stack و Heap

## 3.1 Stack چیست؟

## 3.2 Heap چیست؟

## 3.3 تفاوت Stack و Heap

## 3.4 نقش Stack در اجرای JavaScript

## 3.5 نقش Heap در نگهداری Objectها

## 3.6 Primitiveها و Memory

## 3.7 Objectها و Memory

## 3.8 Arrayها و Memory

## 3.9 Functionها و Memory

## 3.10 Reference چیست؟

## 3.11 Strong Reference چیست؟

> توجه: این بخش را ساده توضیح بده و بعداً در بخش WeakRef به‌صورت عمیق‌تر بررسی کن.

---

# 4. Reachability

یکی از مهم‌ترین بخش‌های آموزش را به مفهوم **Reachability** اختصاص بده.

## 4.1 Reachable چیست؟

## 4.2 Unreachable چیست؟

## 4.3 چرا Reachability برای Garbage Collector مهم است؟

## 4.4 Root چیست؟

## 4.5 Garbage Collection Root چیست؟

## 4.6 Global Object به‌عنوان Root

## 4.7 Reference Graph چیست؟

## 4.8 مسیر دسترسی به Objectها

## 4.9 چه زمانی یک Object قابل جمع‌آوری می‌شود؟

## 4.10 تفاوت:

```text
Object is unused
```

و:

```text
Object is unreachable
```

این تفاوت را با مثال‌های متعدد توضیح بده.

---

# 5. Mark-and-Sweep

## 5.1 Mark-and-Sweep چیست؟

## 5.2 چرا Mark-and-Sweep به وجود آمد؟

## 5.3 مرحله Mark

## 5.4 مرحله Sweep

## 5.5 پیدا کردن Objectهای Reachable

## 5.6 پیدا کردن Objectهای Unreachable

## 5.7 مثال ساده Mark-and-Sweep

## 5.8 مثال با چند Object

## 5.9 مثال با Reference Chain

## 5.10 مثال با Circular Reference

## 5.11 چرا Circular Reference در Mark-and-Sweep مشکل اصلی نیست؟

---

# 6. Reference Counting

## 6.1 Reference Counting چیست؟

## 6.2 چگونه کار می‌کند؟

## 6.3 مثال ساده Reference Counting

## 6.4 مشکل Circular Reference

## 6.5 مثال Circular Reference

## 6.6 تفاوت Reference Counting و Mark-and-Sweep

## 6.7 آیا موتورهای مدرن JavaScript از Reference Counting به‌عنوان الگوریتم اصلی GC استفاده می‌کنند؟

در این قسمت از منابع معتبر استفاده کن و تفاوت الگوریتم‌های تاریخی و موتورهای مدرن را دقیق توضیح بده.

---

# 7. Circular Reference

## 7.1 Circular Reference چیست؟

## 7.2 مثال ساده

## 7.3 Circular Reference بین دو Object

## 7.4 Circular Reference بین چند Object

## 7.5 آیا Circular Reference همیشه Memory Leak ایجاد می‌کند؟

## 7.6 چرا Mark-and-Sweep می‌تواند Cycleها را مدیریت کند؟

## 7.7 تفاوت Circular Reference و Memory Leak

---

# 8. Garbage Collector چگونه تصمیم می‌گیرد؟

## 8.1 آیا GC می‌فهمد یک Object دیگر استفاده نمی‌شود؟

## 8.2 آیا GC دقیقاً می‌داند چه زمانی Object دیگر لازم نیست؟

## 8.3 Reachability چگونه تعیین می‌شود؟

## 8.4 Rootها

## 8.5 Reference Graph

## 8.6 Unreachable Objects

## 8.7 آیا زمان Garbage Collection قابل پیش‌بینی است؟

## 8.8 چرا JavaScript اجازه کنترل کامل GC را نمی‌دهد؟

---

# 9. Generational Garbage Collection

## 9.1 Generational GC چیست؟

## 9.2 چرا Objectها به Generation تقسیم می‌شوند؟

## 9.3 Generational Hypothesis چیست؟

## 9.4 Young Generation چیست؟

## 9.5 Old Generation چیست؟

## 9.6 Nursery چیست؟

## 9.7 Intermediate Generation چیست؟

## 9.8 Promotion چیست؟

## 9.9 Minor GC چیست؟

## 9.10 Major GC چیست؟

## 9.11 چرا Objectهای کوتاه‌عمر اهمیت دارند؟

## 9.12 مثال عملی از Objectهای کوتاه‌عمر

---

# 10. Garbage Collection در V8

## 10.1 V8 چیست؟

## 10.2 V8 چه ارتباطی با JavaScript دارد؟

## 10.3 آیا V8 خود JavaScript است؟

## 10.4 JavaScript Engine چیست؟

## 10.5 Heap در V8

## 10.6 Young Generation در V8

## 10.7 Old Generation در V8

## 10.8 Scavenger چیست؟

## 10.9 Mark-Sweep

## 10.10 Mark-Compact

## 10.11 Object Promotion

## 10.12 Object Moving

## 10.13 Compaction

## 10.14 Fragmentation

## 10.15 Write Barrier

## 10.16 Remembered Set

در این بخش حتماً از مستندات رسمی V8 استفاده کن و مشخص کن که جزئیات داخلی V8 ممکن است با نسخه‌های مختلف تغییر کند. V8 از Garbage Collection نسلی استفاده می‌کند و مستندات رسمی آن Young و Old Generation و فرآیندهای مربوط به آن را توضیح می‌دهند.

---

# 11. انواع تکنیک‌های Garbage Collection

## 11.1 Stop-the-World

## 11.2 Incremental Garbage Collection

## 11.3 Concurrent Garbage Collection

## 11.4 Parallel Garbage Collection

## 11.5 Compaction

## 11.6 Copying Collector

## 11.7 Generational Collector

## 11.8 تفاوت این تکنیک‌ها

برای هرکدام:

* تعریف
* دلیل استفاده
* مزایا
* معایب
* مثال ساده
* ارتباط با Performance

را توضیح بده.

---

# 12. Garbage Collection و Performance

## 12.1 GC چگونه روی Performance تأثیر می‌گذارد؟

## 12.2 GC Pause چیست؟

## 12.3 GC Pressure چیست؟

## 12.4 Allocation زیاد چیست؟

## 12.5 چرا Allocation زیاد می‌تواند باعث GC بیشتر شود؟

## 12.6 آیا ایجاد Object زیاد همیشه بد است؟

## 12.7 Objectهای کوتاه‌عمر

## 12.8 Objectهای بلندعمر

## 12.9 Memory Pressure

## 12.10 رابطه Memory و CPU

## 12.11 رابطه Garbage Collection و Latency

---

# 13. Memory Leak

## 13.1 Memory Leak چیست؟

## 13.2 چرا Memory Leak در JavaScript امکان‌پذیر است؟

## 13.3 آیا Garbage Collector می‌تواند تمام Memory Leakها را برطرف کند؟

## 13.4 تفاوت:

```text
Garbage
```

```text
Memory Leak
```

```text
High Memory Usage
```

## 13.5 نشانه‌های Memory Leak

## 13.6 رشد دائمی Heap

## 13.7 Memory Leak در برنامه‌های Long-Running

---

# 14. دلایل رایج Memory Leak

## 14.1 Global Variables

## 14.2 Accidental Globals

## 14.3 Event Listenerها

## 14.4 setInterval

## 14.5 setTimeout

## 14.6 Closure

## 14.7 Cacheهای بدون محدودیت

## 14.8 Arrayهای بزرگ

## 14.9 Mapهای بزرگ

## 14.10 DOM Referenceها

## 14.11 Detached DOM Nodes

## 14.12 Subscriptionها

## 14.13 Observerها

## 14.14 Promiseها و عملیات Async طولانی

برای هر مورد یک مثال Memory Leak ارائه کن و سپس نسخه اصلاح‌شده را نشان بده.

---

# 15. Closure و Garbage Collection

## 15.1 Closure چیست؟

## 15.2 Closure چگونه به Memory مربوط می‌شود؟

## 15.3 آیا Closure باعث Memory Leak می‌شود؟

## 15.4 چه زمانی Closure می‌تواند Objectها را زنده نگه دارد؟

## 15.5 مثال ساده

## 15.6 مثال Memory Leak

## 15.7 روش صحیح مدیریت Closure

---

# 16. Event Listener و Garbage Collection

## 16.1 Event Listener چیست؟

## 16.2 Event Listener چگونه Reference ایجاد می‌کند؟

## 16.3 addEventListener

## 16.4 removeEventListener

## 16.5 Anonymous Function و مشکل حذف Listener

## 16.6 مثال Memory Leak

## 16.7 Cleanup صحیح

---

# 17. Timerها و Garbage Collection

## 17.1 setTimeout

## 17.2 setInterval

## 17.3 clearTimeout

## 17.4 clearInterval

## 17.5 Timer و Closure

## 17.6 Timer چگونه می‌تواند Object را زنده نگه دارد؟

## 17.7 مثال Memory Leak با setInterval

## 17.8 نسخه اصلاح‌شده

---

# 18. Map و Set

## 18.1 Map چیست؟

## 18.2 Set چیست؟

## 18.3 Map و Strong Reference

## 18.4 Set و Strong Reference

## 18.5 چرا Map می‌تواند باعث نگه‌داشتن Objectها شود؟

## 18.6 مثال Memory Leak با Map

---

# 19. WeakMap و WeakSet

## 19.1 WeakMap چیست؟

## 19.2 WeakSet چیست؟

## 19.3 تفاوت Map و WeakMap

## 19.4 تفاوت Set و WeakSet

## 19.5 Weak Reference چیست؟

## 19.6 چرا WeakMap با Garbage Collection ارتباط دارد؟

## 19.7 چه چیزی در WeakMap به‌صورت Weak نگهداری می‌شود؟

## 19.8 چرا WeakMap قابل Iterate کردن نیست؟

## 19.9 مثال کاربردی WeakMap

## 19.10 مثال کاربردی WeakSet

## 19.11 چه زمانی WeakMap مناسب است؟

## 19.12 چه زمانی استفاده از WeakMap اشتباه است؟

---

# 20. WeakRef

## 20.1 WeakRef چیست؟

## 20.2 Strong Reference چیست؟

## 20.3 Weak Reference چیست؟

## 20.4 تفاوت Strong Reference و Weak Reference

## 20.5 ساخت WeakRef

## 20.6 متد deref()

## 20.7 مثال عملی WeakRef

## 20.8 WeakRef و Cache

## 20.9 آیا WeakRef تضمین می‌کند Object حذف شود؟

## 20.10 آیا زمان GC قابل پیش‌بینی است؟

## 20.11 چرا نباید Logic اصلی برنامه را به WeakRef وابسته کرد؟

در این بخش تأکید کن که رفتار زمان‌بندی Garbage Collection قطعی نیست.

---

# 21. FinalizationRegistry

## 21.1 FinalizationRegistry چیست؟

## 21.2 چرا وجود دارد؟

## 21.3 register()

## 21.4 unregister()

## 21.5 Cleanup Callback

## 21.6 مثال ساده

## 21.7 رابطه FinalizationRegistry و Garbage Collection

## 21.8 آیا Callback همیشه اجرا می‌شود؟

## 21.9 آیا زمان اجرای Callback قابل پیش‌بینی است؟

## 21.10 چرا نباید Logic اصلی برنامه را به FinalizationRegistry وابسته کرد؟

## 21.11 موارد استفاده مناسب

## 21.12 موارد استفاده نامناسب

بر اساس مستندات MDN صریحاً توضیح بده که اجرای Cleanup Callback زمان مشخص و تضمین‌شده‌ای ندارد و نباید برای Logic حیاتی برنامه استفاده شود.

---

# 22. آیا می‌توان Garbage Collection را دستی اجرا کرد؟

## 22.1 آیا JavaScript API عمومی برای اجرای GC دارد؟

## 22.2 چرا کنترل مستقیم GC در JavaScript وجود ندارد؟

## 22.3 --expose-gc در Node.js

## 22.4 global.gc()

## 22.5 کاربرد آن برای Debugging

## 22.6 آیا استفاده از global.gc() در Production مناسب است؟

## 22.7 تفاوت Debugging و Production

طبق مستندات معتبر توضیح بده که Node.js/V8 می‌تواند ابزارهایی برای Debugging و آزمایش GC ارائه دهد، اما این موضوع با کنترل عادی GC در زبان JavaScript متفاوت است.

---

# 23. بررسی Memory در Browser

## 23.1 Chrome DevTools چیست؟

## 23.2 Memory Panel

## 23.3 Heap Snapshot

## 23.4 گرفتن Heap Snapshot

## 23.5 بررسی Objectها

## 23.6 Retained Size

## 23.7 Shallow Size

## 23.8 Retainers

## 23.9 بررسی Reference Chain

## 23.10 مقایسه دو Heap Snapshot

## 23.11 Allocation Timeline

## 23.12 Allocation Sampling

## 23.13 Detached DOM Nodes

## 23.14 پیدا کردن Memory Leak

---

# 24. بررسی Memory در Node.js

## 24.1 process.memoryUsage()

## 24.2 heapUsed

## 24.3 heapTotal

## 24.4 rss

## 24.5 external

## 24.6 arrayBuffers

## 24.7 Node.js Inspector

## 24.8 --inspect

## 24.9 Heap Snapshot

## 24.10 --expose-gc

## 24.11 بررسی Memory Leak در Node.js

## 24.12 مثال عملی

---

# 25. Garbage Collection در Browser و Node.js

## 25.1 شباهت‌ها

## 25.2 تفاوت‌ها

## 25.3 نقش V8 در Node.js

## 25.4 نقش JavaScript Engine در Browser

## 25.5 آیا همه Browserها از V8 استفاده می‌کنند؟

## 25.6 آیا Garbage Collector همه JavaScript Engineها یکسان است؟

## 25.7 چرا نباید جزئیات V8 را به کل JavaScript نسبت داد؟

---

# 26. اشتباهات رایج

این قسمت را به‌صورت:

> ❌ تصور اشتباه
> ✅ واقعیت

بنویس.

حداقل موارد زیر را بررسی کن:

### 26.1 «JavaScript خودش حافظه را مدیریت می‌کند، پس Memory Leak نداریم.»

### 26.2 «هر Object بدون استفاده فوراً حذف می‌شود.»

### 26.3 «با null کردن یک متغیر، حافظه فوراً آزاد می‌شود.»

### 26.4 «Circular Reference همیشه Memory Leak است.»

### 26.5 «WeakMap فوراً حافظه را آزاد می‌کند.»

### 26.6 «WeakRef همیشه خیلی سریع undefined می‌شود.»

### 26.7 «FinalizationRegistry همیشه اجرا می‌شود.»

### 26.8 «می‌توان زمان GC را دقیق مشخص کرد.»

### 26.9 «مصرف زیاد RAM همیشه یعنی Memory Leak.»

### 26.10 «Garbage Collector همیشه باعث کندی برنامه می‌شود.»

### 26.11 «V8 همان JavaScript است.»

### 26.12 «تمام JavaScript Engineها دقیقاً یک Garbage Collector دارند.»

---

# 27. Best Practices

## 27.1 مدیریت صحیح Lifecycle

## 27.2 Cleanup کردن Event Listenerها

## 27.3 Cleanup کردن Timerها

## 27.4 مدیریت Cache

## 27.5 جلوگیری از Globalهای غیرضروری

## 27.6 جلوگیری از Referenceهای غیرضروری

## 27.7 استفاده صحیح از Map

## 27.8 استفاده صحیح از WeakMap

## 27.9 استفاده محتاطانه از WeakRef

## 27.10 استفاده محتاطانه از FinalizationRegistry

## 27.11 Profiling قبل از Optimization

## 27.12 جلوگیری از Premature Optimization

---

# 28. پروژه عملی

یک پروژه کوچک JavaScript طراحی کن که در آن عمداً یک Memory Leak ایجاد شود.

پروژه باید شامل موارد زیر باشد:

### مرحله 1

ایجاد Objectهای متعدد.

### مرحله 2

ذخیره Objectها در یک Array یا Map.

### مرحله 3

ایجاد Referenceهای اضافی.

### مرحله 4

ایجاد یک Memory Leak عمدی.

### مرحله 5

بررسی مصرف حافظه.

### مرحله 6

پیدا کردن علت Memory Leak.

### مرحله 7

اصلاح Memory Leak.

### مرحله 8

بررسی دوباره Memory.

### مرحله 9

مقایسه قبل و بعد.

برای پروژه:

* ساختار فایل‌ها را ارائه کن.
* کد کامل ارائه کن.
* نحوه اجرا را توضیح بده.
* نحوه بررسی در Chrome DevTools را توضیح بده.
* نحوه بررسی در Node.js را توضیح بده.
* توضیح بده چرا ممکن است نتیجه در هر اجرا دقیقاً یکسان نباشد.

---

# 29. تمرین‌های آموزشی

حداقل 10 تمرین طراحی کن که از ساده به سخت مرتب شده باشند.

تمرین‌ها باید موضوعات زیر را پوشش دهند:

* Reachability
* Reference
* Mark-and-Sweep
* Circular Reference
* Closure
* Event Listener
* Timer
* Map
* WeakMap
* WeakRef
* Memory Leak
* Heap Snapshot

برای هر تمرین:

* صورت سؤال
* هدف تمرین
* سطح سختی

را بنویس.

در انتها پاسخ یا راهنمای حل تمرین‌ها را ارائه کن.

---

# 30. خلاصه نهایی

در پایان آموزش یک بخش:

## Garbage Collector در 5 دقیقه

ایجاد کن و کل موضوع را بسیار ساده خلاصه کن.

سپس یک جدول مفهومی شامل موارد زیر ایجاد کن:

| مفهوم                | توضیح کوتاه |
| -------------------- | ----------- |
| Memory Management    | ...         |
| Stack                | ...         |
| Heap                 | ...         |
| Reference            | ...         |
| Reachability         | ...         |
| Garbage              | ...         |
| Garbage Collector    | ...         |
| Mark-and-Sweep       | ...         |
| Generational GC      | ...         |
| Memory Leak          | ...         |
| Map                  | ...         |
| WeakMap              | ...         |
| WeakSet              | ...         |
| WeakRef              | ...         |
| FinalizationRegistry | ...         |
| Heap Snapshot        | ...         |

---

# 31. نقشه یادگیری

در پایان مشخص کن برای فهم Garbage Collector چه مسیری را باید طی کنیم:

```text
JavaScript
   ↓
Memory
   ↓
Stack / Heap
   ↓
Reference
   ↓
Reachability
   ↓
Garbage
   ↓
Mark-and-Sweep
   ↓
Generational GC
   ↓
V8
   ↓
Memory Leak
   ↓
WeakMap / WeakSet
   ↓
WeakRef
   ↓
FinalizationRegistry
   ↓
Memory Profiling
   ↓
Performance
```

---

# 32. منابع

در انتهای آموزش بخشی با عنوان:

# منابع و مطالعه بیشتر

قرار بده.

منابع را ترجیحاً از منابع رسمی و معتبر انتخاب کن.

حداقل این منابع را بررسی کن:

1. **MDN – Memory Management**
2. **MDN – WeakMap**
3. **MDN – WeakSet**
4. **MDN – WeakRef**
5. **MDN – FinalizationRegistry**
6. **ECMAScript Specification**
7. **V8 Official Blog – Garbage Collection**
8. **V8 Official Documentation**
9. **Node.js Documentation – Memory**
10. **Chrome DevTools Documentation – Memory**

برای هر منبع:

* عنوان
* نام سایت
* لینک مستقیم
* توضیح کوتاه درباره اینکه این منبع چه چیزی را پوشش می‌دهد

را ارائه کن.

از لینک‌های ساختگی استفاده نکن.

---

# 33. استاندارد لینک‌دهی

در Table of Contents برای Headingهای اصلی لینک ایجاد کن.

مثلاً:

```markdown
## فهرست مطالب

- [1. مقدمه‌ای بر Garbage Collection](#1-مقدمه‌ای-بر-garbage-collection)
- [2. Memory Management](#2-memory-management)
- [3. Stack و Heap](#3-stack-و-heap)
- ...
```

لینک منابع نیز باید واقعی و قابل کلیک باشند.

اگر URL یک منبع تغییر کرده یا معتبر بودن آن مشخص نیست، آن URL را حدس نزن و از منبع رسمی دیگری استفاده کن.

---

# 34. استاندارد کدنویسی

تمام کدهای JavaScript را با:

```javascript
```

قرار بده.

کدها باید:

* قابل اجرا باشند.
* ساده باشند.
* نام‌گذاری مناسب داشته باشند.
* برای مبتدی قابل فهم باشند.
* در صورت نیاز Comment داشته باشند.

از مثال‌های پیچیده در بخش‌های ابتدایی خودداری کن.

---

# 35. استاندارد نهایی Repository

خروجی را طوری بنویس که بتوانم تقریباً بدون تغییر در یک فایل:

```text
Garbage-Collector.md
```

داخل GitHub Repository قرار دهم.

ساختار نهایی باید شامل:

```text
Title
↓
Introduction
↓
Table of Contents
↓
Basic Concepts
↓
Memory Management
↓
Stack / Heap
↓
Reachability
↓
Mark-and-Sweep
↓
Reference Counting
↓
Generational GC
↓
V8
↓
Memory Leak
↓
WeakMap / WeakSet
↓
WeakRef
↓
FinalizationRegistry
↓
Browser DevTools
↓
Node.js Memory
↓
Performance
↓
Best Practices
↓
Practical Project
↓
Exercises
↓
Summary
↓
Learning Roadmap
↓
References
```

باشد.

مهم‌ترین اصل این است که **آموزش برای مبتدی قابل فهم باشد، اما در انتها از نظر فنی سطح آن به مباحث پیشرفته Garbage Collection در JavaScript برسد.**

در تمام آموزش بین موارد زیر تفاوت دقیق ایجاد کن:

```text
JavaScript Language
JavaScript Engine
V8
Memory Management
Garbage Collection
Garbage
Reachability
Memory Leak
Reference
Strong Reference
Weak Reference
```

و هیچ‌کدام را به‌عنوان مترادف یکدیگر معرفی نکن.


### ASSISTANT
# Garbage Collector در JavaScript: از مقدماتی تا پیشرفته

این آموزش جامع، مفاهیم مدیریت حافظه و Garbage Collection را از سطح کاملاً مبتدی تا مباحث پیشرفته موتورهای مدرن مانند V8 پوشش می‌دهد. این محتوا برای قرار گرفتن مستقیم در یک GitHub Repository طراحی شده است.

---

## فهرست مطالب

- [1. مقدمه‌ای بر Garbage Collection](#1-مقدمه‌ای-بر-garbage-collection)
- [2. Memory Management در JavaScript](#2-memory-management-در-javascript)
- [3. Stack و Heap](#3-stack-و-heap)
- [4. Reachability](#4-reachability)
- [5. Mark-and-Sweep](#5-mark-and-sweep)
- [6. Reference Counting](#6-reference-counting)
- [7. Circular Reference](#7-circular-reference)
- [8. Garbage Collector چگونه تصمیم می‌گیرد؟](#8-garbage-collector-چگونه-تصمیم-می‌گیرد)
- [9. Generational Garbage Collection](#9-generational-garbage-collection)
- [10. Garbage Collection در V8](#10-garbage-collection-در-v8)
- [11. انواع تکنیک‌های Garbage Collection](#11-انواع-تکنیک‌های-garbage-collection)
- [12. Garbage Collection و Performance](#12-garbage-collection-و-performance)
- [13. Memory Leak](#13-memory-leak)
- [14. دلایل رایج Memory Leak](#14-دلایل-رایج-memory-leak)
- [15. Closure و Garbage Collection](#15-closure-و-garbage-collection)
- [16. Event Listener و Garbage Collection](#16-event-listener-و-garbage-collection)
- [17. Timerها و Garbage Collection](#17-timerها-و-garbage-collection)
- [18. Map و Set](#18-map-و-set)
- [19. WeakMap و WeakSet](#19-weakmap-و-weakset)
- [20. WeakRef](#20-weakref)
- [21. FinalizationRegistry](#21-finalizationregistry)
- [22. آیا می‌توان Garbage Collection را دستی اجرا کرد؟](#22-آیا-میتوان-garbage-collection-را-دستی-اجرا-کرد)
- [23. بررسی Memory در Browser](#23-بررسی-memory-در-browser)
- [24. بررسی Memory در Node.js](#24-بررسی-memory-در-nodejs)
- [25. Garbage Collection در Browser و Node.js](#25-garbage-collection-در-browser-و-nodejs)
- [26. اشتباهات رایج](#26-اشتباهات-رایج)
- [27. Best Practices](#27-best-practices)
- [28. پروژه عملی](#28-پروژه-عملی)
- [29. تمرین‌های آموزشی](#29-تمرین‌های-آموزشی)
- [30. خلاصه نهایی](#30-خلاصه-نهایی)
- [31. نقشه یادگیری](#31-نقشه-یادگیری)
- [32. منابع و مطالعه بیشتر](#32-منابع-و-مطالعه-بیشتر)

---

## 1. مقدمه‌ای بر Garbage Collection

### 1.1 Garbage Collector چیست؟
**زبان ساده:** یک نظافتچی خودکار که وسایل اضافی و بی‌استفاده را از اتاق (حافظه) جمع می‌کند.
**تعریف فنی:** بخشی از JavaScript Engine که وظیفه شناسایی و آزادسازی حافظه‌ای که دیگر در برنامه استفاده نمی‌شود را بر عهده دارد.

### 1.2 Garbage چیست؟
**زبان ساده:** وسایلی که دیگر به آن‌ها نیاز ندارید و فقط جا اشغال کرده‌اند.
**تعریف فنی:** Objectها یا داده‌هایی که در Heap ذخیره شده‌اند اما دیگر هیچ Reference (ارجاعی) از سمت Rootها به آن‌ها وجود ندارد (Unreachable هستند).

### 1.3 Garbage Collection چیست؟
فرآیند خودکار شناسایی Garbageها و آزادسازی فضای اشغال‌شده توسط آن‌ها برای استفاده مجدد.

### 1.4 چرا JavaScript به Garbage Collector نیاز دارد؟
برای جلوگیری از پر شدن حافظه (Memory) و جلوگیری از خطاهایی مانند `Out of Memory`. بدون GC، برنامه‌نویس باید دائماً حافظه را خالی می‌کرد که خطای انسانی را افزایش می‌داد.

### 1.5 آیا JavaScript خودش حافظه را مدیریت می‌کند؟
بله. JavaScript از **Automatic Memory Management** استفاده می‌کند. برنامه‌نویس نیازی به `malloc` یا `free` ندارد.

### 1.6 آیا برنامه‌نویس JavaScript اصلاً لازم نیست به Memory Management فکر کند؟
خیر! اگرچه GC حافظه را مدیریت می‌کند، اما برنامه‌نویس باید مراقب **Memory Leak** (نشت حافظه) باشد. اگر Referenceای به یک Object بی‌استفاده باقی بماند، GC نمی‌تواند آن را پاک کند.

### 1.7 تفاوت Memory Management در زبان‌های سطح پایین و JavaScript
در C/C++ برنامه‌نویس به‌صورت دستی (Manual) حافظه را Allocate و Deallocate می‌کند. در JavaScript این کار خودکار (Automatic) است.

### 1.8 تفاوت مدیریت حافظه در C/C++ و JavaScript
- **C/C++:** کنترل کامل، سرعت بالا، احتمال خطای انسانی (Dangling Pointers, Memory Leaks).
- **JavaScript:** کنترل کمتر، ایمن‌تر، احتمال Memory Leak منطقی (نگه‌داشتن ناخواسته Reference).

### 1.9 مزایا و محدودیت‌های Garbage Collection
- **مزایا:** کاهش باگ‌های حافظه، توسعه سریع‌تر، ایمنی بیشتر.
- **محدودیت‌ها:** مصرف CPU برای اجرای GC، عدم قطعیت در زمان آزادسازی حافظه (Non-deterministic).

> **خلاصه بخش 1:** GC یک مکانیزم خودکار برای آزادسازی حافظه است. JavaScript این کار را انجام می‌دهد، اما برنامه‌نویس همچنان باید مراقب باشد تا ناخواسته Referenceها را زنده نگه ندارد.

---

## 2. Memory Management در JavaScript

### 2.1 Memory چیست؟
فضایی در سخت‌افزار (RAM) که داده‌ها و دستورالعمل‌ها هنگام اجرا در آن قرار می‌گیرند.

### 2.2 Memory Allocation چیست؟
درخواست فضا از سیستم‌عامل برای ذخیره یک متغیر یا Object.

### 2.3 Memory Usage چیست؟
میزان رمی که برنامه در حال حاضر اشغال کرده است.

### 2.4 Memory Deallocation چیست؟
آزاد کردن فضای اشغال‌شده تا سیستم‌عامل بتواند آن را به برنامه‌های دیگر بدهد.

### 2.5 چرخه حیات حافظه
1. **Allocate:** درخواست حافظه.
2. **Use:** استفاده از حافظه (خواندن/نوشتن).
3. **Release:** آزادسازی حافظه (در JS خودکار انجام می‌شود).

### 2.6 JavaScript چگونه حافظه اختصاص می‌دهد؟
هنگام تعریف متغیر (`let a = 10`) یا ساخت Object (`const obj = {}`)، موتور JS به‌صورت خودکار حافظه لازم را از Heap یا Stack اختصاص می‌دهد.

### 2.7 JavaScript چگونه حافظه را آزاد می‌کند؟
وقتی GC تشخیص دهد یک Object دیگر **Reachable** (قابل دسترس) نیست، آن را از بین می‌برد.

### 2.8 Automatic Memory Management چیست؟
سیستمی که در آن Allocate و Release بدون دخالت مستقیم برنامه‌نویس انجام می‌شود.

### 2.9 تفاوت Manual و Automatic
در Manual (مثل C)، شما `free(ptr)` را صدا می‌زنید. در Automatic (مثل JS)، موتور JS بر اساس Reachability تصمیم می‌گیرد.

> **خلاصه بخش 2:** چرخه حافظه شامل Allocate، Use و Release است. در JS، دو مرحله اول توسط برنامه‌نویس و مرحله سوم توسط GC انجام می‌شود.

---

## 3. Stack و Heap

### 3.1 Stack چیست؟
حافظه‌ای ساختاریافته (LIFO - Last In First Out) برای ذخیره داده‌های ثابت و فراخوانی توابع. مثل یک دسته بشقاب.

### 3.2 Heap چیست؟
حافظه‌ای بزرگ و نامنظم برای ذخیره Objectها و داده‌های پویا (Dynamic). مثل یک انبار بزرگ.

### 3.3 تفاوت Stack و Heap
- **Stack:** سریع، اندازه ثابت، داده‌های Primitive و Referenceها.
- **Heap:** کندتر، اندازه پویا، Objectها و Arrayها.

### 3.4 نقش Stack در اجرای JavaScript
نگهداری **Execution Context** (متغیرهای محلی، پارامترها) و فراخوانی توابع (Call Stack).

### 3.5 نقش Heap در نگهداری Objectها
تمام Objectها، Arrayها و Functionها در Heap ساخته می‌شوند.

### 3.6 Primitiveها و Memory
داده‌هایی مثل `Number`, `String`, `Boolean` به دلیل اندازه ثابت، معمولاً در Stack ذخیره می‌شوند (مگر در شرایط خاص).

### 3.7 Objectها و Memory
همیشه در Heap ذخیره می‌شوند. متغیر در Stack فقط **Reference** (آدرس) آن‌ها را نگه می‌دارد.

### 3.8 Arrayها و Memory
Arrayها Object هستند، پس در Heap قرار می‌گیرند.

### 3.9 Functionها و Memory
توابع نیز Object هستند و در Heap ذخیره می‌شوند.

### 3.10 Reference چیست؟
اشاره‌گری که آدرس یک Object در Heap را در خود نگه می‌دارد. مثل آدرس یک خانه روی یک کاغذ.

### 3.11 Strong Reference چیست؟
یک Reference معمولی که تا زمانی که وجود دارد، GC اجازه پاک کردن Object را نمی‌دهد. (مثل `let a = {}`).

> **خلاصه بخش 3:** Stack برای داده‌های سریع و کوچک (Primitive و Referenceها) و Heap برای Objectهای پویا استفاده می‌شود. متغیرهای شما در Stack، آدرس Objectهای Heap را نگه می‌دارند.

---

## 4. Reachability

### 4.1 Reachable چیست؟
Objectی که از طریق یک مسیر معتبر از **Root** قابل دسترسی است.

### 4.2 Unreachable چیست؟
Objectی که هیچ مسیر دسترسی از Root به آن وجود ندارد. این Objectها **Garbage** هستند.

### 4.3 چرا Reachability برای GC مهم است؟
الگوریتم اصلی GC در JS (Mark-and-Sweep) صرفاً بر اساس Reachability تصمیم به حذف Object می‌گیرد.

### 4.4 Root چیست؟
نقاط شروعی که همیشه به‌عنوان "پایه" در نظر گرفته می‌شوند.

### 4.5 Garbage Collection Root چیست؟
مجموعه‌ای از Referenceهای پایه شامل:
1. Global Object (در Browser: `window`، در Node.js: `global`).
2. متغیرهای محلی و پارامترهای توابعی که در حال حاضر در Call Stack هستند.
3. Closureهای فعال.

### 4.6 Global Object به‌عنوان Root
هر چیزی که به `window` یا `global` متصل باشد (مثل متغیرهای سراسری)، یک Root محسوب می‌شود.

### 4.7 Reference Graph چیست؟
یک نمودار درختی که نشان می‌دهد Objectها چگونه به یکدیگر و در نهایت به Rootها متصل هستند.

### 4.8 مسیر دسترسی به Objectها
از Root شروع می‌شود، به Referenceها می‌رسد و آن‌ها را دنبال می‌کند تا به Objectهای نهایی برسد.

### 4.9 چه زمانی یک Object قابل جمع‌آوری می‌شود؟
زمانی که از تمام Rootها قطع ارتباط کند (Unreachable شود).

### 4.10 تفاوت `Object is unused` و `Object is unreachable`
- **Unused:** برنامه‌نویس می‌داند که Object دیگر به کار نمی‌آید (مفهوم منطقی).
- **Unreachable:** GC تشخیص می‌دهد که هیچ Referenceای به آن وجود ندارد (مفهوم فنی).
*مثال:*
```javascript
let user = { name: "Ali" };
user = null; // حالا Object قبلی unused و unreachable است.
```
اما اگر:
```javascript
let user = { name: "Ali" };
let admin = user;
user = null; // Object هنوز unused نیست (از نظر admin)، و unreachable هم نیست.
```

> **خلاصه بخش 4:** مفهوم کلیدی GC، **Reachability** است. اگر Objectی از طریق Rootها قابل دسترسی نباشد، Garbage محسوب شده و حذف می‌شود.

---

## 5. Mark-and-Sweep

### 5.1 Mark-and-Sweep چیست؟
الگوریتم اصلی و پایه‌ای Garbage Collection در JavaScript مدرن.

### 5.2 چرا Mark-and-Sweep به وجود آمد؟
برای حل مشکل **Circular Reference** که در الگوریتم‌های قدیمی‌تر (مثل Reference Counting) وجود داشت.

### 5.3 مرحله Mark
GC از Rootها شروع می‌کند و تمام Objectهای متصل به آن‌ها را بازدید کرده و علامت (Mark) می‌زند که "این‌ها زنده هستند".

### 5.4 مرحله Sweep
GC تمام حافظه Heap را می‌گردد و هر Objectی که علامت نخورده باشد را حذف و حافظه آن را آزاد می‌کند.

### 5.5 پیدا کردن Objectهای Reachable
با شروع از Root و دنبال کردن Referenceها (Traversal).

### 5.6 پیدا کردن Objectهای Unreachable
هر Objectی در Heap که در مرحله Mark دیده نشود، Unreachable است.

### 5.7 مثال ساده Mark-and-Sweep
```javascript
let user = { name: "Ali" };
user = null;
// مرحله Mark: GC می‌بیند user دیگر به Object اشاره نمی‌کند.
// مرحله Sweep: Object { name: "Ali" } حذف می‌شود.
```

### 5.8 مثال با چند Object
```javascript
let a = { value: 1 };
let b = a;
a = null;
// چون b هنوز به Object اشاره می‌کند، در مرحله Mark علامت می‌خورد و پاک نمی‌شود.
```

### 5.9 مثال با Reference Chain
```javascript
let root = { child: { grandChild: { value: 10 } } };
root = null;
// کل زنجیره از root قطع می‌شود و همه در مرحله Sweep پاک می‌شوند.
```

### 5.10 مثال با Circular Reference
```javascript
let a = {};
let b = {};
a.ref = b;
b.ref = a;
a = null;
b = null;
```

### 5.11 چرا Circular Reference در Mark-and-Sweep مشکل اصلی نیست؟
چون GC از Root شروع می‌کند. چون `a` و `b` هر دو `null` شدند، هیچ Rootای به آن‌ها متصل نیست. GC آن‌ها را Mark نمی‌کند و در Sweep پاک می‌شوند.

> **خلاصه بخش 5:** الگوریتم Mark-and-Sweep با شروع از Rootها، Objectهای زنده را علامت‌گذاری کرده و بقیه را پاک می‌کند. این الگوریتم مشکل Circular Reference را حل می‌کند.

---

## 6. Reference Counting

### 6.1 Reference Counting چیست؟
الگوریتمی قدیمی که تعداد Referenceهای هر Object را می‌شمارد. اگر شمارنده به صفر برسد، Object حذف می‌شود.

### 6.2 چگونه کار می‌کند؟
هر بار Referenceای ساخته می‌شود، شمارنده +1 و هر بار Referenceای از بین می‌رود، شمارنده -1 می‌شود.

### 6.3 مثال ساده Reference Counting
```javascript
let a = { value: 1 }; // Count = 1
let b = a;            // Count = 2
a = null;             // Count = 1
b = null;             // Count = 0 -> حذف می‌شود.
```

### 6.4 مشکل Circular Reference
اگر دو Object به هم Reference بدهند، شمارنده هرگز به صفر نمی‌رسد، حتی اگر از بیرون قطع شوند.

### 6.5 مثال Circular Reference
```javascript
let a = {};
let b = {};
a.ref = b; // Count b = 2
b.ref = a; // Count a = 2
// حتی اگر a و b را null کنیم، چون به هم اشاره دارند، Count صفر نمی‌شود.
```

### 6.6 تفاوت Reference Counting و Mark-and-Sweep
Reference Counting بلادرنگ (Instant) است اما مشکل Cycle دارد. Mark-and-Sweep نیاز به مکث (Pause) دارد اما Cycleها را حل می‌کند.

### 6.7 آیا موتورهای مدرن از Reference Counting استفاده می‌کنند؟
خیر. موتورهای مدرن JS (مثل V8) از Mark-and-Sweep و الگوریتم‌های نسلی (Generational) استفاده می‌کنند. Reference Counting بیشتر در زبان‌هایی مثل Python (به‌عنوان مکمل) یا مرورگرهای بسیار قدیمی (IE6) استفاده می‌شد.

> **خلاصه بخش 6:** Reference Counting به دلیل مشکل Circular Reference در JS مدرن منسوخ شده و جای خود را به Mark-and-Sweep داده است.

---

## 7. Circular Reference

### 7.1 Circular Reference چیست؟
حالتی که دو یا چند Object به یکدیگر Reference می‌دهند و یک چرخه می‌سازند.

### 7.2 مثال ساده
```javascript
let obj = {};
obj.self = obj;
```

### 7.3 Circular Reference بین دو Object
```javascript
let a = {}, b = {};
a.peer = b;
b.peer = a;
```

### 7.4 Circular Reference بین چند Object
یک زنجیره سه‌تایی یا بیشتر که به نقطه شروع خود برمی‌گردد.

### 7.5 آیا Circular Reference همیشه Memory Leak ایجاد می‌کند؟
خیر! در موتورهای مدرن که از Mark-and-Sweep استفاده می‌کنند، اگر چرخه از Rootها قطع شود، GC آن را پیدا کرده و حذف می‌کند.

### 7.6 چرا Mark-and-Sweep می‌تواند Cycleها را مدیریت کند؟
چون الگوریتم از بیرون (Root) به داخل می‌آید. اگر هیچ Rootای به چرخه متصل نباشد، کل چرخه نادیده گرفته شده و پاک می‌شود.

### 7.7 تفاوت Circular Reference و Memory Leak
Circular Reference فقط یک ساختار داده است. Memory Leak زمانی رخ می‌دهد که این ساختار (یا هر Object دیگر) به یک Root متصل بماند و برنامه‌نویس از آن بی‌خبر باشد.

> **خلاصه بخش 7:** Circular Reference به خودی خود بد نیست و در JS مدرن باعث Memory Leak نمی‌شود، مگر اینکه به Rootها متصل بماند.

---

## 8. Garbage Collector چگونه تصمیم می‌گیرد؟

### 8.1 آیا GC می‌فهمد یک Object دیگر استفاده نمی‌شود؟
خیر. GC فقط می‌فهمد آیا Object **Reachable** است یا خیر. او از "منطق برنامه" خبر ندارد.

### 8.2 آیا GC دقیقاً می‌داند چه زمانی Object دیگر لازم نیست؟
خیر. تا زمانی که Referenceای وجود داشته باشد، GC فرض می‌کند Object لازم است.

### 8.3 Reachability چگونه تعیین می‌شود؟
با الگوریتم Mark-and-Sweep و شروع از Rootها.

### 8.4 Rootها
شامل Global Object، متغیرهای محلی فعال، و Closureها.

### 8.5 Reference Graph
GC یک گراف از تمام Objectها می‌سازد و آن‌هایی که به Root متصل‌اند را نگه می‌دارد.

### 8.6 Unreachable Objects
Objectهایی که در گراف، مسیری به Root ندارند.

### 8.7 آیا زمان Garbage Collection قابل پیش‌بینی است؟
**خیر.** زمان اجرای GC توسط موتور JS (مثل V8) بر اساس فشار حافظه (Memory Pressure) و الگوریتم‌های داخلی تعیین می‌شود. شما نمی‌توانید بگویید "همین الان GC را اجرا کن".

### 8.8 چرا JavaScript اجازه کنترل کامل GC را نمی‌دهد؟
برای حفظ انتزاع (Abstraction) و جلوگیری از خطاهای پیچیده برنامه‌نویس. همچنین به موتور اجازه می‌دهد GC را در بهینه‌ترین زمان ممکن اجرا کند.

> **خلاصه بخش 8:** GC فقط بر اساس Reachability تصمیم می‌گیرد و زمان اجرای آن قطعی و قابل کنترل توسط برنامه‌نویس نیست.

---

## 9. Generational Garbage Collection

### 9.1 Generational GC چیست؟
تکنیکی که Heap را بر اساس "سن" Objectها به بخش‌های مختلف تقسیم می‌کند تا GC سریع‌تر اجرا شود.

### 9.2 چرا Objectها به Generation تقسیم می‌شوند؟
چون بررسی کل Heap زمان‌بر است. با تقسیم آن، GC می‌تواند فقط بخش‌هایی که احتمال تغییر در آن‌ها بیشتر است را بررسی کند.

### 9.3 Generational Hypothesis چیست؟
یک فرضیه علمی که می‌گوید: **"اکثر Objectها خیلی زود می‌میرند (Weak Generational Hypothesis)"** و **"Objectهایی که زنده می‌مانند، تمایل دارند تا مدت طولانی زنده بمانند"**.

### 9.4 Young Generation
بخشی از Heap که Objectهای جدید در آن ساخته می‌شوند. GC در این بخش بسیار سریع و مکرر اجرا می‌شود.

### 9.5 Old Generation
بخشی که Objectهای زنده‌مانده از Young Generation به آن منتقل می‌شوند. GC در این بخش کندتر و کمتر اجرا می‌شود.

### 9.6 Nursery چیست؟
نام دیگر Young Generation در برخی موتورها (مثل V8).

### 9.7 Intermediate Generation
در برخی موتورها (مثل V8 قدیم یا Java)، یک بخش میانی بین Young و Old وجود دارد.

### 9.8 Promotion چیست؟
فرآیند انتقال یک Object از Young Generation به Old Generation پس از چندین بار جان‌سالمی در GCها.

### 9.9 Minor GC چیست؟
GCای که فقط Young Generation را تمیز می‌کند. بسیار سریع است.

### 9.10 Major GC (Full GC)
GCای که کل Heap (Young و Old) را بررسی می‌کند. کندتر است و Pause بیشتری ایجاد می‌کند.

### 9.11 چرا Objectهای کوتاه‌عمر اهمیت دارند؟
چون اکثر Objectها (مثل متغیرهای موقت در توابع) کوتاه‌عمرند. GC آن‌ها را سریعاً در Young Gen پاک می‌کند و نیازی به انتقال به Old Gen نیست.

### 9.12 مثال عملی از Objectهای کوتاه‌عمر
```javascript
function calculate() {
  let temp = { data: [] }; // این Object کوتاه‌عمر است و در Young Gen پاک می‌شود.
  return temp.data.length;
}
```

> **خلاصه بخش 9:** Generational GC با فرض اینکه اکثر Objectها زود می‌میرند، Heap را به Young و Old تقسیم می‌کند تا Performance را به شدت افزایش دهد.

---

## 10. Garbage Collection در V8

*(توجه: جزئیات داخلی V8 ممکن است با نسخه‌های مختلف تغییر کند. این بخش بر اساس مستندات رسمی V8 تا سال 2026 است).*

### 10.1 V8 چیست؟
موتور متن‌باز JavaScript که توسط گوگل توسعه یافته و در Chrome و Node.js استفاده می‌شود.

### 10.2 V8 چه ارتباطی با JavaScript دارد؟
V8 کد JS را می‌خواند و به کد ماشین (Machine Code) تبدیل می‌کند.

### 10.3 آیا V8 خود JavaScript است؟
خیر. V8 یک **JavaScript Engine** است. JS زبان است، V8 مجری آن.

### 10.4 JavaScript Engine چیست؟
نرم‌افزاری که کد JS را Parses، Compile و Execute می‌کند.

### 10.5 Heap در V8
حافظه‌ای که V8 برای Objectها اختصاص می‌دهد و به Young و Old Generation تقسیم شده است.

### 10.6 Young Generation در V8
به دو بخش **New Space** تقسیم می‌شود (From Space و To Space) برای الگوریتم Copying.

### 10.7 Old Generation در V8
بخش بزرگتر برای Objectهای بلندعمر.

### 10.8 Scavenger چیست؟
الگوریتم GC مخصوص Young Generation در V8 (بر اساس Cheney's algorithm) که بسیار سریع است و Objectهای زنده را از From به To کپی می‌کند.

### 10.9 Mark-Sweep
الگوریتمی برای Old Generation که Objectهای زنده را علامت می‌زند.

### 10.10 Mark-Compact
ادامه Mark-Sweep که در آن Objectهای زنده در انتهای Heap فشرده (Compact) می‌شوند تا Fragmentation از بین برود.

### 10.11 Object Promotion
وقتی یک Object در Young Gen چندین بار (مثلاً در V8 معمولاً ۱ بار یا بر اساس سن) زنده بماند، به Old Gen منتقل می‌شود.

### 10.12 Object Moving
در Scavenger، Objectهای زنده کپی می‌شوند. این کار باعث Defragmentation طبیعی Young Gen می‌شود.

### 10.13 Compaction
فرآیند فشرده‌سازی Old Gen برای رفع Fragmentation.

### 10.14 Fragmentation
وقتی حافظه آزاد به صورت تکه‌تکه (Pockets) پراکنده شود و نتوان یک Block بزرگ را Allocate کرد.

### 10.15 Write Barrier
تکنیکی در V8 که وقتی یک Object در Old Gen به Objectی در Young Gen Reference می‌دهد، آن را در یک لیست خاص (Remembered Set) ثبت می‌کند تا Minor GC بتواند آن را پیدا کند.

### 10.16 Remembered Set
لیستی از Referenceهای Old-to-Young که توسط Write Barrier پر می‌شود.

> **خلاصه بخش 10:** V8 از یک GC نسلی پیشرفته استفاده می‌کند. Scavenger برای Young Gen (سریع) و Mark-Compact برای Old Gen (فشرده‌سازی). جزئیات دقیق ممکن است در نسخه‌های جدیدتر V8 (مثل پروژه Orinoco) تغییر کند.

---

## 11. انواع تکنیک‌های Garbage Collection

### 11.1 Stop-the-World
- **تعریف:** اجرای برنامه متوقف می‌شود تا GC کار کند.
- **دلیل:** سادگی و جلوگیری از تغییرات همزمان در Heap.
- **مزایا:** پیاده‌سازی ساده.
- **معایب:** ایجاد Latency (مکث) در برنامه.
- **ارتباط با Performance:** باعث Jank در UI می‌شود.

### 11.2 Incremental Garbage Collection
- **تعریف:** GC کار خود را به تکه‌های کوچک تقسیم کرده و بین اجرای کد برنامه انجام می‌دهد.
- **مزایا:** کاهش Pause Time.
- **معایب:** پیچیدگی بالاتر، سربار (Overhead) بیشتر.

### 11.3 Concurrent Garbage Collection
- **تعریف:** GC همزمان با اجرای برنامه (روی Threadهای دیگر) کار می‌کند.
- **مزایا:** تقریباً بدون مکث.
- **معایب:** نیاز به هماهنگی پیچیده (مثل Write Barrier).

### 11.4 Parallel Garbage Collection
- **تعریف:** استفاده از چند Thread برای اجرای GC.
- **مزایا:** سرعت بالاتر GC.

### 11.5 Compaction
- **تعریف:** جابجایی Objectهای زنده برای پر کردن حفره‌های حافظه.
- **مزایا:** Allocation سریع‌تر در آینده.
- **معایب:** هزینه CPU برای جابجایی و آپدیت Referenceها.

### 11.6 Copying Collector
- **تعریف:** کپی کردن Objectهای زنده به یک فضای جدید و دور ریختن فضای قدیمی.
- **مزایا:** رفع کامل Fragmentation.
- **معایب:** نیاز به ۲ برابر فضا.

### 11.7 Generational Collector
- **تعریف:** تقسیم Heap بر اساس سن Objectها (توضیح داده شد).

### 11.8 تفاوت این تکنیک‌ها
این تکنیک‌ها mutually exclusive نیستند. V8 مدرن ترکیبی از **Generational**, **Concurrent**, **Parallel**, **Mark-Compact** و **Copying** (برای Young Gen) است.

> **خلاصه بخش 11:** موتورهای مدرن از ترکیب تکنیک‌ها برای به حداقل رساندن Pause و به حداکثر رساندن Throughput استفاده می‌کنند.

---

## 12. Garbage Collection و Performance

### 12.1 GC چگونه روی Performance تأثیر می‌گذارد؟
GC نیاز به CPU دارد و در زمان اجرا (Pause) برنامه را متوقف می‌کند.

### 12.2 GC Pause چیست؟
مدت زمانی که برنامه به دلیل اجرای GC متوقف می‌شود.

### 12.3 GC Pressure چیست؟
فشاری که نرخ بالای Allocation به GC وارد می‌کند و باعث اجرای مکرر آن می‌شود.

### 12.4 Allocation زیاد چیست؟
ساختن Objectهای موقت و بی‌شمار در یک حلقه یا تابع.

### 12.5 چرا Allocation زیاد باعث GC بیشتر می‌شود؟
چون Young Generation سریع پر می‌شود و موتور مجبور به اجرای Minor GC می‌شود.

### 12.6 آیا ایجاد Object زیاد همیشه بد است؟
خیر. در JS مدرن، ساخت Object کوتاه‌عمر بسیار بهینه است. GC برای این کار طراحی شده است.

### 12.7 Objectهای کوتاه‌عمر
در Young Gen ساخته و سریع پاک می‌شوند. هزینه بسیار کمی دارند.

### 12.8 Objectهای بلندعمر
به Old Gen می‌روند. Major GC را تحریک می‌کنند که پرهزینه است.

### 12.9 Memory Pressure
وقتی برنامه به سقف حافظه نزدیک می‌شود و GC مجبور به تلاش بیشتر برای آزادسازی فضا می‌شود.

### 12.10 رابطه Memory و CPU
استفاده بیشتر از Memory (با Objectهای کوتاه‌عمر) می‌تواند CPU را درگیر GC کند. گاهی Object Pooling (استفاده مجدد) بهتر است، اما در JS مدرن Premature Optimization محسوب می‌شود.

### 12.11 رابطه Garbage Collection و Latency
GC Pause مستقیماً Latency را افزایش می‌دهد. در بازی‌ها یا سرورهای Real-time، این موضوع حیاتی است.

> **خلاصه بخش 12:** GC برای Performance حیاتی است اما Pause ایجاد می‌کند. ساخت Object کوتاه‌عمر در JS مدرن بهینه است، اما Allocation بی‌رویه باعث GC Pressure می‌شود.

---

## 13. Memory Leak

### 13.1 Memory Leak چیست؟
وقتی برنامه‌نویس ناخواسته Referenceای به یک Object بی‌استفاده نگه می‌دارد و GC نمی‌تواند آن را پاک کند.

### 13.2 چرا Memory Leak در JavaScript امکان‌پذیر است؟
چون GC فقط Unreachableها را پاک می‌کند. اگر Objectی Reachable باشد اما "منطقی" دیگر لازم نباشد، GC آن را پاک نمی‌کند.

### 13.3 آیا GC می‌تواند تمام Memory Leakها را برطرف کند؟
خیر. GC فقط نشت‌های فیزیکی (Physical Leaks) را حل می‌کند، نه نشت‌های منطقی (Logical Leaks).

### 13.4 تفاوت Garbage، Memory Leak و High Memory Usage
- **Garbage:** Objectهای Unreachable (GC آن‌ها را پاک می‌کند).
- **Memory Leak:** Objectهای Reachable اما بی‌استفاده (رشد مداوم حافظه).
- **High Memory Usage:** مصرف بالای حافظه که ممکن است کاملاً طبیعی باشد (مثل Cacheهای بزرگ).

### 13.5 نشانه‌های Memory Leak
رشد مداوم و بدون بازگشت خط `heapUsed` در طول زمان.

### 13.6 رشد دائمی Heap
اگر نمودار مصرف حافظه پس از هر GC بالاتر از قبل برود، Leak دارید.

### 13.7 Memory Leak در برنامه‌های Long-Running
در سرورهای Node.js یا SPAهای Browser، Leakها در درازمدت باعث Crash می‌شوند.

> **خلاصه بخش 13:** Memory Leak زمانی رخ می‌دهد که Referenceهای ناخواسته باعث Reachable ماندن Objectهای بی‌استفاده شوند. GC نمی‌تواند این مشکل منطقی را حل کند.

---

## 14. دلایل رایج Memory Leak

### 14.1 Global Variables
```javascript
// ❌ Leak
function leak() { globalVar = "I am global"; } 
// ✅ Fix
function noLeak() { let localVar = "I am local"; }
```

### 14.2 Accidental Globals
```javascript
// ❌ Leak (فراموش کردن let/const)
function createLeak() { temp = "data"; } 
```

### 14.3 Event Listenerها
```javascript
// ❌ Leak
element.addEventListener('click', () => { /* ... */ });
// ✅ Fix
const handler = () => { /* ... */ };
element.addEventListener('click', handler);
// بعداً: element.removeEventListener('click', handler);
```

### 14.4 setInterval
```javascript
// ❌ Leak
setInterval(() => { /* کار با یک Object بزرگ */ }, 1000);
// ✅ Fix
const id = setInterval(...);
clearInterval(id);
```

### 14.5 setTimeout
اگر `setTimeout` به یک Object بزرگ Reference بدهد و قبل از اجرا Cancel نشود، Object زنده می‌ماند.

### 14.6 Closure
```javascript
// ❌ Leak
function outer() {
  let bigData = new Array(1000000);
  return function inner() { console.log("Hi"); } // bigData در Closure زنده می‌ماند
}
```

### 14.7 Cacheهای بدون محدودیت
```javascript
const cache = new Map();
// ❌ Leak: cache هرگز خالی نمی‌شود.
// ✅ Fix: استفاده از WeakMap یا محدود کردن اندازه cache.
```

### 14.8 Arrayهای بزرگ
`push` کردن مداوم به یک Array سراسری بدون `pop` یا `splice`.

### 14.9 Mapهای بزرگ
مشابه Array، اگر Keyها پاک نشوند، Map رشد می‌کند.

### 14.10 DOM Referenceها
ذخیره یک Element در یک متغیر JS حتی پس از حذف از DOM.

### 14.11 Detached DOM Nodes
```javascript
let ref;
function create() {
  let div = document.createElement('div');
  ref = div; // ❌ Leak
  // div به DOM اضافه نمی‌شود اما در ref زنده است.
}
```

### 14.12 Subscriptionها
مشترک شدن در RxJS یا EventEmitter و فراموش کردن `unsubscribe`.

### 14.13 Observerها
مشابه Subscriptionها.

### 14.14 Promiseها و عملیات Async طولانی
نگه‌داشتن Resolve/Reject در یک حلقه بی‌پایان یا ذخیره داده‌های بزرگ در `.then()`.

> **خلاصه بخش 14:** شایع‌ترین دلایل Leak شامل Globalها، Event Listenerهای پاک‌نشده، Timerها، Closureها و Cacheهای بدون محدودیت هستند.

---

## 15. Closure و Garbage Collection

### 15.1 Closure چیست؟
تابعی که به متغیرهای Scope بیرونی خود دسترسی دارد، حتی پس از اتمام اجرای آن Scope.

### 15.2 Closure چگونه به Memory مربوط می‌شود؟
متغیرهای Scope بیرونی در Heap (یا Environment Record) زنده می‌مانند تا Closure بتواند به آن‌ها دسترسی داشته باشد.

### 15.3 آیا Closure باعث Memory Leak می‌شود؟
اگر به درستی مدیریت نشود، بله. اگر Closure دیگر استفاده نشود اما Referenceای به آن باقی بماند، متغیرهای بیرونی را زنده نگه می‌دارد.

### 15.4 چه زمانی Closure می‌تواند Objectها را زنده نگه دارد؟
وقتی تابع داخلی به متغیر بزرگی در Scope بیرونی Reference می‌دهد و خود تابع داخلی در جایی (مثل Event Listener) ذخیره می‌شود.

### 15.5 مثال ساده
```javascript
function makeCounter() {
  let count = 0; // در Closure زنده می‌ماند
  return () => ++count;
}
```

### 15.6 مثال Memory Leak
```javascript
let globalHandler;
function setup() {
  let hugeData = generateHugeData();
  globalHandler = function() { console.log("Click"); }; 
  // موتورهای مدرن ممکن است hugeData را بهینه‌سازی کنند اگر استفاده نشود، 
  // اما اگر hugeData در handler استفاده شود، Leak قطعی است.
}
```

### 15.7 روش صحیح مدیریت Closure
استفاده از `null` برای متغیرهای بزرگ در صورت عدم نیاز، و پاک‌سازی Event Listenerها.

> **خلاصه بخش 15:** Closureها متغیرهای بیرونی را زنده نگه می‌دارند. اگر مراقب نباشید، می‌توانند باعث Leak شوند. موتورهای مدرن گاهی متغیرهای استفاده‌نشده در Closure را بهینه‌سازی می‌کنند، اما نباید به آن اعتماد کرد.

---

## 16. Event Listener و Garbage Collection

### 16.1 Event Listener چیست؟
تابعی که برای واکنش به یک رویداد (مثل کلیک) ثبت می‌شود.

### 16.2 Event Listener چگونه Reference ایجاد می‌کند؟
DOM Element یک Strong Reference به تابع Handler نگه می‌دارد.

### 16.3 addEventListener
متد استاندارد برای ثبت Listener.

### 16.4 removeEventListener
متد استاندارد برای حذف Listener.

### 16.5 Anonymous Function و مشکل حذف Listener
```javascript
// ❌ نمی‌توان حذف کرد
element.addEventListener('click', function() { ... });
```

### 16.6 مثال Memory Leak
ایجاد و حذف مداوم Elementها در DOM بدون حذف Listenerهای آن‌ها.

### 16.7 Cleanup صحیح
همیشه در `destroy` یا `unmount` (مثل React `useEffect` cleanup)، Listenerها را حذف کنید.

> **خلاصه بخش 16:** Event Listenerها یک Strong Reference از DOM به تابع Handler می‌سازند. فراموش کردن `removeEventListener` باعث Leak می‌شود.

---

## 17. Timerها و Garbage Collection

### 17.1 setTimeout / 17.2 setInterval
توابعی که کد را در آینده اجرا می‌کنند.

### 17.3 clearTimeout / 17.4 clearInterval
توابعی برای Cancel کردن Timerها.

### 17.5 Timer و Closure
Timerها یک Closure به Scope خود می‌سازند.

### 17.6 Timer چگونه می‌تواند Object را زنده نگه دارد؟
تا زمانی که Timer فعال است، موتور JS باید تابع و متغیرهای آن را در حافظه نگه دارد.

### 17.7 مثال Memory Leak با setInterval
```javascript
function startTracking() {
  let data = new Array(100000);
  setInterval(() => { console.log(data.length); }, 1000);
  // data هرگز پاک نمی‌شود چون setInterval فعال است.
}
```

### 17.8 نسخه اصلاح‌شده
```javascript
function startTracking() {
  let data = new Array(100000);
  const id = setInterval(() => { console.log(data.length); }, 1000);
  // بعد از اتمام کار: clearInterval(id);
}
```

> **خلاصه بخش 17:** Timerهای فعال، Closureهای خود را زنده نگه می‌دارند. همیشه آن‌ها را در زمان مناسب Cancel کنید.

---

## 18. Map و Set

### 18.1 Map / 18.2 Set
ساختارهای داده ES6 برای نگهداری Key-Value (Map) و مقادیر یکتا (Set).

### 18.3 Map و Strong Reference / 18.4 Set و Strong Reference
Map و Set معمولی، **Strong Reference** به Keyها و Elementهای خود نگه می‌دارند.

### 18.5 چرا Map می‌تواند باعث نگه‌داشتن Objectها شود؟
چون تا زمانی که Key در Map است (یا `delete` نشود)، GC نمی‌تواند آن را پاک کند، حتی اگر در جای دیگر برنامه استفاده نشود.

### 18.6 مثال Memory Leak با Map
```javascript
let cache = new Map();
let obj = { data: "large" };
cache.set(obj, "result");
obj = null; // ❌ Object هنوز در Map است و پاک نمی‌شود.
```

> **خلاصه بخش 18:** Map و Set معمولی Strong Reference هستند و می‌توانند باعث Leak شوند اگر Keyها/Elementها پاک نشوند.

---

## 19. WeakMap و WeakSet

### 19.1 WeakMap / 19.2 WeakSet
نسخه‌های ضعیف Map و Set که Reference **Weak** به Keyها/Elementها نگه می‌دارند.

### 19.3 تفاوت Map و WeakMap / 19.4 تفاوت Set و WeakSet
- WeakMap فقط Object را به‌عنوان Key می‌پذیرد.
- WeakMap قابل Iterate نیست (`keys()`, `values()`, `entries()` ندارد).
- WeakSet فقط Object می‌پذیرد و قابل Iterate نیست.

### 19.5 Weak Reference چیست؟
Referenceای که مانع از GC شدن Object نمی‌شود.

### 19.6 چرا WeakMap با GC ارتباط دارد؟
اگر تنها Reference باقی‌مانده به یک Object، یک Weak Reference (در WeakMap) باشد، GC آن Object را پاک کرده و Entry مربوطه را از WeakMap حذف می‌کند.

### 19.7 چه چیزی در WeakMap به‌صورت Weak نگهداری می‌شود؟
فقط **Keyها**. Valueها Strong هستند (اما چون Key پاک شود، Value هم غیرقابل دسترس شده و پاک می‌شود).

### 19.8 چرا WeakMap قابل Iterate کردن نیست؟
چون GC می‌تواند در هر لحظه Keyها را حذف کند. اگر Iterate ممکن بود، لیست Keyها در حین پیمایش تغییر می‌کرد و باعث باگ می‌شد.

### 19.9 مثال کاربردی WeakMap
ذخیره Metadata برای Objectها بدون جلوگیری از GC آن‌ها:
```javascript
let weakCache = new WeakMap();
let obj = {};
weakCache.set(obj, "cached data");
obj = null; // obj و Entry آن در WeakCache پاک می‌شوند.
```

### 19.10 مثال کاربردی WeakSet
نگهداری لیستی از Objectهای "بازدید شده" در یک الگوریتم بدون جلوگیری از GC.

### 19.11 چه زمانی WeakMap مناسب است؟
برای Cacheها، ذخیره Metadata، و Private Data.

### 19.12 چه زمانی استفاده از WeakMap اشتباه است؟
وقتی نیاز به Iterate دارید، یا وقتی Keyها Primitive هستند.

> **خلاصه بخش 19:** WeakMap و WeakSet از Weak Reference استفاده می‌کنند و مانع GC نمی‌شوند. برای Cache و Metadata عالی هستند اما قابل Iterate نیستند.

---

## 20. WeakRef

### 20.1 WeakRef چیست؟
کلاسی در ES2021 که یک Weak Reference به یک Object می‌سازد.

### 20.2 Strong Reference / 20.3 Weak Reference
(توضیح داده شد).

### 20.4 تفاوت Strong و Weak
Strong مانع GC می‌شود، Weak نمی‌شود.

### 20.5 ساخت WeakRef
```javascript
let obj = { data: "test" };
let weak = new WeakRef(obj);
```

### 20.6 متد deref()
برای دسترسی به Object اصلی استفاده می‌شود. اگر Object پاک شده باشد، `undefined` برمی‌گرداند.
```javascript
let target = weak.deref();
if (target) { /* استفاده */ }
```

### 20.7 مثال عملی WeakRef
```javascript
let cache = new WeakRef(someLargeObject);
// بعداً:
let data = cache.deref();
if (data) { /* استفاده */ } else { /* Object پاک شده */ }
```

### 20.8 WeakRef و Cache
مناسب برای پیاده‌سازی Cacheهای پیشرفته که در صورت کمبود حافظه، خودبه‌خود خالی می‌شوند.

### 20.9 آیا WeakRef تضمین می‌کند Object حذف شود؟
**خیر.** موتور JS ممکن است تصمیم بگیرد Object را پاک نکند.

### 20.10 آیا زمان GC قابل پیش‌بینی است؟
**خیر.**

### 20.11 چرا نباید Logic اصلی برنامه را به WeakRef وابسته کرد؟
چون رفتار آن Non-deterministic است. ممکن است در یک اجرا `deref()` مقدار برگرداند و در اجرای دیگر `undefined`.

> **خلاصه بخش 20:** WeakRef اجازه می‌دهد یک Reference ضعیف بسازید و با `deref()` آن را بخوانید. اما به دلیل عدم قطعیت در زمان GC، نباید برای Logic حیاتی استفاده شود.

---

## 21. FinalizationRegistry

### 21.1 FinalizationRegistry چیست؟
کلاسی در ES2021 که اجازه می‌دهد یک Callback را برای زمان GC شدن یک Object ثبت کنید.

### 21.2 چرا وجود دارد؟
برای انجام Cleanupهای خارجی (مثل بستن File Handle یا آزادسازی WebAssembly Memory) وقتی یک Object JS پاک می‌شود.

### 21.3 register()
```javascript
const registry = new FinalizationRegistry((heldValue) => {
  console.log("Cleaning up:", heldValue);
});
registry.register(targetObject, "metadata");
```

### 21.4 unregister()
لغو ثبت یک Object.

### 21.5 Cleanup Callback
تابعی که پس از GC شدن `targetObject` اجرا می‌شود.

### 21.6 مثال ساده
```javascript
const registry = new FinalizationRegistry(id => {
  console.log(`Object ${id} was garbage collected.`);
});
let obj = {};
registry.register(obj, "obj-1");
obj = null; // پس از GC، Callback اجرا می‌شود.
```

### 21.7 رابطه FinalizationRegistry و GC
Callback فقط زمانی اجرا می‌شود که GC، `targetObject` را پاک کند.

### 21.8 آیا Callback همیشه اجرا می‌شود؟
**خیر.** ممکن است برنامه قبل از GC بسته شود، یا GC اصلاً اجرا نشود.

### 21.9 آیا زمان اجرای Callback قابل پیش‌بینی است؟
**خیر.**

### 21.10 چرا نباید Logic اصلی برنامه را به FinalizationRegistry وابسته کرد؟
طبق مستندات MDN: *"The cleanup callback is not guaranteed to run."* نباید برای منطق حیاتی یا آزادسازی منابع ضروری (بدون Fallback) استفاده شود.

### 21.11 موارد استفاده مناسب
آزادسازی منابع خارجی (مثل C++ handles در Node.js N-API) به‌عنوان یک "ایمنی اضافی".

### 21.12 موارد استفاده نامناسب
مدیریت State برنامه، Logهای حیاتی، یا آزادسازی منابعی که حتماً باید آزاد شوند (برای این‌ها از `try/finally` یا متدهای `close()` صریح استفاده کنید).

> **خلاصه بخش 21:** FinalizationRegistry برای اجرای Callback پس از GC است. اما اجرای آن تضمین‌شده نیست و نباید برای Logic اصلی برنامه استفاده شود.

---

## 22. آیا می‌توان Garbage Collection را دستی اجرا کرد؟

### 22.1 آیا JavaScript API عمومی برای اجرای GC دارد؟
**خیر.** هیچ متد استانداردی مثل `gc()` در زبان JS وجود ندارد.

### 22.2 چرا کنترل مستقیم GC در JavaScript وجود ندارد؟
برای حفظ انتزاع و اجازه دادن به موتور برای بهینه‌سازی زمان‌بندی GC.

### 22.3 `--expose-gc` در Node.js
یک Flag مخصوص Node.js/V8 که یک API غیررسمی را در اختیار برنامه‌نویس قرار می‌دهد.

### 22.4 `global.gc()`
با اجرای `node --expose-gc app.js`، می‌توانید `global.gc()` را صدا بزنید تا GC را درخواست کنید.

### 22.5 کاربرد آن برای Debugging
برای تست کردن اینکه آیا Objectی واقعاً Unreachable شده است یا خیر.

### 22.6 آیا استفاده از `global.gc()` در Production مناسب است؟
**خیر.** این کار Performance را به شدت کاهش می‌دهد و فقط برای Debugging/Test است.

### 22.7 تفاوت Debugging و Production
در Debugging می‌خواهید رفتار GC را کنترل کنید. در Production باید به موتور اعتماد کنید.

> **خلاصه بخش 22:** JS استاندارد API برای GC ندارد. Node.js با `--expose-gc` این امکان را فقط برای Debugging فراهم می‌کند.

---

## 23. بررسی Memory در Browser

### 23.1 Chrome DevTools چیست؟
مجموعه ابزارهای قدرتمند گوگل کروم برای Debugging.

### 23.2 Memory Panel
بخشی از DevTools برای بررسی مصرف حافظه.

### 23.3 Heap Snapshot
عکس‌برداری از تمام Objectهای موجود در Heap در یک لحظه.

### 23.4 گرفتن Heap Snapshot
در تب Memory، گزینه "Heap snapshot" را انتخاب و "Take snapshot" را بزنید.

### 23.5 بررسی Objectها
می‌توانید Objectها را بر اساس Constructor (مثل `Array`, `string`) فیلتر کنید.

### 23.6 Retained Size
حافظه‌ای که اگر این Object پاک شود، آزاد می‌شود (شامل Objectهای زیرمجموعه).

### 23.7 Shallow Size
حافظه خود Object (بدون زیرمجموعه‌ها).

### 23.8 Retainers
لیستی که نشان می‌دهد چه Referenceهایی این Object را زنده نگه داشته‌اند.

### 23.9 بررسی Reference Chain
با باز کردن Retainers، می‌توانید مسیر دسترسی از Root تا Object را ببینید.

### 23.10 مقایسه دو Heap Snapshot
گزینه "Comparison" اجازه می‌دهد تفاوت دو Snapshot را ببینید (Objectهای جدید، حذف‌شده و تغییر اندازه).

### 23.11 Allocation Timeline
ضبط لحظه‌به‌لحظه Allocationها برای پیدا کردن زمان‌های اوج مصرف.

### 23.12 Allocation Sampling
روش سبک‌تر برای بررسی Allocationها با سربار کمتر.

### 23.13 Detached DOM Nodes
در Snapshot با فیلتر `Detached` می‌توانید DOMهای حذف‌شده اما زنده را پیدا کنید.

### 23.14 پیدا کردن Memory Leak
با گرفتن Snapshot، انجام یک عملیات، و گرفتن Snapshot دوم، و مقایسه آن‌ها.

> **خلاصه بخش 23:** Chrome DevTools ابزارهایی مثل Heap Snapshot و Allocation Timeline را برای پیدا کردن Leakها و بررسی Retainerها ارائه می‌دهد.

---

## 24. بررسی Memory در Node.js

### 24.1 `process.memoryUsage()`
متدی که آمار مصرف حافظه Node.js را برمی‌گرداند.

### 24.2 `heapUsed`
میزان حافظه Heap که در حال حاضر استفاده می‌شود.

### 24.3 `heapTotal`
کل حافظه Heap که V8 اختصاص داده است.

### 24.4 `rss`
میزان کل حافظه اشغال‌شده توسط پروسه در سیستم‌عامل (Resident Set Size).

### 24.5 `external`
حافظه استفاده‌شده توسط C++ Bindings (مثل Bufferها).

### 24.6 `arrayBuffers`
حافظه اختصاص‌یافته برای `ArrayBuffer` و `SharedArrayBuffer`.

### 24.7 Node.js Inspector
ابزاری برای اتصال DevTools کروم به پروسه Node.js.

### 24.8 `--inspect`
Flagی برای فعال‌سازی Inspector: `node --inspect app.js`.

### 24.9 Heap Snapshot در Node.js
از طریق Inspector یا کدنویسی با `v8.writeHeapSnapshot()`.

### 24.10 `--expose-gc`
(توضیح داده شد).

### 24.11 بررسی Memory Leak در Node.js
استفاده از `process.memoryUsage()` در یک `setInterval` برای رصد رشد `heapUsed`.

### 24.12 مثال عملی
```javascript
setInterval(() => {
  console.log(process.memoryUsage().heapUsed / 1024 / 1024, "MB");
}, 1000);
```

> **خلاصه بخش 24:** در Node.js می‌توانید با `process.memoryUsage()` و Inspector، مصرف حافظه را رصد کرده و Heap Snapshot بگیرید.

---

## 25. Garbage Collection در Browser و Node.js

### 25.1 شباهت‌ها
هر دو از V8 (یا موتور مشابه) استفاده می‌کنند. الگوریتم‌های پایه (Mark-Sweep, Generational) یکسان است.

### 25.2 تفاوت‌ها
- **Browser:** محدودیت حافظه کمتر، تمرکز بر UI Latency، وجود DOM.
- **Node.js:** دسترسی به RAM بیشتر، تمرکز بر Throughput، عدم وجود DOM.

### 25.3 نقش V8 در Node.js
V8 در Node.js برای Server-side بهینه‌سازی شده است (مثل Heap Size بزرگتر).

### 25.4 نقش JavaScript Engine در Browser
موتور در Browser باید با Renderer و compositor هماهنگ باشد تا Frame Drop ایجاد نشود.

### 25.5 آیا همه Browserها از V8 استفاده می‌کنند؟
خیر. Firefox از SpiderMonkey، Safari از JavaScriptCore استفاده می‌کند.

### 25.6 آیا Garbage Collector همه Engineها یکسان است؟
خیر. هر موتور الگوریتم‌های خاص خود را دارد (هرچند همگی از اصول Generational و Mark-Sweep پیروی می‌کنند).

### 25.7 چرا نباید جزئیات V8 را به کل JavaScript نسبت داد؟
چون JS یک Spec است. جزئیات GC در SpiderMonkey یا JavaScriptCore متفاوت است. کد شما باید در همه Engineها کار کند.

> **خلاصه بخش 25:** اگرچه اصول GC یکسان است، اما پیاده‌سازی و بهینه‌سازی‌ها در Browser و Node.js و Engineهای مختلف متفاوت است.

---

## 26. اشتباهات رایج

### 26.1 «JavaScript خودش حافظه را مدیریت می‌کند، پس Memory Leak نداریم.»
> ❌ تصور اشتباه: GC همه چیز را حل می‌کند.
> ✅ واقعیت: GC فقط Unreachableها را پاک می‌کند. Logical Leakها همچنان ممکن است.

### 26.2 «هر Object بدون استفاده فوراً حذف می‌شود.»
> ❌ تصور اشتباه: به محض `null` کردن، حذف می‌شود.
> ✅ واقعیت: حذف زمانی رخ می‌دهد که GC اجرا شود و Object Unreachable باشد.

### 26.3 «با null کردن یک متغیر، حافظه فوراً آزاد می‌شود.»
> ❌ تصور اشتباه: `a = null` یعنی آزادسازی آنی.
> ✅ واقعیت: فقط Reference قطع می‌شود. GC بعداً آن را پاک می‌کند.

### 26.4 «Circular Reference همیشه Memory Leak است.»
> ❌ تصور اشتباه: چرخه‌ها خطرناک‌اند.
> ✅ واقعیت: در Mark-and-Sweep مدرن، اگر چرخه از Root قطع شود، پاک می‌شود.

### 26.5 «WeakMap فوراً حافظه را آزاد می‌کند.»
> ❌ تصور اشتباه: WeakMap = آزادسازی آنی.
> ✅ واقعیت: WeakMap فقط مانع GC نمی‌شود. زمان GC نامشخص است.

### 26.6 «WeakRef همیشه خیلی سریع undefined می‌شود.»
> ❌ تصور اشتباه: به محض `null` کردن، `deref()` مقدار `undefined` می‌دهد.
> ✅ واقعیت: تا زمانی که GC اجرا نشود، `deref()` مقدار برمی‌گرداند.

### 26.7 «FinalizationRegistry همیشه اجرا می‌شود.»
> ❌ تصور اشتباه: Callback حتماً اجرا می‌شود.
> ✅ واقعیت: اجرای Callback تضمین‌شده نیست.

### 26.8 «می‌توان زمان GC را دقیق مشخص کرد.»
> ❌ تصور اشتباه: ما کنترل زمان GC را داریم.
> ✅ واقعیت: زمان‌بندی GC کاملاً در اختیار موتور JS است.

### 26.9 «مصرف زیاد RAM همیشه یعنی Memory Leak.»
> ❌ تصور اشتباه: RAM بالا = Leak.
> ✅ واقعیت: ممکن است Cache یا داده‌های ضروری باشند. Leak یعنی "رشد مداوم".

### 26.10 «Garbage Collector همیشه باعث کندی برنامه می‌شود.»
> ❌ تصور اشتباه: GC همیشه بد است.
> ✅ واقعیت: GC مدرن بسیار بهینه است و Pauseها بسیار کوتاه‌اند.

### 26.11 «V8 همان JavaScript است.»
> ❌ تصور اشتباه: V8 = JS.
> ✅ واقعیت: V8 یک Engine است که JS را اجرا می‌کند.

### 26.12 «تمام JavaScript Engineها دقیقاً یک Garbage Collector دارند.»
> ❌ تصور اشتباه: همه Engineها یکسان‌اند.
> ✅ واقعیت: هر موتور (V8, SpiderMonkey, JSC) پیاده‌سازی خاص خود را دارد.

> **خلاصه بخش 26:** درک نادرست از قطعیت GC و زمان‌بندی آن، منجر به باگ‌های پیچیده می‌شود. GC یک فرآیند غیرقطعی است.

---

## 27. Best Practices

### 27.1 مدیریت صحیح Lifecycle
برای هر Object، بدانید چه زمانی ساخته و چه زمانی باید پاک شود.

### 27.2 Cleanup کردن Event Listenerها
همیشه در `destroy` یا `unmount`، Listenerها را حذف کنید.

### 27.3 Cleanup کردن Timerها
`clearTimeout` و `clearInterval` را فراموش نکنید.

### 27.4 مدیریت Cache
از `WeakMap` برای Cacheها استفاده کنید یا محدودیت اندازه (LRU) بگذارید.

### 27.5 جلوگیری از Globalهای غیرضروری
از `let` و `const` استفاده کنید. از آلوده کردن `window` خودداری کنید.

### 27.6 جلوگیری از Referenceهای غیرضروری
پس از اتمام کار با یک Object بزرگ، آن را `null` کنید (اگر Scope طولانی دارد).

### 27.7 استفاده صحیح از Map
اگر Keyها ممکن است حذف شوند، از `WeakMap` استفاده کنید.

### 27.8 استفاده صحیح از WeakMap
برای Metadata و Cacheهای ضعیف عالی است.

### 27.9 استفاده محتاطانه از WeakRef
فقط برای بهینه‌سازی Cache، نه برای Logic اصلی.

### 27.10 استفاده محتاطانه از FinalizationRegistry
فقط برای Cleanup منابع خارجی، با در نظر گرفتن Fallback.

### 27.11 Profiling قبل از Optimization
هرگز بدون اندازه‌گیری (با DevTools یا `process.memoryUsage()`) کد را بهینه نکنید.

### 27.12 جلوگیری از Premature Optimization
کد را تمیز و خوانا بنویسید. فقط در صورت مشاهده Leak یا مشکل Performance، بهینه‌سازی کنید.

> **خلاصه بخش 27:** بهترین راه جلوگیری از Leak، Cleanup صحیح و پرهیز از نگهداری ناخواسته Referenceها است. هرگز بدون Profiling بهینه‌سازی نکنید.

---

## 28. پروژه عملی

در این پروژه، یک Memory Leak عمدی در Node.js ایجاد کرده و آن را پیدا و رفع می‌کنیم.

### ساختار فایل‌ها
```text
gc-project/
  ├── leak.js
  └── fixed.js
```

### مرحله 1 تا 4: ایجاد Memory Leak عمدی (`leak.js`)
```javascript
// leak.js
const cache = new Map();
let counter = 0;

function createLeak() {
  // مرحله 1 و 2: ساخت Object و ذخیره در Map
  let largeObject = { id: counter++, data: new Array(10000).fill("leak") };
  
  // مرحله 3 و 4: Reference اضافی و Leak عمدی
  cache.set(largeObject.id, largeObject); 
  
  // ما هرگز cache را پاک نمی‌کنیم!
}

setInterval(() => {
  createLeak();
  const mem = process.memoryUsage();
  console.log(`Heap Used: ${(mem.heapUsed / 1024 / 1024).toFixed(2)} MB`);
}, 100);
```

### مرحله 5 و 6: بررسی مصرف و پیدا کردن علت
اجرا کنید:
```bash
node leak.js
```
مشاهده می‌کنید که `Heap Used` به‌صورت خطی رشد می‌کند و هرگز کم نمی‌شود. علت: `cache` یک Strong Reference به تمام `largeObject`ها نگه می‌دارد.

### مرحله 7 و 8: اصلاح Memory Leak (`fixed.js`)
```javascript
// fixed.js
const cache = new Map();
let counter = 0;
const MAX_CACHE_SIZE = 50;

function createNoLeak() {
  let largeObject = { id: counter++, data: new Array(10000).fill("fixed") };
  cache.set(largeObject.id, largeObject);
  
  // اصلاح: محدود کردن اندازه Cache
  if (cache.size > MAX_CACHE_SIZE) {
    const firstKey = cache.keys().next().value;
    cache.delete(firstKey);
  }
}

setInterval(() => {
  createNoLeak();
  const mem = process.memoryUsage();
  console.log(`Heap Used: ${(mem.heapUsed / 1024 / 1024).toFixed(2)} MB`);
}, 100);
```

### مرحله 9: مقایسه قبل و بعد
با اجرای `node fixed.js`، می‌بینید که `Heap Used` تا یک حد مشخص رشد کرده و سپس نوسان می‌کند (به دلیل GC).

### نحوه بررسی در Chrome DevTools
1. `node --inspect leak.js` را اجرا کنید.
2. کروم را باز کرده و `chrome://inspect` را بروید.
3. به تب Memory رفته و Heap Snapshot بگیرید.
4. `Map` و محتویات آن را بررسی کنید.

### چرا نتیجه در هر اجرا دقیقاً یکسان نیست؟
چون زمان‌بندی GC توسط V8 بر اساس شرایط سیستم و الگوریتم‌های داخلی انجام می‌شود و قطعی نیست.

> **خلاصه پروژه:** ما یک Cache بدون محدودیت ساختیم که باعث Leak شد. با محدود کردن اندازه Cache، مشکل را حل کردیم و با `process.memoryUsage()` آن را اثبات کردیم.

---

## 29. تمرین‌های آموزشی

### تمرین 1: Reachability
- **صورت سؤال:** کدی بنویسید که یک Object بسازد و سپس آن را Unreachable کند.
- **هدف:** درک مفهوم Reachability.
- **سطح:** آسان.

### تمرین 2: Circular Reference
- **صورت سؤال:** دو Object بسازید که به هم Reference بدهند. آیا در JS مدرن Leak ایجاد می‌کنند؟ اثبات کنید.
- **هدف:** درک رفتار Mark-and-Sweep با Cycleها.
- **سطح:** متوسط.

### تمرین 3: Closure Leak
- **صورت سؤال:** یک Closure بسازید که یک Array بزرگ را در Scope بیرونی نگه دارد. چگونه آن را رفع می‌کنید؟
- **هدف:** درک ارتباط Closure و حافظه.
- **سطح:** متوسط.

### تمرین 4: Event Listener
- **صورت سؤال:** یک Element بسازید، Listener اضافه کنید، Element را از DOM حذف کنید. آیا Listener پاک می‌شود؟
- **هدف:** درک Detached DOM و Listenerها.
- **سطح:** متوسط.

### تمرین 5: Timer
- **صورت سؤال:** یک `setInterval` بسازید که هر ثانیه یک Object بزرگ بسازد. چگونه Leak را رفع می‌کنید؟
- **هدف:** مدیریت Timerها.
- **سطح:** آسان.

### تمرین 6: Map vs WeakMap
- **صورت سؤال:** یک `Map` و یک `WeakMap` بسازید. Keyها را `null` کنید. تفاوت رفتار را با `process.memoryUsage()` نشان دهید.
- **هدف:** درک عملی Weak Reference.
- **سطح:** متوسط.

### تمرین 7: WeakRef
- **صورت سؤال:** یک `WeakRef` بسازید. Object را `null` کنید. با `--expose-gc` و `global.gc()` بررسی کنید چه زمانی `deref()` مقدار `undefined` می‌دهد.
- **هدف:** درک عدم قطعیت WeakRef.
- **سطح:** پیشرفته.

### تمرین 8: FinalizationRegistry
- **صورت سؤال:** یک `FinalizationRegistry` بسازید و Callback آن را لاگ کنید. چرا گاهی اجرا نمی‌شود؟
- **هدف:** درک ماهیت Non-deterministic.
- **سطح:** پیشرفته.

### تمرین 9: Heap Snapshot
- **صورت سؤال:** در Browser، یک Leak کوچک ایجاد کنید و با مقایسه دو Heap Snapshot آن را پیدا کنید.
- **هدف:** کار با DevTools.
- **سطح:** متوسط.

### تمرین 10: پروژه کوچک Cache
- **صورت سؤال:** یک Cache با `WeakMap` بنویسید که Metadata یک Object را نگه دارد. ثابت کنید با حذف Object، Cache هم خالی می‌شود.
- **هدف:** پیاده‌سازی عملی WeakMap.
- **سطح:** پیشرفته.

**راهنمای حل:**
- تمرین 1: `let a = {}; a = null;`
- تمرین 2: `let a={}, b={}; a.b=b; b.a=a; a=null; b=null;` (پاک می‌شوند).
- تمرین 6: در `Map` حافظه رشد می‌کند، در `WeakMap` ثابت می‌ماند.
- تمرین 7: `node --expose-gc` و صدا زدن `global.gc()`.

---

## 30. خلاصه نهایی

### Garbage Collector در 5 دقیقه
JavaScript به‌صورت خودکار حافظه را مدیریت می‌کند. وقتی متغیری می‌سازید، حافظه Allocate می‌شود. موتور JS (مثل V8) از الگوریتم **Mark-and-Sweep** استفاده می‌کند: از نقاط پایه (Rootها) شروع می‌کند، تمام Objectهای متصل را علامت می‌زند (Mark) و بقیه را پاک می‌کند (Sweep). برای افزایش سرعت، Heap به بخش‌های Young (Objectهای جدید) و Old (Objectهای قدیمی) تقسیم می‌شود (Generational GC).
اگر برنامه‌نویس ناخواسته Referenceای به یک Object بی‌استفاده نگه دارد (مثل Event Listener، Timer، یا Cache)، **Memory Leak** رخ می‌دهد. برای جلوگیری از این مشکل، باید Lifecycleها را مدیریت کرد. ابزارهایی مثل `WeakMap` و `WeakRef` اجازه می‌دهند Referenceهای ضعیف بسازیم که مانع GC نمی‌شوند، اما زمان اجرای GC هرگز قطعی نیست.

### جدول مفهومی

| مفهوم | توضیح کوتاه |
| --- | --- |
| **Memory Management** | فرآیند کنترل و تخصیص حافظه RAM توسط برنامه. |
| **Stack** | حافظه سریع و ساختاریافته برای داده‌های ثابت و Call Stack. |
| **Heap** | حافظه بزرگ و پویا برای Objectها و داده‌های متغیر. |
| **Reference** | اشاره‌گری که آدرس یک Object در Heap را نگه می‌دارد. |
| **Reachability** | قابلیت دسترسی یک Object از طریق Rootها (ملاک GC). |
| **Garbage** | Objectهای Unreachable که آماده حذف هستند. |
| **Garbage Collector** | مکانیزم خودکار شناسایی و حذف Garbageها. |
| **Mark-and-Sweep** | الگوریتم اصلی GC: علامت‌گذاری Objectهای زنده و حذف بقیه. |
| **Generational GC** | تقسیم Heap به Young و Old بر اساس سن Objectها برای سرعت بیشتر. |
| **Memory Leak** | نشت حافظه به دلیل نگهداری ناخواسته Referenceها. |
| **Map** | ساختار داده Key-Value با Strong Reference. |
| **WeakMap** | Map با Weak Reference به Keyها (مانع GC نمی‌شود). |
| **WeakSet** | Set با Weak Reference به Elementها. |
| **WeakRef** | کلاسی برای ساخت یک Weak Reference به یک Object. |
| **FinalizationRegistry** | کلاسی برای ثبت Callback جهت اجرای پس از GC شدن یک Object. |
| **Heap Snapshot** | عکس‌برداری از وضعیت Heap برای بررسی Leakها. |

---

## 31. نقشه یادگیری

برای درک عمیق Garbage Collection، این مسیر را طی کنید:

```text
JavaScript
   ↓
Memory
   ↓
Stack / Heap
   ↓
Reference
   ↓
Reachability
   ↓
Garbage
   ↓
Mark-and-Sweep
   ↓
Generational GC
   ↓
V8
   ↓
Memory Leak
   ↓
WeakMap / WeakSet
   ↓
WeakRef
   ↓
FinalizationRegistry
   ↓
Memory Profiling
   ↓
Performance
```

---

## 32. منابع و مطالعه بیشتر

برای مطالعه عمیق‌تر، از منابع رسمی و معتبر زیر استفاده کنید:

1. **MDN – Memory Management**
   - **سایت:** Mozilla Developer Network
   - **لینک:** [Memory Management](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_management)
   - **توضیح:** مرجع اصلی و رسمی برای مفاهیم پایه مدیریت حافظه در JS.

2. **MDN – WeakMap**
   - **سایت:** Mozilla Developer Network
   - **لینک:** [WeakMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap)
   - **توضیح:** مستندات کامل WeakMap و رفتار آن با GC.

3. **MDN – WeakSet**
   - **سایت:** Mozilla Developer Network
   - **لینک:** [WeakSet](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet)
   - **توضیح:** مرجع رسمی WeakSet.

4. **MDN – WeakRef**
   - **سایت:** Mozilla Developer Network
   - **لینک:** [WeakRef](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakRef)
   - **توضیح:** توضیح دقیق WeakRef و هشدارهای مربوط به عدم قطعیت آن.

5. **MDN – FinalizationRegistry**
   - **سایت:** Mozilla Developer Network
   - **لینک:** [FinalizationRegistry](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry)
   - **توضیح:** مستندات رسمی و هشدارهای مهم درباره عدم تضمین اجرای Callback.

6. **ECMAScript Specification**
   - **سایت:** TC39
   - **لینک:** [ECMAScript Language Specification](https://tc39.es/ecma262/)
   - **توضیح:** استاندارد رسمی زبان JavaScript (بخش‌های مربوط به Memory Model و WeakRef).

7. **V8 Official Blog – Garbage Collection**
   - **سایت:** V8 Developer Blog
   - **لینک:** [V8 Blog - Trash Talk (GC Series)](https://v8.dev/blog/trash-talk)
   - **توضیح:** مقالات عمیق مهندسان گوگل درباره الگوریتم‌های GC در V8.

8. **V8 Official Documentation**
   - **سایت:** V8
   - **لینک:** [V8 Docs - Garbage Collection](https://v8.dev/docs)
   - **توضیح:** مستندات فنی معماری V8.

9. **Node.js Documentation – Memory**
   - **سایت:** Node.js
   - **لینک:** [Node.js Memory Diagnostics](https://nodejs.org/en/learn/diagnostics/memory/overview)
   - **توضیح:** راهنمای رسمی Node.js برای بررسی و دیباگ مصرف حافظه.

10. **Chrome DevTools Documentation – Memory**
    - **سایت:** Chrome for Developers
    - **لینک:** [Memory Panel](https://developer.chrome.com/docs/devtools/memory)
    - **توضیح:** آموزش گام‌به‌گام استفاده از ابزارهای Memory در کروم.

---
*این آموزش در تاریخ 16 سپتامبر 2026 بازبینی و به‌روزرسانی شده است.*
