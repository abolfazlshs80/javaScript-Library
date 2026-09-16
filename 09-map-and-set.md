# Data Structures در JavaScript — Map و Set

برای یک Repository آموزشی GitHub تولید کنی.

مخاطب این آموزش افراد **مبتدی تا متوسط و سپس توسعه‌دهندگان پیشرفته JavaScript** هستند؛ بنابراین آموزش باید از ساده‌ترین مفاهیم شروع شود و به‌صورت تدریجی به مباحث پیشرفته برسد.

---

# قوانین کلی آموزش

* زبان توضیحات: **فارسی ساده و روان**
* کدها: **JavaScript**
* اصطلاحات مهم انگلیسی را در کنار معادل فارسی آن‌ها بنویس.
* ابتدا مفهوم را خیلی ساده توضیح بده، سپس مثال بزن و بعد وارد جزئیات فنی شو.
* هیچ مفهوم مهمی را بدون مثال رها نکن.
* مثال‌ها را از ساده به واقعی و سپس پیشرفته مرتب کن.
* در صورت امکان برای هر مفهوم مثال:

  1. ساده
  2. متوسط
  3. کاربردی/واقعی
     ارائه کن.
* کدها باید قابل اجرا و صحیح باشند.
* اگر در کدی اشتباه رایج وجود دارد، آن را با بخش **اشتباه رایج** توضیح بده.
* از توضیحات بیش از حد پیچیده در ابتدای آموزش خودداری کن.
* در بخش‌های پیشرفته می‌توانی وارد جزئیات ECMAScript و رفتار داخلی JavaScript شوی.
* هرجا تفاوت مهمی وجود دارد، با مثال نشان بده.
* از اطلاعات منسوخ استفاده نکن.
* قابلیت‌هایی که اخیراً به JavaScript اضافه شده‌اند را در صورت مرتبط بودن معرفی کن و وضعیت پشتیبانی آن‌ها را ذکر کن.

---

# 1. مقدمه

ابتدا توضیح بده:

## Data Structure چیست؟

به زبان خیلی ساده توضیح بده:

* ساختار داده چیست؟
* چرا به Data Structure نیاز داریم؟
* JavaScript چه ساختارهای داده‌ای دارد؟
* Array چیست؟
* Object چیست؟
* Map چیست؟
* Set چیست؟
* WeakMap چیست؟
* WeakSet چیست؟

در پایان این بخش توضیح بده که چرا JavaScript علاوه بر Array و Object، ساختارهایی مانند Map و Set دارد.

---

# 2. جایگاه Map و Set در JavaScript

توضیح بده:

* Map و Set چه نوع Data Structureهایی هستند؟
* Keyed Collections چیست؟
* Map و Set چه تفاوتی با Array دارند؟
* Map و Set چه تفاوتی با Object دارند؟
* Map و Set از چه نسخه‌ای از ECMAScript وارد JavaScript شدند؟
* مفهوم Iterable چیست و چرا برای Map و Set مهم است؟

یک تصویر ذهنی ساده نیز ارائه کن:

```text
Array
 └── ordered collection

Object
 └── property → value

Map
 └── key → value

Set
 └── unique values
```

---

# 3. Map چیست؟

Map را از صفر توضیح بده.

توضیح بده:

* Map چیست؟
* چرا از Map استفاده می‌کنیم؟
* ساختار key/value چیست؟
* آیا key در Map باید String باشد؟
* آیا Object می‌تواند key باشد؟
* آیا Function می‌تواند key باشد؟
* آیا Number، Boolean، Symbol و BigInt می‌توانند key باشند؟
* آیا یک key می‌تواند چند بار وجود داشته باشد؟

مثال ساده:

```javascript
const users = new Map();

users.set("name", "Ali");
users.set("age", 25);
```

خروجی و رفتار آن را توضیح بده.

---

# 4. ساخت Map

روش‌های مختلف ساخت Map را آموزش بده.

### Empty Map

```javascript
const map = new Map();
```

### Map با Array از Entries

```javascript
const map = new Map([
    ["name", "Ali"],
    ["age", 25]
]);
```

توضیح بده:

* Entry چیست؟
* چرا داده‌ها به صورت `[key, value]` هستند؟
* Map Constructor چگونه کار می‌کند؟

---

# 5. افزودن داده با set()

به‌صورت کامل توضیح بده:

```javascript
map.set(key, value);
```

بررسی کن:

* set چیست؟
* اگر key وجود نداشته باشد چه می‌شود؟
* اگر key قبلاً وجود داشته باشد چه می‌شود؟
* آیا set یک Map جدید ایجاد می‌کند؟
* مقدار برگشتی set چیست؟
* Method Chaining چیست؟

مثال:

```javascript
map
    .set("name", "Ali")
    .set("age", 25)
    .set("city", "Sari");
```

---

# 6. دریافت داده با get()

توضیح بده:

```javascript
map.get(key);
```

بررسی کن:

* اگر key وجود داشته باشد چه اتفاقی می‌افتد؟
* اگر key وجود نداشته باشد چه چیزی برمی‌گردد؟
* تفاوت `undefined` واقعی با key موجودی که مقدار آن undefined است چیست؟

مثال:

```javascript
const map = new Map();

map.set("name", "Ali");

console.log(map.get("name"));
console.log(map.get("age"));
```

---

# 7. بررسی وجود Key با has()

توضیح بده:

```javascript
map.has(key);
```

مثال‌های مختلف ارائه کن.

همچنین توضیح بده چرا در بعضی شرایط بهتر است به جای:

```javascript
map.get(key)
```

از:

```javascript
map.has(key)
```

استفاده کنیم.

---

# 8. حذف داده با delete()

توضیح بده:

```javascript
map.delete(key);
```

بررسی کن:

* خروجی `delete`
* حذف key موجود
* حذف key غیرموجود

مثال عملی ارائه کن.

---

# 9. حذف تمام داده‌ها با clear()

توضیح بده:

```javascript
map.clear();
```

و تفاوت آن را با `delete()` توضیح بده.

---

# 10. تعداد عناصر با size

توضیح بده:

```javascript
map.size
```

تفاوت `size` با:

```javascript
array.length
```

را نیز توضیح بده.

---

# 11. Iteration روی Map

این بخش را کامل آموزش بده.

## for...of

```javascript
for (const item of map) {
    console.log(item);
}
```

توضیح بده چرا خروجی به شکل:

```javascript
[key, value]
```

است.

---

## Destructuring در Map

```javascript
for (const [key, value] of map) {
    console.log(key, value);
}
```

توضیح بده Destructuring چگونه اینجا استفاده شده است.

---

# 12. keys()

توضیح بده:

```javascript
map.keys();
```

و مثال عملی ارائه کن.

---

# 13. values()

توضیح بده:

```javascript
map.values();
```

و مثال عملی ارائه کن.

---

# 14. entries()

توضیح بده:

```javascript
map.entries();
```

و ارتباط آن با:

```javascript
for...of
```

را توضیح بده.

---

# 15. forEach() در Map

توضیح بده:

```javascript
map.forEach((value, key) => {
    console.log(key, value);
});
```

حتماً تفاوت ترتیب پارامترهای `forEach` در Map با برخی متدهای Array را توضیح بده.

---

# 16. ترتیب داده‌ها در Map

توضیح بده:

* آیا Map ترتیب عناصر را حفظ می‌کند؟
* منظور از insertion order چیست؟
* اگر یک key دوباره set شود چه اتفاقی برای ترتیب می‌افتد؟

مثال ارائه کن.

---

# 17. Key Equality در Map

این بخش را از ساده تا پیشرفته توضیح بده.

موضوعات:

* مقایسه keyها
* `===`
* SameValueZero
* `NaN`
* `0`
* `-0`
* Object Reference

مثال:

```javascript
const map = new Map();

map.set(NaN, "hello");

console.log(map.get(NaN));
```

سپس مثال Object:

```javascript
const user1 = {};
const user2 = {};

const map = new Map();

map.set(user1, "Ali");

console.log(map.get(user1));
console.log(map.get(user2));
```

توضیح بده چرا `user2` همان key محسوب نمی‌شود.

---

# 18. Object به عنوان Key در Map

به‌صورت کامل توضیح بده:

```javascript
const user = {
    id: 1
};

const map = new Map();

map.set(user, "Admin");
```

توضیح بده:

* Reference چیست؟
* Object Identity چیست؟
* چرا دو Object با propertyهای یکسان الزاماً key یکسان نیستند؟

---

# 19. Function به عنوان Key

مثال:

```javascript
function test() {}

const map = new Map();

map.set(test, "some value");
```

توضیح بده چرا Function نیز می‌تواند key باشد.

---

# 20. Map در مقابل Object

یک مقایسه آموزشی کامل انجام بده.

بررسی کن:

* نوع key
* حفظ ترتیب
* size
* iteration
* performance considerations
* prototype
* accidental keys
* serialization
* API
* کاربردهای مناسب

مثال‌های مشابه با:

```javascript
const user = {
    name: "Ali"
};
```

و:

```javascript
const user = new Map([
    ["name", "Ali"]
]);
```

ارائه کن.

تأکید کن که این مقایسه نباید به این نتیجه ساده تبدیل شود که همیشه Map بهتر از Object یا برعکس است؛ انتخاب به نوع داده و نیاز برنامه بستگی دارد.

