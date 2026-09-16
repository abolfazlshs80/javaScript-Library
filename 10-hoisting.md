
## فهرست مطالب

...

## مقدمه

...

## منابع معتبر

...
```

خوانایی برای GitHub بسیار مهم است.

از این موارد استفاده کن:

* Emoji در حد متعادل
* Calloutهای Markdown در صورت نیاز
* Code Block
* جدول
* مثال
* خروجی
* نکته
* هشدار
* تمرین
* سوال
* پاسخ

اما از شلوغ کردن بیش از حد صفحه خودداری کن.

مخاطب اصلی این آموزش **برنامه‌نویس مبتدی JavaScript** است؛ بنابراین هیچ مفهوم پیشرفته‌ای را بدون توضیح مقدماتی وارد نکن.

در عین حال، آموزش باید در بخش‌های پایانی به اندازه‌ای عمیق باشد که یک برنامه‌نویس متوسط بتواند ارتباط Hoisting با **Scope، Execution Context، Environment Record، TDZ، Closure، Modules و ECMAScript Specification** را درک کند.

در پایان نیز یک **جمع‌بندی بسیار ساده و قابل حفظ کردن** ارائه کن.


### ASSISTANT
# 🚀 آموزش جامع Hoisting در JavaScript
> **از مقدماتی تا پیشرفته | درک عمیق رفتار JavaScript و ECMAScript**

این مخزن (Repository) یک راهنمای کامل، گام‌به‌گام و عمیق درباره مفهوم **Hoisting** در جاوااسکریپت است. هدف ما عبور از مدل‌های ذهنی ساده‌سازی‌شده و رسیدن به درک دقیق رفتار موتور JavaScript (Engine) و مشخصات رسمی ECMAScript است.

---

## 📑 فهرست مطالب
<details>
<summary>برای مشاهده فهرست کامل کلیک کنید</summary>

1. [مقدمه‌ای بر Hoisting](#1-مقدمه‌ای-بر-hoisting)
2. [پیش‌نیازها: قبل از Hoisting](#2-javascript-قبل-از-بررسی-hoisting)
3. [Hoisting و Execution Context](#3-hoisting-و-execution-context)
4. [Hoisting در var](#4-hoisting-در-var)
5. [تفاوت Declaration و Initialization در var](#5-تفاوت-declaration-و-initialization-در-var)
6. [Hoisting در Function Declaration](#6-hoisting-در-function-declaration)
7. [Function Declaration در برابر Function Expression](#7-function-declaration-در-برابر-function-expression)
8. [Hoisting در Arrow Function](#8-hoisting-در-arrow-function)
9. [Hoisting در let](#9-hoisting-در-let)
10. [Temporal Dead Zone (TDZ)](#10-temporal-dead-zone-tdz)
11. [Hoisting در const](#11-hoisting-در-const)
12. [مقایسه var و let و const](#12-مقایسه-var-و-let-و-const)
13. [Hoisting و Scope](#13-hoisting-و-scope)
14. [Shadowing و Hoisting](#14-shadowing-و-hoisting)
15. [Hoisting در کلاس‌ها (Classes)](#15-hoisting-در-کلاس‌ها)
16. [Hoisting در import و export](#16-hoisting-در-import-و-export)
17. [Hoisting در Parameters](#17-hoisting-در-parameters)
18. [Hoisting و Default Parameters](#18-hoisting-و-default-parameters)
19. [Hoisting و Destructuring](#19-hoisting-و-destructuring)
20. [Hoisting و Closures](#20-hoisting-و-closures)
21. [Hoisting در Loops](#21-hoisting-در-loops)
22. [Hoisting در Conditional Statements](#22-hoisting-در-conditional-statements)
23. [Hoisting و var در Block](#23-hoisting-و-var-در-block)
24. [Hoisting در Nested Functions](#24-hoisting-در-nested-functions)
25. [ترتیب Hoisting در var و Function Declaration](#25-ترتیب-hoisting-در-var-و-function-declaration)
26. [Hoisting و Redeclaration](#26-hoisting-و-redeclaration)
27. [Hoisting و Global Scope](#27-hoisting-و-global-scope)
28. [Hoisting در Browser و Node.js](#28-hoisting-در-browser-و-nodejs)
29. [Hoisting و Strict Mode](#29-hoisting-و-strict-mode)
30. [Hoisting و typeof](#30-hoisting-و-typeof)
31. [Hoisting و Errorها](#31-hoisting-و-errorها)
32. [اشتباهات رایج درباره Hoisting](#32-اشتباهات-رایج-درباره-hoisting)
33. [Hoisting در مصاحبه‌های JavaScript](#33-hoisting-در-مصاحبههای-javascript)
34. [سوالات خروجی کد (Output Questions)](#34-سوالات-خروجی-کد-output-questions)
35. [مثال‌های Trick و Edge Case](#35-مثال‌های-trick-و-edge-case)
36. [Hoisting از دید JavaScript Engine](#36-hoisting-از-دید-javascript-engine)
37. [Hoisting از دید ECMAScript Specification](#37-hoisting-از-دید-ecmascript-specification)
38. [Hoisting واقعی در برابر مدل ذهنی](#38-hoisting-واقعی-در-برابر-مدل-ذهنی)
39. [تفاوت Hoisting و Scope](#39-تفاوت-hoisting-و-scope)
40. [تفاوت Hoisting و Temporal Dead Zone](#40-تفاوت-hoisting-و-temporal-dead-zone)
41. [Hoisting و Best Practices](#41-hoisting-و-best-practices)
42. [پروژه کوچک برای تمرین](#42-پروژه-کوچک-برای-تمرین-hoisting)
43. [تمرین‌های عملی](#43-تمرین‌های-عملی)
44. [Cheat Sheet](#44-cheat-sheet)
45. [جدول نهایی رفتار Hoisting](#45-جدول-نهایی-رفتار-hoisting)
46. [نقشه یادگیری](#46-نقشه-یادگیری-hoisting)
47. [منابع معتبر](#48-منابع-معتبر)
</details>

---

## 1. مقدمه‌ای بر Hoisting

### 1.1 Hoisting چیست؟
**Hoisting** (بالا بردن / ارجاع) یک رفتار در JavaScript است که طی آن، تعاریف (Declarations) متغیرها و توابع، **پیش از آنکه اجرای کد به خط مورد نظر برسد**، در مرحله ساخت (Creation Phase) در حافظه ثبت می‌شوند.

### 1.2 معنی لغوی Hoisting
کلمه Hoisting به معنای «بالا کشیدن» یا «بالا بردن» است.

### 1.3 چرا به آن Hoisting می‌گوییم؟
در روزهای اولیه JavaScript، توسعه‌دهندگان متوجه شدند که می‌توانند از یک متغیر یا تابع **قبل از خطی که آن را تعریف کرده‌اند** استفاده کنند. برای توضیح این رفتار عجیب، اصطلاح «Hoisting» یا «بالا بردن کد به بالای فایل» توسط جامعه برنامه‌نویسان ابداع شد.

### 1.4 ⚠️ آیا واقعاً JavaScript کد را به بالای فایل منتقل می‌کند؟
**خیر! این یک بزرگترین سوءتفاهم در JavaScript است.**
موتور JavaScript (Engine) کد شما را خط‌به‌خط جابه‌جا **نمی‌کند**. آنچه اتفاق می‌افتد این است که Engine در مرحله **Parsing** (تجزیه)، کد را می‌خواند و قبل از اجرای خط‌به‌خط (Execution)، نام متغیرها و توابع را در یک ساختار داده‌ای به نام **Environment Record** ثبت می‌کند.
> 💡 **نکته کلیدی:** عبارت «کد به بالا منتقل می‌شود» فقط یک **مدل ذهنی (Mental Model)** برای درک ساده‌تر است، نه واقعیت فنی.

### 1.5 یک مثال بسیار ساده
```javascript
console.log(name); // خروجی: undefined
var name = "Ali";
```
**توضیح:** اگر کد واقعاً جابه‌جا می‌شد، باید `undefined` چاپ می‌شد (که می‌شود)، اما در واقعیت Engine نام `name` را قبل از اجرا ثبت کرده و مقدار پیش‌فرض `undefined` را به آن اختصاص داده است.

### 1.6 Hoisting چه مشکلی را حل می‌کند؟
در ابتدا، این رفتار به برنامه‌نویسان اجازه می‌داد توابع کمکی (Helper Functions) را در انتهای فایل بنویسند و در ابتدای فایل فراخوانی کنند، بدون اینکه نگران ترتیب نوشتن کد باشند.

### 1.7 چرا شناخت Hoisting مهم است؟
برای جلوگیری از باگ‌های عجیب (مثل `undefined` گرفتن متغیرها یا خطای `ReferenceError`) و درک عمیق نحوه کار موتور JS.

### 1.8 آیا Hoisting یک اصطلاح رسمی در ECMAScript است؟
**خیر.** کلمه "Hoisting" در Specification رسمی TC39 وجود ندارد. این یک اصطلاح رایج بین توسعه‌دهندگان (Developer Jargon) است. در Spec از مفاهیمی مثل **VariableDeclarationInstantiation** و **Binding** استفاده می‌شود.

### 1.9 تفاوت مدل ذهنی ساده با رفتار واقعی
*   **مدل ذهنی:** `var x; console.log(x); x = 10;` (کد جابه‌جا شده).
*   **رفتار واقعی:** Engine یک Execution Context می‌سازد، نام `x` را در Environment Record ثبت می‌کند (با مقدار `undefined`)، سپس شروع به اجرای خط‌به‌خط کد اصلی می‌کند.

---

## 2. JavaScript قبل از بررسی Hoisting

برای درک Hoisting، باید تفاوت ۳ مفهوم حیاتی را بدانید:

### 2.1 تا 2.4 مفاهیم پایه
*   **Source Code:** کد متنی که شما می‌نویسید.
*   **Parsing:** Engine کد را می‌خواند و به AST (درخت نحو انتزاعی) تبدیل می‌کند.
*   **Execution:** اجرای دستور به دستور کد.
*   **JavaScript Engine:** نرم‌افزاری (مثل V8 در کروم) که کد را اجرا می‌کند.

### 2.5 تا 2.7 Execution Context
هر بار که کدی اجرا می‌شود، یک **Execution Context** (زمینه اجرا) ساخته می‌شود.
*   **Global EC:** زمینه اجرای کل فایل.
*   **Function EC:** زمینه اجرای داخل یک تابع.

### 2.8 تا 2.10 Scope و Environment
*   **Scope:** محدوده‌ای که یک متغیر قابل دسترسی است.
*   **Lexical Scope:** Scope بر اساس مکان فیزیکی کد در فایل تعیین می‌شود.
*   **Environment:** ساختاری که متغیرها و مقادیرشان را نگه می‌دارد.

### 2.11 تا 2.13 تفاوت Declaration، Initialization و Assignment
این مهم‌ترین بخش برای درک Hoisting است:

```javascript
var x;       // 1. Declaration (اعلان): ثبت نام x در حافظه
x = 10;      // 2. Initialization (مقداردهی اولیه): اولین باری که مقداری به آن می‌دهیم
x = 20;      // 3. Assignment (تخصیص): تغییر مقدار یک متغیر از قبل تعریف شده
```
> ⚠️ **Hoisting فقط و فقط Declaration را شامل می‌شود.** مقداردهی (Initialization/Assignment) سر خط خودش انجام می‌شود.

---

## 3. Hoisting و Execution Context

وقتی یک تابع یا اسکریپت اجرا می‌شود، Engine دو مرحله را طی می‌کند (این یک مدل آموزشی است):

### 3.1 Creation Phase (مرحله ساخت)
Engine کد را اسکن می‌کند. هر `var` یا `function declaration` که می‌بیند را در **Environment Record** ثبت می‌کند (Hoisting در همین لحظه رخ می‌دهد).

### 3.2 Execution Phase (مرحله اجرا)
Engine خط به خط کد شما را اجرا می‌کند و مقادیر را تخصیص می‌دهد.

### 3.3 تا 3.6 مفاهیم پیشرفته Environment
*   **Variable Environment:** بخشی از EC که متغیرهای `var` را نگه می‌دارد.
*   **Lexical Environment:** ساختاری که Scope و زنجیره Scopeها را مدیریت می‌کند.
*   **Environment Record:** جدولی (مثل یک آبجکت) که نام متغیرها (Bindings) و مقادیرشان را ذخیره می‌کند.

### 3.7 و 3.8 مثال مرحله‌به‌مرحله
```javascript
console.log(name); // خروجی: undefined
var name = "Ali";
```
**اتفاق واقعی در Engine:**
1.  **Creation Phase:** نام `name` در Environment Record ثبت می‌شود. مقدار پیش‌فرض `undefined` به آن داده می‌شود.
2.  **Execution Phase:**
    *   خط ۱: `console.log(name)` -> مقدار `name` را می‌خواند (`undefined`).
    *   خط ۲: `name = "Ali"` -> مقدار `name` تغییر می‌کند.

---

## 4. Hoisting در var

### 4.1 تا 4.5 رفتار var
متغیرهای `var` **Declaration Hoisting** دارند. یعنی نام آن‌ها به بالای Scope می‌رود و مقدارشان `undefined` می‌شود.

```javascript
console.log(x); // خروجی: undefined
var x = 10;
```
**مدل ذهنی برای درک:**
```javascript
var x;            // Hoisted & Initialized to undefined
console.log(x);   // undefined
x = 10;           // Assignment happens here
```

### 4.6 چرا نتیجه undefined است؟
چون Engine نام `x` را می‌شناسد (خطای ReferenceError نمی‌دهد)، اما هنوز به خط `x = 10` نرسیده است، پس مقدار پیش‌فرض `undefined` را برمی‌گرداند.

---

## 5. تفاوت Declaration و Initialization در var

```javascript
// حالت ۱
var x;
console.log(x); // undefined (اعلان شده، مقداردهی نشده)

