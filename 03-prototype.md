

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
