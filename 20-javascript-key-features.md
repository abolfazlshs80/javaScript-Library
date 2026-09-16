# JavaScript Characteristics

## فهرست مطالب

## 1. مقدمه

## 2. Client-Side JavaScript

## 3. Lightweight

## 4. Object-Oriented Programming

## 5. Weakly Typed / Loosely Typed

## 6. Dynamically Typed

## 7. Functional Programming

## 8. Prototype-Based

## 9. Interpreted and JIT Compilation

## 10. Platform Independent / Cross-Platform

## 11. مقایسه ویژگی‌ها

## 12. سوءبرداشت‌های رایج

## 13. مثال‌های عملی

## 14. تمرین‌ها

## 15. جمع‌بندی

## 16. منابع
```

فهرست مطالب باید دارای لینک‌های داخلی معتبر و سازگار با GitHub Markdown باشد.

---

## منابع معتبر

برای تهیه محتوا از منابع معتبر و ترجیحاً رسمی استفاده کن. منابع پیشنهادی:

1. **MDN Web Docs**

   * JavaScript Guide
   * JavaScript Language Overview
   * JavaScript Introduction
   * JavaScript Reference
   * Inheritance and the Prototype Chain
   * Client-Side Web APIs

2. **ECMAScript Language Specification**

   * برای مفاهیم دقیق زبان، نوع‌ها، Objectها و Prototypeها

3. **TC39**

   * برای استانداردسازی و قابلیت‌های ECMAScript

4. **V8 Documentation**

   * برای توضیح JavaScript Engine، اجرای کد و JIT

5. **Node.js Documentation**

   * برای تفاوت محیط اجرای Server-Side و Browser

در پایان، بخش **منابع** را با لینک مستقیم به صفحات استفاده‌شده قرار بده.

برای هر منبع، عنوان صفحه، نام وب‌سایت و لینک معتبر را بنویس.

اگر درباره موضوعی منبع معتبر و قطعی وجود ندارد یا اصطلاحی محل اختلاف است، آن را صریحاً بیان کن و از ارائه ادعای قطعی خودداری کن.

**هدف نهایی:** تولید یک آموزش جامع، دقیق، خوانا و قابل استفاده برای یادگیری JavaScript از مقدماتی تا پیشرفته که بتوانم مستقیماً در ریپوزیتوری GitHub خود قرار دهم.


### ASSISTANT
# JavaScript Characteristics

## فهرست مطالب

* [1. مقدمه](#1-مقدمه)
* [2. Client-Side JavaScript](#2-client-side-javascript)
* [3. Lightweight](#3-lightweight)
* [4. Object-Oriented Programming](#4-object-oriented-programming)
* [5. Weakly Typed / Loosely Typed](#5-weakly-typed--loosely-typed)
* [6. Dynamically Typed](#6-dynamically-typed)
* [7. Functional Programming](#7-functional-programming)
* [8. Prototype-Based](#8-prototype-based)
* [9. Interpreted and JIT Compilation](#9-interpreted-and-jit-compilation)
* [10. Platform Independent / Cross-Platform](#10-platform-independent--cross-platform)
* [11. مقایسه ویژگی‌ها](#11-مقایسه-ویژگی‌ها)
* [12. سوءبرداشت‌های رایج](#12-سوءبرداشت‌های-رایج)
* [13. مثال‌های عملی](#13-مثال‌های-عملی)
* [14. تمرین‌ها و پاسخ‌نامه](#14-تمرین‌ها-و-پاسخ‌نامه)
* [15. جمع‌بندی](#15-جمع‌بندی)
* [16. منابع](#16-منابع)

---

## 1. مقدمه

### JavaScript چیست؟
جاوااسکریپت یک زبان برنامه‌نویسی سطح بالا، پویا و چندمنظوره است. اگر وب را یک انسان در نظر بگیریم، HTML اسکلت و استخوان‌بندی، CSS پوست و ظاهر، و JavaScript مغز و عضلات آن است که رفتار و پویایی را ایجاد می‌کند.

### تفاوت JavaScript و Java
با وجود شباهت نامی، این دو زبان هیچ ارتباطی با هم ندارند. **Java** یک زبان کامپایل‌شده، شیءگرای کلاسیک و شدیداً تایپ‌شده است (مانند یک خودرو). **JavaScript** یک زبان مفسری/تفسیری-کامپایل، چندپارادایمی و پویا است (مانند یک فرش). شباهت نام آن‌ها تنها یک ترفند بازاریابی در دهه ۹۰ میلادی بود.

### ECMAScript چیست؟
**ECMAScript** (یا ES) استاندارد و مشخصات (Specification) زبانی است که JavaScript بر اساس آن ساخته شده است. سازمان **TC39** مسئول توسعه این استاندارد است. وقتی می‌گوییم ES6 یا ES2015، منظورمان نسخه‌ای از استاندارد ECMAScript است. JavaScript، پیاده‌سازیِ (Implementation) این استاندارد توسط موتورهای مختلف است.

### محیط‌های اجرا (Environments)
جاوااسکریپت برای اجرا به یک میزبان (Host) نیاز دارد.
* **مرورگرها (Browsers):** محیط پیش‌فرض برای تعامل با کاربر.
* **Node.js / Deno / Bun:** محیط‌هایی برای اجرای JS در سمت سرور یا سیستم‌عامل.

### تفاوت زبان، موتور و Runtime
این تفکیک بسیار حیاتی است:
1. **زبان (Language):** خودِ JavaScript (قواعد، Syntax، ECMAScript).
2. **موتور (Engine):** نرم‌افزاری که کد JS را می‌خواند و اجرا می‌کند (مانند **V8** در کروم/Node.js، **SpiderMonkey** در فایرفاکس).
3. **محیط اجرا (Runtime):** بسته‌ای که موتور JS را به همراه APIهای اضافی ارائه می‌دهد (مرورگر APIهای DOM را می‌دهد، Node.js APIهای فایل‌سیستم را).

> 💡 **نکته مهم:** شناخت این ویژگی‌ها به شما "مدل ذهنی" (Mental Model) می‌دهد تا به جای حفظ کردن کدها، رفتار زبان را پیش‌بینی کنید.

---

## 2. Client-Side JavaScript

### Client-Side یعنی چه؟
در معماری شبکه، **Client** (مشتری) درخواست‌دهنده و **Server** (سرور) پاسخ‌دهنده است. Client-Side JS یعنی کدی که روی دستگاه کاربر (معمولاً در مرورگر) دانلود و اجرا می‌شود.

### نحوه اجرا در مرورگر
وقتی مرورگر یک صفحه HTML را دریافت می‌کند، آن را تجزیه کرده و **DOM** (Document Object Model) را می‌سازد. DOM یک نمایش درختی و شیءگرا از صفحه است. موتور JS به DOM دسترسی پیدا کرده و می‌تواند آن را دستکاری کند.

### ارتباط با HTML/CSS و DOM
JS می‌تواند عناصر HTML را انتخاب، ایجاد، حذف و استایل‌های CSS را تغییر دهد.
```javascript
// انتخاب یک دکمه و تغییر متن آن
const btn = document.querySelector('#myBtn');
btn.textContent = 'کلیک شد!';
btn.style.color = 'red';
```

### مدیریت رویدادها (Events)
JS منتظر اتفاقاتی مثل کلیک، تایپ یا ارسال فرم می‌ماند.
```javascript
btn.addEventListener('click', function() {
  alert('دکمه کلیک شد!');
});
```

### ارتباط با سرور (fetch)
JS می‌تواند بدون رفرش صفحه، با سرور ارتباط برقرار کند (Ajax/Fetch).
```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data));
```

### تفاوت Client-Side و Server-Side
* **Client-Side:** تعامل با کاربر، انیمیشن، اعتبارسنجی فرم. (محیط: مرورگر)
* **Server-Side:** دسترسی به دیتابیس، احراز هویت، عملیات سنگین. (محیط: Node.js)

### محدودیت‌های امنیتی (Sandbox)
JS در مرورگر در یک "جعبه شنی" (Sandbox) اجرا می‌شود. نمی‌تواند فایل‌های سیستم کاربر را بخواند، نرم‌افزار نصب کند یا به صورت مستقیم به دیتابیس سرور وصل شود. این محدودیت برای حفظ امنیت کاربر است.

> ⚠️ **توجه:** Client-Side بودن به معنی اجرای کد *فقط* روی کامپیوتر کاربر است، اما این کد می‌تواند درخواست‌هایی را به سرور بفرستد و داده‌های سرور را دریافت و نمایش دهد.

---

## 3. Lightweight

### Lightweight در زبان‌های برنامه‌نویسی
این اصطلاح به معنی **سادگی در تعبیه (Embedding)**، **Syntax روان** و **عدم نیاز به زیرساخت‌های سنگین** برای شروع است.

### چرا JS Lightweight است؟
در روزهای اول وب، برای اضافه کردن یک انیمیشن ساده نیازی به کامپایلر، فایل‌های باینری بزرگ یا محیط‌های پیچیده نبود. فقط کافی بود یک تگ `<script>` در HTML قرار دهید. این "سبکی در یکپارچه‌سازی" مفهوم Lightweight بودن JS است.

### آیا به معنی کم‌حجم بودن فایل یا مصرف کم RAM است؟
**خیر!** این یک سوءبرداشت بزرگ است.
* موتورهای مدرن JS (مثل V8) به شدت پیچیده‌اند و رم (RAM) زیادی مصرف می‌کنند.
* برنامه‌های JS (مثل اپلیکیشن‌های React یا Electron) می‌توانند بسیار سنگین باشند.

### چه عواملی باعث سنگین شدن می‌شوند؟
1. **Bundlers و Frameworks:** کتابخانه‌های بزرگ و کدهای تولید شده توسط بیلدرها.
2. **DOM Manipulation:** دستکاری هزاران عنصر در صفحه.
3. **Memory Leaks:** عدم آزادسازی حافظه (مثلاً در Closureها یا Event Listenerهای فراموش‌شده).

### ارتباط با تجربه کاربر (UX)
سبکی JS در زمان *بارگذاری اولیه* (به دلیل عدم نیاز به کامپایل آفلاین) و *یادگیری* آن است، نه لزوماً در *اجرای نهایی*. برای عملکرد بهتر، توسعه‌دهندگان باید کدها را Minify و بهینه کنند.

---

## 4. Object-Oriented Programming (OOP)

### OOP چیست؟
رویکردی در برنامه‌نویسی که مدل‌سازی دنیا واقعی را بر اساس **اشیاء (Objects)** انجام می‌دهد. هر شیء ترکیبی از **ویژگی‌ها (Properties)** و **رفتارها (Methods)** است.

### چرا JS شیءگراست؟
در JS تقریباً همه‌چیز شیء است (به جز Primitiveها). شما می‌توانید مفاهیم OOP را پیاده‌سازی کنید.

### چهار ستون OOP در JavaScript
1. **Encapsulation (کپسوله‌سازی):** پنهان کردن جزئیات داخلی. (با `#` در ES6).
2. **Abstraction (انتزاع):** پیچیدگی را پنهان و فقط ضروریات را نمایش دادن.
3. **Inheritance (وراثت):** یک شیء ویژگی‌های شیء دیگر را به ارث ببرد.
4. **Polymorphism (چندریختی):** یک متد بتواند رفتارهای متفاوتی بر اساس شیء داشته باشد.