---

# 21. Map در مقابل Array

مثال‌هایی ارائه کن که نشان دهند:

* چه زمانی Array مناسب است؟
* چه زمانی Map مناسب است؟

مثلاً:

```javascript
users.find(...)
```

در مقابل:

```javascript
usersMap.get(id)
```

توضیح بده.

در مورد پیچیدگی زمانی نیز با احتیاط توضیح بده و از ادعاهای مطلق درباره implementation داخلی JavaScript خودداری کن.

---

# 22. تبدیل Map به Array

روش‌های مختلف را آموزش بده:

```javascript
[...map]
```

```javascript
Array.from(map)
```

و:

```javascript
[...map.keys()]
```

```javascript
[...map.values()]
```

---

# 23. تبدیل Array به Map

مثال:

```javascript
const users = [
    [1, "Ali"],
    [2, "Reza"],
    [3, "Sara"]
];

const userMap = new Map(users);
```

توضیح بده که ورودی Map Constructor باید iterable مناسب از key/value pairها باشد.

---

# 24. تبدیل Object به Map

روش‌های مختلف را توضیح بده.

مثال:

```javascript
const user = {
    name: "Ali",
    age: 25
};

const map = new Map(Object.entries(user));
```

و برعکس:

```javascript
const object = Object.fromEntries(map);
```

محدودیت‌ها و تفاوت‌های Object و Map را نیز توضیح بده.

---

# 25. کاربردهای واقعی Map

چندین مثال واقعی ارائه کن:

### User Lookup

```javascript
const users = new Map();
```

### Cache

```javascript
const cache = new Map();
```

### Counting

```javascript
const counter = new Map();
```

### Grouping

```javascript
const groups = new Map();
```

### Mapping ID به Object

```javascript
users.set(user.id, user);
```

### Memoization

توضیح بده چگونه Map می‌تواند برای cache کردن نتیجه Function استفاده شود.

---

# 26. ساخت Frequency Counter با Map

مثال کامل:

```javascript
const words = ["js", "csharp", "js", "python", "js"];

const frequency = new Map();
```

و تعداد تکرار هر مقدار را محاسبه کن.

سپس راه‌حل را خط‌به‌خط توضیح بده.

---

# 27. Set چیست؟

اکنون وارد بخش Set شو.

توضیح بده:

* Set چیست؟
* چرا از Set استفاده می‌کنیم؟
* Set چه چیزی را ذخیره می‌کند؟
* آیا مقدار تکراری قبول می‌کند؟
* آیا ترتیب عناصر را حفظ می‌کند؟

مثال:

```javascript
const numbers = new Set();

numbers.add(10);
numbers.add(20);
numbers.add(10);

console.log(numbers);
```

---

# 28. ساخت Set

### Empty Set

```javascript
const set = new Set();
```

### Set از Array

```javascript
const set = new Set([1, 2, 3, 3, 4]);
```

خروجی را توضیح بده.

---

# 29. add()

توضیح بده:

```javascript
set.add(value);
```

بررسی کن:

* افزودن مقدار جدید
* افزودن مقدار تکراری
* مقدار برگشتی `add()`
* chaining

مثال:

```javascript
set
    .add(1)
    .add(2)
    .add(3);
```

---

# 30. has()

توضیح بده:

```javascript
set.has(value);
```

مثال‌های مختلف ارائه کن.

---

# 31. delete()

توضیح بده:

```javascript
set.delete(value);
```

و خروجی آن را بررسی کن.

---

# 32. clear()

توضیح بده:

```javascript
set.clear();
```

---

# 33. size

توضیح بده:

```javascript
set.size;
```

---

# 34. Iteration در Set

این روش‌ها را آموزش بده:

```javascript
for...of
```

```javascript
set.values()
```

```javascript
set.keys()
```

```javascript
set.entries()
```

```javascript
set.forEach()
```

توضیح بده چرا `keys()` و `values()` در Set رفتار متفاوتی با چیزی که ممکن است مبتدی انتظار داشته باشد دارند.

---

# 35. حذف Duplicate از Array با Set

این یکی از مهم‌ترین کاربردهای Set است.

مثال:

```javascript
const numbers = [1, 2, 2, 3, 4, 4, 5];

const uniqueNumbers = [...new Set(numbers)];

console.log(uniqueNumbers);
```

خط‌به‌خط توضیح بده.

---

# 36. Set و Equality

مانند Map توضیح بده:

* SameValueZero
* NaN
* 0
* -0
* Object Reference

مثال‌های واضح ارائه کن.

---

# 37. Object در Set

مثال:

```javascript
const user1 = { id: 1 };
const user2 = { id: 1 };

const set = new Set();

set.add(user1);
set.add(user2);
```

توضیح بده چرا هر دو Object داخل Set قرار می‌گیرند.

---

# 38. Set در مقابل Array

توضیح بده:

* Array چه زمانی مناسب است؟
* Set چه زمانی مناسب است؟
* Duplicate
* Membership checking
* ترتیب
* Index
* Access by index
* Iteration
* کاربردهای واقعی

مثال:

```javascript
array.includes(value)
```

در مقابل:

```javascript
set.has(value)
```

با توضیح دقیق و بدون ادعاهای مطلق درباره performance.

---

# 39. عملیات مجموعه‌ای با Set

این بخش را از مقدماتی تا پیشرفته آموزش بده.

## Union

اجتماع دو Set

```text
A ∪ B
```

مثال JavaScript.

---

## Intersection

اشتراک:

```text
A ∩ B
```

مثال JavaScript.

---

## Difference

تفاضل:

```text
A - B
```

مثال JavaScript.

---

## Symmetric Difference

تفاضل متقارن:

```text
A △ B
```

مثال JavaScript.

---

# 40. متدهای جدید Set

متدهای جدید Set را نیز پوشش بده، در صورت پشتیبانی در استاندارد فعلی JavaScript.

بررسی کن:

```javascript
union()
intersection()
difference()
symmetricDifference()
isSubsetOf()
isSupersetOf()
isDisjointFrom()
```

برای هرکدام:

* مفهوم
* syntax
* مثال
* خروجی
* کاربرد واقعی

را توضیح بده.

همچنین وضعیت پشتیبانی مرورگرها را در صورت نیاز از MDN بررسی کن.

---

# 41. Map.groupBy()

در بخش پیشرفته این قابلیت را آموزش بده:

```javascript
Map.groupBy()
```

توضیح بده:

* Map.groupBy چیست؟
* چه زمانی استفاده می‌شود؟
* callback چه چیزی برمی‌گرداند؟
* چرا خروجی Map است؟
* تفاوت آن با Object.groupBy چیست؟

مثال واقعی:

```javascript
const products = [
    { name: "Laptop", category: "tech" },
    { name: "Phone", category: "tech" },
    { name: "Apple", category: "food" }
];
```

محصولات را بر اساس category گروه‌بندی کن.

همچنین زمان معرفی و وضعیت پشتیبانی آن را از MDN بررسی کن. `Map.groupBy()` از قابلیت‌های نسبتاً جدید JavaScript است و MDN آن را از مارس 2024 در مرورگرهای جدید در دسترس می‌داند.

---

# 42. WeakMap و WeakSet

در پایان بخش Map و Set، یک مقدمه نسبتاً کامل درباره:

```javascript
WeakMap
WeakSet
```

ارائه کن.

توضیح بده:

* WeakMap چیست؟
* WeakSet چیست؟
* تفاوت Map و WeakMap
* تفاوت Set و WeakSet
* Garbage Collection
* چرا WeakMap و WeakSet iterable نیستند؟
* چه زمانی باید از آن‌ها استفاده کرد؟

یک مثال ساده از کاربرد WeakMap نیز ارائه کن.

---

# 43. Garbage Collection و Map / WeakMap

در سطح پیشرفته توضیح بده:

* Reference چیست؟
* Garbage Collection چیست؟
* چرا نگه داشتن reference می‌تواند روی lifecycle Object تأثیر بگذارد؟
* WeakMap چه مشکلی را حل می‌کند؟

این بخش باید ساده شروع شود و سپس وارد جزئیات شود.

---

# 44. Performance و Complexity

یک بخش مقدماتی درباره Big O ارائه کن.

سپس درباره عملیات‌هایی مانند:

```text
Map.get()
Map.set()
Map.has()
Map.delete()

Set.add()
Set.has()
Set.delete()
```

توضیح بده.

حتماً تأکید کن که ECMAScript الزام نمی‌کند Map یا Set حتماً با Hash Table پیاده‌سازی شوند؛ Specification فقط الزاماتی درباره رفتار و دسترسی sublinear در حالت متوسط دارد. بنابراین درباره implementation داخلی موتورهای مختلف JavaScript با قطعیت غیرضروری صحبت نکن.

---

# 45. اشتباهات رایج Map

نمونه اشتباهات:

```javascript
const map = new Map();

map["name"] = "Ali";
```

توضیح بده چرا این روش برای ذخیره entry در Map صحیح نیست.

روش صحیح:

```javascript
map.set("name", "Ali");
```

همچنین اشتباهات مربوط به:

* Object keys
* undefined
* duplicate keys
* iteration
* size
* تبدیل Map به Object

را بررسی کن.

MDN نیز صراحتاً توضیح می‌دهد که اضافه کردن property با `map["key"]` با ساختار داخلی Map یکی نیست و برای ذخیره entry باید از `set()` استفاده شود.

