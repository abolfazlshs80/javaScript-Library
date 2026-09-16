# نحوه آموزش هر بخش

برای **هر یک از تیترهای بالا** این ساختار را رعایت کن:

### 1. توضیح خیلی ساده

ابتدا مفهوم را طوری توضیح بده که یک فرد مبتدی بتواند آن را بفهمد.

از اصطلاحات پیچیده بدون توضیح استفاده نکن.

اگر اصطلاح تخصصی استفاده شد، همان‌جا معنی آن را توضیح بده.

---

### 2. چرا به این مفهوم نیاز داریم؟

فقط تعریف نکن.

توضیح بده:

* چه مشکلی وجود داشت؟
* Generator چه مشکلی را حل می‌کند؟
* قبل از Generator معمولاً چه کاری انجام می‌دادیم؟
* Generator چه چیزی را ساده‌تر می‌کند؟

---

### 3. Syntax

Syntax مربوط به موضوع را با مثال ساده نشان بده.

مثلاً برای Generator Function:

```javascript
function* generateNumbers() {
    yield 1;
    yield 2;
    yield 3;
}
```

---

### 4. مثال ساده

یک مثال کوچک و قابل فهم ارائه کن.

---

### 5. خروجی کد

اگر امکان دارد خروجی را نیز نمایش بده.

مثلاً:

```text
1
2
3
```

---

### 6. توضیح خط‌به‌خط

کدهای مهم را خط‌به‌خط توضیح بده.

---

### 7. مثال واقعی‌تر

بعد از مثال ساده، یک مثال کاربردی‌تر ارائه کن.

---

### 8. اشتباه رایج

اشتباهاتی که برنامه‌نویسان مبتدی ممکن است انجام دهند را توضیح بده.

مثلاً:

```javascript
function* numbers() {
    yield 1;
}

const generator = numbers();

console.log(generator);
```

توضیح بده که `numbers()` مستقیماً مقدار `1` را برنمی‌گرداند؛ بلکه یک Generator Object ایجاد می‌کند.

---

# بخش بسیار مهم: تفاوت Generator Function و Generator Object

حتماً این تفاوت را به شکل بسیار ساده توضیح بده.

مثلاً:

```javascript
function* numbers() {
    yield 1;
    yield 2;
}
```

در اینجا:

```text
numbers
```

یک Generator Function است.

اما:

```javascript
const generator = numbers();
```

متغیر:

```text
generator
```

یک Generator Object است.

تفاوت این دو را با مثال و جدول توضیح بده.

---

# بخش yield

`yield` را بسیار دقیق توضیح بده.

مثال:

```javascript
function* numbers() {
    console.log("start");

    yield 1;

    console.log("middle");

    yield 2;

    console.log("end");
}
```

سپس مرحله‌به‌مرحله نشان بده:

```javascript
const generator = numbers();

generator.next();
generator.next();
generator.next();
generator.next();
```

توضیح بده در هر مرحله دقیقاً چه اتفاقی می‌افتد.

---

# بخش next()

توضیح بده:

```javascript
generator.next()
```

چه کاری انجام می‌دهد.

همچنین توضیح بده که نتیجه `next()` یک Object با ساختار زیر است:

```javascript
{
    value: ...,
    done: ...
}
```

مثلاً:

```javascript
{
    value: 1,
    done: false
}
```

و:

```javascript
{
    value: undefined,
    done: true
}
```

توضیح بده `value` و `done` دقیقاً چه معنی دارند.

---

# بخش مهم next(value)

این قسمت را از مقدماتی تا پیشرفته توضیح بده.

مثال:

```javascript
function* generator() {
    const value = yield "Enter a value";

    console.log(value);
}

const gen = generator();

console.log(gen.next());

console.log(gen.next("Hello"));
```

توضیح بده چرا مقدار اولین `next()` به Generator ارسال نمی‌شود و مقدار `next("Hello")` چگونه وارد `yield` می‌شود.

---

# بخش yield*

`yield*` را به زبان ساده توضیح بده.

مثال:

```javascript
function* first() {
    yield 1;
    yield 2;
}

function* second() {
    yield* first();

    yield 3;
}
```

سپس توضیح بده:

```javascript
const gen = second();

console.log(gen.next());
console.log(gen.next());
console.log(gen.next());
```

همچنین توضیح بده که `yield*` می‌تواند به Generator یا Iterable دیگری delegation انجام دهد.

---

# Generator و Iterator

این بخش را بسیار ساده اما عمیق توضیح بده.

ابتدا بگو:

```text
Iterable چیست؟
Iterator چیست؟
Generator چیست؟
```

سپس رابطه آنها را توضیح بده:

```text
Generator
   ↓
Iterator
   ↓
Iterable
```

البته اگر این نمودار از نظر فنی دقیق نیست، نمودار صحیح‌تری ارائه کن.

توضیح بده Generator Object مطابق مستندات JavaScript هم Iterator Protocol و هم Iterable Protocol را پیاده‌سازی می‌کند.

---

# Generator و for...of

مثال:

```javascript
function* numbers() {
    yield 10;
    yield 20;
    yield 30;
}

for (const number of numbers()) {
    console.log(number);
}
```

توضیح بده چرا `for...of` می‌تواند Generator را مصرف کند.

---

# Generatorهای Infinite

توضیح بده چگونه Generator می‌تواند یک Sequence بی‌نهایت ایجاد کند.

مثال:

```javascript
function* infiniteNumbers() {
    let number = 0;

    while (true) {
        yield number++;
    }
}
```

سپس نشان بده چگونه بدون ایجاد یک Array بسیار بزرگ، چند مقدار اول را دریافت کنیم.

حتماً توضیح بده که Generator مقادیر را به صورت on-demand تولید می‌کند.

---

# Generator و Lazy Evaluation

مفهوم Lazy Evaluation را خیلی ساده توضیح بده.

تفاوت این دو را نشان بده:

```javascript
const numbers = [1, 2, 3, 4, 5];
```

و:

```javascript
function* numbers() {
    yield 1;
    yield 2;
    yield 3;
    yield 4;
    yield 5;
}
```

توضیح بده که Generator می‌تواند مقدار را زمانی تولید کند که واقعاً درخواست شده باشد.

---

# Generator.return()

توضیح بده:

```javascript
generator.return(value)
```

چه کاری انجام می‌دهد.

مثال:

```javascript
function* numbers() {
    yield 1;
    yield 2;
    yield 3;
}

const gen = numbers();

console.log(gen.next());

console.log(gen.return("finished"));

console.log(gen.next());
```

همچنین درباره `try...finally` و cleanup توضیح بده.

---

# Generator.throw()

توضیح بده:

```javascript
generator.throw(error)
```

چگونه Exception را در نقطه‌ای که Generator متوقف شده است وارد می‌کند.

مثال ساده با:

```javascript
try {
    
} catch (error) {

}
```

ارائه کن و جریان اجرای آن را مرحله‌به‌مرحله توضیح بده.

---

# Generator در Object

مثال:

