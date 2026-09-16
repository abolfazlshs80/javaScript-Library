

1. [Function چیست؟](#1-function-چیست)
2. [تعریف Function](#2-تعریف-function)
3. [Calling / Invoking Function](#3-calling--invoking-function)
4. [Parameter و Argument](#4-parameter-و-argument)
5. [Return](#5-return)
6. [Function Declaration](#6-function-declaration)
7. [Function Expression](#7-function-expression)
8. [Anonymous Function](#8-anonymous-function)
9. [Function به‌عنوان Value](#9-function-بهعنوان-value)
10. [Passing Function as Argument](#10-passing-function-as-argument)
11. [Callback Function](#11-callback-function)
12. [ساخت Callback به‌صورت دستی](#12-ساخت-callback-بهصورت-دستی)
13. [Higher-Order Function](#13-higher-order-function)
14. [بررسی کد separation](#14-بررسی-کد-separation)
15. [Callback و شرط‌ها](#15-callback-و-شرطها)
16. [Callback و Array](#16-callback-و-array)
17. [filter](#17-filter)
18. [map](#18-map)
19. [forEach](#19-foreach)
20. [reduce](#20-reduce)
21. [Function Expression در مثال area](#21-function-expression-در-مثال-area)
22. [Callback در calcCircle](#22-callback-در-calcCircle)
23. [Arrow Function](#23-arrow-function)
24. [تبدیل Callback به Arrow Function](#24-تبدیل-callback-به-arrow-function)
25. [Anonymous Callback](#25-anonymous-callback)
26. [Callback Synchronous](#26-callback-synchronous)
27. [Callback Asynchronous](#27-callback-asynchronous)
28. [setTimeout و Callback](#28-settimeout-و-callback)
29. [Callback در Eventها](#29-callback-در-eventها)
30. [Callback و this](#30-callback-و-this)
31. [Callback Hell](#31-callback-hell)
32. [مقایسه Callback و Promise](#32-مقایسه-callback-و-promise)
33. [مقایسه Callback و async/await](#33-مقایسه-callback-و-asyncawait)
34. [اشتباهات رایج](#34-اشتباهات-رایج)
35. [تمرین‌های مقدماتی](#35-تمرینهای-مقدماتی)
36. [تمرین‌های متوسط](#36-تمرینهای-متوسط)
37. [تمرین‌های پیشرفته](#37-تمرینهای-پیشرفته)
38. [پروژه کوچک](#38-پروژه-کوچک)
39. [جمع‌بندی](#39-جمعبندی)
40. [منابع](#40-منابع)

---

## 1. Function چیست؟

تابع (Function) مانند یک «دستگاه» یا «کارخانه» کوچک در کد شماست. شما مواد اولیه (ورودی) را به آن می‌دهید، دستگاه کار خود را انجام می‌دهد و در نهایت یک محصول (خروجی) به شما تحویل می‌دهد.

* **چرا از Function استفاده می‌کنیم؟** برای جلوگیری از تکرار کد (اصل DRY: Don't Repeat Yourself). اگر بخواهید یک کار را ۱۰ بار انجام دهید، به‌جای نوشتن ۱۰ بار کد، یک تابع می‌نویسید و ۱۰ بار آن را فراخوانی می‌کنید.
* **Input و Output:** ورودی‌ها داده‌هایی هستند که تابع برای کار کردن نیاز دارد. خروجی نتیجه‌ای است که تابع پس از پردازش برمی‌گرداند.
* **زمان اجرا:** تابع فقط زمانی اجرا می‌شود که شما صراحتاً آن را «فراخوانی» (Call) کنید. تعریف کردن تابع به تنهایی، آن را اجرا نمی‌کند.

```javascript
function sayHello() {
    console.log("Hello");
}
// تا اینجا هیچ چیزی چاپ نمی‌شود، چون تابع فقط تعریف شده است.
```

> 💡 نکته: تعریف Function مانند نوشتن یک دستورالعمل روی کاغذ است. اجرای (Call) آن مانند انجام دادن واقعی آن دستورالعمل است.

---

## 2. تعریف Function

ساختار کلی تعریف یک تابع به این شکل است:

```javascript
function functionName(parameters) {
    // function body (بدنه تابع)
    // کدهایی که باید اجرا شوند
}
```

اجزای آن:
* `function`: کلمه کلیدی جاوااسکریپت برای اعلام ساخت یک تابع.
* `functionName`: نام تابع (باید معنادار و با حروف کوچک شروع شود، مثلاً `calculateSum`).
* `()`: پرانتزهایی که ورودی‌ها را نگه می‌دارند.
* `parameters`: متغیرهایی که در پرانتز تعریف می‌شوند و نقش «جای خالی» برای ورودی‌ها را دارند.
* `{ }`: آکولادهایی که بدنه تابع را محدود می‌کنند.

---

## 3. Calling / Invoking Function

برای اجرای تابع، باید نام آن را به همراه پرانتز بنویسید. به این کار فراخوانی (Calling) یا احضار (Invoking) می‌گویند.

```javascript
sayHello;  // فقط به خود تابع اشاره می‌کند (مثل اشاره به یک دستورالعمل روی کاغذ)
sayHello(); // تابع را اجرا می‌کند (مثل انجام دادن دستورالعمل)
```

> ⚠️ توجه: فراموش کردن پرانتز `()` یکی از رایج‌ترین اشتباهات مبتدیان است. بدون پرانتز، تابع اجرا نمی‌شود.

---

## 4. Parameter و Argument

* **پارامتر (Parameter):** متغیری است که در زمان *تعریف* تابع داخل پرانتز می‌نویسیم (نام مستعار).
* **آرگومان (Argument):** مقدار واقعی‌ای است که در زمان *فراخوانی* تابع به آن می‌دهیم.

```javascript
function greet(name) { // 'name' یک Parameter است
    console.log("Hello " + name);
}

greet("Ali"); // "Ali" یک Argument است
```

مثال با چند پارامتر:
```javascript
function add(a, b) {
    console.log(a + b);
}
add(5, 10); // a=5, b=10
```

---

## 5. Return

دستور `return` دو کار انجام می‌دهد:
1. مقدار مشخص‌شده را به عنوان خروجی تابع برمی‌گرداند.
2. اجرای تابع را بلافاصله متوقف می‌کند.

تفاوت `console.log` و `return`:
* `console.log` فقط چیزی را در کنسول نمایش می‌دهد و تمام.
* `return` مقدار را برای استفاده‌های بعدی در کد برمی‌گرداند.

```javascript
function sum(a, b) {
    return a + b;
}

const result = sum(10, 20); // مقدار 30 در متغیر result ذخیره می‌شود
console.log(result); // 30
```

* اگر `return` نداشته باشیم، تابع به‌طور پیش‌فرض `undefined` برمی‌گرداند.
* **ارتباط با Callback:** توابع Callback اغلب مقداری را `return` می‌کنند تا تابع اصلی (Higher-Order Function) بتواند بر اساس آن `true` یا `false` تصمیم‌گیری کند.

---

## 6. Function Declaration

این همان روش استانداردی است که تا اینجا دیدیم:

```javascript
function sum(a, b) {
    return a + b;
}
```

**Hoisting (بالا بردن):** در جاوااسکریپت، توابعی که با روش Declaration تعریف می‌شوند، قبل از اجرای کد توسط موتور جاوااسکریپت «به بالای فایل منتقل» می‌شوند. بنابراین می‌توانید قبل از تعریف تابع، آن را فراخوانی کنید:

```javascript
sayHello(); // کار می‌کند!

function sayHello() {
    console.log("Hello");
}
```

---

## 7. Function Expression

در این روش، تابع را به عنوان یک مقدار (Value) به یک متغیر اختصاص می‌دهیم:

```javascript
const sum = function (a, b) {
    return a + b;
};
```

| ویژگی | Function Declaration | Function Expression |
| :--- | :--- | :--- |
| **نحوه تعریف** | `function name() {}` | `const name = function() {}` |
| **نام** | اجباری است | اختیاری است (معمولاً Anonymous) |
| **Hoisting** | دارد (قبل از تعریف قابل فراخوانی است) | ندارد (باید بعد از تعریف فراخوانی شود) |
| **کاربرد** | توابع اصلی و عمومی برنامه | Callbackها، توابع یک‌بار مصرف، ماژولار کردن کد |

> 💡 نکته: Function Expressionها در نوشتن Callbackها بسیار رایج‌تر هستند.

---

## 8. Anonymous Function

تابع ناشناس (Anonymous Function) تابعی است که نام ندارد:

```javascript
function () {
    console.log("Hello");
}
```

چون نام ندارد، به تنهایی قابل فراخوانی نیست. معمولاً به یک متغیر اختصاص داده می‌شود یا به عنوان Callback به تابع دیگری پاس داده می‌شود.

```javascript
const greet = function () {
    console.log("Hello");
};
greet();
```

---

## 9. Function به‌عنوان Value

در جاوااسکریپت، توابع «شهروند درجه یک» (First-Class Citizens) هستند. یعنی مانند اعداد یا رشته‌ها می‌توانند در متغیرها ذخیره شوند.

```javascript
function sayHello() {
    console.log("Hello");
}

const myFunction = sayHello; // پرانتز ندارد! فقط ارجاع به تابع
myFunction(); // "Hello" چاپ می‌شود
```

تفاوت حیاتی:
```javascript
const a = sayHello;  // 'a' اکنون خودِ تابع است.
const b = sayHello(); // 'b' مقدار بازگشتیِ اجرای تابع است (در اینجا undefined، چون return ندارد).
```

---

## 10. Passing Function as Argument

چون تابع یک Value است، می‌توانیم آن را به عنوان آرگومان به تابع دیگری بدهیم:

```javascript
function execute(callback) {
    callback(); // اجرای تابعی که پاس داده شده
}

function sayHello() {
    console.log("Hello");
}

execute(sayHello); // "Hello"
```
**مراحل اجرا:**
1. تابع `execute` فراخوانی می‌شود و تابع `sayHello` به آن داده می‌شود.
2. داخل `execute`، پارامتر `callback` اکنون به تابع `sayHello` اشاره می‌کند.
3. دستور `callback()` اجرا می‌شود که در واقع همان `sayHello()` است.

---

## 11. Callback Function

**تعریف:** تابع Callback تابعی است که به عنوان آرگومان به تابع دیگری داده می‌شود تا توسط آن تابع (در زمان مناسب) اجرا شود.

```javascript
function process(callback) {
    callback();
}

function hello() {
    console.log("Hello");
}

process(hello); // صحیح: ارجاع به تابع پاس داده می‌شود
// process(hello()); // غلط: خروجی اجرای hello (که undefined است) پاس داده می‌شود!
```

> 💡 نکته: وقتی نام تابع را بدون پرانتز می‌نویسیم (`hello`)، در حال پاس دادن «خود تابع» هستیم. وقتی با پرانتز می‌نویسیم (`hello()`)، در حال پاس دادن «نتیجه اجرای تابع» هستیم.

---

## 12. ساخت Callback به‌صورت دستی

بیایید یک تابع عمومی بسازیم که رفتار خود را از Callback می‌گیرد:

```javascript
function calculate(a, b, operation) {
    return operation(a, b);
}

function sum(a, b) {
    return a + b;
}

function multiply(a, b) {
    return a * b;
}

console.log(calculate(10, 20, sum));      // 30
console.log(calculate(10, 20, multiply)); // 200
```
تابع `calculate` نمی‌داند چه عملیاتی قرار است انجام شود؛ این وظیفه Callback (`operation`) است که این رفتار را تعیین می‌کند.

---

## 13. Higher-Order Function

تابع مرتبه بالا (Higher-Order Function) تابعی است که:
1. یک یا چند تابع را به عنوان آرگومان دریافت کند، **یا**
2. یک تابع را به عنوان خروجی (`return`) برگرداند.

در مثال قبل، `calculate` یک Higher-Order Function است، و `sum` یک Callback Function است.

```text
Higher-Order Function
        ↓
    دریافت Function
        ↓
     Callback
```

---

## 14. بررسی کد separation

کد اصلی شما با کمی اصلاح برای خوانایی بیشتر (استفاده از `if` به جای ternary با `null`):

```javascript
const numbers = [1, 5, 7, 9, 8, 12];

function isOdd(num) {
    return num % 2 !== 0;
}

function isEven(num) {
    return num % 2 === 0;
}

function separation(arr, callback) {
    const array = [];

    for (let i = 0; i < arr.length; i++) {
        if (callback(arr[i])) {
            array.push(arr[i]);
        }
    }

    return array;
}

console.log(separation(numbers, isEven)); // [8, 12]
console.log(separation(numbers, isOdd));  // [1, 5, 7, 9]
```

**تحلیل خط‌به‌خط:**
* `arr`: آرایه ورودی (مثلاً `numbers`).
* `callback`: تابع شرطی (مثلاً `isEven`).
* `callback(arr[i])`: عنصر فعلی آرایه را به تابع شرطی می‌دهد. اگر `true` برگرداند، شرط `if` برقرار می‌شود.
* `array.push(arr[i])`: اگر شرط برقرار بود، عنصر به آرایه جدید اضافه می‌شود.
* این تابع عمومی شده است، زیرا با تغییر Callback، بدون تغییر کد اصلی `separation`، می‌توانیم اعداد زوج، فرد، یا هر شرط دیگری را فیلتر کنیم.

---

## 15. Callback و شرط‌ها

قدرت Callback در انعطاف‌پذیری آن است. ما می‌توانیم بی‌نهایت تابع شرطی بسازیم و همه را به یک تابع واحد بدهیم:

```javascript
function isGreaterThanFive(num) {
    return num > 5;
}

function isPositive(num) {
    return num > 0;
}

console.log(separation(numbers, isGreaterThanFive)); // [7, 9, 8, 12]
console.log(separation(numbers, isPositive));        // [1, 5, 7, 9, 8, 12]
```
> 💡 نکته: یک تابع می‌تواند رفتار خود را به‌طور کامل از طریق Callback دریافت‌شده تغییر دهد.

---

## 16. Callback و Array

جاوااسکریپت متدهای داخلی آرایه دارد که همگی از Callback استفاده می‌کنند. این متدها در واقع همان `separation` یا مشابه آن هستند که از قبل ساخته شده‌اند.

```javascript
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(function (number) {
    console.log(number);
});
```
* `forEach`: یک Higher-Order Function است.
* `function(number) {...}`: یک Callback است که برای **هر عنصر** آرایه یک بار اجرا می‌شود.

---

## 17. filter

متد `filter()` دقیقاً همان کاری را می‌کند که تابع `separation` ما انجام می‌داد. یک آرایه جدید شامل عناصری که Callback برای آن‌ها `true` برگردانده است، می‌سازد.

```javascript
const numbers = [1, 2, 3, 4, 5, 6];

const evenNumbers = numbers.filter(function (number) {
    return number % 2 === 0;
});

console.log(evenNumbers); // [2, 4, 6]
```
مقایسه با کد دستی ما:
`separation(numbers, isEven)` دقیقاً معادل `numbers.filter(isEven)` است، اما دومی استاندارد و بهینه‌تر است.

---

## 18. map

متد `map()` یک آرایه جدید می‌سازد که حاصل اجرای Callback روی **تک‌تک** عناصر آرایه اصلی است (تعداد عناصر تغییر نمی‌کند، فقط مقادیر تغییر می‌کنند).

```javascript
const numbers = [1, 2, 3];

const result = numbers.map(function (number) {
    return number * 2;
});

console.log(result); // [2, 4, 6]
```
* `filter`: تعداد عناصر را **کم** می‌کند (بر اساس شرط).
* `map`: تعداد عناصر را **حفظ** می‌کند (تغییر شکل می‌دهد).

---

## 19. forEach

متد `forEach` فقط برای اجرای یک عملیات روی هر عنصر است و هیچ مقداری را `return` نمی‌کند (خروجی آن `undefined` است). برخلاف `map` که آرایه جدید می‌سازد.

```javascript
numbers.forEach(function (number) {
    console.log(number * 2); // فقط چاپ می‌کند، آرایه جدیدی نمی‌سازد
});
```

---

## 20. reduce

متد `reduce()` آرایه را به یک **مقدار واحد** (یک عدد، یک رشته، یک آبجکت) تقلیل می‌دهد.

```javascript
const numbers = [1, 2, 3, 4];

const result = numbers.reduce(function (sum, number) {
    return sum + number;
}, 0); // 0 مقدار اولیه sum است

console.log(result); // 10
```
**مراحل اجرا:**
1. دور اول: `sum` = 0, `number` = 1 → return 1
2. دور دوم: `sum` = 1, `number` = 2 → return 3
3. دور سوم: `sum` = 3, `number` = 3 → return 6
4. دور چهارم: `sum` = 6, `number` = 4 → return 10

---

## 21. Function Expression در مثال area

```javascript
const area = function (radius) {
    return Math.PI * radius * radius;
};
```
* چرا Function Expression است؟ چون تابع به یک متغیر (`area`) اختصاص داده شده است.
* `radius`: پارامتر ورودی (شعاع دایره).
* `Math.PI`: یک ثابت داخلی جاوااسکریپت برابر با ۳.۱۴۱۵۹...
* `return`: حاصل ضرب را برمی‌گرداند تا بتوانیم آن را ذخیره یا چاپ کنیم.
* چرا در متغیر قرار دادیم؟ تا بتوانیم آن را به عنوان Callback به توابع دیگر پاس دهیم.

---

## 22. Callback در calcCircle

```javascript
function calcCircle(radius, callback) {
    return callback(radius);
}

const area = function (radius) {
    return Math.PI * radius * radius;
};

const diameter = function (radius) {
    return 2 * radius;
};

console.log(calcCircle(10, area));    // 314.159...
console.log(calcCircle(10, diameter)); // 20
```

**مراحل اجرای `calcCircle(10, area)`:**
```text
calcCircle(10, area)
        ↓
radius = 10
        ↓
callback = area (تابع مساحت)
        ↓
callback(radius) → area(10)
        ↓
Math.PI * 10 * 10
        ↓
314.159...
```
نکته مهم: `calcCircle` اصلاً نمی‌داند که قرار است مساحت حساب کند یا قطر. این «رفتار» توسط Callback تزریق می‌شود. این اوج انعطاف‌پذیری در برنامه‌نویسی است.

---

## 23. Arrow Function

توابع پیکانی (Arrow Functions) روشی مدرن‌تر و کوتاه‌تر برای نوشتن Function Expressionها هستند (معرفی شده در ES6).

```javascript
// حالت معمولی
const sum = (a, b) => {
    return a + b;
};

// حالت کوتاه (Implicit Return)
const sumShort = (a, b) => a + b;

// یک پارامتر (پرانتز اختیاری است)
const square = number => number * number;

// بدون پارامتر (پرانتز خالی الزامی است)
const sayHello = () => console.log("Hello");
```

---

## 24. تبدیل Callback به Arrow Function

بیایید یک Callback معمولی را مرحله‌به‌مرحله به Arrow Function تبدیل کنیم:

```javascript
// 1. حالت اولیه
numbers.filter(function (number) {
    return number % 2 === 0;
});

// 2. حذف کلمه function و اضافه کردن =>
numbers.filter((number) => {
    return number % 2 === 0;
});

// 3. حذف پرانتز پارامتر (چون یک پارامتر دارد) و حذف آکولاد و return (چون یک خط است)
numbers.filter(number => number % 2 === 0);
```

---

## 25. Anonymous Callback

```javascript
numbers.filter(function (number) {
    return number > 5;
});
```
چرا نام ندارد؟ چون ما آن را در جایی ذخیره نمی‌کنیم؛ فقط می‌خواهیم همین‌جا و همین‌یک‌بار اجرا شود.
نسخه مدرن آن با Arrow Function بسیار خواناتر است:
```javascript
numbers.filter(number => number > 5);
```

---

## 26. Callback Synchronous

یک Callback همگام (Synchronous) بلافاصله و در همان لحظه‌ای که تابع اصلی آن را فراخوانی می‌کند، اجرا می‌شود.

```javascript
function process(callback) {
    console.log("Start");
    callback(); // بلافاصله اجرا می‌شود
    console.log("End");
}

process(() => {
    console.log("Callback");
});
```
**خروجی:**
```text
Start
Callback
End
```

---

## 27. Callback Asynchronous

یک Callback ناهمگام (Asynchronous) بعداً، پس از اتمام یک عملیات زمان‌بر، اجرا می‌شود و جلوی اجرای بقیه کد را نمی‌گیرد.

```javascript
console.log("Start");

setTimeout(() => {
    console.log("Callback");
}, 1000);

console.log("End");
```
**خروجی:**
```text
Start
End
Callback
```
چرا؟ چون `setTimeout` به موتور جاوااسکریپت می‌گوید: «این Callback را بردار و ۱۰۰۰ میلی‌ثانیه دیگر در صف اجرا قرار بده». کد اصلی به اجرای خط بعدی (`End`) ادامه می‌دهد.

---

## 28. setTimeout و Callback

`setTimeout` یک Higher-Order Function داخلی جاوااسکریپت است که دو آرگومان اصلی می‌گیرد:
1. یک Callback Function (کاری که باید بعداً انجام شود).
2. Delay (تأخیر به میلی‌ثانیه).

```javascript
setTimeout(() => {
    console.log("Hello");
}, 2000); // بعد از 2 ثانیه اجرا می‌شود
```
این یکی از رایج‌ترین مثال‌های Asynchronous Callback است.

---

## 29. Callback در Eventها

در برنامه‌نویسی وب، ما منتظر می‌مانیم تا کاربر کاری انجام دهد (مثلاً کلیک کند). Callback اینجا نقش کلیدی دارد:

```javascript
const button = document.querySelector("button");

button.addEventListener("click", function () {
    console.log("Clicked");
});

// یا با Arrow Function
button.addEventListener("click", () => {
    console.log("Clicked");
});
```
* `addEventListener`: Higher-Order Function است.
* `"click"`: رویداد (Event).
* تابع ناشناس: Callback است که **فقط زمانی** اجرا می‌شود که رویداد رخ دهد.

---

## 30. Callback و this

مفهوم `this` در Callbackها می‌تواند گیج‌کننده باشد. رفتار آن به نحوه تعریف تابع بستگی دارد:

```javascript
const user = {
    name: "Ali",
    
    // تابع معمولی: this به آبجکتی اشاره می‌کند که تابع را فراخوانی کرده (user)
    normalFunction: function () {
        console.log(this.name); // "Ali"
    },

    // Arrow Function: this را از محیط بیرونی (Lexical Scope) به ارث می‌برد
    // در اینجا محیط بیرونی Global است، نه user!
    arrowFunction: () => {
        console.log(this.name); // undefined
    }
};

user.normalFunction();
user.arrowFunction();
```
> 💡 نکته: هرگز از Arrow Function برای متدهای یک آبجکت (که نیاز به دسترسی به `this` آن آبجکت دارند) استفاده نکنید، مگر اینکه دقیقاً بدانید Lexical Scoping چه می‌کند.

---

## 31. Callback Hell

وقتی چندین عملیات Asynchronous به هم وابسته باشند، مجبوریم Callbackها را درون هم تو در تو (Nested) کنیم. این وضعیت به «جهنم Callback» (Callback Hell) یا «هرم عذاب» معروف است:

```javascript
getData(function(a) {
    getMoreData(a, function(b) {
        getEvenMoreData(b, function(c) {
            console.log("Done: ", c);
        });
    });
});
```
این کد به‌شدت ناخوانا، سخت در دیباگ و نگهداری است.

---

## 32. مقایسه Callback و Promise

Promise (وعده) برای حل مشکل Callback Hell معرفی شد. به‌جای تو در تو کردن توابع، زنجیره‌ای از `.then()` ایجاد می‌کنیم:

```text
Callback
    ↓
تو در تو و ناخوانا (Pyramid of Doom)

Promise
    ↓
زنجیره‌ای و خواناتر (.then().catch())
```

---

## 33. مقایسه Callback و async/await

`async/await` روشی مدرن‌تر برای کار با Promiseهاست که کد Asynchronous را شبیه به کد Synchronous و خوانا می‌کند.

**1. با Callback:**
```javascript
fetchData(function(data) {
    console.log(data);
});
```

**2. با Promise:**
```javascript
fetchData()
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

**3. با async/await:**
```javascript
async function processData() {
    try {
        const data = await fetchData();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}
```
هدف: درک این است که `async/await` و `Promise` جایگزین‌های مدرن و خواناتر برای مدیریت عملیات‌هایی هستند که قبلاً فقط با Callback انجام می‌شدند.

---

## 34. اشتباهات رایج

### اشتباه 1: اجرای تابع به‌جای پاس دادن آن
```javascript
// غلط: خروجی hello() (که undefined است) پاس داده می‌شود
process(hello()); 
// صحیح: خود تابع پاس داده می‌شود
process(hello); 
```

### اشتباه 2: فراموش کردن `return`
```javascript
function isEven(num) {
    num % 2 === 0; // مقدار محاسبه می‌شود اما برمی‌گردد undefined!
}
// صحیح: return num % 2 === 0;
```

### اشتباه 3: استفاده از `=` به‌جای `===`
```javascript
// غلط: این یک انتساب است، نه مقایسه!
num % 2 = 0; 
// صحیح:
num % 2 === 0; 
```

### اشتباه 4: اشتباه گرفتن Function Expression و Function Call
```javascript
const myFunc = function() { return 5; };
console.log(myFunc);  // چاپ می‌کند: [Function: myFunc]
console.log(myFunc()); // چاپ می‌کند: 5
```

### اشتباه 5: استفاده اشتباه از Arrow Function با `{}`
```javascript
// غلط: وقتی آکولاد می‌گذارید، باید صراحتاً return کنید
const square = number => {
    number * number; // خروجی: undefined
};

// صحیح 1: با return صریح
const square = number => {
    return number * number;
};

// صحیح 2: حذف آکولاد برای Implicit Return
const square = number => number * number;
```

---

## 35. تمرین‌های مقدماتی

> 📝 تمرین
1. تابعی بنویسید که یک عدد را دریافت کند و زوج بودن آن را بررسی کند (`true`/`false`).
2. تابعی بنویسید که دو عدد را دریافت و حاصل‌ضرب آن‌ها را `return` کند.
3. تابعی به نام `runTwice` بنویسید که یک Callback را دریافت کرده و دقیقاً دو بار آن را اجرا کند.
4. تابعی بنویسید که یک آرایه از اعداد را دریافت کند و با استفاده از یک Callback، فقط اعداد بزرگ‌تر از ۱۰ را در یک آرایه جدید برگرداند (شبیه `separation`).
5. تابعی بنویسید که یک آرایه و یک Callback بگیرد و Callback را روی تمام عناصر اجرا و نتیجه را در کنسول چاپ کند.

> ### راهنمای حل
> 1. `const isEven = n => n % 2 === 0;`
> 2. `const multiply = (a, b) => a * b;`
> 3. `const runTwice = cb => { cb(); cb(); };`
> 4. از یک حلقه `for` و `if (callback(arr[i]))` استفاده کنید.
> 5. از `forEach` یا حلقه `for` استفاده کنید: `arr.forEach(item => console.log(callback(item)));`

---

## 36. تمرین‌های متوسط

> 📝 تمرین
1. تابع `myFilter` را از صفر بسازید (دقیقاً مانند `separation` اما با نام استاندارد).
2. تابع `myMap` را بسازید که یک آرایه و یک Callback بگیرد و آرایه‌ای جدید با مقادیر تغییریافته برگرداند.
3. یک ماشین‌حساب (`calculator`) بسازید که سه آرگومان بگیرد: `num1`, `num2`, و `operation` (Callback).
4. تابع `calculate` را طوری تغییر دهید که اگر `operation` پاس داده نشد، به‌طور پیش‌فرض جمع (`sum`) را انجام دهد.
5. تمام Function Expressionهای تمرین‌های بالا را به Arrow Function تبدیل کنید.

---

## 37. تمرین‌های پیشرفته

> 📝 تمرین
1. با استفاده از `filter`، `map` و `reduce`، تابعی بنویسید که آرایه‌ای از اعداد را بگیرد، فقط اعداد فرد را نگه دارد، آن‌ها را به توان ۲ برساند و در نهایت مجموع آن‌ها را محاسبه کند (همه در یک زنجیره یا Chaining).
2. یک Higher-Order Function بنویسید که یک تابع را به عنوان ورودی بگیرد و یک تابع جدید برگرداند که قبل از اجرای تابع اصلی، یک پیام "Logging..." چاپ کند (مقدمه‌ای بر Decorator Pattern).

---

## 38. پروژه کوچک: Mini Data Processor

هدف: پردازش داده‌ها با استفاده از Callbackها برای درک انعطاف‌پذیری کد.

```javascript
const numbers = [1, 5, 7, 9, 8, 12, 20, 3];

// 1. توابع شرطی (Predicates)
const isEven = num => num % 2 === 0;
const isOdd = num => num % 2 !== 0;
const isGreaterThan10 = num => num > 10;

// 2. توابع تبدیل (Transformers)
const square = num => num * num;
const double = num => num * 2;

// 3. تابع پردازش عمومی (Higher-Order Function)
function processArray(arr, callback) {
    const result = [];
    for (let i = 0; i < arr.length; i++) {
        result.push(callback(arr[i]));
    }
    return result;
}

// استفاده از processArray (مشابه map)
console.log(processArray(numbers, square)); 
// [1, 25, 49, 81, 64, 144, 400, 9]

// --- نسخه مدرن با متدهای داخلی آرایه ---

// فیلتر کردن اعداد بزرگتر از 10
const bigNumbers = numbers.filter(isGreaterThan10); // [12, 20]

// تبدیل به توان 2
const squared = bigNumbers.map(square); // [144, 400]

// جمع زدن کل
const total = squared.reduce((sum, num) => sum + num, 0); // 544

console.log("Total:", total);
```

---

## 39. جمع‌بندی

مسیر یادگیری ما به این شکل بود:

```text
Function
   ↓
Function Expression
   ↓
Function as Value
   ↓
Passing Function as Argument
   ↓
Callback Function
   ↓
Higher-Order Function
   ↓
Array Methods (filter, map, reduce)
   ↓
Arrow Function
   ↓
Synchronous Callback
   ↓
Asynchronous Callback
   ↓
Promise (راه‌حل مدرن‌تر)
   ↓
async/await (خواناترین حالت)
```

### جدول جمع‌بندی مفاهیم

| مفهوم | معنی ساده |
| :--- | :--- |
| **Function** | دستگاهی که ورودی می‌گیرد، پردازش می‌کند و خروجی می‌دهد. |
| **Parameter** | نام مستعار متغیر در زمان تعریف تابع. |
| **Argument** | مقدار واقعی پاس داده شده در زمان فراخوانی. |
| **Return** | خروجی تابع و پایان‌دهنده اجرای آن. |
| **Function Declaration** | تعریف تابع با کلمه `function` (دارای Hoisting). |
| **Function Expression** | اختصاص تابع به یک متغیر (بدون Hoisting). |
| **Anonymous Function** | تابعی که نام ندارد و معمولاً یک‌بار مصرف است. |
| **Callback** | تابعی که به تابع دیگری داده می‌شود تا بعداً اجرا شود. |
| **Higher-Order Function** | تابعی که تابع دیگری را دریافت یا برگرداند. |
| **Arrow Function** | روش کوتاه و مدرن نوشتن Function Expression. |

---

## 40. منابع

برای مطالعه عمیق‌تر و اطمینان از صحت مفاهیم، همیشه به مستندات رسمی مراجعه کنید:

1. **[MDN Web Docs — Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)**  
   *مرجع کامل و رسمی برای درک نحوه تعریف و فراخوانی توابع در جاوااسکریپت.*
2. **[MDN Web Docs — Callback Function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)**  
   *توضیح واژه‌نامه‌ای و دقیق از مفهوم Callback.*
3. **[MDN Web Docs — Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)**  
   *مستندات رسمی متد `filter` و نحوه کار با Callback در آرایه‌ها.*
4. **[MDN Web Docs — Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)**  
   *توضیح کامل Syntax، محدودیت‌ها و رفتار `this` در توابع پیکانی.*
5. **[JavaScript.info — Function Expressions](https://javascript.info/function-expressions)**  
   *آموزش بسیار روان و مرحله‌به‌مرحله تفاوت Declaration و Expression.*
6. **[JavaScript.info — Callbacks](https://javascript.info/callbacks)**  
   *توضیح عالی از Callbackهای Synchronous و Asynchronous و مقدمه‌ای بر Callback Hell.*

> 💡 نکته نهایی: بهترین راه برای یادگیری Callbackها، نوشتن کد است. مثال‌های این راهنما را در کنسول مرورگر یا Node.js اجرا کنید، مقادیر را تغییر دهید و خروجی‌ها را مشاهده کنید. موفق باشید!