---

# 46. اشتباهات رایج Set

اشتباهات مربوط به:

* انتظار index داشتن
* استفاده از `length`
* انتظار نگهداری duplicate
* مقایسه Objectها
* اشتباه در تبدیل Set به Array

را با مثال توضیح بده.

---

# 47. Map یا Set یا Object یا Array؟

یک راهنمای تصمیم‌گیری بساز.

مثلاً:

```text
آیا داده‌ها key/value هستند؟
        |
       بله
        |
       Map

آیا فقط مقادیر یکتا نیاز داریم؟
        |
       بله
        |
       Set

آیا ترتیب و index مهم است؟
        |
       بله
        |
      Array

آیا داده‌ها property-based و object-like هستند؟
        |
       بله
        |
      Object
```

اما تأکید کن که این فقط یک راهنمای اولیه است و انتخاب نهایی به نیاز برنامه بستگی دارد.

---

# 48. پروژه‌های کوچک عملی

حداقل 5 تمرین عملی طراحی کن:

## Project 1

حذف Duplicate از لیست کاربران/اعداد با Set

## Project 2

ساخت User Cache با Map

## Project 3

Frequency Counter

## Project 4

Grouping محصولات با Map

## Project 5

سیستم ساده Permission با Set

برای هر پروژه:

* مسئله
* ورودی
* خروجی مورد انتظار
* راهنمای حل
* راه‌حل
* توضیح کد

ارائه کن.

---

# 49. تمرین‌های پایان فصل

حداقل 15 سؤال تمرینی طراحی کن.

سطح‌بندی:

### Beginner

5 سؤال

### Intermediate

5 سؤال

### Advanced

5 سؤال

سؤالات باید بیشتر عملی باشند تا حفظی.

---

# 50. سؤالات مصاحبه JavaScript

حداقل 15 سؤال مصاحبه‌ای درباره Map و Set ارائه کن.

مثلاً:

* Map چیست؟
* تفاوت Map و Object چیست؟
* تفاوت Set و Array چیست؟
* آیا Object می‌تواند key در Map باشد؟
* چرا دو Object مشابه در Set دو مقدار متفاوت محسوب می‌شوند؟
* SameValueZero چیست؟
* Map.groupBy چیست؟
* WeakMap چه تفاوتی با Map دارد؟
* چرا WeakMap قابل iteration نیست؟
* چه زمانی از Set استفاده می‌کنیم؟

برای هر سؤال پاسخ واضح و کوتاه ارائه کن.

---

# 51. Cheat Sheet

در پایان یک Cheat Sheet کامل ارائه کن.

مثلاً:

```text
MAP

new Map()
set()
get()
has()
delete()
clear()
size
keys()
values()
entries()
forEach()
Map.groupBy()
```

و:

```text
SET

new Set()
add()
has()
delete()
clear()
size
keys()
values()
entries()
forEach()
union()
intersection()
difference()
symmetricDifference()
isSubsetOf()
isSupersetOf()
isDisjointFrom()
```

---

# 52. جدول مقایسه نهایی

یک جدول ساده و خوانا برای مقایسه:

```text
Array
Object
Map
Set
WeakMap
WeakSet
```

بر اساس:

* نوع داده
* duplicate
* key/value
* index
* iteration
* size
* کاربرد
* object key
* garbage collection
* مثال کاربردی

---

# 53. جمع‌بندی

در پایان:

* Map را در چند جمله خلاصه کن.
* Set را در چند جمله خلاصه کن.
* تفاوت اصلی آن‌ها را بگو.
* موارد استفاده واقعی را جمع‌بندی کن.
* اشتباهات مهم را یادآوری کن.
* مسیر یادگیری بعدی را پیشنهاد بده.

---

# 54. منابع معتبر

در پایان فقط از منابع معتبر استفاده کن و منابع را با لینک مستقیم ارائه بده.

اولویت منابع:

1. MDN Web Docs
2. ECMAScript / TC39
3. JavaScript.info در صورت مرتبط بودن
4. Microsoft Learn در صورت وجود مستندات مرتبط

حداقل منابع اصلی:

* MDN — Map
* MDN — Set
* MDN — Keyed Collections
* MDN — WeakMap
* MDN — WeakSet
* MDN — Map.groupBy
* ECMAScript Specification — Keyed Collections

برای هر منبع:

```text
نام منبع
توضیح کوتاه
لینک معتبر
```

ارائه کن.

---

# فرمت نهایی Repository

خروجی را به شکلی بنویس که بتوانم مستقیماً داخل فایل:

```text
README.md
```

قرار دهم.

ساختار Markdown رعایت شود.

در ابتدای فایل یک عنوان اصلی قرار بده:

# JavaScript Data Structures — Map & Set

سپس یک توضیح کوتاه درباره هدف آموزش.

بعد:

## فهرست مطالب

برای تمام Headingهای اصلی لینک داخلی Markdown ایجاد کن.

مثلاً:

```markdown
- [Map چیست؟](#map-چیست)
- [ساخت Map](#ساخت-map)
- [متدهای Map](#متدهای-map)
- [Set چیست؟](#set-چیست)
```

از Headingهای منظم استفاده کن:

```text
# سطح اصلی
## بخش
### زیربخش
```

---

# استاندارد نوشتن مثال‌ها

هر مثال مهم را با این ساختار بنویس:

### مثال

```javascript
const map = new Map();

map.set("name", "Ali");

console.log(map.get("name"));
```

### خروجی

```text
Ali
```

### توضیح

خط‌به‌خط توضیح بده که چه اتفاقی افتاده است.

---

# نکته بسیار مهم

محتوا را صرفاً به شکل فهرست API ننویس.

هدف آموزش این است که خواننده **واقعاً بفهمد Map و Set چه هستند، چرا وجود دارند، چه مشکلی را حل می‌کنند، چه زمانی باید از آن‌ها استفاده کند و چه تفاوتی با Object و Array دارند.**

مسیر آموزش باید:

```text
مفهوم
↓
مثال ساده
↓
Syntax
↓
API
↓
مثال واقعی
↓
مقایسه
↓
اشتباهات رایج
↓
Performance
↓
مباحث پیشرفته
↓
تمرین
↓
پروژه
↓
مصاحبه
↓
Cheat Sheet
```

باشد.

تمام ادعاهای فنی مهم را با منابع معتبر تطبیق بده و در انتهای آموزش منابع را با لینک معتبر قرار بده.


### ASSISTANT
# JavaScript Data Structures — Map & Set

این آموزش جامع، مرحله‌به‌مرحله و از مقدماتی تا پیشرفته، برای درک عمیق ساختارهای داده‌ی `Map` و `Set` در جاوااسکریپت طراحی شده است. هدف این است که نه‌تنها با سینتکس (Syntax) آشنا شوید، بلکه بفهمید این ساختارها چه مشکلی را حل می‌کنند، چه زمانی باید از آن‌ها استفاده کنید و چگونه در سطح موتور جاوااسکریپت کار می‌کنند.

---

## فهرست مطالب