// حالت ۲
console.log(x); // undefined (اعلان Hoist شده، مقداردهی نشده)
var x = 10;

// حالت ۳
console.log(x); // undefined (اعلان Hoist شده، مقداردهی در خط بعد)
var x;
x = 10;
```
**نتیجه:** در هر سه حالت، اگر قبل از مقداردهی دسترسی داشته باشیم، `undefined` است.

---

## 6. Hoisting در Function Declaration

### 6.1 تا 6.3 رفتار توابع
توابعی که به صورت **Declaration** تعریف می‌شوند، **کامل** Hoist می‌شوند (هم نام و هم بدنه تابع).

```javascript
sayHello(); // خروجی: Hello

function sayHello() {
    console.log("Hello");
}
```
**چرا کار می‌کند؟** چون در Creation Phase، کل تابع در حافظه ثبت می‌شود.

### 6.4 تا 6.8 Scope و Strict Mode
*   **Global/Function Scope:** توابع کاملاً Hoist می‌شوند.
*   **Block Scope (غیر Strict):** در مرورگرها، توابع داخل `if` یا `{}` گاهی به Scope بیرونی Hoist می‌شدند (رفتار قدیمی و خطرناک).
*   **Strict Mode / Module:** توابع داخل Block، **فقط در همان Block** معتبرند و Hoist نمی‌شوند.

---

## 7. Function Declaration در برابر Function Expression

این یکی از مهم‌ترین تفاوت‌هاست:

```javascript
// ۱. Function Declaration (کار می‌کند)
sayHello(); // Hello
function sayHello() { console.log("Hello"); }