### تکامل OOP در JS
**۱. Object Literal (ساده‌ترین حالت):**
```javascript
const user = {
  name: "Ali",
  sayHello() { console.log(`Hi, I'm ${this.name}`); }
};
```

**۲. Constructor Function (روش قدیمی):**
```javascript
function User(name) {
  this.name = name;
}
User.prototype.sayHello = function() { /* ... */ };
const ali = new User("Ali");
```

**۳. کلاس‌ها (ES6 - Syntactic Sugar):**
```javascript
class User {
  #password; // Private Field
  
  constructor(name, password) {
    this.name = name;
    this.#password = password;
  }
  
  sayHello() {
    console.log(`Hello, ${this.name}`);
  }
}

class Admin extends User {
  constructor(name, password, role) {
    super(name, password);
    this.role = role;
  }
  
  // Method Overriding
  sayHello() {
    console.log(`Hello Admin ${this.name}`);
  }
}
```

### تفاوت با Java/C#
در Java/C#، کلاس‌ها "الگوهای ساخت" (Blueprints) هستند. در JS، کلاس‌ها فقط **Syntactic Sugar** (ظاهر زیبا) روی سیستم **Prototype-Based** هستند. اشیاء مستقیماً از اشیاء دیگر ارث‌بری می‌کنند، نه از کلاس.

---

## 5. Weakly Typed / Loosely Typed

### تعریف دقیق (بسیار مهم)
* **Dynamic Typing:** زمان بررسی نوع داده (Runtime).
* **Weak/Loose Typing:** اجازه دادن به موتور برای **تبدیل ضمنی نوع‌ها (Type Coercion)** بدون خطا دادن.

> 💡 **نکته علمی:** JS هم Dynamic است و هم Weak/Loose. این دو اصطلاح یکی نیستند. Weak بودن به معنی "اجازه دادن به ترکیب سیب و پرتقال" با تلاش برای تبدیل آن‌ها به یک میوه است.

### Type Coercion (تبدیل نوع ضمنی)
وقتی عملگرها با نوع‌های متفاوت روبرو می‌شوند، JS سعی می‌کند آن‌ها را تبدیل کند.

```javascript
console.log("5" + 2);   // "52" (عدد به رشته تبدیل شد، چون + با رشته اولویت الحاق دارد)
console.log("5" - 2);   // 3 (رشته به عدد تبدیل شد، چون - فقط برای اعداد است)
console.log(true + 1);  // 2 (true به 1 تبدیل شد)
console.log(false == 0);// true (تبدیل ضمنی)
console.log(null == undefined); // true (قانون خاص JS)
```

### تفاوت `==` و `===`
* `==` (Equality): تبدیل نوع ضمنی انجام می‌دهد.
* `===` (Strict Equality): هم مقدار و هم نوع باید یکی باشد (بدون تبدیل).

### مزایا و معایب
* **مزیت:** انعطاف‌پذیری بالا، نوشتن کد سریع‌تر.
* **عیب:** باگ‌های پنهان و غیرقابل پیش‌بینی.
* **راه‌حل:** همیشه از `===` استفاده کنید و برای پروژه‌های بزرگ از **TypeScript** استفاده نمایید.

---

## 6. Dynamically Typed

### Dynamic Typing چیست؟
نوع داده به **متغیر** متصل نیست، بلکه به **مقدار (Value)** متصل است. متغیر فقط یک "ظرف" یا "نشانگر" است.

```javascript
let value = 10;       // value اکنون به یک Number اشاره دارد
value = "Hello";      // همان ظرف اکنون به یک String اشاره دارد
value = true;         // و اکنون به یک Boolean
```

### تفاوت `let` و `const`
* `let`: اجازه تغییر مقدار (و نوع) را می‌دهد.
* `const`: فقط **ارجاع (Reference)** را ثابت نگه می‌دارد. نوع داده ثابت نمی‌شود!
```javascript
const user = { name: "Ali" };
user.name = "Reza"; // مجاز است (تغییر ویژگی داخل شیء)
user = {};          // خطا! (تغییر خود ارجاع ممنوع است)
```

### بررسی نوع در Runtime
* `typeof value`: نوع primitiveها را برمی‌گرداند.
* `instanceof`: بررسی می‌کند آیا یک شیء از کلاس/prototype خاصی است یا خیر.
* `Array.isArray()`: تنها راه قطعی برای تشخیص آرایه.

---

## 7. Functional Programming (FP)

### FP چیست؟
پارادایمی که محاسبات را بر اساس **توابع ریاضی** می‌بیند. از تغییر状态 (State) و داده‌های قابل تغییر (Mutable) پرهیز می‌کند.

### مفاهیم کلیدی
1. **First-Class Functions:** توابع شهروند درجه یک هستند؛ می‌توان آن‌ها را در متغیر ذخیره کرد، به عنوان آرگومان فرستاد یا به عنوان خروجی برگرداند.
2. **Higher-Order Functions:** توابعی که تابع دیگری را می‌گیرند یا برمی‌گردانند (مثل `map`, `filter`).
3. **Pure Functions:** تابعی که همیشه برای یک ورودی مشخص، خروجی یکسان می‌دهد و Side Effect (تغییر متغیر بیرونی) ندارد.
4. **Immutability:** داده‌ها تغییر نمی‌کنند، بلکه کپی جدیدی ساخته می‌شود.

### Declarative vs Imperative
* **Imperative (دستوری):** *چگونه* انجام دهم؟ (حلقه `for`)
* **Declarative (اعلامی):** *چه چیزی* می‌خواهم؟ (`map`, `filter`)

```javascript
const numbers = [1, 2, 3, 4, 5];

