# قوانین بسیار مهم درباره JavaScript

این قوانین را در تمام محتوا رعایت کن:

1. JavaScript را یک زبان **Prototype-based** معرفی کن.
2. توضیح بده که JavaScript فقط Class-based نیست و Objectها نقش اصلی را دارند.
3. توضیح بده که `class` در JavaScript یک Syntax سطح بالاتر برای کار با Prototypeهاست.
4. تفاوت `prototype` و `[[Prototype]]` را به‌صورت شفاف توضیح بده.
5. تأکید کن که `prototype` یک Property معمولاً مرتبط با Functionهای سازنده است، اما `[[Prototype]]` یک Internal Slot مربوط به Object است.
6. توضیح بده که `__proto__` با `prototype` یکی نیست.
7. استفاده از `Object.getPrototypeOf()` را برای مشاهده Prototype ترجیح بده.
8. توضیح بده که `__proto__` یک Accessor قدیمی و غیرتوصیه‌شده است.
9. از مثال‌های JavaScript مدرن استفاده کن.
10. از `const` و `let` استفاده کن و `var` را فقط در صورت نیاز توضیح بده.
11. هر مفهوم را ابتدا با مثال ساده و سپس با مثال دقیق‌تر توضیح بده.
12. از اصطلاحات C# و Java به‌صورت مستقیم استفاده نکن؛ مگر برای مقایسه و رفع سوءتفاهم.
13. اگر قابلیتی به نسخه خاصی از JavaScript وابسته است، وضعیت پشتیبانی آن را از منبع معتبر بررسی کن.
14. هرجا رفتار داخلی موتور JavaScript مطرح می‌شود، تفاوت میان Specification و پیاده‌سازی موتور را روشن کن.
15. از ادعاهای نادرست مانند «همه Objectها مستقیماً از Object.prototype ارث می‌برند» خودداری کن؛ Objectهایی مانند `Object.create(null)` را نیز توضیح بده.

---

# زبان و سبک نوشتار

* زبان اصلی: **فارسی**
* اصطلاحات تخصصی انگلیسی را در کنار معادل فارسی بنویس.
* لحن آموزشی، ساده، روان و حرفه‌ای باشد.
* فرض کن خواننده مبتدی است.
* ابتدا مفهوم را با زبان ساده توضیح بده، سپس وارد جزئیات فنی شو.
* هر مفهوم را با مثال واقعی و سپس مثال کدنویسی توضیح بده.
* از پاراگراف‌های کوتاه و Headingهای منظم استفاده کن.
* از جدول فقط زمانی استفاده کن که برای مقایسه مفید باشد.
* از تکرار بی‌دلیل مطالب خودداری کن.
* کدها باید خوانا، استاندارد و قابل‌اجرا باشند.
* در صورت امکان، خروجی کد را نیز نشان بده.
* هرجا لازم است، با نمودار ASCII یا Mermaid ارتباط Objectها و Prototypeها را نمایش بده.

---

# ساختار کلی خروجی

خروجی باید یک فایل Markdown کامل و مناسب ریپوزیتوری GitHub باشد.

در ابتدای فایل:

* عنوان اصلی
* توضیح کوتاه

قرار بده.

ساختار پیشنهادی:

```markdown
# Prototype in JavaScript

توضیح کوتاه درباره Prototype

## Prerequisites

- JavaScript Basics
- Variables
- Functions
- Objects
- `this`
- Scope
- `new`


- [1. مقدمه‌ای بر Prototype](#1-مقدمه‌ای-بر-prototype)
- [2. Object و Property](#2-object-و-property)
- [3. Prototype چیست؟](#3-prototype-چیست)
- [4. Prototype Chain](#4-prototype-chain)
- [5. prototype و [[Prototype]]](#5-prototype-و-prototype)
- [6. Constructor Function](#6-constructor-function)
- [7. عملگر new](#7-عملگر-new)
- [8. Object.create](#8-objectcreate)
- [9. مشاهده و تغییر Prototype](#9-مشاهده-و-تغییر-prototype)
- [10. Inheritance با Prototype](#10-inheritance-با-prototype)
- [11. Class و Prototype](#11-class-و-prototype)
- [12. Property Lookup و Shadowing](#12-property-lookup-و-shadowing)
- [13. مباحث پیشرفته](#13-مباحث-پیشرفته)
- [14. اشتباهات رایج](#14-اشتباهات-رایج)
- [15. تمرین‌ها](#15-تمرینها)
- [16. جمع‌بندی](#16-جمع‌بندی)
- [17. منابع](#17-منابع)
```


---

# بخش اول: مقدمه‌ای بر Prototype

## 1.1 Prototype چیست؟

توضیح بده:

* Prototype به زبان ساده چیست؟
* چرا Prototype یکی از مفاهیم اصلی JavaScript است؟
* چرا JavaScript را Prototype-based می‌نامند؟
* Prototype چه مشکلی را حل می‌کند؟
* چگونه چند Object می‌توانند رفتار مشترک داشته باشند؟

مثال واقعی:

* چند خودرو که از یک رفتار مشترک استفاده می‌کنند.
* چند کاربر که متد `sayHello()` مشترک دارند.
* چند محصول که متد `getPrice()` مشترک دارند.

مثال ساده:

```javascript
const personPrototype = {
  sayHello() {
    console.log("Hello!");
  }
};

const person = Object.create(personPrototype);

person.sayHello();
```

توضیح بده:

* `personPrototype` چیست؟
* `person` چیست؟
* چرا `person` می‌تواند `sayHello()` را اجرا کند؟
* آیا متد واقعاً داخل خود `person` قرار دارد؟

---

## 1.2 Prototype چه چیزی نیست؟

توضیح بده:

* Prototype با Class یکی نیست.
* Prototype با Object یکی نیست.
* Prototype با Constructor Function یکی نیست.
* `prototype` با `[[Prototype]]` یکی نیست.
* Prototype به معنی کپی‌شدن کامل Object نیست.

برای هر مورد مثال ساده ارائه بده.

---

# بخش دوم: Object و Property

## 2.1 Object چیست؟

توضیح بده:

* Object چیست؟
* Own Property چیست؟
* Inherited Property چیست؟
* Property و Method چه تفاوتی دارند؟
* Object چگونه Propertyهای خود را نگهداری می‌کند؟

مثال:

```javascript
const person = {
  name: "Ali",

  sayHello() {
    console.log(`Hello, ${this.name}`);
  }
};
```

توضیح بده:

* `name` یک Own Property است.
* `sayHello` یک Method است.
* چگونه می‌توان Own Propertyها را بررسی کرد؟

---

## 2.2 Own Property و Inherited Property

مثال:

```javascript
const parent = {
  role: "admin"
};

const child = Object.create(parent);

child.name = "Ali";
```

توضیح بده:

* `name` کجا قرار دارد؟
* `role` کجا قرار دارد؟
* چرا `child.role` مقدار `"admin"` را برمی‌گرداند؟
* تفاوت Own Property و Inherited Property چیست؟

مثال‌های زیر را نیز توضیح بده:

```javascript
Object.hasOwn(child, "name");
Object.hasOwn(child, "role");
```

---

# بخش سوم: Prototype چیست؟

## 3.1 تعریف دقیق Prototype

توضیح بده:

* Prototype یک Object است.
* هر Object می‌تواند یک Prototype داشته باشد.
* Prototype خودش می‌تواند Prototype دیگری داشته باشد.
* این ارتباط یک زنجیره ایجاد می‌کند.
* در انتهای زنجیره معمولاً به `null` می‌رسیم.

نمودار ساده:

```text
object
   ↓
prototype
   ↓
prototype
   ↓
Object.prototype
   ↓
null
```

توضیح بده که این نمودار مفهومی است و زنجیره واقعی هر Object ممکن است متفاوت باشد.

---

## 3.2 چرا Prototype مهم است؟

توضیح بده:

* اشتراک رفتار
* کاهش تکرار متدها
* Property Lookup
* Inheritance
* ارتباط با Constructor Function
* ارتباط با Class
* نقش Prototype در Built-in Objectها

مثال:

