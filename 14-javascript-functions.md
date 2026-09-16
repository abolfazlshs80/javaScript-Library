# سرفصل کلی

آموزش باید حداقل شامل تمام موضوعات زیر باشد و اگر موضوع مهم دیگری درباره Function در JavaScript وجود دارد که در این فهرست نیست، آن را نیز در جای مناسب اضافه کن.

## 1. Function چیست؟

توضیح ساده:

* Function چیست؟
* چرا از Function استفاده می‌کنیم؟
* Function چه مشکلی را حل می‌کند؟
* مفهوم Reusability
* کاهش تکرار کد
* خوانایی و نگهداری کد
* Function به عنوان یک Block از کد
* Function Input و Output

مثال ساده:

```js
function sayHello() {
    return "hello";
}
```

توضیح بده:

* `function`
* نام Function
* `()`
* `{ }`
* `return`

---

# 2. تعریف و اجرای Function

توضیح بده که تعریف کردن Function با اجرای آن متفاوت است.

مثال:

```js
function functionName() {
    return "hello";
}
```

سپس:

```js
const result = functionName();
console.log(result);
```

توضیح کامل مفهوم:

* Function Definition
* Function Call
* Function Invocation
* Return Value
* ذخیره کردن نتیجه Function در یک Variable

توضیح بده:

```js
functionName()
```

چه اتفاقی می‌افتد.

همچنین تفاوت این دو را توضیح بده:

```js
functionName
```

و:

```js
functionName()
```

---

# 3. Function Declaration

توضیح کامل `Function Declaration`.

مثال:

```js
function sum1() {
    return "declaration";
}
```

توضیح:

* Syntax
* نحوه تعریف
* نحوه فراخوانی
* ویژگی‌های Function Declaration
* Hoisting در Function Declaration
* تفاوت Declaration با Expression

مثال Hoisting:

```js
sayHello();

function sayHello() {
    console.log("Hello");
}
```

توضیح بده چرا این کد کار می‌کند.

---

# 4. Function Expression

توضیح کامل `Function Expression`.

مثال:

```js
const sum2 = function () {
    return "expression";
};
```

توضیح:

* Function Expression چیست؟
* Anonymous Function چیست؟
* چرا Function را داخل Variable قرار می‌دهیم؟
* چگونه Function Expression را اجرا کنیم؟
* تفاوت Function Declaration و Function Expression

مثال:

```js
const greet = function () {
    console.log("Hello");
};

greet();
```

همچنین Hoisting مربوط به Function Expression را با Declaration مقایسه کن.

---

# 5. Anonymous Function

توضیح بده:

```js
function () {
    console.log("Hello");
}
```

چرا این Function نام ندارد و کجا استفاده می‌شود.

مثال‌های کاربردی Anonymous Function را توضیح بده.

---

# 6. Arrow Function

توضیح کامل Arrow Function از ساده تا پیشرفته.

مثال:

```js
const sum2 = () => {
    return "expression";
};
```

سپس Syntax کوتاه‌تر:

```js
const sum2 = () => "expression";
```

توضیح بده:

* Arrow Function چیست؟
* Syntax
* تفاوت با Function معمولی
* Implicit Return
* Explicit Return
* Parentheses
* یک Parameter
* چند Parameter
* بدون Parameter

مثال:

```js
const square = number => number * number;
```

و:

```js
const add = (a, b) => a + b;
```

---

# 7. Parameters و Arguments

این بخش را کاملاً ساده توضیح بده.

مثال:

```js
function greetings1(user1, user2, user3) {
    console.log(
        "welcome " + user1 +
        " and " + user2 +
        " and " + user3
    );
}
```

سپس:

```js
greetings1("ali", "reza", "hamid");
```

توضیح دقیق:

* Parameter چیست؟
* Argument چیست؟
* تفاوت Parameter و Argument
* ترتیب Arguments
* تعداد کمتر از Parameters
* تعداد بیشتر از Parameters
* مقدار `undefined`

مثال:

```js
function greet(name) {
    console.log(name);
}

greet();
```

---

# 8. Default Parameters

توضیح کامل Default Parameter.

مثال:

```js
function greet(name = "Guest") {
    console.log("Hello " + name);
}
```

توضیح بده:

```js
greet();
```

و:

```js
greet("Ali");
```

چه تفاوتی دارند.

همچنین بررسی کن اگر مقدار `undefined` ارسال شود چه اتفاقی می‌افتد.

---

# 9. Rest Parameters

توضیح ساده Rest Parameter.

مثال:

```js
function sum(...numbers) {
    console.log(numbers);
}

sum(1, 2, 3, 4);
```

توضیح بده چرا `...numbers` یک Array می‌سازد.

تفاوت Rest Parameter و Spread Syntax را توضیح بده.

---

# 10. Spread Syntax در Function Call

این مثال را حتماً توضیح بده:

```js
const names = ["ali", "reza", "hamid"];

greetings1("sara", ...names);
```

توضیح مرحله‌به‌مرحله:

```js
...names
```

چه کاری انجام می‌دهد.

قبل از Spread:

```js
greetings1("sara", names);
```

و بعد از Spread:

```js
greetings1("sara", ...names);
```

را مقایسه کن.

---

# 11. Return

توضیح کامل `return`.

مثال:

```js
function add(a, b) {
    return a + b;
}

const result = add(10, 20);

console.log(result);
```

توضیح:

* `return` چیست؟
* چرا از Return استفاده می‌کنیم؟
* Return کردن مقدار
* Return کردن String
* Return کردن Number
* Return کردن Boolean
* Return کردن Object
* Return کردن Array
* Return کردن Function

همچنین توضیح بده `return` باعث پایان اجرای Function می‌شود.

مثال:

```js
function test() {
    return "hello";

    console.log("this will not execute");
}
```

---

# 12. Function بدون Return

مثال:

```js
function test() {
    console.log("Hello");
}

const result = test();

console.log(result);
```

توضیح بده چرا مقدار `undefined` دریافت می‌کنیم.

تفاوت:

```js
console.log()
```

با:

```js
return
```

را کاملاً توضیح بده.

---

# 13. Scope در Function

توضیح ساده و سپس پیشرفته:

* Global Scope
* Function Scope
* Block Scope
* Local Variable
* Global Variable

مثال:

```js
function test() {
    const message = "hello";
    console.log(message);
}

test();

console.log(message);
```

توضیح بده چرا خطا ایجاد می‌شود.

---

# 14. Nested Functions

توضیح Function داخل Function.

مثال:

```js
function outer() {

    function inner() {
        console.log("inner");
    }

    inner();
}

outer();
```

توضیح:

* Nested Function چیست؟
* Scope آن چگونه کار می‌کند؟
* دسترسی Function داخلی به متغیرهای بیرونی

---

# 15. Callback Function

توضیح ساده Callback.

ابتدا مفهوم را بدون APIهای پیچیده توضیح بده.

مثال:

```js
function greet(name) {
    console.log("Hello " + name);
}

function processUser(callback) {
    callback("Ali");
}

processUser(greet);
```

توضیح بده چرا Function می‌تواند به عنوان Argument ارسال شود.

---

# 16. Function به عنوان First-Class Citizen

توضیح بده که در JavaScript Function یک مقدار است.

بررسی کن که Function می‌تواند:

* در Variable ذخیره شود
* به عنوان Argument ارسال شود
* از Function دیگر Return شود
* داخل Object قرار بگیرد
* داخل Array قرار بگیرد

مثال برای هر مورد ارائه کن.

---

# 17. Higher-Order Function

توضیح ساده Higher-Order Function.

تعریف:

Functionای که:

* Function دریافت می‌کند
* یا Function برمی‌گرداند
* یا هر دو

مثال:

```js
function operation(a, b, callback) {
    return callback(a, b);
}

const result = operation(10, 20, (x, y) => x + y);

console.log(result);
```

---

# 18. Functions Returning Functions

مثال:

```js
function createGreeting(message) {
    return function (name) {
        return message + " " + name;
    };
}

const greet = createGreeting("Hello");

console.log(greet("Ali"));
```