// Imperative
let evensSquared = [];
for(let i=0; i<numbers.length; i++) {
  if(numbers[i] % 2 === 0) evensSquared.push(numbers[i] * numbers[i]);
}

// Declarative (Functional)
const result = numbers
  .filter(n => n % 2 === 0)
  .map(n => n * n);
```

### Closure و Arrow Functions
* **Closure:** تابعی که متغیرهای محیط بیرونی خود را به خاطر می‌سپارد.
* **Arrow Functions:** Syntax کوتاه‌تر و رفتار متفاوت `this` (ارث‌بری `this` از محیط لغوی).

> 💡 **توجه:** JS یک زبان **Multi-Paradigm** است. شما می‌توانید OOP و FP را در یک پروژه ترکیب کنید (مثلاً استفاده از `class` برای ساختار و `map/filter` برای پردازش داده).

---

## 8. Prototype-Based

### Prototype-Based یعنی چه؟
در زبان‌های Class-Based (مثل Java)، ابتدا یک کلاس (نقشه) ساخته می‌شود، سپس شیء. در JS، **اشیاء مستقیماً از اشیاء دیگر ارث‌بری می‌کنند**. هر شیء یک لینک مخفی به یک شیء دیگر به نام **Prototype** دارد.

### Prototype Chain و Property Lookup
وقتی `obj.property` را صدا می‌زنید:
1. JS در خود `obj` می‌گردد.
2. اگر نبود، به `[[Prototype]]` (پدر) آن می‌رود.
3. این زنجیره تا رسیدن به `null` ادامه می‌یابد.

### تفاوت `prototype` و `__proto__` (بسیار مهم)
* `__proto__` (یا `Object.getPrototypeOf()`): لینک مخفی **داخل هر شیء** که به پدرش اشاره می‌کند.
* `prototype`: یک **ویژگی (Property) مخصوص توابع (Functions)** که وقتی با `new` صدا زده می‌شوند، به عنوان `__proto__` به شیء جدید اختصاص می‌یابد.

```javascript
function Person(name) {
  this.name = name;
}