```javascript
const personPrototype = {
  greet() {
    console.log(`Hello, ${this.name}`);
  }
};

const ali = Object.create(personPrototype);
const sara = Object.create(personPrototype);

ali.name = "Ali";
sara.name = "Sara";
```

توضیح بده چرا `ali.greet` و `sara.greet` به یک Function مشترک اشاره می‌کنند.

---

# بخش چهارم: Prototype Chain

## 4.1 Prototype Chain چیست؟

توضیح بده:

* Prototype Chain چیست؟
* چرا به آن زنجیره Prototype می‌گویند؟
* JavaScript چگونه از یک Object به Prototype آن می‌رود؟
* چرا جست‌وجو تا `null` ادامه پیدا می‌کند؟

مثال:

```javascript
const grandParent = {
  familyName: "Shabani"
};

const parent = Object.create(grandParent);
parent.parentName = "Reza";

const child = Object.create(parent);
child.name = "Ali";
```

نمودار:

```text
child
  ↓
parent
  ↓
grandParent
  ↓
Object.prototype
  ↓
null
```

---

## 4.2 Property Lookup

توضیح بده:

وقتی می‌نویسیم:

```javascript
child.familyName;
```

JavaScript چه مراحلی را طی می‌کند؟

توضیح بده:

1. ابتدا Object اصلی بررسی می‌شود.
2. اگر Property پیدا نشود، Prototype بررسی می‌شود.
3. این روند در زنجیره ادامه پیدا می‌کند.
4. اگر Property پیدا نشود و به `null` برسیم، نتیجه `undefined` است.

مثال‌های مختلف ارائه بده.

---

## 4.3 Shadowing

توضیح بده:

* Shadowing چیست؟
* چگونه یک Own Property می‌تواند Property ارث‌رسیده را پنهان کند؟
* چرا Property نزدیک‌تر اولویت دارد؟

مثال:

```javascript
const parent = {
  role: "admin"
};

const child = Object.create(parent);

console.log(child.role);

child.role = "user";

console.log(child.role);
console.log(parent.role);
```

توضیح خط‌به‌خط بده.

---

## 4.4 تغییر Prototype و اثر آن

توضیح بده:

* اگر Prototype تغییر کند، چه اتفاقی برای Objectهای وابسته می‌افتد؟
* چرا تغییر Prototype می‌تواند روی رفتار Objectها اثر بگذارد؟
* چرا تغییر Prototype در Runtime معمولاً توصیه نمی‌شود؟

---

# بخش پنجم: prototype و [[Prototype]]

## 5.1 `[[Prototype]]` چیست؟

توضیح بده:

* `[[Prototype]]` یک Internal Slot در Object است.
* این Slot به Object دیگری اشاره می‌کند.
* برای دسترسی استاندارد به آن از `Object.getPrototypeOf()` استفاده می‌کنیم.
* این مفهوم با Property معمولی `prototype` متفاوت است.

مثال:

```javascript
const parent = {
  greet() {
    console.log("Hello");
  }
};

const child = Object.create(parent);

console.log(Object.getPrototypeOf(child) === parent);
```

---

## 5.2 `prototype` چیست؟

توضیح بده:

* Functionها می‌توانند Propertyای به نام `prototype` داشته باشند.
* این Property معمولاً در Constructor Functionها اهمیت دارد.
* وقتی Function با `new` فراخوانی می‌شود، Prototype مربوط به Instance از آن استفاده می‌کند.
* Arrow Function به‌صورت پیش‌فرض `prototype` مخصوص Constructor ندارد.

مثال:

```javascript
function Person(name) {
  this.name = name;
}

console.log(Person.prototype);
```

مثال Arrow Function:

```javascript
const PersonArrow = () => {};

console.log(PersonArrow.prototype);
```

توضیح بده چرا خروجی این دو متفاوت است.

---

## 5.3 تفاوت `prototype` و `[[Prototype]]`

یک مقایسه دقیق اما ساده ارائه بده.

| مفهوم                     | توضیح                                   |
| ------------------------- | --------------------------------------- |
| `prototype`               | Property موجود روی Functionهای سازنده   |
| `[[Prototype]]`           | ارتباط داخلی یک Object با Prototype خود |
| `Object.getPrototypeOf()` | روش استاندارد مشاهده `[[Prototype]]`    |
| `Object.create()`         | ساخت Object با Prototype مشخص           |

مثال کامل ارائه بده:

```javascript
function Person() {}

const person = new Person();

console.log(Person.prototype);
console.log(Object.getPrototypeOf(person));

console.log(Object.getPrototypeOf(person) === Person.prototype);
```

---

# بخش ششم: Constructor Function

## 6.1 Constructor Function چیست؟

توضیح بده:

* Constructor Function چیست؟
* چرا قبل از معرفی Classها استفاده می‌شد؟
* تفاوت Function معمولی و Constructor Function چیست؟
* Convention نام‌گذاری Constructor Function چیست؟
* نقش `new` چیست؟

مثال:

```javascript
function Person(name) {
  this.name = name;
}

const ali = new Person("Ali");
```

توضیح بده:

* `this` به چه Objectای اشاره می‌کند؟
* `new Person()` چه چیزی برمی‌گرداند؟
* Prototype این Object چیست؟

---

## 6.2 افزودن متد به Prototype

مثال:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function () {
  console.log(`Hello, I am ${this.name}`);
};

const ali = new Person("Ali");
const sara = new Person("Sara");

ali.sayHello();
sara.sayHello();
```

توضیح بده:

* چرا متد داخل Constructor تعریف نشده؟
* چرا متد روی Prototype قرار گرفته؟
* چرا همه Instanceها می‌توانند از آن استفاده کنند؟
* آیا هر Instance یک کپی مستقل از Function دارد؟

---

## 6.3 Constructor Property

توضیح بده:

* `constructor` چیست؟
* چرا `Person.prototype.constructor` به `Person` اشاره می‌کند؟
* آیا `constructor` یک Property معمولی است؟
* چرا هنگام بازنویسی Prototype ممکن است مقدار آن تغییر کند؟

مثال:

```javascript
function Person() {}

console.log(Person.prototype.constructor === Person);
```

---

# بخش هفتم: عملگر `new`

## 7.1 `new` چگونه کار می‌کند؟

توضیح بده که به‌صورت مفهومی، هنگام اجرای:

```javascript
const person = new Person("Ali");
```

مراحل زیر رخ می‌دهد:

1. یک Object جدید ساخته می‌شود.
2. Prototype آن به `Person.prototype` متصل می‌شود.
3. Constructor Function با `this` جدید اجرا می‌شود.
4. اگر Constructor یک Object معتبر برنگرداند، Object ساخته‌شده برگردانده می‌شود.

این مراحل را با مثال توضیح بده.

---

## 7.2 شبیه‌سازی ساده `new`

یک شبیه‌سازی آموزشی ساده ارائه بده و تأکید کن که این پیاده‌سازی کامل Specification نیست.

مثال:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function () {
  console.log(`Hello, ${this.name}`);
};

function createPerson(name) {
  const person = Object.create(Person.prototype);

  Person.call(person, name);

  return person;
}
```

توضیح بده:

* چرا `Object.create()` استفاده شده؟
* چرا `Person.call()` استفاده شده؟
* چه تفاوتی با `new Person()` دارد؟
* چه رفتارهایی در این شبیه‌سازی پوشش داده نشده‌اند؟

---

## 7.3 رفتار `new` با Return

توضیح بده:

* اگر Constructor یک Object برگرداند چه اتفاقی می‌افتد؟
* اگر یک Primitive برگرداند چه اتفاقی می‌افتد؟
* چرا این موضوع مهم است؟

مثال‌های ساده ارائه بده.

---

# بخش هشتم: Object.create()

## 8.1 `Object.create()` چیست؟

توضیح بده:

* `Object.create()` چیست؟
* چگونه یک Object جدید با Prototype مشخص می‌سازد؟
* تفاوت آن با `new` چیست؟
* چه زمانی استفاده از آن مناسب است؟

مثال:

```javascript
const personPrototype = {
  greet() {
    console.log(`Hello, ${this.name}`);
  }
};

const person = Object.create(personPrototype);

person.name = "Ali";
person.greet();
```

---