// ۲. Function Expression با var (خطا می‌دهد)
sayHello(); // TypeError: sayHello is not a function
var sayHello = function () { console.log("Hello"); };
// دلیل: فقط var Hoist شده (undefined)، نه مقدار تابع.

// ۳. Function Expression با let (خطا می‌دهد)
sayHello(); // ReferenceError: Cannot access 'sayHello' before initialization
let sayHello = function () { console.log("Hello"); };
// دلیل: در TDZ است.

// ۴. Function Expression با const (خطا می‌دهد)
sayHello(); // ReferenceError
const sayHello = function () { console.log("Hello"); };
```

---

## 8. Hoisting در Arrow Function

Arrow Functionها توابع خاصی برای Hoisting ندارند. آن‌ها دقیقاً مثل **Function Expression** رفتار می‌کنند و به متغیری که به آن اختصاص داده شده‌اند وابسته‌اند.

```javascript
hello(); // TypeError (با var) یا ReferenceError (با let/const)
const hello = () => console.log("Hello");
```

---

## 9. Hoisting در let

### 9.1 و 9.2 آیا let Hoist می‌شود؟
**بله!** این یک اشتباه رایج است که بگوییم `let` Hoist نمی‌شود. اگر Hoist نمی‌شد، JavaScript باید آن را یک متغیر کاملاً تعریف‌نشده (Undeclared) می‌دید و خطای `x is not defined` می‌داد. اما خطای متفاوتی می‌دهد که نشان می‌دهد نام آن را می‌شناسد!

### 9.3 تا 9.6 Temporal Dead Zone (TDZ)
`let` و `const` Hoist می‌شوند (نامشان ثبت می‌شود)، اما **مقداردهی اولیه (Initialization) نمی‌شوند**. فاصله بین شروع Scope تا خط Declaration، **TDZ** نام دارد.

```javascript
console.log(x); // ReferenceError: Cannot access 'x' before initialization
let x = 10;
```
**دلیل:** نام `x` در Environment Record ثبت شده، اما در حالت `uninitialized` است. دسترسی به آن در TDZ خطای `ReferenceError` دارد.

---

## 10. Temporal Dead Zone (TDZ)

### 10.1 تا 10.6 تعریف TDZ
TDZ منطقه‌ای است از شروع Block تا خطی که `let` یا `const` مقداردهی می‌شوند.
*   برای `let`، `const` و `class` وجود دارد.
*   دسترسی در TDZ باعث `ReferenceError` می‌شود.

### 10.7 تا 10.10 TDZ و typeof
```javascript
console.log(typeof y); // "undefined" (متغیر اصلا وجود ندارد)
console.log(typeof x); // ReferenceError! (متغیر وجود دارد اما در TDZ است)
let x = 10;
```
> 💡 **نکته طلایی:** اپراتور `typeof` فقط برای متغیرهای **کاملاً تعریف‌نشده** امن است. برای متغیرهای `let/const` در TDZ، خطا می‌دهد.

---

## 11. Hoisting در const

رفتار `const` دقیقاً مانند `let` است (Hoist می‌شود، TDZ دارد).
**تفاوت:** `const` حتماً باید در همان خط Declaration مقداردهی شود، وگرنه SyntaxError می‌دهد.

```javascript
console.log(x); // ReferenceError (TDZ)
const x = 10;
```

---

## 12. مقایسه var و let و const

| ویژگی | `var` | `let` | `const` |
| :--- | :--- | :--- | :--- |
| **Scope** | Function / Global | Block | Block |
| **Hoisting** | بله (با مقدار `undefined`) | بله (بدون مقداردهی) | بله (بدون مقداردهی) |
| **مقدار قبل از Declaration** | `undefined` | `ReferenceError` (TDZ) | `ReferenceError` (TDZ) |
| **TDZ** | ندارد | دارد | دارد |
| **Initialization اجباری** | خیر | خیر | **بله** |
| **Re-declaration** | مجاز | **ممنوع** | **ممنوع** |
| **Re-assignment** | مجاز | مجاز | **ممنوع** |
| **Global Object Property** | بله (در مرورگر `window.x`) | خیر | خیر |

---

## 13. Hoisting و Scope

Hoisting به Scope وابسته است. `var` فقط در Function Scope یا Global Scope Hoist می‌شود.

```javascript
var x = 10;
function test() {
    console.log(x); // undefined
    var x = 20;
}
test();
```
**دلیل:** `var x = 20` در داخل تابع Hoist می‌شود و متغیر `x` محلی را می‌سازد (Shadowing). بنابراین `x` بیرونی (10) دیده نمی‌شود و چون هنوز به خط 20 نرسیده‌ایم، `undefined` است.

---

## 14. Shadowing و Hoisting

```javascript
let x = 10;
{
    console.log(x); // ReferenceError (TDZ)
    let x = 20;
}
```
**توضیح:** `let x = 20` یک Scope جدید می‌سازد و `x` بیرونی را Shadow می‌کند. اما چون در TDZ است، خطا می‌دهد.

---

## 15. Hoisting در کلاس‌ها (Classes)

کلاس‌ها دقیقاً مانند `let` و `const` رفتار می‌کنند (Hoist می‌شوند اما در TDZ هستند).

```javascript
const user = new User(); // ReferenceError: Cannot access 'User' before initialization
class User {}
```
**دلیل:** جلوگیری از باگ‌هایی که ممکن است قبل از تعریف کامل کلاس (و متدهای آن) رخ دهد.

---

## 16. Hoisting در import و export

دستورات `import` **قبل از هر کد دیگری** در ماژول Hoist و اجرا می‌شوند.

```javascript
console.log(myVar); // کار می‌کند
import { myVar } from './module.js';
```
**دلیل:** Engine باید ابتدا وابستگی‌ها را resolve و execute کند تا ماژول فعلی بتواند از آن‌ها استفاده کند.

---

## 17 و 18. Hoisting در Parameters و Default Parameters

پارامترهای تابع یک Scope مخصوص به خود دارند.

```javascript
function test(a = b, b = 10) {
    console.log(a);
}
test(); // ReferenceError: Cannot access 'b' before initialization
```
**دلیل:** پارامترها در یک TDZ داخلی قرار دارند. `a` نمی‌تواند به `b` که هنوز مقداردهی نشده ارجاع دهد.

---

## 19. Hoisting و Destructuring

Destructuring تابعی از `var`، `let` یا `const` است و همان قوانین را دارد.

```javascript
console.log(a); // ReferenceError
const { a } = { a: 10 };
```

---

## 20 و 21. Hoisting، Closures و Loops

مشهورترین مثال Hoisting و Scope:

```javascript
// با var
for (var i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100);
}
// خروجی: 3, 3, 3
// دلیل: var فقط یک بار در Scope بیرونی Hoist می‌شود. Closureها به همان یک متغیر مشترک اشاره می‌کنند.