// متد را روی prototype تابع قرار می‌دهیم تا در حافظه Share شود
Person.prototype.sayHello = function() {
  return `Hello, ${this.name}`;
};

const ali = new Person("Ali");

console.log(Object.getPrototypeOf(ali) === Person.prototype); // true
console.log(ali.__proto__ === Person.prototype); // true (روش قدیمی)
```

### چرا متدها روی Prototype هستند؟
اگر متد را در Constructor بنویسیم، برای هر شیء یک کپی از تابع در حافظه ساخته می‌شود. با قرار دادن روی `prototype`، همه اشیاء از **یک تابع واحد** استفاده می‌کنند (بهینه‌سازی حافظه).

### آیا `class` واقعاً Class-Based است؟
خیر. کلمه کلیدی `class` در ES6 فقط **Syntactic Sugar** است. در پشت صحنه، JS همان کار Constructor و Prototype را انجام می‌دهد.

---

## 9. Interpreted and JIT Compilation

### Interpreted vs Compiled
* **Compiled (مثل C++):** کد منبع یکجا به زبان ماشین تبدیل و فایل اجرایی ساخته می‌شود.
* **Interpreted (مثل Python قدیمی):** کد خط‌به‌خط خوانده و اجرا می‌شود.

### واقعیت مدرن: JIT (Just-In-Time)
جاوااسکریپت در گذشته مفسری بود، اما موتورهای مدرن (مثل **V8** گوگل) از **JIT Compilation** استفاده می‌کنند تا سرعتی هم‌رده زبان‌های کامپایل‌شده داشته باشند.

### مراحل اجرای کد در V8:
1. **Parsing:** کد به توکن و سپس **AST** (درخت نحو انتزاعی) تبدیل می‌شود.
2. **Ignition (Interpreter):** AST به **Bytecode** تبدیل و اجرا می‌شود.
3. **Profiling:** موتور در حین اجرا، کدهای پرتکرار (Hot code) را شناسایی می‌کند.
4. **TurboFan (Compiler):** کدهای Hot را به شدت بهینه کرده و به **Machine Code** مستقیم تبدیل می‌کند.

> 💡 **نتیجه:** گفتن اینکه "JS فقط Interpreted است" از نظر فنی برای موتورهای مدرن **نادرست** است. JS زبانی است که در زمان اجرا (On-the-fly) کامپایل می‌شود.

---

## 10. Platform Independent / Cross-Platform

### Platform Independent یعنی چه؟
کد نوشته‌شده در یک سیستم‌عامل، بدون تغییر در سیستم‌عامل دیگر اجرا می‌شود.

### نقش ECMAScript
استاندارد ECMAScript تضمین می‌کند که **هسته زبان** (Syntax، نوع‌ها، حلقه‌ها) در همه موتورها (V8, SpiderMonkey) یکسان رفتار کند.

### تفاوت Cross-Platform بودن زبان و برنامه
* **زبان JS:** Cross-Platform است (هسته زبان همه‌جا یکسان است).
* **APIهای محیطی:** Cross-Platform **نیستند**.
  * `document.querySelector()` فقط در مرورگر کار می‌کند (در Node.js خطا می‌دهد).
  * `require('fs')` فقط در Node.js کار می‌کند (در مرورگر وجود ندارد).

### راه‌حل‌های Cross-Platform واقعی
برای نوشتن کدی که همه‌جا اجرا شود، باید از APIهای استاندارد استفاده کرد یا از فریم‌ورک‌های واسط بهره برد:
* **React Native:** برای موبایل (iOS/Android).
* **Electron:** برای دسکتاپ (Windows/Mac/Linux).
* **Deno / Bun:** تلاش برای یکسان‌سازی Web APIs در سمت سرور.

```javascript
// این کد در همه جا (Browser, Node, Deno) کار می‌کند:
console.log("Hello Cross-Platform JS"); 