## 8.2 `Object.create(null)`

توضیح بده:

* چگونه Object بدون Prototype بسازیم؟
* چرا `Object.create(null)` مهم است؟
* چه تفاوتی با `{}` دارد؟
* چرا متدهایی مانند `toString()` یا `hasOwnProperty()` در آن وجود ندارند؟

مثال:

```javascript
const dictionary = Object.create(null);

dictionary.name = "Ali";

console.log(dictionary.name);
console.log(dictionary.toString);
```

---

## 8.3 پارامتر دوم `Object.create()`

توضیح بده:

* Property Descriptor چیست؟
* `writable`
* `enumerable`
* `configurable`
* `value`
* `get`
* `set`

مثال:

```javascript
const person = Object.create(Object.prototype, {
  name: {
    value: "Ali",
    writable: true,
    enumerable: true,
    configurable: true
  }
});
```

توضیح بده این گزینه‌ها چه تأثیری دارند.

---

# بخش نهم: مشاهده و تغییر Prototype

## 9.1 `Object.getPrototypeOf()`

توضیح بده:

* کاربرد آن چیست؟
* چگونه Prototype واقعی یک Object را مشاهده کنیم؟
* تفاوت آن با بررسی `prototype` یک Function چیست؟

مثال:

```javascript
const parent = {};
const child = Object.create(parent);

console.log(Object.getPrototypeOf(child) === parent);
```

---

## 9.2 `Object.setPrototypeOf()`

توضیح بده:

* کاربرد آن چیست؟
* چگونه Prototype یک Object را تغییر می‌دهد؟
* چرا تغییر Prototype در Runtime می‌تواند هزینه عملکردی داشته باشد؟
* چرا بهتر است Prototype در زمان ساخت Object تعیین شود؟

مثال:

```javascript
const parent = {
  greet() {
    console.log("Hello");
  }
};

const child = {};

Object.setPrototypeOf(child, parent);

child.greet();
```

---

## 9.3 `__proto__`

توضیح بده:

* `__proto__` چیست؟
* چرا با `prototype` متفاوت است؟
* چرا استفاده از آن در کد جدید توصیه نمی‌شود؟
* جایگزین استاندارد آن چیست؟

مثال مقایسه‌ای ارائه بده.

---

# بخش دهم: Inheritance با Prototype

## 10.1 Inheritance چیست؟

توضیح بده:

* Inheritance چیست؟
* چگونه JavaScript با Prototype آن را پیاده‌سازی می‌کند؟
* رابطه `is-a` چیست؟
* تفاوت Inheritance در JavaScript با زبان‌های Class-based چیست؟

---

## 10.2 Inheritance با Constructor Function

مثال:

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.eat = function () {
  console.log(`${this.name} is eating.`);
};