// با let
for (let i = 0; i < 3; i++) {
    setTimeout(() => console.log(i), 100);
}
// خروجی: 0, 1, 2
// دلیل: let در هر Iteration یک Binding جدید می‌سازد. Closureها به متغیرهای مجزای هر دور حلقه اشاره می‌کنند.
```

---

## 22 و 23. Hoisting در Block و Conditionals

```javascript
if (true) {
    var x = 10;
}
console.log(x); // 10 (چون var Block Scope ندارد و به Global/Function Hoist شده)

if (true) {
    let y = 20;
}
console.log(y); // ReferenceError (چون let Block Scope دارد و خارج از Block در دسترس نیست)
```

---

## 24. Hoisting در Nested Functions

Function Declarations فقط تا **Function Scope** بیرونی خود Hoist می‌شوند، نه Global.

```javascript
function outer() {
    inner(); // Hello
    function inner() { console.log("Hello"); }
}
outer();
console.log(inner); // ReferenceError (inner در Global وجود ندارد)
```

---

## 25. ترتیب Hoisting (توابع در برابر var)

اگر هم نام `function` و هم `var` داشته باشیم:
1. **Function Declarations** اول Hoist می‌شوند.
2. **var Declarations** دوم Hoist می‌شوند (اگر نام تکراری باشد، نادیده گرفته می‌شود).
3. **Assignmentها** به ترتیب اجرا می‌شوند.

```javascript
console.log(foo); // function foo() {}
var foo = 10;
function foo() { console.log("function"); }
console.log(foo); // 10
```
**توضیح:** ابتدا تابع `foo` ثبت می‌شود. سپس `var foo` به دلیل تکراری بودن نادیده گرفته می‌شود. در مرحله اجرا، `foo = 10` مقدار تابع را با عدد جایگزین می‌کند.

---

## 26. Hoisting و Redeclaration

```javascript
var x = 10; var x = 20; // مجاز
let y = 10; let y = 20; // SyntaxError: Identifier 'y' has already been declared
var z = 10; let z = 20; // SyntaxError (تداخل var و let در یک Scope)
```

---

## 27. Hoisting و Global Scope

در مرورگر، `var`های Global به `window` متصل می‌شوند. `let` و `const` خیر.

```javascript
var a = 1; let b = 2; const c = 3;
console.log(window.a); // 1
console.log(window.b); // undefined
```

---

## 28. Browser و Node.js

*   **Browser Script:** همان قوانین بالا.
*   **Node.js CommonJS:** هر فایل در یک تابع (IIFE)包裹 می‌شود. پس `var`های فایل به `global` متصل نمی‌شوند، بلکه Function Scope دارند.
*   **ES Modules:** همیشه در Strict Mode هستند.

---

## 29. Hoisting و Strict Mode

در Strict Mode، توابع داخل Block دیگر به Scope بیرونی Hoist نمی‌شوند (Block-scoped می‌شوند).

```javascript
"use strict";
if (true) {
    function myFunc() { console.log("Hello"); }
}
myFunc(); // ReferenceError
```

---

## 30 و 31. typeof و Errorها

*   **ReferenceError:** دسترسی به متغیر در TDZ یا متغیر تعریف‌نشده.
*   **SyntaxError:** Redeclaration با `let/const`.
*   **TypeError:** تلاش برای فراخوانی `undefined` به عنوان تابع.

```javascript
console.log(typeof notDefined); // "undefined" (امن)
console.log(typeof inTDZ);      // ReferenceError (ناامن)
let inTDZ = 10;
```

---

## 32. اشتباهات رایج درباره Hoisting

1.  ❌ *JS کد را به بالا منتقل می‌کند.* ✅ **غلط.** Engine Environment را قبل از اجرا می‌سازد.
2.  ❌ *let و const Hoist نمی‌شوند.* ✅ **غلط.** Hoist می‌شوند اما در TDZ هستند.
3.  ❌ *Function Expression ها Hoist می‌شوند.* ✅ **غلط.** فقط Declaration ها.
4.  ❌ *Hoisting یعنی Scope.* ✅ **غلط.** Hoisting زمان ثبت نام است، Scope محدوده دسترسی است.
5.  ❌ *undefined یعنی متغیر وجود ندارد.* ✅ **غلط.** یعنی ثبت شده اما مقداردهی نشده.
6.  ❌ *class ها Hoist نمی‌شوند.* ✅ **غلط.** Hoist می‌شوند ولی در TDZ هستند.
7.  ❌ *var داخل Block Scope دارد.* ✅ **غلط.** Function/Global Scope دارد.
8.  ❌ *typeof برای TDZ امن است.* ✅ **غلط.** خطای ReferenceError می‌دهد.
9.  ❌ *Hoisting فقط برای متغیرهاست.* ✅ **غلط.** برای توابع و کلاس‌ها هم هست.
10. ❌ *در حلقه for، let مثل var رفتار می‌کند.* ✅ **غلط.** let در هر دور حلقه Binding جدید می‌سازد.

---

## 33 و 34. سوالات مصاحبه و خروجی کد

**سوال ۱:**
```javascript
❓ خروجی چیست؟
var a = 1;
function b() {
    a = 10;
    return;
    function a() {}
}
b();
console.log(a);
```
✅ **پاسخ:** `1`
**دلیل:** `function a()` داخل تابع `b` Hoist می‌شود و یک متغیر محلی `a` می‌سازد. `a = 10` متغیر محلی را تغییر می‌دهد، نه Global را.

**سوال ۲:**
```javascript
❓ خروجی چیست؟
let a = 10;
function test() {
    console.log(a);
    let a = 20;
}
test();
```
✅ **پاسخ:** `ReferenceError`
**دلیل:** `let a = 20` باعث Shadowing می‌شود و `a` محلی در TDZ قرار می‌گیرد.

---

## 35. مثال‌های Trick و Edge Case

```javascript
var x = 10;
let y = 20;

