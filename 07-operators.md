# 1. Operator چیست؟

ابتدا مفهوم Operator را خیلی ساده توضیح بده.

توضیح بده:

* Operator چیست؟
* Operand چیست؟
* Operator چه کاری انجام می‌دهد؟
* تفاوت Operator و Function چیست؟
* مثال‌های ساده از Operatorها

مثال:

```javascript
let result = 10 + 20;
```

توضیح بده:

* `10` چیست؟
* `20` چیست؟
* `+` چیست؟
* `result` چیست؟

---

# 2. انواع Operatorها

Operatorهای JavaScript را دسته‌بندی کن و برای هر دسته توضیح کوتاه بده:

* Arithmetic
* Assignment
* Comparison
* Logical
* Unary
* Relational
* Conditional / Ternary
* Bitwise
* String
* Nullish Coalescing
* Optional Chaining در ارتباط با Expressionها

در صورت وجود تفاوت بین Operator و Expression آن را نیز توضیح بده.

---

# 3. Arithmetic Operators

تمام Arithmetic Operatorهای مهم را از پایه تا پیشرفته توضیح بده:

```javascript
+
-
*
/
%
**
```

برای هرکدام:

* تعریف
* Syntax
* مثال ساده
* خروجی
* کاربرد
* نکات مهم
* رفتار با Typeهای مختلف

مثلاً:

```javascript
let a = 8;
let b = 2;

console.log(a + b);
console.log(a - b);
console.log(a * b);
console.log(a / b);
console.log(a % b);
console.log(a ** b);
```

همچنین توضیح بده:

```javascript
const c = (a + b) * 3;
```

و مفهوم **Operator Precedence** را با همین مثال معرفی کن.

---

# 4. Assignment Operators

Operator انتساب را توضیح بده:

```javascript
=
```

و سپس Assignment Operatorهای ترکیبی:

```javascript
+=
-=
*=
/=
%=
**=
&&=
||=
??=
```

مثال:

```javascript
let a = 50;
let b = 30;

a *= b;

console.log(a);
```

توضیح بده:

```javascript
a *= b;
```

معادل چیست؟

```javascript
a = a * b;
```

همچنین برای `+=`، `-=`, `*=`, `/=`, `%=` مثال بزن.

در سطح پیشرفته `&&=`, `||=`, `??=` را نیز توضیح بده و تفاوت رفتار آن‌ها را نشان بده.

---

# 5. Comparison Operators

Comparison Operatorها را کامل توضیح بده:

```javascript
>
<
>=
<=
==
!=
===
!==
```

برای هرکدام مثال بزن.

مثال:

```javascript
let a = 10;
let b = 10;

console.log(a == b);
console.log(a === b);
```

توضیح بده چرا `==` و `===` رفتار متفاوتی دارند.

همچنین مثال‌های زیر را بررسی کن:

```javascript
console.log(true > 1);
console.log("10" == 10);
console.log("10" === 10);
```

خروجی و دلیل خروجی را دقیق توضیح بده.

---

# 6. Logical Operators

Logical Operatorها را از پایه توضیح بده:

```javascript
!
&&
||
```

بعد وارد رفتار پیشرفته آن‌ها شو.

---

# 7. NOT Operator `!`

این بخش را بسیار ساده توضیح بده.

مثال:

```javascript
let a = true;
let b = false;

console.log(!a);
console.log(!b);
```

توضیح بده:

```text
!true  → false
!false → true
```

سپس مفهوم **Boolean Conversion** را توضیح بده.

مثال:

```javascript
console.log(!10);
console.log(!0);
console.log(!"hello");
console.log(!"");
```

برای هر مثال توضیح بده JavaScript چگونه مقدار را به Boolean تبدیل می‌کند.

---

# 8. Double NOT `!!`

توضیح بده چرا این کد:

```javascript
console.log(!!10);
```

نتیجه `true` می‌دهد.

مثال‌های مختلف:

```javascript
console.log(!!10);
console.log(!!0);
console.log(!!"hello");
console.log(!!"");
console.log(!!null);
console.log(!!undefined);
```

توضیح بده `!!value` در واقع چه کاری انجام می‌دهد و چه ارتباطی با `Boolean(value)` دارد.

---

# 9. AND Operator `&&`

Operator `&&` را از ساده تا پیشرفته توضیح بده.

مثال Boolean:

```javascript
let a = true;
let b = false;

console.log(a && b);
```

جدول Truth Table نیز ارائه کن.

سپس بسیار مهم:

توضیح بده `&&` در JavaScript الزاماً Boolean برنمی‌گرداند.

مثلاً:

```javascript
console.log("hello" && "world");
console.log(10 && 20);
console.log(0 && 20);
console.log(null && "hello");
```

مفهوم **Short-Circuit Evaluation** را توضیح بده.

---

# 10. OR Operator `||`

مثال:

```javascript
let a = true;
let b = false;

console.log(a || b);
```

Truth Table ارائه کن.

سپس توضیح بده `||` نیز می‌تواند یکی از Operandها را برگرداند.

مثال:

```javascript
console.log("hello" || "world");
console.log("" || "world");
console.log(0 || 100);
```

این مثال را نیز بررسی کن:

```javascript
const x1 = "js" || "ali";

console.log(x1);
```

توضیح بده چرا نتیجه `"js"` است.

---

# 11. Nullish Coalescing Operator `??`

Operator زیر را از پایه توضیح بده:

```javascript
??
```

مثال:

```javascript
const x2 = 0 ?? "js";

console.log(x2);
```

توضیح بده چرا نتیجه `0` است.

سپس مثال‌های زیر را بررسی کن:

```javascript
console.log(null ?? "default");
console.log(undefined ?? "default");
console.log(false ?? "default");
console.log(0 ?? "default");
console.log("" ?? "default");
```

تفاوت Nullish با Falsy را به زبان ساده توضیح بده.

---

# 12. تفاوت `||` و `??`

این بخش بسیار مهم است.

مثال:

```javascript
console.log(0 || "default");
console.log(0 ?? "default");

console.log("" || "default");
console.log("" ?? "default");

console.log(false || "default");
console.log(false ?? "default");

console.log(null || "default");
console.log(null ?? "default");
```

برای هرکدام خروجی و دلیل آن را توضیح بده.

یک جدول مقایسه‌ای نیز ارائه کن.

---

# 13. Conditional / Ternary Operator

Ternary Operator را توضیح بده:

```javascript
condition ? valueIfTrue : valueIfFalse
```

مثال:

```javascript
let age = 20;

const checkAdult = age > 50 ? "old" : "young";

console.log(checkAdult);
```

توضیح بده:

* condition چیست؟
* `?` چه کاری می‌کند؟
* قسمت True چیست؟
* `:` چه کاری می‌کند؟
* قسمت False چیست؟

سپس مثال ساده‌تر:

```javascript
const result = age >= 18 ? "adult" : "child";
```

تفاوت Ternary با `if/else` را توضیح بده.

همچنین توضیح بده چرا Nested Ternary می‌تواند خوانایی را کاهش دهد.

---

# 14. Increment و Decrement

توضیح بده:

```javascript
++
--
```

مثال:

```javascript
let a = 10;

console.log(++a);
console.log(a);
```

و:

```javascript
let b = 10;

console.log(b++);
console.log(b);
```

---

# 15. Prefix و Postfix

تفاوت این دو را کاملاً ساده توضیح بده:

```javascript
++a
a++
```

و:

```javascript
--a
a--
```

مثال مرحله‌به‌مرحله بزن و مقدار Variable را بعد از هر خط نشان بده.

---

# 16. Unary Operators

Operatorهای Unary را معرفی کن و توضیح بده چرا به یک Operand نیاز دارند.

موارد مهم:

```javascript
+
-
!
~
typeof
delete
void
```

برای هرکدام مثال بزن.

---

# 17. typeof

