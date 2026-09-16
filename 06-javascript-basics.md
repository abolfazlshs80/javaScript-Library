
1. [مقدمه](#مقدمه)
2. [Number در JavaScript](#number-در-javascript)
3. [اعداد صحیح و اعشاری](#اعداد-صحیح-و-اعشاری)
4. [اعداد منفی](#اعداد-منفی)
5. [Scientific Notation](#scientific-notation)
6. [toFixed](#tofixed)
7. [Number.MIN_VALUE](#numbermin_value)
8. [Infinity](#infinity)
9. [NaN](#nan)
10. [String در JavaScript](#string-در-javascript)
11. [طول String و length](#طول-string-و-length)
12. [دسترسی به کاراکترها](#دسترسی-به-کاراکترها)
13. [charAt](#charat)
14. [at](#at)
15. [indexOf و lastIndexOf](#indexof-و-lastindexof)
16. [search](#search)
17. [includes](#includes)
18. [substring](#substring)
19. [slice](#slice)
20. [startsWith و endsWith](#startswith-و-endswith)
21. [trim](#trim)
22. [trimStart و trimEnd](#trimstart-و-trimend)
23. [padStart و padEnd](#padstart-و-padend)
24. [replace و replaceAll](#replace-و-replaceall)
25. [repeat](#repeat)
26. [String Concatenation](#string-concatenation)
27. [Template Literals](#template-literals)
28. [concat](#concat)
29. [Boolean در JavaScript](#boolean-در-javascript)
30. [Truthy و Falsy](#truthy-و-falsy)
31. [Symbol](#symbol)
32. [Undefined](#undefined)
33. [typeof](#typeof)
34. [Type Conversion](#type-conversion)
35. [تبدیل به Number](#تبدیل-به-number)
36. [تبدیل به Boolean](#تبدیل-به-boolean)
37. [تبدیل به String](#تبدیل-به-string)
38. [مقایسه انواع داده](#مقایسه-انواع-داده)
39. [نکات مهم و اشتباهات رایج](#نکات-مهم-و-اشتباهات-رایج)
40. [جمع‌بندی](#جمع‌بندی)
41. [منابع معتبر](#منابع-معتبر)

---

# 1. Number در JavaScript

از صفر توضیح بده:

* Number چیست؟
* JavaScript چگونه اعداد را نمایش می‌دهد؟
* تفاوت Integer و Floating Point
* اعداد مثبت
* اعداد منفی
* اعداد اعشاری
* محدودیت دقت Number
* مفهوم IEEE 754 به زبان ساده
* چرا بعضی محاسبات اعشاری در JavaScript ممکن است نتیجه‌ای مانند زیر داشته باشند؟

```javascript
console.log(0.1 + 0.2);
```

توضیح بده چرا نتیجه دقیقاً `0.3` نیست.

---

# 2. اعداد منفی و اعشاری

کد زیر را خط‌به‌خط توضیح بده:

```javascript
let number = -10.548;

console.log(number);
```

توضیح بده:

* `let` چیست؟
* مقدار `-10.548` چه نوع داده‌ای است؟
* `typeof number` چه چیزی برمی‌گرداند؟
* تفاوت عدد منفی و مثبت چیست؟

مثال‌های بیشتری ارائه کن.

---

# 3. Scientific Notation

کد زیر را توضیح بده:

```javascript
let number1 = 1e-4;

console.log(number1);
```

توضیح بده:

* Scientific Notation چیست؟
* `e` یعنی چه؟
* `1e-4` یعنی چه؟
* `1e4` چه مقداری است؟
* `2.5e3` چه مقداری است؟
* کاربرد Scientific Notation چیست؟

مثال:

```javascript
console.log(1e3);
console.log(1e-3);
console.log(2.5e4);
```

---

# 4. toFixed

کد زیر را توضیح بده:

```javascript
let number2 = 12.646;

console.log(number2.toFixed(5));
```

توضیح بده:

* `toFixed()` چیست؟
* پارامتر آن چه کاربردی دارد؟
* چرا خروجی ممکن است String باشد؟
* تفاوت `12.646.toFixed(5)` با مقدار عددی چیست؟
* Rounding چگونه انجام می‌شود؟

مثال‌های مختلف ارائه کن.

---

# 5. Number.MIN_VALUE

کد زیر را توضیح بده:

```javascript
console.log(Number.MIN_VALUE);
```

حتماً تفاوت این موارد را توضیح بده:

```javascript
Number.MIN_VALUE
Number.MAX_VALUE
Number.MIN_SAFE_INTEGER
Number.MAX_SAFE_INTEGER
```

تأکید کن که `Number.MIN_VALUE` به معنی کوچک‌ترین عدد منفی نیست و مفهوم آن را به زبان ساده توضیح بده.

---

# 6. Infinity

کد زیر را توضیح بده:

```javascript
console.log(2 / 0);
```

توضیح بده:

* چرا نتیجه `Infinity` است؟
* Infinity چه نوع داده‌ای است؟
* `typeof Infinity` چیست؟
* `-Infinity` چیست؟
* `Number.isFinite()` چیست؟

مثال:

```javascript
console.log(10 / 0);
console.log(-10 / 0);
console.log(Number.isFinite(10));
console.log(Number.isFinite(Infinity));
```

---

# 7. NaN

کد زیر را توضیح بده:

```javascript
console.log('a' / 2);
```

توضیح بده:

* `NaN` چیست؟
* مخفف چیست؟
* چرا `'a' / 2` نتیجه `NaN` می‌دهد؟
* آیا NaN از نوع Number است؟
* تفاوت `NaN` با `undefined` و `null`
* `Number.isNaN()`
* تفاوت `Number.isNaN()` با `isNaN()`

مثال‌های مناسب ارائه کن.

---

# 8. String در JavaScript

کد زیر را توضیح بده:

```javascript
let info = "My name is Ali!";
let language = "javascript";

console.log(info);
```

توضیح بده:

* String چیست؟
* String را چگونه ایجاد می‌کنیم؟
* Single Quote
* Double Quote
* Backtick
* تفاوت آنها
* String Immutable چیست؟

مثال:

```javascript
let a = "hello";
let b = 'hello';
let c = `hello`;
```

---

# 9. length

کد زیر را توضیح بده:

```javascript
console.log(info.length);
```

توضیح بده:

* `length` چیست؟
* آیا فاصله هم جزو کاراکترها محسوب می‌شود؟
* آیا `length` متد است یا Property؟
* تفاوت Property و Method را ساده توضیح بده.

---

# 10. دسترسی به کاراکترهای String

این موارد را توضیح بده:

```javascript
console.log(info[0]);
console.log(info[17]);
```

توضیح بده:

* Index چیست؟
* چرا Index از صفر شروع می‌شود؟
* اگر Index وجود نداشته باشد چه اتفاقی می‌افتد؟

---

# 11. charAt

کد زیر را توضیح بده:

```javascript
console.log(info.charAt(-5));
```

توضیح بده:

* `charAt()` چیست؟
* Index منفی چگونه رفتار می‌کند؟
* اگر Index خارج از محدوده باشد چه می‌شود؟

---

# 12. at

کد زیر را توضیح بده:

```javascript
console.log(info.at(-5));
```

توضیح بده:

* `at()` چیست؟
* چه تفاوتی با `charAt()` دارد؟
* چرا `at()` برای Index منفی کاربردی است؟

جدول مقایسه‌ای بین:

```text
string[index]
charAt()
at()
```

ارائه کن.

---

# 13. indexOf و lastIndexOf

کدهای زیر را توضیح بده:

```javascript
console.log(info.indexOf('i'));
console.log(info.lastIndexOf('i'));
```

توضیح بده:

* `indexOf()` چیست؟
* `lastIndexOf()` چیست؟
* اگر مقدار پیدا نشود چه چیزی برمی‌گردد؟
* تفاوت آنها

---

# 14. search

کد زیر را توضیح بده:

```javascript
console.log(info.search('Ali'));
```

توضیح بده:

* `search()` چیست؟
* تفاوت `search()` و `indexOf()`
* ارتباط `search()` با Regular Expression

مثال ساده Regex نیز ارائه کن.

---

# 15. includes

کد زیر را توضیح بده:

```javascript
console.log(info.includes('Reza'));
```

توضیح بده:

* `includes()` چیست؟
* خروجی آن چیست؟
* چه زمانی از آن استفاده می‌کنیم؟
* تفاوت آن با `indexOf()`

---

# 16. substring

کد زیر را توضیح بده:

```javascript
console.log(info.substring(11, 14));
```

توضیح بده:

* `substring()` چیست؟
* Start و End چگونه کار می‌کنند؟
* End شامل می‌شود یا نه؟
* رفتار Index منفی
* تفاوت substring و slice

---

# 17. slice

کد زیر را توضیح بده:

```javascript
console.log(info.slice(-5, -2));
```

توضیح بده:

* `slice()` چیست؟
* Index منفی
* Start و End
* تفاوت `slice()` و `substring()`

مثال‌های مختلف ارائه کن.

---

# 18. startsWith و endsWith

این کدها را توضیح بده:

```javascript
console.log(info.startsWith("m"));
console.log(info.endsWith("!"));
```

توضیح بده:

* `startsWith()`
* `endsWith()`
* Case Sensitivity
* پارامترهای آنها

---

# 19. trim

با یک متغیر مانند زیر توضیح بده:

```javascript
let message = "   Hello JavaScript   ";
```

سپس:

```javascript
console.log(message.trim());
console.log(message.trimStart());
console.log(message.trimEnd());
```

توضیح بده:

* `trim()`
* `trimStart()`
* `trimEnd()`
* کاربرد آنها در Form Validation
* آیا String اصلی تغییر می‌کند؟

---

# 20. padStart و padEnd

کد زیر را توضیح بده:

```javascript
let love = "I love";

console.log(love.padEnd(9, '.'));
console.log(love.padStart(9, 'x'));
```

توضیح بده:

* Padding چیست؟
* `padStart()`
* `padEnd()`
* پارامتر اول
* پارامتر دوم
* کاربرد در شماره، کد، ساعت و موارد مشابه

---

# 21. replace و replaceAll


```javascript
console.log(info.replace('Ali', 'Reza'));
console.log(language.replace('java', 'type'));
console.log(language.replaceAll('a', 'x'));
```

توضیح بده:

* `replace()`
* `replaceAll()`
* تفاوت آنها
* آیا String اصلی تغییر می‌کند؟
* Case Sensitivity
* استفاده از Regex در replace

مثال:

```javascript
let text = "JavaScript is great. JavaScript is powerful.";
```

---

# 22. repeat

کد زیر را توضیح بده:

```javascript
console.log(language.repeat(3));
```

توضیح بده:

* `repeat()` چیست؟
* پارامتر آن چیست؟
* چه محدودیت‌هایی دارد؟

---

# 23. String Concatenation

این روش‌ها را توضیح بده:

```javascript
console.log(love + ' ' + language + '!');
```

و:

```javascript
console.log(love.concat(' ', language, '!'));
```

توضیح بده:

* Concatenation چیست؟
* استفاده از `+`
* استفاده از `concat()`
* مزایا و تفاوت آنها

---

# 24. Template Literals

کد صحیح زیر را توضیح بده:

```javascript
console.log(`${love} ${language}!`);
```

توضیح بده:

* Template Literal چیست؟
* Backtick چیست؟
* `${}` چیست؟
* چرا نسبت به Concatenation خواناتر است؟
* استفاده از Expression داخل Template Literal

مثال:

```javascript
let age = 30;

console.log(`My age is ${age}`);
console.log(`Result: ${10 + 20}`);
```

---

# 25. Boolean

این کدها را توضیح بده:

```javascript
console.log(Boolean(0));
console.log(Boolean(-20));

console.log(Boolean(''));
console.log(Boolean('hello'));
```

توضیح بده:

* Boolean چیست؟
* `true`
* `false`
* تبدیل مقدار به Boolean

---

# 26. Truthy و Falsy

یک بخش کامل و بسیار ساده درباره Truthy و Falsy ایجاد کن.

تمام مقادیر مهم Falsy را پوشش بده، از جمله:

```javascript
false
0
-0
0n
""
null
undefined
NaN
```

سپس مثال‌های Truthy ارائه کن.

توضیح بده:

```javascript
Boolean(value)
```

چگونه کار می‌کند.

همچنین مثال‌های کاربردی با:

```javascript
if
&&
||
!
!!
```

ارائه کن.

---

# 27. Symbol

کدهای زیر را توضیح بده:

```javascript
let firstname1 = Symbol('first name');
let firstname2 = Symbol('first name');

console.log(firstname1 === firstname2);
```

توضیح بده:

* Symbol چیست؟
* چرا `Symbol()` یک Primitive Data Type است؟
* چرا دو Symbol با Description یکسان برابر نیستند؟
* Description چیست؟
* کاربرد Symbol در JavaScript
* Symbol به عنوان Object Property
* `Symbol.for()`
* تفاوت `Symbol()` و `Symbol.for()`

مثال ساده ارائه کن.

---

# 28. Undefined

کد زیر را توضیح بده:

```javascript
let u = undefined;

console.log(u);
```

توضیح بده:

* Undefined چیست؟
* چه زمانی JavaScript مقدار `undefined` تولید می‌کند؟
* متغیر بدون مقدار
* Property غیرموجود
* Function بدون return
* تفاوت `undefined` و `null`

مثال:

```javascript
let x;
console.log(x);
```

---

# 29. typeof

این کد را بررسی کن:

```javascript
console.log(typeof function() {});
```

سپس `typeof` را به‌صورت کامل آموزش بده.

تمام موارد مهم را بررسی کن:

```javascript
typeof 10
typeof "hello"
typeof true
typeof undefined
typeof Symbol()
typeof 10n
typeof {}
typeof []
typeof null
typeof function() {}
```

حتماً درباره رفتار معروف زیر توضیح بده:

```javascript
typeof null
```

و اینکه چرا نتیجه آن `object` است.

---

# 30. Type Conversion

یک بخش کامل برای Type Conversion ایجاد کن.

توضیح بده:

* Type Conversion چیست؟
* Explicit Conversion
* Implicit Conversion
* تفاوت آنها

---

# 31. تبدیل به Number

کد زیر را توضیح بده:

```javascript
let name = "ali";
let name2 = "10";

console.log(Number(name2));
```

سپس مثال‌های زیر:

```javascript
Number("10")
Number("10.5")
Number("")
Number(" ")
Number("hello")
Number(true)
Number(false)
Number(null)
Number(undefined)
```

نتیجه تمام آنها را توضیح بده.

---

# 32. تبدیل به Boolean

این مثال را توضیح بده:

```javascript
console.log(Boolean(name));
```

سپس جدول کامل مقادیر مختلف و نتیجه Boolean آنها ایجاد کن.

---

# 33. تبدیل به String

کد زیر را توضیح بده:

```javascript
console.log(String());
```

سپس:

```javascript
String(10)
String(true)
String(false)
String(null)
String(undefined)
String(Symbol("id"))
```

را بررسی کن.

---

# 34. مقایسه انواع داده

یک بخش آموزشی برای مقایسه موارد زیر ایجاد کن:

```javascript
String
Number
Boolean
Undefined
Null
Symbol
BigInt
Object
```

توضیح بده:

* Primitive چیست؟
* Non-Primitive چیست؟
* کدام موارد Primitive هستند؟
* تفاوت Primitive و Object به زبان ساده

---

# 35. اشتباهات رایج

حداقل 15 اشتباه رایج مبتدیان درباره این موضوعات را توضیح بده.

مثلاً:

* اشتباه گرفتن `length` با `length()`
* تصور اینکه `charAt(-1)` آخرین کاراکتر را می‌دهد
* اشتباه گرفتن `substring()` و `slice()`
* تصور اینکه `replace()` همه موارد را تغییر می‌دهد
* اشتباه گرفتن `Number.MIN_VALUE` با کوچک‌ترین عدد منفی
* تصور اینکه `NaN` از نوع `NaN` است
* تصور اینکه `null` با `undefined` یکسان است
* فراموش کردن Case Sensitivity در String
* اشتباه گرفتن `==` و `===`
* تصور اینکه متدهای String، String اصلی را تغییر می‌دهند

---

# 36. مثال عملی

در پایان یک مثال نسبتاً واقعی ایجاد کن که در آن چند مورد از مفاهیم بالا با هم استفاده شده باشند.

مثلاً:

```javascript
let firstName = "Ali";
let lastName = "Ahmadi";
let age = 30;
let isStudent = false;

console.log(`Name: ${firstName} ${lastName}`);
console.log(`Age: ${age}`);
console.log(`Student: ${isStudent}`);
```

سپس کد را خط‌به‌خط تحلیل کن.

---

# 37. تمرین

در پایان حداقل:

* 10 تمرین ساده
* 10 تمرین متوسط
* 5 تمرین چالشی

ارائه کن.

تمرین‌ها باید فقط از مفاهیمی باشند که در همین فصل آموزش داده شده‌اند.

برای تمرین‌های چالشی، در ابتدا جواب را نشان نده.

در انتها یک بخش جداگانه با عنوان:

```text
## پاسخ تمرین‌ها
```

ایجاد کن.

---

# 38. جمع‌بندی

در انتها یک خلاصه بسیار ساده از تمام مفاهیم ارائه کن.

مثلاً:

| مفهوم     | کاربرد                             |
| --------- | ---------------------------------- |
| Number    | کار با اعداد                       |
| String    | کار با متن                         |
| Boolean   | true/false                         |
| Symbol    | ایجاد مقدارهای Symbol منحصر‌به‌فرد |
| Undefined | مقدار تعریف‌نشده                   |
| typeof    | تشخیص نوع مقدار                    |
| Number()  | تبدیل به Number                    |
| Boolean() | تبدیل به Boolean                   |
| String()  | تبدیل به String                    |

---

# 39. منابع معتبر

اطلاعات را از منابع معتبر و به‌روز جمع‌آوری کن.

اولویت منابع:

1. MDN Web Docs
2. ECMAScript Specification
3. JavaScript.info
4. منابع رسمی مرتبط با استاندارد JavaScript

در پایان یک بخش:

# منابع معتبر

ایجاد کن و برای هر موضوع لینک مستقیم منبع را قرار بده.

از لینک‌های جعلی یا نامطمئن استفاده نکن.

منابع باید واقعاً به همان موضوع مرتبط باشند.

---

# نکته بسیار مهم

کدهایی که در این درخواست قرار داده شده‌اند ممکن است به دلیل کپی شدن از ویدئو یا PDF دارای اشتباه تایپی باشند.

بنابراین:

* کدها را اصلاح کن.
* اما مفهوم اصلی کد را حفظ کن.
* اگر یک کد اشتباه است، ابتدا نسخه صحیح آن را نشان بده.
* سپس توضیح بده که مشکل نسخه اولیه چه بوده است.
* خروجی کدهای صحیح را نیز مشخص کن.
* هیچ API یا رفتار JavaScript را حدس نزن.
* در مواردی که رفتار JavaScript وابسته به استاندارد ECMAScript است، از منابع معتبر بررسی کن.

---

# استاندارد نوشتن کد

تمام کدها داخل Code Block قرار بگیرند:

```javascript
let name = "Ali";

console.log(name);
```

خروجی نیز در صورت امکان مشخص شود:

```text
Ali
```

بعد از هر مثال:

### توضیح

به زبان ساده توضیح بده که چه اتفاقی افتاده است.

---

# سطح‌بندی آموزش

مطالب را به سه سطح تقسیم کن:

### 🟢 Beginner

مفاهیم پایه و مثال‌های ساده

### 🟡 Intermediate

متدها، تبدیل نوع، Truthy/Falsy و رفتارهای مهم

### 🔴 Advanced

جزئیات فنی، استاندارد ECMAScript، IEEE 754، Primitiveها، Symbol، Type Coercion و نکات ظریف زبان

---


هدف این است که یک فرد کاملاً مبتدی بعد از خواندن این فصل:

1. Number را در JavaScript بشناسد.
2. تفاوت Infinity و NaN را بداند.
3. String و مهم‌ترین متدهای آن را بلد باشد.
4. تفاوت `slice` و `substring` را بفهمد.
5. تفاوت `charAt` و `at` را بداند.
6. با `replace` و `replaceAll` کار کند.
7. Template Literal را بفهمد.
8. Truthy و Falsy را بشناسد.
9. Symbol و Undefined را درک کند.
10. با `typeof` نوع داده‌ها را بررسی کند.
11. Type Conversion را بفهمد.
12. تفاوت Primitive و Object را بداند.
13. بتواند کدهای واقعی JavaScript را تحلیل کند.

محتوا باید **آموزشی، مرحله‌به‌مرحله، دقیق، خوانا و مناسب GitHub Repository** باشد و از توضیحات غیرضروری و پیچیده در بخش‌های مقدماتی خودداری شود.



این سند به‌عنوان یک راهنمای جامع، مرحله‌به‌مرحله و دقیق برای یادگیری مفاهیم پایه‌ای و پیشرفته انواع داده (Data Types) در JavaScript طراحی شده است. این محتوا برای قرارگیری مستقیم در فایل `README.md` یک Repository آموزشی بهینه‌سازی شده است.

---


1. [مقدمه](#مقدمه)
2. [Number در JavaScript](#number-در-javascript)
3. [اعداد صحیح و اعشاری](#اعداد-صحیح-و-اعشاری)
4. [اعداد منفی](#اعداد-منفی)
5. [Scientific Notation](#scientific-notation)
6. [toFixed](#tofixed)
7. [Number.MIN_VALUE](#numbermin_value)
8. [Infinity](#infinity)
9. [NaN](#nan)
10. [String در JavaScript](#string-در-javascript)
11. [طول String و length](#طول-string-و-length)
12. [دسترسی به کاراکترها](#دسترسی-به-کاراکترها)
13. [charAt](#charat)
14. [at](#at)
15. [indexOf و lastIndexOf](#indexof-و-lastindexof)
16. [search](#search)
17. [includes](#includes)
18. [substring](#substring)
19. [slice](#slice)
20. [startsWith و endsWith](#startswith-و-endswith)
21. [trim](#trim)
22. [trimStart و trimEnd](#trimstart-و-trimend)
23. [padStart و padEnd](#padstart-و-padend)
24. [replace و replaceAll](#replace-و-replaceall)
25. [repeat](#repeat)
26. [String Concatenation](#string-concatenation)
27. [Template Literals](#template-literals)
28. [concat](#concat)
29. [Boolean در JavaScript](#boolean-در-javascript)
30. [Truthy و Falsy](#truthy-و-falsy)
31. [Symbol](#symbol)
32. [Undefined](#undefined)
33. [typeof](#typeof)
34. [Type Conversion](#type-conversion)
35. [تبدیل به Number](#تبدیل-به-number)
36. [تبدیل به Boolean](#تبدیل-به-boolean)
37. [تبدیل به String](#تبدیل-به-string)
38. [مقایسه انواع داده](#مقایسه-انواع-داده)
39. [نکات مهم و اشتباهات رایج](#نکات-مهم-و-اشتباهات-رایج)
40. [مثال عملی](#مثال-عملی)
41. [تمرین](#تمرین)
42. [پاسخ تمرین‌ها](#پاسخ-تمرین‌ها)
43. [جمع‌بندی](#جمع‌بندی)
44. [منابع معتبر](#منابع-معتبر)

---

## مقدمه
به دنیای JavaScript خوش آمدید! در این فصل، ما به بررسی عمیق و همه‌جانبه‌ی انواع داده‌های اولیه (Primitive) و روش‌های کار با آن‌ها می‌پردازیم. درک این مفاهیم، سنگ بنای نوشتن کدهای تمیز، بدون باگ و حرفه‌ای است.

---

## 1. Number در JavaScript
### 🟢 Beginner
در JavaScript، برخلاف بسیاری از زبان‌های دیگر (مثل C++ یا Java)، تنها **یک نوع داده عددی** وجود دارد و آن هم `Number` است. این یعنی اعداد صحیح (Integer) و اعشاری (Floating Point) هر دو از یک نوع هستند.

JavaScript اعداد را بر اساس استاندارد **IEEE 754** به صورت "اعشاری با دقت دوبرابر" (Double-precision 64-bit binary format) ذخیره می‌کند.

### 🔴 Advanced: مشکل دقت اعشاری
چرا `0.1 + 0.2` دقیقاً `0.3` نمی‌شود؟
```javascript
console.log(0.1 + 0.2); // خروجی: 0.30000000000000004
```
**توضیح**: کامپیوترها اعداد را در مبنای ۲ (باینری) ذخیره می‌کنند. کسرهایی مثل `0.1` در مبنای ۲، یک دنباله‌ی نامتناهی دارند (دقیقاً مثل `1/3` که در مبنای ۱۰ می‌شود `0.3333...`). چون حافظه محدود است (۶۴ بیت)، این عدد گرد می‌شود و هنگام جمع، خطای گردکردن کوچک (Precision Error) ایجاد می‌کند. برای محاسبات مالی دقیق، باید از کتابخانه‌هایی مثل `Decimal.js` یا ضرب در توان ۱۰ و تقسیم مجدد استفاده کرد.

---

## 2. اعداد صحیح و اعشاری
### 🟢 Beginner
```javascript
let number = -10.548;
console.log(number);
```
### توضیح:
* `let`: یک کلمه کلیدی برای تعریف متغیر است که اجازه می‌دهد مقدار آن بعداً تغییر کند.
* `-10.548`: یک مقدار از نوع `Number` است که هم علامت منفی دارد و هم بخش اعشاری.
* `typeof number`: مقدار `"number"` را برمی‌گرداند.
* تفاوت عدد منفی و مثبت فقط در علامت و جهت آن روی محور اعداد است؛ از نظر نوع داده (Type) هیچ تفاوتی ندارند.

---

## 3. Scientific Notation
### 🟡 Intermediate
نماد علمی (Scientific Notation) روشی برای نوشتن اعداد بسیار بزرگ یا بسیار کوچک است.
```javascript
let number1 = 1e-4;
console.log(number1); // خروجی: 0.0001

console.log(1e3);   // خروجی: 1000 (1 * 10^3)
console.log(1e-3);  // خروجی: 0.001 (1 * 10^-3)
console.log(2.5e4); // خروجی: 25000 (2.5 * 10^4)
```
### توضیح:
* حرف `e` (یا `E`) به معنی "ضرب در ۱۰ به توان..." است.
* `1e-4` یعنی $1 \times 10^{-4}$ که می‌شود `0.0001`.
* کاربرد اصلی: نمایش اعداد بسیار بزرگ (مثل فاصله ستارگان) یا بسیار کوچک (مثل اندازه اتم) بدون نوشتن صفرهای زیاد.

---

## 4. toFixed
### 🟡 Intermediate
```javascript
let number2 = 12.646;
console.log(number2.toFixed(5)); // خروجی: "12.64600"
```
### توضیح:
* `toFixed(n)`: یک متد است که عدد را به `n` رقم اعشار گرد می‌کند.
* **نکته حیاتی**: خروجی این متد **رشته (String)** است، نه عدد! اگر می‌خواهید دوباره محاسبه ریاضی انجام دهید، باید آن را به عدد تبدیل کنید.
* گردکردن (Rounding): اگر رقم بعدی ۵ یا بیشتر باشد، به بالا گرد می‌شود (مثلاً `12.646.toFixed(2)` می‌شود `"12.65"`).

---

## 5. Number.MIN_VALUE
### 🔴 Advanced
```javascript
console.log(Number.MIN_VALUE); // خروجی: 5e-324
```
### توضیح:
یک اشتباه رایج این است که فکر کنیم `MIN_VALUE` کوچک‌ترین عدد منفی (مثل منفی بی‌نهایت) است. **اینطور نیست!**
* `Number.MIN_VALUE`: کوچک‌ترین عدد **مثبت** غیرصفر است که JavaScript می‌تواند نمایش دهد ($5 \times 10^{-324}$).
* `Number.MAX_VALUE`: بزرگ‌ترین عدد مثبت ممکن ($1.79 \times 10^{308}$).
* `Number.MIN_SAFE_INTEGER`: کوچک‌ترین عدد صحیح امن ($-9007199254740991$). فراتر از این، محاسبات صحیح دچار خطا می‌شوند.
* `Number.MAX_SAFE_INTEGER`: بزرگ‌ترین عدد صحیح امن ($9007199254740991$).

---

## 6. Infinity
### 🟢 Beginner
```javascript
console.log(2 / 0); // خروجی: Infinity
console.log(10 / 0); // خروجی: Infinity
console.log(-10 / 0); // خروجی: -Infinity
console.log(Number.isFinite(10)); // خروجی: true
console.log(Number.isFinite(Infinity)); // خروجی: false
```
### توضیح:
* تقسیم یک عدد مثبت بر صفر در JavaScript خطا نمی‌دهد، بلکه `Infinity` (بی‌نهایت) برمی‌گرداند.
* `typeof Infinity` برابر با `"number"` است.
* `Number.isFinite()`: بررسی می‌کند که آیا یک مقدار، یک عدد متناهی (معمولی) است یا خیر. برای `Infinity`، `NaN` و رشته‌ها `false` برمی‌گرداند.

---

## 7. NaN
### 🟡 Intermediate
```javascript
console.log('a' / 2); // خروجی: NaN
```
### توضیح:
* `NaN` مخفف **Not-a-Number** است.
* زمانی رخ می‌دهد که یک عملیات ریاضی نامعتبر انجام شود (مثل تقسیم رشته بر عدد).
* **نکته عجیب**: `typeof NaN` برابر با `"number"` است! (این یک ویژگی تاریخی در زبان است).
* تفاوت با `undefined` و `null`: `NaN` یک مقدار عددی نامعتبر است، اما `undefined` یعنی "مقداردهی نشده" و `null` یعنی "عمداً خالی".
* `Number.isNaN()`: فقط اگر مقدار دقیقاً `NaN` باشد `true` برمی‌گرداند.
* تفاوت با `isNaN()` قدیمی: تابع سراسری `isNaN("hello")` مقدار `true` برمی‌گرداند (چون سعی می‌کند رشته را به عدد تبدیل کند و شکست می‌خورد)، اما `Number.isNaN("hello")` مقدار `false` برمی‌گرداند (چون ابتدا بررسی می‌کند که آیا اصلاً نوع داده عدد است یا خیر).

---

## 8. String در JavaScript
### 🟢 Beginner
```javascript
let info = "My name is Ali!";
let language = 'javascript';
let greeting = `Hello`;

console.log(info); // خروجی: My name is Ali!
```
### توضیح:
* `String` (رشته) برای ذخیره متن استفاده می‌شود.
* سه روش تعریف داریم:
  1. Single Quote (`'...'`)
  2. Double Quote (`"..."`)
  3. Backtick (`` `...` ``): که قابلیت Template Literal را فراهم می‌کند.
* **Immutability (تغییرناپذیری)**: در JavaScript، رشته‌ها تغییرناپذیرند. یعنی شما نمی‌توانید یک کاراکتر خاص از رشته را مستقیماً تغییر دهید (مثلاً `info[0] = 'Y'` کار نمی‌کند). هر عملیاتی روی رشته، یک رشته‌ی **جدید** می‌سازد.

---

## 9. طول String و length
### 🟢 Beginner
```javascript
console.log(info.length); // خروجی: 17
```
### توضیح:
* `length`: یک **Property** (ویژگی) است، نه یک **Method** (متد). بنابراین پرانتز ندارد (`length()` اشتباه است).
* فاصله‌ها (Space) نیز به‌عنوان یک کاراکتر شمرده می‌شوند.
* تفاوت Property و Method: Property یک ویژگی یا داده است (مثل `length`)، اما Method یک عمل یا تابع است که روی داده اجرا می‌شود (مثل `toUpperCase()`).

---

## 10. دسترسی به کاراکترها
### 🟢 Beginner
```javascript
console.log(info[0]);  // خروجی: "M"
console.log(info[17]); // خروجی: undefined
```
### توضیح:
* Index (شاخص): موقعیت هر کاراکتر در رشته است.
* در برنامه‌نویسی، شمارش از **صفر** شروع می‌شود. پس `info[0]` اولین کاراکتر است.
* اگر Index بزرگ‌تر یا مساوی `length` باشد، JavaScript خطا نمی‌دهد، بلکه `undefined` برمی‌گرداند.

---

## 11. charAt
### 🟡 Intermediate
```javascript
console.log(info.charAt(-5)); // خروجی: "" (رشته خالی)
```
### توضیح:
* `charAt(index)`: کاراکتر موجود در شاخص مشخص‌شده را برمی‌گرداند.
* **رفتار با Index منفی**: اگر عدد منفی یا خارج از محدوده باشد، به‌جای خطا، یک **رشته خالی** (`""`) برمی‌گرداند. این رفتار در نسخه‌های قدیمی JS طراحی شد و اکنون منسوخ در نظر گرفته می‌شود.

---

## 12. at
### 🟡 Intermediate
```javascript
console.log(info.at(-5)); // خروجی: "A"
```
### توضیح:
* `at(index)`: یک متد مدرن (ES2022) که رفتار هوشمندانه‌تری دارد.
* **تفاوت با `charAt`**: متد `at` از **Index منفی** پشتیبانی می‌کند و شمارش را از انتهای رشته شروع می‌کند. `info.at(-1)` آخرین کاراکتر را برمی‌گرداند.
* اگر Index خارج از محدوده باشد، `undefined` برمی‌گرداند (نه رشته خالی).

| روش | دسترسی عادی | دسترسی با عدد منفی | خارج از محدوده |
| :--- | :--- | :--- | :--- |
| `string[index]` | ✅ کار می‌کند | ❌ `undefined` می‌دهد | `undefined` |
| `charAt(index)` | ✅ کار می‌کند | ❌ `""` (رشته خالی) می‌دهد | `""` |
| `at(index)` | ✅ کار می‌کند | ✅ از انتها می‌شمارد | `undefined` |

---

## 13. indexOf و lastIndexOf
### 🟡 Intermediate
```javascript
console.log(info.indexOf('i'));      // خروجی: 8
console.log(info.lastIndexOf('i'));  // خروجی: 13
```
### توضیح:
* `indexOf('مقدار')`: اولین موقعیتی که مقدار در رشته پیدا شود را برمی‌گرداند (از چپ به راست جستجو می‌کند).
* `lastIndexOf('مقدار')`: آخرین موقعیتی که مقدار پیدا شود را برمی‌گرداند (از راست به چپ جستجو می‌کند، اما ایندکس را از چپ می‌شمارد).
* اگر مقدار پیدا نشود، هر دو متد مقدار **`-1`** را برمی‌گردانند.

---

## 14. search
### 🔴 Advanced
```javascript
console.log(info.search('Ali')); // خروجی: 11
// مثال با Regex:
console.log(info.search(/ali/i)); // خروجی: 11 (i به معنی نادیده گرفتن حروف بزرگ/کوچک است)
```
### توضیح:
* `search()`: شبیه به `indexOf` عمل می‌کند، اما **قدرت اصلی آن در پشتیبانی از Regular Expression (Regex)** است.
* تفاوت با `indexOf`: متد `indexOf` نمی‌تواند الگوهای پیچیده (Regex) را جستجو کند، اما `search` می‌تواند. هر دو در صورت عدم یافتن، `-1` برمی‌گردانند.

---

## 15. includes
### 🟡 Intermediate
```javascript
console.log(info.includes('Reza')); // خروجی: false
console.log(info.includes('Ali'));  // خروجی: true
```
### توضیح:
* `includes()`: بررسی می‌کند که آیا یک زیررشته (Substring) درون رشته وجود دارد یا خیر.
* خروجی آن همیشه یک **Boolean** (`true` یا `false`) است.
* تفاوت با `indexOf`: خوانایی کد با `includes` بیشتر است (`if (str.includes('x'))` بسیار خواناتر از `if (str.indexOf('x') !== -1)` است).

---

## 16. substring
### 🟡 Intermediate
```javascript
console.log(info.substring(11, 14)); // خروجی: " Al"
```
### توضیح:
* `substring(start, end)`: بخشی از رشته را از شاخص `start` تا `end` استخراج می‌کند.
* **نکته مهم**: کاراکتر در شاخص `end` **شامل نمی‌شود** (Exclusive).
* رفتار با اعداد منفی: اگر عدد منفی بدهید، آن را به‌عنوان `0` در نظر می‌گیرد.
* اگر `start` بزرگ‌تر از `end` باشد، به‌طور خودکار جای آن‌ها را عوض می‌کند.

---

## 17. slice
### 🟡 Intermediate
```javascript
console.log(info.slice(-5, -2)); // خروجی: " Al"
```
### توضیح:
* `slice(start, end)`: مشابه `substring` عمل می‌کند، اما **از Index منفی پشتیبانی می‌کند** (شمارش از انتهای رشته).
* تفاوت کلیدی با `substring`:
  1. `slice` با اعداد منفی به‌درستی از انتها می‌شمارد.
  2. اگر `start` بزرگ‌تر از `end` باشد، `slice` یک رشته خالی `""` برمی‌گرداند (برخلاف `substring` که جابجا می‌کند).

---

## 18. startsWith و endsWith
### 🟡 Intermediate
```javascript
console.log(info.startsWith("m")); // خروجی: false (حساس به حروف بزرگ/کوچک)
console.log(info.startsWith("M")); // خروجی: true
console.log(info.endsWith("!"));   // خروجی: true
```
### توضیح:
* `startsWith()`: بررسی می‌کند رشته با چه چیزی شروع می‌شود.
* `endsWith()`: بررسی می‌کند رشته با چه چیزی تمام می‌شود.
* هر دو به حروف بزرگ و کوچک (Case Sensitivity) حساس هستند.
* هر دو یک پارامتر اختیاری دوم دارند که موقعیت شروع جستجو را مشخص می‌کند.

---

## 19. trim
### 🟡 Intermediate
```javascript
let message = "   Hello JavaScript   ";
console.log(message.trim());      // خروجی: "Hello JavaScript"
console.log(message.trimStart()); // خروجی: "Hello JavaScript   "
console.log(message.trimEnd());   // خروجی: "   Hello JavaScript"
```
### توضیح:
* `trim()`: فاصله‌های خالی (Whitespace) را از **ابتدا و انتهای** رشته حذف می‌کند.
* `trimStart()` (یا `trimLeft`): فقط از ابتدا حذف می‌کند.
* `trimEnd()` (یا `trimRight`): فقط از انتها حذف می‌کند.
* کاربرد اصلی: پاک‌سازی ورودی‌های کاربر در فرم‌ها (Form Validation) قبل از ارسال به سرور.
* رشته اصلی تغییر نمی‌کند (Immutability).

---

## 20. padStart و padEnd
### 🟡 Intermediate
```javascript
let love = "I love";
console.log(love.padEnd(9, '.'));    // خروجی: "I love..."
console.log(love.padStart(9, 'x'));  // خروجی: "xxxI love"
```
### توضیح:
* Padding: پر کردن فضای خالی رشته تا رسیدن به یک طول مشخص.
* پارامتر اول: طول نهایی مورد نظر رشته.
* پارامتر دوم: کاراکتری که برای پر کردن استفاده می‌شود (پیش‌فرض فاصله است).
* کاربرد: فرمت‌دهی ساعت (`"9".padStart(2, "0")` -> `"09"`) یا نمایش شماره‌های کارت بانکی.

---

## 21. replace و replaceAll
### 🟡 Intermediate
```javascript
let text = "JavaScript is great. JavaScript is powerful.";
console.log(text.replace('JavaScript', 'TypeScript')); 
// خروجی: "TypeScript is great. JavaScript is powerful." (فقط اولی)

console.log(text.replaceAll('JavaScript', 'TypeScript')); 
// خروجی: "TypeScript is great. TypeScript is powerful." (همه)
```
### توضیح:
* `replace()`: فقط **اولین** تطابق را جایگزین می‌کند (مگر اینکه از Regex با فلگ `g` استفاده کنید).
* `replaceAll()`: **تمام** تطابق‌ها را جایگزین می‌کند (معرفی‌شده در ES2021).
* رشته اصلی تغییر نمی‌کند و یک رشته جدید برگردانده می‌شود.

---

## 22. repeat
### 🟡 Intermediate
```javascript
let language = "js-";
console.log(language.repeat(3)); // خروجی: "js-js-js-"
```
### توضیح:
* `repeat(n)`: رشته را `n` بار پشت سر هم تکرار می‌کند.
* محدودیت: اگر `n` منفی یا بی‌نهایت باشد، خطای `RangeError` می‌دهد. اعداد اعشاری به سمت پایین گرد می‌شوند (مثلاً `2.9` می‌شود `2`).

---

## 23. String Concatenation
### 🟢 Beginner
```javascript
let love = "I love";
let language = "JavaScript";

console.log(love + ' ' + language + '!'); // خروجی: "I love JavaScript!"
console.log(love.concat(' ', language, '!')); // خروجی: "I love JavaScript!"
```
### توضیح:
* Concatenation (الحاق): چسباندن رشته‌ها به یکدیگر.
* استفاده از `+`: رایج‌ترین و ساده‌ترین روش.
* استفاده از `concat()`: متدی است که هر تعداد آرگومان را می‌گیرد و به هم می‌چسباند. امروزه به ندرت استفاده می‌شود زیرا Template Literalها خواناتر هستند.

---

## 24. Template Literals
### 🟢 Beginner
```javascript
let age = 30;
console.log(`My age is ${age}`);       // خروجی: "My age is 30"
console.log(`Result: ${10 + 20}`);     // خروجی: "Result: 30"
```
### توضیح:
* Template Literal: روشی مدرن برای ساخت رشته با استفاده از **Backtick** (`` ` ``).
* `${}`: اجازه می‌دهد متغیرها یا هر عبارت (Expression) جاوااسکریپتی را مستقیماً درون رشته قرار دهید.
* مزیت: خوانایی بسیار بالاتر نسبت به استفاده مکرر از `+` و امکان ایجاد رشته‌های چندخطی (Multi-line) بدون نیاز به `\n`.

---

## 25. Boolean در JavaScript
### 🟢 Beginner
```javascript
console.log(Boolean(0));    // خروجی: false
console.log(Boolean(-20));  // خروجی: true
console.log(Boolean(''));   // خروجی: false
console.log(Boolean('hello')); // خروجی: true
```
### توضیح:
* `Boolean`: یک نوع داده منطقی است که فقط دو مقدار دارد: `true` (درست) و `false` (نادرست).
* تابع `Boolean()` یک مقدار را به معادل منطقی آن تبدیل می‌کند.

---

## 26. Truthy و Falsy
### 🟡 Intermediate
در JavaScript، همه مقادیر هنگام ارزیابی در یک زمینه منطقی (مثل دستور `if`)، یا **Truthy** (درست‌نما) یا **Falsy** (نادرست‌نما) هستند.

### مقادیر Falsy (فقط همین ۸ مورد):
1. `false`
2. `0` (و `-0`)
3. `0n` (BigInt صفر)
4. `""` یا `''` یا `` `` `` (رشته خالی)
5. `null`
6. `undefined`
7. `NaN`

**هر چیز دیگری در JavaScript مقدار Truthy دارد** (حتی رشته `"false"` یا آرایه خالی `[]` یا شیء خالی `{}`).

### مثال‌های کاربردی:
```javascript
let name = "";
if (!name) { // چون name Falsy است، !name می‌شود true
    console.log("Name is empty!");
}

// استفاده از && و || برای مقداردهی پیش‌فرض
let user = null;
let displayName = user || "Guest"; // خروجی: "Guest"
```

---

## 27. Symbol
### 🔴 Advanced
```javascript
let firstname1 = Symbol('first name');
let firstname2 = Symbol('first name');

console.log(firstname1 === firstname2); // خروجی: false
```
### توضیح:
* `Symbol`: یک نوع داده اولیه (Primitive) است که در ES6 معرفی شد و هدف آن ایجاد **مقادیر کاملاً منحصر‌به‌فرد** است.
* حتی اگر Description (رشته‌ی داخل پرانتز) یکسان باشد، هر `Symbol()` یک هویت کاملاً جدید و متمایز می‌سازد.
* کاربرد اصلی: ایجاد کلیدهای (Keys) منحصر‌به‌فرد برای اشیاء (Objects) تا از تداخل نام ویژگی‌ها (Name Collision) جلوگیری شود.
* `Symbol.for(key)`: یک Symbol سراسری (Global) ایجاد می‌کند. اگر قبلاً با این کلید ساخته شده باشد، همان را برمی‌گرداند (برخلاف `Symbol()`).

---

## 28. Undefined
### 🟢 Beginner
```javascript
let u = undefined;
let x;
console.log(x); // خروجی: undefined
```
### توضیح:
* `Undefined`: به این معنی است که یک متغیر تعریف شده، اما **هنوز مقداری به آن اختصاص داده نشده است**.
* چه زمانی تولید می‌شود؟
  1. متغیر تعریف شده ولی مقداردهی نشده (`let a;`).
  2. دسترسی به یک Property که در شیء وجود ندارد (`obj.missingProp`).
  3. تابعی که مقدار `return` ندارد، به‌طور پیش‌فرض `undefined` برمی‌گرداند.
* تفاوت با `null`: `null` یک مقدار "خالی" است که **عمداً** توسط برنامه‌نویس تنظیم می‌شود، اما `undefined` معمولاً به معنی "عدم وجود مقدار به‌صورت سیستمی" است.

---

## 29. typeof
### 🟡 Intermediate
```javascript
console.log(typeof 10);             // "number"
console.log(typeof "hello");        // "string"
console.log(typeof true);           // "boolean"
console.log(typeof undefined);      // "undefined"
console.log(typeof Symbol());       // "symbol"
console.log(typeof 10n);            // "bigint"
console.log(typeof {});             // "object"
console.log(typeof []);             // "object"
console.log(typeof function() {});  // "function"
console.log(typeof null);           // "object" (باگ تاریخی!)
```
### توضیح:
* `typeof`: عملگری است که نوع داده یک مقدار را به‌صورت رشته برمی‌گرداند.
* **باگ تاریخی `typeof null`**: نتیجه `"object"` است. این یک باگ در نسخه‌های اولیه JavaScript بود که به دلایل سازگاری با کدهای قدیمی (Backward Compatibility) هرگز اصلاح نشد. برای بررسی `null` باید مستقیماً از `value === null` استفاده کرد.
* توجه: `typeof []` هم `"object"` برمی‌گرداند. برای تشخیص آرایه باید از `Array.isArray()` استفاده کرد.

---

## 30. Type Conversion
### 🟡 Intermediate
تبدیل نوع (Type Conversion) به دو دسته تقسیم می‌شود:
1. **Explicit (صریح)**: برنامه‌نویس عمداً نوع را تغییر می‌دهد (مثلاً با `Number()` یا `String()`).
2. **Implicit (ضمنی یا Coercion)**: موتور JavaScript به‌طور خودکار و پنهانی نوع را برای انجام یک عملیات تغییر می‌دهد (مثلاً در `"5" - 2`، رشته `"5"` به عدد تبدیل می‌شود).

---

## 31. تبدیل به Number
### 🟡 Intermediate
```javascript
console.log(Number("10"));       // 10
console.log(Number("10.5"));     // 10.5
console.log(Number(""));         // 0
console.log(Number(" "));        // 0 (فاصله‌ها نادیده گرفته می‌شوند)
console.log(Number("hello"));    // NaN (تبدیل ناموفق)
console.log(Number(true));       // 1
console.log(Number(false));      // 0
console.log(Number(null));       // 0
console.log(Number(undefined));  // NaN
```
### توضیح:
تابع `Number()` سعی می‌کند کل مقدار را به عدد تبدیل کند. اگر کوچک‌ترین بخش غیرعددی (به جز فاصله) وجود داشته باشد، `NaN` برمی‌گرداند. (برای استخراج عدد از ابتدای رشته، از `parseInt` یا `parseFloat` استفاده می‌شود).

---

## 32. تبدیل به Boolean
### 🟡 Intermediate
```javascript
let name = "Ali";
console.log(Boolean(name)); // true
```
همان‌طور که در بخش Truthy/Falsy توضیح داده شد، فقط ۸ مقدار خاص `false` می‌شوند و بقیه مقادیر `true` خواهند شد.

---

## 33. تبدیل به String
### 🟡 Intermediate
```javascript
console.log(String(10));          // "10"
console.log(String(true));        // "true"
console.log(String(null));        // "null"
console.log(String(undefined));   // "undefined"
console.log(String(Symbol("id"))); // "Symbol(id)"
```
### توضیح:
تابع `String()` تقریباً هر مقداری را به نمایش متنی معقول آن تبدیل می‌کند و هرگز `NaN` برنمی‌گرداند.

---

## 34. مقایسه انواع داده
### 🔴 Advanced
انواع داده در JavaScript به دو دسته کلی تقسیم می‌شوند:
1. **Primitive (اولیه)**: مقدار آن‌ها مستقیماً ذخیره می‌شود و تغییرناپذیر (Immutable) هستند. شامل: `Number`, `String`, `Boolean`, `Undefined`, `Null`, `Symbol`, `BigInt`.
2. **Non-Primitive (مرجع / Object)**: شامل `Object`, `Array`, `Function`. این مقادیر به‌صورت مرجع (Reference) در حافظه ذخیره می‌شوند و قابل تغییر (Mutable) هستند.

---

## 35. نکات مهم و اشتباهات رایج
### 🟡 Intermediate
1. **اشتباه گرفتن `length` با `length()`**: `length` یک Property است، نه متد.
2. **تصور اینکه `charAt(-1)` آخرین کاراکتر را می‌دهد**: خیر، رشته خالی `""` می‌دهد. برای این کار از `at(-1)` استفاده کنید.
3. **اشتباه گرفتن `substring` و `slice`**: `substring` اعداد منفی را `0` در نظر می‌گیرد و جای start/end را عوض می‌کند، اما `slice` از انتها می‌شمارد.
4. **تصور اینکه `replace` همه موارد را تغییر می‌دهد**: فقط اولین مورد را تغییر می‌دهد. برای همه از `replaceAll` یا Regex با فلگ `g` استفاده کنید.
5. **اشتباه گرفتن `Number.MIN_VALUE` با کوچک‌ترین عدد منفی**: این مقدار، کوچک‌ترین عدد **مثبت** است.
6. **تصور اینکه `NaN` از نوع `NaN` است**: `typeof NaN` برابر `"number"` است.
7. **تصور اینکه `null` با `undefined` یکسان است**: `null === undefined` مقدار `false` است (اما `null == undefined` مقدار `true` است).
8. **فراموش کردن Case Sensitivity**: در رشته‌ها، `"A"` با `"a"` متفاوت است.
9. **اشتباه گرفتن `==` و `===`**: `==` تبدیل نوع ضمنی انجام می‌دهد، اما `===` (توصیه‌شده) هم مقدار و هم نوع را بررسی می‌کند.
10. **تصور اینکه متدهای String، رشته اصلی را تغییر می‌دهند**: رشته‌ها Immutable هستند؛ متدها همیشه یک رشته **جدید** برمی‌گردانند.
11. **استفاده از `typeof` برای تشخیص آرایه**: `typeof []` برابر `"object"` است. باید از `Array.isArray()` استفاده کرد.
12. **تصور اینکه `0.1 + 0.2 === 0.3`**: به دلیل خطای اعشاری IEEE 754، این عبارت `false` است.
13. **فراموش کردن Backtick در Template Literal**: استفاده از `'` یا `"` باعث می‌شود `${}` به‌صورت متن ساده چاپ شود.
14. **استفاده از `isNaN` به‌جای `Number.isNaN`**: `isNaN("test")` مقدار `true` برمی‌گرداند که گمراه‌کننده است.
15. **تغییر مستقیم کاراکتر رشته**: `str[0] = "A"` هیچ خطایی نمی‌دهد، اما هیچ تغییری هم ایجاد نمی‌کند.

---

## 36. مثال عملی
### 🟡 Intermediate
بیایید مفاهیم را در یک سناریوی واقعی ترکیب کنیم:

```javascript
let firstName = "  ali  ";
let lastName = "ahmadi";
let age = "30";
let isStudent = false;

// 1. پاک‌سازی و استانداردسازی نام
let cleanFirstName = firstName.trim().toLowerCase(); // "ali"
let capitalizedFirst = cleanFirstName.charAt(0).toUpperCase() + cleanFirstName.slice(1); // "Ali"

// 2. تبدیل نوع و محاسبه
let ageInFiveYears = Number(age) + 5; // 35

// 3. استفاده از Template Literal و Truthy/Falsy
let status = isStudent ? "Yes" : "No";
let finalMessage = `Name: ${capitalizedFirst} ${lastName}\nAge in 5 years: ${ageInFiveYears}\nStudent: ${status}`;

console.log(finalMessage);
```

### تحلیل خط‌به‌خط:
1. `trim()`: فاصله‌های اضافی را حذف می‌کند. `toLowerCase()` همه را کوچک می‌کند.
2. `charAt(0).toUpperCase()`: حرف اول را بزرگ می‌کند. `slice(1)` بقیه رشته را می‌گیرد و با `+` به هم می‌چسبند (ساخت حرف اول بزرگ).
3. `Number(age)`: رشته `"30"` را به عدد `30` تبدیل می‌کند تا عمل جمع ریاضی انجام شود (جلوگیری از الحاق رشته).
4. `? :`: عملگر شرطی (Ternary) که بر اساس Falsy بودن `isStudent`، مقدار `"No"` را انتخاب می‌کند.
5. `` `...` ``: ساخت رشته نهایی چندخطی و خوانا با استفاده از متغیرها.

---

## 37. تمرین
### 🟢 تمرین‌های ساده
1. نوع داده `typeof 42n` چیست؟
2. طول رشته `"Hello World"` چقدر است؟
3. خروجی `"10" + 5` چیست؟
4. چگونه رشته `"javascript"` را با استفاده از یک متد به `"JAVASCRIPT"` تبدیل می‌کنید؟
5. خروجی `Boolean([])` چیست؟
6. چگونه مطمئن می‌شوید که یک متغیر `undefined` نیست؟
7. خروجی `Number("   ")` چیست؟
8. آخرین کاراکتر رشته `str` را با استفاده از متد `at` چگونه می‌گیرید؟
9. خروجی `typeof NaN` چیست؟
10. چگونه یک رشته را ۴ بار تکرار می‌کنید؟

### 🟡 تمرین‌های متوسط
11. تفاوت خروجی `"5" - 2` و `"5" + 2` را توضیح دهید.
12. با استفاده از `slice`، کلمه `"Script"` را از `"JavaScript"` استخراج کنید.
13. چرا `"0.1 + 0.2 === 0.3"` مقدار `false` برمی‌گرداند؟
14. چگونه بررسی می‌کنید که آیا رشته `"hello"` با `"he"` شروع می‌شود یا خیر؟
15. تمام فاصله‌های رشته `"   a b c   "` را فقط از ابتدا حذف کنید.
16. خروجی `Number.isNaN("hello")` و `isNaN("hello")` را مقایسه کنید.
17. چگونه یک `Symbol` سراسری (Global) ایجاد می‌کنید؟
18. چرا `Number.MIN_VALUE` یک عدد مثبت است؟
19. خروجی `"abc".substring(3, 1)` چیست و چرا؟
20. چگونه مقدار `null` را به رشته تبدیل می‌کنید و خروجی چیست؟

### 🔴 تمرین‌های چالشی
21. بدون استفاده از `+`، چگونه دو رشته را با هم ترکیب می‌کنید؟
22. چرا `typeof null === "object"` است و چگونه می‌توان به‌طور مطمئن `null` را بررسی کرد؟
23. خروجی `[] == ![]` چیست و دلیل منطقی پشت این Coercion چیست؟
24. چگونه یک ویژگی (Property) در یک شیء ایجاد می‌کنید که با `for...in` یا `Object.keys` قابل شمارش نباشد؟ (راهنمایی: Symbol)
25. چگونه می‌توانید مطمئن شوید که یک عدد واردشده توسط کاربر، یک عدد صحیح امن (Safe Integer) است؟

---

## پاسخ تمرین‌ها
<details>
<summary>برای مشاهده پاسخ‌ها کلیک کنید</summary>

1. `"bigint"`
2. `11` (فاصله هم شمرده می‌شود).
3. `"105"` (چون یکی رشته است، عملگر `+` باعث الحاق رشته می‌شود).
4. `"javascript".toUpperCase()`
5. `true` (آرایه خالی یک شیء است و تمام اشیاء Truthy هستند).
6. `if (variable !== undefined)`
7. `0` (فاصله‌های خالی در تبدیل به عدد، صفر در نظر گرفته می‌شوند).
8. `str.at(-1)`
9. `"number"`
10. `"text".repeat(4)`
11. `"5" - 2` می‌شود `3` (تفریق، رشته را به عدد تبدیل می‌کند). اما `"5" + 2` می‌شود `"52"` (جمع، باعث الحاق رشته می‌شود).
12. `"JavaScript".slice(4)` یا `"JavaScript".slice(-6)`
13. به دلیل محدودیت نمایش کسرها در مبنای ۲ (استاندارد IEEE 754) که باعث خطای گردکردن می‌شود.
14. `"hello".startsWith("he")`
15. `"   a b c   ".trimStart()`
16. `Number.isNaN("hello")` برابر `false` است (چون نوع آن عدد نیست). اما `isNaN("hello")` برابر `true` است (چون سعی می‌کند آن را به عدد تبدیل کند و شکست می‌خورد).
17. `Symbol.for("key")`
18. زیرا `MIN_VALUE` به معنی کوچک‌ترین مقدار مثبت غیرصفر قابل نمایش است، نه منفی‌ترین عدد.
19. `"bc"`. زیرا `substring` اگر start بزرگ‌تر از end باشد، به‌طور خودکار آرگومان‌ها را جابجا می‌کند و به `substring(1, 3)` تبدیل می‌شود.
20. `String(null)` که خروجی آن `"null"` (رشته) است.
21. با استفاده از متد `concat`: `"a".concat("b")` یا Template Literals: `` `${a}${b}` ``
22. این یک باگ تاریخی در طراحی اولیه زبان است. راه مطمئن: `value === null`.
23. `true`. دلیل: `![]` ابتدا آرایه را به boolean تبدیل می‌کند (`true`)، سپس آن را معکوس می‌کند (`false`). سپس در مقایسه `[] == false`، آرایه خالی به عدد `0` و `false` هم به عدد `0` تبدیل می‌شود. `0 == 0` برابر `true` است.
24. با استفاده از `Symbol` به عنوان کلید: `obj[Symbol('hidden')] = 'value'`.
25. با استفاده از `Number.isSafeInteger(value)`.
</details>

---

## 38. جمع‌بندی

| مفهوم | کاربرد |
| :--- | :--- |
| **Number** | ذخیره اعداد صحیح و اعشاری (استاندارد IEEE 754). |
| **String** | ذخیره متن (تغییرناپذیر / Immutable). |
| **Boolean** | مقادیر منطقی `true` یا `false`. |
| **Symbol** | ایجاد شناسه‌های کاملاً منحصر‌به‌فرد برای کلیدهای اشیاء. |
| **Undefined** | مقدار پیش‌فرض متغیرهای تعریف‌شده‌ی مقداردهی‌نشده. |
| **typeof** | عملگر تشخیص نوع داده (مراقب باگ `typeof null` باشید). |
| **Truthy/Falsy** | ارزیابی منطقی مقادیر (فقط ۸ مقدار Falsy هستند). |
| **Type Conversion** | تبدیل صریح (`Number()`) یا ضمنی (Coercion) انواع داده. |
| **`slice` vs `substring`** | `slice` از اندیس منفی پشتیبانی می‌کند و جابجا نمی‌کند. |
| **`at` vs `charAt`** | `at` روش مدرن‌تری است که از اندیس منفی برای شمارش از انتها پشتیبانی می‌کند. |

---

## 39. منابع معتبر
برای اطمینان از صحت فنی و به‌روز بودن مطالب، از منابع رسمی و استاندارد زیر استفاده شده است:

1. **MDN Web Docs (Mozilla)**: مرجع اصلی و استاندارد مستندات وب.
   - [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
   - [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
   - [Typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)
2. **ECMAScript Specification**: استاندارد رسمی زبان JavaScript.
   - [IEEE 754 & Number Type](https://tc39.es/ecma262/#sec-ecmascript-language-types-number-type)
3. **JavaScript.info**: یکی از بهترین و به‌روزترین آموزش‌های تعاملی JS.
   - [Type Conversions](https://javascript.info/type-conversions)
   - [String Methods](https://javascript.info/string)

---
*این سند با رعایت استانداردهای آموزشی و فنی روز (تا سال 2026) تهیه شده است. برای گزارش خطا یا پیشنهاد بهبود، لطفاً یک Issue در Repository باز کنید.*