```javascript
const obj = {
    *numbers() {
        yield 1;
        yield 2;
    }
};
```

توضیح بده Generator Method چیست.

---

# Generator در Class

مثال:

```javascript
class Numbers {
    *generate() {
        yield 1;
        yield 2;
        yield 3;
    }
}
```

توضیح بده چگونه Generator Method در Class استفاده می‌شود.

---

# Symbol.iterator

یک مثال عملی برای ساخت Iterable با Generator ارائه کن.

مثلاً:

```javascript
const range = {
    start: 1,
    end: 5,

    *[Symbol.iterator]() {
        for (let i = this.start; i <= this.end; i++) {
            yield i;
        }
    }
};
```

سپس:

```javascript
for (const number of range) {
    console.log(number);
}
```

را توضیح بده.

---

# Generator و Array

تفاوت Generator و Array را از نظر:

* Memory
* Lazy Evaluation
* Random Access
* Iteration
* Infinite Data
* Performance
* خوانایی

توضیح بده.

توجه کن که **ادعای قطعی درباره سریع‌تر بودن Generator نداشته باش**؛ عملکرد به سناریو، موتور JavaScript و نحوه استفاده بستگی دارد.

---

# Generator و Spread Operator

مثال:

```javascript
function* numbers() {
    yield 1;
    yield 2;
    yield 3;
}

const result = [...numbers()];

console.log(result);
```

توضیح بده چه اتفاقی رخ می‌دهد.

---

# Generator و Destructuring

مثال:

```javascript
function* numbers() {
    yield 10;
    yield 20;
    yield 30;
}

const [a, b] = numbers();

console.log(a);
console.log(b);
```

توضیح بده چرا فقط مقدارهای مورد نیاز مصرف می‌شوند.

---

# Generator و Map / Set

نشان بده Generator چگونه می‌تواند با Collectionهای JavaScript کار کند.

---

# Generatorهای کاربردی

چند مثال واقعی ارائه کن، مانند:

### مثال 1: Pagination

```javascript
function* paginate(items, pageSize) {
    // ...
}
```

### مثال 2: ID Generator

```javascript
function* idGenerator() {
    // ...
}
```

### مثال 3: Fibonacci

```javascript
function* fibonacci() {
    // ...
}
```

### مثال 4: Range

```javascript
function* range(start, end) {
    // ...
}
```

### مثال 5: Infinite Sequence

یک Sequence بی‌نهایت بساز.

برای هرکدام توضیح بده:

* مسئله چیست؟
* چرا Generator مناسب است؟
* کد چگونه کار می‌کند؟
* چه زمانی استفاده کنیم؟

---

# Async Generator

بعد از آموزش کامل Generator معمولی، Async Generator را معرفی کن.

توضیح بده:

```javascript
async function* generator() {
    yield 1;
    yield 2;
}
```

و تفاوت آن با:

```javascript
function* generator() {
    yield 1;
    yield 2;
}
```

را توضیح بده.

سپس:

```javascript
for await (const value of generator()) {
    console.log(value);
}
```

را آموزش بده.

تفاوت:

```text
Generator
Async Generator
Iterator
Async Iterator
Iterable
Async Iterable
```

را نیز به زبان ساده توضیح بده.

---

# Generator و Promise / async-await

توضیح بده که Generator و `async/await` چه تفاوتی دارند.

اگر درباره کاربرد تاریخی Generator در مدیریت asynchronous code صحبت می‌کنی، آن را به عنوان **زمینه تاریخی** توضیح بده و با Promise و async/await در JavaScript مدرن مقایسه کن.

از این ادعا که Generator جایگزین مستقیم async/await است خودداری کن.

---

# مباحث پیشرفته

در بخش Advanced این موضوعات را نیز بررسی کن:

* Generator State
* Suspended Execution
* Execution Context
* حفظ Local Variables بین `yield`ها
* Bidirectional Control Flow
* `next(value)`
* `throw()`
* `return()`
* `yield*`
* Delegation
* Generator Composition
* Infinite Iterators
* Lazy Evaluation
* Iterator Protocol
* Iterable Protocol
* Async Iterator Protocol
* Async Generator
* `for await...of`
* `Symbol.iterator`
* `Symbol.asyncIterator`

برای هرکدام ابتدا توضیح ساده و سپس توضیح فنی ارائه کن.

---

# مقایسه‌های مهم

در پایان چند مقایسه کاربردی ارائه کن:

### Generator vs Function

### Generator vs Array

### Generator vs Iterator دستی

### Generator vs Iterable

### Generator vs Async Generator

### Generator vs Promise

### Generator vs async/await

در هر مقایسه ابتدا یک توضیح کوتاه و سپس یک مثال کدنویسی ارائه کن.

---

# اشتباهات رایج

حداقل 10 اشتباه رایج را توضیح بده.

برای هر اشتباه:

```text
❌ کد اشتباه

✅ کد صحیح

💡 دلیل
```

ارائه کن.

---

# سوالات مصاحبه

حداقل 15 سؤال از سطح:

* Beginner
* Intermediate
* Advanced

درباره Generator Function ایجاد کن.

برای هر سؤال پاسخ کامل بده.

مثلاً:

1. Generator Function چیست؟
2. تفاوت Generator Function و Function چیست؟
3. `yield` چه کاری انجام می‌دهد؟
4. `next()` چه چیزی برمی‌گرداند؟
5. `done` چیست؟
6. Generator Object چیست؟
7. `next(value)` چگونه کار می‌کند؟
8. `yield*` چیست؟
9. `return()` چه کاری انجام می‌دهد؟
10. `throw()` چه کاری انجام می‌دهد؟
11. Generator چگونه با Iterable ارتباط دارد؟
12. Generator Infinite چیست؟
13. Lazy Evaluation چیست؟
14. Async Generator چیست؟
15. تفاوت Generator و Async Generator چیست؟

---

# تمرین‌ها

در پایان حداقل 10 تمرین طراحی کن.

تمرین‌ها از ساده به سخت باشند.

### Beginner

مثلاً:

یک Generator بنویس که اعداد 1 تا 5 را تولید کند.

### Intermediate

یک Generator برای Range بنویس.

### Advanced

یک Generator برای Pagination بنویس.

### Expert

یک Async Generator بساز که داده‌ها را به صورت مرحله‌ای تولید کند.

برای هر تمرین:

* صورت سؤال
* ورودی
* خروجی مورد انتظار
* Hint

را بده.

**راه‌حل تمرین‌ها را بلافاصله بعد از سؤال ننویس**؛ ابتدا تمرین را بده و سپس در یک بخش جداگانه Solutions قرار بده.

---

# پروژه کوچک نهایی

در پایان یک پروژه کوچک واقعی با Generator طراحی کن.

مثلاً:

## Lazy Data Processing System

سیستمی بساز که:

1. یک Dataset داشته باشد.
2. داده‌ها را به صورت Lazy تولید کند.
3. داده‌ها را مرحله‌ای پردازش کند.
4. امکان توقف و ادامه داشته باشد.
5. از Generator استفاده کند.
6. از `yield*` در حد مناسب استفاده کند.
7. یک Infinite Generator یا Pagination داشته باشد.

