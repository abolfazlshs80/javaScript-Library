
---

1. [مقدمه](#1-مقدمه)
2. [دستور `if`](#2-دستور-if)
3. [دستور `else`](#3-دستور-else)
4. [دستور `else if`](#4-دستور-else-if)
5. [شرط‌های تو در تو (Nested if)](#5-شرط‌های-تو-در-تو-nested-if)
6. [عملگرهای مقایسه‌ای (Comparison Operators)](#6-عملگرهای-مقایسه‌ای-comparison-operators)
7. [عملگرهای منطقی (Logical Operators)](#7-عملگرهای-منطقی-logical-operators)
8. [مقادیر Truthy و Falsy](#8-مقادیر-truthy-و-falsy)
9. [استفاده از `if` با مقدار مستقیم](#9-استفاده-از-if-با-مقدار-مستقیم)
10. [شرط‌های ترکیبی و تقدم عملگرها](#10-شرط‌های-ترکیبی-و-تقدم-عملگرها)
11. [دستور `switch`](#11-دستور-switch)
12. [اهمیت `break` و مفهوم Fall-through](#12-اهمیت-break-و-مفهوم-fall-through)
13. [دستور `switch` و مقایسه Strict](#13-دستور-switch-و-مقایسه-strict)
14. [الگوی `switch(true)`](#14-الگوی-switchtrue)
15. [مقایسه فنی `if/else` و `switch`](#15-مقایسه-فنی-ifelse-و-switch)
16. [عملگر شرطی (Ternary Operator)](#16-عملگر-شرطی-ternary-operator)
17. [تفاوت Statement و Expression](#17-تفاوت-statement-و-expression)
18. [آشنایی با Object Literal](#18-آشنایی-با-object-literal)
19. [تعریف Method در Object Literal](#19-تعریف-method-در-object-literal)
20. [دسترسی با Dot Notation](#20-دسترسی-با-dot-notation)
21. [دسترسی با Bracket Notation](#21-دسترسی-با-bracket-notation)
22. [بررسی وجود Property](#22-بررسی-وجود-property)
23. [Object Literal به‌عنوان جایگزین شرط‌ها (Lookup Pattern)](#23-object-literal-بهعنوان-جایگزین-شرط‌ها-lookup-pattern)
24. [مقایسه جامع: `if` vs `switch` vs Object Lookup](#24-مقایسه-جامع-if-vs-switch-vs-object-lookup)
25. [۱۵ اشتباه رایج و Best Practiceها](#25-۱۵-اشتباه-رایج-و-best-practiceها)
26. [۱۰ مثال واقعی و کاربردی](#26-۱۰-مثال-واقعی-و-کاربردی)
27. [تمرین‌ها (مقدماتی تا پیشرفته)](#27-تمرین‌ها-مقدماتی-تا-پیشرفته)
28. [پروژه کوچک: Simple User Access System](#28-پروژه-کوچک-simple-user-access-system)
29. [نکات مهمی که باید به خاطر بسپارید](#29-نکات-مهمی-که-باید-به-خاطر-بسپارید)
30. [Cheat Sheet](#30-cheat-sheet)
31. [منابع معتبر](#31-منابع-معتبر)
- [پاسخ تمرین‌ها (Solutions)](#پاسخ-تمرین‌ها-solutions)

---

# 1. مقدمه

* **Conditional Statement (عبارت شرطی) چیست؟** دستوری است که به برنامه می‌گوید: «*اگر* این شرط برقرار بود، این کار را انجام بده؛ *در غیر این صورت*، آن کار را انجام بده.»
* **چرا به شرط نیاز داریم؟** دنیای واقعی و نرم‌افزار خطی نیستند. برنامه باید بر اساس ورودی کاربر، وضعیت سیستم یا داده‌ها، تصمیم‌های متفاوتی بگیرد (مثلاً: اگر رمز عبور درست بود، وارد شو).
* **JavaScript چگونه تصمیم می‌گیرد؟** جاوااسکریپت عبارت داخل پرانتز `()` را ارزیابی (Evaluate) می‌کند. اگر نتیجه نهایی `true` (یا معادل Truthy آن) باشد، بلوک کد `{}` اجرا می‌شود.
* **تفاوت اجرای خطی و شرطی:** در اجرای خطی، کدها از بالا به پایین بدون توقف اجرا می‌شوند. در اجرای شرطی، جریان اجرا (Control Flow) بر اساس نتیجه یک شرط، شاخه‌بندی (Branch) می‌شود.

> **مثال بسیار ساده:**
> ```javascript
> const isRaining = true;
> if (isRaining) {
>     console.log("Take an umbrella"); // این خط فقط اگر isRaining برابر true باشد اجرا می‌شود
> }
> ```

---

# 2. دستور `if`

ساده‌ترین شکل کنترل جریان.

```javascript
if (condition) {
    // code to execute
}
```

* **`if`:** کلمه کلیدی که شروع‌کننده شرط است.
* **`condition`:** عبارتی که باید به `true` یا `false` ارزیابی شود.
* **Body (بدنه):** کدهای داخل `{}` که فقط در صورت `true` بودن شرط اجرا می‌شوند.
* **اگر `true` باشد:** کد داخل `{}` اجرا می‌شود.
* **اگر `false` باشد:** کد داخل `{}` نادیده گرفته شده و برنامه به خط بعد از `}` می‌رود.

**مثال:**
```javascript
const age = 30;

if (age > 20) {
    console.log("you are adult");
}
```
**خروجی:** `you are adult`
**توضیح:** چون `30 > 20` برابر با `true` است، دستور `console.log` اجرا می‌شود.

---

# 3. دستور `else`

وقتی می‌خواهیم بگوییم «اگر شرط برقرار نبود، این کار جایگزین را انجام بده».

```javascript
const age = 18;

if (age >= 18) {
    console.log("You are adult");
} else {
    console.log("You are not adult");
}
```
**خروجی:** `You are adult`
**توضیح:** `else` همیشه به `if` بلافاصله قبل از خود وابسته است. اگر شرط `if` `false` شود، بلوک `else` به‌عنوان مسیر جایگزین (Fallback) اجرا می‌شود. هرگز نمی‌توان `else` را به تنهایی استفاده کرد.

---

# 4. دستور `else if`

برای بررسی چندین حالت مختلف به ترتیب اولویت استفاده می‌شود.

```javascript
const age = 13;

if (age > 20) {
    console.log("You are adult");
} else if (age > 10 && age < 20) {
    console.log("You are teen");
} else {
    console.log("You are kid");
}
```
**خروجی:** `You are teen`

**نکات حیاتی:**
1. **ترتیب بررسی:** جاوااسکریپت از بالا به پایین بررسی می‌کند.
2. **Short-circuiting (میان‌بر):** به محض اینکه اولین شرط `true` شود، آن بلوک اجرا شده و **تمام شرط‌های بعدی نادیده گرفته می‌شوند**.
3. **چرا ترتیب مهم است؟** اگر شرط عمومی‌تر را اول بگذارید، شرط‌های خاص‌تر هرگز اجرا نمی‌شوند.
4. **مشکل Overlapping (هم‌پوشانی):** اگر شرط‌ها هم‌پوشانی داشته باشند، فقط اولین شرطی که `true` شود برنده است.

**مثال اصلاح‌شده و بهینه‌تر:**
```javascript
if (age >= 20) {
    console.log("adult");
} else if (age >= 10) { // چون اگر به اینجا برسد، یعنی age < 20 است، نیاز به && نیست
    console.log("teen");
} else {
    console.log("kid");
}
```

---

# 5. شرط‌های تو در تو (Nested if)

قرار دادن یک `if` داخل `if` دیگر.

```javascript
const age = 25;
const hasTicket = true;

if (age >= 18) {
    if (hasTicket) {
        console.log("You can enter");
    }
}
```
* **چرا استفاده می‌کنیم؟** وقتی یک شرط، پیش‌نیاز منطقی شرط دوم است (مثلاً اول باید بزرگسال باشی، *سپس* بلیت داشته باشی).
* **چه زمانی مناسب نیست؟** وقتی باعث ایجاد "هرم مرگ" (Arrow Anti-pattern) می‌شود و خوانایی کد را به‌شدت کاهش می‌دهد (تو رفتگی‌های زیاد).
* **ساده‌سازی با `&&`:**
```javascript
if (age >= 18 && hasTicket) {
    console.log("You can enter");
}
```
این کد دقیقاً همان کار را انجام می‌دهد اما تمیزتر و خواناتر است.

---

# 6. عملگرهای مقایسه‌ای (Comparison Operators)

این عملگرها دو مقدار را مقایسه کرده و `true` یا `false` برمی‌گردانند.

| عملگر | توضیح | مثال (`true`) |
| :--- | :--- | :--- |
| `>` | بزرگ‌تر از | `5 > 3` |
| `<` | کوچک‌تر از | `3 < 5` |
| `>=` | بزرگ‌تر یا مساوی | `5 >= 5` |
| `<=` | کوچک‌تر یا مساوی | `4 <= 5` |
| `==` | مساوی (با تبدیل نوع) | `5 == "5"` |
| `===` | مساوی (بدون تبدیل نوع - Strict) | `5 === 5` |
| `!=` | نامساوی (با تبدیل نوع) | `5 != "4"` |
| `!==` | نامساوی (بدون تبدیل نوع - Strict) | `5 !== "5"` |

**تفاوت حیاتی `==` و `===`:**
```javascript
console.log(5 == "5");  // true (جاوااسکریپت رشته "5" را به عدد 5 تبدیل می‌کند)
console.log(5 === "5"); // false (نوع داده یکی عدد و دیگری رشته است، پس برابر نیستند)
```
> **Note:** در کدهای مدرن JavaScript، **همیشه** از `===` و `!==` استفاده کنید تا از باگ‌های ناشی از تبدیل نوع ضمنی (Implicit Coercion) جلوگیری شود.

---

# 7. عملگرهای منطقی (Logical Operators)

برای ترکیب چند شرط استفاده می‌شوند.

* **`&&` (AND):** هر دو طرف باید `true` باشند تا نتیجه `true` شود.
* **`||` (OR):** حداقل یکی از طرفین باید `true` باشد تا نتیجه `true` شود.
* **`!` (NOT):** مقدار بولی را معکوس می‌کند (`true` به `false` و برعکس).

**مثال AND:**
```javascript
const age = 25;
const hasTicket = true;

if (age >= 18 && hasTicket) {
    console.log("Allowed"); // اجرا می‌شود چون هر دو true هستند
}
```

**مثال OR:**
```javascript
const isWeekend = true;
const isHoliday = false;

if (isWeekend || isHoliday) {
    console.log("Day off"); // اجرا می‌شود چون حداقل یکی true است
}
```

**مثال NOT:**
```javascript
const isBanned = false;

if (!isBanned) {
    console.log("Access granted"); // اجرا می‌شود چون !false برابر true است
}
```

---

# 8. مقادیر Truthy و Falsy

در جاوااسکریپت، هر مقداری که در یک زمینه بولی (مثل شرط `if`) قرار گیرد، به `true` یا `false` تبدیل می‌شود.

**مقادیر Falsy (همیشه `false` می‌شوند):**
1. `false`
2. `0` (و `-0`)
3. `""` (رشته خالی)
4. `null`
5. `undefined`
6. `NaN` (Not a Number)

**مقادیر Truthy:**
* **هر چیز دیگری!** شامل تمام اعداد غیر صفر، تمام رشته‌های غیر خالی، آرایه‌ها `[]`، و اشیاء `{}` (حتی اگر خالی باشند).

**مثال‌ها:**
```javascript
if (0) { console.log("true"); } else { console.log("false"); } // خروجی: false
if ("hello") { console.log("true"); } // خروجی: true (رشته غیر خالی)
if ("") { console.log("true"); } else { console.log("false"); } // خروجی: false
if ([]) { console.log("true"); } // خروجی: true (آرایه یک شیء است)
if ({}) { console.log("true"); } // خروجی: true (شیء یک شیء است)
```

**تابع `Boolean(value)`:**
این تابع به‌صورت صریح (Explicit) هر مقداری را به معادل بولی آن تبدیل می‌کند.
```javascript
console.log(Boolean("hello")); // true
console.log(Boolean(0));       // false
```

---

# 9. استفاده از `if` با مقدار مستقیم

گاهی متغیر مستقیماً در شرط قرار می‌گیرد. جاوااسکریپت به‌طور خودکار آن را ارزیابی بولی می‌کند.

```javascript
const condition = 0;

if (condition) {
    console.log("executing this if...");
} else {
    console.log("executing this else...");
}
```
**خروجی:** `executing this else...`
**توضیح:** چون `0` یک مقدار Falsy است، شرط `false` ارزیابی شده و بلوک `else` اجرا می‌شود.

**بررسی مقادیر مختلف:**
* `true` -> if اجرا می‌شود.
* `false` -> else اجرا می‌شود.
* `1` -> if اجرا می‌شود (Truthy).
* `0` -> else اجرا می‌شود (Falsy).
* `"hello"` -> if اجرا می‌شود (Truthy).
* `""` -> else اجرا می‌شود (Falsy).

---

# 10. شرط‌های ترکیبی و تقدم عملگرها

در دنیای واقعی، شرط‌ها پیچیده‌تر هستند.

```javascript
// مثال 1: AND
if (age >= 18 && country === "Iran") {
    console.log("Adult in Iran");
}

// مثال 2: OR
if (age < 18 || hasPermission) {
    console.log("Can enter with guardian or permission");
}

// مثال 3: NOT
if (!isLoggedIn) {
    console.log("Please log in first");
}
```

**تقدم عملگرها (Operator Precedence):**
عملگر `&&` بر `||` مقدم است. اما برای خوانایی و جلوگیری از باگ، **همیشه از پرانتز `()` برای گروه‌بندی منطق استفاده کنید**.

```javascript
// بدون پرانتز (خطرناک و گیج‌کننده)
if (age >= 18 && hasTicket || isAdmin) { ... }

// با پرانتز (واضح و ایمن)
if ((age >= 18 && hasTicket) || isAdmin) {
    console.log("Access granted");
}
```

---

# 11. دستور `switch`

وقتی می‌خواهیم یک متغیر را با چندین مقدار ثابت (Exact values) مقایسه کنیم، `switch` خواناتر از زنجیره `else if` است.

```javascript
const day = 2;

switch (day) {
    case 1:
        console.log("Saturday");
        break;
    case 2:
        console.log("Sunday");
        break;
    default:
        console.log("Unknown day");
}
```
**خروجی:** `Sunday`

* **`switch`:** شروع‌کننده ساختار، یک `expression` (معمولاً یک متغیر) را می‌گیرد.
* **`expression`:** مقداری که قرار است ارزیابی و مقایسه شود.
* **`case`:** مقداری که با expression مقایسه می‌شود.
* **`break`:** دستور خروج از بلوک `switch`.
* **`default`:** مشابه `else`، اگر هیچ `case`ای مطابقت نداشت، اجرا می‌شود.

---

# 12. اهمیت `break` و مفهوم Fall-through

اگر `break` را فراموش کنید، جاوااسکریپت پس از اجرای `case` منطبق، به اجرای `case`های بعدی **بدون بررسی شرط** ادامه می‌دهد. به این پدیده **Fall-through** می‌گویند.

**مثال بدون `break` (اشتباه):**
```javascript
const number = 1;

switch (number) {
    case 1:
        console.log("one");
    case 2:
        console.log("two");
    case 3:
        console.log("three");
}
```
**خروجی:**
```text
one
two
three
```
**توضیح:** چون `number` برابر `1` است، از `case 1` شروع به اجرا می‌کند. چون `break` نیست، سرریز (Fall-through) شده و کدهای `case 2` و `case 3` را هم اجرا می‌کند.

**مثال صحیح:**
```javascript
switch (number) {
    case 1:
        console.log("one");
        break; // خروج از switch
    case 2:
        console.log("two");
        break;
    case 3:
        console.log("three");
        break;
}
```
> **Note:** گاهی Fall-through عمدی است (مثلاً برای گروه‌بندی چند `case` با یک خروجی)، اما باید با کامنت واضح مشخص شود.

---

# 13. دستور `switch` و مقایسه Strict

دستور `switch` در زیر کاپوت، از مقایسه **Strict Equality (`===`)** استفاده می‌کند. یعنی هم مقدار و هم نوع داده باید یکسان باشند.

```javascript
const value = "1"; // رشته

switch (value) {
    case 1: // عدد
        console.log("number");
        break;
    case "1": // رشته
        console.log("string");
        break;
}
```
**خروجی:** `string`
**توضیح:** چون `switch` از `===` استفاده می‌کند، `"1" === 1` برابر `false` است، اما `"1" === "1"` برابر `true` است.

---

# 14. الگوی `switch(true)`

این یک الگوی پیشرفته برای شبیه‌سازی `if / else if` با ساختار `switch` است.

```javascript
const age = 15;

switch (true) {
    case age > 20:
        console.log("you are adult");
        break;
    case age > 10 && age <= 20:
        console.log("you are teen");
        break;
    default:
        console.log("you are kid");
        break;
}
```
**خروجی:** `you are teen`

**چگونه کار می‌کند؟**
1. عبارت `switch` مقدار `true` را در نظر می‌گیرد.
2. هر `case` یک عبارت بولی (Boolean Expression) است.
3. جاوااسکریپت هر `case` را ارزیابی می‌کند. اولین `case`ای که نتیجه‌اش `true` شود (یعنی با `switch(true)` برابر باشد)، اجرا می‌شود.

**چه زمانی منطقی است؟**
وقتی چندین شرط پیچیده (Ranges) دارید و می‌خواهید از تکرار کلمه `else if` پرهیز کنید. اما در جامعه جاوااسکریپت، استفاده از `if / else if` برای این سناریو معمولاً خواناتر و استانداردتر در نظر گرفته می‌شود. از `switch(true)` فقط زمانی استفاده کنید که تیم توسعه‌دهنده با آن راحت باشد و واقعاً خوانایی را بهبود بخشد.

---

# 15. مقایسه فنی `if/else` و `switch`

| ویژگی | `if / else if` | `switch` |
| :--- | :--- | :--- |
| **نوع مقایسه** | هر نوع عبارت بولی (Ranges, `<`, `>`, توابع) | فقط مقادیر ثابت (Strict Equality `===`) |
| **خوانایی** | برای شرط‌های پیچیده و محدوده‌ای بهتر است | برای تطبیق یک متغیر با چند مقدار ثابت عالی است |
| **عملکرد** | از بالا به پایین ارزیابی می‌شود | در برخی موتورهای JS برای تعداد زیاد caseها بهینه‌تر است (Jump Table) |
| **Fall-through** | ندارد | دارد (نیاز به مدیریت با `break`) |

> **قانون کلی:** اگر یک متغیر را با چند مقدار مشخص (مثل روزهای هفته، نقش‌های کاربری) مقایسه می‌کنید، `switch` تمیزتر است. اگر محدوده‌ها (`>`, `<`) یا شرط‌های پیچیده دارید، `if/else` مناسب‌تر است.

---

# 16. عملگر شرطی (Ternary Operator)

یک میانبر برای نوشتن `if / else` در یک خط. این یک **Expression** است، نه Statement.

**Syntax:**
```javascript
condition ? valueIfTrue : valueIfFalse
```

**مثال:**
```javascript
const age = 20;
const result = age >= 18 ? "Adult" : "Not Adult";

console.log(result); // خروجی: Adult
```

**تفاوت با `if / else`:**
Ternary مقداری را **برمی‌گرداند** (Return می‌کند)، بنابراین می‌توان آن را در تخصیص متغیر (Assignment) یا بازگشت تابع استفاده کرد. `if / else` فقط جریان اجرا را کنترل می‌کند و مقداری برنمی‌گرداند.

> **هشدار:** از **Nested Ternary** (شرط‌های تو در تو) به‌شدت پرهیز کنید. خوانایی آن به سرعت از بین می‌رود.
> ```javascript
> // بد (غیرقابل خواندن)
> const status = age > 18 ? (hasTicket ? "Entry" : "No Ticket") : "Kid";
> // خوب (استفاده از if/else یا منطق ساده‌تر)
> ```

---

# 17. تفاوت Statement و Expression

درک این تفاوت برای تسلط بر جاوااسکریپت حیاتی است.

* **Statement (دستور):** یک عمل کامل است که کاری انجام می‌دهد، اما **مقداری تولید نمی‌کند**. (مثل `if`, `for`, `while`, `const x = 5;`).
* **Expression (عبارت):** قطعه کدی که **ارزیابی شده و به یک مقدار تبدیل می‌شود**. (مثل `2 + 2`, `"hello"`, `age > 18`, `condition ? "A" : "B"`).

**چرا Ternary در Assignment کار می‌کند اما `if` نه؟**
```javascript
// درست (Ternary یک Expression است و مقدار تولید می‌کند)
const message = isLoggedIn ? "Welcome" : "Please login";

// غلط (Syntax Error) - if یک Statement است و مقدار تولید نمی‌کند
const message = if (isLoggedIn) { "Welcome" } else { "Please login" };
```

---

# 18. آشنایی با Object Literal

**Object Literal** روشی برای ایجاد و مقداردهی اولیه یک شیء (Object) در جاوااسکریپت است.

```javascript
const car = {
    brand: "BMW",
    speed: 200
};
```
* **Object:** ساختار داده‌ای برای ذخیره مجموعه‌ای از جفت‌های Key-Value.
* **Object Literal:** سینتکس `{}` برای ساخت شیء.
* **Property (ویژگی):** جفت Key-Value (مثلاً `brand: "BMW"`).
* **Key (کلید):** نام property (مثل `brand`). همیشه رشته (String) یا Symbol است.
* **Value (مقدار):** داده‌ای که ذخیره می‌شود (مثل `"BMW"`). می‌تواند هر نوع داده‌ای باشد.
* **Method (متد):** Propertyای که مقدار آن یک تابع (Function) است.

---

# 19. تعریف Method در Object Literal

دو روش برای تعریف تابع درون شیء وجود دارد:

**روش 1: استفاده از Arrow Function (با احتیاط):**
```javascript
const carMethod = {
    start: () => {
        console.log("starting");
    },
    "speed up": () => { // کلید با فاصله باید در کوتیشن باشد
        console.log("speeding up");
    }
};
```
> **Note:** استفاده از Arrow Function در متدهای شیء معمولاً توصیه نمی‌شود، زیرا `this` را به درستی به خود شیء اشاره نمی‌دهد (به Lexical Scope بیرونی اشاره می‌کند).

**روش 2: Method Shorthand Syntax (روش مدرن و توصیه‌شده):**
```javascript
const car = {
    start() {
        console.log("starting");
    },
    drive() {
        console.log("driving");
    }
};
```
این سینتکس تمیزتر است و `this` را به درستی به خود شیء `car` متصل می‌کند.

---

# 20. دسترسی با Dot Notation

رایج‌ترین و خواناترین روش برای دسترسی به Propertyها.

```javascript
car.start(); // فراخوانی متد
console.log(car.brand); // دسترسی به مقدار
```
**قانون:** کلید باید یک شناسه (Identifier) معتبر جاوااسکریپت باشد (بدون فاصله، شروع نشدن با عدد).

---

# 21. دسترسی با Bracket Notation

این روش انعطاف‌پذیرتر است و از `[]` استفاده می‌کند.

```javascript
car["start"]();
```
**چرا به آن نیاز داریم؟**
1. **کلیدهای دارای فاصله یا کاراکترهای خاص:**
   ```javascript
   car["speed up"](); // صحیح
   // car.speed up(); // غلط: Syntax Error
   ```
2. **کلیدهای داینامیک (متغیرها):**
   ```javascript
   const action = "drive";
   car[action](); // معادل car.drive()
   ```

---

# 22. بررسی وجود Property

قبل از فراخوانی یک متد یا دسترسی به یک مقدار، بهتر است از وجود آن مطمئن شویم.

**روش 1: بررسی ساده (Truthy Check)**
```javascript
if (car.drive) {
    car.drive();
}
```
* **عیب:** اگر `car.drive` وجود داشته باشد اما مقدارش Falsy باشد (مثل `0`، `""` یا `false`)، این شرط شکست می‌خورد.

**روش 2: عملگر `in`**
```javascript
if ("drive" in car) {
    console.log("Property exists");
}
```
* **توضیح:** بررسی می‌کند که آیا این کلید در شیء یا زنجیره Prototype آن وجود دارد یا خیر.

**روش 3: `Object.hasOwn` (مدرن و توصیه‌شده)**
```javascript
if (Object.hasOwn(car, "drive")) {
    car.drive();
}
```
* **توضیح:** فقط بررسی می‌کند که آیا این Property **مستقیماً** متعلق به خود شیء است (نه Prototype). این روش جایگزین ایمن‌تر و مدرن‌تر برای `car.hasOwnProperty("drive")` است.

---

# 23. Object Literal به‌عنوان جایگزین شرط‌ها (Lookup Pattern)

به جای زنجیره‌های طولانی `if / else` یا `switch` برای اجرای عملکردهای مختلف، می‌توان از یک شیء به‌عنوان "جدول جستجو" (Lookup Table) استفاده کرد.

**روش قدیمی (`if / else`):**
```javascript
const action = "drive";

if (action === "start") {
    console.log("starting");
} else if (action === "drive") {
    console.log("driving");
} else if (action === "brake") {
    console.log("breaking");
}
```

**روش مدرن (Object Lookup):**
```javascript
const actions = {
    start() { console.log("starting"); },
    drive() { console.log("driving"); },
    brake() { console.log("breaking"); }
};

const action = "drive";

// بررسی وجود و اجرا در یک خط (با Optional Chaining)
actions[action]?.(); 

// یا روش سنتی‌تر:
if (actions[action]) {
    actions[action]();
}
```
**مزیت:** افزودن یک عملیات جدید فقط نیازمند اضافه کردن یک کلید جدید به شیء است، بدون دستکاری منطق شرطی. این الگو در برنامه‌نویسی تابعی و طراحی الگوها بسیار قدرتمند است.

---

# 24. مقایسه جامع: `if` vs `switch` vs Object Lookup

| معیار | `if / else if` | `switch` | Object Lookup |
| :--- | :--- | :--- | :--- |
| **مسئله حل‌شده** | منطق شرطی پیچیده، محدوده‌ها (`>`, `<`) | تطبیق یک مقدار با چند حالت ثابت | نگاشت (Mapping) کلیدها به رفتارها/مقادیر |
| **خوانایی** | خوب برای منطق پیچیده، بد برای لیست‌های طولانی | عالی برای لیست‌های طولانی مقادیر ثابت | عالی برای رفتارهای مبتنی بر کلید (Dispatch) |
| **نگهداری (Maintainability)** | با افزایش شرط‌ها، پیچیده می‌شود | متوسط (خطر فراموشی `break`) | بسیار بالا (افزودن کلید جدید بدون تغییر منطق) |
| **تعداد حالت‌ها** | نامحدود | نامحدود | نامحدود |
| **شرط‌های پیچیده** | پشتیبانی کامل | پشتیبانی نمی‌کند (مگر با `switch(true)`) | پشتیبانی نمی‌کند (فقط کلیدهای دقیق) |
| **مقدارهای ثابت** | ممکن است اما پرحرف | عالی | عالی |

---

# 25. ۱۵ اشتباه رایج و Best Practiceها

1. **فراموش کردن `{}`:** در `if`های تک‌خطی ممکن است، اما همیشه از `{}` استفاده کنید تا از باگ‌های آینده جلوگیری شود.
2. **استفاده از `=` به جای `===`:** `if (a = 5)` مقداردهی می‌کند و همیشه `true` می‌شود! همیشه از `===` استفاده کنید.
3. **استفاده نادرست از `==`:** باعث تبدیل نوع ضمنی و باگ‌های عجیب می‌شود.
4. **اشتباه در `&&` و `||`:** فراموش کردن اینکه `||` نیاز به تکرار متغیر دارد: `if (age === 10 || age === 20)` (نه `age === 10 || 20`).
5. **اشتباه در Truthy/Falsy:** فرض کردن اینکه `[]` یا `{}` برابر `false` هستند (آن‌ها Truthy هستند).
6. **ترتیب نادرست `else if`:** گذاشتن شرط عمومی (`age > 10`) قبل از شرط خاص (`age > 20`).
7. **شرط‌های Overlapping:** نوشتن شرط‌هایی که هم‌پوشانی دارند بدون درک اینکه فقط اولی اجرا می‌شود.
8. **Nested if بیش از حد:** ایجاد کد "هرمی" که دیباگ آن غیرممکن است. از `&&` یا Guard Clauses استفاده کنید.
9. **فراموش کردن `break` در `switch`:** منجر به Fall-through ناخواسته می‌شود.
10. **استفاده از `switch` برای محدوده‌ها:** `switch` برای `>` یا `<` طراحی نشده است (مگر با الگوی `switch(true)` که همیشه بهترین انتخاب نیست).
11. **Ternaryهای تو در تو:** کد را غیرقابل خواندن می‌کند.
12. **استفاده از Dot Notation برای کلیدهای داینامیک:** `obj[varName]` غلط است، باید از `obj[varName]` (Bracket) استفاده شود.
13. **فراخوانی Propertyای که وجود ندارد:** منجر به `undefined is not a function` می‌شود. همیشه وجود آن را بررسی کنید.
14. **استفاده از Arrow Function برای متدهای شیء:** باعث از دست رفتن `this` صحیح می‌شود. از Method Shorthand استفاده کنید.
15. **عدم استفاده از `default` در `switch`:** همیشه یک حالت پیش‌فرض برای مدیریت مقادیر غیرمنتظره در نظر بگیرید.

---

# 26. ۱۰ مثال واقعی و کاربردی

1. **بررسی سن:**
   ```javascript
   const age = 17;
   const canVote = age >= 18 ? "Yes" : "No";
   ```
2. **Login:**
   ```javascript
   if (!username || !password) {
       console.log("Please fill all fields");
   }
   ```
3. **بررسی Admin:**
   ```javascript
   if (user.role === "admin" && user.isActive) {
       showDashboard();
   }
   ```
4. **بررسی موجودی محصول:**
   ```javascript
   if (stock > 0) {
       console.log("In Stock");
   } else {
       console.log("Out of Stock");
   }
   ```
5. **وضعیت سفارش:**
   ```javascript
   switch (orderStatus) {
       case "pending": console.log("Processing"); break;
       case "shipped": console.log("On the way"); break;
       default: console.log("Unknown");
   }
   ```
6. **روزهای هفته (نام فارسی):**
   ```javascript
   const days = { 1: "شنبه", 2: "یکشنبه", 7: "جمعه" };
   console.log(days[new Date().getDay()] || "نامعتبر");
   ```
7. **سطح دسترسی کاربر:**
   ```javascript
   const permissions = { admin: ["read", "write", "delete"], user: ["read"] };
   const userPerms = permissions[role] || ["read"];
   ```
8. **وضعیت پرداخت:**
   ```javascript
   if (isPaid && !isRefunded) {
       console.log("Transaction Complete");
   }
   ```
9. **عملیات ماشین (Lookup):**
   ```javascript
   const carActions = { start: () => "Vroom!", stop: () => "Halt!" };
   console.log(carActions["start"]());
   ```
10. **انتخاب عملیات Calculator:**
    ```javascript
    const mathOps = {
        add: (a, b) => a + b,
        sub: (a, b) => a - b
    };
    console.log(mathOps["add"](5, 3)); // 8
    ```

---

# 27. تمرین‌ها (مقدماتی تا پیشرفته)

### Beginner
1. متغیری به نام `score` بسازید. اگر `score >= 10` بود، "Pass" را چاپ کنید.
2. متغیر `isRaining` را `true` قرار دهید. با `if/else` چاپ کنید "Take umbrella" یا "Enjoy sun".
3. متغیر `age` را چک کنید. اگر `< 13` بود "Kid"، در غیر این صورت "Teen/Adult" چاپ شود.
4. دو متغیر `hasMoney` و `hasTime` بسازید. اگر هر دو `true` بودند، "Go to cinema" چاپ شود.
5. مقدار `""` (رشته خالی) را در یک `if` قرار دهید. چه چیزی چاپ می‌شود؟
6. با استفاده از Ternary، اگر `age >= 18` بود متغیر `status` برابر "Adult" شود، وگرنه "Minor".
7. یک شیء `user` با propertyهای `name` و `age` بسازید و با Dot Notation `name` را چاپ کنید.
8. یک متد `greet` به شیء `user` اضافه کنید که "Hello" چاپ کند و آن را فراخوانی کنید.
9. با استفاده از Bracket Notation به propertyای به نام `"first name"` در یک شیء دسترسی پیدا کنید.
10. یک `switch` ساده برای متغیر `color` با caseهای "red" و "blue" بنویسید.

### Intermediate
11. متغیر `temperature` را چک کنید: اگر `< 0` "Freezing"، اگر `0-15` "Cold"، اگر `16-25` "Mild"، وگرنه "Hot" چاپ شود (با `else if`).
12. یک `switch` برای روزهای هفته (1 تا 7) بنویسید. روزهای 1 تا 5 "Workday" و 6 و 7 "Weekend" چاپ شوند (با استفاده از Fall-through عمدی).
13. بررسی کنید آیا property به نام `email` در شیء `user` وجود دارد یا خیر (با `Object.hasOwn`).
14. یک تابع بنویسید که یک نمره بگیرد و با Ternary تو در تو (فقط برای تمرین، سپس آن را به `if` تبدیل کنید) A, B, C را برگرداند.
15. الگوی Object Lookup را برای تبدیل کد وضعیت HTTP (200, 404, 500) به پیام متنی پیاده‌سازی کنید.
16. شرطی بنویسید که اگر کاربر `isAdmin` بود **یا** (`ownerId === currentUserId`) بود، اجازه ویرایش بدهد.
17. متغیری به نام `data` دارید که ممکن است `null` یا یک شیء باشد. با Optional Chaining (`?.`) property `name` آن را بخوانید.
18. یک شیء `calculator` بسازید که متدهای `add` و `multiply` داشته باشد و با ورودی داینامیک فراخوانی شود.
19. تفاوت خروجی `if ([])` و `if (0)` را با توضیح کتبی بنویسید.
20. یک `switch(true)` بنویسید که بر اساس `score`، رتبه‌بندی (عالی، خوب، ضعیف) را چاپ کند.

### Advanced
21. یک زنجیره `if/else` طولانی را به الگوی Object Lookup (Dispatch Table) بازنویسی (Refactor) کنید.
22. تابعی بنویسید که یک شیء پیکربندی (Config) بگیرد. اگر propertyای وجود نداشت، از مقدار پیش‌فرض (با `||` یا `??`) استفاده کند.
23. با استفاده از متدهای شیء و `this`، یک شیء `bankAccount` بسازید که متد `deposit` داشته باشد و موجودی را به‌روز کند.
24. یک شرط پیچیده بنویسید که ترکیبی از `&&`، `||` و `!` باشد و با پرانتزها کاملاً گروه‌بندی شده باشد تا تقدم عملگرها را نشان دهد.
25. بررسی کنید چرا `if (new Boolean(false))` اجرا می‌شود، اما `if (false)` اجرا نمی‌شود (تفاوت Object بولی و Primitive بولی).
26. یک سیستم مسیریابی (Router) ساده با Object Lookup بسازید که بر اساس `path` (مثل `"/home"`)، تابع مربوطه را اجرا کند.
27. از `switch` برای مدیریت Actionهای یک Redux-like reducer استفاده کنید (با `default` که خطا برمی‌گرداند).
28. یک تابع بنویسید که اگر ورودی `undefined` یا `null` بود، یک شیء پیش‌فرض برگرداند، در غیر این صورت خود ورودی را (با استفاده از Ternary).
29. یک شیء بسازید که کلیدهای آن Symbol باشند و نشان دهید که چگونه می‌توان به آن‌ها دسترسی پیدا کرد (یا چرا در `for...in` دیده نمی‌شوند).
30. کدی بنویسید که وجود یک متد را بررسی کند، و اگر وجود داشت آن را با `call` یا `apply` و مقدار `this` مشخص فراخوانی کند.

---

# 28. پروژه کوچک: Simple User Access System

یک سیستم مدیریت دسترسی که مفاهیم را ترکیب می‌کند.

```javascript
// 1. تعریف داده‌ها
const user = {
    id: 101,
    name: "Ali",
    age: 22,
    role: "editor",
    isBanned: false,
    loginStatus: true
};

const action = "delete_post";

// 2. بررسی اولیه با if (Guard Clause)
if (!user.loginStatus) {
    console.log("Access Denied: Please login first.");
} else if (user.isBanned) {
    console.log("Access Denied: Account is banned.");
} else {
    // 3. بررسی سن با Ternary
    const ageMessage = user.age >= 18 ? "Adult user" : "Minor user";
    console.log(`System Check: ${ageMessage}`);

    // 4. تعیین سطح دسترسی با switch
    let canExecute = false;
    switch (user.role) {
        case "admin":
            canExecute = true;
            break;
        case "editor":
            // اجازه ویرایش و حذف، اما نه تغییر تنظیمات
            canExecute = (action === "edit_post" || action === "delete_post");
            break;
        case "viewer":
            canExecute = false;
            break;
        default:
            console.log("Unknown role");
    }

    // 5. اجرای عملیات با Object Lookup (اگر اجازه داشت)
    if (canExecute) {
        const actions = {
            edit_post() { console.log("Post edited successfully."); },
            delete_post() { console.log("Post deleted successfully."); },
            change_settings() { console.log("Settings changed."); }
        };

        // بررسی وجود و اجرا
        if (Object.hasOwn(actions, action)) {
            actions[action]();
        } else {
            console.log("Invalid action requested.");
        }
    } else {
        console.log("Access Denied: Insufficient permissions for this action.");
    }
}
```
**خروجی این کد:**
```text
System Check: Adult user
Post deleted successfully.
```

---

# 29. نکات مهمی که باید به خاطر بسپارید

* **همیشه از `===` و `!==` استفاده کنید** تا از باگ‌های تبدیل نوع جلوگیری شود.
* **`switch` از مقایسه Strict (`===`) استفاده می‌کند.**
* **آرایه‌ها `[]` و اشیاء `{}` همیشه Truthy هستند**، حتی اگر خالی باشند.
* **از Nested Ternary پرهیز کنید**؛ خوانایی کد از کوتاه‌نویسی مهم‌تر است.
* **برای کلیدهای داینامیک یا دارای فاصله، همیشه از Bracket Notation `[]` استفاده کنید.**
* **الگوی Object Lookup** جایگزین قدرتمند و تمیزی برای زنجیره‌های طولانی `if/else` یا `switch` هنگام نگاشت مقادیر به توابع است.
* **همیشه `default` را در `switch` قرار دهید** تا حالت‌های پیش‌بینی‌نشده مدیریت شوند.

---

# 30. Cheat Sheet

```javascript
// 1. if / else
if (condition) { /* true */ } else { /* false */ }

// 2. else if
if (cond1) { } else if (cond2) { } else { }

// 3. switch
switch (expr) {
    case val1: /* code */ break;
    default: /* code */
}

// 4. Ternary
const res = condition ? "Yes" : "No";

// 5. Object Literal & Methods
const obj = {
    key: "value",
    method() { console.log("hi"); }
};

// 6. Access
obj.key;          // Dot Notation
obj["key name"];  // Bracket Notation (for dynamic/spaced keys)

// 7. Check Property
Object.hasOwn(obj, "key"); // Modern & Safe
```

---

# 31. منابع معتبر

برای مطالعه عمیق‌تر و ارجاع رسمی، از منابع زیر استفاده کنید:

1. **MDN Web Docs (Mozilla)**
   * موضوع: `if...else`, `switch`, Logical Operators, Object.hasOwn
   * لینک: [MDN Control Flow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
2. **JavaScript.info**
   * موضوع: Conditional branching, Logical operators, Object methods & "this"
   * لینک: [JS.info Conditional Operators](https://javascript.info/ifelse)
3. **ECMAScript Specification (ECMA-262)**
   * موضوع: تعریف رسمی Abstract Equality Comparison و Strict Equality
   * لینک: [ECMAScript Spec](https://tc39.es/ecma262/)

---

# پاسخ تمرین‌ها (Solutions)

<details>
<summary><strong>کلیک کنید تا پاسخ تمرین‌های Beginner را ببینید</strong></summary>

1. `if (score >= 10) console.log("Pass");`
2. `if (isRaining) console.log("Take umbrella"); else console.log("Enjoy sun");`
3. `if (age < 13) console.log("Kid"); else console.log("Teen/Adult");`
4. `if (hasMoney && hasTime) console.log("Go to cinema");`
5. `false` چاپ می‌شود (چون `""` Falsy است).
6. `const status = age >= 18 ? "Adult" : "Minor";`
7. `console.log(user.name);`
8. `user.greet = function() { console.log("Hello"); }; user.greet();`
9. `console.log(user["first name"]);`
10. `switch(color) { case "red": console.log("Stop"); break; case "blue": console.log("Go"); break; }`
</details>

<details>
<summary><strong>کلیک کنید تا پاسخ تمرین‌های Intermediate را ببینید</strong></summary>

11. `if (temp < 0) "Freezing"; else if (temp <= 15) "Cold"; else if (temp <= 25) "Mild"; else "Hot";`
12. `switch(day) { case 6: case 7: console.log("Weekend"); break; default: console.log("Workday"); }`
13. `if (Object.hasOwn(user, "email")) { ... }`
14. (توصیه می‌شود به `if` تبدیل شود، اما Ternary تو در تو: `return score >= 90 ? "A" : (score >= 80 ? "B" : "C");`)
15. `const msgs = { 200: "OK", 404: "Not Found", 500: "Server Error" }; console.log(msgs[code] || "Unknown");`
16. `if (isAdmin || ownerId === currentUserId) { /* allow */ }`
17. `console.log(data?.name);`
18. `const calc = { add: (a,b)=>a+b, multiply: (a,b)=>a*b }; console.log(calc[op](5, 2));`
19. `[]` یک شیء است و Truthy می‌باشد (شرط اجرا می‌شود). `0` عدد است و Falsy می‌باشد (شرط اجرا نمی‌شود).
20. `switch(true) { case score >= 90: console.log("Excellent"); break; ... }`
</details>

<details>
<summary><strong>کلیک کنید تا پاسخ تمرین‌های Advanced را ببینید</strong></summary>

21. (Refactoring) تبدیل `if (type === 'A') doA(); else if (type === 'B') doB();` به `const actions = { A: doA, B: doB }; actions[type]?.();`
22. `const finalConfig = { timeout: 5000, ...userConfig };` (یا استفاده از `??`)
23. `const account = { balance: 0, deposit(amount) { this.balance += amount; } };`
24. `if ((isAuth && hasRole) || (isOwner && !isBanned)) { ... }`
25. `new Boolean(false)` یک **Object** است و تمام اشیاء در جاوااسکریپت Truthy هستند. `false` یک Primitive Falsy است.
26. `const routes = { "/home": renderHome, "/about": renderAbout }; routes[path]?.();`
27. `switch(action.type) { case 'ADD': return {...state, val: 1}; default: throw new Error("Unknown action"); }`
28. `return (input === undefined || input === null) ? {} : input;`
29. کلیدهای Symbol در `for...in` یا `Object.keys` ظاهر نمی‌شوند، اما با `Object.getOwnPropertySymbols(obj)` قابل دسترسی هستند.
30. `if (typeof obj.method === 'function') { obj.method.call(customThis); }`
</details>

---
> اگر سؤال خاصی درباره هر یک از این مفاهیم دارید یا می‌خواهید مثال‌ها را با توجه به پروژه‌های واقعی خود در مازندران (مثلاً سیستم‌های رزرو بوم‌گردی یا مدیریت محصولات محلی) شخصی‌سازی کنم، خوشحال می‌شوم کمک کنم!