این مثال را از پایه توضیح بده و سپس مفهوم Closure را به آن مرتبط کن.

---

# 19. Closure

توضیح Closure از صفر.

مثال:

```js
function outer() {
    let counter = 0;

    return function () {
        counter++;
        return counter;
    };
}

const increment = outer();

console.log(increment());
console.log(increment());
console.log(increment());
```

توضیح ساده:

* Closure چیست؟
* چرا Function داخلی هنوز به `counter` دسترسی دارد؟
* Lexical Scope
* کاربردهای Closure
* Private State
* Factory Functions

---

# 20. Recursion

این بخش بسیار مهم است و مثال‌های زیر را حتماً توضیح بده.

## مثال اول:

```js
function countDown(number) {
    console.log(number);

    let nextNumber = number - 1;

    if (nextNumber >= 0) {
        countDown(nextNumber);
    }
}

countDown(10);
```

توضیح مرحله‌به‌مرحله اجرای:

```text
countDown(10)
countDown(9)
countDown(8)
...
countDown(0)
```

مفهوم:

* Recursion چیست؟
* Recursive Function چیست؟
* Base Case چیست؟
* Recursive Case چیست؟
* چرا بدون Base Case ممکن است اجرای Function ادامه پیدا کند؟
* Call Stack و Recursion

---

# 21. مثال Recursive برای Sum

این مثال را کامل توضیح بده:

```js
function sum(number) {
    if (number < 1) return number;

    return number + sum(number - 1);
}

console.log(sum(10));
```

برای مثال `sum(3)` اجرای مرحله‌به‌مرحله را نشان بده:

```text
sum(3)
3 + sum(2)

sum(2)
2 + sum(1)

sum(1)
1 + sum(0)

sum(0)
0
```

و در مرحله برگشت:

```text
sum(0) = 0
sum(1) = 1
sum(2) = 3
sum(3) = 6
```

توضیح بده چرا این Function در نهایت `6` برمی‌گرداند.

---

# 22. Call Stack و Function Execution

به زبان ساده توضیح بده:

* Call Stack چیست؟
* وقتی Function اجرا می‌شود چه اتفاقی می‌افتد؟
* Function چگونه وارد Stack می‌شود؟
* چگونه خارج می‌شود؟
* ارتباط Call Stack با Recursion

مثال ساده ارائه کن.

---

# 23. Function Hoisting

توضیح کامل Hoisting مربوط به Function.

این موارد را مقایسه کن:

### Function Declaration

```js
hello();

function hello() {
    console.log("Hello");
}
```

### Function Expression

```js
hello();

const hello = function () {
    console.log("Hello");
};
```

### Arrow Function

```js
hello();

const hello = () => {
    console.log("Hello");
};
```

نتیجه هرکدام را توضیح بده و دلیل آن را بیان کن.

---

# 24. `this` در Function

توضیح `this` از پایه.

ابتدا مفهوم ساده:

```js
const user = {
    name: "Ali",

    sayHello: function () {
        console.log(this.name);
    }
};

user.sayHello();
```

سپس تفاوت `this` در:

* Regular Function
* Arrow Function
* Object Method
* Function Call
* Method Call

را توضیح بده.

---

# 25. Arrow Function و `this`

توضیح بده چرا Arrow Function رفتار متفاوتی نسبت به Regular Function دارد.

مثال:

```js
const user = {
    name: "Ali",

    sayHello: () => {
        console.log(this.name);
    }
};
```

توضیح بده چرا نباید به صورت ساده فرض کنیم Arrow Function، `this` مربوط به Object را دریافت می‌کند.

---

# 26. Function Methods

مفاهیم مهم مربوط به Function را توضیح بده:

* `call()`
* `apply()`
* `bind()`

برای هرکدام:

* تعریف ساده
* Syntax
* مثال
* کاربرد
* تفاوت با یکدیگر

مثال:

```js
function greet(message) {
    console.log(message + " " + this.name);
}

const user = {
    name: "Ali"
};

greet.call(user, "Hello");
```

---

# 27. IIFE

توضیح:

`Immediately Invoked Function Expression`

مثال:

```js
(function () {
    console.log("Hello");
})();
```

توضیح:

* IIFE چیست؟
* چرا بلافاصله اجرا می‌شود؟
* کاربردهای تاریخی و امروزی
* ارتباط آن با Scope

همچنین نمونه Arrow Function:

```js
(() => {
    console.log("Hello");
})();
```

---

# 28. Pure Function

توضیح مفهوم Pure Function.

مثال:

```js
function add(a, b) {
    return a + b;
}
```

توضیح:

* Same Input → Same Output
* نداشتن Side Effect

سپس مثال یک Function غیر Pure ارائه کن.

---

# 29. Side Effect

توضیح:

* Side Effect چیست؟
* تغییر Variable بیرونی
* تغییر Object
* چاپ در Console
* درخواست شبکه
* تغییر DOM

مثال بزن و تفاوت Function Pure و Impure را توضیح بده.

---

# 30. Function و Object

توضیح بده که Function در JavaScript خودش یک Object قابل استفاده است و می‌تواند Property داشته باشد.

مثال:

```js
function test() {
    console.log("test");
}

test.description = "A test function";

console.log(test.description);
```

در صورت نیاز توضیح بده که Functionها در JavaScript دارای رفتار Object-like هستند.

---

# 31. Function Constructor و `new Function`

در سطح پیشرفته توضیح بده:

```js
const sum = new Function("a", "b", "return a + b");

console.log(sum(10, 20));
```

همچنین توضیح بده چرا استفاده معمول از این روش توصیه نمی‌شود و چه تفاوتی با Function Declaration و Expression دارد.

---

# 32. Generator Functions

در بخش Advanced معرفی کن:

```js
function* numbers() {
    yield 1;
    yield 2;
    yield 3;
}
```

توضیح:

* `function*`
* Generator
* `yield`
* `next()`
* Iterator
* کاربرد Generator

مثال:

```js
const generator = numbers();

console.log(generator.next());
console.log(generator.next());
console.log(generator.next());
```

---

# 33. Async Functions

در سطح پیشرفته توضیح بده:

```js
async function getData() {
    return "data";
}
```

توضیح:

* `async`
* Promise
* Return Value
* چرا Async Function یک Promise برمی‌گرداند

---

# 34. Function و Promise

مثال:

```js
async function getUser() {
    return {
        name: "Ali"
    };
}

getUser().then(user => {
    console.log(user);
});
```

ارتباط Function با Promise را توضیح بده.

---

# 35. Function Parameter پیشرفته

مفاهیم زیر را نیز توضیح بده:

* Destructuring Parameters
* Object Destructuring
* Array Destructuring
* Default Parameters
* Rest Parameters

مثال:

```js
function printUser({ name, age }) {
    console.log(name, age);
}

printUser({
    name: "Ali",
    age: 25
});
```

---

# 36. Function و Destructuring

مثال:

```js
function printNames([first, second]) {
    console.log(first);
    console.log(second);
}

printNames(["Ali", "Reza"]);
```

توضیح بده چگونه Argument به صورت Destructure شده دریافت می‌شود.

---

# 37. Recursion پیشرفته

بعد از توضیح ساده Recursion، مباحث زیر را معرفی کن:

* Recursive Tree
* Nested Data
* Directory Traversal
* Factorial
* Fibonacci
* Divide and Conquer
* خطر Stack Overflow
* تفاوت Recursion و Iteration
* Tail Recursion و وضعیت آن در JavaScript

برای هر مورد مثال ساده ارائه کن.

---

# 38. Function Composition

توضیح مفهوم Function Composition.

مثال:

```js
const addOne = x => x + 1;
const double = x => x * 2;

const result = double(addOne(5));

console.log(result);
```

سپس یک Function برای Composition بنویس.

---

# 39. Currying

توضیح ساده Currying.

مثال:

```js
function multiply(a) {
    return function (b) {
        return a * b;
    };
}

const multiplyByTwo = multiply(2);

console.log(multiplyByTwo(5));
```

توضیح ارتباط Currying با Closure.