function Dog(name) {
  Animal.call(this, name);
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function () {
  console.log("Bark");
};
```

توضیح بده:

* چرا `Animal.call(this, name)` استفاده شده؟
* چرا `Dog.prototype = Object.create(Animal.prototype)` استفاده شده؟
* چرا باید `constructor` را دوباره تنظیم کنیم؟
* زنجیره Prototype چگونه شکل گرفته است؟

---

## 10.3 Inheritance با Class

مثال:

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  eat() {
    console.log(`${this.name} is eating.`);
  }
}

class Dog extends Animal {
  bark() {
    console.log("Bark");
  }
}
```

توضیح بده:

* `extends` چه کاری انجام می‌دهد؟
* Prototype Chain چگونه شکل می‌گیرد؟
* ارتباط `Dog.prototype` و `Animal.prototype` چیست؟
* چرا Class Syntax Prototype را حذف نکرده است؟

---

# بخش یازدهم: Class و Prototype

## 11.1 Class چگونه با Prototype کار می‌کند؟

توضیح بده:

* متدهای Instance در Class کجا قرار می‌گیرند؟
* چرا متدهای Class معمولاً روی Prototype قرار می‌گیرند؟
* چرا هر Instance متد مستقل ندارد؟
* چگونه Class Syntax به Prototype متصل می‌شود؟

مثال:

```javascript
class Person {
  sayHello() {
    console.log("Hello");
  }
}

const ali = new Person();
const sara = new Person();

console.log(Object.getPrototypeOf(ali) === Person.prototype);
console.log(ali.sayHello === sara.sayHello);
```

---

## 11.2 تفاوت Class و Constructor Function

یک مقایسه ساده ارائه بده.

موارد مقایسه:

* Syntax
* Prototype
* Constructor
* Inheritance
* Strict Mode
* Hoisting
* Private Fields
* خوانایی
* کاربرد در پروژه‌های مدرن

تأکید کن که Class و Constructor Function هر دو با Prototype کار می‌کنند، اما Syntax و برخی رفتارهای آن‌ها متفاوت است.

---

# بخش دوازدهم: Property Lookup و Shadowing

## 12.1 الگوریتم ساده Property Lookup

توضیح بده:

* JavaScript چگونه یک Property را پیدا می‌کند؟
* چرا Own Property اولویت دارد؟
* اگر Property پیدا نشود چه می‌شود؟
* چرا `undefined` همیشه به معنی «Property وجود ندارد» نیست؟

مثال:

```javascript
const parent = {
  value: 10
};

const child = Object.create(parent);

console.log(child.value);

child.value = undefined;

console.log(child.value);
console.log(Object.hasOwn(child, "value"));
```

---

## 12.2 Shadowing و Method Overriding

توضیح بده:

* Shadowing چیست؟
* چگونه یک Method در Object فرزند می‌تواند Method Prototype را پنهان کند؟
* ارتباط آن با Override چیست؟

مثال:

```javascript
const parent = {
  greet() {
    console.log("Parent");
  }
};

const child = Object.create(parent);

child.greet = function () {
  console.log("Child");
};

child.greet();
```

---

# بخش سیزدهم: مباحث پیشرفته

این بخش را به‌صورت تدریجی و قابل‌فهم معرفی کن.

## 13.1 Prototype Descriptors

توضیح بده:

* Property Descriptor
* Data Property
* Accessor Property
* `Object.getOwnPropertyDescriptor()`
* `Object.defineProperty()`
* تأثیر Descriptorها بر Prototype

---

## 13.2 `Object.prototype`

توضیح بده:

* `Object.prototype` چیست؟
* چه متدهایی دارد؟
* چرا بسیاری از Objectها از آن استفاده می‌کنند؟
* چرا نباید بی‌دلیل Prototypeهای Built-in را تغییر دهیم؟

---

## 13.3 Built-in Prototypes

توضیح بده:

* `Array.prototype`
* `String.prototype`
* `Number.prototype`
* `Function.prototype`
* `Date.prototype`

مثال:

```javascript
const numbers = [1, 2, 3];

console.log(Object.getPrototypeOf(numbers) === Array.prototype);
```

---

## 13.4 Prototype Pollution

توضیح بده:

* Prototype Pollution چیست؟
* چرا یک مسئله امنیتی است؟
* چگونه تغییر ناخواسته Prototype می‌تواند روی Objectهای دیگر اثر بگذارد؟
* چه الگوهایی خطرناک هستند؟
* چگونه از آن جلوگیری کنیم؟
* چرا استفاده از `Object.create(null)` در برخی سناریوها مفید است؟

مثال آموزشی بی‌خطر ارائه بده و از ارائه دستورالعمل سوءاستفاده واقعی خودداری کن.

---

## 13.5 Performance و Prototype

توضیح بده:

* چرا اشتراک متدها روی Prototype مفید است؟
* چرا تغییر Prototype در Runtime می‌تواند عملکرد را تحت تأثیر قرار دهد؟
* Hidden Classes و Shapes را فقط در حد مفهومی معرفی کن.
* چرا نباید بدون اندازه‌گیری درباره Performance نتیجه‌گیری قطعی کرد؟
* چرا طولانی‌بودن Prototype Chain می‌تواند بر Property Lookup اثر بگذارد؟

---

## 13.6 Mixins

توضیح بده:

* Mixin چیست؟
* چگونه می‌توان رفتار مشترک را بدون Inheritance عمیق ترکیب کرد؟
* تفاوت Mixin و Prototype Inheritance چیست؟
* مزایا و محدودیت‌ها

مثال:

```javascript
const canWalk = {
  walk() {
    console.log("Walking");
  }
};

const canRun = {
  run() {
    console.log("Running");
  }
};

const person = Object.assign({}, canWalk, canRun);
```

---

## 13.7 Prototype و `this`

توضیح بده:

* چرا متد Prototype می‌تواند به داده‌های Instance دسترسی داشته باشد؟
* نقش `this` چیست؟
* تفاوت Method Call و جداکردن Function از Object چیست؟

مثال:

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function () {
  console.log(this.name);
};

const person = new Person("Ali");

person.sayHello();

const greet = person.sayHello;
```

توضیح بده چرا اجرای `greet()` می‌تواند رفتار متفاوتی داشته باشد.

---

# بخش چهاردهم: اشتباهات رایج

موارد زیر را با مثال توضیح بده:

* اشتباه گرفتن `prototype` با `[[Prototype]]`
* تصور اینکه Prototype یک Class است
* تصور اینکه Prototype باعث کپی‌شدن Object می‌شود
* استفاده بی‌دلیل از `__proto__`
* تغییر Prototype در Runtime بدون دلیل
* بازنویسی Prototype بدون تنظیم `constructor`
* قرار دادن داده‌های Instance روی Prototype
* قرار دادن متدهای مشترک داخل Constructor
* استفاده نادرست از `instanceof`
* تغییر Prototypeهای Built-in
* ایجاد Prototype Chain بسیار عمیق
* استفاده از Inheritance فقط برای Reuse کد
* نادیده‌گرفتن `Object.create(null)`
* تصور اینکه `Object.freeze()` Prototype را کاملاً ایمن می‌کند

برای هر مورد:

* مشکل چیست؟
* چرا بد است؟
* مثال ساده
* راهکار بهتر

---

# بخش پانزدهم: تمرین‌ها

برای هر موضوع حداقل ۳ تمرین طراحی کن.

## تمرین‌های مقدماتی

* ساخت Object با `Object.create()`
* بررسی Prototype یک Object
* تشخیص Own Property و Inherited Property
* ساخت یک Prototype Chain ساده

## تمرین‌های Constructor Function

* ساخت `Person`
* افزودن Method به Prototype
* ساخت چند Instance
* بررسی اشتراک متدها

## تمرین‌های Inheritance

* ساخت `Animal` و `Dog`
* ساخت `Vehicle` و `Car`
* پیاده‌سازی Inheritance با Constructor Function
* پیاده‌سازی همان مثال با Class

## تمرین‌های پیشرفته

* ساخت Object با `Object.create(null)`
* کار با Property Descriptor
* پیاده‌سازی یک Mixin
* بررسی Shadowing
* بررسی رفتار `instanceof`
* تحلیل Prototype Chain یک Object Built-in

برای هر تمرین:

* صورت مسئله
* مفاهیم مورد استفاده
* سطح دشواری
* نکته یا راهنمایی کوتاه

در صورت نیاز، پاسخ تمرین‌ها را در بخش جداگانه قرار بده؛ اما ابتدا اجازه بده خواننده خودش تلاش کند.

---

# بخش شانزدهم: جمع‌بندی

در پایان:

* Prototype را در چند جمله خلاصه کن.
* تفاوت `prototype` و `[[Prototype]]` را یادآوری کن.
* Prototype Chain را توضیح بده.
* نقش Constructor Function و `new` را جمع‌بندی کن.
* نقش `Object.create()` را توضیح بده.
* ارتباط Class و Prototype را یادآوری کن.
* تفاوت Inheritance و Composition را بیان کن.
* مهم‌ترین نکات امنیتی و عملکردی را ذکر کن.
* یک مسیر پیشنهادی برای ادامه یادگیری JavaScript ارائه بده.

---

# بخش هفدهم: منابع

در پایان، منابع معتبر و رسمی را معرفی کن.

منابع اصلی پیشنهادی:

1. **MDN — Inheritance and the Prototype Chain**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain

2. **MDN — Object Prototypes**

   * https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Advanced_JavaScript_objects/Object_prototypes

3. **MDN — Object.create()**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create

4. **MDN — Object.getPrototypeOf()**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf

5. **MDN — Object.setPrototypeOf()**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf

6. **MDN — `__proto__`**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/proto

7. **MDN — Classes**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes

8. **MDN — Using Classes**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_classes

9. **MDN — `instanceof`**

   * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof

10. **MDN — Object.prototype**

    * https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object

11. **JavaScript.info — Prototypes**

    * https://javascript.info/prototypes

12. **JavaScript.info — Prototype Methods**

    * https://javascript.info/prototype-methods

13. **JavaScript.info — Class Inheritance**

    * https://javascript.info/class-inheritance

14. **ECMAScript Language Specification**

    * https://tc39.es/ecma262/

15. **OWASP — Prototype Pollution Prevention Cheat Sheet**

    * https://cheatsheetseries.owasp.org/cheatsheets/Prototype_Pollution_Prevention_Cheat_Sheet.html

**قوانین منابع:**

* از منابع رسمی و معتبر استفاده کن.
* منابع اصلی را ترجیحاً از MDN و ECMAScript انتخاب کن.
* برای توضیحات آموزشی تکمیلی می‌توانی از JavaScript.info استفاده کنی.
* برای مباحث امنیتی از منابع معتبر مانند OWASP استفاده کن.
* اگر مطلبی از منبعی برداشت می‌کنی، آن را با زبان خودت توضیح بده و کپی طولانی نکن.
* لینک منابع را بررسی کن و از لینک‌های معتبر استفاده کن.
* در پایان مشخص کن هر منبع برای کدام بخش استفاده شده است.
* اگر یک قابلیت JavaScript به نسخه خاصی وابسته است، نسخه یا وضعیت پشتیبانی آن را بررسی کن.
* از منابع نامعتبر، وبلاگ‌های بدون اعتبار و مطالب بدون تاریخ یا نویسنده مشخص استفاده نکن؛ مگر اینکه صرفاً برای مثال آموزشی باشد.

---

# فرمت نهایی خروجی

خروجی را به‌صورت یک فایل Markdown کامل ارائه بده.

ویژگی‌های خروجی:

* دارای لینک‌دهی معتبر
* دارای Headingهای منظم
* دارای مثال‌های JavaScript
* دارای توضیح خط‌به‌خط کدهای مهم
* دارای مثال واقعی
* دارای مقایسه‌های ضروری
* دارای تمرین
* دارای جمع‌بندی
* دارای منابع معتبر در پایان
* مناسب برای مبتدی
* قابل‌استفاده در GitHub
* بدون پیچیده‌گویی غیرضروری

**مهم:** مطالب را از مقدماتی شروع کن و به‌صورت تدریجی به مباحث پیشرفته برس. هیچ مفهوم مهمی را بدون توضیح قبلی معرفی نکن.


# Prototype در JavaScript

این راهنما برای درک عمیق و کاربردی مفهوم **Prototype** در جاوااسکریپت طراحی شده است. هدف ما این است که شما فقط سینتکس را حفظ نکنید، بلکه دقیقاً بدانید موتور جاوااسکریپت چگونه از Prototype برای اشتراک رفتار، جست‌وجوی Property و ایجاد زنجیره وراثت استفاده می‌کند.

برای بهره‌برداری حداکثری از این مطلب، آشنایی مقدماتی با موارد زیر توصیه می‌شود:
- مبانی جاوااسکریپت (Variables, Functions)
- کار با Objectها و آرایه‌ها
- مفهوم کلیدواژه `this`
- Scope (حوزه دسترسی)
- آشنایی اولیه با عملگر `new`

---

- [1. مقدمه‌ای بر Prototype](#1-مقدمه‌ای-بر-prototype)
- [2. Object و Property](#2-object-و-property)
- [3. Prototype چیست؟](#3-prototype-چیست)
- [4. Prototype Chain](#4-prototype-chain)
- [5. تفاوت `prototype` و `[[Prototype]]`](#5-تفاوت-prototype-و-prototype)
- [6. Constructor Function](#6-constructor-function)
- [7. عملگر `new`](#7-عملگر-new)
- [8. متد `Object.create()`](#8-متد-objectcreate)
- [9. مشاهده و تغییر Prototype](#9-مشاهده-و-تغییر-prototype)
- [10. وراثت (Inheritance) با Prototype](#10-وراثت-inheritance-با-prototype)
- [11. کلاس (Class) و Prototype](#11-کلاس-class-و-prototype)
- [12. جست‌وجوی Property و Shadowing](#12-جست‌وجوی-property-و-shadowing)
- [13. مباحث پیشرفته](#13-مباحث-پیشرفته)
- [14. اشتباهات رایج](#14-اشتباهات-رایج)
- [15. تمرین‌ها](#15-تمرین‌ها)
- [16. جمع‌بندی](#16-جمع‌بندی)
- [17. منابع](#17-منابع)

---

## 1. مقدمه‌ای بر Prototype

### 1.1 Prototype چیست؟
به زبان ساده، **Prototype** یک مکانیزم در جاوااسکریپت است که به Objectها اجازه می‌دهد ویژگی‌ها (Properties) و رفتارها (Methods) را از یک Object دیگر به ارث ببرند. 

جاوااسکریپت یک زبان **Prototype-based** است. برخلاف زبان‌های Class-based (مثل Java یا C#) که در آن‌ها کلاس‌ها نقش نقشه‌ی ساخت را دارند، در جاوااسکریپت خودِ Objectها نقش اصلی را ایفا می‌کنند و می‌توانند مستقیماً به یکدیگر متصل شوند.

**Prototype چه مشکلی را حل می‌کند؟**
فرض کنید 1000 شیء `User` دارید. اگر متد `sayHello()` را داخل هر شیء تعریف کنید، 1000 کپی مستقل از یک تابع یکسان در حافظه خواهید داشت. Prototype این مشکل را با **اشتراک‌گذاری** یک نسخه واحد از متد بین تمام Objectها حل می‌کند.

**مثال واقعی:**
تصور کنید چندین خودرو داریم. همه آن‌ها رفتار `startEngine()` را به اشتراک می‌گذارند. به جای ساخت این متد برای هر خودرو، آن را در یک "الگوی مشترک" (Prototype) قرار می‌دهیم.

```javascript
// الگوی مشترک (Prototype)
const personPrototype = {
  sayHello() {
    console.log(`Hello, I am ${this.name}`);
  }
};

// ساخت یک Object جدید که به personPrototype متصل است
const person = Object.create(personPrototype);
person.name = "Ali";

person.sayHello(); // خروجی: Hello, I am Ali
```
**توضیح:**
- `personPrototype`: یک Object معمولی است که متد `sayHello` را نگه می‌دارد.
- `person`: یک Object جدید است که خودش متد `sayHello` را ندارد، اما چون به `personPrototype` متصل است، می‌تواند آن را اجرا کند.

### 1.2 Prototype چه چیزی نیست؟
- **Prototype یک Class نیست:** کلاس فقط یک "Syntax Sugar" (شیرینی سینتکسی) روی همان مکانیزم Prototype است.
- **Prototype باعث کپی‌شدن Object نمی‌شود:** ارتباط از طریق ارجاع (Reference) است، نه کپی.
- **Property به نام `prototype` با خودِ مفهوم Prototype یکی نیست:** این یکی از بزرگترین منابع سردرگمی است که در بخش 5 به تفصیل بررسی می‌شود.

---

## 2. Object و Property

### 2.1 Object چیست؟
در جاوااسکریپت، Object مجموعه‌ای از جفت‌های Key-Value است. هر Property می‌تواند یک مقدار اولیه (Primitive) یا یک Function (که به آن Method می‌گوییم) باشد.

```javascript
const person = {
  name: "Ali", // Own Property
  sayHello() { // Method
    console.log(`Hello, ${this.name}`);
  }
};
```
- **Own Property (ویژگی اختصاصی):** Propertyای که مستقیماً روی خود Object تعریف شده است (مثل `name`).
- **Inherited Property (ویژگی به ارث رسیده):** Propertyای که روی خود Object نیست، اما از طریق زنجیره Prototype در دسترس است.

### 2.2 بررسی Own Property و Inherited Property
برای تشخیص اینکه یک Property متعلق به خود Object است یا به ارث رسیده، از `Object.hasOwn()` (یا در نسخه‌های قدیمی‌تر `Object.prototype.hasOwnProperty`) استفاده می‌کنیم.

```javascript
const parent = { role: "admin" };
const child = Object.create(parent);

child.name = "Ali";

console.log(child.name); // "Ali"
console.log(child.role); // "admin" (به ارث رسیده)

console.log(Object.hasOwn(child, "name")); // true (اختصاصی)
console.log(Object.hasOwn(child, "role")); // false (به ارث رسیده)
```

---

## 3. Prototype چیست؟

### 3.1 تعریف دقیق
هر Object در جاوااسکریپت (به جز استثناها که در بخش 8 می‌خوانید) یک لینک داخلی به یک Object دیگر دارد که به آن **Prototype** می‌گویند. آن Objectِ Prototype هم می‌تواند Prototype خودش را داشته باشد و این روند ادامه می‌یابد تا زمانی که به `null` برسد.

```text
child Object
   ↓ (لینک داخلی)
parent Object (Prototype)
   ↓
Object.prototype (بالاترین سطح استاندارد)
   ↓
null (پایان زنجیره)
```

### 3.2 چرا Prototype مهم است؟
1. **اشتراک رفتار و کاهش مصرف حافظه:** متدها یک بار تعریف می‌شوند و هزاران Instance از آن‌ها استفاده می‌کنند.
2. **Property Lookup:** موتور جاوااسکریپت برای پیدا کردن یک ویژگی، این زنجیره را طی می‌کند.
3. **پایه و اساس وراثت:** تمام مکانیزم‌های Inheritance در جاوااسکریپت (حتی `class` و `extends`) بر همین اساس کار می‌کنند.

---

## 4. Prototype Chain

### 4.1 Prototype Chain چیست؟
به زنجیره‌ای از Objectها که از طریق لینک‌های Prototype به هم متصل شده‌اند، **Prototype Chain** می‌گویند.

```javascript
const grandParent = { familyName: "Shabani" };
const parent = Object.create(grandParent);
parent.parentName = "Reza";

const child = Object.create(parent);
child.name = "Ali";
```
نمودار زنجیره برای `child`:
```text
child (name: "Ali")
  ↓
parent (parentName: "Reza")
  ↓
grandParent (familyName: "Shabani")
  ↓
Object.prototype (متدهای پیش‌فرض مثل toString)
  ↓
null
```

### 4.2 Property Lookup (جست‌وجوی ویژگی)
وقتی می‌نویسیم `child.familyName`، موتور جاوااسکریپت این مراحل را طی می‌کند:
1. آیا `familyName` یک Own Property در `child` است؟ خیر.
2. به Prototype آن (`parent`) می‌رود. آیا آنجا هست؟ خیر.
3. به Prototype بعدی (`grandParent`) می‌رود. آیا آنجا هست؟ بله! مقدار `"Shabani"` را برمی‌گرداند.
4. اگر در کل زنجیره تا `null` پیدا نشود، مقدار `undefined` برگردانده می‌شود.

### 4.3 Shadowing (سایه‌اندازی)
اگر یک Property با نام یکسان را روی Object فرزند تعریف کنیم، آن Property، Property ارث‌رسیده را "پنهان" (Shadow) می‌کند، زیرا جست‌وجو همیشه از پایین‌ترین سطح (خود Object) شروع می‌شود.

```javascript
const parent = { role: "admin" };
const child = Object.create(parent);

console.log(child.role); // "admin" (از parent خوانده شد)

child.role = "user"; // یک Own Property جدید روی child ساخته می‌شود

console.log(child.role); // "user" (Own Property اولویت دارد)
console.log(parent.role); // "admin" (parent دست‌نخورده باقی مانده است)
```

### 4.4 تغییر Prototype در Runtime
اگر Prototype را پس از ساخت Objectها تغییر دهید، این تغییر بلافاصله روی تمام Objectهایی که به آن متصل هستند تأثیر می‌گذارد. اگرچه این کار ممکن است، اما به دلایل عملکردی (Performance) به‌شدت غیرتوصیه می‌شود.

---

## 5. تفاوت `prototype` و `[[Prototype]]`

این بخش مهم‌ترین قسمت برای رفع سردرگمی است.

### 5.1 `[[Prototype]]` چیست؟
`[[Prototype]]` یک **Internal Slot** (شکاف داخلی) در Specification جاوااسکریپت است. این یک لینک پنهان است که هر Object به Prototype خود دارد. شما نمی‌توانید مستقیماً به `[[Prototype]]` دسترسی داشته باشید، اما می‌توانید از متد استاندارد `Object.getPrototypeOf()` برای خواندن آن استفاده کنید.

### 5.2 `prototype` چیست؟
`prototype` یک **Property معمولی** است که *فقط* روی Functionها (به‌ویژه Constructor Functionها) وجود دارد. این Property مشخص می‌کند که اگر آن Function با کلیدواژه `new` فراخوانی شود، `[[Prototype]]` Object ساخته‌شده، به چه چیزی اشاره خواهد کرد.
*(نکته: Arrow Functionها Property به نام `prototype` ندارند).*

### 5.3 جدول مقایسه

| مفهوم | توضیح | نحوه دسترسی/استفاده |
| :--- | :--- | :--- |
| `[[Prototype]]` | لینک داخلی یک Object به Prototype خودش. | `Object.getPrototypeOf(obj)` |
| `prototype` | یک Property روی Functionها که الگوی ساخت Instanceهای جدید را تعیین می‌کند. | `MyFunction.prototype` |
| `__proto__` | یک Accessor قدیمی و منسوخ شده که نباید در کد جدید استفاده شود. | `obj.__proto__` (اجتناب کنید) |

**مثال روشن‌کننده:**
```javascript
function Person(name) {
  this.name = name;
}

// Person یک Function است، پس Propertyای به نام prototype دارد
console.log(Person.prototype); // { constructor: ƒ }

const ali = new Person("Ali");

// ali یک Object است، پس [[Prototype]] دارد
console.log(Object.getPrototypeOf(ali) === Person.prototype); // true
```

---

## 6. Constructor Function

### 6.1 Constructor Function چیست؟
قبل از معرفی `class` در ES6، از Functionهای معمولی به عنوان سازنده استفاده می‌شد. طبق قرارداد (Convention)، نام این Functionها با حرف بزرگ (PascalCase) شروع می‌شود تا مشخص شود باید با `new` فراخوانی شوند.

```javascript
function Person(name) {
  this.name = name;
}

const ali = new Person("Ali");
```
در اینجا، `this` به Object جدیدی اشاره می‌کند که توسط `new` ساخته شده است.

### 6.2 افزودن متد به Prototype
برای جلوگیری از ساخت کپی‌های متعدد از متدها، آن‌ها را به `prototype` تابع سازنده اضافه می‌کنیم:

```javascript
function Person(name) {
  this.name = name;
}

// متد فقط یک بار در حافظه تعریف می‌شود
Person.prototype.sayHello = function () {
  console.log(`Hello, I am ${this.name}`);
};

const ali = new Person("Ali");
const sara = new Person("Sara");

ali.sayHello(); // Hello, I am Ali
sara.sayHello(); // Hello, I am Sara

console.log(ali.sayHello === sara.sayHello); // true (اشاره به یک تابع واحد در حافظه)
```

### 6.3 Property به نام `constructor`
به‌طور پیش‌فرض، هر `prototype` یک Property به نام `constructor` دارد که به خود Function سازنده اشاره می‌کند.
```javascript
console.log(Person.prototype.constructor === Person); // true
console.log(ali.constructor === Person); // true (از طریق زنجیره Prototype)
```
*هشدار:* اگر کل `prototype` را با یک Object جدید بازنویسی کنیم، این ارتباط از بین می‌رود و باید دستی آن را ترمیم کنیم (در بخش 10 توضیح داده شده است).

---

## 7. عملگر `new`

### 7.1 `new` چگونه کار می‌کند؟
وقتی `new Person("Ali")` را اجرا می‌کنید، موتور جاوااسکریپت به‌صورت مفهومی این 4 مرحله را انجام می‌دهد:
1. یک Object خالی جدید می‌سازد (`{}`).
2. `[[Prototype]]` این Object جدید را به `Person.prototype` متصل می‌کند.
3. Function `Person` را اجرا می‌کند و `this` را به Object جدید bind می‌کند (مقادیر اولیه تنظیم می‌شوند).
4. اگر Function یک Object معتبر برنگرداند، خود Object جدید را برمی‌گرداند.

### 7.2 شبیه‌سازی ساده `new`
برای درک بهتر، می‌توانیم رفتار `new` را شبیه‌سازی کنیم (توجه: این یک شبیه‌سازی آموزشی است و تمام جزئیات Specification را پوشش نمی‌دهد):

```javascript
function myNew(constructorFn, ...args) {
  // 1 & 2: ساخت Object و اتصال Prototype
  const newInstance = Object.create(constructorFn.prototype);
  
  // 3: اجرای Constructor با this جدید
  const result = constructorFn.apply(newInstance, args);
  
  // 4: بررسی مقدار بازگشتی
  return (result !== null && typeof result === 'object') ? result : newInstance;
}

function Person(name) { this.name = name; }
Person.prototype.greet = () => console.log("Hi");

const p = myNew(Person, "Ali");
console.log(p.name); // "Ali"
p.greet(); // "Hi"
```

### 7.3 رفتار `new` با Return
اگر Constructor یک Object (مثل `{}` یا `[]`) را `return` کند، آن Object جایگزین Instance ساخته‌شده می‌شود. اگر یک مقدار Primitive (مثل رشته یا عدد) return شود، نادیده گرفته می‌شود و Instance اصلی برگردانده می‌شود.

---

## 8. متد `Object.create()`

### 8.1 `Object.create()` چیست؟
این متد خالص‌ترین راه برای ساخت یک Object با Prototype مشخص است. برخلاف `new`، نیازی به Constructor Function ندارد.

```javascript
const animalProto = {
  eat() { console.log("Eating..."); }
};

const dog = Object.create(animalProto);
dog.bark = () => console.log("Woof!");

dog.eat(); // Eating... (از Prototype)
dog.bark(); // Woof! (Own Property)
```

### 8.2 `Object.create(null)`
این یک الگوی بسیار مهم است. این کد یک Object کاملاً خالی می‌سازد که **هیچ Prototypeای ندارد** (حتی به `Object.prototype` متصل نیست).
- **کاربرد:** ساخت دیکشنری‌ها یا Mapهای امن.
- **تفاوت با `{}`:** در `{}`، متدهایی مثل `toString` یا `hasOwnProperty` وجود دارند که ممکن است با کلیدهای داده‌های شما تداخل کنند. در `Object.create(null)` این خطر وجود ندارد.

```javascript
const dict = Object.create(null);
dict["toString"] = "This is just a data key, not a method!";
console.log(dict.toString); // "This is just a data key, not a method!"
// console.log(dict.hasOwnProperty("test")); // خطا! این متد وجود ندارد.
```

### 8.3 پارامتر دوم `Object.create()`
می‌توانید Property Descriptorها را هم هنگام ساخت تعریف کنید (مشابه `Object.defineProperties`):
```javascript
const user = Object.create(null, {
  name: {
    value: "Ali",
    writable: true,
    enumerable: true,
    configurable: true
  }
});
```

---

## 9. مشاهده و تغییر Prototype

### 9.1 `Object.getPrototypeOf()`
روش استاندارد و توصیه‌شده برای خواندن `[[Prototype]]` یک Object.
```javascript
const arr = [1, 2, 3];
console.log(Object.getPrototypeOf(arr) === Array.prototype); // true
```

### 9.2 `Object.setPrototypeOf()`
این متد اجازه می‌دهد `[[Prototype]]` یک Object موجود را تغییر دهید.
**هشدار عملکردی:** تغییر Prototype یک Object پس از ساخت، باعث می‌شود موتورهای جاوااسکریپت (مثل V8) بهینه‌سازی‌های پنهان (Hidden Classes / Shapes) را دور بریزند و کد به‌شدت کند شود. همیشه ترجیح دهید Prototype را در زمان ساخت (با `Object.create` یا `new`) تعیین کنید.

### 9.3 `__proto__`
این یک Property دسترسی‌دهنده (Accessor) قدیمی است که در گذشته برای خواندن و نوشتن Prototype استفاده می‌شد. اگرچه در مرورگرها پشتیبانی می‌شود، اما در Specification به عنوان "منسوخ شده" (Deprecated) علامت‌گذاری شده است. **هرگز در کد جدید از آن استفاده نکنید.** به جای آن از `Object.getPrototypeOf()` و `Object.setPrototypeOf()` استفاده کنید.

---

## 10. وراثت (Inheritance) با Prototype

### 10.1 وراثت با Constructor Function
برای شبیه‌سازی `is-a` قبل از ES6، باید زنجیره Prototype را دستی بسازیم:

```javascript
// کلاس والد
function Animal(name) {
  this.name = name;
}
Animal.prototype.eat = function () {
  console.log(`${this.name} is eating.`);
};

// کلاس فرزند
function Dog(name, breed) {
  // 1. فراخوانی Constructor والد برای تنظیم Own Properties
  Animal.call(this, name);
  this.breed = breed;
}

// 2. اتصال Prototype فرزند به یک Object جدید که Prototype آن، والد است
Dog.prototype = Object.create(Animal.prototype);

// 3. ترمیم Property constructor (چون در مرحله قبل بازنویسی شد)
Dog.prototype.constructor = Dog;

// 4. افزودن متدهای اختصاصی فرزند
Dog.prototype.bark = function () {
  console.log("Woof!");
};

const myDog = new Dog("Rex", "German Shepherd");
myDog.eat(); // Rex is eating. (از Animal.prototype)
myDog.bark(); // Woof! (از Dog.prototype)
```

### 10.2 وراثت با Class (ES6)
کلمه کلیدی `class` و `extends` دقیقاً همان کار بالا را انجام می‌دهند، اما با سینتکسی خوانا و ایمن‌تر. زیر کاپوت، هنوز هم از Prototype استفاده می‌شود.

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }
  eat() {
    console.log(`${this.name} is eating.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // معادل Animal.call(this, name)
    this.breed = breed;
  }
  bark() {
    console.log("Woof!");
  }
}
```

---

## 11. کلاس (Class) و Prototype

### 11.1 Class چگونه با Prototype کار می‌کند؟
وقتی یک متد را داخل بدنه `class` تعریف می‌کنید، جاوااسکریپت آن را به‌طور خودکار روی `ClassName.prototype` قرار می‌دهد. این یعنی تمام Instanceها یک متد مشترک را به اشتراک می‌گذارند و حافظه هدر نمی‌رود.

```javascript
class Person {
  sayHello() { // این متد روی Person.prototype قرار می‌گیرد
    console.log("Hello");
  }
}