// این کد فقط در مرورگر کار می‌کند:
document.body.style.background = "red"; 
```

---

## 11. مقایسه ویژگی‌ها

| ویژگی | تعریف ساده | مفهوم فنی | مثال کوتاه | مزیت | محدودیت | سوءبرداشت رایج |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Client-Side** | اجرا روی دستگاه کاربر | اجرا در Sandbox مرورگر با دسترسی به DOM | `document.querySelector()` | تعامل آنی با کاربر | عدم دسترسی به فایل‌سیستم | یعنی کد امن است و هک نمی‌شود |
| **Lightweight** | سبک در تعبیه و یادگیری | Syntax ساده، عدم نیاز به کامپایل آفلاین | `<script>...</script>` | یادگیری سریع، یکپارچگی آسان | مصرف بالای RAM در اپ‌های بزرگ | یعنی برنامه JS رم کمی مصرف می‌کند |
| **Object-Oriented** | مدل‌سازی دنیا واقعی | استفاده از Objects، Properties و Methods | `class User { ... }` | سازماندهی کد، قابلیت استفاده مجدد | پیچیدگی در طراحی معماری | JS کلاس‌های واقعی مثل C# دارد |
| **Weak/Loose** | تبدیل خودکار نوع‌ها | Type Coercion در عملگرها | `"5" + 2 === "52"` | انعطاف‌پذیری در نوشتار | باگ‌های پنهان و گیج‌کننده | یعنی Dynamic Typing است |
| **Dynamic** | نوع متغیر در Runtime | نوع به Value متصل است نه Variable | `let x = 1; x = "A";` | سرعت توسعه، کد کوتاه | عدم تشخیص خطا در زمان نوشتن | یعنی const نوع را ثابت می‌کند |
| **Functional** | توابع به عنوان شهروند درجه یک | First-Class Functions، Pure Functions | `arr.map(x => x * 2)` | کد خوانا، بدون Side Effect | منحنی یادگیری steep | JS فقط یک زبان Functional است |
| **Prototype-Based**| ارث‌بری از اشیاء | Prototype Chain و Property Lookup | `Object.getPrototypeOf()` | اشتراک‌گذاری متدها، حافظه بهینه | درک آن برای مبتدیان دشوار است | `__proto__` و `prototype` یکی هستند |
| **Interpreted/JIT**| اجرا در زمان اجرا | Parse -> AST -> Bytecode -> JIT Machine Code | اجرای کد در Console | عدم نیاز به بیلد، توسعه سریع | پیچیدگی موتورهای مدرن | JS همیشه کند و خط‌به‌خط اجرا می‌شود |
| **Cross-Platform**| اجرا در هر محیطی | هسته زبان استاندارد، APIهای متفاوت | `console.log()` | یک زبان برای وب، سرور، موبایل | تفاوت APIها در محیط‌های مختلف | همه کدها در Node و Browser یکی اجرا می‌شوند |

---

## 12. سوءبرداشت‌های رایج

1. **JavaScript همان Java است:** خیر، فقط نامشان شبیه است.
2. **JS فقط در مرورگر اجرا می‌شود:** خیر، Node.js و Deno آن را به سرور آوردند.
3. **JS کاملاً Object-Oriented است:** خیر، Multi-Paradigm است و OOP آن بر پایه Prototype است.
4. **Weakly Typed و Dynamically Typed یکی هستند:** خیر، اولی به Coercion مربوط است، دومی به زمان بررسی نوع.
5. **Interpreted یعنی همیشه کند:** خیر، JIT Compilation سرعت آن را به شدت افزایش داده است.
6. **`__proto__` و `prototype` یکی هستند:** خیر، اولی لینک داخلی اشیاء، دومی ویژگیِ توابع Constructor.
7. **`class` در JS دقیقاً مانند C# است:** خیر، فقط Syntactic Sugar برای Prototype است.
8. **Client-Side یعنی کد همیشه امن است:** خیر، کد سمت کاربر قابل دستکاری است (XSS).
9. **Platform Independent یعنی همه APIها یکسان‌اند:** خیر، `document` در Node نیست.
10. **Lightweight یعنی مصرف RAM کم:** خیر، موتور V8 و اپ‌های مدرن رم زیادی مصرف می‌کنند.
11. **`const` نوع داده را ثابت می‌کند:** خیر، فقط Reference را ثابت نگه می‌دارد.
12. **JS یک زبان Functional خالص است:** خیر، Multi-Paradigm است.
13. **همه‌چیز در JS Object است:** خیر، Primitiveها (مثل Number, String) Object نیستند (اما Wrapper دارند).
14. **JS برای کارهای سنگین مناسب نیست:** با WebAssembly و بهینه‌سازی‌های V8، بسیاری از کارهای سنگین با JS انجام می‌شود.
15. **یادگیری JS آسان است، پس نیاز به درک عمیق ندارد:** Syntax آسان است، اما درک مفاهیمی مثل Closure و Prototype نیاز به عمق دارد.

---

## 13. مثال‌های عملی

### مثال ۱: تغییر محتوا (Client-Side & Dynamic)
**مسئله:** ساخت یک شمارنده با کلیک دکمه.
```javascript
let count = 0; // Dynamic Typing
const btn = document.getElementById('incBtn'); // Client-Side DOM

