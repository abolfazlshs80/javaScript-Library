
## فهرست مطالب (Table of Contents)

1. [مقدمه‌ای بر JavaScript Engine](#1-مقدمه‌ای-بر-javascript-engine)
2. [تاریخچه JavaScript Engine](#2-تاریخچه-javascript-engine)
3. [موتورهای معروف JavaScript](#3-موتورهای-معروف-javascript)
4. [JavaScript Engine در مرورگر چگونه کار می‌کند؟](#4-javascript-engine-در-مرورگر-چگونه-کار-میکند)
5. [JavaScript Engine در Node.js چگونه کار می‌کند؟](#5-javascript-engine-در-nodejs-چگونه-کار-میکند)
6. [معماری کلی JavaScript Engine](#6-معماری-کلی-javascript-engine)
7. [مراحل اجرای کد JavaScript](#7-مراحل-اجرای-کد-javascript)
8. [Parsing در JavaScript Engine](#8-parsing-در-javascript-engine)
9. [Interpreter چیست؟](#9-interpreter-چیست)
10. [Compiler و JIT Compiler](#10-compiler-و-jit-compiler)
11. [مراحل بهینه‌سازی در موتورهای مدرن](#11-مراحل-بهینه‌سازی-در-موتورهای-مدرن)
12. [V8 و اجزای مهم آن](#12-v8-و-اجزای-مهم-آن)
13. [Call Stack و Execution Context](#13-call-stack-و-execution-context)
14. [Heap و مدیریت حافظه](#14-heap-و-مدیریت-حافظه)
15. [Garbage Collector و ارتباط آن با JavaScript Engine](#15-garbage-collector-و-ارتباط-آن-با-javascript-engine)
16. [Built-in Objects و Runtime Support](#16-built-in-objects-و-runtime-support)
17. [JavaScript Engine و Web APIs](#17-javascript-engine-و-web-apis)
18. [JavaScript Engine و Event Loop](#18-javascript-engine-و-event-loop)
19. [JavaScript Engine و Type System](#19-javascript-engine-و-type-system)
20. [Hidden Classes و Shapes](#20-hidden-classes-و-shapes)
21. [Inline Caching](#21-inline-caching)
22. [Deoptimization](#22-deoptimization)
23. [JavaScript Engine و Closures](#23-javascript-engine-و-closures)
24. [JavaScript Engine و Modules](#24-javascript-engine-و-modules)
25. [JavaScript Engine و Async/Await](#25-javascript-engine-و-asyncawait)
26. [JavaScript Engine و WebAssembly](#26-javascript-engine-و-webassembly)
27. [JavaScript Engine و چندنخی بودن](#27-javascript-engine-و-چندنخی-بودن)
28. [JavaScript Engine و Performance](#28-javascript-engine-و-performance)
29. [JavaScript Engine و ابزارهای توسعه‌دهنده](#29-javascript-engine-و-ابزارهای-توسعهدهنده)
30. [Debugging در JavaScript Engine](#30-debugging-در-javascript-engine)
31. [JavaScript Engine و امنیت](#31-javascript-engine-و-امنیت)
32. [تفاوت استاندارد ECMAScript با پیاده‌سازی Engine](#32-تفاوت-استاندارد-ecmascript-با-پیاده‌سازی-engine)
33. [ساخت یک JavaScript Engine ساده — بخش آموزشی](#33-ساخت-یک-javascript-engine-ساده--بخش-آموزشی)
34. [باورهای غلط رایج درباره JavaScript Engine](#34-باورهای-غلط-رایج-درباره-javascript-engine)
35. [جمع‌بندی نهایی](#35-جمع‌بندی-نهایی)
- [منابع](#منابع)

---

## 1. مقدمه‌ای بر JavaScript Engine

### توضیح ساده
JavaScript Engine مانند «مترجم همزمان» یا «موتور ماشین» است. همان‌طور که موتور ماشین سوخت را به حرکت تبدیل می‌کند، این موتور کد متنی JavaScript را به دستوراتی تبدیل می‌کند که پردازنده (CPU) کامپیوتر بتواند آن‌ها را بفهمد و اجرا کند.

### تعریف فنی
JavaScript Engine یک برنامه نرم‌افزاری است که کد منبع JavaScript را تجزیه (Parse)، تفسیر (Interpret) یا کامپایل (Compile) کرده و به کد ماشین (Machine Code) یا بایت‌کد (Bytecode) تبدیل می‌کند تا توسط سخت‌افزار اجرا شود.

### مثال
```javascript
console.log("Hello");
```
- **در مرورگر:** موتور (مثلاً V8) این کد را می‌گیرد، آن را اجرا می‌کند و درخواست چاپ را به محیط میزبان (Browser Console) می‌فرستد.
- **در Node.js:** همان موتور V8 کد را اجرا می‌کند، اما درخواست چاپ را به محیط میزبان متفاوتی (Terminal/Console سیستم‌عامل) می‌فرستد.

### نکات مهم
- **زبان برنامه‌نویسی (Programming Language):** مجموعه‌ای از قوانین و نحو (Syntax). (مثل دستور زبان فارسی).
- **Interpreter:** کد را خط‌به‌خط یا بلوک‌به‌بلوک می‌خواند و اجرا می‌کند.
- **Compiler:** کل کد را یکجا به کد ماشین تبدیل می‌کند.
- **Engine:** ترکیبی از Parser، Interpreter، Compiler و مدیریت حافظه است.
- **Runtime Environment:** موتور + Web APIs/Node APIs + Event Loop + Call Stack.
- **Host Environment:** محیطی که کد در آن اجرا می‌شود (مرورگر، Node.js، Deno).

### اشتباهات رایج
- **اشتباه:** JavaScript Engine همان مرورگر است.
- **واقعیت:** مرورگر شامل Rendering Engine (مثل Blink)، JavaScript Engine (مثل V8)، و شبکه‌ای از APIهاست. Engine فقط مسئول اجرای کد JS است.

---

## 2. تاریخچه JavaScript Engine

### توضیح ساده
در ابتدا، JavaScript فقط برای کارهای ساده مثل اعتبارسنجی فرم‌ها بود، بنابراین موتورها بسیار ساده و کند بودند. با پیشرفت وب و ساخت برنامه‌های پیچیده (مثل Gmail)، نیاز به سرعت بیشتر احساس شد و موتورهای مدرن متولد شدند.

### تعریف فنی
اولین موتور، **Mocha** (بعداً SpiderMonkey) توسط برندن آیک در Netscape Navigator (1995) ساخته شد. تا اواسط دهه 2000، موتورها صرفاً Interpreterهای ساده بودند. با شروع «جنگ مرورگرها» و ظهور Google Chrome در 2008 با موتور **V8**، عصر کامپایلرهای JIT (Just-In-Time) و بهینه‌سازی‌های پیشرفته آغاز شد.

### موتورهای مهم تاریخی
- **SpiderMonkey:** اولین موتور، توسعه‌یافته توسط Mozilla (هنوز در Firefox استفاده می‌شود).
- **V8:** توسعه‌یافته توسط Google، انقلابی در سرعت با کامپایل مستقیم به Machine Code.
- **JavaScriptCore (Nitro):** توسعه‌یافته توسط Apple برای Safari.
- **Chakra:** توسعه‌یافته توسط Microsoft برای Edge قدیمی (اکنون Edge از V8 استفاده می‌کند).

### نکات مهم
نقش JIT در افزایش سرعت، تبدیل کد پرتکرار (Hot Code) به کد ماشین بهینه‌شده در حین اجراست، که فاصله بین Interpreter و Compiler سنتی را پر کرد.

---

## 3. موتورهای معروف JavaScript

### V8
- **توسعه‌دهنده:** Google (پروژه Chromium).
- **محیط‌ها:** Google Chrome, Node.js, Deno, Electron.
- **ویژگی‌ها:** کامپایل مستقیم به Machine Code، استفاده از Ignition (Interpreter) و TurboFan (Optimizing Compiler)، مدیریت حافظه نسل‌بندی‌شده.
- **مستندات:** [v8.dev](https://v8.dev/)

### SpiderMonkey
- **توسعه‌دهنده:** Mozilla.
- **محیط‌ها:** Mozilla Firefox.
- **ویژگی‌ها:** استفاده از Baseline Compiler و IonMonkey (Optimizing Compiler)، تمرکز قوی بر امنیت و انطباق با استانداردها.
- **مستندات:** [SpiderMonkey Documentation](https://spidermonkey.dev/)

### JavaScriptCore (JSC)
- **توسعه‌دهنده:** Apple (پروژه WebKit).
- **محیط‌ها:** Safari, React Native (به‌عنوان موتور پیش‌فرض).
- **ویژگی‌ها:** استفاده از LLInt (Low Level Interpreter)، Baseline JIT و FTL (Faster Than Light) JIT.
- **مستندات:** [WebKit JavaScriptCore](https://webkit.org/javascriptcore/)

### جدول مقایسه‌ای
| ویژگی | V8 | SpiderMonkey | JavaScriptCore |
| :--- | :--- | :--- | :--- |
| توسعه‌دهنده | Google | Mozilla | Apple |
| محیط اصلی | Chrome, Node.js | Firefox | Safari |
| Interpreter | Ignition | Baseline | LLInt |
| Optimizing JIT | TurboFan | IonMonkey | FTL JIT |

### نکات مهم
JavaScript یک زبان استاندارد (ECMAScript) است، اما نحوه پیاده‌سازی بهینه‌سازی، مدیریت حافظه و ساختار داخلی در هر موتور متفاوت است.

---

## 4. JavaScript Engine در مرورگر چگونه کار می‌کند؟

### توضیح ساده
وقتی یک صفحه وب باز می‌شود، مرورگر فایل HTML را می‌خواند. وقتی به تگ `<script>` می‌رسد، کار را به موتور JavaScript می‌سپارد. موتور کد را اجرا می‌کند و اگر نیاز به تغییر صفحه یا درخواست شبکه باشد، از ابزارهای مرورگر (Web APIs) کمک می‌گیرد.

### مسیر اجرای ساده
```text
HTML Document
  ↓ (توسط HTML Parser خوانده می‌شود)
Browser encounters <script>
  ↓
JavaScript Engine (Parse → Execute)
  ↓ (درخواست تعامل با صفحه یا شبکه)
Interaction with Host APIs (DOM, Fetch, setTimeout)
  ↓
Rendering Engine (به‌روزرسانی تصویر روی صفحه)
```

### تعریف فنی اجزا
- **HTML Parser:** ساختار DOM را می‌سازد.
- **JavaScript Engine:** کد JS را اجرا می‌کند.
- **Web APIs:** امکاناتی مثل `setTimeout`، `DOM`، `fetch` که توسط مرورگر فراهم می‌شوند، نه خود موتور JS.
- **Event Loop:** هماهنگ‌کننده بین Call Stack موتور JS و صف‌های (Queues) Web APIs.

### مثال
```javascript
document.getElementById("btn").addEventListener("click", () => {
  console.log("Clicked");
});
```
موتور JS تابع را ثبت می‌کند، اما گوش‌دادن به رویداد کلیک و فراخوانی تابع، توسط محیط میزبان (Browser) و Event Loop مدیریت می‌شود.

---

## 5. JavaScript Engine در Node.js چگونه کار می‌کند؟

### توضیح ساده
Node.js یک محیط اجرایی است که موتور V8 را از مرورگر خارج کرده و در سرور قرار می‌دهد. بنابراین، امکانات مرورگر (مثل `window` یا `document`) را ندارد، اما به جای آن، امکانات سیستم‌عامل (مثل خواندن فایل) را از طریق `libuv` فراهم می‌کند.

### تعریف فنی
Node.js = V8 Engine + libuv (برای I/O ناهمگام و Event Loop) + Core Modules (fs, http, etc.) + C++ Bindings.

### مثال
```javascript
console.log("Hello"); // توسط V8 اجرا می‌شود

setTimeout(() => {
  console.log("Timer finished"); // Timer توسط libuv مدیریت می‌شود، callback به Event Loop برمی‌گردد
}, 1000);
```

### نکات مهم
- `document` و `window` وجود ندارند چون Node.js مرورگر نیست (Host Environment متفاوت است).
- `libuv` مسئول مدیریت صف‌ها، Thread Pool و Event Loop در Node.js است.

---

## 6. معماری کلی JavaScript Engine

### توضیح ساده
کد شما یک مسیر چندمرحله‌ای را طی می‌کند: ابتدا خوانده و به درخت تبدیل می‌شود، سپس به یک زبان میانی ساده ترجمه می‌شود، و در نهایت اگر زیاد استفاده شود، به زبان ماشین بهینه تبدیل می‌گردد.

### نمودار معماری (ساده‌شده)
```text
JavaScript Source Code
          ↓
        Parser (تجزیه‌کننده)
          ↓
          AST (درخت نحوی انتزاعی)
          ↓
      Bytecode (کد میانی)
          ↓
     Interpreter (اجرای سریع اولیه)
          ↓
   JIT Optimization (شناسایی کدهای پرتکرار)
          ↓
     Machine Code (کد ماشین بهینه‌شده)
          ↓
       CPU (پردازنده)
```

### اجزای مهم
- **Parser:** کد را به AST تبدیل می‌کند.
- **Interpreter:** بایت‌کد را سریعاً اجرا می‌کند (شروع سریع).
- **Optimizing Compiler:** کدهای داغ (Hot) را به کد ماشین بسیار سریع تبدیل می‌کند.
- **Call Stack:** ردیابی فراخوانی توابع.
- **Heap:** محل ذخیره اشیاء و داده‌های پویا.
- **Garbage Collector:** پاک‌سازی حافظه غیرقابل‌دسترسی در Heap.

---

## 7. مراحل اجرای کد JavaScript

### مثال
```javascript
function add(a, b) {
  return a + b;
}
const result = add(10, 20);
console.log(result);
```

### مراحل گام‌به‌گام
1. **Source Code:** متن کد بالا.
2. **Parser:** کد را خوانده و بررسی می‌کند که از نظر دستوری صحیح است.
3. **AST:** کد را به ساختار درختی تبدیل می‌کند (مثلاً گره `FunctionDeclaration` با فرزندانی برای `a` و `b`).
4. **Bytecode:** AST به دستورالعمل‌های سطح پایین‌تر (بایت‌کد) تبدیل می‌شود.
5. **Interpreter:** بایت‌کد را خط‌به‌خط اجرا می‌کند. تابع `add` تعریف می‌شود.
6. **Execution:** وقتی `add(10, 20)` فراخوانی می‌شود، یک Execution Context جدید در Call Stack ایجاد می‌شود.
7. **Optimization:** اگر `add` هزاران بار فراخوانی شود، JIT Compiler آن را شناسایی کرده و به Machine Code بهینه تبدیل می‌کند.
8. **Machine Code:** CPU دستورالعمل‌های بهینه‌شده جمع کردن دو عدد را مستقیماً اجرا می‌کند.
9. **Result:** مقدار 30 به `console.log` پاس داده می‌شود که خود یک Built-in Object است و درخواست را به Host Environment می‌فرستد.

---

## 8. Parsing در JavaScript Engine

### توضیح ساده
Parsing مانند خواندن یک جمله و تشخیص فاعل، فعل و مفعول است. موتور باید بفهمد هر کلمه چه نقشی دارد قبل از اینکه بتواند آن را اجرا کند.

### تعریف فنی
- **Lexer/Tokenizer:** رشته متنی کد را به توکن‌های معنادار (Tokens) مثل `const`, `x`, `=`, `10`, `+`, `20`, `;` تقسیم می‌کند.
- **Parser:** توکن‌ها را بر اساس قواعد زبان (Grammar) به یک درخت به نام **Abstract Syntax Tree (AST)** تبدیل می‌کند.
- **Syntax Error:** اگر Parser نتواند توکن‌ها را به یک ساختار معتبر تبدیل کند (مثلاً پرانتز بسته نشده)، این خطا را پرتاب می‌کند.

### مثال AST برای `const x = 10 + 20;`
```text
VariableDeclaration
 ├── Kind: "const"
 └── Declarators
      └── VariableDeclarator
           ├── Id: Identifier "x"
           └── Init: BinaryExpression
                ├── Operator: "+"
                ├── Left: Literal (10)
                └── Right: Literal (20)
```

### نکات مهم
AST مستقیماً اجرا نمی‌شود، بلکه به عنوان نقشه‌ی راه برای تولید Bytecode استفاده می‌شود. ابزارهایی مثل Babel یا ESLint نیز از AST برای تحلیل یا تبدیل کد استفاده می‌کنند.

---

## 9. Interpreter چیست؟

### توضیح ساده
Interpreter مانند یک مترجم زنده است که همزمان که سخنران صحبت می‌کند، جملات را ترجمه می‌کند. سریع شروع می‌کند، اما ممکن است در ترجمه جملات تکراری، هر بار از اول تلاش کند.

### تعریف فنی
Interpreter بایت‌کد را می‌خواند و مستقیماً عملیات مربوطه را روی CPU انجام می‌دهد، بدون اینکه آن را به کد ماشین بهینه‌شده تبدیل کند.

### مزایا و محدودیت‌ها
- **مزایا:** شروع اجرای سریع (Low startup time)، مصرف حافظه کمتر.
- **محدودیت‌ها:** سرعت اجرای پایین‌تر برای حلقه‌ها یا توابع پرتکرار، زیرا هر دستورالعمل بایت‌کد باید جداگانه تفسیر شود.

### واقعیت موتورهای مدرن
در موتورهای مدرن، Interpreter (مثل Ignition در V8) کد را سریع اجرا می‌کند و همزمان اطلاعاتی (Profile) جمع‌آوری می‌کند تا به Compiler بگوید کدام بخش‌ها نیاز به بهینه‌سازی دارند.

---

## 10. Compiler و JIT Compiler

### توضیح ساده
Compiler مانند ترجمه کل یک کتاب قبل از انتشار است. زمان می‌برد، اما خواندن آن بسیار سریع است. JIT (Just-In-Time) ترکیبی هوشمند است: ابتدا سریع شروع می‌کند (Interpreter)، و سپس بخش‌هایی که زیاد استفاده می‌شوند را در حین اجرا ترجمه و بهینه می‌کند (Compiler).

### تعریف فنی
- **AOT (Ahead-of-Time):** کامپایل قبل از اجرا (مثل C++ یا Rust).
- **JIT (Just-In-Time):** کامپایل در حین اجرا. موتور تصمیم می‌گیرد کدام توابع "Hot" هستند و آن‌ها را به Machine Code کامپایل می‌کند.

### مثال
اگر تابعی 10,000 بار در یک حلقه فراخوانی شود، Interpreter آن را 10,000 بار تفسیر می‌کند. JIT Compiler پس از چند بار اجرا، متوجه تکرار می‌شود، تابع را به کد ماشین بهینه تبدیل می‌کند و 9,990 فراخوانی بعدی با سرعت بسیار بالا اجرا می‌شوند.

### هزینه‌های JIT
فرآیند بهینه‌سازی خود زمان و حافظه مصرف می‌کند. بنابراین، JIT فقط برای کدهای پرتکرار اعمال می‌شود، نه همه کدها.

---

## 11. مراحل بهینه‌سازی در موتورهای مدرن

### تمرکز بر V8
1. **اجرای اولیه:** Ignition (Interpreter) کد را اجرا می‌کند.
2. **Profiling / Type Feedback:** Ignition اطلاعاتی درباره انواع داده‌ها (مثلاً `a` و `b` همیشه عدد هستند) جمع‌آوری می‌کند.
3. **Optimization:** TurboFan (Optimizing Compiler) این اطلاعات را می‌گیرد و کد ماشین بسیار سریع و تخصصی تولید می‌کند.
4. **Deoptimization:** اگر ناگهان نوع داده تغییر کند (مثلاً به جای عدد، رشته پاس داده شود)، فرضیات TurboFan نقض می‌شود. موتور کد بهینه‌شده را دور ریخته و به اجرای عمومی‌تر (Ignition) باز می‌گردد.

### مثال
```javascript
function add(a, b) { return a + b; }
add(1, 2); // Type Feedback: اعداد صحیح (Small Ints)
add(3, 4); // TurboFan کد ماشین بهینه برای جمع اعداد صحیح می‌سازد.
add("Hello", "World"); // Deoptimization رخ می‌دهد! فرض عدد بودن نقض شد.
```

---

## 12. V8 و اجزای مهم آن

### تعریف فنی اجزای مدرن V8
- **Ignition:** Interpreter مبتنی بر ثبت‌کننده (Register-based) که بایت‌کد را اجرا و Type Feedback جمع‌آوری می‌کند.
- **Sparkplug:** یک Baseline Compiler بدون Profiling که بایت‌کد را سریعاً به کد ماشین تبدیل می‌کند تا تأخیر شروع (Startup latency) را کاهش دهد (بین Ignition و TurboFan).
- **Maglev:** یک Mid-tier Optimizing Compiler که بهینه‌سازی‌های متوسط را با هزینه کمتر نسبت به TurboFan اعمال می‌کند.
- **TurboFan:** Optimizing Compiler نهایی که کد را با استفاده از گراف‌های "Sea of Nodes" به شدت بهینه می‌کند.

### نکات مهم
معماری V8 ثابت نیست. Google مدام اجزایی مثل Sparkplug و Maglev را اضافه می‌کند تا تعادل بهتری بین سرعت شروع (Startup) و سرعت اجرای طولانی‌مدت (Throughput) ایجاد کند.

---

## 13. Call Stack و Execution Context

### توضیح ساده
Call Stack مانند یک دسته بشقاب است. آخرین بشقابی که گذاشته‌اید، اولین بشقابی است که برمی‌دارید (LIFO). هر بار که تابعی فراخوانی می‌شود، یک بشقاب (Execution Context) روی آن قرار می‌گیرد.

### تعریف فنی
- **Execution Context:** محیطی که شامل متغیرها، `this` و زنجیره اسکوپ (Scope Chain) است.
- **Global Execution Context:** اولین کانتکستی که ایجاد می‌شود.
- **Function Execution Context:** برای هر فراخوانی تابع ایجاد می‌شود.
- **Stack Overflow:** وقتی تعداد فراخوانی‌های توابع (مثلاً بازگشتی بی‌پایان) از حد مجاز حافظه Stack فراتر رود.

### مثال
```javascript
function first() { second(); }
function second() { third(); }
function third() { console.log("Hello"); }
first();
```
**مسیر Stack:**
1. `first` وارد Stack می‌شود.
2. `second` وارد Stack می‌شود.
3. `third` وارد Stack می‌شود.
4. `console.log` وارد و خارج می‌شود.
5. `third`، سپس `second`، و در نهایت `first` از Stack خارج می‌شوند (Unwind).

---

## 14. Heap و مدیریت حافظه

### توضیح ساده
اگر Call Stack یک میز کار کوچک و منظم باشد، Heap یک انبار بزرگ و نامنظم است که اشیاء بزرگ در آن نگهداری می‌شوند.

### تعریف فنی
- **Heap:** ناحیه‌ای از حافظه که برای تخصیص پویا (Dynamic Allocation) اشیاء، آرایه‌ها و Closureها استفاده می‌شود.
- **Stack:** برای ذخیره مقادیر اولیه (Primitives) و اشاره‌گرها (References) به اشیاء Heap استفاده می‌شود.
- **Object Allocation:** وقتی `const user = {}` می‌نویسید، خود شیء در Heap ساخته می‌شود و متغیر `user` در Stack، فقط یک اشاره‌گر (آدرس) به آن محل در Heap را نگه می‌دارد.

### مثال
```javascript
const user = { name: "Ali", age: 25 };
```
موتور یک بلوک حافظه در Heap برای این شیء اختصاص می‌دهد. متغیر `user` در Execution Context فعلی (Stack)، آدرس آن بلوک را ذخیره می‌کند.

---

## 15. Garbage Collector و ارتباط آن با JavaScript Engine

### توضیح ساده
Garbage Collector (GC) مانند یک نظافتچی خودکار است که به‌طور دوره‌ای انبار (Heap) را بررسی می‌کند و هر چیزی را که دیگر هیچ‌کس به آن اشاره نمی‌کند، دور می‌ریزد تا فضا خالی شود.

### تعریف فنی
- **Reachability:** اصلی‌ترین مفهوم GC. هر چیزی که از ریشه (Roots، مثل متغیرهای Global یا Call Stack فعلی) قابل دسترسی باشد، زنده است.
- **Mark-and-Sweep:** الگوریتم رایج GC. ابتدا همه اشیاء قابل‌دسترسی را "علامت‌گذاری" (Mark) می‌کند، سپس همه اشیاء علامت‌گذاری‌نشده را "پاک‌سازی" (Sweep) می‌کند.
- **Generational GC:** اشیاء به دو نسل Young (تازه‌ساخت) و Old (قدیمی) تقسیم می‌شوند. Minor GC نسل جوان را سریع پاک می‌کند، Major GC کل Heap را بررسی می‌کند.
- **Stop-the-World:** در حین برخی مراحل GC، اجرای کد JavaScript به‌طور موقت متوقف می‌شود (اگرچه موتورهای مدرن این زمان را به حداقل رسانده‌اند).

### مثال
```javascript
let user = { name: "Ali" };
user = null; // اشاره‌گر به شیء قطع شد.
```
اکنون شیء `{ name: "Ali" }` غیرقابل‌دسترسی (Unreachable) است. در دور بعدی GC، این شیء به‌عنوان Garbage شناسایی و حافظه آن آزاد می‌شود.

### نکات مهم
توسعه‌دهنده نمی‌تواند GC را مستقیماً فراخوانی کند. Memory Leak زمانی رخ می‌دهد که اشیاء غیرضروری به‌طور ناخواسته "قابل‌دسترسی" باقی بمانند (مثلاً در Event Listenerهای ثبت‌شده یا Closureهای بزرگ).

---

## 16. Built-in Objects و Runtime Support

### توضیح ساده
ابزارهایی مثل `Array`، `Promise` یا `Math` جعبه‌ابزاری هستند که موتور در اختیار شما قرار می‌دهد تا مجبور نباشید آن‌ها را از صفر بنویسید.

### تعریف فنی
Built-in Objects اشیایی هستند که توسط **ECMAScript Specification** تعریف شده‌اند، اما **پیاده‌سازی** (Implementation) آن‌ها بر عهده JavaScript Engine است. موتور باید رفتار آن‌ها را دقیقاً مطابق با استاندارد تضمین کند.

### تفاوت با APIهای محیط اجرا
- `Array.prototype.map` یک Built-in استاندارد ECMAScript است (توسط Engine پیاده‌سازی شده).
- `document.getElementById` یک Web API است (توسط Browser Host پیاده‌سازی شده، نه Engine).

---

## 17. JavaScript Engine و Web APIs

### توضیح ساده
موتور JS فقط زبان را می‌فهمد. اگر بخواهید تایمر تنظیم کنید یا درخواست شبکه بفرستید، باید از امکانات محیط میزبان (مرورگر) کمک بگیرید.

### تعریف فنی
Web APIs (مثل `setTimeout`, `fetch`, `DOM`) بخشی از JavaScript Engine **نیستند**. آن‌ها توسط محیط میزبان (Browser) ارائه می‌شوند. موتور JS فقط می‌تواند توابعی را که Host در اختیار Global Object (مثل `window`) قرار داده، فراخوانی کند.

### مثال
```javascript
setTimeout(() => { console.log("Done"); }, 0);
```
موتور JS تابع `setTimeout` را به‌عنوان یک Built-in (که توسط Host تزریق شده) می‌شناسد و آن را اجرا می‌کند، اما عملیات شمارش زمان بر عهده Threadهای جداگانه مرورگر است، نه خود موتور JS.

---

## 18. JavaScript Engine و Event Loop

### توضیح ساده
Event Loop مانند یک مدیر پروژه است که مدام بررسی می‌کند: "آیا کار فوری (Call Stack) تمام شده؟ اگر بله، کارهای صف‌شده (مثل پاسخ شبکه یا تایمر) را یکی‌یکی انجام بده."

### تعریف فنی
Event Loop بخشی از JavaScript Engine **نیست**؛ بخشی از Host Environment (مرورگر یا Node.js) است.
- **Call Stack:** توابع در حال اجرا.
- **Task Queue (Macrotask):** کارهایی مثل `setTimeout`، `setInterval`.
- **Microtask Queue:** کارهایی با اولویت بالاتر مثل `Promise.then` و `queueMicrotask`.
- **Run-to-Completion:** هر Task تا پایان اجرا می‌شود و نمی‌تواند توسط Task دیگری قطع (Interrupt) شود.

### مثال
```javascript
console.log("A");
setTimeout(() => console.log("B"), 0);
Promise.resolve().then(() => console.log("C"));
console.log("D");
```
**خروجی:** `A`, `D`, `C`, `B`
**توضیح:** `A` و `D` همگام (Synchronous) اجرا می‌شوند. سپس Microtask Queue (`C`) قبل از Task Queue (`B`) پردازش می‌شود.

---

## 19. JavaScript Engine و Type System

### توضیح ساده
JavaScript نمی‌داند یک متغیر قرار است چه نوع داده‌ای داشته باشد. این انعطاف‌پذیری برای توسعه‌دهنده راحت است، اما موتور را مجبور می‌کند در هر مرحله نوع داده را بررسی کند که کُند است.

### تعریف فنی
JavaScript دارای **Dynamic Typing** است. موتور باید در زمان اجرا (Runtime) نوع داده‌ها را بررسی کند. موتورهای مدرن از **Type Feedback** استفاده می‌کنند تا حدس بزنند نوع داده چیست و کد را بهینه کنند. اگر نوع تغییر کند، بهینه‌سازی باطل می‌شود.

### مثال
```javascript
let value = 10; // موتور فرض می‌کند Integer است و عملیات ریاضی سریع انجام می‌دهد.
value = "Hello"; // نوع تغییر کرد. موتور باید کد بهینه‌شده را دور بریزد (Deoptimization).
```

---

## 20. Hidden Classes و Shapes

### توضیح ساده
برخلاف تصور، اشیاء در JavaScript Engine مانند دیکشنری‌های کُند (Hash Tables) مدیریت نمی‌شوند. موتور برای اشیایی که ساختار مشابه دارند، یک "قالب پنهان" (Hidden Class) می‌سازد تا دسترسی به ویژگی‌ها (Properties) بسیار سریع، شبیه به کلاس‌ها در C++ باشد.

### تعریف فنی
- **Hidden Class (یا Shape/Map در موتورهای مختلف):** ساختار داخلی که موتور برای ردیابی Layout اشیاء استفاده می‌کند.
- وقتی اشیاء با ترتیب و نام ویژگی‌های یکسان ساخته شوند، Hidden Class آن‌ها به اشتراک گذاشته می‌شود (Shared)، که دسترسی به Property را بهینه می‌کند.

### مثال
```javascript
const user1 = { name: "Ali", age: 25 };
const user2 = { name: "Sara", age: 30 };
```
هر دو شیء یک Hidden Class را به اشتراک می‌گذارند. اما اگر `user3 = { age: 30, name: "Reza" }` (ترتیب متفاوت) باشد، ممکن است Hidden Class متفاوتی ایجاد شود که بهینه‌سازی را کاهش می‌دهد.

---

## 21. Inline Caching

### توضیح ساده
اگر مدام از یک تابع بخواهید نام یک کاربر را بگیرد، موتور به جای اینکه هر بار کل ساختار شیء را جستجو کند، آدرس دقیق آن ویژگی را در حافظه "به خاطر می‌سپارد".

### تعریف فنی
Inline Caching (IC) تکنیکی است که موتور برای ذخیره نتیجه جستجوی Property در محل فراخوانی استفاده می‌کند.
- **Monomorphic:** تابع همیشه با اشیایی از یک Hidden Class فراخوانی شده (سریع‌ترین حالت).
- **Polymorphic:** تعداد محدودی (معمولاً تا 4) Hidden Class مختلف دیده شده است.
- **Megamorphic:** تعداد زیادی Hidden Class مختلف دیده شده (IC غیرفعال می‌شود و عملکرد کند می‌شود).

---

## 22. Deoptimization

### توضیح ساده
گاهی موتور حدس اشتباهی می‌زند و کد را بیش‌ازحد بهینه می‌کند. وقتی واقعیت با حدس موتور مغایرت پیدا می‌کند، موتور مجبور است کد بهینه‌شده را دور بریزد و به حالت کندتر اما مطمئن‌تر بازگردد. این یک "خرابی" نیست، بلکه یک مکانیزم ایمنی هوشمند است.

### تعریف فنی
Deoptimization فرآیند بازگشت از کد ماشین بهینه‌شده (Optimized Machine Code) به بایت‌کد (Bytecode) یا کد کمتر بهینه‌شده است، زیرا Type Feedback یا فرضیات Hidden Class نقض شده‌اند.

---

## 23. JavaScript Engine و Closures

### توضیح ساده
Closure زمانی رخ می‌دهد که یک تابع، متغیرهای تابع بیرونی خود را "به یاد" می‌سپارد، حتی پس از اینکه تابع بیرونی اجرا و تمام شده است.

### تعریف فنی
موتور برای حفظ این متغیرها، آن‌ها را در Heap نگه می‌دارد (نه در Call Stack که با پایان تابع پاک می‌شود). این کار از طریق **Lexical Environment** مدیریت می‌شود.

### مثال
```javascript
function createCounter() {
  let count = 0; // در Heap نگه داشته می‌شود چون توسط Closure استفاده می‌شود
  return function() {
    count++;
    return count;
  };
}
const counter = createCounter();
console.log(counter()); // 1
```
**نکته:** Closureها اگر به‌درستی مدیریت نشوند (مثلاً نگهداری ارجاع به اشیاء بزرگ DOM)، می‌توانند منجر به Memory Leak شوند.

---

## 24. JavaScript Engine و Modules

### توضیح ساده
ماژول‌ها به شما اجازه می‌دهند کد را به فایل‌های جداگانه تقسیم کنید. موتور باید بداند کدام متغیرها خصوصی هستند و کدام‌یک صادر (Export) می‌شوند.

### تعریف فنی
- **Script:** کد سنتی که در یک Scope جهانی اجرا می‌شود.
- **Module:** کدی که دارای Scope مستقل است و از `import`/`export` پشتیبانی می‌کند.
- **Module Loader:** مسئولیت بارگذاری و حل‌وفصل (Resolution) مسیر ماژول‌ها بر عهده **Host Environment** است، نه خود Engine. Engine فقط Module Record (ساختار داخلی AST ماژول) را پردازش می‌کند.

---

## 25. JavaScript Engine و Async/Await

### توضیح ساده
`async/await` فقط یک روش خوانا برای نوشتن Promiseها است. این دستور هیچ Thread جدیدی ایجاد نمی‌کند و کل برنامه را متوقف نمی‌کند، بلکه فقط اجرای *همان تابع* را موقتاً متوقف می‌کند تا نتیجه آماده شود.

### تعریف فنی
وقتی به `await` می‌رسد، موتور تابع را متوقف (Suspend) می‌کند، Execution Context آن را حفظ کرده و کنترل را به Event Loop بازمی‌گرداند. وقتی Promise حل (Resolve) شد، یک Microtask ایجاد می‌شود تا اجرای تابع از همان نقطه ادامه یابد.

---

## 26. JavaScript Engine و WebAssembly

### توضیح ساده
WebAssembly (Wasm) یک فرمت کد باینری است که می‌تواند در کنار JavaScript در مرورگر اجرا شود. برای کارهای سنگین محاسباتی (مثل بازی یا ویرایش ویدیو) عالی است، اما قرار نیست جایگزین JS شود.

### تعریف فنی
موتورهای مدرن JS (مثل V8 و JSC) دارای کامپایلرهای داخلی WebAssembly هستند. Wasm به Machine Code کامپایل می‌شود و سرعت اجرای نزدیک به C++ را فراهم می‌کند، در حالی که JS برای تعامل با DOM و منطق برنامه باقی می‌ماند.

---

## 27. JavaScript Engine و چندنخی بودن

### توضیح ساده
کد JavaScript شما فقط در یک خط (تک‌نخی) اجرا می‌شود. اما محیط میزبان (مرورگر یا Node.js) می‌تواند از چندین Thread برای کارهای پس‌زمینه (مثل شبکه یا تایمر) استفاده کند.

### تعریف فنی
- **Single-Threaded:** موتور JS یک Call Stack اصلی دارد.
- **Web Workers / Node Worker Threads:** اجازه می‌دهند کد JS در یک Thread جداگانه با Call Stack و Heap مستقل اجرا شود. ارتباط بین آن‌ها از طریق پیام‌رسانی (Message Passing) است، نه حافظه مشترک (مگر با `SharedArrayBuffer` که نیازمند مدیریت دقیق با `Atomics` است).
- **Concurrency vs Parallelism:** JS ناهمگامی (Concurrency) را از طریق Event Loop مدیریت می‌کند، نه پردازش موازی (Parallelism) واقعی در یک Thread.

---

## 28. JavaScript Engine و Performance

### توضیح ساده
سرعت کد فقط به الگوریتم شما بستگی ندارد، بلکه به این بستگی دارد که موتور چقدر می‌تواند آن را بهینه کند. تغییر مکرر نوع داده‌ها یا ساختار اشیاء، موتور را مجبور به کار اضافه (Deoptimization) می‌کند.

### نکات مهم
- از **Microbenchmark**ها (مثل تست سرعت یک حلقه خاص) با احتیاط استفاده کنید؛ موتورهای مدرن ممکن است کد تست را آن‌قدر بهینه کنند که با دنیای واقعی متفاوت باشد.
- **Premature Optimization:** ابتدا کد را خوانا و صحیح بنویسید، سپس با ابزارهای Profiling گلوگاه‌ها را پیدا کنید.
- ثبات در نوع داده‌ها (Consistent Types) و ساختار اشیاء (Consistent Shapes) به Inline Caching و JIT کمک می‌کند.

---

## 29. JavaScript Engine و ابزارهای توسعه‌دهنده

### توضیح ساده
برای درک رفتار موتور، نیازی به حدس زدن نیست. مرورگرها ابزارهای قدرتمندی برای مشاهده Call Stack، مصرف حافظه و زمان اجرا ارائه می‌دهند.

### ابزارهای کلیدی (Chrome DevTools)
- **Performance Panel:** ضبط و تحلیل اجرای کد، شناسایی توابع پرتکرار و توقف‌های Garbage Collector.
- **Memory Panel:** گرفتن Heap Snapshot برای پیدا کردن Memory Leakها.
- **`console.time("label")` / `console.timeEnd("label")`:** اندازه‌گیری ساده زمان اجرا.
- **`performance.now()`:** اندازه‌گیری زمان با دقت زیرمیلی‌ثانیه.

---

## 30. Debugging در JavaScript Engine

### انواع خطاها
- **Syntax Error:** توسط Parser شناسایی می‌شود (قبل از اجرا).
- **ReferenceError:** متغیری تعریف نشده است.
- **TypeError:** عملیات روی نوع داده نامعتبر (مثلاً فراخوانی چیزی که تابع نیست).

### نکات مهم
- **Stack Trace:** ردیابی معکوس فراخوانی توابع در Call Stack در لحظه وقوع خطا.
- **Source Map:** ابزاری که کد Machine/Minified را به کد اصلی توسعه‌دهنده نگاشت می‌کند تا Debugging ممکن باشد.
- هر خطایی توسط Engine تولید نمی‌شود؛ برخی خطاها (مثل 404 Network Error) توسط Host Environment گزارش می‌شوند.

---

## 31. JavaScript Engine و امنیت

### توضیح ساده
موتور JS در یک محیط ایزوله (Sandbox) اجرا می‌شود تا کدهای مخرب نتوانند به فایل‌های سیستم یا داده‌های کاربر آسیب برسانند.

### تعریف فنی
- **Sandbox:** محدودیت‌های اعمال‌شده توسط Host Environment. مثلاً JS در مرورگر به‌طور پیش‌فرض دسترسی به فایل‌سیستم ندارد.
- **Prototype Pollution:** یک آسیب‌پذیری منطقی در JS که در آن مهاجم می‌تواند ویژگی‌هایی را به `Object.prototype` تزریق کند و رفتار تمام اشیاء را تغییر دهد. Engine این را به‌عنوان خطا نمی‌شناسد، زیرا از نظر فنی یک عملیات معتبر JS است، اما Host/Developer باید از آن جلوگیری کند.

---

## 32. تفاوت استاندارد ECMAScript با پیاده‌سازی Engine

### توضیح ساده
استاندارد ECMAScript مانند "قانون اساسی" زبان است که می‌گوید زبان *باید* چگونه رفتار کند. JavaScript Engine "دولت" یا "مجری" است که تصمیم می‌گیرد *چگونه* این قوانین را با بهترین سرعت و کارایی اجرا کند.

### تعریف فنی
- **TC39:** کمیته‌ای که استاندارد ECMAScript را توسعه می‌دهد.
- **Specification vs Implementation:** استاندارد رفتار `Array.prototype.map` را تعریف می‌کند، اما نمی‌گوید V8 باید از Ignition یا TurboFan استفاده کند.
- **Test262:** مجموعه تست رسمی برای اطمینان از انطباق (Compatibility) موتورهای مختلف با استاندارد.

---

## 33. ساخت یک JavaScript Engine ساده — بخش آموزشی

> **هشدار:** این یک مدل بسیار ساده‌شده آموزشی است. موتورهای واقعی صدها هزار خط کد C++ هستند.

فرض کنید می‌خواهیم این کد را اجرا کنیم: `let x = 10; let y = 20; x + y;`

### 1. Tokenization
```javascript
// ورودی: "let x = 10;"
// خروجی: [{type: "LET"}, {type: "IDENTIFIER", value: "x"}, {type: "EQUALS"}, {type: "NUMBER", value: 10}]
```

### 2. Parsing (به AST)
```json
{
  "type": "Program",
  "body": [
    {
      "type": "VariableDeclaration",
      "kind": "let",
      "declarations": [{ "id": "x", "init": 10 }]
    }
  ]
}
```

### 3. Evaluation (Interpreter ساده)
```javascript
const environment = {}; // حافظه متغیرها

function evaluate(node) {
  if (node.type === "VariableDeclaration") {
    environment[node.declarations[0].id] = node.declarations[0].init;
  } else if (node.type === "BinaryExpression") {
    return evaluate(node.left) + evaluate(node.right);
  } else if (node.type === "Identifier") {
    return environment[node.name];
  } else if (node.type === "NumberLiteral") {
    return node.value;
  }
}
// اجرای x + y مقدار 30 را برمی‌گرداند.
```

---

## 34. باورهای غلط رایج درباره JavaScript Engine

1. **باور غلط:** JavaScript همیشه خط‌به‌خط اجرا می‌شود.
   **واقعیت:** موتور کد را Parse و بهینه می‌کند. توابع پرتکرار به کد ماشین کامپایل می‌شوند و ترتیب اجرای فیزیکی با ترتیب متنی کد متفاوت است.

2. **باور غلط:** JavaScript هیچ‌وقت Compile نمی‌شود.
   **واقعیت:** موتورهای مدرن از JIT Compilation گسترده استفاده می‌کنند.

3. **باور غلط:** JavaScript Engine همان مرورگر است.
   **واقعیت:** Engine فقط یک جزء از مرورگر است (در کنار Rendering Engine و Network Stack).

4. **باور غلط:** Node.js همان V8 است.
   **واقعیت:** Node.js = V8 + libuv + C++ Core Modules. V8 به تنهایی نمی‌تواند فایل بخواند.

5. **باور غلط:** Event Loop کاملاً داخل Engine قرار دارد.
   **واقعیت:** Event Loop بخشی از Host Environment (مرورگر/Node.js) است، نه موتور JS.

6. **باور غلط:** `setTimeout(..., 0)` یعنی اجرای فوری.
   **واقعیت:** یعنی "در سریع‌ترین زمان ممکن *پس از خالی شدن Call Stack و Microtask Queue* اجرا شود".

7. **باور غلط:** JavaScript همیشه فقط یک Thread دارد.
   **واقعیت:** خود زبان تک‌نخی است، اما محیط میزبان می‌تواند از Web Workers یا Worker Threads برای اجرای موازی استفاده کند.

8. **باور غلط:** Garbage Collector تمام Memory Leakها را حل می‌کند.
   **واقعیت:** GC فقط اشیاء *غیرقابل‌دسترسی* را پاک می‌کند. اگر ارجاعی به شیء باقی بماند (حتی ناخواسته)، Leak رخ می‌دهد.

9. **باور غلط:** JIT همیشه باعث سریع‌تر شدن همه کدها می‌شود.
   **واقعیت:** JIT سربار (Overhead) دارد. برای کدهایی که فقط یک بار اجرا می‌شوند، Interpreter سریع‌تر است.

10. **باور غلط:** هر متغیر دقیقاً در Stack یا Heap قرار دارد.
    **واقعیت:** موتورهای مدرن از تکنیک‌هایی مثل "Escape Analysis" استفاده می‌کنند و ممکن است اشیایی که فرار نمی‌کنند را به‌طور بهینه در Stack قرار دهند، نه لزوماً Heap.

---

## 35. جمع‌بندی نهایی

- **JavaScript Engine چیست؟** برنامه‌ای که کد JS را به دستورالعمل‌های قابل‌فهم برای CPU تبدیل می‌کند.
- **چه چیزی را اجرا می‌کند؟** کد ECMAScript + Built-in Objects.
- **مراحل اجرا:** Source Code → Parser → AST → Bytecode → Interpreter → (JIT Optimization) → Machine Code.
- **نقش Interpreter:** اجرای سریع اولیه و جمع‌آوری اطلاعات (Type Feedback).
- **نقش JIT:** تبدیل کدهای پرتکرار به کد ماشین بهینه‌شده برای حداکثر سرعت.
- **Call Stack:** مدیریت توابع در حال اجرا (LIFO).
- **Heap:** مدیریت حافظه پویا برای اشیاء و Closureها.
- **Garbage Collector:** آزادسازی خودکار حافظه اشیاء غیرقابل‌دسترسی (Reachability).
- **Event Loop:** متعلق به Host Environment است و ناهمگامی (Asynchrony) را مدیریت می‌کند.
- **تفاوت Engine و Runtime:** Engine فقط زبان را اجرا می‌کند؛ Runtime = Engine + APIs + Event Loop.
- **چرا این دانش مفید است؟** به شما کمک می‌کند کدی بنویسید که نه‌تنها صحیح، بلکه از نظر مصرف حافظه و سرعت، با نحوه تفکر موتور هماهنگ باشد (مثل حفظ ثبات انواع داده‌ها و ساختار اشیاء).

---

## منابع

برای مطالعه عمیق‌تر و بررسی صحت فنی مطالب، از منابع رسمی زیر استفاده شده است:

1. **MDN Web Docs** - مستندات جامع برای مفاهیم زبان، Event Loop و Web APIs.
   - [MDN: Concurrency model and the event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Event_loop)
2. **ECMAScript Language Specification** - مرجع نهایی رفتار زبان.
   - [ECMA-262 Standard](https://tc39.es/ecma262/)
3. **V8 Official Documentation** - جزئیات معماری Ignition, TurboFan, Maglev و Sparkplug.
   - [V8 Docs: JavaScript engine basics](https://v8.dev/docs)
   - [V8 Blog: Launching Ignition and TurboFan](https://v8.dev/blog/ignition-and-turbofan)
4. **Mozilla SpiderMonkey Documentation** - معماری موتور Firefox.
   - [SpiderMonkey Internals](https://spidermonkey.dev/)
5. **WebKit JavaScriptCore Documentation** - معماری موتور Safari.
   - [WebKit JavaScriptCore](https://webkit.org/javascriptcore/)
6. **Node.js Official Documentation** - معماری Node.js و نقش libuv.
   - [Node.js Docs: The Node.js Event Loop, Timers, and process.nextTick()](https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick/)
7. **WHATWG HTML Standard** - تعریف رسمی Web APIs و تعامل با موتور JS.
   - [WHATWG Event Loop](https://html.spec.whatwg.org/multipage/webappapis.html#event-loop)

---
*این راهنما با هدف آموزش دقیق و ساختارمند تهیه شده است. برای به‌روز نگه‌داشتن دانش، همیشه مستندات رسمی موتورهای هدف (مثل V8) را برای تغییرات معماری در نسخه‌های جدید بررسی کنید.*