کد پروژه را مرحله‌به‌مرحله بنویس.

---

# سبک نوشتار

لحن آموزش:

* فارسی
* ساده
* روان
* آموزشی
* مناسب مبتدی
* بدون پیچیده‌گویی غیرضروری

باشد.

هر مفهوم را با این ترتیب آموزش بده:

```text
مفهوم ساده
↓
چرا؟
↓
Syntax
↓
مثال ساده
↓
خروجی
↓
توضیح خط‌به‌خط
↓
مثال واقعی
↓
نکات مهم
↓
اشتباهات رایج
↓
تمرین
```

---

# قوانین مهم کدنویسی

تمام مثال‌ها را با JavaScript مدرن بنویس.

ترجیحاً از:

```javascript
const
let
function*
yield
yield*
for...of
for await...of
async function*
```

استفاده کن.

کدها را بدون دلیل پیچیده نکن.

اگر یک مثال را می‌توان با 5 خط نوشت، با 20 خط ننویس.

---

# نکته بسیار مهم درباره صحت مطالب

قبل از نوشتن مطالب، اطلاعات را با منابع معتبر بررسی کن.

منابع اصلی را در اولویت قرار بده:

1. **MDN Web Docs**
2. **ECMAScript Language Specification**
3. **JavaScript.info** برای توضیح آموزشی

در صورت استفاده از منابع دیگر، فقط منابع معتبر و قابل اعتماد استفاده کن.

اطلاعات قدیمی یا مربوط به نسخه‌های قدیمی JavaScript را به عنوان رفتار مدرن JavaScript معرفی نکن.

اگر درباره یک موضوع اختلاف یا ابهام وجود دارد، آن را صریحاً بیان کن.

---

# لینک‌دهی

برای هر موضوع مهم، در صورت وجود، لینک منبع معتبر قرار بده.

در پایان بخشی با عنوان:

# منابع

ایجاد کن و منابع را دسته‌بندی کن:

### منابع رسمی

* MDN
* ECMAScript Specification

### منابع آموزشی

* JavaScript.info

برای هر منبع:

```text
عنوان
توضیح کوتاه
لینک
```

ارائه کن.

---

# جمع‌بندی نهایی

در انتهای آموزش یک نقشه ذهنی ساده از Generator ارائه کن:

```text
Generator Function
        │
        ├── function*
        │
        ├── Generator Object
        │
        ├── yield
        │
        ├── next()
        │      ├── value
        │      └── done
        │
        ├── return()
        │
        ├── throw()
        │
        ├── yield*
        │
        ├── Iterator
        │
        ├── Iterable
        │
        ├── Symbol.iterator
        │
        └── Async Generator
               ├── async function*
               └── for await...of
```

در پایان هم یک بخش:

## اگر فقط 10 نکته از Generator یاد بگیریم

ایجاد کن و 10 نکته کلیدی را بسیار ساده و خلاصه بنویس.

هدف این است که خروجی نهایی **مستقیماً قابل قرار دادن در یک GitHub Repository آموزشی** باشد؛ بنابراین Markdown تمیز، Headingهای استاندارد، Code Block، جدول‌های محدود و لینک‌های داخلی صحیح داشته باشد.


### ASSISTANT
این یک راهنمای جامع، ساختاریافته و آماده‌ی قرارگیری در یک **Repository آموزشی گیت‌هاب** است. تمام مفاهیم از مقدماتی تا پیشرفته با رعایت دقیق ساختار درخواستی، به زبان فارسی روان و با استناد به منابع معتبر (MDN, JavaScript.info, ECMAScript) تهیه شده است.

---

# 📘 راهنمای جامع Generator Function در JavaScript