Operator زیر را کامل توضیح بده:

```javascript
typeof
```

مثال:

```javascript
console.log(typeof 10);
console.log(typeof "hello");
console.log(typeof true);
console.log(typeof undefined);
console.log(typeof null);
```

حتماً درباره رفتار معروف زیر توضیح بده:

```javascript
typeof null
```

و درباره:

```javascript
typeof []
typeof {}
typeof function(){}
```

نیز توضیح بده.

---

# 18. delete

توضیح بده `delete` چگونه برای حذف Property از Object استفاده می‌شود.

مثال:

```javascript
const user = {
    name: "Ali",
    age: 20
};

delete user.age;

console.log(user);
```

تفاوت حذف Property با مقداردهی `undefined` را توضیح بده.

---

# 19. void

Operator `void` را توضیح بده و کاربردهای آن را بررسی کن.

مثال:

```javascript
console.log(void 0);
```

توضیح بده چرا نتیجه `undefined` است و کاربرد واقعی آن در JavaScript چیست.

---

# 20. Relational Operators

موارد زیر را توضیح بده:

```javascript
in
instanceof
```

برای `in` مثال:

```javascript
const user = {
    name: "Ali",
    age: 20
};

console.log("name" in user);
console.log("email" in user);
```

برای `instanceof` نیز مثال عملی ارائه کن.

---

# 21. Equality

تفاوت این موارد را کاملاً توضیح بده:

```javascript
=
==
===
!=
!==
```

حتماً تأکید کن:

```javascript
=
```

برای Assignment است و Comparison نیست.

مثال:

```javascript
let a = 10;

a = 20;
```

سپس:

```javascript
console.log(10 == "10");
console.log(10 === "10");
```

---

# 22. Type Coercion

Type Coercion را از پایه توضیح بده.

مثال:

```javascript
console.log("10" + 5);
console.log("10" - 5);
console.log("10" * 2);
console.log(true + 1);
```

توضیح بده چرا رفتار `+` با سایر Arithmetic Operatorها در بعضی شرایط متفاوت است.

همچنین درباره:

* Implicit Conversion
* Explicit Conversion

توضیح بده.

---

# 23. Truthy و Falsy

تمام Falsy valueهای مهم JavaScript را معرفی کن.

مثال:

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

توضیح بده سایر Valueها معمولاً Truthy هستند.

مثال:

```javascript
if ("hello") {
    console.log("executed");
}
```

---

# 24. Short-Circuit Evaluation

به صورت ساده توضیح بده:

```javascript
&&
||
??
```

چگونه ممکن است قبل از بررسی همه Operandها اجرای Expression متوقف شود.

مثال:

```javascript
false && console.log("hello");
true || console.log("world");
```

سپس کاربردهای واقعی آن را توضیح بده.

---

# 25. Operator Precedence

توضیح بده وقتی چند Operator در یک Expression وجود دارد، JavaScript چگونه ترتیب اجرای آن‌ها را مشخص می‌کند.

مثال:

```javascript
const result = 10 + 5 * 2;
```

و:

```javascript
const result = (10 + 5) * 2;
```

توضیح بده چرا نتایج متفاوت هستند.

از جدول Precedence رسمی JavaScript استفاده کن و موارد مهم را برای مبتدی‌ها ساده کن.

---

# 26. Associativity

تفاوت Precedence و Associativity را توضیح بده.

مثال:

```javascript
a - b - c
```

و Operatorهایی که Right-to-Left هستند را نیز معرفی کن.

---

# 27. ترکیب Operatorها

Expressionهای ترکیبی را بررسی کن:

```javascript
const result = age >= 18 && isActive;
```

و:

```javascript
const name = username || "Guest";
```

و:

```javascript
const value = input ?? "default";
```

برای هرکدام مرحله‌به‌مرحله توضیح بده JavaScript چه کاری انجام می‌دهد.

---

# 28. Operatorها و String

رفتار Operatorها با String را توضیح بده.

مثال:

```javascript
console.log("Hello " + "World");
console.log("10" + 5);
console.log("10" - 5);
```

تفاوت String Concatenation و Numeric Addition را توضیح بده.

---

# 29. Operatorها و Object / Array

بررسی کن Operatorها با Object و Array چه رفتاری دارند.

مثال:

```javascript
const a = [];
const b = [];

console.log(a == b);
console.log(a === b);
```

توضیح بده چرا ممکن است دو Array ظاهراً مشابه، برابر نباشند.

همچنین درباره Reference و Primitive Value در حد لازم توضیح بده.

---

# 30. Bitwise Operators

برای سطح پیشرفته، Bitwise Operatorها را معرفی کن:

```javascript
&
|
^
~
<<
>>
>>>
```

همچنین Assignmentهای مربوط به آن‌ها:

```javascript
&=
|=
^=
<<=
>>=
>>>=
```

ابتدا Binary و Bit را خیلی ساده توضیح بده، سپس مثال بزن.

---

# 31. Operatorهای جدید و مدرن JavaScript

Operatorها و Syntaxهای مدرن مرتبط را نیز بررسی کن:

```javascript
??
??=
&&=
||=
?. 
```

توضیح بده:

* Nullish Coalescing
* Nullish Assignment
* Logical AND Assignment
* Logical OR Assignment
* Optional Chaining

مثال‌های واقعی ارائه کن.

---

# 32. اشتباهات رایج

حداقل 15 اشتباه رایج درباره Operatorها را معرفی کن.

برای مثال:

* اشتباه گرفتن `=` با `==`
* استفاده نکردن از `===`
* اشتباه در `++a` و `a++`
* اشتباه گرفتن `||` و `??`
* تصور اینکه `&&` همیشه Boolean برمی‌گرداند
* نادیده گرفتن Type Coercion
* نادیده گرفتن Operator Precedence
* استفاده بیش از حد از Ternary
* مقایسه اشتباه Objectها
* مقایسه Arrayها
* اشتباه در `typeof null`

برای هر اشتباه، مثال اشتباه و نسخه صحیح ارائه کن.

---

# 33. مثال‌های ترکیبی

حداقل 20 Expression ترکیبی طراحی کن که چند Operator در آن‌ها استفاده شده باشد.

برای هر مثال:

1. کد
2. خروجی
3. توضیح مرحله‌به‌مرحله
4. دلیل انتخاب Operatorها

مثلاً:

```javascript
const result =
    age >= 18 && isActive
        ? "Allowed"
        : "Not Allowed";
```

---

# 34. تمرین

در پایان حداقل 20 تمرین طراحی کن.

تمرین‌ها را از آسان به سخت مرتب کن.

سطوح:

### Beginner

تمرین‌های ساده Arithmetic و Assignment

### Intermediate

Comparison و Logical

### Advanced

Type Coercion، Short-Circuit، Precedence و Expressionهای ترکیبی

### Expert

Expressionهای پیچیده با:

```javascript
&&
||
??
?:
===
!==
++
--
```

برای تمرین‌ها ابتدا جواب را نمایش نده.

بعد از بخش تمرین، یک بخش **Solutions** قرار بده.

---

# 35. نکات مصاحبه‌ای

یک بخش با عنوان:

## JavaScript Operators Interview Questions

ایجاد کن.

حداقل 20 سؤال مهم مصاحبه‌ای همراه با پاسخ ساده ارائه بده.

مثلاً:

```javascript
console.log(10 + "5");
```

خروجی چیست و چرا؟

یا:

```javascript
console.log(0 || "JavaScript");
console.log(0 ?? "JavaScript");
```

یا:

```javascript
console.log(false == 0);
console.log(false === 0);
```

---

# 36. جمع‌بندی

در پایان یک خلاصه بسیار ساده از تمام Operatorهای مهم ارائه کن.

یک جدول خلاصه شامل:

| Operator | نام | کاربرد |
| -------- | --- | ------ |

ایجاد کن.