const p1 = new Person();
const p2 = new Person();

console.log(Object.getPrototypeOf(p1) === Person.prototype); // true
console.log(p1.sayHello === p2.sayHello); // true
```

### 11.2 تفاوت Class و Constructor Function
| ویژگی | Constructor Function | Class (ES6) |
| :--- | :--- | :--- |
| **سینتکس** | شبیه Function معمولی | ساختار بلوکی و خواناتر |
| **Hoisting** | دارد (می‌توان قبل از تعریف فراخوانی کرد) | ندارد (باید بعد از تعریف فراخوانی شود - Temporal Dead Zone) |
| **Strict Mode** | اختیاری | به‌صورت پیش‌فرض فعال است |
| **فراخوانی بدون `new`** | ممکن است (باعث آلودگی Global می‌شود) | خطا می‌دهد (ایمن‌تر) |
| **Private Fields** | نیاز به Closure یا WeakMap دارد | با `#` پشتیبانی می‌شود (مثال: `#name`) |

---

## 12. جست‌وجوی Property و Shadowing

### 12.1 الگوریتم ساده Property Lookup
1. بررسی Own Property.
2. اگر نبود، حرکت به `[[Prototype]]`.
3. تکرار تا پیدا شدن Property یا رسیدن به `null`.
4. اگر نرسید، `undefined`.

