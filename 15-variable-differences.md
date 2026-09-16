# 22. منابع معتبر

در پایان محتوا، بخشی با عنوان **منابع معتبر** ایجاد کن.

از منابع رسمی و معتبر استفاده کن، مانند:

* MDN Web Docs
* ECMAScript Language Specification (ECMA-262)
* مستندات رسمی JavaScript در صورت نیاز

برای هر منبع:

* عنوان صفحه
* نام وب‌سایت
* لینک مستقیم و معتبر
* توضیح کوتاه دربارهٔ اینکه کدام بخش از آموزش بر اساس آن منبع تهیه شده است

**از لینک‌های ساختگی، لینک‌های نامعتبر یا لینک‌های کلی بدون ارتباط مستقیم با موضوع استفاده نکن.**

منابع پیشنهادی اولیه:

* [MDN — let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
* [MDN — const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
* [MDN — var](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)
* [MDN — Variables](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Variables)
* [MDN — Grammar and types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types)
* [ECMAScript Specification — Let and Const Declarations](https://tc39.es/ecma262/2026/multipage/ecmascript-language-statements-and-declarations.html)

---


* خروجی را با یک عنوان مناسب Markdown شروع کن.
* فهرست مطالب را در ابتدای محتوا قرار بده.
* برای فهرست مطالب، لینک‌های داخلی معتبر Markdown ایجاد کن.
* عنوان‌ها را با ساختار `#`، `##` و `###` مرتب کن.
* از کدبلاک‌های مشخص با زبان `javascript` استفاده کن.
* خروجی کدها را با توضیح مشخص کن.
* جدول‌ها باید خوانا باشند و در موبایل نیز تا حد امکان قابل استفاده باشند.
* از ایموجی فقط در صورت نیاز و به‌صورت محدود استفاده کن.
* محتوا باید مناسب قرار گرفتن در یک فایل مانند `let-var-const.md` باشد.
* متن را بیش‌ازحد فشرده نکن؛ خوانایی برای مبتدی اولویت دارد.
* در عین سادگی، دقت فنی را حفظ کن.
* هرجا بین رفتار محیط‌های مختلف تفاوت وجود دارد، آن را مشخص کن.
* از ادعاهای نادرست مانند «`let` و `const` اصلاً Hoist نمی‌شوند» خودداری کن؛ مفهوم را دقیق توضیح بده.
* در پایان، منابع را جداگانه و با لینک‌های معتبر فهرست کن.
* **هیچ بخش اصلی از فهرست بالا را حذف نکن.**


### ASSISTANT
# راهنمای جامع متغیرها در JavaScript: آموزش `let`، `var` و `const` از مقدماتی تا پیشرفته

## فهرست مطالب
1. [مقدمه](#1-مقدمه)
2. [مفاهیم پایهٔ تعریف متغیر](#2-مفاهیم-پایهٔ-تعریف-متغیر)
3. [آموزش `let` از مقدماتی تا پیشرفته](#3-آموزش-let-از-مقدماتی-تا-پیشرفته)
4. [آموزش `const` از مقدماتی تا پیشرفته](#4-آموزش-const-از-مقدماتی-تا-پیشرفته)
5. [آموزش `var` از مقدماتی تا پیشرفته](#5-آموزش-var-از-مقدماتی-تا-پیشرفته)
6. [Scope در JavaScript](#6-scope-در-javascript)
7. [Hoisting](#7-hoisting)
8. [Temporal Dead Zone (TDZ)](#8-temporal-dead-zone-tdz)
9. [مقایسهٔ کامل `var`، `let` و `const`](#9-مقایسهٔ-کامل-var-let-و-const)
10. [تفاوت `const` با Immutable Value](#10-تفاوت-const-با-immutable-value)
11. [استفاده از `let` و `const` در حلقه‌ها](#11-استفاده-از-let-و-const-در-حلقه‌ها)
12. [`let`، `const` و Closure](#12-let-const-و-closure)
13. [`let` و `const` در Destructuring](#13-let-و-const-در-destructuring)
14. [`let` و `const` در Modules](#14-let-و-const-در-modules)
15. [ارتباط با Global Object](#15-ارتباط-با-global-object)
16. [خطاهای رایج و دام‌های مهم](#16-خطاهای-رایج-و-دام‌های-مهم)
17. [بهترین روش‌های استفاده در JavaScript مدرن](#17-بهترین-روش‌های-استفاده-در-javascript-مدرن)
18. [مثال‌های عملی و پروژه‌محور](#18-مثال‌های-عملی-و-پروژه‌محور)
19. [تمرین‌ها](#19-تمرین‌ها)
20. [پرسش‌های متداول (FAQ)](#20-پرسش‌های-متداول-faq)
21. [جمع‌بندی نهایی](#21-جمع‌بندی-نهایی)
22. [منابع معتبر](#22-منابع-معتبر)

---

## 1. مقدمه

### 1.1 متغیر چیست؟
متغیر (Variable) در برنامه‌نویسی مانند یک «جعبهٔ برچسب‌دار» است که مقداری را در خود نگه می‌دارد. ما به این جعبه یک نام می‌دهیم تا بعداً بتوانیم مقدار درون آن را پیدا کنیم، بخوانیم یا تغییر دهیم.
* **مثال روزمره**: تصور کنید یک جعبه دارید که روی آن نوشته‌اید «سن». داخل این جعبه عدد ۲۵ را قرار می‌دهید. هر وقت بپرسید «داخل جعبهٔ سن چیست؟»، پاسخ ۲۵ خواهد بود.

### 1.2 چرا در JavaScript به متغیر نیاز داریم؟
* **نگهداری داده**: ذخیرهٔ اطلاعاتی مثل نام کاربر یا امتیاز بازی.
* **استفادهٔ مجدد**: به جای تایپ مکرر یک مقدار، یک بار آن را در متغیر ذخیره و بارها استفاده می‌کنیم.
* **تغییر داده‌ها**: به‌روزرسانی مقادیر در طول اجرای برنامه (مثل کم شدن جان بازیکن).
* **منطق برنامه**: استفاده در محاسبات ریاضی، شرط‌ها و حلقه‌ها.

### 1.3 معرفی `var`، `let` و `const`
این‌ها سه کلمهٔ کلیدی (Keyword) در JavaScript برای تعریف متغیر هستند:
* `var`: روش قدیمی تعریف متغیر (دارای مشکلاتی در مدیریت Scope).
* `let`: روش مدرن برای متغیرهایی که مقدارشان تغییر می‌کند.
* `const`: روش مدرن برای مقادیری که قرار است ثابت بمانند (Constant).
وجود سه روش به دلیل تکامل زبان JavaScript در طول زمان است.

### 1.4 تاریخچهٔ کوتاه
* در گذشته، فقط `var` وجود داشت که رفتارهای غیرمنتظره‌ای (مثل نشت به Scope بیرونی) داشت.
* در سال ۲۰۱۵، استاندارد **ECMAScript 2015 (ES6)** معرفی شد و `let` و `const` را برای حل مشکلات `var` و ایجاد کد قابل‌پیش‌بینی‌تر اضافه کرد.
* امروزه در JavaScript مدرن، تقریباً به‌طور کامل از `let` و `const` استفاده می‌شود و `var` منسوخ (Deprecated) در نظر گرفته می‌شود.

---

## 2. مفاهیم پایهٔ تعریف متغیر

### 2.1 Declaration (اعلام) چیست؟
اعلام متغیر یعنی به موتور JavaScript می‌گوییم: «یک متغیر با این نام وجود دارد».
```js
let age; // اعلام متغیر age
```

### 2.2 Initialization (مقداردهی اولیه) چیست؟
اختصاص دادن اولین مقدار به متغیر در لحظهٔ تعریف.
```js
let age = 25; // اعلام و مقداردهی اولیه به صورت همزمان
```

### 2.3 Assignment (انتساب) چیست؟
دادن مقدار به یک متغیر (چه برای اولین بار و چه بعد از آن).
```js
age = 25; // انتساب مقدار ۲۵ به متغیر age
```

### 2.4 Reassignment (انتساب مجدد) چیست؟
تغییر مقدار متغیری که قبلاً مقداری داشته است.
```js
let score = 10;
score = 20; // انتساب مجدد (مقدار قبلی با ۲۰ جایگزین شد)
```

### 2.5 مثال ترکیبی
```js
let userName;          // 1. Declaration (اعلام)
userName = "Ali";      // 2. Initialization & Assignment (مقداردهی اولیه و انتساب)
let score = 0;         // 3. Declaration + Initialization در یک خط
score = 10;            // 4. Reassignment (انتساب مجدد)
```

---

## 3. آموزش `let` از مقدماتی تا پیشرفته

### 3.1 `let` چیست؟
`let` کلمهٔ کلیدی برای تعریف متغیری است که **مقدار آن می‌تواند در آینده تغییر کند** و فقط در **Block Scope** (محدودهٔ بلوک) قابل دسترسی است.

### 3.2 تعریف `let` بدون مقدار اولیه
```js
let age;
console.log(age); // خروجی: undefined
```
* **مقدار اولیه**: مقداری که هنگام تعریف به متغیر می‌دهیم.
* **چرا `undefined` است؟**: چون متغیر اعلام شده اما هنوز مقداری به آن انتساب نیافته است.

### 3.3 تعریف `let` همراه با مقدار
```js
let age = 25;
console.log(age); // خروجی: 25
```

### 3.4 تغییر مقدار متغیر `let`
```js
let score = 10;
score = 20;
console.log(score); // خروجی: 20
```

### 3.5 تغییر نوع مقدار در `let`
```js
let value = 10;
value = "Hello";
console.log(value); // خروجی: "Hello"
```
* **ارتباط با Dynamic Typing**: JavaScript یک زبان با تایپ پویا (Dynamic Typing) است، یعنی نوع دادهٔ متغیر در زمان اجرا تعیین می‌شود و می‌تواند تغییر کند.

### 3.6 تعریف چند متغیر با `let`
```js
let a = 1, b = 2, c = 3;
let x, y, z; // اعلام چند متغیر بدون مقدار
```

### 3.7 قوانین نام‌گذاری متغیرها
* **معتبر**: شروع با حرف، `$` یا `_`. شامل حروف، اعداد، `$` و `_`. (مثال: `userName`, `_count`, `$price`)
* **نامعتبر**: شروع با عدد یا استفاده از کاراکترهای خاص مثل `-` یا فاصله. (مثال: `1stPlace`, `my-name`)
* **Case Sensitivity**: `userName` و `Username` دو متغیر کاملاً متفاوت هستند.
* **کلمات کلیدی**: نمی‌توان از کلماتی مثل `let`, `const`, `function` به عنوان نام متغیر استفاده کرد.

### 3.8 خطاهای رایج در استفاده از `let`
1. **استفاده قبل از تعریف**: باعث خطای `ReferenceError` می‌شود (به دلیل TDZ).
2. **تعریف مجدد در یک Scope**: `let x = 1; let x = 2;` باعث خطای `SyntaxError` می‌شود.
3. **استفاده از نام نامعتبر**: `let 123abc = 5;` باعث خطای `SyntaxError` می‌شود.

---

## 4. آموزش `const` از مقدماتی تا پیشرفته

### 4.1 `const` چیست؟
`const` (مخفف Constant) برای تعریف متغیری استفاده می‌شود که **قرار نیست مقدارش تغییر کند**. این متغیر نیز Block Scope است.

### 4.2 الزام مقداردهی اولیه
```js
const pi = 3.14;
```
* **چرا بدون مقدار اولیه مجاز نیست؟**: چون فلسفهٔ `const` ثابت بودن است. اگر مقداری ندهید، موتور JavaScript نمی‌تواند آن را «ثابت» در نظر بگیرد و خطای `SyntaxError: Missing initializer in const declaration` می‌دهد.

### 4.3 تلاش برای تغییر مقدار `const`
```js
const age = 25;
age = 30; // خطا: TypeError: Assignment to constant variable.
```
* **دلیل خطا**: موتور JavaScript اجازهٔ Reassignment (انتساب مجدد) به متغیری که با `const` تعریف شده را نمی‌دهد.

### 4.4 آیا `const` واقعاً ثابت است؟
**خیر، لزوماً.** `const` فقط **Binding** (اتصال نام متغیر به مقدار) را ثابت می‌کند، نه خود مقدار را (در صورتی که مقدار از نوع Reference مثل Object یا Array باشد).

### 4.5 تفاوت Reassignment و Mutation
* **Reassignment**: تغییر کامل مقدار متغیر (مثلاً `x = 5` به `x = 10`). در `const` ممنوع است.
* **Mutation**: تغییر محتوای داخلی یک Object یا Array بدون تغییر خود متغیر. در `const` **مجاز** است.

### 4.6 `const` و Primitive Values
برای مقادیر اولیه (Primitive) مثل `Number`, `String`, `Boolean`, `null`, `undefined`، مقدار ذاتاً غیرقابل تغییر (Immutable) است. بنابراین `const` آن‌ها را کاملاً ثابت نگه می‌دارد.
```js
const name = "Ali";
// name = "Reza"; // خطا
```

### 4.7 `const` و Object
```js
const user = { name: "Ali" };
user.name = "Reza"; // مجاز! (Mutation)
console.log(user.name); // خروجی: "Reza"

// user = { name: "Sara" }; // خطا! (Reassignment ممنوع است)
```
* **چرا تغییر Property مجاز است؟**: چون آدرس حافظهٔ Object تغییر نکرده، فقط محتوای داخلی آن تغییر کرده است.
* **چرا انتساب Object جدید مجاز نیست؟**: چون سعی داریم آدرس حافظهٔ جدیدی را به متغیر `user` متصل کنیم که Reassignment محسوب می‌شود.

### 4.8 `const` و Array
```js
const numbers = [1, 2, 3];
numbers.push(4); // مجاز! آرایه تغییر می‌کند.
console.log(numbers); // خروجی: [1, 2, 3, 4]

// numbers = [5, 6]; // خطا!
```

### 4.9 آیا می‌توان Object یا Array را واقعاً Immutable کرد؟
بله، با استفاده از `Object.freeze()`.
```js
const user = Object.freeze({ name: "Ali" });
user.name = "Reza"; // در حالت Strict Mode خطا می‌دهد، در غیر این صورت بی‌اثر است.
```
* **محدودیت**: `Object.freeze()` سطحی (Shallow) است. اگر Object تو در تو باشد، Propertyهای داخلی آن هنوز قابل تغییر هستند. برای ثابت کردن کامل (Deep Freeze) نیاز به توابع بازگشتی سفارشی است.

### 4.10 خطاهای رایج در استفاده از `const`
* فراموش کردن مقداردهی اولیه.
* تلاش برای Reassignment.
* تصور اشتباه اینکه `const` جلوی تغییر Propertyهای Object را می‌گیرد.

---

## 5. آموزش `var` از مقدماتی تا پیشرفته

### 5.1 `var` چیست؟
روش قدیمی تعریف متغیر در JavaScript که دارای **Function Scope** (و Global Scope) است و رفتار Hoisting آن با `let`/`const` متفاوت است.

### 5.2 تعریف `var` بدون مقدار اولیه
```js
var age;
console.log(age); // undefined
```

### 5.3 تغییر مقدار `var`
```js
var score = 10;
score = 20; // کاملاً مجاز
```

### 5.4 تعریف مجدد متغیر با `var`
```js
var name = "Ali";
var name = "Reza"; // مجاز است! مقدار قبلی بازنویسی می‌شود.
```
* **چرا مشکل‌ساز است؟**: چون ممکن است به‌طور تصادفی متغیری را که قبلاً تعریف کرده‌اید بازنویسی کنید و موتور JavaScript هیچ هشداری ندهد که منجر به باگ‌های سخت‌پیدا می‌شود.

### 5.5 تفاوت `var` با `let` در تعریف مجدد
* `var`: اجازهٔ Redeclaration (تعریف مجدد) در یک Scope را می‌دهد.
* `let`: اجازهٔ Redeclaration در یک Scope را **نمی‌دهد** و خطای `SyntaxError` می‌دهد.

### 5.6 `var` در JavaScript قدیمی
قبلاً تنها راه تعریف متغیر بود. مشکلاتی مثل نشت متغیر از حلقه‌ها و بلوک‌ها (Block Scope نداشتن) و Hoisting گیج‌کننده، باعث شد جامعهٔ برنامه‌نویسی درخواست استانداردی بهتر کند که منجر به معرفی `let` و `const` در ES6 شد.

### 5.7 آیا هنوز باید از `var` استفاده کنیم؟
**خیر.** در کدنویسی مدرن، استفاده از `var` توصیه نمی‌شود. فقط زمانی با آن مواجه می‌شوید که در حال نگهداری (Maintain) کدهای قدیمی (Legacy Code) باشید. همیشه از `const` یا `let` استفاده کنید.

---

## 6. Scope در JavaScript

### 6.1 Scope چیست؟
Scope (محدوده) تعیین می‌کند که یک متغیر در کدام بخش‌های کد قابل دسترسی و مشاهده است. این مفهوم برای جلوگیری از تداخل نام متغیرها و مدیریت حافظه حیاتی است.

### 6.2 Global Scope
متغیری که خارج از تمام توابع و بلوک‌ها تعریف شود. در همه جای برنامه قابل دسترسی است.

### 6.3 Function Scope
متغیری که داخل یک تابع تعریف شود، فقط درون همان تابع قابل دسترسی است. (`var`، `let` و `const` همگی این رفتار را دارند).

### 6.4 Block Scope
محدوده‌ای که با آکولاد `{}` ایجاد می‌شود (مثل داخل `if`، `for`، یا یک بلوک ساده). فقط `let` و `const` به این محدوده احترام می‌گذارند.

### 6.5 Scope در `let`
```js
{
  let message = "Hello";
}
console.log(message); // خطا: ReferenceError: message is not defined
```

### 6.6 Scope در `const`
دقیقاً مانند `let`، Block Scope دارد.

### 6.7 Scope در `var`
```js
{
  var message = "Hello";
}
console.log(message); // خروجی: "Hello" (چون var Block Scope ندارد و به بیرون نشت می‌کند)
```

### 6.8 تفاوت Function Scope و Block Scope
`var` فقط تابع را به عنوان مرز می‌شناسد، اما `{}` معمولی را نادیده می‌گیرد. `let` و `const` هم تابع و هم `{}` را به عنوان مرز می‌شناسند.

### 6.9 Scope در شرط‌ها
```js
if (true) {
  let x = 10;
  var y = 20;
}
// console.log(x); // خطا
console.log(y); // 20
```
این قاعده برای `else` و `switch` نیز به همین شکل است.

### 6.10 Scope در حلقه‌ها
```js
for (let i = 0; i < 3; i++) {
  // i فقط داخل این حلقه وجود دارد
}
// console.log(i); // خطا

for (var j = 0; j < 3; j++) {
  // j به بیرون نشت می‌کند
}
console.log(j); // 3
```

### 6.11 Scope در توابع تو‌در‌تو
تابع داخلی به متغیرهای تابع بیرونی دسترسی دارد، اما برعکس آن صادق نیست.

### 6.12 Scope Chain
وقتی به یک متغیر مراجعه می‌کنید، موتور JavaScript ابتدا در Scope فعلی جست‌وجو می‌کند. اگر پیدا نکرد، به Scope بیرونی (Parent) می‌رود و این زنجیره تا Global Scope ادامه می‌یابد.

### 6.13 Shadowing (سایه‌اندازی)
وقتی در یک Scope داخلی، متغیری با همان نام یک متغیر در Scope بیرونی تعریف می‌کنید، متغیر داخلی متغیر بیرونی را «سایه» می‌اندازد (مخفی می‌کند).
```js
let x = 10;
{
  let x = 20; // Shadowing: این x جدید، x بیرونی را مخفی می‌کند.
  console.log(x); // 20
}
console.log(x); // 10
```
* **تفاوت با Redeclaration**: در Shadowing، ما در Scopeهای **مختلف** تعریف می‌کنیم (مجاز است). در Redeclaration، در **یک Scope** دوباره تعریف می‌کنیم (برای `let`/`const` خطا است).

---

## 7. Hoisting

### 7.1 Hoisting چیست؟
Hoisting (بالا کشیدن) یک رفتار در JavaScript است که در آن **اعلام** (Declaration) متغیرها و توابع در مرحلهٔ کامپایل به بالای Scope خود منتقل می‌شود.
* **نکتهٔ مفهومی صحیح**: کد فیزیکی جابه‌جا نمی‌شود. موتور JavaScript در فاز ایجاد (Creation Phase)، فضای حافظه را برای متغیرها اختصاص می‌دهد قبل از اینکه کد خط‌به‌خط اجرا شود.

### 7.2 Hoisting در `var`
```js
console.log(name); // خروجی: undefined
var name = "Ali";
```
* **دلیل**: اعلام `var` به بالا می‌رود و به‌طور خودکار با `undefined` مقداردهی اولیه می‌شود، اما انتساب (`= "Ali"`) در جای خود باقی می‌ماند.

### 7.3 Hoisting در `let`
```js
console.log(name); // خطا: ReferenceError: Cannot access 'name' before initialization
let name = "Ali";
```
* **چرا متفاوت است؟**: `let` هم Hoist می‌شود (فضای حافظه اختصاص می‌یابد)، اما مقداردهی اولیه نمی‌شود و وارد **Temporal Dead Zone (TDZ)** می‌شود.

### 7.4 Hoisting در `const`
دقیقاً مانند `let` رفتار می‌کند و در TDZ قرار می‌گیرد. علاوه بر این، چون مقداردهی اولیه الزامی است، اگر قبل از خط انتساب استفاده شود، خطا می‌دهد.

### 7.5 مقایسهٔ رفتار سه نوع متغیر
* `var`: Hoist می‌شود + مقداردهی با `undefined`.
* `let` / `const`: Hoist می‌شوند + بدون مقداردهی اولیه (ورود به TDZ).

### 7.6 Hoisting و Function Scope
توابع تعریف‌شده با `function declaration` به‌طور کامل (هم نام و هم بدنه) Hoist می‌شوند و می‌توان قبل از تعریف آن‌ها را فراخوانی کرد.

### 7.7 Hoisting و Block Scope
Hoisting همیشه در سطح Scope فعلی (چه Function و چه Block) رخ می‌دهد.

---

## 8. Temporal Dead Zone (TDZ)

### 8.1 TDZ چیست؟
منطقهٔ مرگ موقت (Temporal Dead Zone) فاصلهٔ بین شروع Scope تا خطی است که متغیر با `let` یا `const` تعریف و مقداردهی می‌شود. در این ناحیه، متغیر وجود دارد اما دسترسی به آن ممنوع است.

### 8.2 TDZ در `let` و `const`
هر دو در لحظهٔ ورود به Scope، Hoist می‌شوند اما تا زمان اجرای خط تعریف، در TDZ باقی می‌مانند.

### 8.4 تفاوت TDZ با Hoisting
Hoisting فرآیند اختصاص فضای حافظه است. TDZ یک مکانیزم ایمنی است که جلوی دسترسی زودهنگام به متغیرهای Hoist شده‌ای که هنوز مقداردهی نشده‌اند را می‌گیرد.

### 8.5 مثال‌های قابل‌فهم از TDZ
```js
console.log("Start");
let x = 10; // از این خط به بعد، TDZ برای x تمام می‌شود.
```

### 8.6 خطای `Cannot access 'x' before initialization`
این خطای مشخصهٔ تلاش برای دسترسی به متغیر درون TDZ است.

### 8.7 TDZ و Shadowing
```js
let x = 10;

{
  console.log(x); // خطا: ReferenceError
  let x = 20;
}
```
* **توضیح دقیق**: به محض ورود به بلوک `{}`، موتور JavaScript اعلام `let x` داخلی را Hoist می‌کند. این `x` داخلی، `x` بیرونی را Shadow می‌کند. اما چون هنوز به خط `let x = 20` نرسیده‌ایم، `x` داخلی در TDZ است. بنابراین `console.log(x)` به جای چاپ ۱۰، با خطای دسترسی زودهنگام مواجه می‌شود.

---

## 9. مقایسهٔ کامل `var`، `let` و `const`

| ویژگی | `var` | `let` | `const` |
| :--- | :---: | :---: | :---: |
| **نوع Scope** | Function / Global | Block | Block |
| **امکان Reassignment** | ✅ بله | ✅ بله | ❌ خیر |
| **امکان Redeclaration** | ✅ بله | ❌ خیر | ❌ خیر |
| **نیاز به Initialization** | ❌ خیر | ❌ خیر | ✅ بله |
| **رفتار Hoisting** | ✅ بله (با `undefined`) | ✅ بله (در TDZ) | ✅ بله (در TDZ) |
| **Temporal Dead Zone** | ❌ خیر | ✅ بله | ✅ بله |
| **استفاده در Block Scope** | ❌ خیر (نشت می‌کند) | ✅ بله | ✅ بله |
| **ایجاد Property روی Global Object** | ✅ بله (در Script) | ❌ خیر | ❌ خیر |
| **کاربرد رایج در کد مدرن** | ❌ منسوخ | ✅ متغیرهای تغییرپذیر | ✅ متغیرهای ثابت/Reference |

*توضیح ردیف‌ها*:
1. **Scope**: `var` فقط تابع را می‌شناسد، اما `let`/`const` آکولاد `{}` را هم مرز می‌دانند.
2. **Reassignment**: `const` اجازهٔ `x = 5` بعد از تعریف را نمی‌دهد.
3. **Redeclaration**: `var x; var x;` مجاز است، اما `let x; let x;` خطا می‌دهد.
4. **Initialization**: `const x;` بلافاصله خطای Syntax می‌دهد.
5. **Hoisting**: همه Hoist می‌شوند، اما `var` مقدار `undefined` می‌گیرد، در حالی که بقیه در TDZ می‌مانند.
6. **Global Object**: در فایل اسکریپت معمولی، `var x` باعث ایجاد `window.x` می‌شود، اما `let x` این کار را نمی‌کند (که برای امنیت بهتر است).

---

## 10. تفاوت `const` با Immutable Value

### 10.1 Binding چیست؟
اتصال (Binding) یعنی وصل کردن یک شناسه (نام متغیر) به یک مقدار خاص در حافظه. `const` این اتصال را ثابت می‌کند.

### 10.2 Reference چیست؟
در JavaScript، متغیرهای Object و Array به جای نگه‌داشتن خود داده، آدرس (Reference) محل ذخیرهٔ داده در حافظه را نگه می‌دارند.

### 10.3 Primitive و Reference Value
* **Primitive**: مقدار مستقیماً ذخیره می‌شود (Number, String, Boolean, null, undefined, Symbol, BigInt).
* **Reference**: آدرس ذخیره می‌شود (Object, Array, Function).

### 10.4 و 10.5 چرا تغییر Property مجاز اما انتساب Object جدید ممنوع است؟
```js
const user = { name: "Ali" };

user.name = "Reza"; // ✅ مجاز: آدرس حافظه تغییر نکرده، فقط محتوای آن آدرس تغییر کرده (Mutation).
// user = { name: "Sara" }; // ❌ خطا: تلاش برای تغییر آدرس حافظه‌ای که متغیر user به آن متصل است (Reassignment).
```

### 10.7 اشتباه رایج: «const یعنی Object ثابت است»
این تصور **نادرست** است. `const` فقط اطمینان می‌دهد که متغیر همیشه به **همان Object** اشاره می‌کند، نه اینکه محتوای آن Object تغییر نکند. برای ثابت کردن محتوا باید از `Object.freeze()` استفاده کرد.

---

## 11. استفاده از `let` و `const` در حلقه‌ها

### 11.1 `let` در حلقهٔ `for`
```js
for (let i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}
// console.log(i); // خطا: i در این Scope وجود ندارد.
```
هر تکرار حلقه، یک Scope جدید برای `i` ایجاد می‌کند.

### 11.2 `var` در حلقهٔ `for`
```js
for (var i = 0; i < 3; i++) {
  // ...
}
console.log(i); // 3 (متغیر به بیرون نشت کرده است)
```

### 11.4 مشکل Closure با `var`
```js
for (var i = 1; i <= 3; i++) {
  setTimeout(function() {
    console.log(i);
  }, 1000);
}
// خروجی: 4, 4, 4 (همه به یک متغیر i مشترک در Scope بیرونی اشاره می‌کنند)
```

### 11.5 حل مشکل با `let`
```js
for (let i = 1; i <= 3; i++) {
  setTimeout(function() {
    console.log(i);
  }, 1000);
}
// خروجی: 1, 2, 3 (هر تکرار، یک i جداگانه دارد که Closure آن را به خاطر می‌سپارد)
```

### 11.6 `const` در حلقه‌ها
* در حلقهٔ `for` معمولی (`for (const i = 0; ...)`) مجاز **نیست**، چون `i++` تلاش برای Reassignment است.
* در حلقه‌های `for...of` و `for...in` مجاز است، چون در هر تکرار، یک متغیر جدید ایجاد می‌شود:
```js
const colors = ["red", "green"];
for (const color of colors) {
  console.log(color); // مجاز و ایمن
}
```

---

## 12. `let`، `const` و Closure

### 12.1 Closure چیست؟
توانایی یک تابع برای به خاطر سپردن و دسترسی به متغیرهای Scope بیرونی خود، حتی پس از اتمام اجرای تابع بیرونی.

### 12.2 و 12.3 رفتار `var` و `let` در Closure
همان‌طور که در بخش ۱۱.۴ و ۱۱.۵ دیده شد، `var` یک متغیر مشترک ایجاد می‌کند که همهٔ Closureها به آخرین مقدار آن اشاره می‌کنند. اما `let` در هر تکرار حلقه، یک Binding جدید ایجاد می‌کند، بنابراین هر Closure مقدار مخصوص به همان تکرار را حفظ می‌کند.

### 12.5 کاربرد عملی در Event Handlerها
```js
const buttons = document.querySelectorAll("button");

// روش قدیمی و پرخطا با var
for (var i = 0; i < buttons.length; i++) {
  buttons[i].addEventListener("click", function() {
    console.log("Button " + i + " clicked"); // همیشه آخرین مقدار i را چاپ می‌کند
  });
}

// روش مدرن و صحیح با let
for (let i = 0; i < buttons.length; i++) {
  buttons[i].addEventListener("click", function() {
    console.log("Button " + i + " clicked"); // مقدار صحیح i را چاپ می‌کند
  });
}
```

---

## 13. `let` و `const` در Destructuring

### 13.1 Destructuring چیست؟
روش کوتاهی برای استخراج مقادیر از آرایه‌ها یا Propertyها از Objectها و انتساب آن‌ها به متغیرها.

### 13.2 Destructuring با `let`
```js
let [a, b] = [10, 20];
console.log(a); // 10
a = 30; // مجاز
```

### 13.3 و 13.4 Destructuring با `const` و Object
```js
const { name, age } = { name: "Ali", age: 25 };
// name = "Reza"; // خطا: Reassignment ممنوع است.
```

### 13.5 تفاوت Reassignment و Destructuring
در Destructuring، شما در حال **اعلام و مقداردهی اولیه** هستید، نه Reassignment. بنابراین استفاده از `const` در Destructuring کاملاً منطقی و رایج است.

### 13.6 خطاهای رایج
تلاش برای Destructuring مقدار `null` یا `undefined` باعث خطای `TypeError` می‌شود.

---

## 14. `let` و `const` در Modules

### 14.1 Module Scope چیست؟
هر فایل JavaScript که به عنوان Module (با `type="module"` یا در Node.js با `import`/`export`) بارگذاری شود، Scope مستقل خود را دارد.

### 14.2 تفاوت Global Scope در Script و Module
در Script معمولی، متغیرهای سطح بالا به Global Object (`window`) متصل می‌شوند. در Module، تمام متغیرهای سطح بالا فقط درون همان فایل Module قابل دسترسی هستند و Global را آلوده نمی‌کنند.

### 14.3 و 14.4 استفاده و Export
```js
// math.js (Module)
export const PI = 3.14;
export let counter = 0;

// main.js
import { PI, counter } from './math.js';
console.log(PI); // 3.14
```

---

## 15. ارتباط با Global Object

### 15.1 Global Object چیست؟
محیطی که تمام متغیرهای سراسری در آن زندگی می‌کنند. در مرورگر `window` یا `globalThis`، و در Node.js `global` است.

### 15.2 رفتار `var` در Script
```js
var name = "Ali";
console.log(globalThis.name); // "Ali" (متغیر به Global Object متصل شد)
```

### 15.3 رفتار `let` و `const` در Script
```js
let age = 25;
console.log(globalThis.age); // undefined (متصل نمی‌شود و ایمن‌تر است)
```

### 15.4 تفاوت Script و Module
همان‌طور که گفته شد، در Moduleها حتی `var` هم به Global Object متصل نمی‌شود و همه چیز در Module Scope باقی می‌ماند.

---

## 16. خطاهای رایج و دام‌های مهم

| # | کد اشتباه | نوع خطا | دلیل خطا | نسخهٔ صحیح |
| :--- | :--- | :--- | :--- | :--- |
| **16.1** | `console.log(x); let x = 5;` | `ReferenceError` | دسترسی در TDZ. | تعریف `let x = 5;` را به بالا منتقل کنید. |
| **16.2** | `let a = 1; let a = 2;` | `SyntaxError` | Redeclaration در یک Scope. | حذف `let` دوم: `a = 2;` |
| **16.3** | `const b = 1; const b = 2;` | `SyntaxError` | Redeclaration. | حذف `const` دوم یا تغییر نام متغیر. |
| **16.4** | `const c;` | `SyntaxError` | عدم مقداردهی اولیه در `const`. | `const c = 10;` |
| **16.5** | `const d = 5; d = 10;` | `TypeError` | تلاش برای Reassignment. | استفاده از `let` به جای `const`. |
| **16.6** | `const arr = [1]; arr = [2];` | `TypeError` | اشتباه گرفتن Mutation با Reassignment. | `arr.push(2);` (تغییر محتوا به جای تغییر آدرس). |
| **16.7** | `if(true) { var x = 1; } console.log(x);` | باگ منطقی | تصور اینکه `var` Block Scope دارد. | استفاده از `let x = 1;` |
| **16.8** | `for(var i=0; i<3; i++) { setTimeout(()=>console.log(i), 100); }` | باگ منطقی | Closure با `var` همیشه آخرین مقدار را می‌گیرد. | استفاده از `let i = 0`. |
| **16.9** | `let 1stPlace = "Ali";` | `SyntaxError` | نام نامعتبر (شروع با عدد). | `let firstPlace = "Ali";` |
| **16.10**| `name = "Ali";` (بدون let/const) | باگ/Strict Error | ایجاد متغیر سراسری ضمنی (Implicit Global). | `let name = "Ali";` |
| **16.11**| `let y; console.log(y === undefined);` | باگ منطقی | اشتباه گرفتن `undefined` با تعریف‌نشده. | متغیر تعریف شده اما مقداردهی نشده است. |

---

## 17. بهترین روش‌های استفاده در JavaScript مدرن

### 17.1 چه زمانی از `const` استفاده کنیم؟
به‌طور پیش‌فرض، **همیشه** از `const` شروع کنید. اگر متغیری دارید که قرار نیست مجدداً مقداردهی شود (شامل اکثر Objectها و Arrayها)، از `const` استفاده کنید.

### 17.2 چه زمانی از `let` استفاده کنیم؟
فقط زمانی که مطمئن هستید مقدار متغیر باید در آینده تغییر کند (مثل شمارنده‌های حلقه، مقادیر جمع‌شونده، یا stateهای تغییرپذیر).

### 17.3 چه زمانی ممکن است با `var` مواجه شویم؟
فقط در کدهای قدیمی (Legacy) یا هنگام مطالعهٔ منابع آموزشی قدیمی. در کد جدید هرگز از آن استفاده نکنید.

### 17.4 اصل معروف
> **"Use `const` when you can, and `let` when you have to."**
> «تا وقتی می‌توانی از `const` استفاده کن، و فقط وقتی مجبور شدی از `let` استفاده کن.»
این اصل باعث می‌شود نیت شما به عنوان برنامه‌نویس (ثابت بودن یا تغییرپذیری) برای خوانندهٔ کد کاملاً شفاف باشد.

### 17.5 چرا `const` خوانایی را افزایش می‌دهد؟
وقتی خوانندهٔ کد `const` را می‌بیند، مطمئن می‌شود که این متغیر در ادامهٔ بلوک، مقدار جدیدی نخواهد گرفت و ذهن او درگیر ردیابی تغییرات آن نمی‌شود.

### 17.6 چرا نباید صرفاً به‌دلیل امکان تغییر Object، همیشه از `let` استفاده کنیم؟
چون `const` جلوی تغییر آدرس Reference را می‌گیرد که خودش یک لایهٔ ایمنی ارزشمند است. تغییر Propertyهای داخلی (Mutation) با `const` کاملاً مجاز و استاندارد است.

### 17.7 نکات مربوط به Style Guideها
استانداردهایی مانند Airbnb Style Guide و ESLint به‌طور پیش‌فرض استفاده از `var` را ممنوع (`no-var`) و استفاده از `const` را به `let` ترجیح می‌دهند (`prefer-const`).

---

## 18. مثال‌های عملی و پروژه‌محور

### مثال ۱: مدیریت امتیاز یک بازی
* **مسئله**: امتیاز بازیکن تغییر می‌کند، اما قوانین بازی ثابت هستند.
* **کد**:
  ```js
  const MAX_SCORE = 1000; // ثابت
  let currentScore = 0;   // تغییرپذیر

  currentScore += 50;
  console.log(currentScore); // 50
  // MAX_SCORE = 500; // خطا (محافظت از منطق بازی)
  ```
* **تحلیل**: `const` برای مقادیر پیکربندی و `let` برای state پویا.

### مثال ۲: پردازش آرایهٔ کاربران
* **مسئله**: اضافه کردن کاربر جدید به لیست بدون بازنشانی کل لیست.
* **کد**:
  ```js
  const users = ["Ali", "Sara"];
  users.push("Reza"); // Mutation مجاز است
  console.log(users); // ["Ali", "Sara", "Reza"]
  ```
* **نکته**: استفاده از `const` برای آرایه‌ها رایج‌ترین الگو است.

### مثال ۳: شمارندهٔ حلقه و Closure
* **مسئله**: چاپ اعداد ۱ تا ۳ با تأخیر ۱ ثانیه‌ای.
* **کد**:
  ```js
  for (let i = 1; i <= 3; i++) {
    setTimeout(() => console.log(i), 1000);
  }
  ```
* **تحلیل**: استفاده از `let` باعث می‌شود هر تکرار Scope جداگانه‌ای داشته باشد و Closure مقدار صحیح را حفظ کند.

### مثال ۴: مدیریت تنظیمات یک برنامه
* **مسئله**: شیء تنظیمات باید وجود داشته باشد، اما کل شیء نباید جایگزین شود.
* **کد**:
  ```js
  const config = { theme: "dark", volume: 80 };
  config.volume = 90; // مجاز
  // config = { theme: "light" }; // خطا (جلوگیری از بازنشانی تصادفی)
  ```

### مثال ۵: مقایسهٔ کد قدیمی و مدرن
* **قدیمی**:
  ```js
  var total = 0;
  for (var i = 0; i < items.length; i++) {
    total += items[i].price;
  }
  ```
* **مدرن**:
  ```js
  let total = 0;
  for (let i = 0; i < items.length; i++) {
    total += items[i].price;
  }
  // یا حتی بهتر با متدهای آرایه:
  const total = items.reduce((sum, item) => sum + item.price, 0);
  ```

---

## 19. تمرین‌ها

### سطح مقدماتی
1. یک متغیر با `let` به نام `city` تعریف کنید و مقدار "Tehran" را به آن بدهید. سپس آن را به "Shiraz" تغییر دهید.
2. یک ثابت با `const` به نام `birthYear` تعریف کنید. آیا می‌توانید آن را تغییر دهید؟ چرا؟

### سطح متوسط
3. خروجی کد زیر چیست؟ چرا؟
   ```js
   var a = 10;
   if (true) {
     var a = 20;
   }
   console.log(a);
   ```
4. کد زیر را اصلاح کنید تا بدون خطا اجرا شود و Object تغییر کند:
   ```js
   const person = { age: 25 };
   person = { age: 26 };
   ```

### سطح پیشرفته
5. خروجی کد زیر را پیش‌بینی و دلیل آن را توضیح دهید:
   ```js
   let x = 5;
   function test() {
     console.log(x);
     let x = 10;
   }
   test();
   ```
6. چرا کد زیر با `var` عدد ۳ را سه بار چاپ می‌کند، اما با `let` اعداد ۰، ۱، ۲ را چاپ می‌کند؟
   ```js
   for (var i = 0; i < 3; i++) {
     setTimeout(() => console.log(i), 100);
   }
   ```

---
### پاسخ‌نامهٔ تمرین‌ها
1. `let city = "Tehran"; city = "Shiraz";` (مجاز است چون `let` اجازهٔ Reassignment می‌دهد).
2. خیر، زیرا `const` اجازهٔ Reassignment را نمی‌دهد و خطای `TypeError` می‌دهد.
3. خروجی `20` است. زیرا `var` Block Scope ندارد و مقدار متغیر سراسری `a` را درون بلوک `if` بازنویسی می‌کند.
4. اصلاح: `person.age = 26;` (تغییر Property به جای Reassignment کل Object).
5. خطای `ReferenceError: Cannot access 'x' before initialization`. به دلیل TDZ، متغیر `x` محلی تابع، متغیر سراسری را Shadow می‌کند و قبل از مقداردهی قابل دسترسی نیست.
6. `var` یک متغیر مشترک در Scope بیرونی ایجاد می‌کند که تا زمان اجرای `setTimeout` به مقدار ۳ رسیده است. `let` در هر تکرار حلقه، یک Scope جدید با مقدار جداگانه ایجاد می‌کند که Closure آن را حفظ می‌کند.

---

## 20. پرسش‌های متداول (FAQ)

1. **تفاوت اصلی `let` و `const` چیست؟** `let` اجازهٔ تغییر مقدار (Reassignment) را می‌دهد، اما `const` خیر.
2. **آیا `const` یعنی مقدار همیشه غیرقابل‌تغییر است؟** خیر، فقط اتصال متغیر ثابت است. محتوای Objectها و Arrayهای تعریف‌شده با `const` قابل تغییر (Mutation) است.
3. **آیا `let` و `const` Hoist می‌شوند؟** بله، اعلام آن‌ها به بالای Scope می‌رود، اما تا زمان مقداردهی در «منطقهٔ مرگ موقت» (TDZ) قرار دارند و دسترسی به آن‌ها خطا می‌دهد.
4. **چرا `let` قبل از تعریف خطا می‌دهد؟** به دلیل وجود TDZ که یک مکانیزم ایمنی برای جلوگیری از استفاده از متغیرهای مقداردهی‌نشده است.
5. **آیا `var` هنوز استفاده می‌شود؟** در کد مدرن خیر. فقط در نگهداری کدهای قدیمی با آن مواجه می‌شوید.
6. **چرا در JavaScript مدرن بیشتر از `const` استفاده می‌کنیم؟** چون خوانایی کد را بالا می‌برد، باگ‌های ناشی از تغییرات تصادفی را کاهش می‌دهد و به موتور JavaScript بهینه‌سازی بهتر را امکان‌پذیر می‌کند.
7. **آیا می‌توان مقدار `const` را تغییر داد؟** فقط محتوای داخلی (Property/Element) در Reference Valueها، نه خود متغیر را.
8. **تفاوت Redeclaration و Reassignment چیست؟** Redeclaration تعریف مجدد متغیر با همان نام در یک Scope است (`let x; let x;`). Reassignment تغییر مقدار متغیر موجود است (`x = 5`).
9. **تفاوت Scope و Closure چیست؟** Scope محدودهٔ دسترسی متغیر است. Closure توانایی تابع به یادآوری Scope بیرونی خود حتی پس از اتمام اجرای آن است.
10. **چرا `var` در حلقه‌ها مشکل‌ساز می‌شود؟** چون Block Scope ندارد و متغیر حلقه به بیرون نشت می‌کند و در ترکیب با Closureها (مثل `setTimeout`) باعث رفتارهای غیرمنتظره می‌شود.
11. **آیا `let` می‌تواند نوع دادهٔ خود را تغییر دهد؟** بله، JavaScript یک زبان با تایپ پویا است (`let x = 5; x = "hello";` مجاز است).
12. **آیا `const` برای Objectها مناسب است؟** بله، بسیار مناسب و رایج است، زیرا جلوی بازنشانی تصادفی کل Object را می‌گیرد در حالی که اجازهٔ تغییر Propertyها را می‌دهد.
13. **تفاوت Script و Module در Scope چیست؟** در Script، متغیرهای سطح بالا Global می‌شوند. در Module، همه چیز در Module Scope باقی می‌ماند و Global را آلوده نمی‌کند.
14. **آیا متغیری که مقدارش `undefined` است، تعریف نشده؟** خیر، متغیر «تعریف» (Declared) شده است، اما هنوز مقداری به آن «انتساب» (Assigned) نیافته است.
15. **آیا `const` از تغییر Propertyهای Object جلوگیری می‌کند؟** خیر، برای این کار باید از `Object.freeze()` استفاده کنید.

---

## 21. جمع‌بندی نهایی

* **`var`**: روش قدیمی، Function Scope، دارای Hoisting با `undefined`، اجازهٔ Redeclaration. **(اجتناب کنید)**
* **`let`**: روش مدرن، Block Scope، دارای Hoisting با TDZ، اجازهٔ Reassignment. **(برای مقادیر تغییرپذیر)**
* **`const`**: روش مدرن، Block Scope، دارای Hoisting با TDZ، نیاز به مقداردهی اولیه، عدم اجازهٔ Reassignment. **(پیش‌فرض انتخاب شما)**

**چک‌لیست سریع انتخاب:**
1. آیا مقدار متغیر قرار است تغییر کند؟
   * خیر ➔ از `const` استفاده کن.
   * بله ➔ به سؤال ۲ برو.
2. آیا این یک شمارندهٔ حلقه یا stateای است که باید به‌روز شود؟
   * بله ➔ از `let` استفاده کن.
3. آیا در حال کار با کد Legacy هستی؟
   * بله ➔ ممکن است مجبور به استفاده از `var` شوی، در غیر این صورت هرگز از آن استفاده نکن.

**اشتباهاتی که باید از آن‌ها دوری کرد:**
* استفاده از `var` در پروژه‌های جدید.
* تصور اینکه `const` Objectها را کاملاً Immutable می‌کند.
* تعریف متغیر بدون کلمهٔ کلیدی (ایجاد Global ضمنی).

---

## 22. منابع معتبر

برای مطالعهٔ عمیق‌تر و ارجاع فنی، از منابع رسمی زیر استفاده کنید:

1. **MDN Web Docs — `let`**  
   *لینک*: [developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)  
   *توضیح*: مرجع کامل رفتار، Scope و TDZ مربوط به `let`.

2. **MDN Web Docs — `const`**  
   *لینک*: [developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)  
   *توضیح*: توضیح دقیق تفاوت Binding و Immutability در `const`.

3. **MDN Web Docs — `var`**  
   *لینک*: [developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)  
   *توضیح*: مستندات رسمی دربارهٔ رفتار Hoisting و Function Scope در `var`.

4. **MDN Web Docs — Variables (Guide)**  
   *لینک*: [developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Variables](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Variables)  
   *توضیح*: راهنمای مقدماتی و روان برای درک مفهوم متغیرها و نام‌گذاری.

5. **MDN Web Docs — Grammar and types**  
   *لینک*: [developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types)  
   *توضیح*: پوشش Declartion، Initialization و تفاوت‌های Primitive و Reference.

6. **ECMAScript Language Specification — Let and Const Declarations**  
   *لینک*: [tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html)  
   *توضیح*: مشخصات رسمی و فنی استاندارد زبان که رفتار دقیق Hoisting و TDZ را تعریف می‌کند.

---
*این سند برای قرارگیری مستقیم در فایل `let-var-const.md` در ریپوزیتوری‌های آموزشی بهینه‌سازی شده است.*