---

# 40. Memoization

توضیح مفهوم Memoization در سطح پیشرفته.

* چرا استفاده می‌شود؟
* Cache کردن نتیجه Function
* چه زمانی مفید است؟
* چه زمانی ممکن است مناسب نباشد؟

مثال ساده ارائه کن.

---

# 41. Function Overloading

توضیح بده JavaScript مانند بعضی زبان‌ها Overloading سنتی بر اساس Signature ندارد.

مثال:

```js
function test(a, b) {
    // ...
}
```

توضیح بده چگونه می‌توان رفتارهای مختلف را با بررسی Arguments پیاده‌سازی کرد.

---

# 42. `arguments` Object

توضیح:

```js
function test() {
    console.log(arguments);
}

test(1, 2, 3);
```

توضیح:

* `arguments` چیست؟
* Array-like چیست؟
* تفاوت با Array
* تفاوت `arguments` با Rest Parameter
* چرا در JavaScript مدرن معمولاً Rest Parameter خواناتر است؟
* رفتار `arguments` در Arrow Function

---

# 43. Function Length و Name

توضیح Propertyهای مهم Function:

```js
function test(a, b, c) {}

console.log(test.length);
console.log(test.name);
```

توضیح:

* `length`
* `name`

و محدودیت‌ها و نکات مربوط به آن‌ها.

---

# 44. Function در Array

مثال:

```js
const operations = [
    () => console.log("add"),
    () => console.log("remove"),
    () => console.log("update")
];

operations[0]();
```

توضیح بده چرا Function می‌تواند داخل Array ذخیره شود.

---

# 45. Function در Object

مثال:

```js
const user = {
    name: "Ali",

    greet() {
        console.log("Hello");
    }
};

user.greet();
```

توضیح:

* Method چیست؟
* Function و Method چه تفاوت مفهومی دارند؟
* Method Shorthand

---

# 46. Factory Function

توضیح ساده Factory Function.

مثال:

```js
function createUser(name, age) {
    return {
        name,
        age
    };
}

const user1 = createUser("Ali", 25);
const user2 = createUser("Reza", 30);
```

توضیح کاربرد Factory Function.

---

# 47. Function Declaration vs Expression vs Arrow

یک مقایسه کامل و بدون رتبه‌بندی ارائه کن.

موارد مقایسه:

* Syntax
* Hoisting
* Name
* `this`
* `arguments`
* Constructor behavior
* استفاده معمول
* خوانایی

---

# 48. اشتباهات رایج در Function

حداقل این موارد را توضیح بده:

* فراموش کردن `return`
* اشتباه گرفتن `return` با `console.log`
* اشتباه گرفتن Parameter و Argument
* استفاده اشتباه از `()`
* اشتباه گرفتن Function Reference و Function Call
* Recursion بدون Base Case
* استفاده اشتباه از Arrow Function برای Object Method
* اشتباه گرفتن Rest و Spread
* انتظار Hoisting مشابه Declaration در Function Expression
* استفاده بیش از حد از Global Variable

برای هر مورد مثال اشتباه و نسخه صحیح ارائه کن.

---

# 49. Best Practices

نکات ساده و کاربردی:

* Function را کوچک و مشخص نگه داریم.
* نام Function باید نشان‌دهنده کاری باشد که انجام می‌دهد.
* از نام‌های واضح استفاده کنیم.
* از Side Effectهای غیرضروری جلوگیری کنیم.
* از Global Variableهای غیرضروری استفاده نکنیم.
* از Parameterهای بیش از حد زیاد جلوگیری کنیم.
* در صورت پیچیده شدن Function آن را به چند Function تقسیم کنیم.
* از Arrow Function و Regular Function بر اساس رفتار موردنیاز استفاده کنیم.
* Recursive Function باید Base Case مشخص داشته باشد.

---

# 50. پروژه کوچک برای تمرین

در پایان چند تمرین مرحله‌ای طراحی کن:

### Beginner

1. Function برای سلام کردن
2. Function جمع دو عدد
3. Function بررسی زوج یا فرد بودن
4. Function محاسبه مربع عدد

### Intermediate

5. Function دریافت چند نام
6. Function استفاده از Rest Parameter
7. Function استفاده از Callback
8. Function ایجاد User
9. Function فیلتر کردن داده‌ها

### Advanced

10. Recursive Countdown
11. Recursive Sum
12. Factorial
13. Closure Counter
14. Function Composition
15. Currying
16. Memoization

برای هر تمرین:

* صورت سؤال
* ورودی
* خروجی مورد انتظار
* یک Hint

ارائه کن، اما در بخش تمرین‌ها ابتدا جواب را نمایش نده.

---

# 51. Cheat Sheet

در پایان یک Cheat Sheet کوتاه برای Function تهیه کن که Syntaxهای مهم را شامل شود:

```js
function test() {}

function test(a) {}

function test(a, b) {}

const test = function () {};

const test = () => {};

const test = x => x * 2;

function test(...args) {}

function test(a = 10) {}

function outer() {
    return function inner() {};
}

function* generator() {}

async function test() {}
```

برای هرکدام یک توضیح بسیار کوتاه بنویس.

---

# 52. خروجی نهایی و ساختار Markdown

خروجی نهایی باید کاملاً مناسب GitHub و Markdown باشد.

در ابتدای آموزش یک مقدمه کوتاه قرار بده.

سپس یک **فهرست مطالب (Table of Contents)** ایجاد کن که به تمام Headingهای اصلی لینک داشته باشد.

ساختار پیشنهادی:

```md
# JavaScript Functions

## فهرست مطالب

- [Function چیست؟](#function-چیست)
- [Function Declaration](#function-declaration)
- [Function Expression](#function-expression)
- [Arrow Function](#arrow-function)
- ...
```

Headingها را به شکلی انتخاب کن که لینک‌های Markdown/GitHub به درستی کار کنند.

---


برای هر مفهوم از این الگو استفاده کن:

### تعریف ساده

یک توضیح کوتاه و قابل فهم.

### Syntax

```js
// syntax
```

### مثال ساده

```js
// example
```

### توضیح خط‌به‌خط

هر قسمت کد را توضیح بده.

### خروجی

```text
...
```

### نکته مهم

نکته‌ای که یک مبتدی باید بداند.

### اشتباه رایج

در صورت وجود، اشتباه رایج را نشان بده.

### مثال واقعی‌تر

در صورت امکان یک مثال کاربردی‌تر ارائه کن.

---

# 54. منابع

در پایان حتماً بخش:

```md
## منابع
```

قرار بده.

برای آموزش از منابع معتبر و رسمی استفاده کن و منابع را با لینک معتبر ارائه بده.

اولویت منابع:

1. MDN Web Docs
2. ECMAScript Specification
3. JavaScript.info
4. منابع آموزشی معتبر دیگر در صورت نیاز

برای هر منبع عنوان و لینک آن را قرار بده.

از لینک‌های ساختگی یا نامعتبر استفاده نکن.

---

# قوانین مهم تولید محتوا