**نکته مهم:** مقدار `undefined` همیشه به معنی "وجود نداشتن Property" نیست. ممکن است Property وجود داشته باشد اما مقدار آن عمداً `undefined` تنظیم شده باشد. برای بررسی قطعی وجود، از `Object.hasOwn()` یا عملگر `in` استفاده کنید.

```javascript
const parent = { value: 10 };
const child = Object.create(parent);

child.value = undefined;

console.log(child.value); // undefined
console.log("value" in child); // true (چون Own Property است)
console.log(Object.hasOwn(child, "value")); // true
```

### 12.2 Shadowing و Method Overriding
همان‌طور که در بخش 4.3 دیدیم، تعریف یک Property با نام یکسان در Object فرزند، Property والد را Shadow می‌کند. در مورد متدها، به این کار **Method Overriding** می‌گویند.

```javascript
const parent = {
  greet() { console.log("Parent"); }
};

const child = Object.create(parent);

child.greet = function () {
  console.log("Child");
};

child.greet(); // "Child" (متد والد پنهان شد)
```

---

## 13. مباحث پیشرفته

### 13.1 Built-in Prototypes
جاوااسکریپت برای انواع داده‌های داخلی خود Prototypeهایی دارد:
- `Array.prototype` (شامل `map`, `filter`, `push`)
- `String.prototype` (شامل `toUpperCase`, `split`)
- `Function.prototype` (شامل `call`, `bind`, `apply`)