همچنین مشخص کن کدام Operatorها برای یک JavaScript Developer مبتدی ضروری‌تر هستند و کدام موارد را می‌توان بعداً یاد گرفت؛ بدون اینکه اهمیت آن‌ها را به شکل سلیقه‌ای رتبه‌بندی کنی.

---

# قوانین نگارش

محتوا باید:

* فارسی باشد.
* اصطلاحات تخصصی JavaScript را به انگلیسی داخل پرانتز یا Backtick بنویسد.
* برای مبتدی کاملاً قابل فهم باشد.
* ابتدا ساده و سپس پیشرفته توضیح داده شود.
* از مثال‌های کوتاه و واقعی استفاده شود.
* خروجی کدها مشخص باشد.
* برای کدهای مهم توضیح خط‌به‌خط ارائه شود.
* تفاوت مفاهیم مشابه به صورت واضح توضیح داده شود.
* از توضیحات غیرضروری و پیچیده خودداری شود.
* از مثال‌های اشتباه نیز برای آموزش استفاده شود.
* در صورت وجود رفتار عجیب یا Exception در JavaScript، دلیل آن را توضیح بده.
* مطالب منسوخ را به عنوان روش پیشنهادی معرفی نکن.
* Syntax مربوط به JavaScript مدرن را در صورت مرتبط بودن پوشش بده.
* در صورت تفاوت رفتار Browser و Node.js، آن را مشخص کن.

---

# قوانین مربوط به منابع

اطلاعات را از منابع معتبر جمع‌آوری کن.

منابع اصلی ترجیحاً:

1. MDN Web Docs
2. ECMAScript Specification
3. JavaScript.info
4. منابع رسمی مرتبط با استاندارد ECMAScript

در پایان یک بخش:

# منابع معتبر

ایجاد کن و برای هر منبع:

* نام منبع
* عنوان صفحه
* لینک مستقیم و معتبر
* توضیح کوتاه درباره اینکه این منبع برای کدام بخش استفاده شده

را ارائه بده.

**لینک‌ها باید واقعی، معتبر و قابل دسترسی باشند.**

از لینک ساختگی استفاده نکن.

---

# نکته مهم درباره کدهای اولیه

کدهای زیر را نیز در آموزش پوشش بده و اگر Syntax آن‌ها در متن سؤال خراب یا ناقص شده، نسخه صحیح JavaScript را بازسازی کن:

```javascript
// NOT
let a = true;
let b = false;

console.log(!a);
console.log(!b);

console.log(!!10);

// AND
console.log(a && b);

// OR
console.log(a || b);

const x1 = "js" || "ali";
console.log(x1);

// nullish operator
const x2 = 0 ?? "js";
console.log(x2);

// ternary
let age = 20;

const checkAdult = age > 50 ? "old" : "young";

console.log(checkAdult);

// assignment
let a = 50;
let b = 30;

console.log(a *= b);
console.log(a);

// arithmetic
let a = 8;
let b = 2;

const c = (a + b) * 3;
console.log(c);

// comparison
let a = 10;
let b = 10;

console.log(a == b);
console.log(a === b);

console.log(true > 1);
```

اگر در کدهای اولیه اشتباه Syntax وجود دارد، ابتدا نسخه صحیح را ارائه کن و سپس توضیح بده.

---

# خروجی نهایی

خروجی را به صورت یک **Markdown Document مناسب GitHub README / آموزشی** تولید کن.

ساختار کلی:

```text
Title
Introduction
Table of Contents

Basic Concepts

Operator Categories

Arithmetic Operators

Assignment Operators

Comparison Operators

Logical Operators

NOT
Double NOT
AND
OR
Nullish Coalescing

Ternary

Increment / Decrement

Unary Operators

typeof
delete
void

Relational Operators

Equality

Type Coercion

Truthy / Falsy

Short-Circuit

Precedence

Associativity

Bitwise

Modern Operators

Common Mistakes

Combined Examples

Exercises

Solutions

Interview Questions

Summary

References
```

محتوا باید **از صفر شروع شود و به سطح پیشرفته برسد** و بین بخش‌ها لینک داخلی Markdown وجود داشته باشد.

هدف نهایی این است که این فایل بتواند به عنوان یک فصل کامل از یک Repository آموزشی JavaScript مورد استفاده قرار بگیرد.


### ASSISTANT
# آموزش جامع عملگرها (Operators) در جاوااسکریپت: از مقدماتی تا پیشرفته

به راهنمای جامع و مرحله‌به‌مرحله **JavaScript Operators** خوش آمدید. این آموزش به گونه‌ای طراحی شده که از مفاهیم پایه شروع شده و شما را به درک عمیقی از رفتارهای پیچیده، Type Coercion، Short-Circuit و اولویت عملگرها می‌رساند. این محتوا برای استفاده در یک Repository آموزشی بهینه‌سازی شده است.

---