btn.addEventListener('click', () => { // Event Handling
  count++;
  document.getElementById('display').textContent = count;
});
```
* **ویژگی‌ها:** Client-Side (DOM, Events)، Dynamic Typing.
* **خروجی:** با هر کلیک، عدد در صفحه یکی اضافه می‌شود.
* **نکته:** اگر `btn` وجود نداشته باشد، خطای `null` می‌دهد (نیاز به بررسی).

### مثال ۲: Type Coercion (Weakly Typed)
**مسئله:** بررسی رفتار عملگرها با نوع‌های متفاوت.
```javascript
function checkTypes(a, b) {
  console.log(`Addition: ${a + b}`);
  console.log(`Subtraction: ${a - b}`);
  console.log(`Strict Equal: ${a === b}`);
}
checkTypes("10", 5);
```
* **ویژگی‌ها:** Weakly Typed (Coercion).
* **خروجی:** Addition: 105 | Subtraction: 5 | Strict Equal: false.
* **نکته:** `+` رشته را اولویت می‌دهد، `-` عدد را.

### مثال ۳: ساخت Object با Prototype (Prototype-Based)
**مسئله:** ساخت سیستم ارث‌بری برای خودروها.
```javascript
function Vehicle(type) {
  this.type = type;
}
Vehicle.prototype.start = function() {
  return `${this.type} is starting...`;
};