```javascript
const nums = [1, 2];
console.log(Object.getPrototypeOf(nums) === Array.prototype); // true
```
*هشدار:* هرگز Built-in Prototypes را تغییر ندهید (مثلاً `Array.prototype.myMethod = ...`). این کار باعث تداخل با کدهای دیگر و کتابخانه‌ها می‌شود و به آن **Monkey Patching** مخرب می‌گویند.

### 13.2 Prototype Pollution (آلودگی Prototype)
این یک آسیب‌پذیری امنیتی جدی در جاوااسکریپت (به‌ویژه در Node.js) است. اگر مهاجم بتواند Propertyای را به `Object.prototype` تزریق کند، **تمام** Objectهای برنامه آن Property را به ارث می‌برند.

```javascript
// سناریوی خطرناک (مثال آموزشی)
const userInput = '{"__proto__": {"isAdmin": true}}';
const parsed = JSON.parse(userInput);

// اگر کتابخانه‌ای ناایمن این را ادغام کند:
Object.assign({}, parsed); 

const regularUser = {};
console.log(regularUser.isAdmin); // true! (کل برنامه آلوده شد)
```
**راهکار جلوگیری:**
- استفاده از `Object.create(null)` برای دیکشنری‌ها.
- استفاده از `Object.hasOwn()` به جای بررسی مستقیم Propertyها.
- استفاده از `Map` به جای Object ساده برای ذخیره کلید-مقدارهای پویا.
- به‌روزرسانی کتابخانه‌ها و استفاده از ابزارهای Linting امنیتی.

### 13.3 Performance و Prototype
- **اشتراک متد:** استفاده از Prototype برای متدها، مصرف حافظه را به‌شدت کاهش می‌دهد.
- **طول زنجیره:** زنجیره‌های Prototype بسیار عمیق می‌توانند Property Lookup را کند کنند (هرچند موتورهای مدرن با "Inline Caching" این اثر را به حداقل می‌رسانند).
- **تغییر در Runtime:** همان‌طور که گفته شد، `Object.setPrototypeOf` باعث Deoptimization در موتور V8 می‌شود.

### 13.4 Mixins
به جای وراثت عمیق (که می‌تواند شکننده باشد)، می‌توان از Mixinها برای ترکیب رفتارها استفاده کرد. `Object.assign` می‌تواند Propertyها را از چند Object منبع به یک Object هدف کپی کند (توجه: این کپی است، نه لینک Prototype).