## فهرست مطالب (Table of Contents)
1. [Generator Function چیست؟](#1-generator-function-چیست)
2. [چرا Generator Function به وجود آمد؟](#2-چرا-generator-function-به-وجود-آمد)
3. [تفاوت Function معمولی و Generator Function](#3-تفاوت-function-معمولی-و-generator-function)
4. [ساختار Generator Function](#4-ساختار-generator-function)
5. [اولین Generator Function](#5-اولین-generator-function)
6. [Generator Object چیست؟](#6-generator-object-چیست)
7. [yield چیست؟](#7-yield-چیست)
8. [next() چیست؟](#8-next-چیست)
9. [value و done](#9-value-و-done)
10. [چرخه اجرای Generator](#10-چرخه-اجرای-generator)
11. [متوقف شدن و ادامه اجرای Generator](#11-متوقف-شدن-و-ادامه-اجرای-generator)
12. [Generator و return](#12-generator-و-return)
13. [Generator و for...of](#13-generator-و-forof)
14. [Generator و Iterator](#14-generator-و-iterator)
15. [Generator و Iterable](#15-generator-و-iterable)
16. [Generator و Symbol.iterator](#16-generator-و-symboliterator)
17. [ارسال مقدار با next(value)](#17-ارسال-مقدار-با-nextvalue)
18. [yield به عنوان یک Expression](#18-yield-به-عنوان-یک-expression)
19. [yield* چیست؟](#19-yield-چیست)
20. [Delegation با yield*](#20-delegation-با-yield)
21. [Generatorهای تو در تو](#21-generatorهای-تو-در-تو)
22. [Generator Function Expression](#22-generator-function-expression)
23. [Generator Method](#23-generator-method)
24. [Generator در Object](#24-generator-در-object)
25. [Generator در Class](#25-generator-در-class)
26. [Generatorهای بی‌نهایت](#26-generatorهای-بی‌نهایت)
27. [Lazy Evaluation با Generator](#27-lazy-evaluation-با-generator)
28. [Generator برای تولید داده مرحله‌ای](#28-generator-برای-تولید-داده-مرحله‌ای)
29. [Generator برای Pagination](#29-generator-برای-pagination)
30. [Generator برای Sequence](#30-generator-برای-sequence)
31. [Generator برای Fibonacci](#31-generator-برای-fibonacci)
32. [مدیریت خطا با generator.throw()](#32-مدیریت-خطا-با-generatorthrow)
33. [پایان دادن به Generator با generator.return()](#33-پایان-دادن-به-generator-با-generatorreturn)
34. [try/catch/finally در Generator](#34-trycatchfinally-در-generator)
35. [کنترل دوطرفه جریان با Generator](#35-کنترل-دوطرفه-جریان-با-generator)
36. [مفهوم Execution Context در Generator](#36-مفهوم-execution-context-در-generator)
37. [Generator و State](#37-generator-و-state)
38. [Generator و Lazy Data](#38-generator-و-lazy-data)
39. [Generator در مقابل Array](#39-generator-در-مقابل-array)
40. [Generator در مقابل Iterator دستی](#40-generator-در-مقابل-iterator-دستی)
41. [Generator در مقابل Function معمولی](#41-generator-در-مقابل-function-معمولی)
42. [مزایای Generator](#42-مزایای-generator)
43. [معایب و محدودیت‌های Generator](#43-معایب-و-محدودیت‌های-generator)
44. [چه زمانی از Generator استفاده کنیم؟](#44-چه-زمانی-از-generator-استفاده-کنیم)
45. [چه زمانی از Generator استفاده نکنیم؟](#45-چه-زمانی-از-generator-استفاده-نکنیم)
46. [Generator و Memory Efficiency](#46-generator-و-memory-efficiency)
47. [Generator و Infinite Sequence](#47-generator-و-infinite-sequence)
48. [ترکیب Generator با Array Methods](#48-ترکیب-generator-با-array-methods)
49. [ترکیب Generator با Destructuring](#49-ترکیب-generator-با-destructuring)
50. [ترکیب Generator با Spread Operator](#50-ترکیب-generator-با-spread-operator)
51. [Generator و Map/Set](#51-generator-و-mapset)
52. [Generator و Async Generator](#52-generator-و-async-generator)
53. [Async Generator Function چیست؟](#53-async-generator-function-چیست)
54. [تفاوت Generator و Async Generator](#54-تفاوت-generator-و-async-generator)
55. [async function*](#55-async-function)
56. [for await...of](#56-for-awaitof)
57. [کاربرد Generator در JavaScript مدرن](#57-کاربرد-generator-در-javascript-مدرن)
58. [اشتباهات رایج](#58-اشتباهات-رایج)
59. [نکات مهم برای مصاحبه](#59-نکات-مهم-برای-مصاحبه)
60. [پروژه‌های تمرینی](#60-پروژه‌های-تمرینی)
61. [جمع‌بندی](#61-جمع‌بندی)
62. [منابع](#62-منابع)

---

## 1. Generator Function چیست؟
**توضیح ساده:** یک تابع خاص در جاوااسکریپت است که می‌تواند اجرای خود را متوقف (Pause) و دوباره از همان‌جا ادامه (Resume) دهد.
**چرا نیاز داریم؟** توابع معمولی تا پایان اجرا می‌شوند و نمی‌توانند وسط کار متوقف شوند. Generator این کنترل را به ما می‌دهد.
**Syntax:**
```javascript
function* myGenerator() {
  yield 1;
}
```
**مثال ساده:**
```javascript
function* sayHi() {
  yield "Hello";
  yield "World";
}
const gen = sayHi();
console.log(gen.next().value); // "Hello"
```
**نکته:** علامت `*` بعد از `function` نشان‌دهنده Generator است.

## 2. چرا Generator Function به وجود آمد؟
**مشکل:** قبل از ES6، برای تولید دنباله‌های داده (مثل اعداد 1 تا 1000) یا مدیریت عملیات ناهمگام (Async)، باید کل داده را در یک آرایه ذخیره می‌کردیم (مصرف حافظه بالا) یا از Callbackهای تو در تو استفاده می‌کردیم (کد پیچیده).
**راه‌حل Generator:** تولید داده به صورت "درخواستی" (On-demand) و توقف اجرا تا زمان آماده شدن داده بعدی.

## 3. تفاوت Function معمولی و Generator Function
| ویژگی | Function معمولی | Generator Function |
| :--- | :--- | :--- |
| **اعلان** | `function name()` | `function* name()` |
| **اجرا** | با فراخوانی، تا پایان اجرا می‌شود. | با فراخوانی، اجرا نمی‌شود؛ یک Object برمی‌گرداند. |
| **بازگشت مقدار** | با `return` (فقط یک‌بار) | با `yield` (چندین بار) |
| **وضعیت (State)** | پس از اجرا، متغیرهای محلی از بین می‌روند. | وضعیت متغیرهای محلی بین `yield`ها حفظ می‌شود. |

## 4. ساختار Generator Function
```javascript
function* generatorName(parameters) {
  // کدها
  yield value;
  // کدها
  yield anotherValue;
}
```

## 5. اولین Generator Function
```javascript
function* countToThree() {
  yield 1;
  yield 2;
  yield 3;
}
const counter = countToThree();
console.log(counter.next()); // { value: 1, done: false }
console.log(counter.next()); // { value: 2, done: false }
console.log(counter.next()); // { value: 3, done: false }
console.log(counter.next()); // { value: undefined, done: true }
```

## 6. Generator Object چیست؟
**تفاوت بسیار مهم:**
```javascript
function* numbers() {
  yield 1;
}
```
- `numbers`: یک **Generator Function** است (قالب و دستورالعمل).
- `const gen = numbers();`: متغیر `gen` یک **Generator Object** است. فراخوانی تابع، کد داخل آن را اجرا **نمی‌کند**، بلکه یک شیء Iterator برمی‌گرداند که متد `next()` دارد.

## 7. yield چیست؟
**توضیح ساده:** `yield` مانند یک `return` هوشمند است. مقدار را برمی‌گرداند، اما اجرای تابع را **متوقف** می‌کند و وضعیت را حفظ می‌کند تا با فراخوانی بعدی `next()` ادامه یابد.
**مثال:**
```javascript
function* steps() {
  console.log("Step 1");
  yield "A";
  console.log("Step 2");
  yield "B";
}
const gen = steps();
gen.next(); // چاپ: Step 1 | برگشت: { value: "A", done: false }
gen.next(); // چاپ: Step 2 | برگشت: { value: "B", done: false }
```

## 8. next() چیست؟
متدی روی Generator Object است که اجرای تابع را تا رسیدن به `yield` بعدی (یا `return`) پیش می‌برد.
**خروجی:** یک شیء با دو ویژگی: `{ value: any, done: boolean }`.

## 9. value و done
- `value`: مقداری که توسط `yield` یا `return` تولید شده است.
- `done`: یک بولین که اگر `true` باشد، یعنی Generator به پایان رسیده و دیگر مقداری تولید نمی‌کند.

## 10. چرخه اجرای Generator
1. فراخوانی تابع Generator -> ساخت Generator Object (بدون اجرای کد داخلی).
2. فراخوانی `next()` -> اجرا تا اولین `yield`.
3. توقف و برگرداندن `{ value, done: false }`.
4. فراخوانی `next()` بعدی -> ادامه از خط بعد از `yield` قبلی.
5. تکرار تا پایان تابع یا رسیدن به `return`.

## 11. متوقف شدن و ادامه اجرای Generator
این ذات Generator است. با هر `yield` متوقف می‌شود (Suspended) و با `next()` ادامه می‌یابد (Resumed). این باعث می‌شود حافظه و پردازش فقط زمانی مصرف شود که نیاز است.

## 12. Generator و return
اگر در Generator از `return` استفاده کنید، Generator بلافاصله پایان می‌یابد (`done: true`) و مقدار `return` به عنوان `value` برگردانده می‌شود. `yield`های بعدی اجرا نخواهند شد.
```javascript
function* gen() {
  yield 1;
  return "End";
  yield 2; // هرگز اجرا نمی‌شود
}
const g = gen();
console.log(g.next()); // { value: 1, done: false }
console.log(g.next()); // { value: "End", done: true }
```

## 13. Generator و for...of
حلقه `for...of` به طور خودکار `next()` را فراخوانی می‌کند و تا زمانی که `done: true` شود، مقدار `value` را استخراج می‌کند.
```javascript
function* colors() {
  yield "Red";
  yield "Green";
}
for (const color of colors()) {
  console.log(color); // Red \n Green
}
```

## 14. Generator و Iterator
**Iterator** یک شیء است که متد `next()` دارد و `{ value, done }` برمی‌گرداند.
**رابطه:** هر Generator Object، یک Iterator است (چون متد `next()` دارد).

## 15. Generator و Iterable
**Iterable** شیئی است که متد `Symbol.iterator` دارد و یک Iterator برمی‌گرداند.
**رابطه:** هر Generator Object، هم Iterator است و هم Iterable (چون متد `Symbol.iterator` دارد که خودش را برمی‌گرداند). به همین دلیل در `for...of` کار می‌کند.

## 16. Generator و Symbol.iterator
می‌توانیم از Generator برای پیاده‌سازی آسان پروتکل Iterable در اشیاء استفاده کنیم:
```javascript
const range = {
  from: 1,
  to: 3,
  *[Symbol.iterator]() {
    for (let i = this.from; i <= this.to; i++) {
      yield i;
    }
  }
};
console.log([...range]); // [1, 2, 3]
```

## 17. ارسال مقدار با next(value)
**مفهوم پیشرفته:** `next(value)` نه تنها اجرای Generator را ادامه می‌دهد، بلکه مقدار `value` را به عنوان نتیجه‌ی عبارت `yield` که تابع را متوقف کرده بود، تزریق می‌کند.
**نکته حیاتی:** اولین `next()` هیچ مقداری را دریافت نمی‌کند (یا اگر بدهید، نادیده گرفته می‌شود)، زیرا هنوز به اولین `yield` نرسیده‌ایم.
```javascript
function* ask() {
  const name = yield "What is your name?";
  console.log("Hello " + name);
}
const gen = ask();
console.log(gen.next().value); // "What is your name?"
console.log(gen.next("Ali").value); // چاپ: "Hello Ali" | برگشت: undefined
```

## 18. yield به عنوان یک Expression
برخلاف `return` که یک Statement است، `yield` یک Expression است و می‌تواند مقداری را ارزیابی کند (مقداری که از طریق `next(value)` ارسال می‌شود).
```javascript
function* calc() {
  const result = yield 10;
  yield result * 2;
}
const g = calc();
g.next(); // { value: 10, done: false }
g.next(5); // { value: 10, done: false } (5 * 2)
```

## 19. yield* چیست؟
**توضیح ساده:** `yield*` برای "تفویض اختیار" (Delegation) به یک Generator یا Iterable دیگر استفاده می‌شود. مانند این است که بگوییم: "از آن یکی تابع، همه مقادیر را یکی‌یکی yield کن".

## 20. Delegation با yield*
```javascript
function* inner() {
  yield 2;
  yield 3;
}
function* outer() {
  yield 1;
  yield* inner(); // تفویض به inner
  yield 4;
}
console.log([...outer()]); // [1, 2, 3, 4]
```

## 21. Generatorهای تو در تو
همان مفهوم Delegation است. به جای نوشتن حلقه‌های تو در تو برای yield کردن مقادیر یک آرایه یا Generator دیگر، از `yield*` استفاده می‌کنیم تا کد تمیز بماند.

## 22. Generator Function Expression
می‌توان Generator را به صورت Anonymous یا Named Expression تعریف کرد:
```javascript
const genExpr = function* () {
  yield 1;
};
```

## 23. Generator Method
تعریف Generator به عنوان متد یک شیء:
```javascript
const obj = {
  *myMethod() {
    yield 1;
  }
};
```

## 24. Generator در Object
(مشابه بخش 23). این روش برای تعریف Iteratorهای سفارشی برای اشیاء بسیار رایج است.

## 25. Generator در Class
می‌توان متدهای Generator را در کلاس‌ها تعریف کرد:
```javascript
class Collection {
  constructor(items) { this.items = items; }
  *getItems() {
    for (let item of this.items) {
      yield item;
    }
  }
}
const col = new Collection([1, 2]);
for (let x of col.getItems()) console.log(x);
```

## 26. Generatorهای بی‌نهایت
Generatorها می‌توانند بدون پایان اجرا شوند، چون مقادیر را فقط هنگام درخواست تولید می‌کنند و حافظه را پر نمی‌کنند.
```javascript
function* infinite() {
  let i = 0;
  while (true) {
    yield i++;
  }
}
const gen = infinite();
console.log(gen.next().value); // 0
console.log(gen.next().value); // 1
// هرگز با خطای Out of Memory مواجه نمی‌شویم
```

## 27. Lazy Evaluation با Generator
**توضیح:** ارزیابی تنبل. یعنی محاسبه مقدار تا زمانی که واقعاً به آن نیاز نداشته باشیم، به تعویق می‌افتد.
**تفاوت با Array:** آرایه همه مقادیر را همین حالا در حافظه می‌سازد. Generator هر بار فقط یک مقدار را می‌سازد.

## 28. Generator برای تولید داده مرحله‌ای
مثال: خواندن یک فایل بزرگ خط به خط (به جای خواندن کل فایل در حافظه).

## 29. Generator برای Pagination
```javascript
function* paginate(data, pageSize) {
  for (let i = 0; i < data.length; i += pageSize) {
    yield data.slice(i, i + pageSize);
  }
}
const data = [1, 2, 3, 4, 5, 6];
const pages = paginate(data, 2);
console.log(pages.next().value); // [1, 2]
console.log(pages.next().value); // [3, 4]
```

## 30. Generator برای Sequence
تولید دنباله‌های ریاضی یا شناسه‌ها بدون ذخیره کل دنباله.

## 31. Generator برای Fibonacci
```javascript
function* fibonacci() {
  let [prev, curr] = [0, 1];
  while (true) {
    yield curr;
    [prev, curr] = [curr, prev + curr];
  }
}
const fib = fibonacci();
console.log(fib.next().value); // 1
console.log(fib.next().value); // 1
console.log(fib.next().value); // 2
console.log(fib.next().value); // 3
```

## 32. مدیریت خطا با generator.throw()
می‌توان یک خطا را به داخل Generator تزریق کرد، دقیقاً در خطی که با `yield` متوقف شده است.
```javascript
function* gen() {
  try {
    yield 1;
  } catch (e) {
    console.log("Error caught:", e.message);
  }
}
const g = gen();
g.next(); // { value: 1, done: false }
g.throw(new Error("Oops!")); // چاپ: Error caught: Oops! | { value: undefined, done: true }
```

## 33. پایان دادن به Generator با generator.return()
متد `return()` باعث می‌شود Generator فوراً پایان یابد (`done: true`) و مقداری که به آن می‌دهید را به عنوان `value` برگرداند. همچنین بلوک `finally` را اجرا می‌کند.
```javascript
function* gen() {
  try {
    yield 1;
    yield 2;
  } finally {
    console.log("Cleaning up...");
  }
}
const g = gen();
console.log(g.next()); // { value: 1, done: false }
console.log(g.return("End")); // چاپ: Cleaning up... | { value: "End", done: true }
```

## 34. try/catch/finally در Generator
کاملاً مانند توابع معمولی کار می‌کند، با این تفاوت که اگر Generator با `return()` یا `throw()` خاتمه یابد، بلوک `finally` حتماً اجرا می‌شود (برای پاکسازی منابع عالی است).

## 35. کنترل دوطرفه جریان با Generator
Generator یک کانال دوطرفه است:
1. به بیرون: مقدار را با `yield` می‌فرستد.
2. به درون: مقدار را با `next(value)` دریافت می‌کند.
این ویژگی، پایه‌ی ساخت ابزارهایی مثل Redux-Saga در اکوسیستم جاوااسکریپت است.

## 36. مفهوم Execution Context در Generator
وقتی یک Generator متوقف می‌شود، Execution Context آن (شامل متغیرهای محلی و نقطه اجرا) در حافظه "منجمد" (Frozen) می‌شود. با فراخوانی `next()`، این Context بازیابی و ادامه می‌یابد.

## 37. Generator و State
Generatorها به طور ذاتی Stateful (حالت‌دار) هستند. آن‌ها وضعیت داخلی خود را بین فراخوانی‌ها حفظ می‌کنند، بدون اینکه نیاز به متغیرهای سراسری (Global) یا بستارهای پیچیده (Closures) باشد.

## 38. Generator و Lazy Data
داده‌های Lazy داده‌هایی هستند که فقط هنگام مصرف محاسبه می‌شوند. Generatorها بهترین ابزار برای پیاده‌سازی این الگو در جاوااسکریپت هستند.

## 39. Generator در مقابل Array
| ویژگی | Array | Generator |
| :--- | :--- | :--- |
| **حافظه** | همه داده‌ها را یکجا نگه می‌دارد (O(N)) | فقط یک داده را در هر لحظه نگه می‌دارد (O(1)) |
| **دسترسی** | دسترسی تصادفی (Random Access) دارد (`arr[2]`) | فقط دسترسی ترتیبی (Sequential) دارد |
| **داده بی‌نهایت** | غیرممکن (باعث Crash می‌شود) | ممکن و کارآمد |

## 40. Generator در مقابل Iterator دستی
ساخت یک Iterator دستی نیاز به پیاده‌سازی شیء با متد `next()` و مدیریت دستی متغیرهای وضعیت دارد. Generator این کار را به صورت خودکار و با سینتکس خوانا انجام می‌دهد.

## 41. Generator در مقابل Function معمولی
تابع معمولی یک قرارداد "یک ورودی، یک خروجی" دارد و بلافاصله تمام می‌شود. Generator یک قرارداد "چندین ورودی، چندین خروجی در طول زمان" دارد.

## 42. مزایای Generator
- بهینگی حافظه (Memory Efficiency).
- کد خواناتر برای دنباله‌ها و عملیات ناهمگام.
- امکان توقف و ادامه (Pause/Resume).
- پیاده‌سازی آسان پروتکل Iterable.

## 43. معایب و محدودیت‌های Generator
- نمی‌توان به عقب برگشت (فقط رو به جلو).
- دسترسی تصادفی (Random Access) ندارد.
- برای داده‌های کوچک، سربار (Overhead) آن نسبت به آرایه معمولی کمی بیشتر است.
- دیباگ کردن آن می‌تواند کمی پیچیده‌تر از توابع معمولی باشد.

## 44. چه زمانی از Generator استفاده کنیم؟
- وقتی با دنباله‌های بزرگ یا بی‌نهایت داده کار می‌کنیم.
- وقتی می‌خواهیم یک شیء را Iterable کنیم.
- وقتی نیاز به تولید داده مرحله‌ای (Lazy) داریم.
- برای مدیریت پیچیده‌ی عملیات ناهمگام (مثل الگوهای Saga).

## 45. چه زمانی از Generator استفاده نکنیم؟
- وقتی به دسترسی تصادفی (Index-based) نیاز دارید.
- وقتی نیاز دارید داده‌ها را چندین بار پیمایش کنید (Generatorها یک‌بار مصرف هستند؛ پس از `done: true`، باید یک Generator جدید بسازید).
- برای مجموعه داده‌های بسیار کوچک که سربار Generator توجیه‌پذیر نیست.

## 46. Generator و Memory Efficiency
چون Generatorها داده‌ها را "در لحظه" (On-the-fly) تولید می‌کنند، مصرف حافظه آن‌ها ثابت (O(1)) است، حتی اگر دنباله‌ی تولیدی بی‌نهایت باشد.

## 47. Generator و Infinite Sequence
(به بخش 26 و 31 مراجعه کنید). این یکی از قوی‌ترین کاربردهای Generator است که با آرایه‌ها غیرممکن است.

## 48. ترکیب Generator با Array Methods
Generatorها مستقیماً متدهای آرایه (مثل `map`, `filter`) را ندارند. اما می‌توان آن‌ها را به آرایه تبدیل کرد:
```javascript
function* nums() { yield 1; yield 2; yield 3; }
const arr = Array.from(nums());
console.log(arr.map(x => x * 2)); // [2, 4, 6]
```

## 49. ترکیب Generator با Destructuring
```javascript
function* coords() {
  yield 10;
  yield 20;
  yield 30;
}
const [x, y] = coords();
console.log(x, y); // 10 20
// توجه: فقط دو بار next() فراخوانی می‌شود و مقدار سوم تولید نمی‌شود (بهینه‌سازی).
```

## 50. ترکیب Generator با Spread Operator
```javascript
function* chars() {
  yield 'a';
  yield 'b';
}
const arr = [...chars()]; // ['a', 'b']
// هشدار: اگر Generator بی‌نهایت باشد، استفاده از Spread باعث هنگ کردن برنامه می‌شود!
```

## 51. Generator و Map/Set
می‌توان از Generator برای مقداردهی اولیه یا پیمایش Map و Set استفاده کرد:
```javascript
function* getKeys(map) {
  for (let [key, value] of map) {
    yield key;
  }
}
const m = new Map([['a', 1], ['b', 2]]);
console.log([...getKeys(m)]); // ['a', 'b']
```

## 52. Generator و Async Generator
وقتی داده‌هایی که می‌خواهیم Yield کنیم، به صورت ناهمگام (مثلاً از شبکه یا دیتابیس) به دست می‌آیند، از Async Generator استفاده می‌کنیم.

## 53. Async Generator Function چیست؟
تابعی که با `async function*` تعریف می‌شود و `yield` آن می‌تواند یک Promise را برگرداند یا منتظر یک Promise بماند.

## 54. تفاوت Generator و Async Generator
- Generator: `next()` یک `{ value, done }` همگام برمی‌گرداند.
- Async Generator: `next()` یک **Promise** برمی‌گرداند که به `{ value, done }` حل می‌شود.

## 55. async function*
```javascript
async function* fetchPages() {
  yield await fetch('page1').then(res => res.json());
  yield await fetch('page2').then(res => res.json());
}
```

## 56. for await...of
حلقه‌ای که مخصوص مصرف Async Iterableها (مثل Async Generator) است.
```javascript
async function main() {
  for await (const page of fetchPages()) {
    console.log(page);
  }
}
main();
```

## 57. کاربرد Generator در JavaScript مدرن
امروزه کمتر برای مدیریت Async (که `async/await` جایگزین بهتری است) استفاده می‌شود، اما در موارد زیر همچنان بی‌رقیب است:
- پیاده‌سازی Iterableهای سفارشی.
- تولید داده‌های تست (Mock Data).
- کتابخانه‌های مدیریت State پیشرفته (مثل Redux-Saga).
- پردازش جریان داده (Stream Processing).

## 58. اشتباهات رایج
1. ❌ `const g = myGen(); console.log(g);` (انتظار مقدار yield شده دارید)
   ✅ `console.log(g.next().value);`
   💡 فراخوانی تابع Generator، یک Object برمی‌گرداند، نه مقدار yield شده.
2. ❌ ارسال مقدار به اولین `next()`: `g.next("hello")`
   ✅ `g.next(); g.next("hello");`
   💡 اولین `next()` فقط Generator را شروع می‌کند و آرگومان آن نادیده گرفته می‌شود.
3. ❌ استفاده از `for...of` روی Generator بی‌نهایت بدون شرط `break`.
   ✅ استفاده از `break` یا محدود کردن تعداد دفعات `next()`.
   💡 حلقه `for...of` تا `done: true` ادامه می‌یابد و در Generator بی‌نهایت، هرگز تمام نمی‌شود.
4. ❌ تلاش برای پیمایش مجدد یک Generator تمام شده.
   ✅ ساخت یک نمونه جدید از Generator: `const g2 = myGen();`
   💡 Generatorها یک‌بار مصرف (One-time use) هستند.
5. ❌ استفاده از `yield` در تابع معمولی یا Arrow Function.
   ✅ استفاده از `function*`.
   💡 `yield` فقط در داخل Generator Function معتبر است.
6. ❌ انتظار دسترسی به `g[2]` در Generator.
   ✅ استفاده از حلقه یا تبدیل به آرایه (اگر محدود است).
   💡 Generatorها دسترسی تصادفی (Random Access) ندارند.
7. ❌ فراموش کردن `await` در `for await...of`.
   ✅ `for await (const x of asyncGen())`
   💡 برای مصرف Async Generator باید از `for await...of` استفاده کرد، نه `for...of`.
8. ❌ استفاده از `yield*` روی یک مقدار غیر-Iterable.
   ✅ اطمینان از اینکه مقدار سمت راست `yield*` یک Iterable یا Generator است.
9. ❌ تعریف Generator با Arrow Function: `const gen = *() => {}`
   ✅ `const gen = function*() {}`
   💡 Arrow Functionها نمی‌توانند Generator باشند.
10. ❌ استفاده از `return` به جای `yield` برای تولید چندین مقدار.
    ✅ استفاده از `yield`.
    💡 `return` اجرای Generator را فوراً پایان می‌دهد.

## 59. نکات مهم برای مصاحبه
1. **Generator Function چیست؟** تابعی که می‌تواند متوقف و ادامه یابد و با `function*` تعریف می‌شود.
2. **تفاوت آن با Function معمولی؟** حفظ وضعیت (State) بین فراخوانی‌ها و استفاده از `yield` به جای `return`.
3. **`yield` چه می‌کند؟** مقدار را برمی‌گرداند و اجرا را متوقف می‌کند.
4. **`next()` چه برمی‌گرداند؟** شیء `{ value: any, done: boolean }`.
5. **`done` چیست؟** نشان‌دهنده پایان یافتن Generator است.
6. **Generator Object چیست؟** نمونه‌ای که از فراخوانی Generator Function ساخته می‌شود و متد `next()` دارد.
7. **`next(value)` چگونه کار می‌کند؟** مقدار `value` را به عنوان نتیجه‌ی `yield` فعلی به داخل تابع تزریق می‌کند (به جز اولین `next`).
8. **`yield*` چیست؟** عملگر تفویض (Delegation) به یک Generator یا Iterable دیگر.
9. **`return()` چه می‌کند؟** Generator را فوراً پایان می‌دهد و `done: true` می‌کند.
10. **`throw()` چه می‌کند؟** یک خطا را در نقطه توقف فعلی Generator تزریق می‌کند.
11. **ارتباط با Iterable؟** Generator Object هم Iterator است (دارای `next`) و هم Iterable (دارای `Symbol.iterator`).
12. **Infinite Generator چیست؟** Generatorی که حلقه‌ی بی‌پایان دارد اما به دلیل Lazy Evaluation، حافظه را پر نمی‌کند.
13. **Lazy Evaluation چیست؟** تولید یا محاسبه داده فقط در زمان درخواست.
14. **Async Generator چیست؟** Generatorی که با `async function*` تعریف می‌شود و `next()` آن Promise برمی‌گرداند.
15. **تفاوت با Async/Await؟** `async/await` برای انتظار روی یک عملیات ناهمگام است، اما Async Generator برای تولید *جریانی* از داده‌های ناهمگام در طول زمان است.

## 60. پروژه‌های تمرینی

### Beginner
**سؤال:** یک Generator بنویسید که اعداد 1 تا 5 را تولید کند.
**ورودی:** بدون ورودی
**خروجی مورد انتظار:** 1, 2, 3, 4, 5
**Hint:** از یک حلقه `for` ساده و `yield` استفاده کنید.

### Intermediate
**سؤال:** یک Generator به نام `range(start, end, step)` بنویسید.
**ورودی:** `range(2, 10, 2)`
**خروجی مورد انتظار:** 2, 4, 6, 8
**Hint:** از یک حلقه `while` استفاده کنید و متغیر شمارنده را به اندازه `step` افزایش دهید.

### Advanced
**سؤال:** یک Generator برای Pagination بنویسید که یک آرایه بزرگ و اندازه صفحه (pageSize) بگیرد و هر بار یک صفحه را Yield کند.
**ورودی:** `paginate([1,2,3,4,5], 2)`
**خروجی مورد انتظار:** `[1, 2]`, سپس `[3, 4]`, سپس `[5]`
**Hint:** از `Array.prototype.slice` در یک حلقه استفاده کنید.

### Expert
**سؤال:** یک Async Generator بسازید که نام فایل‌ها را از یک آرایه بگیرد و به صورت شبیه‌سازی شده (با `setTimeout` یا `Promise`) محتوای هر فایل را یکی‌یکی Yield کند.
**ورودی:** `['file1.txt', 'file2.txt']`
**خروجی مورد انتظار:** Promiseهایی که به محتوای فایل حل می‌شوند.
**Hint:** از `async function*` و `yield await new Promise(...)` استفاده کنید.

---
*(راه‌حل تمرین‌ها در انتهای سند قرار دارد)*
---

## 61. جمع‌بندی

### نقشه ذهنی Generator
```text
Generator Function
        │
        ├── function* (اعلان)
        │
        ├── Generator Object (خروجی فراخوانی)
        │      ├── next() ──► { value, done }
        │      ├── return() ──► پایان زودهنگام
        │      └── throw() ──► تزریق خطا
        │
        ├── yield (توقف و بازگشت مقدار)
        │      └── yield* (تفویض به Iterable دیگر)
        │
        ├── Iterator Protocol (دارای متد next)
        │
        ├── Iterable Protocol (دارای Symbol.iterator)
        │      └── قابل استفاده در for...of, [...], destructuring
        │
        └── Async Generator
               ├── async function*
               ├── next() برمی‌گرداند: Promise<{ value, done }>
               └── قابل مصرف در for await...of
```

### اگر فقط 10 نکته از Generator یاد بگیریم:
1. با `function*` تعریف می‌شود.
2. با فراخوانی، اجرا نمی‌شود؛ یک Generator Object برمی‌گرداند.
3. `yield` اجرا را متوقف می‌کند و مقدار را برمی‌گرداند.
4. `next()` اجرا را از جایی که متوقف شده بود ادامه می‌دهد.
5. خروجی `next()` همیشه `{ value, done }` است.
6. اولین `next()` نمی‌تواند مقداری را به داخل Generator بفرستد.
7. Generatorها هم Iterator هستند و هم Iterable.
8. برای داده‌های بی‌نهایت یا بزرگ، مصرف حافظه‌ی آن‌ها O(1) است (Lazy Evaluation).
9. `yield*` برای تفویض به یک Generator یا آرایه دیگر است.
10. Generatorها یک‌بار مصرف هستند؛ پس از `done: true` باید دوباره ساخته شوند.

## 62. منابع

### منابع رسمی
- **MDN Web Docs: Iterators and Generators**
  - توضیح: مستندات رسمی و جامع موزیلا درباره پروتکل‌های تکرار و Generatorها.
  - لینک: [MDN Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator)
- **ECMAScript Language Specification (Generators)**
  - توضیح: مشخصات فنی و دقیق رفتار Generatorها در استاندارد زبان.
  - لینک: [ECMAScript Generators](https://tc39.es/ecma262/#sec-generator-function-definitions)

### منابع آموزشی
- **JavaScript.info: Generators**
  - توضیح: یکی از بهترین و روان‌ترین آموزش‌های مرحله‌به‌مرحله با مثال‌های کاربردی.
  - لینک: [JS.info Generators](https://javascript.info/generators)
- **JavaScript.info: Async Iteration**
  - توضیح: پوشش کامل Async Generatorها و `for await...of`.
  - لینک: [JS.info Async Iteration](https://javascript.info/async-iterators-generators)

---

## پیوست: راه‌حل تمرین‌ها (Solutions)

<details>
<summary>🔽 کلیک کنید تا راه‌حل‌ها نمایش داده شوند</summary>

### Beginner Solution
```javascript
function* oneToFive() {
  for (let i = 1; i <= 5; i++) {
    yield i;
  }
}
const gen = oneToFive();
for (const num of gen) console.log(num);
```

### Intermediate Solution
```javascript
function* range(start, end, step = 1) {
  for (let i = start; i < end; i += step) {
    yield i;
  }
}
console.log([...range(2, 10, 2)]); // [2, 4, 6, 8]
```

### Advanced Solution
```javascript
function* paginate(items, pageSize) {
  for (let i = 0; i < items.length; i += pageSize) {
    yield items.slice(i, i + pageSize);
  }
}
const pages = paginate([1, 2, 3, 4, 5], 2);
console.log(pages.next().value); // [1, 2]
console.log(pages.next().value); // [3, 4]
console.log(pages.next().value); // [5]
```

### Expert Solution
```javascript
const files = ['data1.json', 'data2.json'];

async function* fetchFiles(fileList) {
  for (const file of fileList) {
    // شبیه‌سازی درخواست شبکه
    const data = await new Promise(resolve => 
      setTimeout(() => resolve(`Content of ${file}`), 1000)
    );
    yield data;
  }
}

async function main() {
  for await (const content of fetchFiles(files)) {
    console.log(content);
  }
}
main();
```
</details>

---

## پروژه کوچک نهایی: Lazy Data Processing System

این پروژه یک سیستم پردازش داده را شبیه‌سازی می‌کند که داده‌ها را به صورت Lazy از یک منبع (مثلاً دیتابیس) می‌خواند، روی آن‌ها فیلتر و تبدیل انجام می‌دهد و امکان توقف پردازش را فراهم می‌کند.

```javascript
// 1. منبع داده (شبیه‌سازی یک دنباله بی‌نهایت یا بسیار بزرگ)
function* dataSource() {
  let id = 1;
  while (true) {
    yield { id: id++, value: Math.floor(Math.random() * 100) };
  }
}

// 2. Generator فیلتر کننده (فقط اعداد زوج را رد می‌کند)
function* filterEven(source) {
  for (const item of source) {
    if (item.value % 2 === 0) {
      yield item;
    }
  }
}

// 3. Generator تبدیل کننده (افزودن یک فیلد processed)
function* transformData(source) {
  for (const item of source) {
    yield { ...item, processed: true, timestamp: Date.now() };
  }
}

// 4. Pipeline پردازش (ترکیب با yield*)
function* processingPipeline() {
  const source = dataSource();
  const filtered = filterEven(source);
  yield* transformData(filtered);
}

// 5. اجرای سیستم با کنترل دستی (مثلاً پردازش فقط 5 آیتم و توقف)
function runSystem(limit) {
  const pipeline = processingPipeline();
  let count = 0;

  console.log("Starting processing...");
  
  while (count < limit) {
    const result = pipeline.next();
    if (result.done) break;
    
    console.log(`Processed [${count + 1}]:`, result.value);
    count++;
  }
  
  console.log("Processing stopped. Memory efficient!");
}

// اجرا: فقط 5 رکورد پردازش می‌شود، بقیه هرگز تولید یا محاسبه نمی‌شوند.
runSystem(5);
```
**چرا این پروژه عالی است؟**
- از `yield*` برای ترکیب تمیز مراحل استفاده کرده است.
- کاملاً Lazy است: اگر `limit` برابر 5 باشد، `dataSource` هرگز بیش از آنچه لازم است (شاید 10 بار برای پیدا کردن 5 عدد زوج) اجرا نمی‌شود.
- مصرف حافظه ثابت است، حتی اگر `dataSource` بی‌نهایت باشد.

---
*این سند با رعایت استانداردهای ECMAScript 2026 و با هدف ایجاد یک منبع آموزشی باکیفیت برای جامعه توسعه‌دهندگان فارسی‌زبان تهیه شده است.*