{
    console.log(x); // 10
    console.log(y); // ReferenceError (TDZ)
    var x = 30;     // همان متغیر بیرونی است
    let y = 40;     // متغیر جدید Block Scope
}
```

---

## 36. Hoisting از دید JavaScript Engine

1.  **Parsing:** کد به AST تبدیل می‌شود.
2.  **Compilation:** به Bytecode تبدیل می‌شود.
3.  **Execution Context Creation:**
    *   **Lexical Environment** ساخته می‌شود.
    *   **Environment Record** (از نوع Declarative) ایجاد می‌شود.
    *   برای `var`: `CreateMutableBinding` و `InitializeBinding` با `undefined`.
    *   برای `let/const`: `CreateMutableBinding` / `CreateImmutableBinding` (بدون مقداردهی - TDZ).
4.  **Execution:** خطوط کد اجرا و `SetMutableBinding` فراخوانی می‌شود.

---

## 37. Hoisting از دید ECMAScript Specification

در Spec، مفهومی به نام Hoisting نداریم. مفاهیم معادل:
*   **Binding:** اتصال یک نام به یک مقدار در Environment.
*   **VariableDeclarationInstantiation:** فرآیندی که قبل از اجرای Function/Script، تمام `var`ها را `undefined` می‌کند.
*   **LexicalDeclaration:** فرآیند ثبت `let/const` که آن‌ها را در حالت `uninitialized` نگه می‌دارد.
*   **HoistableDeclaration:** اصطلاح Spec برای Function Declarations.

---

## 38. Hoisting واقعی در برابر مدل ذهنی

**مدل ذهنی:**
```javascript
var a;
console.log(a);
a = 5;
```
**واقعیت Engine:**
کد شما دقیقاً همان‌جایی که نوشته‌اید اجرا می‌شود. اما Engine قبل از شروع اجرا، یک جدول (Environment Record) ساخته و نام `a` را با برچسب "قابل دسترسی اما بدون مقدار" در آن قرار داده است. وقتی به خط `console.log` می‌رسد، Engine جدول را چک می‌کند، `a` را می‌یابد و چون مقداری ندارد، `undefined` برمی‌گرداند.

---

## 39 و 40. تفاوت مفاهیم

| مفهوم | تعریف |
| :--- | :--- |
| **Hoisting** | ثبت نام متغیر/تابع در Environment قبل از اجرای خطی. |
| **Scope** | قوانین تعیین‌کننده اینکه متغیر از کجا قابل دسترسی است. |
| **TDZ** | بازه زمانی بین ثبت نام `let/const` تا مقداردهی آن‌ها. |
| **Execution Context** | محیطی که کد در آن اجرا می‌شود (شامل Scope و Environment). |
| **Closure** | توانایی یک تابع در به یاد آوردن Scope خود حتی پس از اتمام اجرای Scope بیرونی. |

---

## 41. Hoisting و Best Practices

1.  **هرگز به Hoisting تکیه نکنید.** همیشه متغیرها را قبل از استفاده Declare کنید.
2.  **از `var` استفاده نکنید.** فقط `let` و `const`.
3.  **توابع را با `const` و Arrow Function تعریف کنید** (مگر اینکه به Hoisting نیاز داشته باشید).
4.  **اعلام متغیرها در بالاترین نقطه Scope** (برای خوانایی).
5.  **از Strict Mode استفاده کنید** تا از رفتارهای عجیب Block Functions جلوگیری کنید.

---

## 42. پروژه کوچک برای تمرین

یک سیستم مدیریت تسک ساده بنویسید که:
1.  از `const` برای لیست تسک‌ها استفاده کند.
2.  توابع `addTask` و `removeTask` را با Function Declaration بنویسد (تا Hoist شوند).
3.  یک حلقه `for` با `let` برای رندر کردن تسک‌ها داشته باشد (برای درک Closure).
4.  سعی کنید عمداً یک متغیر را در TDZ صدا بزنید تا خطا را ببینید.

---

## 43. تمرین‌های عملی

**Level 1: Beginner**
1. خروجی `console.log(x); var x = 5;` چیست؟
2. تفاوت `var` و `let` در Hoisting را بنویسید.
3. آیا Arrow Function ها Hoist می‌شوند؟

**Level 2: Intermediate**
4. خروجی حلقه `for` با `var` و `setTimeout` را پیش‌بینی کنید.
5. چرا `typeof` در TDZ خطا می‌دهد؟
6. تفاوت Function Declaration و Expression در Hoisting چیست؟

**Level 3: Advanced**
7. رفتار `class` در Hoisting را با `function` مقایسه کنید.
8. در Spec، `VariableDeclarationInstantiation` چه می‌کند؟
9. چرا `import` ها قبل از کد اجرا می‌شوند؟
10. خروجی کد ترکیبی Shadowing و TDZ را تحلیل کنید.

*(پاسخ‌ها را می‌توانید با اجرای کدها در Console مرورگر بررسی کنید)*

---

## 44. Cheat Sheet

```text
var
↓
Declaration Hoisted (Initialized to undefined)
↓
Accessible before declaration (returns undefined)

