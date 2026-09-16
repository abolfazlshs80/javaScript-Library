
# JavaScript Loops & Array Iteration 🔄

آموزش جامع حلقه‌ها، پیمایش آرایه‌ها، پیمایش Object و متدهای مهم Array در JavaScript — از مقدماتی تا پیشرفته.

> 🎯 **هدف این آموزش:** در پایان این راهنما، شما قادر خواهید بود هر نوع Loop را بفهمید، بنویسید و تفاوت بین متدهای مختلف را تشخیص دهید.

---


### مبانی Loop و Iteration
- [1. مقدمه‌ای بر Iteration](#1-مقدمه‌ای-بر-iteration)
- [2. Classic `for` Loop](#2-classic-for-loop)
- [3. پیمایش Array با `for`](#3-پیمایش-array-با-for)
- [4. Nested Loops](#4-nested-loops-حلقه‌های-تو-در-تو)
- [5. Infinite Loop](#5-infinite-loop-حلقه-بی‌نهایت)
- [6. `for (;;)` Loop بدون پارامتر](#6-for-loop-بدون-پارامتر)
- [7. `while` Loop](#7-while-loop)
- [8. `do...while`](#8-dowhile)
- [9. `break`](#9-break)
- [10. `continue`](#10-continue)
- [11. Labeled Statements و Nested Loop Control](#11-labeled-statements)

### پیمایش پیشرفته
- [12. `for...of`](#12-forof)
- [13. `for...in`](#13-forin)
- [14. تفاوت `for...of` و `for...in`](#14-تفاوت-forof-و-forin)

### Object Iteration
- [15. `Object.keys()`](#15-objectkeys)
- [16. `Object.values()`](#16-objectvalues)
- [17. `Object.entries()`](#17-objectentries)

### Array Methods (Functional Iteration)
- [18. Array Methods و Functional Iteration](#18-array-methods-و-functional-iteration)
- [19. Callback Function](#19-callback-function)
- [20. `map()`](#20-map)
- [21. `filter()`](#21-filter)
- [22. `find()`](#22-find)
- [23. `findIndex()`](#23-findindex)
- [24. `findLast()` و `findLastIndex()`](#24-findlast-و-findlastindex)
- [25. `forEach()`](#25-foreach)
- [26. `some()`](#26-some)
- [27. `every()`](#27-every)
- [28. `reduce()`](#28-reduce)
- [29. کاربردهای `reduce()`](#29-کاربردهای-reduce)
- [30. `reduceRight()`](#30-reduceright)

### متدهای پیشرفته و الگوها
- [31. Method Chaining (زنجیره کردن)](#31-method-chaining-زنجیره-کردن)
- [32. `sort()`](#32-sort)
- [33. Sort کردن Objectها](#33-sort-کردن-objectها)
- [34. Mutation و Array Methods](#34-mutation-و-array-methods)

### مثال کاربردی کامل
- [35. مثال کامل با `persons`](#35-مثال-کامل-با-persons)
- [36. Arrow Function در Array Methods](#36-arrow-function-در-array-methods)
- [37. نکات Performance](#37-نکات-performance)

### مفاهیم پیشرفته
- [38. Iterator و Iterable](#38-iterator-و-iterable)
- [39. Generator و Iteration](#39-generator-و-iteration)

### جمع‌بندی و مرور
- [40. اشتباهات رایج (Common Mistakes)](#40-common-mistakes-اشتباهات-رایج)
- [41. مقایسه نهایی](#41-مقایسه-نهایی)
- [42. چه زمانی از کدام روش استفاده کنیم؟](#42-چه-زمانی-از-کدام-روش-استفاده-کنیم)
- [43. تمرین‌ها](#43-تمرین‌ها)
- [44. جمع‌بندی نهایی](#44-جمع‌بندی-نهایی)
- [45. References / منابع](#45-references--منابع)

---

## 1. مقدمه‌ای بر Iteration

### 🤔 Iteration چیست؟

**Iteration** (تکرار / پیمایش) یعنی یک کار را چند بار پشت سر هم انجام دهیم، معمولاً روی یک سری از داده‌ها.

**مثال روزمره:**
- وقتی شما از روی ۱۰ تا کتاب عبور می‌کنید و اسم هر کتاب را می‌خوانید → این Iteration است.
- وقتی در سبد خرید سایت، قیمت هر محصول را جمع می‌کنید → این Iteration است.

### چرا به Iteration نیاز داریم؟

فرض کنید یک Array از ۱۰۰۰ عدد دارید. نمی‌توانید تک‌تک آن‌ها را دستی در کنسول چاپ کنید. Iteration به شما اجازه می‌دهد این کار را با **یک کد کوتاه** انجام دهید.

### پیمایش یعنی چه؟

**پیمایش (Traversal)** یعنی عبور کردن از روی تمام (یا بخشی از) عناصر یک ساختار داده‌ای مثل Array یا Object.

### Loop چیست؟

**Loop** (حلقه) یک ساختار در زبان برنامه‌نویسی است که به ما اجازه می‌دهد یک قطعه کد را چندین بار اجرا کنیم.

### چه زمانی از Loop استفاده می‌کنیم؟

- برای پردازش همه عناصر یک Array
- برای جستجو در یک مجموعه داده
- برای تکرار یک عملیات N بار
- برای خواندن داده‌ها از API و ذخیره در UI
- برای محاسبات (مثل جمع، میانگین، ماکسیمم و ...)

### تفاوت Iteration و Loop

| Iteration | Loop |
| --------- | ---- |
| **مفهوم** — یعنی «پیمایش روی داده‌ها» | **ساختار کد** — یعنی `for`, `while` و ... |
| **چه کاری** می‌خواهیم انجام دهیم | **چگونه** آن کار را انجام می‌دهیم |

### رابطه Loop با Array و Object

Array و Object دو ساختار داده‌ای رایج هستند. از آنجا که این ساختارها چندین داده در خود نگه می‌دارند، برای کار با آن‌ها به Loop نیاز داریم.

### یک مثال ساده از پیمایش

```javascript
const numbers = [1, 2, 3, 4];

for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}
```

**توضیح خط‌به‌خط:**

| خط | توضیح |
| -- | ----- |
| `const numbers = [1, 2, 3, 4];` | یک آرایه با ۴ عدد تعریف می‌کنیم. |
| `let i = 0;` | یک شمارنده با مقدار اولیه ۰ می‌سازیم (اولین Index در آرایه، ۰ است). |
| `i < numbers.length` | تا زمانی که `i` کوچکتر از طول آرایه (۴) است، ادامه می‌دهیم. |
| `i++` | بعد از هر دور، `i` را یکی زیاد می‌کنیم. |
| `console.log(numbers[i])` | مقدار آرایه در Index فعلی را چاپ می‌کنیم. |

**خروجی:**
```
1
2
3
4
```

---

## 2. Classic `for` Loop

حلقه `for` کلاسیک، پرکاربردترین حلقه در JavaScript است.

### Syntax

```javascript
for (initialization; condition; iterator) {
    // code to execute
}
```

سه بخش اصلی دارد:

### 1) Initialization (مقداردهی اولیه)

```javascript
let i = 0;
```

- فقط یک بار، در ابتدای Loop اجرا می‌شود.
- معمولاً متغیر شمارنده را تعریف می‌کنیم.
- `i` نام رایج است (مخفف **index**).

### 2) Condition (شرط)

```javascript
i < 10;
```

- قبل از هر بار اجرای Loop بررسی می‌شود.
- اگر `true` باشد، کد اجرا می‌شود.
- اگر `false` باشد، Loop متوقف می‌شود.

### 3) Iterator (گام حرکت)

```javascript
i++;
```

- در انتهای هر دور اجرا می‌شود.
- معمولاً شمارنده را افزایش یا کاهش می‌دهد.

### ترتیب اجرا

```
1. Initialization (یک بار)
2. بررسی Condition
   ├── اگر true → اجرای کد داخل Loop
   │               ├── اجرای Iterator
   │               └── بازگشت به مرحله 2
   └── اگر false → خروج از Loop
```

### مثال

```javascript
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

**اجرای مرحله‌به‌مرحله:**

| دور | مقدار `i` | شرط `i < 5` | عمل |
| --- | --------- | ----------- | --- |
| 1   | 0         | `true`      | چاپ `0` |
| 2   | 1         | `true`      | چاپ `1` |
| 3   | 2         | `true`      | چاپ `2` |
| 4   | 3         | `true`      | چاپ `3` |
| 5   | 4         | `true`      | چاپ `4` |
| 6   | 5         | `false`     | خروج |

**خروجی:**
```
0
1
2
3
4
```

> 💡 **نکته مهم:** شمارش در JavaScript از `0` شروع می‌شود، نه از `1`. پس `i < 5` پنج بار اجرا می‌شود.

---

## 3. پیمایش Array با `for`

### مثال

```javascript
const array = ["a", "b", "c", "d"];

for (let i = 0; i < array.length; i++) {
    console.log(i, array[i]);
}
```

**خروجی:**
```
0 'a'
1 'b'
2 'c'
3 'd'
```

### مفاهیم کلیدی

| مفهوم | توضیح |
| ----- | ----- |
| `i` | شمارنده یا Index فعلی |
| `array[i]` | مقدار داخل آرایه در Index `i` |
| **Index** | شماره خانه آرایه (از ۰ شروع می‌شود) |
| **Length** | تعداد کل عناصر آرایه |
| **اولین Index** | `0` |
| **آخرین Index** | `array.length - 1` |

### چرا `i < array.length` و نه `i <= array.length`؟

```javascript
const arr = ["a", "b", "c"];
// arr.length === 3
// Index های موجود: 0, 1, 2
// Index 3 وجود ندارد!
```

| شرط | Index های استفاده‌شده | نتیجه |
| --- | --------------------- | ----- |
| `i < 3` | 0, 1, 2 | ✅ درست |
| `i <= 3` | 0, 1, 2, 3 | ❌ خطا: `undefined` |

اگر از `<=` استفاده کنید، به Index نامعتبر دسترسی پیدا می‌کنید و `undefined` دریافت می‌کنید.

```javascript
const arr = ["a", "b", "c"];
console.log(arr[3]); // undefined
```

> 💡 **نکته مهم:** همیشه از `< array.length` استفاده کنید، نه `<=`.

---

## 4. Nested Loops (حلقه‌های تو در تو)

زمانی که یک Loop داخل Loop دیگری قرار می‌گیرد، **Nested Loop** داریم.

### مثال

```javascript
for (let i = 0; i < 3; i++) {
    for (let j = 0; j < 2; j++) {
        console.log(i, j);
    }
}
```

### مفاهیم

| مفهوم | توضیح |
| ----- | ----- |
| **حلقه بیرونی** | `for (let i = ...)` — دور اصلی |
| **حلقه داخلی** | `for (let j = ...)` — برای هر دور حلقه بیرونی کامل اجرا می‌شود |

### تعداد اجراها

- حلقه بیرونی: ۳ بار (`i` = 0, 1, 2)
- حلقه داخلی: ۲ بار (`j` = 0, 1)
- **کل اجراها:** `3 × 2 = 6`

### خروجی

```
0 0
0 1
1 0
1 1
2 0
2 1
```

**توضیح:**
- در `i=0`، حلقه داخلی با `j=0` و `j=1` اجرا می‌شود.
- در `i=1`، دوباره حلقه داخلی از ابتدا شروع می‌شود.
- در `i=2`، همین‌طور.

### مثال روزمره

فرض کنید ۳ جعبه (حلقه بیرونی) دارید و در هر جعبه ۲ توپ (حلقه داخلی):

```
جعبه 0: توپ 0, توپ 1
جعبه 1: توپ 0, توپ 1
جعبه 2: توپ 0, توپ 1
```

### مثال کاربردی: ساخت جدول ضرب

```javascript
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 3; j++) {
        console.log(`${i} × ${j} = ${i * j}`);
    }
}
```

**خروجی:**
```
1 × 1 = 1
1 × 2 = 2
1 × 3 = 3
2 × 1 = 2
2 × 2 = 4
2 × 3 = 6
3 × 1 = 3
3 × 2 = 6
3 × 3 = 9
```

---

## 5. Infinite Loop (حلقه بی‌نهایت)

**Infinite Loop** حلقه‌ای است که هیچ‌گاه متوقف نمی‌شود چون شرط آن همیشه `true` است.

### ❌ مثال اشتباه

```javascript
let i = 0;

while (i < 10) {
    console.log(i);
    // ❌ فراموش کردیم i را افزایش دهیم!
}
```

**مشکل:** `i` همیشه `0` است، پس `i < 10` همیشه `true` می‌ماند. حلقه بی‌نهایت اجرا می‌شود.

### ✅ نسخه صحیح

```javascript
let i = 0;

while (i < 10) {
    console.log(i);
    i++; // ✅ حالا i در هر دور افزایش می‌یابد
}
```

### خطرات Infinite Loop

- 🔴 **فریز شدن مرورگر** — مرورگر نمی‌تواند به کاربر پاسخ دهد.
- 🔴 **کرش شدن Node.js** — برنامه به مصرف ۱۰۰٪ CPU می‌رسد.
- 🔴 **مصرف بی‌رویه حافظه**
- 🔴 در موارد مدرن، مرورگرها بعد از چند ثانیه، اسکریپت را متوقف می‌کنند و پیام می‌دهند: *"A script on this page may be busy..."*

### راه‌های جلوگیری

1. همیشه مطمئن شوید شمارنده در هر دور تغییر می‌کند.
2. از `break` برای خروج اضطراری استفاده کنید.
3. قبل از اجرا، شرط Loop را با دقت بررسی کنید.

---

## 6. `for (;;)` Loop بدون پارامتر

اگر هر سه بخش Loop را حذف کنید، Loop بی‌نهایت می‌شود:

```javascript
for (;;) {
    // کد
}
```

چرا بی‌نهایت؟ چون **شرطی وجود ندارد** که `false` شود.

### مثال کنترل‌شده با `break`

```javascript
let i = 0;

for (;;) {
    if (i > 10) {
        break; // خروج از Loop
    }

    console.log(i);
    i++;
}
```

**خروجی:**
```
0
1
2
3
4
5
6
7
8
9
10
```

**کاربردها:**
- Loopهایی که شرط پیچیده‌ای دارند.
- Event Loop در برنامه‌های سرور (Node.js).
- بازی‌ها (Game Loop).

> 💡 **نکته مهم:** همیشه در `for(;;)` یک راه خروج (`break`) قرار دهید.

---

## 7. `while` Loop

### Syntax

```javascript
while (condition) {
    // code
}
```

### مثال

```javascript
let i = 0;

while (i < 10) {
    console.log(i);
    i++;
}
```

**خروجی:**
```
0
1
2
3
4
5
6
7
8
9
```

### تفاوت `while` و `for`

| ویژگی | `for` | `while` |
| ----- | ----- | ------- |
| ساختار | همه چیز در یک خط | Initialization و Iterator جدا |
| کاربرد معمول | تعداد دورها مشخص | تعداد دورها نامشخص |
| خوانایی | بهتر برای شمارش ساده | بهتر برای شرط‌های پیچیده |

### چه زمانی `while` استفاده کنیم؟

وقتی نمی‌دانید چند بار باید تکرار شود. مثال:

```javascript
let userInput = "";

while (userInput !== "exit") {
    userInput = prompt("Type 'exit' to stop:");
}
```

---

## 8. `do...while`

### Syntax

```javascript
do {
    // code
} while (condition);
```

### مثال

```javascript
let i = 0;

do {
    console.log(i);
    i++;
} while (i < 5);
```

**خروجی:**
```
0
1
2
3
4
```

### 🔑 تفاوت کلیدی: `while` vs `do...while`

- `while`: **اول شرط را بررسی می‌کند**، بعد کد را اجرا می‌کند.
- `do...while`: **اول کد را اجرا می‌کند**، بعد شرط را بررسی می‌کند.

### مثال مقایسه‌ای

```javascript
let x = 10;

// while
while (x < 5) {
    console.log("while:", x); // هیچ‌گاه اجرا نمی‌شود
}

// do...while
do {
    console.log("do...while:", x); // یک بار اجرا می‌شود
} while (x < 5);
```

**خروجی:**
```
do...while: 10
```

> 💡 **نکته مهم:** `do...while` حداقل **یک بار** اجرا می‌شود، حتی اگر شرط از ابتدا `false` باشد.

### کاربرد رایج

```javascript
let password;

do {
    password = prompt("Enter password:");
} while (password !== "1234");
```

حتماً یک بار از کاربر سوال می‌پرسیم، سپس شرط را چک می‌کنیم.

---

## 9. `break`

`break` حلقه را **بلافاصله** متوقف می‌کند.

### مثال

```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }

    console.log(i);
}
```

**خروجی:**
```
0
1
2
3
4
```

وقتی `i === 5` شد، `break` اجرا می‌شود و حلقه از همان نقطه متوقف می‌شود. حتی `5` چاپ نمی‌شود.

### مثال کاربردی: پیدا کردن اولین عدد خاص

```javascript
const numbers = [2, 4, 6, 7, 8, 10];

for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] % 2 !== 0) {
        console.log("First odd:", numbers[i]);
        break;
    }
}
// Output: First odd: 7
```

به محض یافتن عدد فرد، Loop را متوقف می‌کنیم.

---

## 10. `continue`

`continue` فقط **Iteration فعلی** را رد می‌کند و به Iteration بعدی می‌رود.

### مثال

```javascript
for (let i = 0; i <= 10; i++) {
    if (i % 2 === 0) {
        continue; // این Iteration را رد کن
    }

    console.log(i);
}
```

**خروجی (فقط اعداد فرد):**
```
1
3
5
7
9
```

### تفاوت `break` و `continue`

| `break` | `continue` |
| ------- | ---------- |
| حلقه را **کاملاً** متوقف می‌کند | فقط Iteration فعلی را رد می‌کند |
| دیگر هیچ Iteration اجرا نمی‌شود | Iteration بعدی اجرا می‌شود |
| خروج کامل از Loop | پرش به دور بعدی Loop |

### نمودار ساده

```
Loop:
┌── دور 1: continue → رد می‌شود
├── دور 2: اجرا
├── دور 3: break → Loop متوقف می‌شود
└── دور 4: (اجرا نمی‌شود)
```

---

## 11. Labeled Statements

**Label** یک اسم روی Loop است که می‌توانیم با `break` یا `continue` از روی آن‌ها کنترل بیشتری داشته باشیم.

### Syntax

```javascript
outerLoop: for (...) {
    for (...) {
        break outerLoop;
    }
}
```

### مثال

```javascript
outer: for (let i = 0; i < 3; i++) {
    for (let j = 0; j < 3; j++) {
        if (i === 1 && j === 1) {
            break outer; // حلقه بیرونی را می‌شکند
        }
        console.log(i, j);
    }
}
```

**خروجی:**
```
0 0
0 1
0 2
1 0
```

وقتی `i=1, j=1` شد، هر دو حلقه متوقف می‌شوند.

### چه زمانی استفاده کنیم؟

- در Nested Loopهای پیچیده که می‌خواهیم از حلقه بیرونی خارج شویم.
- در الگوریتم‌هایی که نیاز به کنترل دقیق دارند (مثل ماتریس).

### چرا نباید زیاد استفاده کنیم؟

- خوانایی کد را کاهش می‌دهد.
- کد را شبیه `goto` در زبان‌های قدیمی می‌کند (که عموماً بدشمار می‌شود).
- معمولاً می‌توان با Extract کردن به تابع، جایگزین بهتری یافت.

```javascript
// جایگزین بهتر:
function findItem(matrix, target) {
    for (let i = 0; i < matrix.length; i++) {
        for (let j = 0; j < matrix[i].length; j++) {
            if (matrix[i][j] === target) return { i, j };
        }
    }
    return null;
}
```

---

## 12. `for...of`

حلقه `for...of` برای پیمایش **Iterableها** طراحی شده است.

### Syntax

```javascript
for (const item of iterable) {
    // code
}
```

### مثال ساده

```javascript
const numbers = [1, 2, 3, 4, 5];

for (const item of numbers) {
    console.log(item);
}
```

**خروجی:**
```
1
2
3
4
5
```

### ویژگی‌ها

- ✅ **مقدار عنصر** را مستقیماً می‌دهد (نه Index).
- ✅ برای **Iterable**ها کار می‌کند.
- ❌ برای Objectهای معمولی (Plain Object) کار نمی‌کند.

### Iterable چیست؟

Iterable هر چیزی است که `Symbol.iterator` دارد. شامل:
- Array
- String
- Set
- Map
- NodeList
- Generator

### مثال با String

```javascript
const name = "Ali";

for (const char of name) {
    console.log(char);
}
```

**خروجی:**
```
A
l
i
```

### مثال با Set

```javascript
const uniqueNumbers = new Set([1, 2, 2, 3, 3, 3]);

for (const num of uniqueNumbers) {
    console.log(num);
}
```

**خروجی:**
```
1
2
3
```

### مثال با Map

```javascript
const user = new Map();
user.set("name", "Ali");
user.set("age", 20);

for (const [key, value] of user) {
    console.log(key, value);
}
```

**خروجی:**
```
name Ali
age 20
```

> 💡 **نکته مهم:** وقتی فقط به **مقدار** نیاز دارید، از `for...of` استفاده کنید. نیازی به `array[i]` نیست.

---

## 13. `for...in`

حلقه `for...in` برای پیمایش **Propertyهای یک Object** طراحی شده است.

### Syntax

```javascript
for (const key in object) {
    // code
}
```

### مثال

```javascript
const person = {
    name: "Ali",
    age: 20
};

for (const key in person) {
    console.log(key);
}
```

**خروجی:**
```
name
age
```

### دسترسی به مقدار

```javascript
for (const key in person) {
    console.log(key, person[key]);
}
```

**خروجی:**
```
name Ali
age 20
```

### کاربرد

`for...in` معمولاً برای پیمایش Propertyهای **Object** استفاده می‌شود.

> ⚠️ **هشدار:** `for...in` Propertyهای ارثی‌برده‌شده از Prototype Chain را هم پیمایش می‌کند. برای فیلتر کردن، از `hasOwnProperty` استفاده کنید:

```javascript
for (const key in person) {
    if (Object.hasOwn(person, key)) {
        console.log(key, person[key]);
    }
}
```

---

## 14. تفاوت `for...of` و `for...in`

### مثال مقایسه‌ای

```javascript
const numbers = [10, 20, 30];

// for...of
for (const item of numbers) {
    console.log("of:", item);
}

// for...in
for (const item in numbers) {
    console.log("in:", item);
}
```

**خروجی:**
```
of: 10
of: 20
of: 30
in: 0
in: 1
in: 2
```

### جدول مقایسه

| ویژگی | `for...of` | `for...in` |
| ----- | ---------- | ---------- |
| برمی‌گرداند | **مقدار (Value)** | **کلید (Key/Index)** |
| کاربرد | Iterableها (Array, String, Set, Map) | Objectهای Plain |
| Prototype Chain | ❌ پیمایش نمی‌کند | ✅ پیمایش می‌کند |
| ترتیب | تضمین‌شده (بر اساس Iterator) | ⚠️ تضمین نشده برای Propertyهای عددی در برخی نسخه‌ها |

### چرا `for...in` برای Array مناسب نیست؟

```javascript
const arr = [10, 20, 30];
arr.custom = "hello"; // Property اضافه می‌کنیم

for (const i in arr) {
    console.log(i); // 0, 1, 2, custom !!!
}
```

`for...in` Propertyهای غیر Indexی را هم نشان می‌دهد، پس برای Array **خطرناک** است. همیشه برای Array از `for...of` یا متدهای Array استفاده کنید.

---

## 15. `Object.keys()`

`Object.keys()` یک آرایه از **نام Propertyها**ی Object را برمی‌گرداند.

### Syntax

```javascript
Object.keys(object);
```

### مثال

```javascript
const person = {
    name: "Ali",
    age: 20,
    city: "Sari"
};

const keys = Object.keys(person);
console.log(keys);
```

**خروجی:**
```
['name', 'age', 'city']
```

### کاربرد: پیمایش با متدهای Array

```javascript
Object.keys(person).forEach((key) => {
    console.log(key, person[key]);
});
```

**خروجی:**
```
name Ali
age 20
city Sari
```

---

## 16. `Object.values()`

`Object.values()` یک آرایه از **مقدارهای Propertyها** را برمی‌گرداند.

### مثال

```javascript
const person = {
    name: "Ali",
    age: 20,
    city: "Sari"
};

const values = Object.values(person);
console.log(values);
```

**خروجی:**
```
['Ali', 20, 'Sari']
```

### کاربرد

```javascript
const prices = { apple: 100, banana: 50, orange: 80 };
const total = Object.values(prices).reduce((sum, price) => sum + price, 0);
console.log(total); // 230
```

---

## 17. `Object.entries()`

`Object.entries()` یک آرایه از **جفت‌های `[key, value]`** را برمی‌گرداند.

### مثال

```javascript
const person = {
    name: "Ali",
    age: 20
};

const entries = Object.entries(person);
console.log(entries);
```

**خروجی:**
```
[
  ['name', 'Ali'],
  ['age', 20]
]
```

### پیمایش با Destructuring

```javascript
for (const [key, value] of Object.entries(person)) {
    console.log(key, value);
}
```

**خروجی:**
```
name Ali
age 20
```

### Destructuring چیست؟

در `[key, value]` ما **Destructuring** انجام می‌دهیم، یعنی آرایه `[key, value]` را به دو متغیر جدا تبدیل می‌کنیم.

```javascript
const entry = ['name', 'Ali'];
const [key, value] = entry;
console.log(key);   // 'name'
console.log(value); // 'Ali'
```

### تبدیل Object به Map

```javascript
const map = new Map(Object.entries(person));
console.log(map.get("name")); // 'Ali'
```

### تبدیل Map به Object

```javascript
const obj = Object.fromEntries(map);
console.log(obj); // { name: 'Ali', age: 20 }
```

---

## 18. Array Methods و Functional Iteration

بعد از حلقه‌های کلاسیک، وارد دنیای **Array Methods** می‌شویم. این متدها روشی **مدرن‌تر، خوانا‌تر و قابل اعتمادتر** برای کار با آرایه‌ها ارائه می‌دهند.

### چرا Array Methodها مهم هستند؟

- ✅ **Readability** (خوانایی) بهتر
- ✅ **Immutability** (تغییر نکردن داده اصلی) در بسیاری از متدها
- ✅ **Composable** (قابل ترکیب) — می‌توان چند متد را زنجیره کرد.
- ✅ کمتر در معرض خطای انسانی (مثل فراموش کردن `i++`)
- ✅ سازگار با Functional Programming

### تفاوت Loop کلاسیک با Array Methods

| ویژگی | Loop کلاسیک | Array Methods |
| ----- | ----------- | ------------- |
| Syntax | پیچیده‌تر | ساده‌تر |
| کنترل Index | دستی | اتوماتیک |
| Immutability | معمولا mutable | معمولا immutable |
| Composability | سخت | آسان |

### Callback Function چیست؟

**Callback** یک تابع است که به عنوان آرگومان به تابع دیگری داده می‌شود. در متدهای Array، Callback معمولاً برای هر عنصر اجرا می‌شود.

```javascript
array.method(function callback(item, index, array) {
    // code
});
```

### Higher-Order Function چیست؟

**Higher-Order Function** تابعی است که:
1. یک تابع را به عنوان آرگومان می‌پذیرد، یا
2. یک تابع را برمی‌گرداند.

همه متدهای Array (مثل `map`, `filter`, `reduce`) **Higher-Order Functions** هستند.

### مثال

```javascript
const numbers = [1, 2, 3, 4];

const result = numbers.map((item) => {
    return item * 2;
});

console.log(result); // [2, 4, 6, 8]
```

---

## 19. Callback Function

قبل از ورود به متدهای Array، باید Callback را خوب بفهمیم.

### مثال ساده

```javascript
function processNumber(number, callback) {
    callback(number);
}

processNumber(10, (number) => {
    console.log(number);
});
```

**خروجی:**
```
10
```

### توضیح خط‌به‌خط

1. `processNumber` یک تابع است که دو پارامتر می‌گیرد: یک عدد و یک تابع (callback).
2. درون تابع، `callback(number)` را فراخوانی می‌کنیم.
3. وقتی `processNumber(10, ...)` را صدا می‌زنیم، تابع دوم (Arrow Function) را به عنوان callback ارسال می‌کنیم.
4. `callback(10)` یعنی Arrow Function را با `number=10` اجرا می‌کنیم.

### مثال پیشرفته‌تر

```javascript
function greet(name, callback) {
    console.log("Hi " + name);
    callback();
}

function callMe() {
    console.log("I am callback function");
}

greet("Ali", callMe);
```

**خروجی:**
```
Hi Ali
I am callback function
```

---

## 20. `map()`

`map()` روی هر عنصر آرایه یک تابع را اجرا می‌کند و یک **آرایه جدید** با نتایج برمی‌گرداند.

### Syntax

```javascript
array.map(callback(item, index, array));
```

### مثال

```javascript
const numbers = [1, 2, 3, 4];

const result = numbers.map((item) => {
    return item * 2;
});

console.log(result);
```

**خروجی:**
```
[2, 4, 6, 8]
```

### ویژگی‌ها

| ویژگی | توضیح |
| ----- | ----- |
| آرایه اصلی تغییر می‌کند؟ | ❌ خیر (Immutable) |
| خروجی چیست؟ | یک **آرایه جدید** |
| طول آرایه خروجی؟ | همیشه برابر با طول آرایه ورودی |
| کاربرد | **تبدیل** عناصر |

### پارامترهای Callback

```javascript
array.map((item, index, array) => { ... });
```

| پارامتر | توضیح |
| ------- | ----- |
| `item` | مقدار عنصر فعلی |
| `index` | Index عنصر فعلی (اختیاری) |
| `array` | خود آرایه (اختیاری، کم استفاده می‌شود) |

### مثال با Index

```javascript
const names = ["Ali", "Reza", "Sara"];

const result = names.map((name, index) => {
    return `${index + 1}. ${name}`;
});

console.log(result);
```

**خروجی:**
```
['1. Ali', '2. Reza', '3. Sara']
```

### مثال واقعی: استخراج Property از Objectها

```javascript
const users = [
    { id: 1, name: "Ali", age: 20 },
    { id: 2, name: "Sara", age: 25 },
    { id: 3, name: "Reza", age: 30 }
];

const names = users.map((user) => user.name);
console.log(names); // ['Ali', 'Sara', 'Reza']
```

> 💡 **نکته مهم:** وقتی `return` را فراموش کنید، `undefined` دریافت می‌کنید!

---

## 21. `filter()`

`filter()` آرایه‌ای جدید شامل **عناصری که شرط را دارند** برمی‌گرداند.

### Syntax

```javascript
array.filter(callback(item, index, array));
```

### مثال

```javascript
const numbers = [1, 2, 3, 4, 5];

const result = numbers.filter((item) => {
    return item > 3;
});

console.log(result);
```

**خروجی:**
```
[4, 5]
```

### شرط `true` و `false`

- اگر callback برای یک عنصر `true` برگرداند → عنصر **در آرایه خروجی** قرار می‌گیرد.
- اگر `false` برگرداند → عنصر **حذف می‌شود**.

### مثال با Object

```javascript
const students = [
    { name: "Ali", age: 20, isStudent: false },
    { name: "Babak", age: 17, isStudent: true }
];

const result = students.filter((item) => {
    return item.isStudent;
});

console.log(result);
```

**خروجی:**
```
[{ name: "Babak", age: 17, isStudent: true }]
```

### مثال واقعی: فیلتر محصولات موجود

```javascript
const products = [
    { name: "Laptop", price: 1000, inStock: true },
    { name: "Phone", price: 500, inStock: false },
    { name: "Tablet", price: 300, inStock: true }
];

const available = products.filter((p) => p.inStock);
console.log(available);
```

---

## 22. `find()`

`find()` **اولین عنصری** که شرط را دارد برمی‌گرداند (نه یک آرایه).

### Syntax

```javascript
array.find(callback(item, index, array));
```

### مثال

```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Kaveh", age: 25 },
    { name: "Kaveh", age: 30 } // Kaveh دوم
];

const result = persons.find((item) => {
    return item.name === "Kaveh";
});

console.log(result);
```

**خروجی:**
```
{ name: "Kaveh", age: 25 }
```

> فقط اولین Kaveh را برمی‌گرداند، نه هر دو را.

### اگر چیزی پیدا نشود؟

```javascript
const result = persons.find((item) => item.name === "Nonexistent");
console.log(result); // undefined
```

### تفاوت `find()` و `filter()`

| `find()` | `filter()` |
| -------- | ---------- |
| **اولین** عنصر مطابق | **همه** عناصر مطابق |
| یک عنصر یا `undefined` برمی‌گرداند | یک **آرایه** برمی‌گرداند |
| بعد از یافتن، Loop را متوقف می‌کند | تمام آرایه را پیمایش می‌کند |

---

## 23. `findIndex()`

`findIndex()` **Index اولین عنصری** که شرط را دارد برمی‌گرداند.

### مثال

```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Kaveh", age: 25 },
    { name: "Sara", age: 30 }
];

const result = persons.findIndex((item) => {
    return item.name === "Kaveh";
});

console.log(result);
```

**خروجی:**
```
1
```

### تفاوت با `find()`

| `find()` | `findIndex()` |
| -------- | ------------- |
| خود **عنصر** را برمی‌گرداند | **Index** عنصر را برمی‌گرداند |
| اگر نیافت: `undefined` | اگر نیافت: `-1` |

### کاربرد

```javascript
const index = users.findIndex((u) => u.id === 123);
if (index !== -1) {
    users.splice(index, 1); // حذف کاربر
}
```

---

## 24. `findLast()` و `findLastIndex()`

این متدها در ES2023 اضافه شدند و **از انتهای آرایه** جستجو می‌کنند.

### مثال

```javascript
const persons = [
    { name: "Ali", age: 18 },
    { name: "Sara", age: 25 },
    { name: "Reza", age: 42 }
];

const result = persons.findLast((item) => {
    return item.age > 20;
});

console.log(result);
```

**خروجی:**
```
{ name: "Reza", age: 42 }
```

### `findLastIndex()`

```javascript
const result = persons.findLastIndex((item) => {
    return item.age > 20;
});

console.log(result); // 2 (Index Reza)
```

### جدول مقایسه

| متد | جهت جستجو | خروجی |
| --- | --------- | ----- |
| `find()` | از ابتدا | اولین عنصر |
| `findIndex()` | از ابتدا | Index اولین عنصر |
| `findLast()` | از انتها | آخرین عنصر |
| `findLastIndex()` | از انتها | Index آخرین عنصر |

---

## 25. `forEach()`

`forEach()` یک عملیات را روی هر عنصر اجرا می‌کند، اما **چیزی برنمی‌گرداند**.

### Syntax

```javascript
array.forEach(callback(item, index, array));
```

### مثال

```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Sara", age: 25 }
];

persons.forEach((item) => {
    console.log(item.name);
});
```

**خروجی:**
```
Ali
Sara
```

### تفاوت `forEach()` و `map()`

| `forEach()` | `map()` |
| ----------- | ------- |
| `undefined` برمی‌گرداند | آرایه جدید برمی‌گرداند |
| فقط برای **اجرای عملیات** | برای **تبدیل** داده‌ها |
| مناسب برای Side Effects (مثل `console.log`) | مناسب برای تبدیل داده |
| قابلیت `break`/`return` ندارد | با `return` مقدار برمی‌گرداند |

### چرا نمی‌توان انتظار Array جدید داشت؟

```javascript
const result = persons.forEach((person) => {
    return person.name;
});

console.log(result); // undefined !!!
```

`forEach` همیشه `undefined` برمی‌گرداند. اگر می‌خواهید آرایه جدید بگیرید، از `map` استفاده کنید.

### Side Effect چیست؟

هر کاری که خارج از تابع اتفاق بیفتد. مثل:
- چاپ در کنسول
- تغییر DOM
- تغییر یک متغیر بیرونی
- فراخوانی API

---

## 26. `some()`

`some()` بررسی می‌کند که **حداقل یک عنصر** شرط را دارد یا نه.

### Syntax

```javascript
array.some(callback(item, index, array));
```

### مثال

```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Sara", age: 25 },
    { name: "Reza", age: 42 }
];

const result = persons.some((item) => {
    return item.age > 40;
});

console.log(result); // true
```

چون **Reza** سن بالای ۴۰ دارد، نتیجه `true` است.

### سوالی که می‌پرسد

> آیا حداقل یک عنصر در آرایه شرط را برآورده می‌کند؟

### مثال واقعی: اعتبارسنجی فرم

```javascript
const fields = [
    { name: "email", value: "" },
    { name: "password", value: "secret" }
];

const hasEmpty = fields.some((field) => field.value === "");
console.log(hasEmpty); // true
```

---

## 27. `every()`

`every()` بررسی می‌کند که **همه عناصر** شرط را دارند یا نه.

### مثال

```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Sara", age: 25 },
    { name: "Reza", age: 42 }
];

const result = persons.every((item) => {
    return item.age > 40;
});

console.log(result); // false
```

فقط Reza بالای ۴۰ است، پس نتیجه `false` است.

### سوالی که می‌پرسد

> آیا **همه** عناصر در آرایه شرط را برآورده می‌کنند؟

### تفاوت `some()` و `every()`

| `some()` | `every()` |
| -------- | --------- |
| حداقل یکی | همه |
| "آیا وجود دارد؟" | "آیا همه هست؟" |
| OR منطقی | AND منطقی |

### مثال مقایسه‌ای

```javascript
const ages = [20, 25, 42];

console.log(ages.some(age => age > 40));  // true (42 هست)
console.log(ages.every(age => age > 40)); // false (همه نیست)

console.log(ages.every(age => age > 10)); // true (همه بالای 10)
```

### مثال واقعی: بررسی مجوز همه کاربرها

```javascript
const users = [
    { name: "Ali", role: "admin" },
    { name: "Sara", role: "admin" }
];

const allAdmins = users.every((u) => u.role === "admin");
console.log(allAdmins); // true
```

---

## 28. `reduce()`

`reduce()` **آرایه را به یک مقدار واحد** تبدیل می‌کند. این قدرتمندترین متد Array است.

### Syntax

```javascript
array.reduce(callback(accumulator, currentValue, index, array), initialValue);
```

### مثال

```javascript
const numbers = [1, 2, 3, 4];

const result = numbers.reduce((total, currentItem) => {
    return total + currentItem;
}, 0);

console.log(result);
```

**خروجی:**
```
10
```

### مفاهیم کلیدی

| مفهوم | توضیح |
| ----- | ----- |
| **accumulator** | مقداری که تا الان جمع شده (در دور بعدی استفاده می‌شود) |
| **currentValue** | عنصر فعلی آرایه |
| **initialValue** | مقدار اولیه accumulator |

### Reduce چگونه کار می‌کند؟ (مرحله‌به‌مرحله)

| دور | accumulator | currentValue | return |
| --- | ----------- | ------------ | ------ |
| 1   | 0 (initial) | 1            | 0 + 1 = 1 |
| 2   | 1           | 2            | 1 + 2 = 3 |
| 3   | 3           | 3            | 3 + 3 = 6 |
| 4   | 6           | 4            | 6 + 4 = 10 |

**نتیجه نهایی:** `10`

### جدول ساده‌تر

```
ابتدا: acc = 0
+ 1 → acc = 1
+ 2 → acc = 3
+ 3 → acc = 6
+ 4 → acc = 10
```

### اهمیت `initialValue`

اگر `initialValue` را حذف کنید، اولین عنصر آرایه به عنوان `accumulator` استفاده می‌شود:

```javascript
const numbers = [1, 2, 3, 4];
const result = numbers.reduce((acc, curr) => acc + curr);
// مرحله 1: acc=1, curr=2 → return 3
// مرحله 2: acc=3, curr=3 → return 6
// مرحله 3: acc=6, curr=4 → return 10
```

### مثال: ضرب عناصر

```javascript
const numbers = [1, 2, 3, 4];
const product = numbers.reduce((acc, curr) => acc * curr, 1);
console.log(product); // 24
```

> 💡 **نکته مهم:** همیشه `initialValue` را مشخص کنید تا باگ‌های ناخواسته ایجاد نشود.

---

## 29. کاربردهای `reduce()`

### 1) جمع عناصر

```javascript
const numbers = [1, 2, 3, 4];
const total = numbers.reduce((sum, item) => sum + item, 0);
console.log(total); // 10
```

### 2) شمارش (Counting)

```javascript
const fruits = ["apple", "banana", "apple", "orange", "banana", "apple"];

const counts = fruits.reduce((acc, fruit) => {
    acc[fruit] = (acc[fruit] || 0) + 1;
    return acc;
}, {});

console.log(counts);
```

**خروجی:**
```
{ apple: 3, banana: 2, orange: 1 }
```

### 3) ساخت Object از Array

```javascript
const entries = [["name", "Ali"], ["age", 20]];

const obj = entries.reduce((acc, [key, value]) => {
    acc[key] = value;
    return acc;
}, {});

console.log(obj); // { name: 'Ali', age: 20 }
```

### 4) Grouping (گروه‌بندی)

```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Sara", age: 35 },
    { name: "Reza", age: 42 }
];

const grouped = persons.reduce((acc, person) => {
    const group = person.age >= 30 ? "senior" : "junior";
    if (!acc[group]) acc[group] = [];
    acc[group].push(person);
    return acc;
}, {});

console.log(grouped);
```

**خروجی:**
```
{
  junior: [{ name: "Ali", age: 20 }],
  senior: [
    { name: "Sara", age: 35 },
    { name: "Reza", age: 42 }
  ]
}
```

### 5) Flat کردن آرایه تو در تو

```javascript
const nested = [[1, 2], [3, 4], [5, 6]];

const flat = nested.reduce((acc, arr) => acc.concat(arr), []);
console.log(flat); // [1, 2, 3, 4, 5, 6]
```

### 6) محاسبه مجموع قیمت محصولات

```javascript
const cart = [
    { name: "Book", price: 20 },
    { name: "Pen", price: 5 },
    { name: "Bag", price: 35 }
];

const total = cart.reduce((sum, item) => sum + item.price, 0);
console.log(total); // 60
```

### 7) پیدا کردن Max/Min

```javascript
const numbers = [3, 7, 2, 9, 1, 5];

const max = numbers.reduce((a, b) => (a > b ? a : b));
console.log(max); // 9

const min = numbers.reduce((a, b) => (a < b ? a : b));
console.log(min); // 1
```

---

## 30. `reduceRight()`

`reduceRight()` دقیقاً مثل `reduce()` است، اما **از راست به چپ** (از انتها به ابتدا) کار می‌کند.

### مثال

```javascript
const chars = ["a", "l", "a"];

const result = chars.reduceRight((acc, curr) => {
    return acc + curr;
}, "hello ");

console.log(result);
```

**خروجی:**
```
hello ala
```

### مقایسه با `reduce()`

```javascript
const chars = ["a", "b", "c"];

const r1 = chars.reduce((acc, curr) => acc + curr, "");
console.log(r1); // "abc"

const r2 = chars.reduceRight((acc, curr) => acc + curr, "");
console.log(r2); // "cba"
```

### کاربرد: معکوس کردن آرایه

```javascript
const reversed = [1, 2, 3].reduceRight((acc, curr) => {
    acc.push(curr);
    return acc;
}, []);
console.log(reversed); // [3, 2, 1]
```

### جدول مقایسه

| متد | جهت | کاربرد |
| --- | ----- | ------ |
| `reduce()` | چپ به راست | تجمیع عمومی |
| `reduceRight()` | راست به چپ | معکوس کردن، Right-associative ops |

---

## 31. Method Chaining (زنجیره کردن)

چون اکثر متدهای Array **آرایه جدید برمی‌گردانند**، می‌توانیم آن‌ها را **زنجیره** کنیم.

### مثال

```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Sara", age: 16 },
    { name: "Reza", age: 30 }
];

const result = persons
    .filter((person) => person.age >= 18)
    .map((person) => person.name);

console.log(result);
```

**خروجی:**
```
['Ali', 'Reza']
```

### توضیح مرحله‌به‌مرحله

| مرحله | عمل | خروجی |
| ----- | --- | ----- |
| 1 | `persons` (اصلی) | `[{Ali, 20}, {Sara, 16}, {Reza, 30}]` |
| 2 | `.filter()` | `[{Ali, 20}, {Reza, 30}]` |
| 3 | `.map()` | `['Ali', 'Reza']` |

### مثال پیچیده‌تر

```javascript
const result = persons
    .filter((person) => person.age >= 18)
    .map((person) => ({ ...person, isAdult: true }))
    .sort((a, b) => a.age - b.age);
```

### نکات مهم

- هر مرحله آرایه جدید می‌سازد.
- ترتیب متدها مهم است.
- متدهایی که آرایه برنمی‌گردانند (مثل `forEach`, `some`, `every`) نمی‌توانند در وسط زنجیره باشند.

### مثال اشتباه

```javascript
persons
    .forEach((p) => console.log(p)) // undefined برمی‌گرداند
    .map((p) => p.name); // ❌ TypeError
```

---

## 32. `sort()`

`sort()` عناصر آرایه را **در محل (in-place)** مرتب می‌کند.

### Syntax

```javascript
array.sort(compareFunction);
```

### مثال پیش‌فرض

```javascript
const numbers = [10, 2, 30, 4];

numbers.sort();

console.log(numbers);
```

**خروجی:**
```
[10, 2, 30, 4]  // ❌ اشتباه!
```

### ❗ چرا نتیجه عجیب است؟

`sort()` به صورت پیش‌فرض عناصر را به **String** تبدیل می‌کند و بر اساس **Unicode** مرتب می‌کند.

```
"10" < "2"  (چون '1' < '2')
```

### ✅ روش صحیح برای اعداد

```javascript
const numbers = [10, 2, 30, 4];

numbers.sort((a, b) => {
    return a - b;
});

console.log(numbers);
```

**خروجی:**
```
[2, 4, 10, 30]
```

### مرتب‌سازی نزولی

```javascript
numbers.sort((a, b) => {
    return b - a;
});

console.log(numbers);
```

**خروجی:**
```
[30, 10, 4, 2]
```

### منطق `compareFunction`

تابع مقایسه باید یک عدد برگرداند:

| مقدار برگشتی | معنی |
| ------------ | ---- |
| **منفی** | `a` قبل از `b` |
| **صفر** | ترتیب بدون تغییر |
| **مثبت** | `b` قبل از `a` |

### مرتب‌سازی String

```javascript
const names = ["Charlie", "Ali", "Bob"];
names.sort();
console.log(names); // ['Ali', 'Bob', 'Charlie']
```

---

## 33. Sort کردن Objectها

```javascript
const persons = [
    { name: "Ali", age: 20, isStudent: false },
    { name: "Siavash", age: 35, isStudent: false },
    { name: "Kaveh", age: 42, isStudent: false },
    { name: "Babak", age: 17, isStudent: true },
    { name: "Maziar", age: 19, isStudent: false },
    { name: "Rostam", age: 25, isStudent: true }
];
```

### مرتب‌سازی بر اساس سن (صعودی)

```javascript
const result = persons.sort((a, b) => {
    return a.age - b.age;
});

console.log(result);
```

**خروجی:**
```
[
  { name: "Babak", age: 17, ... },
  { name: "Maziar", age: 19, ... },
  { name: "Ali", age: 20, ... },
  { name: "Rostam", age: 25, ... },
  { name: "Siavash", age: 35, ... },
  { name: "Kaveh", age: 42, ... }
]
```

### مرتب‌سازی نزولی

```javascript
persons.sort((a, b) => b.age - a.age);
```

### مرتب‌سازی بر اساس String

```javascript
persons.sort((a, b) => a.name.localeCompare(b.name));
```

`localeCompare` برای مقایسه Stringها در زبان‌های مختلف مناسب است.

### مرتب‌سازی چند سطحی

```javascript
persons.sort((a, b) => {
    if (a.age !== b.age) return a.age - b.age;
    return a.name.localeCompare(b.name);
});
```

---

## 34. Mutation و Array Methods

**Mutation** یعنی تغییر آرایه اصلی. بعضی متدها Array را تغییر می‌دهند، بعضی آرایه جدید می‌سازند.

### جدول Mutation

| متد | Array جدید؟ | Mutable؟ |
| --- | ----------- | -------- |
| `map` | ✅ بله | ❌ خیر |
| `filter` | ✅ بله | ❌ خیر |
| `find` | - | ❌ خیر |
| `findIndex` | - | ❌ خیر |
| `forEach` | - | ⚠️ بستگی به callback |
| `some` | - | ❌ خیر |
| `every` | - | ❌ خیر |
| `reduce` | مقدار جدید | ❌ خیر (اگر درست استفاده شود) |
| **`sort`** | همان آرایه | **✅ بله، Mutable است!** |

### مثال `sort()` — Mutable

```javascript
const arr = [3, 1, 2];
const sorted = arr.sort();

console.log(arr);    // [1, 2, 3] — تغییر کرده!
console.log(sorted); // [1, 2, 3] — همان آرایه

console.log(arr === sorted); // true
```

### راه‌حل: ساخت کپی قبل از `sort()`

```javascript
const arr = [3, 1, 2];

// روش 1: spread
const sorted1 = [...arr].sort((a, b) => a - b);

// روش 2: slice
const sorted2 = arr.slice().sort((a, b) => a - b);

// روش 3: toSorted() (ES2023 — غیر mutable)
const sorted3 = arr.toSorted((a, b) => a - b);

console.log(arr); // [3, 1, 2] — تغییر نکرده!
```

### متدهای Mutable دیگر

| متد | عمل |
| --- | --- |
| `push()` | اضافه به انتها |
| `pop()` | حذف از انتها |
| `shift()` | حذف از ابتدا |
| `unshift()` | اضافه به ابتدا |
| `splice()` | حذف/اضافه در موقعیت خاص |
| `reverse()` | معکوس کردن |
| `sort()` | مرتب‌سازی |

### متدهای Immutable (ES2023 به بعد)

| متد جدید | جایگزین |
| -------- | ------- |
| `toSorted()` | `sort()` |
| `toReversed()` | `reverse()` |
| `toSpliced()` | `splice()` |
| `with()` | `arr[i] = x` |

---

## 35. مثال کامل با `persons`

بیایید همه متدها را روی یک آرایه واقعی ببینیم.

```javascript
const persons = [
    { name: "Ali", age: 20, isStudent: false },
    { name: "Siavash", age: 35, isStudent: false },
    { name: "Kaveh", age: 42, isStudent: false },
    { name: "Babak", age: 17, isStudent: true },
    { name: "Maziar", age: 19, isStudent: false },
    { name: "Rostam", age: 25, isStudent: true }
];
```

### 1) پیدا کردن افراد بالای 40 سال (filter)

```javascript
const over40 = persons.filter((p) => p.age > 40);
console.log(over40);
// [{ name: "Kaveh", age: 42, isStudent: false }]
```

### 2) پیدا کردن Kaveh (find)

```javascript
const kaveh = persons.find((p) => p.name === "Kaveh");
console.log(kaveh);
// { name: "Kaveh", age: 42, isStudent: false }
```

### 3) پیدا کردن Index مربوط به Kaveh (findIndex)

```javascript
const index = persons.findIndex((p) => p.name === "Kaveh");
console.log(index); // 2
```

### 4) پیدا کردن آخرین فرد با شرط (findLast)

```javascript
const lastStudent = persons.findLast((p) => p.isStudent);
console.log(lastStudent);
// { name: "Rostam", age: 25, isStudent: true }
```

### 5) ایجاد Property جدید (map)

```javascript
const withElderly = persons.map((item) => {
    return {
        ...item,
        elderly: item.age >= 60
    };
});

console.log(withElderly[2]);
// { name: "Kaveh", age: 42, isStudent: false, elderly: false }
```

### 6) بررسی حداقل یک دانش‌آموز (some)

```javascript
const hasStudent = persons.some((p) => p.isStudent);
console.log(hasStudent); // true
```

### 7) بررسی اینکه همه بالای 40 سال هستند (every)

```javascript
const allOver40 = persons.every((p) => p.age > 40);
console.log(allOver40); // false
```

### 8) محاسبه مجموع سن (reduce)

```javascript
const totalAge = persons.reduce((sum, p) => sum + p.age, 0);
console.log(totalAge); // 158
```

### 9) مرتب‌سازی بر اساس سن (sort)

```javascript
const sorted = [...persons].sort((a, b) => a.age - b.age);
console.log(sorted.map((p) => p.name));
// ['Babak', 'Maziar', 'Ali', 'Rostam', 'Siavash', 'Kaveh']
```

### 10) ترکیب متدها (Method Chaining)

```javascript
const studentNames = persons
    .filter((p) => p.isStudent)
    .map((p) => p.name)
    .sort();

console.log(studentNames);
// ['Babak', 'Rostam']
```

---

## 36. Arrow Function در Array Methods

Arrow Function‌ها روش کوتاه‌تری برای نوشتن Callback هستند.

### مقایسه

```javascript
// Regular Function
function (item) {
    return item.age > 20;
}

// Arrow Function — حالت کامل
(item) => {
    return item.age > 20;
}

// Arrow Function — Implicit Return (کوتاه‌ترین)
item => item.age > 20
```

### قواعد Arrow Function

| وضعیت | نحوه نوشتن |
| ----- | ---------- |
| ۰ پارامتر | `() => { ... }` |
| ۱ پارامتر | `item => { ... }` (پارانتز اختیاری) |
| چند پارامتر | `(a, b) => { ... }` |
| یک خط و return | `item => item.age > 20` |
| چند خط | `item => { return ... }` |
| برگشت Object | `item => ({ key: value })` (نیاز به پرانتز) |

### مثال

```javascript
// Regular
const r1 = numbers.filter(function (item) {
    return item > 10;
});

// Arrow (کوتاه‌تر)
const r2 = numbers.filter(item => item > 10);
```

### مثال با برگشت Object

```javascript
const users = [
    { name: "Ali", age: 20 },
    { name: "Sara", age: 25 }
];

const result = users.map(user => ({
    fullName: user.name,
    isAdult: user.age >= 18
}));

console.log(result);
```

**خروجی:**
```
[
  { fullName: 'Ali', isAdult: true },
  { fullName: 'Sara', isAdult: true }
]
```

> 💡 **نکته مهم:** برای برگشت Object در Arrow Function یک‌خطی، حتماً از `()` استفاده کنید.

---

## 37. نکات Performance

> ⚠️ **توجه:** این بخش پیشرفته است. اگر تازه شروع کرده‌اید، فعلاً این بخش را بگذارید کنار.

### آیا همیشه `for` سریع‌تر است؟

به طور کلی، `for` کلاسیک کمی سریع‌تر از `map`/`filter` است چون:
- Overhead فراخوانی Callback ندارد.
- JavaScript Engine می‌تواند آن را بهتر بهینه‌سازی کند.

**اما** در عمل:
- تفاوت در اکثر برنامه‌ها **ناچیز** است.
- برای آرایه‌های کوچک و متوسط، تفاوت را متوجه نمی‌شوید.
- **خوانایی کد** معمولاً مهم‌تر از micro-optimization است.

### هزینه ایجاد Array جدید

متدهایی مثل `map` و `filter` آرایه جدید می‌سازند. این یعنی:
- مصرف حافظه بیشتر
- GC (Garbage Collection) بیشتر

برای آرایه‌های خیلی بزرگ (مثلاً میلیون‌ها عنصر)، این می‌تواند مشکل‌ساز شود.

### چه زمانی `for` مناسب‌تر است؟

- آرایه‌های خیلی بزرگ (میلیون‌ها عنصر)
- الگوریتم‌های پیچیده که نیاز به کنترل دقیق دارند
- حلقه‌هایی که نیاز به `break` یا `continue` دارند
- کار با دیتای غیر Iterable

### چه زمانی `map/filter/reduce` مناسب‌ترند؟

- بیشتر برنامه‌های روزمره
- کدی که باید خوانا و قابل نگهداری باشد
- کار با React و کتابخانه‌های مدرن
- وقتی نیاز به Immutability دارید

### از Micro-optimization غیرضروری پرهیز کنید

❌ به جای:
```javascript
// نادرست: نگرانی بی‌مورد
const result = [];
for (let i = 0; i < users.length; i++) {
    result.push(users[i].name);
}
```

✅ این را بنویسید:
```javascript
// درست: خوانا
const result = users.map(u => u.name);
```

### Benchmark و ادعاها

- نتایج Benchmark به **Engine** (V8، SpiderMonkey و ...)، **نسخه Node.js/مرورگر**، و **اندازه داده** بستگی دارد.
- ادعاهای قطعی مثل "map همیشه ۳x کندتر است" معمولاً دقیق نیستند.
- قبل از بهینه‌سازی، **Profile** کنید.

---

## 38. Iterator و Iterable

### Iterable چیست؟

**Iterable** هر شیئی است که `Symbol.iterator` داشته باشد. یعنی می‌توانیم روی آن حلقه بزنیم.

### Iterator چیست؟

**Iterator** یک شیئ است که متد `next()` دارد. `next()` یک Object برمی‌گرداند:

```javascript
{ value: ..., done: true/false }
```

### Symbol.iterator

```javascript
const numbers = [1, 2, 3];
const iterator = numbers[Symbol.iterator]();

console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: 2, done: false }
console.log(iterator.next()); // { value: 3, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

### `for...of` چگونه کار می‌کند؟

```javascript
for (const item of numbers) { ... }
```

معادل این است:

```javascript
const iterator = numbers[Symbol.iterator]();

while (true) {
    const { value, done } = iterator.next();
    if (done) break;
    // item = value
}
```

### Array چگونه Iterable است؟

Arrayها `Symbol.iterator` دارند، پس می‌توان با `for...of` پیمایش کرد.

### String چگونه Iterable است؟

```javascript
for (const char of "hello") {
    console.log(char); // h, e, l, l, o
}
```

### ساخت Iterator دستی

```javascript
function createCounter() {
    let count = 0;
    return {
        next() {
            count++;
            return { value: count, done: false };
        },
        [Symbol.iterator]() {
            return this;
        }
    };
}

const counter = createCounter();
for (const num of counter) {
    console.log(num);
    if (num >= 3) break;
}
// 1, 2, 3
```

---

## 39. Generator و Iteration

**Generator** تابعی است که می‌تواند مقادیر را یکی‌یکی تولید کند (yield).

### Syntax

```javascript
function* numbers() {
    yield 1;
    yield 2;
    yield 3;
}
```

### مثال

```javascript
const gen = numbers();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

### استفاده با `for...of`

```javascript
function* fibonacci() {
    let a = 0, b = 1;
    while (true) {
        yield a;
        [a, b] = [b, a + b];
    }
}

for (const num of fibonacci()) {
    if (num > 50) break;
    console.log(num);
}
// 0, 1, 1, 2, 3, 5, 8, 13, 21, 34
```

### Generator به عنوان Iterable

Generatorها به طور خودکار `Symbol.iterator` دارند، پس می‌توان از آن‌ها با `for...of` استفاده کرد.

### کاربرد

- Infinite sequences
- Lazy evaluation
- Async operations (با `async function*`)
- State machines

---

## 40. Common Mistakes (اشتباهات رایج)

### 1) استفاده اشتباه از `<=` در Loop

```javascript
// ❌ اشتباه
for (let i = 0; i <= arr.length; i++) {
    console.log(arr[i]); // undefined در آخرین Iteration
}

// ✅ درست
for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
```

### 2) فراموش کردن `i++`

```javascript
let i = 0;
while (i < 10) {
    console.log(i);
    // ❌ i++ فراموش شده → Infinite Loop
}
```

### 3) Infinite Loop

همیشه مطمئن شوید شمارنده در هر دور تغییر می‌کند.

### 4) استفاده اشتباه از `for...in` برای Array

```javascript
// ❌ نادرست
for (const i in arr) { ... }

// ✅ درست
for (const item of arr) { ... }
```

### 5) اشتباه گرفتن `map` و `forEach`

```javascript
// ❌ اشتباه: می‌خواهیم Array جدید بسازیم
const result = users.forEach(u => u.name); // undefined

// ✅ درست
const result = users.map(u => u.name);
```

### 6) اشتباه گرفتن `find` و `filter`

```javascript
// find → یک عنصر یا undefined
const user = users.find(u => u.id === 1);

// filter → یک Array (حتی خالی)
const users2 = users.filter(u => u.id === 1);
```

### 7) اشتباه گرفتن `some` و `every`

- `some` = **حداقل یکی**
- `every` = **همه**

### 8) فراموش کردن `return` در Callback

```javascript
// ❌ اشتباه
const result = numbers.map((n) => {
    n * 2;
});
// result = [undefined, undefined, ...]

// ✅ درست
const result = numbers.map((n) => {
    return n * 2;
});

// ✅ کوتاه‌تر
const result = numbers.map(n => n * 2);
```

### 9) استفاده اشتباه از `sort()` برای اعداد

```javascript
// ❌ اشتباه
[10, 2, 30].sort(); // [10, 2, 30]

// ✅ درست
[10, 2, 30].sort((a, b) => a - b); // [2, 10, 30]
```

### 10) تغییر ناخواسته Array اصلی

```javascript
const arr = [3, 1, 2];
arr.sort(); // آرایه اصلی تغییر می‌کند

// ✅ بهتر
const sorted = [...arr].sort((a, b) => a - b);
```

### 11) استفاده بی‌دلیل از `reduce`

برای کارهای ساده، از متدهای ساده‌تر استفاده کنید:

```javascript
// ❌ بیش از حد پیچیده
const sum = numbers.reduce((a, b) => a + b, 0);

// ✅ ساده‌تر اگر فقط جمع است
let sum = 0;
for (const n of numbers) sum += n;
```

البته `reduce` برای جمع کاملاً قابل قبول است — فقط برای کارهای خیلی ساده، `for` را هم در نظر بگیرید.

### 12) Chainهای بسیار پیچیده و غیرخوانا

```javascript
// ❌ خیلی طولانی و سخت خواندن
const result = data.filter(...).map(...).filter(...).reduce(...).sort(...).map(...);

// ✅ تقسیم کنید
const active = data.filter(...);
const names = active.map(...);
const filtered = names.filter(...);
// ...
```

---

## 41. مقایسه نهایی

| Method | خروجی | Array جدید؟ | کاربرد | Mutable؟ |
| ------ | ----- | ----------- | ------ | -------- |
| `for` | - | - | Loop عمومی | - |
| `while` | - | - | Loop با شرط نامشخص | - |
| `do...while` | - | - | حداقل یک بار اجرا | - |
| `for...of` | - | - | پیمایش Iterable (Values) | - |
| `for...in` | - | - | پیمایش Object (Keys) | - |
| `forEach` | `undefined` | ❌ خیر | اجرای عملیات روی عناصر | بستگی دارد |
| `map` | Array | ✅ بله | تبدیل عناصر | ❌ خیر |
| `filter` | Array | ✅ بله | فیلتر کردن | ❌ خیر |
| `find` | Element یا `undefined` | - | اولین مورد مطابق | ❌ خیر |
| `findIndex` | Number یا `-1` | - | Index اولین مورد | ❌ خیر |
| `findLast` | Element یا `undefined` | - | آخرین مورد مطابق | ❌ خیر |
| `findLastIndex` | Number یا `-1` | - | Index آخرین مورد | ❌ خیر |
| `some` | Boolean | - | حداقل یکی | ❌ خیر |
| `every` | Boolean | - | همه | ❌ خیر |
| `reduce` | هر نوع | - | تجمیع | ❌ خیر |
| `reduceRight` | هر نوع | - | تجمیع از انتها | ❌ خیر |
| `sort` | Array | همان آرایه | مرتب‌سازی | **✅ بله** |

---

## 42. چه زمانی از کدام روش استفاده کنیم؟

| هدف | روش پیشنهادی |
| --- | ------------ |
| فقط Loop بزنیم (تعداد مشخص) | `for` |
| Loop با شرط پیچیده (تعداد نامشخص) | `while` |
| حداقل یک بار اجرا | `do...while` |
| پیمایش Values یک Iterable | `for...of` |
| پیمایش Keys یک Object | `for...in` یا `Object.keys()` |
| اجرای عملیات (Side Effect) روی همه عناصر | `forEach` |
| تبدیل عناصر (به آرایه جدید) | `map` |
| فیلتر کردن عناصر | `filter` |
| پیدا کردن یک عنصر | `find` |
| پیدا کردن Index یک عنصر | `findIndex` |
| پیدا کردن آخرین عنصر | `findLast` |
| بررسی وجود حداقل یک مورد | `some` |
| بررسی اینکه همه شرایط را دارند | `every` |
| تجمیع به یک مقدار (جمع، ضرب، و ...) | `reduce` |
| مرتب‌سازی | `sort` |

### الگوی تصمیم‌گیری

```
آیا می‌خواهید آرایه جدید بسازید؟
├── بله
│   ├── تبدیل همه عناصر → map
│   ├── فیلتر کردن → filter
│   ├── مرتب‌سازی → sort
│   └── تجمیع → reduce
└── خیر
    ├── فقط اجرا کردن → forEach
    ├── پیدا کردن یک مورد → find
    ├── بررسی شرط → some / every
    └── پیدا کردن Index → findIndex
```

---

## 43. تمرین‌ها

### تمرین‌های مقدماتی

**1) چاپ اعداد 1 تا 10**
با استفاده از حلقه `for`، اعداد ۱ تا ۱۰ را چاپ کنید.

**2) چاپ اعداد زوج**
اعداد زوج از ۱ تا ۲۰ را چاپ کنید.

**3) پیمایش Array**
آرایه `["apple", "banana", "orange"]` را پیمایش کنید و هر میوه را چاپ کنید.

**4) پیدا کردن بزرگ‌ترین عدد**
بزرگ‌ترین عدد در `[5, 2, 9, 1, 7, 3]` را با `for` پیدا کنید.

**5) جمع عناصر Array**
مجموع اعداد `[10, 20, 30, 40, 50]` را محاسبه کنید.

### تمرین‌های متوسط

**6) استفاده از `map`**
یک آرایه از اسامی دارید. آرایه‌ای بسازید که هر اسم با "Hello " شروع شود.

**7) استفاده از `filter`**
از آرایه‌ای از اعداد، فقط اعداد مثبت را فیلتر کنید.

**8) استفاده از `find`**
در آرایه‌ای از کاربران، اولین کاربر با `role === "admin"` را پیدا کنید.

**9) استفاده از `some`**
بررسی کنید آیا آرایه‌ای از اعداد، حداقل یک عدد منفی دارد یا نه.

**10) استفاده از `every`**
بررسی کنید آیا همه اعداد در آرایه بزرگتر از ۰ هستند یا نه.

**11) استفاده از `reduce`**
مجموع قیمت‌های آرایه‌ای از محصولات را محاسبه کنید.

### تمرین‌های پیشرفته

**12) مرتب‌سازی افراد بر اساس سن**
با استفاده از `sort`، آرایه‌ای از افراد را بر اساس سن مرتب کنید.

**13) پیدا کردن دانش‌آموزان**
از آرایه `persons`، همه دانش‌آموزان را پیدا کنید.

**14) محاسبه مجموع سن افراد**
مجموع سن همه افراد را با `reduce` محاسبه کنید.

**15) تمرین ترکیبی**
از آرایه `persons`:
1. فقط افراد بزرگسال (سن >= ۱۸) را فیلتر کنید.
2. آرایه‌ای از اسم‌هایشان بسازید.
3. بر اساس اسم مرتب کنید.

---

## Solutions

<details>
<summary>👈 کلیک کنید تا پاسخ‌ها را ببینید</summary>

### پاسخ تمرین 1
```javascript
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
```

### پاسخ تمرین 2
```javascript
for (let i = 1; i <= 20; i++) {
    if (i % 2 === 0) console.log(i);
}
```

### پاسخ تمرین 3
```javascript
const fruits = ["apple", "banana", "orange"];

for (const fruit of fruits) {
    console.log(fruit);
}
```

### پاسخ تمرین 4
```javascript
const numbers = [5, 2, 9, 1, 7, 3];
let max = numbers[0];

for (const num of numbers) {
    if (num > max) max = num;
}
console.log(max); // 9
```

### پاسخ تمرین 5
```javascript
const numbers = [10, 20, 30, 40, 50];
let sum = 0;

for (const num of numbers) {
    sum += num;
}
console.log(sum); // 150
```

### پاسخ تمرین 6
```javascript
const names = ["Ali", "Sara", "Reza"];
const greetings = names.map(name => `Hello ${name}`);
console.log(greetings);
// ['Hello Ali', 'Hello Sara', 'Hello Reza']
```

### پاسخ تمرین 7
```javascript
const numbers = [-5, 3, -2, 8, -1, 10];
const positives = numbers.filter(n => n > 0);
console.log(positives); // [3, 8, 10]
```

### پاسخ تمرین 8
```javascript
const users = [
    { name: "Ali", role: "user" },
    { name: "Sara", role: "admin" },
    { name: "Reza", role: "admin" }
];
const admin = users.find(u => u.role === "admin");
console.log(admin); // { name: "Sara", role: "admin" }
```

### پاسخ تمرین 9
```javascript
const numbers = [3, 7, 2, -4, 9];
const hasNegative = numbers.some(n => n < 0);
console.log(hasNegative); // true
```

### پاسخ تمرین 10
```javascript
const numbers = [3, 7, 2, 5, 9];
const allPositive = numbers.every(n => n > 0);
console.log(allPositive); // true
```

### پاسخ تمرین 11
```javascript
const products = [
    { name: "Book", price: 20 },
    { name: "Pen", price: 5 },
    { name: "Bag", price: 35 }
];

const total = products.reduce((sum, p) => sum + p.price, 0);
console.log(total); // 60
```

### پاسخ تمرین 12
```javascript
const persons = [
    { name: "Ali", age: 20 },
    { name: "Sara", age: 15 },
    { name: "Reza", age: 30 }
];

persons.sort((a, b) => a.age - b.age);
console.log(persons);
```

### پاسخ تمرین 13
```javascript
const students = persons.filter(p => p.isStudent);
console.log(students);
```

### پاسخ تمرین 14
```javascript
const totalAge = persons.reduce((sum, p) => sum + p.age, 0);
console.log(totalAge); // 158
```

### پاسخ تمرین 15
```javascript
const result = persons
    .filter(p => p.age >= 18)
    .map(p => p.name)
    .sort();

console.log(result);
// ['Ali', 'Kaveh', 'Maziar', 'Rostam', 'Siavash']
```

</details>

---

## 44. جمع‌بندی نهایی

### Loop چیست؟
ساختاری که اجازه می‌دهد یک قطعه کد را چند بار اجرا کنیم.

### `for` چیست؟
رایج‌ترین نوع Loop با Initialization، Condition و Iterator.

### `while` چیست؟
Loopی که تا زمانی که شرط `true` است اجرا می‌شود.

### `do...while` چیست؟
حلقه‌ای که **حداقل یک بار** اجرا می‌شود.

### `for...of` چیست؟
حلقه‌ای برای پیمایش **Iterableها** (Array، String، Set، Map) و برگرداندن **مقدار**.

### `for...in` چیست؟
حلقه‌ای برای پیمایش **Propertyهای Object** و برگرداندن **کلید**.

### Callback چیست؟
تابعی که به عنوان آرگومان به تابع دیگری داده می‌شود.

### `map` چیست؟
آرایه‌ای جدید می‌سازد که هر عنصرش نتیجه Callback است.

### `filter` چیست؟
آرایه‌ای جدید از عناصری که شرط را دارند می‌سازد.

### `find` چیست؟
اولین عنصری که شرط را دارد برمی‌گرداند.

### `some` چیست؟
بررسی می‌کند آیا **حداقل یک عنصر** شرط را دارد یا نه.

### `every` چیست؟
بررسی می‌کند آیا **همه عناصر** شرط را دارند یا نه.

### `reduce` چیست؟
آرایه را به یک مقدار واحد تبدیل می‌کند (مثل جمع، ضرب و ...).

### `sort` چیست؟
عناصر را مرتب می‌کند. **Mutable** است!

### Iterator چیست؟
شیئی با متد `next()` که برای پیمایش Iterableها استفاده می‌شود.

---

## 45. References / منابع

### منابع رسمی و معتبر

- 📘 [MDN Web Docs — Loops and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
- 📘 [MDN Web Docs — `for` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
- 📘 [MDN Web Docs — `for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
- 📘 [MDN Web Docs — `for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)
- 📘 [MDN Web Docs — `while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
- 📘 [MDN Web Docs — `do...while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)
- 📘 [MDN Web Docs — `break`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break)
- 📘 [MDN Web Docs — `continue`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue)

### متدهای Array

- 📘 [MDN — `Array.prototype.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- 📘 [MDN — `Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- 📘 [MDN — `Array.prototype.find()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
- 📘 [MDN — `Array.prototype.findIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
- 📘 [MDN — `Array.prototype.findLast()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLast)
- 📘 [MDN — `Array.prototype.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- 📘 [MDN — `Array.prototype.some()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
- 📘 [MDN — `Array.prototype.every()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
- 📘 [MDN — `Array.prototype.reduce()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
- 📘 [MDN — `Array.prototype.reduceRight()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceRight)
- 📘 [MDN — `Array.prototype.sort()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

### Object Methods

- 📘 [MDN — `Object.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)
- 📘 [MDN — `Object.values()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values)
- 📘 [MDN — `Object.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)

### مفاهیم پیشرفته

- 📘 [MDN — Iterators and generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
- 📘 [MDN — Iteration protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
- 📘 [MDN — `Symbol.iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator)

### JavaScript.info (آموزش عمیق)

- 📘 [JavaScript.info — Loops: while and for](https://javascript.info/while-for)
- 📘 [JavaScript.info — Arrays methods](https://javascript.info/array-methods)
- 📘 [JavaScript.info — Iterables](https://javascript.info/iterable)
- 📘 [JavaScript.info — Generators](https://javascript.info/generators)

### ECMAScript Specification

- 📘 [ECMAScript Language Specification — ECMA-262](https://tc39.es/ecma262/)
  - Section: Statements (Loops)
  - Section: Array Prototype Methods
  - Section: Iterator Protocols

### سایر منابع مفید

- 📘 [MDN — Arrow function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
- 📘 [MDN — Destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

---

## 🎉 پایان

تبریک می‌گویم! شما الان یک درک کامل از Loopها و Array Methods در JavaScript دارید.

**قدم‌های بعدی پیشنهادی:**

1. تمرین‌های این آموزش را چند بار حل کنید.
2. پروژه‌های کوچک بسازید (مثل To-Do List، ماشین حساب، فیلتر محصولات).
3. مستندات MDN را برای هر متد مطالعه کنید.
4. روی پروژه‌های واقعی Open Source کار کنید.

**به یاد داشته باشید:** تسلط بر JavaScript نیاز به **تمرین مداوم** دارد. هیچ‌کس با یک بار خواندن این مطالب استاد نمی‌شود. کد بزنید، اشتباه کنید، یاد بگیرید.

> *"The only way to learn a new programming language is by writing programs in it."* — Dennis Ritchie

---

<div align="center">

**Happy Coding! 💻✨**

</div>
```

این README کامل و حرفه‌ای آماده است. تمام ۴۴ بخش درخواست شده را پوشش می‌دهد، از مبانی شروع می‌کند و تا مفاهیم پیشرفته (Iterator، Generator، Performance) می‌رود.

**ویژگی‌های کلیدی این آموزش:**

✅ **ساختار منسجم** — از ساده به پیچیده  
✅ **خط‌به‌خط توضیح** — هر مثال تشریح می‌شود  
✅ **مثال‌های واقعی** — با `persons` و داده‌های کاربردی  
✅ **جداول مقایسه‌ای** — برای درک بهتر تفاوت‌ها  
✅ **نکات مهم** — در کنار مفاهیم کلیدی  
✅ **Common Mistakes** — اشتباهات رایج توضیح داده شده  
✅ **تمرین‌های عملی** — ۱۵ تمرین با Solutions  
✅ **جدول تصمیم‌گیری** — برای انتخاب متد مناسب  
✅ **منابع معتبر** — MDN، JavaScript.info، ECMAScript Spec  

شما می‌توانید این فایل را مستقیماً به عنوان `README.md` در ریپوزیتوری GitHub خود قرار دهید.