1. آموزش را از صفر شروع کن.
2. فرض نکن خواننده Function را می‌شناسد.
3. ابتدا ساده، سپس متوسط، سپس پیشرفته.
4. اصطلاحات انگلیسی مهم را داخل پرانتز کنار معادل فارسی بنویس.
5. کدها با JavaScript مدرن باشند.
6. هیچ موضوع مهمی درباره Function را بدون توضیح رها نکن.
7. بین Function، Method، Callback، Higher-Order Function و Closure تفاوت را روشن کن.
8. بین Rest و Spread تفاوت را کاملاً مشخص کن.
9. بین Function Declaration، Function Expression و Arrow Function مقایسه دقیق انجام بده.
10. Recursion را با Call Stack توضیح بده.
11. برای مفاهیم پیچیده از مثال‌های کوچک استفاده کن.
12. از مثال‌های واقعی و قابل لمس استفاده کن.
13. خروجی کدها را در صورت امکان نمایش بده.
14. اشتباهات رایج را حتماً پوشش بده.
15. از تکرار بیهوده مطالب جلوگیری کن.
16. آموزش باید قابل مطالعه برای مبتدی باشد ولی در پایان تا سطح پیشرفته ادامه پیدا کند.
17. از منابع معتبر استفاده کن.
18. در پایان منابع را همراه لینک معتبر قرار بده.
19. هیچ لینک ساختگی تولید نکن.
20. متن نهایی باید تمیز، منظم و آماده قرار گرفتن در Repository باشد.
21. اگر در نسخه‌های جدید JavaScript تفاوت یا نکته‌ای وجود دارد، آن را با توجه به استاندارد ECMAScript توضیح بده.
22. در مواردی که یک رفتار به محیط اجرا وابسته است، این موضوع را صریحاً بیان کن.
23. برای مطالبی مانند `this`، `arguments`، Hoisting، Closure، Recursion و Async Function توضیح مرحله‌ای و مثال‌محور ارائه کن.
24. در پایان یک جمع‌بندی از مهم‌ترین مفاهیمی که یک JavaScript Developer باید درباره Function بداند ارائه کن.
25. محتوا را به صورت یک آموزش یکپارچه و منظم تولید کن، نه مجموعه‌ای از پاسخ‌های جداگانه.


### ASSISTANT
# آموزش جامع توابع (Functions) در JavaScript

به آموزش جامع و مرحله‌به‌مرحله **Function در JavaScript** خوش آمدید. این راهنما برای ریپوزیتوری‌های آموزشی طراحی شده و شما را از سطح کاملاً مبتدی تا مفاهیم پیشرفته همراهی می‌کند. هدف این است که با زبانی ساده، مثال‌های کاربردی و ساختاری منظم، درک عمیقی از توابع پیدا کنید.

---

## فهرست مطالب