- [1. مقدمه: Data Structure چیست؟](#1-مقدمه-data-structure-چیست)
- [2. جایگاه Map و Set در JavaScript](#2-جایگاه-map-و-set-در-javascript)
- [3. Map چیست؟](#3-map-چیست)
- [4. ساخت Map](#4-ساخت-map)
- [5. افزودن داده با set()](#5-افزودن-داده-با-set)
- [6. دریافت داده با get()](#6-دریافت-داده-با-get)
- [7. بررسی وجود Key با has()](#7-بررسی-وجود-key-با-has)
- [8. حذف داده با delete()](#8-حذف-داده-با-delete)
- [9. حذف تمام داده‌ها با clear()](#9-حذف-تمام-داده‌ها-با-clear)
- [10. تعداد عناصر با size](#10-تعداد-عناصر-با-size)
- [11. Iteration روی Map](#11-iteration-روی-map)
- [12. متد keys()](#12-متد-keys)
- [13. متد values()](#13-متد-values)
- [14. متد entries()](#14-متد-entries)
- [15. متد forEach() در Map](#15-متد-foreach-در-map)
- [16. ترتیب داده‌ها در Map](#16-ترتیب-داده‌ها-در-map)
- [17. Key Equality در Map](#17-key-equality-در-map)
- [18. Object به عنوان Key در Map](#18-object-به-عنوان-key-در-map)
- [19. Function به عنوان Key](#19-function-به-عنوان-key)
- [20. Map در مقابل Object](#20-map-در-مقابل-object)
- [21. Map در مقابل Array](#21-map-در-مقابل-array)
- [22. تبدیل Map به Array](#22-تبدیل-map-به-array)
- [23. تبدیل Array به Map](#23-تبدیل-array-به-map)
- [24. تبدیل Object به Map](#24-تبدیل-object-به-map)
- [25. کاربردهای واقعی Map](#25-کاربردهای-واقعی-map)
- [26. ساخت Frequency Counter با Map](#26-ساخت-frequency-counter-با-map)
- [27. Set چیست؟](#27-set-چیست)
- [28. ساخت Set](#28-ساخت-set)
- [29. متد add()](#29-متد-add)
- [30. متد has() در Set](#30-متد-has-در-set)
- [31. متد delete() در Set](#31-متد-delete-در-set)
- [32. متد clear() در Set](#32-متد-clear-در-set)
- [33. ویژگی size در Set](#33-ویژگی-size-در-set)
- [34. Iteration در Set](#34-iteration-در-set)
- [35. حذف Duplicate از Array با Set](#35-حذف-duplicate-از-array-با-set)
- [36. Set و Equality](#36-set-و-equality)
- [37. Object در Set](#37-object-در-set)
- [38. Set در مقابل Array](#38-set-در-مقابل-array)
- [39. عملیات مجموعه‌ای با Set](#39-عملیات-مجموعه‌ای-با-set)
- [40. متدهای جدید Set](#40-متدهای-جدید-set)
- [41. متد Map.groupBy()](#41-متد-mapgroupby)
- [42. WeakMap و WeakSet](#42-weakmap-و-weakset)
- [43. Garbage Collection و Map / WeakMap](#43-garbage-collection-و-map--weakmap)
- [44. Performance و Complexity](#44-performance-و-complexity)
- [45. اشتباهات رایج Map](#45-اشتباهات-رایج-map)
- [46. اشتباهات رایج Set](#46-اشتباهات-رایج-set)
- [47. راهنمای تصمیم‌گیری: Map یا Set یا Object یا Array؟](#47-راهنمای-تصمیم‌گیری-map-یا-set-یا-object-یا-array)
- [48. پروژه‌های کوچک عملی](#48-پروژه‌های-کوچک-عملی)
- [49. تمرین‌های پایان فصل](#49-تمرین‌های-پایان-فصل)
- [50. سؤالات مصاحبه JavaScript](#50-سؤالات-مصاحبه-javascript)
- [51. Cheat Sheet](#51-cheat-sheet)
- [52. جدول مقایسه نهایی](#52-جدول-مقایسه-نهایی)
- [53. جمع‌بندی](#53-جمع‌بندی)
- [54. منابع معتبر](#54-منابع-معتبر)

---

## 1. مقدمه: Data Structure چیست؟

**ساختار داده (Data Structure)** روشی برای سازماندهی، ذخیره و مدیریت داده‌ها در کامپیوتر است تا دسترسی و اصلاح آن‌ها به‌صورت کارآمد انجام شود.
ما به Data Structure نیاز داریم زیرا داده‌های خام به‌تنهایی قابل مدیریت نیستند. ساختار مناسب باعث افزایش سرعت، کاهش مصرف حافظه و خوانایی کد می‌شود.

جاوااسکریپت ساختارهای داده‌ی اصلی زیر را دارد:
- **Array (آرایه)**: مجموعه‌ای مرتب از داده‌ها که با اندیس (Index) عددی دسترسی پیدا می‌کنیم.
- **Object (شیء)**: مجموعه‌ای از جفت‌های Key/Value که در آن Keyها فقط می‌توانند String یا Symbol باشند.
- **Map**: مجموعه‌ای از جفت‌های Key/Value که در آن Key می‌تواند **هر نوع داده‌ای** باشد و ترتیب درج حفظ می‌شود.
- **Set**: مجموعه‌ای از مقادیر **یکتا (Unique)** که ترتیب درج را حفظ می‌کند.
- **WeakMap**: مشابه Map، اما Keyها باید Object باشند و به‌صورت "ضعیف" (Weak) نگهداری می‌شوند (قابل Garbage Collection هستند).
- **WeakSet**: مشابه Set، اما فقط Object را می‌پذیرد و به‌صورت "ضعیف" نگهداری می‌شود.

**چرا JavaScript علاوه بر Array و Object، به Map و Set نیاز داشت؟**
Objectها محدودیت‌هایی دارند: Keyها فقط String/Symbol هستند، ترتیب عناصر (در نسخه‌های قدیمی) تضمین‌شده نبود، ویژگی `size` برای شمارش سریع وجود نداشت و ممکن بود با Keyهای تصادفی (مثل `toString`) تداخل ایجاد شود. Map و Set در ES6 (2015) معرفی شدند تا این خلاءها را پر کنند.

---

## 2. جایگاه Map و Set در JavaScript

Map و Set جزو **Keyed Collections** (مجموعه‌های کلیددار) هستند.
- **Iterable**: هر دو ساختار Iterable (قابل پیمایش) هستند، یعنی می‌توان روی آن‌ها از `for...of` یا Spread Operator (`...`) استفاده کرد.

تفاوت‌های کلیدی:
- **با Array**: آرایه بر اساس Index عددی مرتب است، اما Map بر اساس Key و Set بر اساس یکتایی مقادیر.
- **با Object**: Object برای ساختارهای ثابت و داده‌های JSON-like است، اما Map برای دیکشنری‌های پویا با Keyهای متنوع طراحی شده است.

تصویر ذهنی ساده:
```text
Array
 └── ordered collection (مجموعه مرتب با اندیس عددی)

Object
 └── property → value (فقط String/Symbol به عنوان کلید)

Map
 └── key → value (هر نوع داده‌ای می‌تواند کلید باشد، حفظ ترتیب)

Set
 └── unique values (فقط مقادیر یکتا، بدون کلید)
```

---

## 3. Map چیست؟

**Map** یک ساختار داده است که داده‌ها را به‌صورت جفت‌های **Key/Value** (کلید/مقدار) ذخیره می‌کند.
برخلاف Object، در Map کلید می‌تواند **هر نوع داده‌ای** باشد: String، Number، Boolean، Object، Function، Symbol یا حتی `NaN`.

### مثال
```javascript
const users = new Map();

users.set("name", "Ali");
users.set("age", 25);
```
### خروجی
```text
Map(2) { 'name' => 'Ali', 'age' => 25 }
```
### توضیح
ما یک Map خالی ساختیم و دو جفت کلید/مقدار به آن اضافه کردیم. Map این داده‌ها را دقیقاً به همان ترتیبی که وارد شده‌اند، نگه می‌دارد.

---

## 4. ساخت Map

### Empty Map (Map خالی)
```javascript
const map = new Map();
```

### Map با Array از Entries
```javascript
const map = new Map([
    ["name", "Ali"],
    ["age", 25]
]);
```
### توضیح
- **Entry**: به هر جفت `[key, value]` یک Entry گفته می‌شود.
- **Map Constructor**: وقتی یک Iterable (مثل آرایه‌ای از آرایه‌ها) به `new Map()` می‌دهیم، آن را پیمایش کرده و هر زیرآرایه را به‌عنوان یک `[key, value]` در نظر می‌گیرد.

---

## 5. افزودن داده با set()

متد `set(key, value)` یک جفت کلید/مقدار به Map اضافه می‌کند.

### بررسی رفتار:
- اگر key وجود نداشته باشد، اضافه می‌شود.
- اگر key قبلاً وجود داشته باشد، مقدار آن **به‌روزرسانی** (Override) می‌شود.
- متد `set` خودِ Map را برمی‌گرداند، بنابراین امکان **Method Chaining** (زنجیره‌سازی متدها) وجود دارد.

### مثال
```javascript
const map = new Map();

map
    .set("name", "Ali")
    .set("age", 25)
    .set("city", "Sari");

console.log(map.get("city"));
```
### خروجی
```text
Sari
```

---

## 6. دریافت داده با get()

متد `get(key)` مقدار مرتبط با کلید را برمی‌گرداند.

### بررسی رفتار:
- اگر key وجود داشته باشد، مقدار آن برگردانده می‌شود.
- اگر key وجود نداشته باشد، مقدار `undefined` برگردانده می‌شود.

### مثال
```javascript
const map = new Map();
map.set("name", "Ali");

console.log(map.get("name")); // Ali
console.log(map.get("age"));  // undefined
```
**نکته مهم**: اگر واقعاً مقدار `undefined` را برای یک کلید ذخیره کرده باشید، `get` نیز `undefined` برمی‌گرداند. برای تشخیص اینکه آیا کلید اصلاً وجود دارد یا خیر، باید از `has()` استفاده کنید.

---

## 7. بررسی وجود Key با has()

متد `has(key)` یک مقدار Boolean (`true` یا `false`) برمی‌گرداند که نشان می‌دهد آیا کلید در Map وجود دارد یا خیر.

### مثال
```javascript
const map = new Map();
map.set("active", undefined);

console.log(map.has("active")); // true (کلید وجود دارد، حتی اگر مقدارش undefined باشد)
console.log(map.has("name"));   // false
```
**چرا به جای `get` از `has` استفاده کنیم؟** وقتی مقدار ذخیره‌شده ممکن است عمداً `undefined` یا `null` باشد، `get` نمی‌تواند بین "کلید وجود ندارد" و "مقدار کلید undefined است" تمایز قائل شود، اما `has` این تمایز را به‌دقت انجام می‌دهد.

---

## 8. حذف داده با delete()

متد `delete(key)` یک Entry را حذف می‌کند.

### بررسی رفتار:
- اگر کلید وجود داشته و حذف شود، `true` برمی‌گرداند.
- اگر کلید وجود نداشته باشد، `false` برمی‌گرداند.

### مثال
```javascript
const map = new Map([["a", 1], ["b", 2]]);

console.log(map.delete("a")); // true
console.log(map.delete("c")); // false
console.log(map.size);        // 1
```

---

## 9. حذف تمام داده‌ها با clear()

متد `clear()` تمام Entryهای Map را یک‌جا حذف می‌کند.
تفاوت آن با `delete` این است که `delete` تک‌تک عمل می‌کند و نیاز به دانستن کلید دارد، اما `clear` بدون آرگومان، کل ساختار را خالی می‌کند.

### مثال
```javascript
const map = new Map([["a", 1], ["b", 2]]);
map.clear();
console.log(map.size); // 0
```

---

## 10. تعداد عناصر با size

ویژگی `size` تعداد جفت‌های Key/Value موجود در Map را برمی‌گرداند.
**تفاوت با `array.length`**: در آرایه، `length` نشان‌دهنده‌ی بالاترین اندیس عددی + 1 است و ممکن است با تعداد واقعی عناصر متفاوت باشد (در آرایه‌های پراکنده یا Sparse). اما `size` در Map همیشه دقیقاً برابر با تعداد Entryهای واقعی است.

---

## 11. Iteration روی Map

Mapها Iterable هستند، بنابراین می‌توان به‌راحتی روی آن‌ها پیمایش کرد.

### for...of
```javascript
const map = new Map([["name", "Ali"], ["age", 25]]);

for (const item of map) {
    console.log(item);
}
```
### خروجی
```text
[ 'name', 'Ali' ]
[ 'age', 25 ]
```
### توضیح
هر آیتم در پیمایش، خود یک آرایه به‌صورت `[key, value]` است.

### Destructuring در Map
برای دسترسی مستقیم به کلید و مقدار، از Destructuring استفاده می‌کنیم:
```javascript
for (const [key, value] of map) {
    console.log(`${key}: ${value}`);
}
```
### خروجی
```text
name: Ali
age: 25
```

---

## 12. متد keys()

یک Iterator جدید برمی‌گرداند که فقط شامل **کلیدها** است.
```javascript
const map = new Map([["a", 1], ["b", 2]]);
for (const key of map.keys()) {
    console.log(key); // a, b
}
```

---

## 13. متد values()

یک Iterator جدید برمی‌گرداند که فقط شامل **مقادیر** است.
```javascript
for (const value of map.values()) {
    console.log(value); // 1, 2
}
```

---

## 14. متد entries()

یک Iterator برمی‌گرداند که شامل `[key, value]` است. این رفتار پیش‌فرض Map در `for...of` است.
```javascript
for (const entry of map.entries()) {
    console.log(entry); // ['a', 1], ['b', 2]
}
```

---

## 15. متد forEach() در Map

مشابه `forEach` در آرایه، اما ترتیب پارامترهای Callback متفاوت است.

### مثال
```javascript
const map = new Map([["name", "Ali"], ["age", 25]]);

map.forEach((value, key, currentMap) => {
    console.log(`${key} = ${value}`);
});
```
### خروجی
```text
name = Ali
age = 25
```
### توضیح
در آرایه، پارامتر اول `value` و دوم `index` است. در Map، پارامتر اول `value` و دوم `key` است (برای سازگاری با متد `forEach` در Objectهای قدیمی و Map در زبان‌های دیگر).

---

## 16. ترتیب داده‌ها در Map

بله، Map **ترتیب درج (Insertion Order)** را حفظ می‌کند.
اگر یک کلید را دوباره `set` کنید، مقدار آن به‌روزرسانی می‌شود اما **ترتیب آن تغییر نمی‌کند** (در جایگاه اولیه‌ی خود باقی می‌ماند).

### مثال
```javascript
const map = new Map();
map.set("a", 1);
map.set("b", 2);
map.set("a", 3); // به‌روزرسانی

console.log([...map.keys()]); // ['a', 'b'] (ترتیب عوض نشد)
```

---

## 17. Key Equality در Map

Map برای بررسی برابری کلیدها از الگوریتم **SameValueZero** استفاده می‌کند. این الگوریتم شبیه `===` است، با دو تفاوت مهم:
1. `NaN` با `NaN` برابر در نظر گرفته می‌شود (برخلاف `===` که `NaN === NaN` مقدار `false` می‌دهد).
2. `0` و `-0` برابر در نظر گرفته می‌شوند.

### مثال NaN
```javascript
const map = new Map();
map.set(NaN, "hello");

console.log(map.get(NaN)); // "hello" (در Object این کار ممکن نبود)
```

### مثال Object Reference
```javascript
const user1 = {};
const user2 = {};
const map = new Map();

map.set(user1, "Ali");

console.log(map.get(user1)); // "Ali"
console.log(map.get(user2)); // undefined
```
### توضیح
`user1` و `user2` هر دو Object خالی هستند، اما **Reference** (آدرس حافظه) متفاوتی دارند. Map بر اساس Reference مقایسه می‌کند، نه محتوای Object.

---

## 18. Object به عنوان Key در Map

این یکی از قدرتمندترین ویژگی‌های Map است. شما می‌توانید یک Object را به‌عنوان کلید استفاده کنید.

### مثال
```javascript
const user = { id: 1 };
const map = new Map();

map.set(user, "Admin");

console.log(map.get(user)); // "Admin"
```
### توضیح
اینجا `user` به‌عنوان Reference ذخیره می‌شود. تا زمانی که Reference دقیقاً همان شیء باشد، مقدار بازیابی می‌شود. این برای نگاشت متادیتا به اشیاء (مثلاً گره‌های DOM) بسیار کاربرد دارد.

---

## 19. Function به عنوان Key

توابع در جاوااسکریپت نیز Object هستند، بنابراین می‌توانند به‌عنوان Key استفاده شوند.

### مثال
```javascript
function test() {}
const map = new Map();
map.set(test, "some value");

console.log(map.get(test)); // "some value"
```
این ویژگی برای ذخیره‌سازی Cache مرتبط با توابع خاص یا متادیتای توابع مفید است.

---

## 20. Map در مقابل Object

| ویژگی | Object | Map |
| :--- | :--- | :--- |
| **نوع Key** | فقط String و Symbol | هر نوع داده‌ای (Number, Object, Function, ...) |
| **حفظ ترتیب** | خیر (به‌جز در موارد خاص و نسخه‌های جدید) | بله، همیشه Insertion Order حفظ می‌شود |
| **تعداد عناصر** | باید دستی محاسبه شود (`Object.keys().length`) | ویژگی `size` دارد |
| **Iteration** | نیاز به `Object.keys/values/entries` دارد | مستقیماً Iterable است (`for...of`) |
| **Performance** | برای افزودن/حذف مکرر کلیدها بهینه نیست | برای افزودن/حذف مکرر بهینه‌تر است |
| **Prototype** | کلیدهای تصادفی ممکن است با متدهای Prototype تداخل کنند | هیچ تداخلی با کلیدهای از پیش تعریف‌شده ندارد |
| **Serialization** | پشتیبانی کامل توسط `JSON.stringify` | پشتیبانی نمی‌شود (باید تبدیل شود) |

**نتیجه‌گیری**: اگر داده‌های شما ساختار ثابت، JSON-like و با کلیدهای رشته‌ای دارند، از Object استفاده کنید. اگر نیاز به کلیدهای پویا، حفظ ترتیب یا عملکرد بهتر در افزودن/حذف مکرر دارید، Map انتخاب بهتری است.

---

## 21. Map در مقابل Array

- **Array** زمانی مناسب است که داده‌ها مرتب باشند و نیاز به دسترسی بر اساس اندیس عددی، یا استفاده از متدهایی مثل `map`، `filter`، `find` داشته باشید.
- **Map** زمانی مناسب است که نیاز به جستجوی سریع بر اساس یک "کلید" خاص (مثلاً ID) داشته باشید.

### مثال مقایسه جستجو
```javascript
// با Array (پیچیدگی زمانی O(n))
const usersArray = [{ id: 1, name: "Ali" }, { id: 2, name: "Reza" }];
const user = usersArray.find(u => u.id === 2);

// با Map (پیچیدگی زمانی متوسط O(1))
const usersMap = new Map([[1, "Ali"], [2, "Reza"]]);
const userName = usersMap.get(2);
```
*توجه*: اگرچه موتورهای JS معمولاً Map را با Hash Table پیاده‌سازی می‌کنند که دسترسی O(1) دارد، اما Spec جاوااسکریپت فقط دسترسی Sublinear (زیرخطی) را تضمین می‌کند. با این حال، در عمل Map برای Lookup بسیار سریع‌تر از `Array.find` است.

---

## 22. تبدیل Map به Array

به دلیل Iterable بودن Map، تبدیل آن به آرایه بسیار ساده است:

```javascript
const map = new Map([["a", 1], ["b", 2]]);

// 1. با Spread Operator
const arr1 = [...map]; // [['a', 1], ['b', 2]]

// 2. با Array.from
const arr2 = Array.from(map);

// فقط کلیدها
const keys = [...map.keys()]; // ['a', 'b']

// فقط مقادیر
const values = [...map.values()]; // [1, 2]
```

---

## 23. تبدیل Array به Map

همان‌طور که در بخش ساخت دیدیم، Constructor Map یک Iterable از `[key, value]` را می‌پذیرد.

### مثال
```javascript
const users = [
    [1, "Ali"],
    [2, "Reza"],
    [3, "Sara"]
];

const userMap = new Map(users);
console.log(userMap.get(2)); // "Reza"
```

---

## 24. تبدیل Object به Map

### Object به Map
با استفاده از `Object.entries()`:
```javascript
const user = { name: "Ali", age: 25 };
const map = new Map(Object.entries(user));
console.log(map.get("name")); // "Ali"
```

### Map به Object
با استفاده از `Object.fromEntries()` (معرفی‌شده در ES2019):
```javascript
const map = new Map([["name", "Ali"], ["age", 25]]);
const obj = Object.fromEntries(map);
console.log(obj.name); // "Ali"
```
**محدودیت**: اگر کلیدهای Map از نوع Object یا Number باشند، هنگام تبدیل به Object، همه به String تبدیل می‌شوند که ممکن است باعث تداخل شود.

---

## 25. کاربردهای واقعی Map

1. **User Lookup**: ذخیره کاربران با ID به‌عنوان کلید برای جستجوی O(1).
2. **Cache**: ذخیره‌سازی نتایج محاسبات سنگین با آرگومان‌های تابع به‌عنوان کلید.
3. **Counting**: شمارش تکرار آیتم‌ها.
4. **Grouping**: گروه‌بندی داده‌ها بر اساس یک ویژگی خاص.
5. **Memoization**: ذخیره خروجی تابع برای ورودی‌های خاص جهت جلوگیری از محاسبه مجدد.

---

## 26. ساخت Frequency Counter با Map

محاسبه‌ی تعداد تکرار هر کلمه در یک آرایه.

### مثال
```javascript
const words = ["js", "csharp", "js", "python", "js"];
const frequency = new Map();

for (const word of words) {
    const count = frequency.get(word) || 0;
    frequency.set(word, count + 1);
}

console.log(frequency);
```
### خروجی
```text
Map(3) { 'js' => 3, 'csharp' => 1, 'python' => 1 }
```
### توضیح خط‌به‌خط:
1. روی هر کلمه در آرایه پیمایش می‌کنیم.
2. با `get` تعداد فعلی را می‌گیریم. اگر وجود نداشت (`undefined`)، مقدار پیش‌فرض `0` را در نظر می‌گیریم.
3. با `set` مقدار جدید (تعداد فعلی + 1) را ذخیره می‌کنیم.

---

## 27. Set چیست؟

**Set** یک ساختار داده است که فقط مقادیر **یکتا (Unique)** را ذخیره می‌کند. Set کلید (Key) ندارد، فقط مقدار (Value) دارد.
- آیا مقدار تکراری قبول می‌کند؟ خیر، مقادیر تکراری نادیده گرفته می‌شوند.
- آیا ترتیب را حفظ می‌کند؟ بله، ترتیب درج (Insertion Order) حفظ می‌شود.

### مثال
```javascript
const numbers = new Set();
numbers.add(10);
numbers.add(20);
numbers.add(10); // تکراری، نادیده گرفته می‌شود

console.log(numbers);
```
### خروجی
```text
Set(2) { 10, 20 }
```

---

## 28. ساخت Set

### Empty Set
```javascript
const set = new Set();
```

### Set از Array
```javascript
const set = new Set([1, 2, 3, 3, 4]);
console.log(set); // Set(4) { 1, 2, 3, 4 }
```
### توضیح
Constructor، آرایه را پیمایش کرده و فقط مقادیر یکتا را نگه می‌دارد. این سریع‌ترین راه برای حذف مقادیر تکراری از آرایه است.

---

## 29. متد add()

مقداری را به Set اضافه می‌کند. اگر مقدار تکراری باشد، تغییری ایجاد نمی‌شود. این متد خودِ Set را برمی‌گرداند (امکان Chaining).

### مثال
```javascript
const set = new Set();
set.add(1).add(2).add(3).add(2);

console.log(set); // Set(3) { 1, 2, 3 }
```

---

## 30. متد has() در Set

بررسی می‌کند که آیا یک مقدار در Set وجود دارد یا خیر.

### مثال
```javascript
const set = new Set(["apple", "banana"]);
console.log(set.has("apple"));  // true
console.log(set.has("orange")); // false
```

---

## 31. متد delete() در Set

یک مقدار را حذف می‌کند. اگر حذف موفقیت‌آمیز باشد `true`، در غیر این صورت `false` برمی‌گرداند.

### مثال
```javascript
const set = new Set([1, 2]);
console.log(set.delete(2)); // true
console.log(set.delete(3)); // false
```

---

## 32. متد clear() در Set

تمام مقادیر را از Set حذف می‌کند.

---

## 33. ویژگی size در Set

تعداد مقادیر یکتای موجود در Set را برمی‌گرداند.

---

## 34. Iteration در Set

Set نیز Iterable است.

```javascript
const set = new Set(["a", "b"]);

// for...of
for (const val of set) {
    console.log(val); // a, b
}

// متدها
console.log([...set.values()]); // ['a', 'b']
console.log([...set.keys()]);   // ['a', 'b'] (در Set، keys همان values است برای سازگاری با Map)
console.log([...set.entries()]); // [['a', 'a'], ['b', 'b']] (برای سازگاری با Map)

// forEach
set.forEach((value, key, currentSet) => {
    console.log(value); // در Set، value و key یکسان هستند
});
```

---

## 35. حذف Duplicate از Array با Set

این رایج‌ترین کاربرد Set در توسعه‌ی وب است.

### مثال
```javascript
const numbers = [1, 2, 2, 3, 4, 4, 5];

const uniqueNumbers = [...new Set(numbers)];

console.log(uniqueNumbers);
```
### خروجی
```text
[1, 2, 3, 4, 5]
```
### توضیح خط‌به‌خط:
1. `new Set(numbers)`: آرایه را به Set تبدیل می‌کند و مقادیر تکراری خودبه‌خود حذف می‌شوند.
2. `...` (Spread Operator): مقادیر یکتای Set را استخراج کرده و درون یک آرایه‌ی جدید `[]` قرار می‌دهد.

---

## 36. Set و Equality

Set نیز مانند Map از الگوریتم **SameValueZero** استفاده می‌کند.

```javascript
const set = new Set();
set.add(NaN);
set.add(NaN);
set.add(0);
set.add(-0);

console.log(set.size); // 2 (فقط NaN و 0، زیرا -0 و 0 یکسان هستند و NaN تکراری حذف شد)
```

---

## 37. Object در Set

همانند Map، Set بر اساس Reference مقایسه می‌کند.

### مثال
```javascript
const user1 = { id: 1 };
const user2 = { id: 1 };

const set = new Set();
set.add(user1);
set.add(user2);

console.log(set.size); // 2
```
### توضیح
با اینکه محتوای `user1` و `user2` یکسان است، اما دو شیء متفاوت در حافظه هستند، بنابراین هر دو در Set نگهداری می‌شوند.

---

## 38. Set در مقابل Array

| ویژگی | Array | Set |
| :--- | :--- | :--- |
| **مقادیر تکراری** | مجاز است | مجاز نیست (Unique) |
| **بررسی عضویت (Membership)** | `includes()` (پیچیدگی O(n)) | `has()` (پیچیدگی متوسط O(1)) |
| **دسترسی با اندیس** | بله (`arr[0]`) | خیر |
| **حذف عنصر** | `splice` یا `filter` (کند) | `delete()` (سریع) |
| **کاربرد اصلی** | لیست‌های مرتب، پردازش داده | مجموعه‌های یکتا، بررسی سریع وجود داده |

---

## 39. عملیات مجموعه‌ای با Set

می‌توان عملیات ریاضی مجموعه‌ها را با ترکیب Set و Array انجام داد.

### Union (اجتماع: A ∪ B)
```javascript
const a = new Set([1, 2, 3]);
const b = new Set([3, 4, 5]);
const union = new Set([...a, ...b]);
console.log(union); // Set(5) { 1, 2, 3, 4, 5 }
```

### Intersection (اشتراک: A ∩ B)
```javascript
const intersection = new Set([...a].filter(x => b.has(x)));
console.log(intersection); // Set(1) { 3 }
```

### Difference (تفاضل: A - B)
```javascript
const difference = new Set([...a].filter(x => !b.has(x)));
console.log(difference); // Set(2) { 1, 2 }
```

---

## 40. متدهای جدید Set

جاوااسکریپت اخیراً متدهای مجموعه‌ای بومی (Native) را به Set اضافه کرده است (پشتیبانی گسترده از 2024 به بعد در مرورگرهای مدرن). این متدها Set جدیدی برمی‌گردانند و زنجیره‌ای (Chainable) هستند.

### union()
```javascript
const a = new Set([1, 2]);
const b = new Set([2, 3]);
console.log(a.union(b)); // Set(3) { 1, 2, 3 }
```

### intersection()
```javascript
console.log(a.intersection(b)); // Set(1) { 2 }
```

### difference()
```javascript
console.log(a.difference(b)); // Set(1) { 1 } (عناصری که در a هستند ولی در b نیستند)
```

### symmetricDifference() (تفاضل متقارن)
```javascript
console.log(a.symmetricDifference(b)); // Set(2) { 1, 3 } (عناصری که فقط در یکی از دو مجموعه هستند)
```

### isSubsetOf() / isSupersetOf() / isDisjointFrom()
```javascript
const small = new Set([1]);
const big = new Set([1, 2, 3]);
const other = new Set([4, 5]);

console.log(small.isSubsetOf(big)); // true
console.log(big.isSupersetOf(small)); // true
console.log(small.isDisjointFrom(other)); // true (هیچ اشتراکی ندارند)
```

---

## 41. متد Map.groupBy()

این متد (معرفی‌شده در ES2024) یک آرایه را بر اساس یک تابع Callback گروه‌بندی کرده و نتیجه را در یک **Map** برمی‌گرداند.

### مثال
```javascript
const products = [
    { name: "Laptop", category: "tech" },
    { name: "Phone", category: "tech" },
    { name: "Apple", category: "food" }
];

const grouped = Map.groupBy(products, product => product.category);

console.log(grouped.get("tech"));
// [{ name: "Laptop", category: "tech" }, { name: "Phone", category: "tech" }]
```
### چرا Map برمی‌گرداند؟
زیرا کلید گروه‌بندی می‌تواند هر نوع داده‌ای باشد (مثلاً یک Object یا Number)، و Map بر خلاف Object، ترتیب و انواع کلید را به‌درستی مدیریت می‌کند. (توجه: `Object.groupBy()` نیز وجود دارد که نتیجه را در یک Object با پروتوتایپ null برمی‌گرداند).

---

## 42. WeakMap و WeakSet

### WeakMap
شبیه Map است، اما **کلیدها فقط می‌توانند Object باشند** (نه Primitiveها).
### WeakSet
شبیه Set است، اما **فقط می‌تواند Object نگه دارد**.

### تفاوت اصلی با Map/Set:
1. **Non-Iterable**: نمی‌توانید روی آن‌ها `for...of` اجرا کنید یا `keys()` بگیرید.
2. **Garbage Collection Friendly**: اگر هیچ Reference دیگری به Objectِ کلید (در WeakMap) یا مقدار (در WeakSet) وجود نداشته باشد، آن Object توسط موتور جاوااسکریپت از حافظه پاک می‌شود و Entry مربوطه در WeakMap/WeakSet نیز خودبه‌خود حذف می‌شود.

### چه زمانی استفاده کنیم؟
زمانی که می‌خواهید متادیتا یا Cache را به یک Object (مثلاً یک عنصر DOM) متصل کنید، اما نمی‌خواهید مانع از پاک شدن آن Object از حافظه شوید (جلوگیری از Memory Leak).

---

## 43. Garbage Collection و Map / WeakMap

**Garbage Collection (GC)** فرآیندی است که موتور JS اشیایی را که دیگر قابل دسترسی نیستند (No reachable references)، از حافظه پاک می‌کند.

### مشکل Map معمولی:
```javascript
let user = { name: "Ali" };
const map = new Map();
map.set(user, "Admin");

user = null; // Reference به شیء حذف شد
```
در اینجا، با اینکه `user = null` شد، اما `Map` هنوز یک Reference داخلی به آن شیء دارد. بنابراین GC نمی‌تواند آن را پاک کند و **Memory Leak** رخ می‌دهد.

### راه‌حل WeakMap:
```javascript
let user = { name: "Ali" };
const weakMap = new WeakMap();
weakMap.set(user, "Admin");

user = null; // حالا GC می‌تواند شیء { name: "Ali" } را پاک کند و Entry از WeakMap محو می‌شود.
```
به همین دلیل WeakMap قابل پیمایش نیست: موتور JS نمی‌تواند تضمین کند که چه زمانی یک Entry ممکن است توسط GC حذف شود، بنابراین لیست کردن کلیدها غیرممکن است.

---

## 44. Performance و Complexity

در نظریه‌ی Big O:
- `Map.get()`, `Map.set()`, `Map.has()`, `Map.delete()`: به‌طور متوسط **O(1)** (دسترسی ثابت).
- `Set.add()`, `Set.has()`, `Set.delete()`: به‌طور متوسط **O(1)**.

**نکته‌ی مهم Spec**: استاندارد ECMAScript الزام نمی‌کند که Map/Set حتماً با Hash Table پیاده‌سازی شوند، اما الزام می‌کند که دسترسی باید در حالت متوسط Sublinear (بهتر از O(n)) باشد. در عمل، تمام موتورهای مدرن (V8, SpiderMonkey) از Hash Table بهینه‌شده استفاده می‌کنند که عملکردی نزدیک به O(1) دارد. این باعث می‌شود `Map.has()` بسیار سریع‌تر از `Array.includes()` (که O(n) است) باشد.

---

## 45. اشتباهات رایج Map

### اشتباه 1: استفاده از سینتکس Object برای Map
```javascript
const map = new Map();
map["name"] = "Ali"; // اشتباه! این یک Property به خودِ شیء Map اضافه می‌کند، نه یک Entry.
console.log(map.size); // 0
```
**راه صحیح**: `map.set("name", "Ali")`

### اشتباه 2: انتظار داشته باشیم دو Object مشابه، یک کلید باشند.
```javascript
const map = new Map();
map.set({}, "value");
console.log(map.get({})); // undefined (دو {} متفاوت هستند)
```

### اشتباه 3: استفاده از `length`
Map ویژگی `length` ندارد. باید از `size` استفاده کنید.

---

## 46. اشتباهات رایج Set

### اشتباه 1: انتظار دسترسی با اندیس
```javascript
const set = new Set(["a", "b"]);
console.log(set[0]); // undefined (Set اندیس ندارد)
```

### اشتباه 2: استفاده از `length`
```javascript
const set = new Set([1, 2]);
console.log(set.length); // undefined (باید از set.size استفاده کرد)
```

### اشتباه 3: انتظار حذف تکراری‌ها در Objectها
```javascript
const set = new Set();
set.add({ id: 1 });
set.add({ id: 1 });
console.log(set.size); // 2 (چون Reference متفاوت است)
```

---

## 47. راهنمای تصمیم‌گیری: Map یا Set یا Object یا Array؟

```text
آیا داده‌ها جفت Key/Value هستند و کلید می‌تواند غیررشته‌ای باشد یا ترتیب مهم است؟
        |
       بله
        |
       Map
        |
       خیر
        ↓
آیا فقط به مقادیر یکتا (Unique) نیاز داریم و بررسی سریع عضویت مهم است؟
        |
       بله
        |
       Set
        |
       خیر
        ↓
آیا ترتیب عناصر و دسترسی با اندیس عددی (Index) مهم است؟
        |
       بله
        |
      Array
        |
       خیر
        ↓
آیا داده‌ها ساختار ثابت، JSON-like و با کلیدهای رشته‌ای دارند؟
        |
       بله
        |
      Object
```
*تذکر*: این یک راهنمای اولیه است. همیشه نیازهای خاص برنامه (مثل نیاز به Serialization برای Object/Array) را در نظر بگیرید.

---

## 48. پروژه‌های کوچک عملی

### Project 1: حذف Duplicate از لیست کاربران با Set
- **مسئله**: لیستی از اعداد داریم، اعداد تکراری را حذف کنید.
- **ورودی**: `[1, 2, 2, 3, 4, 4]`
- **خروجی**: `[1, 2, 3, 4]`
- **راه‌حل**:
```javascript
const deduplicate = (arr) => [...new Set(arr)];
console.log(deduplicate([1, 2, 2, 3, 4, 4]));
```

### Project 2: ساخت User Cache با Map
- **مسئله**: نتیجه‌ی یک تابع سنگین را بر اساس ID کاربر کش کنید.
- **راه‌حل**:
```javascript
const cache = new Map();
function getUserData(id) {
    if (cache.has(id)) return cache.get(id);
    
    const data = { id, name: "User " + id, fetchedAt: Date.now() }; // شبیه‌سازی عملیات سنگین
    cache.set(id, data);
    return data;
}
```

### Project 3: Frequency Counter
- **مسئله**: تعداد تکرار هر حرف در یک رشته را بشمارید.
- **راه‌حل**:
```javascript
function countChars(str) {
    const freq = new Map();
    for (const char of str) {
        freq.set(char, (freq.get(char) || 0) + 1);
    }
    return freq;
}
console.log(countChars("hello")); // Map { 'h' => 1, 'e' => 1, 'l' => 2, 'o' => 1 }
```

### Project 4: Grouping محصولات با Map.groupBy()
- **مسئله**: محصولات را بر اساس دسته‌بندی گروه‌بندی کنید.
- **راه‌حل**:
```javascript
const items = [{ type: "fruit", name: "Apple" }, { type: "fruit", name: "Banana" }, { type: "veg", name: "Carrot" }];
const grouped = Map.groupBy(items, item => item.type);
console.log(grouped.get("fruit")); // [{ type: "fruit", name: "Apple" }, ...]
```

### Project 5: سیستم ساده Permission با Set
- **مسئله**: بررسی کنید آیا کاربر دسترسی خاصی دارد یا خیر.
- **راه‌حل**:
```javascript
const userPermissions = new Set(["read", "write"]);
function hasPermission(permission) {
    return userPermissions.has(permission);
}
console.log(hasPermission("write")); // true
console.log(hasPermission("delete")); // false
```

---

## 49. تمرین‌های پایان فصل

### Beginner
1. یک Map بسازید و سه جفت کلید/مقدار به آن اضافه کنید.
2. بررسی کنید آیا یک کلید خاص در Map وجود دارد یا خیر.
3. یک آرایه با اعداد تکراری را با استفاده از Set به آرایه‌ای با اعداد یکتا تبدیل کنید.
4. تعداد عناصر یک Set را چاپ کنید.
5. تمام کلیدهای یک Map را با استفاده از `for...of` چاپ کنید.

### Intermediate
6. یک Map بسازید که از یک Object به‌عنوان کلید استفاده کند و مقدار آن را بازیابی کنید.
7. یک Map را به یک Object و سپس آن Object را دوباره به Map تبدیل کنید.
8. با استفاده از `Set`، اشتراک (Intersection) دو آرایه را پیدا کنید.
9. از Method Chaining برای اضافه کردن 5 مقدار متوالی به یک Map استفاده کنید.
10. یک Frequency Counter برای یک آرایه از رشته‌ها بنویسید.

### Advanced
11. توضیح دهید چرا `map.get({})` مقدار `undefined` برمی‌گرداند حتی اگر `map.set({}, "value")` را اجرا کرده باشیم.
12. یک WeakMap بسازید و نشان دهید چگونه با `null` کردن Reference، داده از حافظه پاک می‌شود (مفهومی).
13. با استفاده از متدهای جدید Set (`union`, `intersection`)، عملیات روی دو مجموعه را انجام دهید.
14. تفاوت الگوریتم `SameValueZero` با `===` را با ذکر مثال `NaN` توضیح دهید.
15. از `Map.groupBy()` برای گروه‌بندی یک آرایه از اشیاء بر اساس یک ویژگی عددی استفاده کنید.

---

## 50. سؤالات مصاحبه JavaScript

1. **Map چیست؟** ساختاری برای ذخیره جفت‌های Key/Value که در آن کلید می‌تواند هر نوع داده‌ای باشد و ترتیب درج حفظ می‌شود.
2. **تفاوت Map و Object چیست؟** Map کلیدهای غیررشته‌ای را می‌پذیرد، `size` دارد، Iterable است و ترتیب را تضمین می‌کند. Object فقط String/Symbol را به‌عنوان کلید می‌پذیرد.
3. **تفاوت Set و Array چیست؟** Set فقط مقادیر یکتا را نگه می‌دارد و دسترسی/حذف در آن سریع‌تر است، اما دسترسی با اندیس ندارد.
4. **آیا Object می‌تواند key در Map باشد؟** بله، و بر اساس Reference مقایسه می‌شود.
5. **چرا دو Object مشابه در Set دو مقدار متفاوت محسوب می‌شوند؟** زیرا مقایسه بر اساس Reference (آدرس حافظه) است، نه مقدار (Value).
6. **SameValueZero چیست؟** الگوریتم مقایسه‌ی Map/Set که شبیه `===` است، اما `NaN` را برابر با `NaN` و `0` را برابر با `-0` می‌داند.
7. **Map.groupBy چیست؟** متدی که یک آرایه را بر اساس Callback گروه‌بندی کرده و نتیجه را در یک Map برمی‌گرداند.
8. **WeakMap چه تفاوتی با Map دارد؟** کلیدهای WeakMap فقط Object هستند، قابل پیمایش نیستند و مانع Garbage Collection نمی‌شوند.
9. **چرا WeakMap قابل iteration نیست؟** زیرا GC می‌تواند هر لحظه کلیدها را پاک کند، بنابراین لیست کردن آن‌ها غیرقابل پیش‌بینی و غیرممکن است.
10. **چه زمانی از Set استفاده می‌کنیم؟** برای حذف تکراری‌ها از آرایه یا بررسی سریع عضویت (Membership checking).
11. **چرا `map["key"] = value` اشتباه است؟** زیرا این کار یک Property به خودِ شیء Map اضافه می‌کند، نه یک Entry در ساختار داده‌ی Map. باید از `map.set()` استفاده کرد.
12. **آیا Map ترتیب را حفظ می‌کند؟** بله، همیشه ترتیب درج (Insertion Order) حفظ می‌شود.
13. **چگونه Map را به آرایه تبدیل می‌کنیم؟** با استفاده از Spread Operator: `[...map]` یا `Array.from(map)`.
14. **پیچیدگی زمانی `Map.has()` چقدر است؟** به‌طور متوسط O(1).
15. **تفاوت `Object.groupBy` و `Map.groupBy` چیست؟** اولی یک Object با پروتوتایپ null برمی‌گرداند، دومی یک Map که از کلیدهای غیررشته‌ای و حفظ ترتیب پشتیبانی می‌کند.

---

## 51. Cheat Sheet

### MAP
```text
new Map([iterable])     // ساخت Map جدید
map.set(key, value)     // افزودن/به‌روزرسانی Entry
map.get(key)            // دریافت مقدار
map.has(key)            // بررسی وجود کلید (Boolean)
map.delete(key)         // حذف Entry
map.clear()             // حذف تمام Entryها
map.size                // تعداد Entryها
map.keys()              // Iterator کلیدها
map.values()            // Iterator مقادیر
map.entries()           // Iterator جفت‌های [key, value]
map.forEach(cb)         // پیمایش (value, key, map)
Map.groupBy(arr, cb)    // گروه‌بندی آرایه در Map (ES2024)
```

### SET
```text
new Set([iterable])     // ساخت Set جدید
set.add(value)          // افزودن مقدار
set.has(value)          // بررسی وجود مقدار (Boolean)
set.delete(value)       // حذف مقدار
set.clear()             // حذف تمام مقادیر
set.size                // تعداد مقادیر یکتا
set.union(other)        // اجتماع (ES جدید)
set.intersection(other) // اشتراک (ES جدید)
set.difference(other)   // تفاضل (ES جدید)
set.symmetricDifference // تفاضل متقارن (ES جدید)
set.isSubsetOf(other)   // بررسی زیرمجموعه (ES جدید)
```

---

## 52. جدول مقایسه نهایی

| ویژگی | Array | Object | Map | Set | WeakMap | WeakSet |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **نوع داده** | لیست مرتب | دیکشنری | دیکشنری پیشرفته | مجموعه یکتا | دیکشنری ضعیف | مجموعه ضعیف |
| **Duplicate** | مجاز | مجاز (در مقادیر) | مجاز (در مقادیر) | **غیرمجاز** | مجاز (در مقادیر) | **غیرمجاز** |
| **Key/Value** | Index/Value | String/Symbol -> Value | **هر نوع** -> Value | فقط Value | **فقط Object** -> Value | **فقط Object** |
| **حفظ ترتیب** | بله | خیر (عموماً) | **بله** | **بله** | خیر | خیر |
| **Iteration** | بله | غیرمستقیم | **بله (مستقیم)** | **بله (مستقیم)** | **خیر** | **خیر** |
| **Size/Length** | `length` | دستی | **`size`** | **`size`** | خیر | خیر |
| **Garbage Collection** | عادی | عادی | عادی (نگهدارنده قوی) | عادی (نگهدارنده قوی) | **ضعیف (Weak)** | **ضعیف (Weak)** |
| **کاربرد اصلی** | لیست داده‌ها | ساختار ثابت، JSON | Lookup پویا، کلیدهای متنوع | حذف تکراری، Membership | Cache متادیتای Object | ردیابی وضعیت Objectها |

---

## 53. جمع‌بندی

- **Map** یک ساختار داده‌ی کلید/مقدار است که انعطاف‌پذیری بیشتری نسبت به Object دارد (هر نوع کلید، حفظ ترتیب، `size`، و عملکرد بهتر در افزودن/حذف).
- **Set** مجموعه‌ای از مقادیر یکتا است که برای حذف تکراری‌ها و بررسی سریع وجود یک مقدار (Membership) بی‌نظیر است.
- **تفاوت اصلی**: Map برای نگاشت (Mapping) استفاده می‌شود، در حالی که Set برای نگهداری مجموعه‌ای از آیتم‌های منحصربه‌فرد به کار می‌رود.
- **اشتباهات مهم**: استفاده از سینتکس Object (`map["key"]`) برای Map، انتظار داشتن `length` در Set، و نادیده گرفتن تفاوت Reference در Objectها.
- **مسیر یادگیری بعدی**: مطالعه‌ی عمیق‌تر درباره الگوریتم‌های Hash Table، بررسی Internal Slots در موتور V8، و کار با `WeakRef` و `FinalizationRegistry` برای مدیریت پیشرفته حافظه.

---

## 54. منابع معتبر

برای اطمینان از صحت فنی و به‌روز بودن اطلاعات، به منابع اصلی زیر مراجعه کنید:

1. **MDN Web Docs — Map**  
   توضیحات کامل، مثال‌ها و سازگاری مرورگرها.  
   🔗 [developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)

2. **MDN Web Docs — Set**  
   راهنمای جامع متدها و عملیات جدید Set.  
   🔗 [developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

3. **MDN Web Docs — Keyed Collections**  
   نمای کلی از Map، Set، WeakMap و WeakSet.  
   🔗 [developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections)

4. **MDN Web Docs — Map.groupBy()**  
   مستندات رسمی متد جدید گروه‌بندی.  
   🔗 [developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/groupBy](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/groupBy)

5. **ECMAScript Specification — Keyed Collections**  
   استاندارد رسمی رفتار و الگوریتم SameValueZero.  
   🔗 [tc39.es/ecma262/#sec-keyed-collection](https://tc39.es/ecma262/#sec-keyed-collection)

6. **JavaScript.info — Map and Set**  
   آموزش روان و کاربردی با مثال‌های عالی.  
   🔗 [javascript.info/map-set](https://javascript.info/map-set)

---
*تهیه‌شده برای Repository آموزشی GitHub | به‌روزرسانی: 2026*