let / const
↓
Declaration Hoisted (Uninitialized)
↓
TDZ starts
↓
ReferenceError if accessed in TDZ
↓
TDZ ends at declaration line

function declaration
↓
Fully Hoisted (Name + Body)
↓
Accessible before declaration

function expression / class
↓
Follows the variable declaration rules (var/let/const)
```

---

## 45. جدول نهایی رفتار Hoisting

| Declaration | Hoisting Behavior | Before Declaration | TDZ | Scope |
| :--- | :--- | :--- | :--- | :--- |
| `var` | Declaration Only | `undefined` | ❌ No | Function / Global |
| `let` | Declaration Only | `ReferenceError` | ✅ Yes | Block |
| `const` | Declaration Only | `ReferenceError` | ✅ Yes | Block |
| `function` | Full (Name + Body) | Callable | ❌ No | Block (Strict) / Function |
| `class` | Declaration Only | `ReferenceError` | ✅ Yes | Block |
| `import` | Fully Hoisted | Available | ❌ No | Module |

---

## 46. نقشه یادگیری Hoisting

```text
JavaScript Basics
       ↓
Variables (var, let, const)
       ↓
Declaration vs Initialization vs Assignment
       ↓
Scope (Global, Function, Block)
       ↓
Execution Context (Creation & Execution Phase)
       ↓