1. [Function چیست؟](#1-function-چیست)
2. [تعریف و اجرای Function](#2-تعریف-و-اجرای-function)
3. [Function Declaration](#3-function-declaration)
4. [Function Expression](#4-function-expression)
5. [Anonymous Function](#5-anonymous-function)
6. [Arrow Function](#6-arrow-function)
7. [Parameters و Arguments](#7-parameters-و-arguments)
8. [Default Parameters](#8-default-parameters)
9. [Rest Parameters](#9-rest-parameters)
10. [Spread Syntax در Function Call](#10-spread-syntax-در-function-call)
11. [Return](#11-return)
12. [Function بدون Return](#12-function-بدون-return)
13. [Scope در Function](#13-scope-در-function)
14. [Nested Functions](#14-nested-functions)
15. [Callback Function](#15-callback-function)
16. [Function به عنوان First-Class Citizen](#16-function-به-عنوان-first-class-citizen)
17. [Higher-Order Function](#17-higher-order-function)
18. [Functions Returning Functions](#18-functions-returning-functions)
19. [Closure](#19-closure)
20. [Recursion](#20-recursion)
21. [مثال Recursive برای Sum](#21-مثال-recursive-برای-sum)
22. [Call Stack و Function Execution](#22-call-stack-و-function-execution)
23. [Function Hoisting](#23-function-hoisting)
24. [`this` در Function](#24-this-در-function)
25. [Arrow Function و `this`](#25-arrow-function-و-this)
26. [Function Methods](#26-function-methods)
27. [IIFE](#27-iife)
28. [Pure Function](#28-pure-function)
29. [Side Effect](#29-side-effect)
30. [Function و Object](#30-function-و-object)
31. [Function Constructor و `new Function`](#31-function-constructor-و-new-function)
32. [Generator Functions](#32-generator-functions)
33. [Async Functions](#33-async-functions)
34. [Function و Promise](#34-function-و-promise)
35. [Function Parameter پیشرفته](#35-function-parameter-پیشرفته)
36. [Function و Destructuring](#36-function-و-destructuring)
37. [Recursion پیشرفته](#37-recursion-پیشرفته)
38. [Function Composition](#38-function-composition)
39. [Currying](#39-currying)
40. [Memoization](#40-memoization)
41. [Function Overloading](#41-function-overloading)
42. [`arguments` Object](#42-arguments-object)
43. [Function Length و Name](#43-function-length-و-name)
44. [Function در Array](#44-function-در-array)
45. [Function در Object](#45-function-در-object)
46. [Factory Function](#46-factory-function)
47. [Function Declaration vs Expression vs Arrow](#47-function-declaration-vs-expression-vs-arrow)
48. [اشتباهات رایج در Function](#48-اشتباهات-رایج-در-function)
49. [Best Practices](#49-best-practices)
50. [پروژه کوچک برای تمرین](#50-پروژه-کوچک-برای-تمرین)
51. [Cheat Sheet](#51-cheat-sheet)
52. [منابع](#52-منابع)

---

## 1. Function چیست؟

### تعریف ساده
Function (تابع) مانند یک «دستگاه» یا «کارخانه» کوچک در کد است که یک کار مشخص را انجام می‌دهد. شما به آن مواد اولیه (ورودی) می‌دهید و آن محصول نهایی (خروجی) را به شما تحویل می‌دهد.

### چرا از Function استفاده می‌کنیم؟
* **Reusability (قابلیت استفاده مجدد)**: یک بار می‌نویسیم، بارها استفاده می‌کنیم.
* **کاهش تکرار کد (DRY)**: از نوشتن کدهای تکراری جلوگیری می‌کند.
* **خوانایی و نگهداری**: کد را به بخش‌های منطقی و کوچک تقسیم می‌کند.

### مثال ساده
```js
function sayHello() {
    return "hello";
}
```

### توضیح خط‌به‌خط
* `function`: کلمه کلیدی برای تعریف تابع.
* `sayHello`: نام تابع (باید توصیف‌کننده کار آن باشد).
* `()`: پرانتزهایی که ورودی‌ها (Parameters) را نگه می‌دارند (در اینجا خالی است).
* `{ }`: بلوک کد که دستورات تابع داخل آن قرار می‌گیرد.
* `return`: مقداری که تابع به عنوان خروجی برمی‌گرداند.

### خروجی
(هنوز اجرا نشده، فقط تعریف شده است).

### نکته مهم
Function تا زمانی که «فراخوانی» (Call) نشود، اجرا نمی‌شود.

---

## 2. تعریف و اجرای Function

### تعریف ساده
تعریف کردن (Definition) یعنی ساختن دستگاه؛ اجرای (Invocation/Call) یعنی روشن کردن و استفاده از آن.

### مثال
```js
function functionName() {
    return "hello";
}

const result = functionName();
console.log(result);
```

### توضیح خط‌به‌خط
1. `function functionName() { ... }`: تعریف تابع (ساخت دستگاه).
2. `functionName()`: فراخوانی تابع (روشن کردن دستگاه). پرانتز `()` دستور اجرا را صادر می‌کند.
3. `const result = ...`: مقدار بازگشتی (`"hello"`) در متغیر `result` ذخیره می‌شود.
4. `console.log(result)`: مقدار ذخیره‌شده چاپ می‌شود.

### خروجی
```text
hello
```

### نکته مهم
تفاوت `functionName` (ارجاع به خود تابع) با `functionName()` (اجرای تابع و دریافت نتیجه) بسیار حیاتی است.

### اشتباه رایج
نوشتن `const result = functionName;` (بدون پرانتز). در این حالت، به جای اجرا، خودِ کد تابع در متغیر ذخیره می‌شود.

---

## 3. Function Declaration

### تعریف ساده
روش کلاسیک و استاندارد تعریف تابع با کلمه کلیدی `function`.

### Syntax
```js
function name(param1, param2) {
    // body
}
```

### مثال
```js
function sum1() {
    return "declaration";
}
console.log(sum1());
```

### ویژگی‌ها و Hoisting
در JavaScript، **Function Declaration**ها به بالای Scope خود منتقل می‌شوند (Hoisting). یعنی می‌توانید قبل از تعریف، آن‌ها را فراخوانی کنید.

### مثال Hoisting
```js
sayHello(); // کار می‌کند!

function sayHello() {
    console.log("Hello");
}
```
**چرا کار می‌کند؟** موتور جاوااسکریپت قبل از اجرای کد، تعریف `sayHello` را در حافظه ثبت می‌کند.

---

## 4. Function Expression

### تعریف ساده
زمانی که یک تابع را به عنوان مقداری به یک متغیر اختصاص می‌دهیم.

### مثال
```js
const sum2 = function () {
    return "expression";
};
console.log(sum2());
```

### توضیح
* **Anonymous Function**: تابعی که نام ندارد (مثل مثال بالا).
* **چرا در Variable؟** برای مدیریت بهتر، پاس دادن به عنوان Callback، یا محدود کردن Scope.
* **تفاوت با Declaration**: Function Expressionها **Hoisting نمی‌شوند** (فقط اعلان متغیر Hoist می‌شود، نه مقدار تابع).

### مثال مقایسه Hoisting
```js
// greet(); // خطا: Cannot access 'greet' before initialization

const greet = function () {
    console.log("Hello");
};
greet(); // کار می‌کند
```

---

## 5. Anonymous Function

### تعریف ساده
تابعی که نام ندارد. معمولاً به عنوان مقدار به متغیرها اختصاص می‌یابد یا به عنوان آرگومان به توابع دیگر پاس داده می‌شود.

### مثال
```js
setTimeout(function() {
    console.log("Executed after 1 second");
}, 1000);
```

### نکته مهم
در دیباگ کردن، توابع بی‌نام ممکن است در Call Stack به صورت `(anonymous)` نمایش داده شوند که ردیابی خطا را سخت می‌کند. بهتر است در صورت امکان از Named Function Expression استفاده کنید.

---

## 6. Arrow Function

### تعریف ساده
روش مدرن و کوتاه‌تر نوشتن تابع که در ES6 معرفی شد.

### Syntax
```js
const name = (params) => { /* body */ };
```

### مثال و Implicit Return
```js
const sum2 = () => {
    return "expression";
};

// حالت کوتاه‌تر (Implicit Return)
const sum3 = () => "expression";

const square = number => number * number; // یک پارامتر: پرانتز اختیاری
const add = (a, b) => a + b; // چند پارامتر: پرانتز الزامی
const greet = () => console.log("Hi"); // بدون پارامتر: پرانتز خالی الزامی
```

### تفاوت با Regular Function
1. Syntax کوتاه‌تر.
2. `this` را به صورت Lexical (از محیط بیرونی) به ارث می‌برد.
3. شیء `arguments` را ندارد.
4. نمی‌تواند به عنوان Constructor (با `new`) استفاده شود.

---

## 7. Parameters و Arguments

### تعریف ساده
* **Parameter (پارامتر)**: متغیرهای تعریف‌شده در پرانتز تابع (مثل ظرف‌های خالی).
* **Argument (آرگومان)**: مقادیر واقعی که هنگام فراخوانی به تابع داده می‌شوند (مثل محتویات ظرف).

### مثال
```js
function greetings1(user1, user2, user3) {
    console.log("welcome " + user1 + " and " + user2 + " and " + user3);
}

greetings1("ali", "reza", "hamid");
```

### توضیح خط‌به‌خط
* `user1, user2, user3`: پارامترها هستند.
* `"ali", "reza", "hamid"`: آرگومان‌ها هستند که به ترتیب جایگزین پارامترها می‌شوند.

### حالت‌های خاص
* **تعداد کمتر Arguments**: پارامترهای بدون مقدار، `undefined` می‌شوند.
* **تعداد بیشتر Arguments**: آرگومان‌های اضافی نادیده گرفته می‌شوند (مگر با `arguments` یا Rest).

### مثال خطا
```js
function greet(name) {
    console.log(name);
}
greet(); // خروجی: undefined
```

---

## 8. Default Parameters

### تعریف ساده
تعیین مقدار پیش‌فرض برای پارامترها، در صورتی که آرگومانی ارسال نشود یا `undefined` باشد.

### مثال
```js
function greet(name = "Guest") {
    console.log("Hello " + name);
}

greet(); // Hello Guest
greet("Ali"); // Hello Ali
greet(undefined); // Hello Guest
greet(null); // Hello null (چون null مقداری است، نه undefined)
```

### نکته مهم
مقادیر پیش‌فرض فقط برای `undefined` اعمال می‌شوند، نه برای `null` یا `""` (رشته خالی).

---

## 9. Rest Parameters

### تعریف ساده
امکان جمع‌آوری تمام آرگومان‌های باقی‌مانده در یک آرایه واقعی با استفاده از `...`.

### مثال
```js
function sum(...numbers) {
    console.log(numbers); // [1, 2, 3, 4]
    return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

### توضیح
`...numbers` تمام آرگومان‌های پاس‌داده‌شده را گرفته و در یک آرایه به نام `numbers` قرار می‌دهد. این برخلاف شیء `arguments`، یک آرایه واقعی است و متدهای آرایه (مثل `map`, `reduce`) روی آن کار می‌کنند.

---

## 10. Spread Syntax در Function Call

### تعریف ساده
برعکس Rest، عملگر Spread (`...`) یک آرایه یا شیء را «باز» کرده و عناصر آن را به عنوان آرگومان‌های جداگانه به تابع پاس می‌دهد.

### مثال
```js
const names = ["ali", "reza", "hamid"];

function greetings1(u1, u2, u3, u4) {
    console.log(u1, u2, u3, u4);
}

// بدون Spread
greetings1("sara", names); 
// خروجی: sara ["ali", "reza", "hamid"] undefined undefined

// با Spread
greetings1("sara", ...names); 
// خروجی: sara ali reza hamid
```

### توضیح
`...names` آرایه را باز کرده و `"ali"`, `"reza"`, `"hamid"` را به عنوان سه آرگومان مجزا ارسال می‌کند.

---

## 11. Return

### تعریف ساده
دستوری که اجرای تابع را متوقف کرده و مقداری را به محل فراخوانی برمی‌گرداند.

### مثال
```js
function add(a, b) {
    return a + b;
}
const result = add(10, 20);
console.log(result); // 30
```

### انواع مقادیر Return
تابع می‌تواند هر نوع داده‌ای برگرداند: `String`, `Number`, `Boolean`, `Object`, `Array` یا حتی یک `Function` دیگر.

### نکته مهم
کدهای بعد از `return` هرگز اجرا نمی‌شوند (Unreachable code).

### مثال
```js
function test() {
    return "hello";
    console.log("this will not execute"); // اجرا نمی‌شود
}
```

---

## 12. Function بدون Return

### تعریف ساده
اگر تابعی `return` نداشته باشد، به طور پیش‌فرض مقدار `undefined` برمی‌گرداند.

### مثال
```js
function test() {
    console.log("Hello");
}

const result = test();
console.log(result); // undefined
```

### تفاوت `console.log` و `return`
* `console.log`: فقط چیزی را در کنسول چاپ می‌کند (برای انسان).
* `return`: مقداری را برای استفاده در ادامه کد برمی‌گرداند (برای ماشین).

---

## 13. Scope در Function

### تعریف ساده
Scope (دامنه) تعیین می‌کند که متغیرها در کجا قابل دسترسی هستند.

### مثال
```js
function test() {
    const message = "hello"; // Local Variable
    console.log(message); // کار می‌کند
}

test();
// console.log(message); // خطا: message is not defined
```

### توضیح
* **Global Scope**: متغیرهای بیرون از همه توابع.
* **Function Scope**: متغیرهای تعریف‌شده داخل تابع (فقط داخل همان تابع قابل دسترسی‌اند).
* **Block Scope**: متغیرهای `let` و `const` داخل `{ }` (مثل `if` یا `for`).

---

## 14. Nested Functions

### تعریف ساده
تعریف یک تابع در داخل تابع دیگر.

### مثال
```js
function outer() {
    const outerVar = "I am outer";

    function inner() {
        console.log("inner");
        console.log(outerVar); // دسترسی به متغیر بیرونی
    }

    inner();
}
outer();
```

### نکته مهم
تابع داخلی (`inner`) به متغیرهای تابع بیرونی (`outer`) دسترسی دارد، اما برعکس آن صادق نیست.

---

## 15. Callback Function

### تعریف ساده
تابعی که به عنوان آرگومان به تابع دیگر پاس داده می‌شود تا بعداً اجرا شود.

### مثال
```js
function greet(name) {
    console.log("Hello " + name);
}

function processUser(callback) {
    // انجام برخی کارها...
    callback("Ali");
}

processUser(greet); // Hello Ali
```

### نکته مهم
توجه کنید که `greet` (بدون پرانتز) پاس داده می‌شود تا ارجاع تابع ارسال شود، نه نتیجه اجرای آن.

---

## 16. Function به عنوان First-Class Citizen

### تعریف ساده
در JavaScript، توابع «شهروند درجه یک» هستند؛ یعنی مانند هر مقدار دیگری (عدد، رشته) رفتار می‌کنند.

### قابلیت‌ها:
1. **ذخیره در متغیر**: `const fn = function() {}`
2. **ارسال به عنوان آرگومان**: (Callback)
3. **بازگشت از تابع**: (Higher-Order)
4. **ذخیره در Object**: (Method)
5. **ذخیره در Array**: `const arr = [() => 1, () => 2]`

---

## 17. Higher-Order Function

### تعریف ساده
تابعی که حداقل یکی از این دو کار را انجام دهد:
1. یک یا چند تابع را به عنوان آرگومان دریافت کند.
2. یک تابع را به عنوان خروجی برگرداند.

### مثال
```js
function operation(a, b, callback) {
    return callback(a, b);
}

const result = operation(10, 20, (x, y) => x + y);
console.log(result); // 30
```
*مثال‌های داخلی JS*: `map`, `filter`, `reduce`.

---

## 18. Functions Returning Functions

### تعریف ساده
تابعی که خروجی آن، یک تابع دیگر است. این پایه و اساس مفهوم Closure است.

### مثال
```js
function createGreeting(message) {
    return function (name) {
        return message + " " + name;
    };
}

const greet = createGreeting("Hello");
console.log(greet("Ali")); // Hello Ali
```

### توضیح
`createGreeting` یک کارخانه تابع است. `greet` اکنون تابعی است که `message` را در حافظه خود نگه داشته است.

---

## 19. Closure

### تعریف ساده
Closure زمانی رخ می‌دهد که یک تابع داخلی، حتی پس از اتمام اجرای تابع بیرونی، به متغیرهای Lexical Scope (دامنه واژگانی) تابع بیرونی دسترسی داشته باشد.

### مثال
```js
function outer() {
    let counter = 0;

    return function () {
        counter++;
        return counter;
    };
}

const increment = outer();

console.log(increment()); // 1
console.log(increment()); // 2
console.log(increment()); // 3
```

### توضیح
تابع بازگشتی، متغیر `counter` را «به خاطر می‌سپارد». این مکانیزم برای ایجاد **Private State** (وضعیت خصوصی) در JS استفاده می‌شود.

---

## 20. Recursion

### تعریف ساده
Recursion (بازگشت) زمانی است که یک تابع، خودش را فراخوانی می‌کند.

### مثال
```js
function countDown(number) {
    console.log(number);
    let nextNumber = number - 1;

    if (nextNumber >= 0) { // Base Case (شرط توقف)
        countDown(nextNumber); // Recursive Case
    }
}

countDown(3);
```

### خروجی
```text
3
2
1
0
```

### مفاهیم کلیدی
* **Base Case**: شرطی که باعث توقف بازگشت می‌شود (جلوگیری از حلقه بی‌نهایت).
* **Recursive Case**: بخشی که تابع خودش را فراخوانی می‌کند.
* **Call Stack**: هر فراخوانی در حافظه (Stack) ذخیره می‌شود. بدون Base Case، Stack Overflow رخ می‌دهد.

---

## 21. مثال Recursive برای Sum

### مثال
```js
function sum(number) {
    if (number < 1) return 0; // Base Case اصلاح‌شده برای جمع صحیح
    return number + sum(number - 1);
}

console.log(sum(3)); // 6
```

### اجرای مرحله‌به‌مرحله (فاز رفت):
```text
sum(3) -> 3 + sum(2)
sum(2) -> 2 + sum(1)
sum(1) -> 1 + sum(0)
sum(0) -> 0 (Base Case)
```

### اجرای مرحله‌به‌مرحله (فاز برگشت):
```text
sum(0) = 0
sum(1) = 1 + 0 = 1
sum(2) = 2 + 1 = 3
sum(3) = 3 + 3 = 6
```
**چرا 6؟** چون مقادیر در مسیر برگشت از Stack با هم جمع می‌شوند.

---

## 22. Call Stack و Function Execution

### تعریف ساده
Call Stack یک ساختار داده LIFO (Last In, First Out) است که ردیابی می‌کند کدام تابع در حال اجراست.

### مثال
```js
function first() {
    console.log("First");
}
function second() {
    first();
}
second();
```

### توضیح
1. `second()` به Stack اضافه می‌شود (Push).
2. `first()` به Stack اضافه می‌شود.
3. `first()` اجرا و از Stack خارج می‌شود (Pop).
4. `second()` اجرا و از Stack خارج می‌شود.
در Recursion، اگر Base Case نباشد، Stack پر شده و خطای `Maximum call stack size exceeded` رخ می‌دهد.

---

## 23. Function Hoisting

### مقایسه کامل
#### 1. Function Declaration
```js
hello(); // کار می‌کند
function hello() { console.log("Hello"); }
```
*دلیل*: کل تعریف تابع به بالای Scope منتقل می‌شود.

#### 2. Function Expression
```js
// hello(); // خطا: Cannot access 'hello' before initialization
const hello = function () { console.log("Hello"); };
```
*دلیل*: فقط اعلان `const` Hoist می‌شود، نه مقدار تابع.

#### 3. Arrow Function
```js
// hello(); // خطا: Cannot access 'hello' before initialization
const hello = () => { console.log("Hello"); };
```
*دلیل*: مشابه Function Expression رفتار می‌کند.

---

## 24. `this` در Function

### تعریف ساده
`this` به شیء‌ای اشاره می‌کند که تابع را «فراخوانی» کرده است (نه لزوماً تعریف کرده است).

### مثال
```js
const user = {
    name: "Ali",
    sayHello: function () {
        console.log(this.name); // "Ali"
    }
};
user.sayHello();
```

### رفتارهای مختلف `this`:
* **Regular Function (استقلال)**: در حالت Strict Mode برابر `undefined`، در غیر این صورت `global object` (مثل `window`).
* **Method Call**: شیء قبل از نقطه (`user.`).
* **Explicit Binding**: با `call`, `apply`, `bind` قابل تنظیم است.

---

## 25. Arrow Function و `this`

### تعریف ساده
Arrow Function `this` خودش را ندارد؛ بلکه `this` را از محیط بیرونی (Lexical Scope) به ارث می‌برد.

### مثال
```js
const user = {
    name: "Ali",
    sayHello: () => {
        console.log(this.name); // undefined (یا خطا در Strict Mode)
    }
};
```

### نکته مهم
هرگز از Arrow Function برای تعریف Method در Object استفاده نکنید، مگر اینکه عمداً بخواهید `this` بیرونی (مثلاً `window`) را بگیرید.

---

## 26. Function Methods

### تعریف ساده
متدهای داخلی برای کنترل دستی مقدار `this` در توابع.

### 1. `call()`
```js
function greet(message) {
    console.log(message + " " + this.name);
}
const user = { name: "Ali" };
greet.call(user, "Hello"); // Hello Ali
```
*آرگومان‌ها به صورت جداگانه پاس داده می‌شوند.*

### 2. `apply()`
مشابه `call`، اما آرگومان‌ها را به صورت **آرایه** دریافت می‌کند: `greet.apply(user, ["Hello"])`.

### 3. `bind()`
یک **تابع جدید** برمی‌گرداند که `this` آن برای همیشه به شیء مشخص‌شده قفل شده است.
```js
const boundGreet = greet.bind(user);
boundGreet("Hi"); // Hi Ali
```

---

## 27. IIFE

### تعریف ساده
Immediately Invoked Function Expression: تابعی که به محض تعریف، اجرا می‌شود.

### مثال
```js
(function () {
    console.log("Hello");
})();
// یا با Arrow Function:
(() => console.log("Hello"))();
```

### کاربرد
ایجاد یک Scope خصوصی برای جلوگیری از آلودگی Global Scope (بسیار رایج قبل از آمدن `let`/`const` و ماژول‌ها).

---

## 28. Pure Function

### تعریف ساده
تابعی که دو ویژگی دارد:
1. **Same Input → Same Output**: با ورودی یکسان، همیشه خروجی یکسان می‌دهد.
2. **No Side Effects**: هیچ تغییری در بیرون از تابع ایجاد نمی‌کند.

### مثال
```js
function add(a, b) {
    return a + b;
}
```

### نکته مهم
توابع Pure تست‌پذیری و دیباگ کردن بسیار آسانی دارند.

---

## 29. Side Effect

### تعریف ساده
هر کاری که تابع علاوه بر برگرداندن مقدار، در دنیای بیرون انجام دهد.

### مثال‌های Side Effect:
* تغییر یک متغیر Global.
* تغییر (Mutate) یک شیء یا آرایه پاس‌داده‌شده.
* چاپ در کنسول (`console.log`).
* درخواست شبکه (Fetch/API).
* تغییر DOM.

### مثال Impure
```js
let total = 0;
function addImpure(val) {
    total += val; // Side Effect: تغییر متغیر بیرونی
    return total;
}
```

---

## 30. Function و Object

### تعریف ساده
در JavaScript، توابع خودشان نوعی Object هستند و می‌توانند Property و Method داشته باشند.

### مثال
```js
function test() {
    console.log("test");
}
test.description = "A test function";
console.log(test.description); // A test function
```

---

## 31. Function Constructor و `new Function`

### تعریف ساده
روش ساخت تابع از طریق رشته (String).

### مثال
```js
const sum = new Function("a", "b", "return a + b");
console.log(sum(10, 20)); // 30
```

### نکته مهم
این روش به دلیل **مشکلات امنیتی** (خطر Injection مشابه `eval`) و **کند بودن** (عدم بهینه‌سازی توسط موتور JS) به شدت غیرتوصیه می‌شود.

---

## 32. Generator Functions

### تعریف ساده
توابعی که می‌توانند اجرای خود را متوقف (`yield`) و بعداً ادامه دهند.

### مثال
```js
function* numbers() {
    yield 1;
    yield 2;
    yield 3;
}

const gen = numbers();
console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

### کاربرد
مدیریت داده‌های بزرگ (Lazy Evaluation) و پیاده‌سازی Async/Await در زیر پوسته JS.

---

## 33. Async Functions

### تعریف ساده
تابعی که با کلمه کلیدی `async` تعریف می‌شود و همیشه یک **Promise** برمی‌گرداند.

### مثال
```js
async function getData() {
    return "data";
}
```
*توضیح*: حتی اگر رشته برگردانید، JS آن را درون یک Promise موفق (`Promise.resolve("data")`) قرار می‌دهد.

---

## 34. Function و Promise

### مثال
```js
async function getUser() {
    return { name: "Ali" };
}

getUser().then(user => {
    console.log(user); // { name: "Ali" }
});
```

### توضیح
چون `getUser` یک Async Function است، خروجی آن Promise است و می‌توان با `.then()` یا `await` نتیجه آن را دریافت کرد.

---

## 35. Function Parameter پیشرفته

### Destructuring Parameters
امکان استخراج مستقیم مقادیر از آبجکت یا آرایه در امضای تابع.

### مثال (Object)
```js
function printUser({ name, age }) {
    console.log(name, age);
}
printUser({ name: "Ali", age: 25 }); // Ali 25
```

### مثال (Array)
```js
function printCoords([x, y]) {
    console.log(x, y);
}
printCoords([10, 20]); // 10 20
```

---

## 36. Function و Destructuring (تکمیلی)

می‌توان مقادیر پیش‌فرض را نیز در Destructuring ترکیب کرد:
```js
function createUser({ name = "Guest", role = "User" } = {}) {
    console.log(name, role);
}
createUser(); // Guest User
createUser({ name: "Reza" }); // Reza User
```

---

## 37. Recursion پیشرفته

### مفاهیم
* **Recursive Tree**: توابعی که بیش از یک بار خود را فراخوانی می‌کنند (مثل Fibonacci یا پیمایش درخت).
* **Factorial**:
  ```js
  function factorial(n) {
      if (n === 0) return 1;
      return n * factorial(n - 1);
  }
  ```
* **خطر Stack Overflow**: برای داده‌های بزرگ، Call Stack پر می‌شود.
* **Tail Recursion**: حالتی که فراخوانی بازگشتی *آخرین* عملیات تابع است. (توجه: اکثر موتورهای JS مدرن مثل V8 بهینه‌سازی Tail Call را به طور کامل پیاده‌سازی نکرده‌اند، پس همچنان خطرناک است).

---

## 38. Function Composition

### تعریف ساده
ترکیب دو یا چند تابع به طوری که خروجی یکی، ورودی دیگری شود.

### مثال
```js
const addOne = x => x + 1;
const double = x => x * 2;

const result = double(addOne(5)); // (5 + 1) * 2 = 12
console.log(result);
```

### تابع Composition سفارشی
```js
const compose = (f, g) => x => f(g(x));
const addOneAndDouble = compose(double, addOne);
console.log(addOneAndDouble(5)); // 12
```

---

## 39. Currying

### تعریف ساده
تبدیل یک تابع با چند آرگومان به زنجیره‌ای از توابع تک‌آرگومانی.

### مثال
```js
function multiply(a) {
    return function (b) {
        return a * b;
    };
}

const multiplyByTwo = multiply(2);
console.log(multiplyByTwo(5)); // 10
```

### ارتباط با Closure
هر تابع داخلی، آرگومان `a` را در Closure خود نگه می‌دارد تا زمانی که `b` ارائه شود.

---

## 40. Memoization

### تعریف ساده
تکنیک بهینه‌سازی که نتایج فراخوانی‌های پرهزینه تابع را Cache (ذخیره) می‌کند تا در صورت فراخوانی مجدد با همان ورودی، محاسبه مجدد انجام نشود.

### مثال
```js
function memoize(fn) {
    const cache = {};
    return function(...args) {
        const key = JSON.stringify(args);
        if (cache[key]) return cache[key];
        const result = fn(...args);
        cache[key] = result;
        return result;
    };
}

const slowSquare = memoize(n => {
    console.log("Calculating...");
    return n * n;
});

console.log(slowSquare(5)); // Calculating... \n 25
console.log(slowSquare(5)); // 25 (از Cache)
```

---

## 41. Function Overloading

### تعریف ساده
JavaScript از Overloading سنتی (چند تابع با نام یکسان و پارامترهای مختلف) پشتیبانی **نمی‌کند**. آخرین تعریف، قبلی‌ها را بازنویسی می‌کند.

### راه‌حل جایگزین
بررسی تعداد یا نوع آرگومان‌ها داخل یک تابع واحد.

### مثال
```js
function greet(param) {
    if (typeof param === "string") {
        console.log("Hello " + param);
    } else if (typeof param === "object" && param.name) {
        console.log("Hello " + param.name);
    } else {
        console.log("Hello Guest");
    }
}
```

---

## 42. `arguments` Object

### تعریف ساده
یک شیء شبه‌آرایه (Array-like) که در دسترس تمام توابع غیر-Arrow قرار دارد و شامل تمام آرگومان‌های پاس‌داده‌شده است.

### مثال
```js
function test() {
    console.log(arguments); // [Arguments] { '0': 1, '1': 2, '2': 3 }
}
test(1, 2, 3);
```

### تفاوت با Rest Parameter
* `arguments` یک آرایه واقعی نیست (متدهای `map` یا `filter` را ندارد).
* در Arrow Functionها در دسترس نیست.
* **Rest Parameter (`...args`)** در JS مدرن خواناتر، ایمن‌تر و یک آرایه واقعی است.

---

## 43. Function Length و Name

### تعریف ساده
هر تابع دو Property داخلی دارد:
* `.name`: نام تابع.
* `.length`: تعداد پارامترهای مورد انتظار (قبل از اولین پارامتر پیش‌فرض یا Rest).

### مثال
```js
function test(a, b, c = 10) {}
console.log(test.name); // "test"
console.log(test.length); // 2 (چون c پیش‌فرض دارد)
```

---

## 44. Function در Array

### تعریف ساده
از آنجا که توابع First-Class Citizen هستند، می‌توانند در آرایه ذخیره و اجرا شوند.

### مثال
```js
const operations = [
    () => console.log("add"),
    () => console.log("remove")
];

operations[0](); // add
```

---

## 45. Function در Object

### تعریف ساده
وقتی یک تابع به عنوان Property یک شیء تعریف می‌شود، به آن **Method** می‌گویند.

### مثال (Method Shorthand)
```js
const user = {
    name: "Ali",
    greet() { // شورت‌هند مدرن به جای greet: function()
        console.log("Hello " + this.name);
    }
};
user.greet();
```

---

## 46. Factory Function

### تعریف ساده
تابعی که یک شیء جدید می‌سازد و برمی‌گرداند، بدون نیاز به کلمه کلیدی `new` یا Class.

### مثال
```js
function createUser(name, age) {
    return {
        name,
        age,
        greet() { console.log("Hi " + this.name); }
    };
}
const user1 = createUser("Ali", 25);
```

---

## 47. Function Declaration vs Expression vs Arrow

| ویژگی | Declaration | Expression | Arrow Function |
| :--- | :--- | :--- | :--- |
| **Syntax** | `function name() {}` | `const name = function() {}` | `const name = () => {}` |
| **Hoisting** | بله (کامل) | خیر (فقط اعلان متغیر) | خیر (فقط اعلان متغیر) |
| **`this`** | داینامیک (بسته به فراخوانی) | داینامیک | Lexical (ارث‌بری از بیرون) |
| **`arguments`** | دارد | دارد | ندارد |
| **Constructor** | بله (`new`) | بله (`new`) | خیر |
| **کاربرد معمول** | توابع اصلی و سطح بالا | Callbackها، IIFE | Callbackهای کوتاه، متدهای آرایه |

---

## 48. اشتباهات رایج در Function

1. **فراموش کردن `return`**:
   * ❌ `function add(a,b) { a + b; }`
   * ✅ `function add(a,b) { return a + b; }`
2. **اشتباه گرفتن `return` با `console.log`**: تابع باید مقدار برگرداند، نه فقط چاپ کند.
3. **استفاده از Arrow Function برای Object Method**: باعث از دست رفتن `this` می‌شود.
4. **فراخوانی به جای ارجاع در Callback**:
   * ❌ `setTimeout(greet(), 1000)`
   * ✅ `setTimeout(greet, 1000)`
5. **Recursion بدون Base Case**: باعث `Stack Overflow` می‌شود.
6. **تغییر مستقیم آرگومان‌های شیء/آرایه** (ایجاد Side Effect ناخواسته).

---

## 49. Best Practices

* **نام‌گذاری**: نام تابع باید با یک فعل شروع شود و کار آن را توصیف کند (مثل `calculateTotal`, `getUser`).
* **Single Responsibility**: هر تابع باید فقط **یک کار** را انجام دهد. اگر طولانی شد، آن را بشکنید.
* **پرهیز از Global Variables**: تا حد امکان از متغیرهای سراسری درون توابع استفاده نکنید.
* **تعداد پارامترها**: اگر بیش از 3 پارامتر دارید، آن‌ها را در یک Object گروه‌بندی کنید.
* **Pure Functions**: تا حد ممکن توابع را Pure نگه دارید تا تست‌پذیری افزایش یابد.

---

## 50. پروژه کوچک برای تمرین

### Beginner
1. **سلام کردن**: تابعی بنویسید که یک نام بگیرد و `"Hello, [name]"` برگرداند.
2. **جمع دو عدد**: تابعی که دو عدد بگیرد و جمع آن‌ها را برگرداند.
3. **زوج یا فرد**: تابعی که یک عدد بگیرد و `true` (زوج) یا `false` (فرد) برگرداند.
4. **مربع عدد**: تابعی که مربع یک عدد را محاسبه کند.

### Intermediate
5. **چند نام**: تابعی که 3 نام بگیرد و آن‌ها را با کاما جدا کرده چاپ کند.
6. **Rest Parameter**: تابعی که هر تعداد عدد بگیرد و مجموع آن‌ها را برگرداند.
7. **Callback**: تابعی به نام `processData` که یک آرایه و یک callback بگیرد و callback را روی هر عنصر اجرا کند.
8. **ایجاد User**: یک Factory Function بنویسید که `name` و `age` بگیرد و یک Object با متد `introduce` برگرداند.
9. **فیلتر کردن**: تابعی که یک آرایه از اعداد و یک عدد حد آستانه بگیرد و اعداد بزرگتر را فیلتر کند (بدون استفاده از `Array.filter` داخلی، با حلقه).

### Advanced
10. **Recursive Countdown**: تابع بازگشتی که از `n` تا `1` بشمارد و آرایه‌ای از اعداد برگرداند.
11. **Recursive Sum**: مجموع ارقام یک عدد را به صورت بازگشتی حساب کنید (مثلاً `123` -> `6`).
12. **Factorial**: محاسبه فاکتوریل با Recursion.
13. **Closure Counter**: تابعی بنویسید که یک شمارنده با قابلیت `increment` و `decrement` و `reset` برگرداند (بدون استفاده از Class).
14. **Function Composition**: تابعی به نام `pipe` بنویسید که آرایه‌ای از توابع را گرفته و خروجی هر کدام را به ورودی بعدی بدهد.
15. **Currying**: تابع `multiply(a)(b)(c)` را پیاده‌سازی کنید.
16. **Memoization**: تابع Fibonacci را با استفاده از تکنیک Memoization بهینه‌سازی کنید.

*(Hint: برای تمرین‌های پیشرفته، به بخش‌های Closure و Recursion این راهنما مراجعه کنید. جواب‌ها را خودتان بنویسید تا یادگیری عمیق‌تر شود!)*

---

## 51. Cheat Sheet

```js
// 1. Declaration
function test() {}

// 2. با پارامتر
function test(a) {}
function test(a, b) {}

// 3. Expression
const test = function () {};

// 4. Arrow Function
const test = () => {};
const test = x => x * 2; // Implicit Return

// 5. Rest Parameters
function test(...args) {}

// 6. Default Parameters
function test(a = 10) {}

// 7. Nested / Returning Function
function outer() {
    return function inner() {};
}

// 8. Generator
function* generator() {}

// 9. Async Function
async function test() {}
```

---

## 52. منابع

برای مطالعه عمیق‌تر و ارجاع به استانداردها، از منابع معتبر زیر استفاده کنید:

1. **MDN Web Docs - Functions**  
   [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
2. **JavaScript.info - Functions**  
   [https://javascript.info/function-basics](https://javascript.info/function-basics)
3. **ECMAScript Language Specification (Functions)**  
   [https://tc39.es/ecma262/#sec-function-definitions](https://tc39.es/ecma262/#sec-function-definitions)
4. **MDN Web Docs - Closures**  
   [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
5. **MDN Web Docs - Arrow Functions**  
   [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

---

### جمع‌بندی
توابع قلب تپنده JavaScript هستند. از یک `function` ساده برای چاپ متن تا مفاهیم پیشرفته‌ای مثل Closure، Recursion و Async Programming، تسلط بر توابع به شما اجازه می‌دهد کدهایی تمیز، ماژولار و قابل نگهداری بنویسید. این راهنما را به عنوان مرجع در ریپوزیتوری خود نگه دارید و با تمرین مداوم، مفاهیم را ملکه ذهن کنید.