## فهرست مطالب
1. [Operator چیست؟](#1-operator-چیست)
2. [Operand چیست؟](#2-operand-چیست)
3. [انواع Operatorها در JavaScript](#3-انواع-operatorها-در-javascript)
4. [Arithmetic Operators](#4-arithmetic-operators)
5. [Assignment Operators](#5-assignment-operators)
6. [Comparison Operators](#6-comparison-operators)
7. [Logical Operators](#7-logical-operators)
8. [NOT Operator `!`](#8-not-operator-)
9. [Double NOT `!!`](#9-double-not-)
10. [AND Operator `&&`](#10-and-operator-)
11. [OR Operator `||`](#11-or-operator-)
12. [Nullish Coalescing Operator `??`](#12-nullish-coalescing-operator-)
13. [تفاوت `||` و `??`](#13-تفاوت--و-)
14. [Conditional / Ternary Operator `?:`](#14-conditional--ternary-operator-)
15. [Increment و Decrement](#15-increment-و-decrement)
16. [Prefix و Postfix](#16-prefix-و-postfix)
17. [Unary Operators](#17-unary-operators)
18. [Unary Plus و Unary Minus](#18-unary-plus-و-unary-minus)
19. [`typeof` Operator](#19-typeof-operator)
20. [`delete` Operator](#20-delete-operator)
21. [`void` Operator](#21-void-operator)
22. [Relational Operators](#22-relational-operators)
23. [`in` Operator](#23-in-operator)
24. [`instanceof` Operator](#24-instanceof-operator)
25. [Equality Operators](#25-equality-operators)
26. [تفاوت `==` و `===`](#26-تفاوت--و-)
27. [تفاوت `!=` و `!==`](#27-تفاوت--و-)
28. [Type Coercion در Operatorها](#28-type-coercion-در-operatorها)
29. [Truthiness و Falsiness](#29-truthiness-و-falsiness)
30. [Short-Circuit Evaluation](#30-short-circuit-evaluation)
31. [Operator Precedence](#31-operator-precedence)
32. [Operator Associativity](#32-operator-associativity)
33. [تفاوت `=` و `==` و `===`](#33-تفاوت--و--و-)
34. [تفاوت `&&`، `||` و `??`](#34-تفاوت---و-)
35. [ترکیب چند Operator](#35-ترکیب-چند-operator)
36. [Operatorها و String](#36-operatorها-و-string)
37. [Operatorها و Number](#37-operatorها-و-number)
38. [Operatorها و Boolean](#38-operatorها-و-boolean)
39. [Operatorها و Object](#39-operatorها-و-object)
40. [Operatorها و Array](#40-operatorها-و-array)
41. [اشتباهات رایج](#41-اشتباهات-رایج)
42. [نکات پیشرفته](#42-نکات-پیشرفته)
43. [مثال‌های ترکیبی](#43-مثال‌های-ترکیبی)
44. [تمرین‌ها](#44-تمرینها)
45. [جمع‌بندی](#45-جمع‌بندی)
46. [منابع معتبر](#46-منابع-معتبر)

---

## 1. Operator چیست؟
**Operator (عملگر)** نماد یا کاراکتری است که به موتور جاوااسکریپت می‌گوید چه عملیات ریاضی، منطقی یا مقایسه‌ای را روی مقادیر (Values) یا متغیرها (Variables) انجام دهد.
- **تفاوت با Function:** Operatorها بخشی از Syntax (دستور زبان) هستند و مستقیماً توسط موتور اجرا می‌شوند، در حالی که Functionها بلوک‌های کدی هستند که فراخوانی می‌شوند.

## 2. Operand چیست؟
**Operand (عملوند)** مقداری است که Operator روی آن عمل می‌کند.
```javascript
let result = 10 + 20;
```
- `10` و `20`: **Operand** (عملوند) هستند.
- `+`: **Operator** (عملگر) است.
- `result`: متغیری است که **خروجی** عملیات را در خود ذخیره می‌کند.

## 3. انواع Operatorها در JavaScript
- **Arithmetic:** عملیات ریاضی (`+`, `-`, `*`, `/`)
- **Assignment:** مقداردهی (`=`, `+=`)
- **Comparison:** مقایسه (`>`, `<`, `===`)
- **Logical:** منطق بولی (`&&`, `||`, `!`)
- **Unary:** تک‌عملوندی (`typeof`, `delete`, `++`)
- **Relational:** رابطه‌ای (`in`, `instanceof`)
- **Conditional / Ternary:** شرطی (`?:`)
- **Bitwise:** عملیات روی بیت‌ها (`&`, `|`, `^`)
- **String:** الحاق رشته (`+`)
- **Nullish Coalescing:** مدیریت مقادیر پوچ (`??`)
- **Optional Chaining:** دسترسی ایمن به پراپرتی‌ها (`?.`)

> **نکته:** Operator نماد است (مثل `+`)، اما **Expression (عبارت)** ترکیبی از Operandها و Operatorهاست که در نهایت به یک Value ارزیابی می‌شود (مثل `10 + 20`).

---

## 4. Arithmetic Operators
این عملگرها برای محاسبات ریاضی استفاده می‌شوند.

```javascript
let a = 8;
let b = 2;

console.log(a + b);  // 10 (جمع)
console.log(a - b);  // 6  (تفریق)
console.log(a * b);  // 16 (ضرب)
console.log(a / b);  // 4  (تقسیم)
console.log(a % b);  // 0  (باقیمانده تقسیم)
console.log(a ** b); // 64 (توان: 8 به توان 2)
```
**نکته مهم (Precedence):**
```javascript
const c = (a + b) * 3; // (8 + 2) * 3 = 30
```
پرانتز `()` بالاترین اولویت را دارد. بدون پرانتز، `*` قبل از `+` اجرا می‌شد.

---

## 5. Assignment Operators
برای اختصاص مقدار به متغیر استفاده می‌شوند.

```javascript
let a = 50;
let b = 30;

a *= b; // معادل است با: a = a * b; (یعنی a = 50 * 30)
console.log(a); // 1500
```
سایر موارد: `+=`, `-=`, `/=`, `%=`, `**=`.
**عملگرهای منطقی جدید (Logical Assignment):**
- `a &&= b`: اگر `a` truthy باشد، `b` را در `a` قرار می‌دهد.
- `a ||= b`: اگر `a` falsy باشد، `b` را در `a` قرار می‌دهد.
- `a ??= b`: اگر `a` null یا undefined باشد، `b` را در `a` قرار می‌دهد.

---

## 6. Comparison Operators
نتیجه این عملگرها همیشه `true` یا `false` است.

```javascript
let a = 10;
let b = 10;

console.log(a == b);  // true (مقایسه با تبدیل نوع)
console.log(a === b); // true (مقایسه سخت‌گیرانه: هم مقدار، هم نوع)
```

---

## 7. Logical Operators
شامل `!` (NOT)، `&&` (AND)، `||` (OR). این‌ها فقط با Boolean کار نمی‌کنند و می‌توانند خود مقادیر را برگردانند (Short-Circuit).

---

## 8. NOT Operator `!`
مقدار را به Boolean تبدیل کرده و سپس آن را معکوس می‌کند.
```javascript
let a = true;
let b = false;

console.log(!a); // false
console.log(!b); // true

console.log(!10);      // false (چون 10Truthy است، معکوس آن false می‌شود)
console.log(!0);       // true  (چون 0Falsy است، معکوس آن true می‌شود)
console.log(!"hello"); // false
console.log(!"");      // true
```

---

## 9. Double NOT `!!`
یک ترفند رایج برای تبدیل صریح (Explicit) هر مقداری به Boolean واقعی (`true` یا `false`). معادل `Boolean(value)` است.
```javascript
console.log(!!10);        // true
console.log(!!0);         // false
console.log(!!"hello");   // true
console.log(!!"");        // false
console.log(!!null);      // false
console.log(!!undefined); // false
```

---

## 10. AND Operator `&&`
اگر عملوند اول falsy باشد، همان را برمی‌گرداند (Short-Circuit). در غیر این صورت، عملوند دوم را برمی‌گرداند.
```javascript
console.log("hello" && "world"); // "world"
console.log(10 && 20);           // 20
console.log(0 && 20);            // 0 (چون 0 falsy است، ارزیابی متوقف می‌شود)
console.log(null && "hello");    // null
```

---

## 11. OR Operator `||`
اگر عملوند اول truthy باشد، همان را برمی‌گرداند (Short-Circuit). در غیر این صورت، عملوند دوم را برمی‌گرداند.
```javascript
console.log("hello" || "world"); // "hello"
console.log("" || "world");      // "world"
console.log(0 || 100);           // 100

const x1 = "js" || "ali";
console.log(x1); // "js" (چون "js" truthy است، ارزیابی متوقف و همان برگردانده می‌شود)
```

---

## 12. Nullish Coalescing Operator `??`
فقط و فقط اگر مقدار سمت چپ `null` یا `undefined` باشد، مقدار سمت راست را برمی‌گرداند. سایر مقادیر Falsy (مثل `0` یا `""`) را معتبر می‌داند.
```javascript
const x2 = 0 ?? "js";
console.log(x2); // 0 (چون 0 نه null است نه undefined)

console.log(null ?? "default");      // "default"
console.log(undefined ?? "default"); // "default"
console.log(false ?? "default");     // false
console.log(0 ?? "default");         // 0
console.log("" ?? "default");        // ""
```

---

## 13. تفاوت `||` و `??`
این یکی از مهم‌ترین مفاهیم برای مدیریت مقادیر پیش‌فرض است.

| مقدار سمت چپ | `|| "default"` | `?? "default"` | دلیل |
| :--- | :--- | :--- | :--- |
| `0` | `"default"` | `0` | `||` عدد 0 را falsy می‌داند، اما `??` آن را معتبر می‌داند. |
| `""` | `"default"` | `""` | `||` رشته خالی را falsy می‌داند. |
| `false` | `"default"` | `false` | `||` مقدار false را falsy می‌داند. |
| `null` | `"default"` | `"default"` | هر دو، null را پوچ می‌دانند. |

---

## 14. Conditional / Ternary Operator `?:`
تنها Operator سه‌تایی در جاوااسکریپت. جایگزین مختصر برای `if/else` است که **مقدار برمی‌گرداند**.
```javascript
let age = 20;
const checkAdult = age > 50 ? "old" : "young";
console.log(checkAdult); // "young"
```
- `condition`: `age > 50`
- `?`: اگر شرط true بود، عبارت بعدی اجرا شود.
- `:`: اگر شرط false بود، عبارت بعدی اجرا شود.
> **هشدار:** از Nested Ternary (شرط‌های تو در تو مثل `a ? b : c ? d : e`) به شدت پرهیز کنید چون خوانایی کد را نابود می‌کند.

---

## 15. Increment و Decrement
به ترتیب برای افزایش یا کاهش یک واحدی متغیر استفاده می‌شوند.
```javascript
let a = 10;
console.log(++a); // 11 (اول افزایش می‌دهد، بعد برمی‌گرداند)
console.log(a);   // 11
```

---

## 16. Prefix و Postfix
تفاوت در زمان بازگرداندن مقدار است.
```javascript
let b = 10;
console.log(b++); // 10 (اول مقدار فعلی را برمی‌گرداند، بعد افزایش می‌دهد)
console.log(b);   // 11
```
همین قاعده برای `--a` (Prefix Decrement) و `a--` (Postfix Decrement) برقرار است.

---

## 17. Unary Operators
عملگرهایی که فقط به یک Operand نیاز دارند.
شامل: `+`, `-`, `!`, `~`, `typeof`, `delete`, `void`.

---

## 18. Unary Plus و Unary Minus
- Unary Plus (`+`): سعی می‌کند مقدار را به Number تبدیل کند.
- Unary Minus (`-`): مقدار را به Number تبدیل کرده و علامت آن را منفی می‌کند.
```javascript
console.log(+"10"); // 10 (Number)
console.log(+"hello"); // NaN
console.log(-"5"); // -5
```

---

## 19. `typeof` Operator
نوع داده یک مقدار را به صورت رشته برمی‌گرداند.
```javascript
console.log(typeof 10);        // "number"
console.log(typeof "hello");   // "string"
console.log(typeof true);      // "boolean"
console.log(typeof undefined); // "undefined"
console.log(typeof null);      // "object" (یک باگ تاریخی در JS که هرگز اصلاح نشد!)
console.log(typeof []);        // "object" (آرایه‌ها در JS نوعی Object هستند)
console.log(typeof {});        // "object"
console.log(typeof function(){}); // "function" (استثنای مفید)
```

---

## 20. `delete` Operator
برای حذف یک Property از یک Object استفاده می‌شود.
```javascript
const user = { name: "Ali", age: 20 };
delete user.age;
console.log(user); // { name: "Ali" }
```
**تفاوت با `undefined`:**
- `delete user.age`: پراپرتی `age` کاملاً از Object حذف می‌شود (`"age" in user` می‌شود `false`).
- `user.age = undefined`: پراپرتی وجود دارد، اما مقدارش `undefined` است (`"age" in user` می‌شود `true`).

---

## 21. `void` Operator
عبارت مقابل خود را ارزیابی می‌کند و همیشه `undefined` برمی‌گرداند.
```javascript
console.log(void 0); // undefined
```
**کاربرد:** در گذشته برای اطمینان از دریافت `undefined` واقعی (چون در ES5 متغیر `undefined` قابل بازنویسی بود) یا در لینک‌های HTML به صورت `href="javascript:void(0)"` برای جلوگیری از رفرش صفحه استفاده می‌شد.

---

## 22. Relational Operators
- **`in`**: بررسی می‌کند آیا یک Property (رشته یا Symbol) در یک Object یا زنجیره Prototype آن وجود دارد.
```javascript
const user = { name: "Ali", age: 20 };
console.log("name" in user);  // true
console.log("email" in user); // false
console.log("toString" in user); // true (چون در Prototype وجود دارد)
```
- **`instanceof`**: بررسی می‌کند آیا یک Object نمونه‌ای از یک Constructor خاص است (بررسی زنجیره Prototype).
```javascript
console.log([] instanceof Array); // true
console.log({} instanceof Object); // true
```

---

## 23. Equality Operators
- `=` : انتساب (Assignment) است، نه مقایسه!
- `==` : مقایسه با تبدیل نوع (Loose Equality).
- `===` : مقایسه سخت‌گیرانه (Strict Equality: بدون تبدیل نوع).
- `!=` و `!==` : معکوس دو مورد بالا.

---

## 24. تفاوت `==` و `===`
```javascript
console.log(10 == "10");  // true (جاوااسکریپت رشته "10" را به عدد 10 تبدیل می‌کند)
console.log(10 === "10"); // false (نوع‌ها متفاوت هستند: Number vs String)
```
> **قانون طلایی:** همیشه در مقایسه از `===` و `!==` استفاده کنید مگر اینکه دلیل بسیار خاصی برای استفاده از `==` داشته باشید.

---

## 25. تفاوت `!=` و `!==`
```javascript
console.log(10 != "10");  // false (چون با تبدیل نوع برابرند)
console.log(10 !== "10"); // true (چون نوع‌ها متفاوتند، پس "نامساوی سخت‌گیرانه" برقرار است)
```

---

## 26. Type Coercion در Operatorها
تبدیل نوع خودکار (Implicit) که توسط موتور JS انجام می‌شود.
```javascript
console.log("10" + 5);  // "105" (عملگر + وقتی یک طرف String باشد، الحاق رشته انجام می‌دهد)
console.log("10" - 5);  // 5   (عملگر - فقط روی اعداد کار می‌کند، پس "10" به عدد تبدیل می‌شود)
console.log("10" * 2);  // 20
console.log(true + 1);  // 2   (true به 1 تبدیل می‌شود)
```

---

## 27. Truthiness و Falsiness
مقادیری که در زمینه Boolean به `false` تبدیل می‌شوند، **Falsy** نام دارند. در JS فقط 8 مقدار Falsy وجود دارد:
1. `false`
2. `0`
3. `-0`
4. `0n` (BigInt zero)
5. `""` (رشته خالی)
6. `null`
7. `undefined`
8. `NaN`

**هر چیز دیگری Truthy است** (حتی `"0"`, `"false"`, `[]`, `{}`).
```javascript
if ("hello") { console.log("executed"); } // اجرا می‌شود چون "hello" Truthy است.
```

---

## 28. Short-Circuit Evaluation
ارزیابی میان‌بر: موتور JS به محض اینکه نتیجه نهایی یک عبارت منطقی قطعی شود، ارزیابی بقیه عبارت را متوقف می‌کند.
```javascript
false && console.log("hello"); // چیزی چاپ نمی‌شود (چون سمت چپ false است، نتیجه نهایی قطعاً false است)
true || console.log("world");  // چیزی چاپ نمی‌شود (چون سمت چپ true است، نتیجه نهایی قطعاً true است)
```
**کاربرد واقعی:**
```javascript
const userName = user && user.name; // اگر user وجود داشته باشد، name را بگیر (جلوگیری از خطا)
const config = userConfig || defaultConfig; // مقداردهی پیش‌فرض
```

---

## 29. Operator Precedence (اولویت عملگرها)
مشخص می‌کند کدام عملگر زودتر اجرا شود. (مشابه PEMDAS در ریاضی).
```javascript
const result1 = 10 + 5 * 2; // 20 (ضرب اولویت بالاتری نسبت به جمع دارد)
const result2 = (10 + 5) * 2; // 30 (پرانتز بالاترین اولویت را دارد)
```
ترتیب تقریبی (از بالا به پایین):
1. `()`, `?.`, `[]`
2. `++`, `--`, `!`, `typeof`, `void`, `delete` (Unary)
3. `**`
4. `*`, `/`, `%`
5. `+`, `-`
6. `<`, `<=`, `>`, `>=`, `in`, `instanceof`
7. `==`, `!=`, `===`, `!==`
8. `&&`
9. `||`
10. `??`
11. `?:` (Ternary)
12. `=`, `+=`, `-=`, `??=`, `||=`, `&&=` (Assignment)

---

## 30. Operator Associativity (شرکت‌پذیری)
وقتی چند عملگر با **اولویت یکسان** پشت سر هم می‌آیند، Associativity جهت اجرا را مشخص می‌کند.
- **Left-to-Right (چپ به راست):** اکثر عملگرها مثل `-`, `+`, `*`, `&&`, `||`.
  ```javascript
  let res = 10 - 5 - 2; // معادل (10 - 5) - 2 = 3
  ```
- **Right-to-Left (راست به چپ):** Assignment (`=`), Ternary (`?:`), Unary، و توان (`**`).
  ```javascript
  let a, b, c;
  a = b = c = 5; // ابتدا c=5، سپس b=5، سپس a=5
  ```

---

## 31. تفاوت `=` و `==` و `===`
- `=`: مقدار را اختصاص می‌دهد (Assignment).
- `==`: مقدار را با تبدیل نوع مقایسه می‌کند.
- `===`: مقدار و نوع را بدون تبدیل مقایسه می‌کند.

---

## 32. تفاوت `&&`، `||` و `??`
- `&&`: اولین مقدار Falsy یا آخرین مقدار را برمی‌گرداند.
- `||`: اولین مقدار Truthy یا آخرین مقدار را برمی‌گرداند.
- `??`: اولین مقداری که `null` یا `undefined` نباشد را برمی‌گرداند.

---

## 33. ترکیب چند Operator
```javascript
const age = 20;
const isActive = true;

// مرحله 1: age >= 18 (true)
// مرحله 2: true && isActive (true)
// مرحله 3: true ? "Allowed" : "Not Allowed"
const result = age >= 18 && isActive ? "Allowed" : "Not Allowed";
console.log(result); // "Allowed"
```

---

## 34. Operatorها و String
عملگر `+` با Stringها به معنای **الحاق (Concatenation)** است.
```javascript
console.log("Hello " + "World"); // "Hello World"
console.log("10" + 5); // "105" (عدد 5 به رشته تبدیل و چسبانده می‌شود)
```

---

## 35. Operatorها و Number
تمام عملگرهای ریاضی (`-`, `*`, `/`, `%`, `**`) عملوندها را به Number تبدیل می‌کنند.
```javascript
console.log("10" - "2"); // 8
console.log("10" * "2"); // 20
```

---

## 36. Operatorها و Boolean
در عملیات ریاضی، `true` به `1` و `false` به `0` تبدیل می‌شود.
```javascript
console.log(true + true); // 2
console.log(false * 10);  // 0
```

---

## 37. Operatorها و Object / Array
هنگام استفاده از `+`، اشیاء و آرایه‌ها ابتدا به Primitive (معمولاً رشته) تبدیل می‌شوند (از طریق متد `toString` یا `valueOf`).
```javascript
console.log([] + []); // "" (آرایه خالی به رشته خالی تبدیل می‌شود)
console.log({} + []); // 0 یا "[object Object]" بسته به محیط اجرا (رفتار پیچیده پارسینگ)
```
**مقایسه Reference:**
```javascript
const a = [];
const b = [];
console.log(a == b);  // false
console.log(a === b); // false
```
دو آرایه یا Object جداگانه، حتی اگر محتوای یکسانی داشته باشند، به دلیل داشتن **آدرس حافظه (Reference)** متفاوت، هرگز برابر نیستند.

---

## 38. Bitwise Operators (پیشرفته)
این عملگرها اعداد را به نمایش باینری (32 بیتی) تبدیل کرده و عملیات را روی بیت‌ها انجام می‌دهند.
- `&` (AND): اگر هر دو بیت 1 باشند، 1 می‌شود.
- `|` (OR): اگر حداقل یکی 1 باشد، 1 می‌شود.
- `^` (XOR): اگر بیت‌ها متفاوت باشند، 1 می‌شود.
- `~` (NOT): بیت‌ها را معکوس می‌کند (`~x` برابر است با `-(x + 1)`).
- `<<` (Shift Left), `>>` (Shift Right), `>>>` (Shift Right با پر کردن صفر).
> **کاربرد:** در عملکردهای سطح پایین، ماسک کردن بیت‌ها، یا الگوریتم‌های رمزنگاری ساده. در توسعه وب روزمره به ندرت استفاده می‌شود.

---

## 39. Operatorهای جدید و مدرن JavaScript
- **`?.` (Optional Chaining):** اگر مقدار سمت چپ null/undefined باشد، به جای خطا، `undefined` برمی‌گرداند.
  ```javascript
  const user = {};
  console.log(user.address?.city); // undefined (به جای TypeError)
  ```
- **`??=`, `||=`, `&&=` (Logical Assignment):** ترکیب تخصیص و منطق که در بخش 5 توضیح داده شد.

---

## 40. اشتباهات رایج
1. **استفاده از `=` به جای `==` یا `===` در شرط:** `if (a = 5)` همیشه true می‌شود و مقدار `a` را تغییر می‌دهد!
2. **مقایسه آرایه‌ها/اشیاء:** `[] == []` همیشه `false` است.
3. **نادیده گرفتن `typeof null`:** فکر می‌کنند `null` نوع `null` دارد، در حالی که `"object"` است.
4. **استفاده از `||` برای مقدار پیش‌فرض عددی:** `0 || 10` می‌شود `10` (در حالی که شاید `0` مقدار معتبری باشد). راه حل: `??`.
5. **فرض اینکه `&&` همیشه Boolean برمی‌گرداند:** `"a" && "b"` مقدار `"b"` را برمی‌گرداند.
6. **اشتباه در Prefix/Postfix:** استفاده از `a++` درون یک عبارت پیچیده و انتظار مقدار افزایش‌یافته.
7. **مقایسه `NaN`:** `NaN === NaN` همیشه `false` است. باید از `Number.isNaN()` استفاده کرد.
8. **جمع رشته و عدد:** `"5" + 3` می‌شود `"53"`، نه `8`.
9. **استفاده از `in` برای آرایه:** `"length" in []` true است، اما معمولاً هدف بررسی مقدار است نه پراپرتی.
10. **فراموش کردن پرانتز در Ternary تو در تو:** باعث خوانایی بسیار پایین می‌شود.
11. **استفاده از `delete` برای متغیرهای `var`/`let`/`const`:** کار نمی‌کند و خطا می‌دهد (فقط برای پراپرتی Object است).
12. **تبدیل نوع ضمنی ناخواسته:** `true == 1` (true) اما `true === 1` (false).
13. **استفاده از `==` با `null`:** `null == undefined` true است، اما `null === undefined` false است.
14. **اولویت عملگرها:** `a && b || c` ممکن است به دلیل اولویت `&&` بالاتر از `||`، انتظارات شما را برآورده نکند.
15. **استفاده از `+` برای تبدیل نوع به جای `Number()`:** اگرچه `+"10"` کار می‌کند، اما `Number("10")` خواناتر است.

---

## 41. مثال‌های ترکیبی (20 مورد)

1. `console.log(5 + "5" - 2);`
   - **خروجی:** `53` (رشته) -> `51` (عدد). دلیل: `5 + "5"` می‌شود `"55"`. سپس `"55" - 2` باعث تبدیل رشته به عدد و تفریق می‌شود.
2. `console.log(true + false + 1);`
   - **خروجی:** `2`. دلیل: `1 + 0 + 1`.
3. `console.log(0 || "Hello" && "World");`
   - **خروجی:** `"World"`. دلیل: اولویت `&&` بالاتر از `||` است. `"Hello" && "World"` می‌شود `"World"`. سپس `0 || "World"` می‌شود `"World"`.
4. `console.log(null ?? 0 || "default");`
   - **خروجی:** `0`. دلیل: `null ?? 0` می‌شود `0`. سپس `0 || "default"` می‌شود `"default"`. **صبر کنید!** اولویت `??` و `||` در ES2020 نیاز به پرانتز دارد اگر ترکیب شوند، اما اگر بدون پرانتز باشند، `??` اولویت کمتری نسبت به `||` ندارد، بلکه ترکیب مستقیم آن‌ها بدون پرانتز **Syntax Error** است! (نکته پیشرفته: `null ?? (0 || "default")` می‌شود `"default"`).
5. `console.log(!!"" + !![] + !!{});`
   - **خروجی:** `2`. دلیل: `false + true + true` -> `0 + 1 + 1 = 2`.
6. `let x = 10; console.log(x++ + ++x);`
   - **خروجی:** `22`. دلیل: `x++` مقدار 10 را برمی‌گرداند و x می‌شود 11. سپس `++x` مقدار x را به 12 افزایش داده و 12 را برمی‌گرداند. `10 + 12 = 22`.
7. `console.log([] == ![]);`
   - **خروجی:** `true`. دلیل: `![]` می‌شود `false`. سپس `[] == false`. آرایه خالی به رشته `""` و سپس به عدد `0` تبدیل می‌شود. `false` هم به `0` تبدیل می‌شود. `0 == 0` true است.
8. `console.log({} + []);`
   - **خروجی:** `0` (در Node.js) یا `"[object Object]"` (در برخی کنسول‌های مرورگر به دلیل پارسینگ متفاوت). دلیل: رفتار پیچیده تبدیل نوع ضمنی.
9. `console.log(3 > 2 > 1);`
   - **خروجی:** `false`. دلیل: `3 > 2` می‌شود `true`. سپس `true > 1` می‌شود `1 > 1` که `false` است.
10. `console.log(1 < 2 < 3);`
    - **خروجی:** `true`. دلیل: `1 < 2` می‌شود `true`. سپس `true < 3` می‌شود `1 < 3` که `true` است.
11. `const a = { val: 1 }; const b = a; a.val = 2; console.log(b.val);`
    - **خروجی:** `2`. دلیل: اشیاء با Reference کپی می‌شوند، نه با Value.
12. `console.log("5" * "2" / "1");`
    - **خروجی:** `10`. دلیل: تمام عملوندها به عدد تبدیل می‌شوند.
13. `console.log(10 ** 2 ** 3);`
    - **خروجی:** `100000000` (10 به توان 8). دلیل: عملگر `**` Right-to-Left Associative است. ابتدا `2 ** 3 = 8`، سپس `10 ** 8`.
14. `let y; console.log(y ??= 5);`
    - **خروجی:** `5`. دلیل: `y` undefined است، پس مقدار 5 اختصاص می‌یابد.
15. `console.log("a" in ["a", "b"]);`
    - **خروجی:** `false`. دلیل: عملگر `in` ایندکس‌ها (0, 1) یا پراپرتی‌ها را چک می‌کند، نه مقادیر را.
16. `console.log(0.1 + 0.2 === 0.3);`
    - **خروجی:** `false`. دلیل: خطای دقت شناور (Floating Point) در استاندارد IEEE 754. حاصل `0.30000000000000004` است.
17. `console.log(typeof typeof 10);`
    - **خروجی:** `"string"`. دلیل: `typeof 10` می‌شود `"number"` (که خودش یک رشته است). `typeof "number"` می‌شود `"string"`.
18. `console.log(1 && 2 && 3 && 4);`
    - **خروجی:** `4`. دلیل: همه truthy هستند، پس آخرین مقدار برگردانده می‌شود.
19. `console.log(0 || "" || null || "found");`
    - **خروجی:** `"found"`. دلیل: اولین مقدار truthy را برمی‌گرداند.
20. `console.log(delete Object.prototype);`
    - **خروجی:** `false` (در Strict Mode خطا می‌دهد). دلیل: پراپرتی‌های پیکربندی‌نشده (non-configurable) قابل حذف نیستند.

---

## 42. تمرین‌ها

### Beginner
1. حاصل `15 % 4` چیست؟
2. مقدار `let x = 5; x += 3;` چیست؟
3. خروجی `typeof "100"` چیست؟
4. آیا `"5" == 5` برابر است با `true` یا `false`؟
5. حاصل `!!"Hello"` چیست؟

### Intermediate
6. خروجی `console.log(0 || "JS" || "Python")` چیست؟
7. خروجی `console.log(0 ?? "JS" ?? "Python")` چیست؟
8. مقدار `let a = 10; console.log(a++); console.log(a);` به ترتیب چیست؟
9. آیا `[] == false` برابر با `true` است یا `false`؟ (فکر کنید!)
10. خروجی `5 + 2 * "3"` چیست؟

### Advanced
11. خروجی `console.log(10 > 9 > 8)` چیست؟
12. مقدار `const x = null; console.log(x ??= "default");` چیست؟
13. چرا `console.log(NaN === NaN)` مقدار `false` می‌دهد؟
14. خروجی `console.log(typeof null)` چیست و چرا اینطور است؟
15. حاصل `console.log(2 ** 3 ** 2)` چیست؟ (به Associativity دقت کنید).

### Expert
16. خروجی `console.log([] + {})` چیست؟
17. مقدار `console.log("foo" && "bar" || "baz")` چیست؟
18. آیا `delete` می‌تواند یک متغیر تعریف شده با `let` را حذف کند؟
19. خروجی `console.log(1 < 2 < 3 === true)` چیست؟
20. چگونه بدون استفاده از `Boolean()` و `!!`، مقدار `"0"` را به `false` تبدیل منطقی کنید؟ (راهنمایی: با عملگرهای مقایسه‌ای).

---

## 43. Solutions (پاسخ تمرین‌ها)
1. `3` (باقیمانده 15 تقسیم بر 4).
2. `8`.
3. `"string"`.
4. `true` (به دلیل Type Coercion).
5. `true`.
6. `"JS"` (اولین مقدار truthy).
7. `0` (چون 0 نه null است نه undefined).
8. `10` سپس `11`.
9. `true` (آرایه خالی به `""` و سپس به `0` تبدیل می‌شود، `false` هم به `0` تبدیل می‌شود).
10. `11` (ابتدا ضرب: `2 * "3"` می‌شود `6`، سپس `5 + 6`).
11. `false` (`10 > 9` می‌شود `true`، سپس `true > 8` می‌شود `1 > 8` که `false` است).
12. `"default"` (چون `x` برابر `null` است).
13. طبق استاندارد IEEE 754، `NaN` با هیچ چیز، حتی خودش، برابر نیست.
14. `"object"`. این یک باگ تاریخی در نسخه اول جاوااسکریپت بود که برای حفظ سازگندی (Backward Compatibility) هرگز اصلاح نشد.
15. `512`. (چون `**` راست‌به‌چپ است: ابتدا `3 ** 2 = 9`، سپس `2 ** 9 = 512`).
16. `"[object Object]"` (هر دو به رشته تبدیل و الحاق می‌شوند).
17. `"bar"` (`"foo" && "bar"` می‌شود `"bar"`. سپس `"bar" || "baz"` می‌شود `"bar"`).
18. خیر، `delete` فقط برای پراپرتی‌های اشیاء کار می‌کند و برای متغیرهای Lexical (`let`/`const`) خطای Strict Mode می‌دهد.
19. `true` (`1 < 2` می‌شود `true`. `true < 3` می‌شود `1 < 3` که `true` است. `true === true` می‌شود `true`).
20. `Number("0") === 0` یا `+"0" === 0` یا `"0" == false`.

---

## 44. نکات مصاحبه‌ای (JavaScript Operators Interview Questions)

1. **سوال:** خروجی `10 + "5"` چیست؟
   **پاسخ:** `"105"`. عملگر `+` وقتی یک طرف رشته باشد، عملیات الحاق (Concatenation) انجام می‌دهد.
2. **سوال:** تفاوت `0 || "JS"` و `0 ?? "JS"` چیست؟
   **پاسخ:** اولی `"JS"` برمی‌گرداند (چون 0 falsy است). دومی `0` برمی‌گرداند (چون 0 null/undefined نیست).
3. **سوال:** چرا `[] == ![]` برابر `true` است؟
   **پاسخ:** `![]` ارزیابی شده و `false` می‌شود. سپس `[] == false`. آرایه خالی به رشته `""` و سپس به عدد `0` تبدیل می‌شود. `false` نیز به `0` تبدیل می‌شود. `0 == 0` true است.
4. **سوال:** خروجی `typeof typeof 10` چیست؟
   **پاسخ:** `"string"`. `typeof 10` می‌شود `"number"` (رشته). `typeof "number"` می‌شود `"string"`.
5. **سوال:** چگونه بررسی کنیم یک متغیر دقیقاً `NaN` است؟
   **پاسخ:** با استفاده از `Number.isNaN(x)`. استفاده از `x === NaN` همیشه `false` می‌شود.
6. **سوال:** اولویت عملگر `??` نسبت به `||` چگونه است؟
   **پاسخ:** ترکیب مستقیم آن‌ها بدون پرانتز (مثل `a ?? b || c`) در جاوااسکریپت مدرن **Syntax Error** می‌دهد تا از ابهام جلوگیری شود. باید از پرانتز استفاده کرد.
7. **سوال:** خروجی `3 > 2 > 1` چیست؟
   **پاسخ:** `false`. چون `3 > 2` می‌شود `true`، و سپس `true > 1` می‌شود `1 > 1` که `false` است.
8. **سوال:** عملگر `void 0` چه کاربردی دارد؟
   **پاسخ:** تضمین می‌کند که مقدار `undefined` واقعی برگردانده شود، حتی اگر متغیر جهانی `undefined` در کدهای قدیمی بازنویسی شده باشد.
9. **سوال:** آیا عملگر `delete` روی متغیرهای `let` کار می‌کند؟
   **پاسخ:** خیر، فقط روی پراپرتی‌های قابل پیکربندی (configurable) اشیاء کار می‌کند.
10. **سوال:** تفاوت `a = a + 1` و `a++` چیست؟
    **پاسخ:** از نظر نتیجه نهایی روی `a` یکسان است، اما `a++` یک Expression است که مقدار *قبلی* `a` را برمی‌گرداند، در حالی که `a = a + 1` مقدار *جدید* را برمی‌گرداند.
11. **سوال:** چرا `0.1 + 0.2 === 0.3` برابر `false` است؟
    **پاسخ:** به دلیل محدودیت نمایش اعداد اعشاری در استاندارد IEEE 754 (Floating Point)، حاصل `0.30000000000000004` می‌شود.
12. **سوال:** خروجی `console.log(1 && 2 && 3)` چیست؟
    **پاسخ:** `3`. عملگر `&&` آخرین مقدار truthy را برمی‌گرداند.
13. **سوال:** عملگر `?.` (Optional Chaining) چه مشکلی را حل می‌کند؟
    **پاسخ:** از پرتاب خطای `TypeError: Cannot read properties of undefined` هنگام دسترسی به پراپرتی‌های تو در تو در اشیایی که ممکن است null/undefined باشند، جلوگیری می‌کند.
14. **سوال:** آیا `null === undefined` درست است؟
    **پاسخ:** خیر، `false` است. اما `null == undefined` درست است (`true`).
15. **سوال:** عملگر `~` (Bitwise NOT) روی عدد 5 چه می‌کند؟
    **پاسخ:** مقدار `-(5 + 1)` یعنی `-6` را برمی‌گرداند.
16. **سوال:** چگونه می‌توان فهمید یک آرایه واقعاً آرایه است؟ (چون `typeof []` می‌شود `"object"`)
    **پاسخ:** با استفاده از `Array.isArray([])`.
17. **سوال:** خروجی `console.log("5" - - "2")` چیست؟
    **پاسخ:** `7`. Unary Minus دوم `"2"` را به `-2` تبدیل می‌کند. سپس `"5" - (-2)` می‌شود `5 + 2 = 7`.
18. **سوال:** آیا می‌توان عملگرها را در جاوااسکریپت Overload (بازتعریف) کرد؟ (مثل ++ در C++)
    **پاسخ:** خیر، جاوااسکریپت از Operator Overloading پشتیبانی نمی‌کند.
19. **سوال:** تفاوت `in` و `hasOwnProperty` چیست؟
    **پاسخ:** `in` زنجیره Prototype را هم بررسی می‌کند، اما `hasOwnProperty` فقط پراپرتی‌های مستقیم خود شیء را چک می‌کند.
20. **سوال:** چرا توصیه می‌شود همیشه از `===` به جای `==` استفاده کنیم؟
    **پاسخ:** برای جلوگیری از تبدیل نوع ضمنی (Implicit Type Coercion) که می‌تواند منجر به باگ‌های غیرمنتظره و سخت‌ردیابی شود (مثل `"" == 0` که true است).

---

## 45. جمع‌بندی

| Operator | نام | کاربرد اصلی | سطح ضرورت |
| :--- | :--- | :--- | :--- |
| `=`, `+=`, `-=` | Assignment | مقداردهی به متغیرها | **ضروری (مبتدی)** |
| `+`, `-`, `*`, `/` | Arithmetic | محاسبات ریاضی | **ضروری (مبتدی)** |
| `===`, `!==` | Strict Equality | مقایسه دقیق مقدار و نوع | **ضروری (مبتدی)** |
| `&&`, `||`, `!` | Logical | ترکیب شرایط منطقی | **ضروری (مبتدی)** |
| `>`, `<`, `>=`, `<=` | Relational | مقایسه بزرگی/کوچکی | **ضروری (مبتدی)** |
| `?:` | Ternary | شرط‌های کوتاه و مقداردهی | متوسط |
| `??`, `?.` | Nullish / Optional | مدیریت ایمن مقادیر پوچ | **ضروری (متوسط)** |
| `typeof`, `instanceof` | Type/Instance | بررسی نوع داده یا کلاس | متوسط |
| `++`, `--` | Increment/Decrement | افزایش/کاهش یک واحدی | متوسط |
| `&`, `|`, `^`, `~`, `<<` | Bitwise | عملیات سطح بیت (پایین‌سطح) | پیشرفته |

**مسیر یادگیری پیشنهادی:**
1. ابتدا روی `=`، `+`، `-`، `===`، `&&`، `||` و `!` مسلط شوید.
2. سپس مفهوم **Type Coercion** و **Truthy/Falsy** را درک کنید تا رفتار `==` و `||` را بفهمید.
3. در نهایت، عملگرهای مدرن `??` و `?.` و مفاهیم پیشرفته‌ای مثل **Short-Circuit** و **Precedence** را برای نوشتن کد تمیز (Clean Code) فرا بگیرید.

---

## 46. منابع معتبر

برای اطمینان از صحت اطلاعات و مطالعه عمیق‌تر، به منابع رسمی زیر مراجعه کنید:

1. **MDN Web Docs (Mozilla)**
   - *عنوان:* [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators)
   - *توضیح:* مرجع اصلی و جامع برای تمام عملگرها، جدول اولویت‌ها و رفتارهای نوع داده.
2. **JavaScript.info**
   - *عنوان:* [Operators](https://javascript.info/operators)
   - *توضیح:* آموزش بسیار روان و مرحله‌به‌مرحله با مثال‌های کاربردی، به‌ویژه برای مفاهیم Coercion و Short-Circuit.
3. **ECMAScript Language Specification (TC39)**
   - *عنوان:* [ECMAScript® 2023 Language Specification - Expressions](https://tc39.es/ecma262/#sec-ecmascript-language-expressions)
   - *توضیح:* منبع نهایی و استاندارد رسمی رفتار عملگرها (برای درک عمیق فنی و موارد Edge Case).
4. **MDN Web Docs**
   - *عنوان:* [Operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence)
   - *توضیح:* جدول کامل و به‌روز اولویت و شرکت‌پذیری (Associativity) تمام عملگرها.

---
*این سند با رعایت استانداردهای جاوااسکریپت مدرن (ES2023+) و با هدف آموزش اصولی تهیه شده است. برای هرگونه بازخورد یا اصلاح، به Repository آموزشی مراجعه کنید.*