const car = new Vehicle("Car");
console.log(car.start()); // Car is starting...
console.log(car.hasOwnProperty('start')); // false (روی Prototype است)
```
* **ویژگی‌ها:** Prototype-Based، OOP.
* **نکته:** متد `start` در خود `car` نیست، بلکه در زنجیره Prototype یافت می‌شود.

### مثال ۴: پردازش داده (Functional Programming)
**مسئله:** فیلتر کردن و تغییر لیست کاربران.
```javascript
const users = [
  { name: "Ali", age: 25 },
  { name: "Sara", age: 17 },
  { name: "Reza", age: 30 }
];

const adultNames = users
  .filter(user => user.age >= 18) // Pure Function
  .map(user => user.name.toUpperCase()); // Immutability (آرایه جدید)

console.log(adultNames); // ["ALI", "REZA"]
```
* **ویژگی‌ها:** Functional (HOFs, Declarative, Immutability).
* **نکته:** آرایه اصلی `users` دست نخورده باقی مانده است.

### مثال ۵: تشخیص محیط (Cross-Platform)
**مسئله:** اجرای کد متفاوت بر اساس محیط.
```javascript
function getEnvironmentInfo() {
  if (typeof window !== 'undefined') {
    return `Browser: ${window.location.href}`;
  } else if (typeof process !== 'undefined') {
    return `Node.js: ${process.version}`;
  }
  return "Unknown Environment";
}
console.log(getEnvironmentInfo());
```
* **ویژگی‌ها:** Cross-Platform (تشخیص APIهای محیط).
* **نکته:** بررسی وجود `window` یا `process` برای جلوگیری از خطای ReferenceError.

---

## 14. تمرین‌ها و پاسخ‌نامه

*(برای هر فصل، نمونه‌ای از سوالات مفهومی، تشریحی، کدنویسی و چالشی آورده شده است)*

### فصل ۱ تا ۳ (مقدمه، Client-Side، Lightweight)
1. **مفهومی:** تفاوت Engine و Runtime را با یک مثال توضیح دهید.
2. **مفهومی:** چرا JS در مرورگر نمی‌تواند فایل‌های هارد دیسک را بخواند؟
3. **مفهومی:** Lightweight بودن به چه معناست و به چه معنا نیست؟
4. **تشریحی:** چرخه درخواست و پاسخ در Client-Side JS را توضیح دهید.
5. **تشریحی:** نقش DOM در ارتباط JS و HTML چیست؟
6. **کدنویسی:** یک دکمه بسازید که با کلیک، رنگ پس‌زمینه `body` را تغییر دهد.
7. **کدنویسی:** با `fetch` یک داده از یک API عمومی (مثل JSONPlaceholder) بگیرید و در `console` چاپ کنید.
8. **چالشی:** چرا قرار دادن `<script>` در انتهای `<body>` در گذشته توصیه می‌شد اما امروزه با `defer` تغییر کرده است؟

### فصل ۴ تا ۶ (OOP، Weak، Dynamic)
1. **مفهومی:** تفاوت `==` و `===` چیست؟
2. **مفهومی:** چرا `typeof null` برابر با `"object"` است؟ (یک باگ تاریخی).
3. **مفهومی:** آیا `const` باعث Immutable شدن شیء می‌شود؟
4. **تشریحی:** چهار ستون OOP را در JS با مثال توضیح دهید.
5. **تشریحی:** مفهوم Type Coercion را با دو مثال مثبت و منفی شرح دهید.
6. **کدنویسی:** یک `class BankAccount` بسازید با متد `deposit` و `withdraw` و یک Private Field برای `balance`.
7. **کدنویسی:** تابعی بنویسید که نوع ورودی‌های خود را با `typeof` و `Array.isArray` تشخیص دهد.
8. **چالشی:** خروجی `[] == ![]` چیست و چرا؟ (تحلیل Coercion).

### فصل ۷ تا ۹ (Functional، Prototype، Interpreted)
1. **مفهومی:** تفاوت First-Class Function و Higher-Order Function چیست؟
2. **مفهومی:** `prototype` و `__proto__` چه تفاوتی دارند؟
3. **مفهومی:** JIT Compilation چگونه سرعت JS را افزایش می‌دهد؟
4. **تشریحی:** مفهوم Closure را با یک مثال کاربردی (مثل ساخت شمارنده) توضیح دهید.
5. **تشریحی:** مراحل تبدیل کد JS به Machine Code در موتور V8 را نام ببرید.
6. **کدنویسی:** آرایه‌ای از اعداد را با `reduce` جمع بزنید.
7. **کدنویسی:** یک Constructor Function بسازید و متدی را روی Prototype آن قرار دهید.
8. **چالشی:** چرا `person1.sayHello === person2.sayHello` در حالت Constructor (بدون prototype) برابر `false` است اما با Prototype برابر `true` می‌شود؟

### فصل ۱۰ (Cross-Platform)
1. **مفهومی:** چرا `document` در Node.js کار نمی‌کند؟
2. **تشریحی:** نقش ECMAScript در Cross-Platform بودن چیست؟
3. **کدنویسی:** کدی بنویسید که فقط در محیط Browser اجرا شود و در Node.js خطا ندهد.
4. **چالشی:** چگونه می‌توان یک کد JS نوشت که هم در مرورگر و هم در Node.js ماژول‌های یکسانی را Export کند (UMD Pattern)؟

---

### 💡 پاسخ‌نامه خلاصه (برای خودارزیابی)

* **فصل ۱-۳:**
  * *تفاوت Engine/Runtime:* موتور (V8) کد را اجرا می‌کند، Runtime (Node) APIهای اضافی مثل فایل‌سیستم را به موتور تزریق می‌کند.
  * *امنیت:* به دلیل Sandbox و جلوگیری از دسترسی به منابع محلی کاربر.
  * *کد رنگ:* `document.body.style.backgroundColor = 'blue';`
* **فصل ۴-۶:**
  * *const:* خیر، فقط Reference ثابت است. `const obj = {}; obj.a = 1;` مجاز است.
  * *چالش `[] == ![]`:* خروجی `true` است. `![]` می‌شود `false`. سپس `[]` به primitive تبدیل می‌شود (`""`) و `false` به `0`. رشته خالی `""` به عدد `0` تبدیل می‌شود. `0 == 0` می‌شود `true`.
* **فصل ۷-۹:**
  * *Closure:* تابعی که متغیرهای scope بیرونی را به یاد می‌سپارد.
  * *چالش Prototype:* در حالت عادی هر بار Constructor صدا زده شود یک تابع جدید در حافظه ساخته می‌شود (آدرس‌ها متفاوت). روی Prototype، همه به یک تابع واحد در حافظه اشاره می‌کنند.
* **فصل ۱۰:**
  * *چالش UMD:* استفاده از الگوی `(function(root, factory) { ... })(this, function() { ... })` برای تشخیص محیط (CommonJS, AMD, Global).

---

## 15. جمع‌بندی

جاوااسکریپت زبانی است که از سادگیِ یک اسکریپت مرورگری به غولی در دنیای برنامه‌نویسی تبدیل شده است. درک ویژگی‌هایی مانند **Prototype-Based** بودن، **Dynamic/Weak Typing** و معماری **JIT** به شما کمک می‌کند تا از یک "کدنویس صرف" به یک "مهندس نرم‌افزار" تبدیل شوید.
این زبان با وجود تمام نقص‌های تاریخی (مثل Coercionهای عجیب)، به دلیل **انعطاف‌پذیری**، **جامعه بزرگ** و **Cross-Platform** بودن، هنوز هم پادشاه بلامنازع وب و یکی از محبوب‌ترین زبان‌های دنیا باقی مانده است.

---

## 16. منابع

برای مطالعه عمیق‌تر، منابع زیر پیشنهاد می‌شوند:

1. **MDN Web Docs (Mozilla)**
   * [JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
   * [Inheritance and the Prototype Chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
2. **ECMAScript Language Specification**
   * [TC39 ECMAScript Specification](https://tc39.es/ecma262/)
3. **V8 Documentation**
   * [V8 Blog: JIT Compilation](https://v8.dev/blog/jit-compiler)
   * [Ignition Interpreter](https://v8.dev/blog/ignition-interpreter)
4. **Node.js Documentation**
   * [Node.js Guides](https://nodejs.org/en/learn)
5. **کتاب‌های پیشنهادی:**
   * *You Don't Know JS Yet* by Kyle Simpson (منبع رایگان و فوق‌العاده برای درک عمیق).
   * *JavaScript: The Good Parts* by Douglas Crockford (کلاسیک و مفهومی).

---
*این مستند برای ریپازیتوری‌های آموزشی GitHub طراحی شده است. در صورت نیاز به توسعه هر بخش، می‌توانید به منابع MDN مراجعه کنید.*