Hoisting (Mental Model vs Engine Reality)
       ↓
TDZ (Temporal Dead Zone)
       ↓
Functions (Declaration vs Expression)
       ↓
Classes & Modules
       ↓
Closures & Loops
       ↓
JavaScript Engine & ECMAScript Spec
```

---

## 48. منابع معتبر

برای مطالعه عمیق‌تر، منابع زیر پیشنهاد می‌شوند:

### منابع رسمی
*   **[MDN Web Docs: Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)** - بهترین مرجع برای درک مفاهیم پایه و رفتارهای استاندارد.
*   **[MDN: var, let, const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)** - مستندات رسمی دستورات متغیرها.
*   **[ECMAScript Specification (TC39)](https://tc39.es/ecma262/)** - مرجع نهایی و رسمی (بخش‌های *Executable Code and Execution Contexts* و *Ordinary and Exotic Objects Behaviors*).

### مقالات و ویدیوهای آموزشی معتبر
*   **[JavaScript Visualized: Execution Context & Hoisting](https://dev.to/lydiahallie/javascript-visualized-execution-contexts-hoisting-scopes-closures-5g46)** - مقاله عالی از Lydia Hallie با تصویرسازی.
*   **[You Don't Know JS Yet: Scope & Closures](https://github.com/getify/You-Dont-Know-JS)** - کتاب رایگان و بی‌نظیر Kyle Simpson (بخش Hoisting).

---

> 🎯 **جمع‌بندی نهایی برای به خاطر سپردن:**
> Hoisting یعنی **ثبت نام‌ها قبل از اجرا**.
> `var` ثبت می‌شود و `undefined` می‌گیرد.
> `let/const/class` ثبت می‌شوند اما **قفل (TDZ)** می‌مانند تا به خطشان برسیم.
> `function` کامل ثبت می‌شود.
> **هرگز کد جابه‌جا نمی‌شود؛ این Engine است که حافظه را آماده می‌کند.**

---
*تهیه شده برای جامعه برنامه‌نویسان JavaScript | 📅 آخرین بروزرسانی: 2026*