```javascript
const canWalk = { walk() { console.log("Walking"); } };
const canRun = { run() { console.log("Running"); } };

const athlete = {};
Object.assign(athlete, canWalk, canRun);

athlete.walk(); // Walking
```

### 13.5 Prototype و `this`
مقدار `this` در یک متد Prototype، در زمان **فراخوانی** (Call time) تعیین می‌شود، نه در زمان تعریف. اگر متد را از Object جدا کنید، `this` خود را از دست می‌دهد.

```javascript
function Person(name) { this.name = name; }
Person.prototype.sayHi = function() { console.log(this.name); };

const p = new Person("Ali");
p.sayHi(); // "Ali" (this برابر با p است)

const greet = p.sayHi;
greet(); // undefined (در Strict Mode) یا مقدار Global (در غیر این صورت)
// راه‌حل: استفاده از bind
const boundGreet = p.sayHi.bind(p);
boundGreet(); // "Ali"
```

---

## 14. اشتباهات رایج

| اشتباه | چرا بد است؟ | راهکار بهتر |
| :--- | :--- | :--- |
| **استفاده از `__proto__`** | منسوخ شده و در برخی محیط‌ها پشتیبانی نمی‌شود. | از `Object.getPrototypeOf()` استفاده کنید. |
| **تعریف متد داخل Constructor** | باعث ساخت هزاران کپی از یک تابع در حافظه می‌شود. | متد را روی `Constructor.prototype` تعریف کنید. |
| **قرار دادن داده‌های Reference (مثل آرایه) روی Prototype** | این داده بین تمام Instanceها به اشتراک گذاشته می‌شود و تغییر یکی، بقیه را خراب می‌کند. | داده‌های Instance را داخل Constructor با `this` مقداردهی کنید. |
| **بازنویسی کامل `prototype` بدون تنظیم `constructor`** | ارتباط `instance.constructor` به سازنده اصلی قطع می‌شود. | پس از انتساب، `NewProto.constructor = Func` را تنظیم کنید. |
| **تغییر Prototype در زمان اجرا** | باعث از بین رفتن بهینه‌سازی‌های موتور جاوااسکریپت و کندی شدید می‌شود. | Prototype را فقط در زمان ساخت تعیین کنید. |
| **استفاده از Object معمولی `{}` به عنوان دیکشنری** | Propertyهایی مثل `toString` ممکن است با کلیدهای داده تداخل کنند. | از `Object.create(null)` یا `Map` استفاده کنید. |

---

## 15. تمرین‌ها

### سطح مقدماتی
1. **ساخت زنجیره:** با استفاده از `Object.create()`، سه Object بسازید (`grandparent`, `parent`, `child`) به‌طوری که `child` به `parent` و `parent` به `grandparent` متصل باشد. یک Property روی `grandparent` تعریف کنید و از طریق `child` به آن دسترسی پیدا کنید.
2. **تشخیص مالکیت:** یک Object بسازید که یک Own Property و یک Inherited Property داشته باشد. با استفاده از `Object.hasOwn()` و عملگر `in` تفاوت آن‌ها را نشان دهید.
3. **دیکشنری امن:** یک Object با `Object.create(null)` بسازید. سعی کنید کلیدی به نام `hasOwnProperty` به آن اضافه کنید و نشان دهید که با متد پیش‌فرض تداخل ندارد.

### سطح Constructor Function
4. **ساخت کتاب:** یک Constructor Function به نام `Book` بسازید که `title` و `author` بگیرد. یک متد `getSummary()` به `Book.prototype` اضافه کنید. دو Instance بسازید و ثابت کنید که `getSummary` هر دو به یک تابع در حافظه اشاره می‌کند.
5. **بررسی `constructor`:** `Book.prototype` را با یک Object جدید بازنویسی کنید. سپس نشان دهید که `bookInstance.constructor` دیگر به `Book` اشاره نمی‌کند و آن را ترمیم کنید.

### سطح پیشرفته
6. **وراثت دستی:** بدون استفاده از `class`، یک Constructor به نام `Vehicle` و یکی به نام `Car` بسازید. `Car` باید از `Vehicle` ارث‌بری کند و متد اختصاصی `honk()` داشته باشد.
7. **تحلیل `this`:** یک Object با یک متد روی Prototype آن بسازید. متد را در یک متغیر ذخیره کرده و فراخوانی کنید تا خطای `this` را مشاهده کنید. سپس با `bind` آن را اصلاح کنید.
8. **شبیه‌سازی `instanceof`:** یک تابع به نام `myInstanceOf(obj, constructorFn)` بنویسید که با پیمایش زنجیره Prototype (`Object.getPrototypeOf`) بررسی کند آیا `obj` از `constructorFn` ساخته شده است یا خیر.

<details>
<summary><strong>💡 راهنمایی برای تمرین 8 (myInstanceOf)</strong></summary>
برای حل این تمرین، یک حلقه `while` ایجاد کنید. در هر تکرار، `obj` را به `Object.getPrototypeOf(obj)` به‌روزرسانی کنید. اگر به `null` رسیدید، `false` برگردانید. اگر در هر مرحله `obj === constructorFn.prototype` بود، `true` برگردانید.
</details>

---

## 16. جمع‌بندی

- **Prototype** یک مکانیزم لینک‌دهی بین Objectها در جاوااسکریپت است که امکان اشتراک رفتار و وراثت را فراهم می‌کند.
- **`[[Prototype]]`** لینک داخلی واقعی است (با `Object.getPrototypeOf` خوانده می‌شود)، در حالی که **`prototype`** یک Property روی Functionهاست که الگوی ساخت Instanceهای جدید را تعیین می‌کند.
- **Prototype Chain** مسیری است که موتور جاوااسکریپت برای جست‌وجوی Propertyها طی می‌کند تا به `null` برسد.
- کلیدواژه **`new`** یک Object می‌سازد، `[[Prototype]]` آن را به `Function.prototype` متصل می‌کند و Constructor را اجرا می‌نماید.
- **`Object.create()`** خالص‌ترین روش برای ساخت Object با Prototype دلخواه است و `Object.create(null)` برای ساخت دیکشنری‌های امن ایده‌آل است.
- **`class`** در جاوااسکریپت جایگزین Prototype نشده است؛ بلکه یک Syntax Sugar (شیرینی سینتکسی) روی همان مکانیزم Prototype است.
- از تغییر Prototype در زمان اجرا (Runtime) و دستکاری Prototypeهای Built-in به‌دلایل امنیتی (Prototype Pollution) و عملکردی خودداری کنید.

**مسیر پیشنهادی ادامه یادگیری:** پس از تسلط بر این مفاهیم، مطالعه در مورد `Object.defineProperty`، `Proxy`، و الگوی طراحی Composition over Inheritance (ترکیب به جای وراثت) را در برنامه خود قرار دهید.

---

## 17. منابع

برای مطالعه عمیق‌تر و بررسی جزئیات Specification، منابع رسمی زیر توصیه می‌شوند:

1. **MDN Web Docs — Inheritance and the Prototype Chain**  
   [لینک منبع](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain)
2. **MDN Web Docs — Object Prototypes**  
   [لینک منبع](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Advanced_JavaScript_objects/Object_prototypes)
3. **MDN Web Docs — `Object.create()`**  
   [لینک منبع](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create)
4. **MDN Web Docs — `Object.getPrototypeOf()`**  
   [لینک منبع](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf)
5. **MDN Web Docs — Classes**  
   [لینک منبع](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
6. **JavaScript.info — Prototypes, Inheritance**  
   [لینک منبع](https://javascript.info/prototypes)
7. **ECMAScript Language Specification (بخش Ordinary Object Internal Methods)**  
   [لینک منبع](https://tc39.es/ecma262/)
8. **OWASP — Prototype Pollution Prevention Cheat Sheet**  
   [لینک منبع](https://cheatsheetseries.owasp.org/cheatsheets/Prototype_Pollution_Prevention_Cheat_Sheet.html)

---
*این سند با رعایت استانداردهای آموزشی و با هدف ایجاد درک عمیق از معماری داخلی جاوااسکریپت تهیه شده است. برای گزارش اشکال یا پیشنهاد بهبود، می‌توانید از طریق Issues ریپوزیتوری اقدام کنید.*
