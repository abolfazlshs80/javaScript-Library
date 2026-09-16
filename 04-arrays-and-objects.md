

- [۱. آشنایی با Array](#۱-آشنایی-با-array)
- [۲. دسترسی به عناصر Array](#۲-دسترسی-به-عناصر-array)
- [۳. تغییر عناصر Array و مفهوم const](#۳-تغییر-عناصر-array-و-مفهوم-const)
- [۴. ویژگی Array Length](#۴-ویژگی-array-length)
- [۵. اضافه کردن عنصر با Index](#۵-اضافه-کردن-عنصر-با-index)
- [۶. متد Array.isArray()](#۶-متد-arrayisarray)
- [۷. معرفی متدهای Array](#۷-معرفی-متدهای-array)
- [۸. متد push()](#۸-متد-push)
- [۹. متد pop()](#۹-متد-pop)
- [۱۰. متد shift()](#۱۰-متد-shift)
- [۱۱. متد unshift()](#۱۱-متد-unshift)
- [۱۲. متد includes()](#۱۲-متد-includes)
- [۱۳. متد slice()](#۱۳-متد-slice)
- [۱۴. متد splice()](#۱۴-متد-splice)
- [۱۵. تفاوت slice و splice](#۱۵-تفاوت-slice-و-splice)
- [۱۶. متد reverse()](#۱۶-متد-reverse)
- [۱۷. متد flat()](#۱۷-متد-flat)
- [۱۸. سایر متدهای مهم Array](#۱۸-سایر-متدهای-مهم-array)
- [۱۹. عملگر Spread و Array](#۱۹-عملگر-spread-و-array)
- [۲۰. مفهوم Reference در Array](#۲۰-مفهوم-reference-در-array)
- [۲۱. Nested Array و Shallow/Deep Copy](#۲۱-nested-array-و-shallowdeep-copy)
- [۲۲. پیمایش Array (Iteration)](#۲۲-پیمایش-array-iteration)
- [۲۳. مفهوم Callback Function](#۲۳-مفهوم-callback-function)
- [۲۴. متد map()](#۲۴-متد-map)
- [۲۵. متد filter()](#۲۵-متد-filter)
- [۲۶. متد reduce()](#۲۶-متد-reduce)
- [۲۷. آشنایی با Object](#۲۷-آشنایی-با-object)
- [۲۸. Property و Value](#۲۸-property-و-value)
- [۲۹. Dot Notation و Bracket Notation](#۲۹-dot-notation-و-bracket-notation)
- [۳۰. تغییر Property در Object](#۳۰-تغییر-property-در-object)
- [۳۱. اضافه کردن Property](#۳۱-اضافه-کردن-property)
- [۳۲. حذف Property](#۳۲-حذف-property)
- [۳۳. بررسی وجود Property](#۳۳-بررسی-وجود-property)
- [۳۴. متد در Object (Object Method)](#۳۴-متد-در-object-object-method)
- [۳۵. Object داخل Array](#۳۵-object-داخل-array)
- [۳۶. Array داخل Object](#۳۶-array-داخل-object)
- [۳۷. Object تودرتو (Nested Object)](#۳۷-object-تودرتو-nested-object)
- [۳۸. متد Object.keys()](#۳۸-متد-objectkeys)
- [۳۹. متد Object.values()](#۳۹-متد-objectvalues)
- [۴۰. متد Object.entries()](#۴۰-متد-objectentries)
- [۴۱. حلقه for...in](#۴۱-حلقه-forin)
- [۴۲. عملگر Spread و Object](#۴۲-عملگر-spread-و-object)
- [۴۳. مفهوم Reference در Object](#۴۳-مفهوم-reference-در-object)
- [۴۴. Shallow Copy و Deep Copy در Object](#۴۴-shallow-copy-و-deep-copy-در-object)
- [۴۵. متد Object.assign()](#۴۵-متد-objectassign)
- [۴۶. تجزیه یا Destructuring در Array](#۴۶-تجزیه-یا-destructuring-در-array)
- [۴۷. تجزیه یا Destructuring در Object](#۴۷-تجزیه-یا-destructuring-در-object)
- [۴۸. کار با Array و Object به صورت ترکیبی](#۴۸-کار-با-array-و-object-به-صورت-ترکیبی)
- [۴۹. Array of Objects در پروژه‌های واقعی](#۴۹-array-of-objects-در-پروژههای-واقعی)
- [۵۰. Object و JSON](#۵۰-object-و-json)
- [۵۱. مقایسه Array و Object](#۵۱-مقایسه-array-و-object)
- [۵۲. مفاهیم Mutable و Immutable](#۵۲-مفاهیم-mutable-و-immutable)
- [۵۳. اشتباهات رایج (Common Mistakes)](#۵۳-اشتباهات-رایج-common-mistakes)
- [۵۴. مثال پروژه‌ای جامع](#۵۴-مثال-پروژه‌ای-جامع)
- [۵۵. مباحث پیشرفته (Advanced)](#۵۵-مباحث-پیشرفته-advanced)
- [۵۶. نتیجه‌گیری](#۵۶-نتیجه‌گیری)
- [۵۷. تمرین‌های عملی](#۵۷-تمرین‌های-عملی)
- [۵۸. منابع (References)](#۵۸-منابع-references)

---

## ۱. آشنایی با Array

### تعریف ساده
آرایه (Array) یک ساختار داده است که به شما اجازه می‌دهد چندین مقدار را در یک متغیر واحد ذخیره کنید. تصور کنید یک جعبه دارید که می‌توانید چندین وسیله مختلف را در آن بچینید.

### چرا از Array استفاده می‌کنیم؟
به جای ساخت ۱۰۰ متغیر جداگانه برای ۱۰۰ نام بازیکن، همه را در یک آرایه ذخیره می‌کنیم تا مدیریت، پیمایش و تغییر آن‌ها آسان باشد.

### ساخت Array
**Array Literal** (روش توصیه‌شده و رایج):
```javascript
const array = ["a", 12, true];
console.log(array); // ["a", 12, true]
```
**Array Constructor** (کمتر رایج، اما معتبر):
```javascript
const arr = new Array(3); // آرایه‌ای با ۳ خانه خالی
```

### انواع داده در Array
آرایه در جاوااسکریپت می‌تواند شامل انواع مختلف داده باشد:
- String: `["Ali", "Reza"]`
- Number: `[10, 20, 30]`
- Boolean: `[true, false]`
- Object: `[{name: "Ali"}, {name: "Reza"}]`
- Array دیگر (Nested Array): `[1, [2, 3], 4]`

### تفاوت Array با Variable معمولی
متغیر معمولی فقط **یک** مقدار نگه می‌دارد، اما Array یک **مجموعه مرتب** از مقادیر را نگه می‌دارد.

---

## ۲. دسترسی به عناصر Array

### تعریف ساده
هر عنصر در آرایه یک شماره موقعیت دارد که به آن **Index** (اندیس) می‌گویند. در جاوااسکریپت، شمارش Index از **صفر** شروع می‌شود.

### مثال
```javascript
const players = ["Haaland", "Rodri", "KDB"];

console.log(players[0]); // "Haaland" (اولین عنصر)
console.log(players[1]); // "Rodri"
console.log(players[2]); // "KDB" (آخرین عنصر)
```

### نکات مهم
- **Index نامعتبر**: اگر به اندیسی دسترسی پیدا کنید که وجود ندارد (مثلاً `players[5]`)، جاوااسکریپت خطا نمی‌دهد، بلکه مقدار `undefined` برمی‌گرداند.
- **دسترسی به آخرین عنصر**: `players[players.length - 1]`

---

## ۳. تغییر عناصر Array و مفهوم const

### تعریف ساده
کلمه کلیدی `const` به این معنی است که **متغیر** نمی‌تواند به آرایه‌ی دیگری اشاره کند، اما **محتویات** آن آرایه کاملاً قابل تغییر هستند.

### مثال
```javascript
const array = ["a", 12, true];
array[0] = "b";
console.log(array); // ["b", 12, true]
```

### چرا با وجود `const` می‌توانیم عنصر را تغییر دهیم؟
`const` فقط ارجاع (Reference) به حافظه را قفل می‌کند، نه محتویات داخل آن حافظه را.

### چرا این کار خطا می‌دهد؟
```javascript
const array = [1, 2, 3];
array = [4, 5, 6]; // TypeError: Assignment to constant variable.
```
**دلیل**: شما در حال تلاش برای تغییر کل ارجاع متغیر `array` به یک آرایه‌ی جدید در حافظه هستید، که `const` اجازه این کار را نمی‌دهد.

---

## ۴. ویژگی Array Length

### تعریف ساده
ویژگی `length` تعداد عناصر موجود در آرایه را برمی‌گرداند.

### مثال
```javascript
const players = ["Haaland", "Rodri", "KDB"];
console.log(players.length); // 3
```

### تغییر `length`
- **کوتاه کردن آرایه**: اگر `length` را کمتر کنید، عناصر انتهای آرایه حذف می‌شوند.
  ```javascript
  players.length = 2;
  console.log(players); // ["Haaland", "Rodri"]
  ```
- **افزایش `length`**: خانه‌های جدید با مقدار `undefined` (یا Empty Slot) پر می‌شوند.
- **رابطه Index و Length**: آخرین اندیس همیشه برابر است با `length - 1`.

---

## ۵. اضافه کردن عنصر با Index

### مثال
```javascript
const benchPlayer = [];
benchPlayer[0] = "Lewis";
benchPlayer[1] = "Doku";
console.log(benchPlayer); // ["Lewis", "Doku"]
```

### اضافه کردن در Index بزرگ‌تر (ایجاد Empty Slot)
```javascript
const players = [];
players[3] = "Silva";
console.log(players); // [empty × 3, "Silva"]
console.log(players.length); // 4
```
**تفاوت Empty Slot با `undefined`**: `undefined` یک مقدار واقعی است که به یک خانه اختصاص داده شده، اما Empty Slot یعنی آن خانه اصلاً وجود فیزیکی در حافظه ندارد (هرچند `length` آن را محاسبه می‌کند).

---

## ۶. متد Array.isArray()

### تعریف ساده
برای تشخیص اینکه آیا یک متغیر آرایه است یا خیر، از این متد استفاده می‌کنیم.

### چرا `typeof []` مقدار `"object"` برمی‌گرداند؟
در جاوااسکریپت، آرایه‌ها در واقع نوع خاصی از Object هستند. بنابراین `typeof` آن‌ها را `"object"` تشخیص می‌دهد.

### مثال
```javascript
console.log(Array.isArray([])); // true
console.log(Array.isArray("hello")); // false
console.log(Array.isArray({})); // false
```
**نکته**: این معتبرترین و ایمن‌ترین روش برای تشخیص آرایه است.

---

## ۷. معرفی متدهای Array
در بخش‌های بعدی، متدها را با قالب استاندارد بررسی می‌کنیم.

---

## ۸. متد push()

### تعریف ساده
یک یا چند عنصر را به **انتهای** آرایه اضافه می‌کند.

### Syntax
```javascript
array.push(element1, ..., elementN)
```

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB"];
players.push("Phillips");
console.log(players); // ["Haaland", "Rodri", "KDB", "Phillips"]
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: Yes**

### Return Value
طول (length) جدید آرایه را برمی‌گرداند.

### اشتباهات رایج
فرض کردن اینکه `push` خود آرایه را برمی‌گرداند. `push` عدد (طول جدید) برمی‌گرداند.

---

## ۹. متد pop()

### تعریف ساده
آخرین عنصر آرایه را **حذف** می‌کند.

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB"];
const removed = players.pop();
console.log(removed); // "KDB"
console.log(players); // ["Haaland", "Rodri"]
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: Yes**

### Return Value
عنصر حذف‌شده را برمی‌گرداند. اگر آرایه خالی باشد، `undefined` برمی‌گرداند.

---

## ۱۰. متد shift()

### تعریف ساده
اولین عنصر آرایه را **حذف** می‌کند و تمام عناصر باقی‌مانده را یک خانه به جلو می‌آورد (Indexها تغییر می‌کنند).

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB"];
const removed = players.shift();
console.log(removed); // "Haaland"
console.log(players); // ["Rodri", "KDB"]
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: Yes**

### Return Value
عنصر حذف‌شده را برمی‌گرداند.

---

## ۱۱. متد unshift()

### تعریف ساده
یک یا چند عنصر را به **ابتدای** آرایه اضافه می‌کند و Index بقیه عناصر را به‌روز می‌کند.

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB"];
const newLength = players.unshift("Stones");
console.log(newLength); // 4
console.log(players); // ["Stones", "Haaland", "Rodri", "KDB"]
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: Yes**

### Return Value
طول جدید آرایه را برمی‌گرداند.

---

## ۱۲. متد includes()

### تعریف ساده
بررسی می‌کند که آیا یک مقدار خاص در آرایه وجود دارد یا خیر.

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB"];
console.log(players.includes("KDB")); // true
console.log(players.includes("Silva")); // false
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: No (Immutable)**

### Return Value
مقدار `true` یا `false`.

### نکات مهم
- **Case Sensitivity**: به بزرگی و کوچکی حروف حساس است (`"kdb"` با `"KDB"` برابر نیست).
- **تفاوت با `indexOf`**: متد `indexOf` موقعیت عددی عنصر را برمی‌گرداند (یا `-1` اگر پیدا نشود)، اما `includes` مستقیماً `boolean` برمی‌گرداند که خواناتر است.

---

## ۱۳. متد slice()

### تعریف ساده
بخشی از آرایه را کپی کرده و به عنوان یک آرایه جدید برمی‌گرداند، بدون اینکه آرایه اصلی را تغییر دهد.

### Syntax
```javascript
array.slice(start, end)
```
- `start`: اندیس شروع (شامل می‌شود).
- `end`: اندیس پایان (**شامل نمی‌شود**).

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB", "Silva"];
const result = players.slice(1, 3);
console.log(result); // ["Rodri", "KDB"]
console.log(players); // ["Haaland", "Rodri", "KDB", "Silva"] (تغییر نکرده)
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: No (Immutable)**

### Return Value
یک آرایه جدید شامل عناصر انتخاب‌شده.

---

## ۱۴. متد splice()

### تعریف ساده
برای **حذف**، **جایگزینی** یا **اضافه کردن** عناصر در مکان‌های خاص از آرایه استفاده می‌شود.

### Syntax
```javascript
array.splice(start, deleteCount, item1, item2, ...)
```

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB"];
const removed = players.splice(1, 2, "X");
console.log(removed); // ["Rodri", "KDB"] (عناصر حذف‌شده)
console.log(players); // ["Haaland", "X"] (آرایه تغییر کرده)
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: Yes**

### Return Value
آرایه‌ای از عناصر حذف‌شده.

---

## ۱۵. تفاوت slice و splice

| ویژگی | `slice()` | `splice()` |
| :--- | :--- | :--- |
| **تغییر آرایه اصلی** | خیر (Immutable) | بله (Mutable) |
| **هدف اصلی** | کپی کردن بخشی از آرایه | حذف یا اضافه کردن عناصر |
| **پارامترها** | `(start, end)` | `(start, deleteCount, items...)` |
| **Return Value** | آرایه جدید (عناصر انتخاب‌شده) | آرایه‌ای از عناصر حذف‌شده |

---

## ۱۶. متد reverse()

### تعریف ساده
ترتیب عناصر آرایه را برعکس می‌کند.

### مثال ساده
```javascript
const players = ["Haaland", "Rodri", "KDB"];
players.reverse();
console.log(players); // ["KDB", "Rodri", "Haaland"]
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: Yes** (بسیار مراقب باشید، آرایه اصلی عوض می‌شود).

### Return Value
ارجاع به همان آرایه تغییریافته را برمی‌گرداند.

---

## ۱۷. متد flat()

### تعریف ساده
آرایه‌های تودرتو (Nested Arrays) را تا عمق مشخصی صاف (Flat) می‌کند و در یک آرایه جدید برمی‌گرداند.

### مثال ساده
```javascript
const numbers = [1, 2, 3, [5, 6], [7, [8, 9]]];
console.log(numbers.flat());       // [1, 2, 3, 5, 6, 7, [8, 9]] (عمق پیش‌فرض: 1)
console.log(numbers.flat(2));      // [1, 2, 3, 5, 6, 7, 8, 9]
console.log(numbers.flat(Infinity)); // [1, 2, 3, 5, 6, 7, 8, 9] (همه سطوح)
```

### آیا آرایه اصلی تغییر می‌کند؟
**Mutable: No (Immutable)**

### نکته مهم
متد `flat()` به طور خودکار Empty Slotها را حذف می‌کند.

---

## ۱۸. سایر متدهای مهم Array

### Searching (جستجو)
- **`indexOf(value)`**: اولین اندیس مقدار را برمی‌گرداند (یا `-1`). (Immutable)
- **`lastIndexOf(value)`**: آخرین اندیس مقدار را برمی‌گرداند. (Immutable)
- **`find(callback)`**: اولین مقداری که شرط callback را true کند برمی‌گرداند. (Immutable)
- **`findIndex(callback)`**: اندیس اولین مقداری که شرط را true کند برمی‌گرداند. (Immutable)
- **`findLast()` / `findLastIndex()`**: (ES2023) مانند `find` اما از انتها به ابتدا جستجو می‌کند. (Immutable)

### Iteration (پیمایش)
- **`forEach(callback)`**: برای هر عنصر یک تابع اجرا می‌کند. هیچ چیزی برنمی‌گرداند (`undefined`). (Mutable: خیر، اما اگر در callback آرایه را تغییر دهید، اصلی تغییر می‌کند).
- **`for...of`**: ساختار حلقه برای پیمایش مقادیر آرایه.

### Transformation (تبدیل)
- **`map(callback)`**: یک آرایه جدید با نتایج اجرای تابع روی هر عنصر می‌سازد. (Immutable)
- **`filter(callback)`**: یک آرایه جدید شامل عناصری که شرط را true کرده‌اند می‌سازد. (Immutable)
- **`reduce(callback, initialValue)`**: آرایه را به یک مقدار واحد (عدد، شیء، و غیره) کاهش می‌دهد. (Immutable)
- **`reduceRight()`**: مانند `reduce` اما از راست به چپ.
- **`flatMap()`**: ترکیب `map` و `flat(1)`. (Immutable)

### Checking (بررسی)
- **`some(callback)`**: اگر حداقل یک عنصر شرط را true کند، `true` برمی‌گرداند. (Immutable)
- **`every(callback)`**: اگر همه عناصر شرط را true کنند، `true` برمی‌گرداند. (Immutable)

### Sorting (مرتب‌سازی)
- **`sort(compareFn)`**: آرایه را مرتب می‌کند (پیش‌فرض بر اساس رشته). (Mutable)
- **`toSorted()`**: (ES2023) نسخه Immutable متد `sort`. یک آرایه جدید مرتب‌شده برمی‌گرداند.
- **`toReversed()`**: (ES2023) نسخه Immutable متد `reverse`.

### Copying & Creation
- **`concat()`**: دو یا چند آرایه را ادغام کرده و آرایه جدید برمی‌گرداند. (Immutable)
- **`Array.from(iterable)`**: یک آرایه جدید از یک شیء شبه‌آرایه (مثل NodeList) یا iterable می‌سازد.
- **`Array.of(...elements)`**: یک آرایه جدید از تعداد متغیری از آرگومان‌ها می‌سازد (تفاوت آن با `new Array()` در برخورد با یک آرگومان عددی است).

---

## ۱۹. عملگر Spread و Array

### تعریف ساده
عملگر Spread (`...`) عناصر یک آرایه را «باز» می‌کند. برای کپی کردن یا ترکیب آرایه‌ها عالی است.

### مثال
```javascript
const players = ["Haaland", "Rodri", "KDB"];
const newPlayers = [...players, "Silva"];
console.log(newPlayers); // ["Haaland", "Rodri", "KDB", "Silva"]
```

### نکات مهم
- این یک **Shallow Copy** (کپی سطحی) ایجاد می‌کند.
- بسیار خواناتر و مدرن‌تر از `concat()` است.

---

## ۲۰. مفهوم Reference در Array

در جاوااسکریپت، آرایه‌ها و اشیاء بر اساس **Reference** (ارجاع) ذخیره می‌شوند، نه Value.

### مثال ۱: ارجاع یکسان
```javascript
const a = [1, 2, 3];
const b = a; // b به همان حافظه‌ای اشاره می‌کند که a اشاره می‌کند
b.push(4);
console.log(a); // [1, 2, 3, 4] (a هم تغییر کرد!)
console.log(b); // [1, 2, 3, 4]
```

### مثال ۲: کپی واقعی با Spread
```javascript
const a = [1, 2, 3];
const b = [...a]; // یک آرایه جدید در حافظه ساخته می‌شود
b.push(4);
console.log(a); // [1, 2, 3] (تغییر نکرده)
console.log(b); // [1, 2, 3, 4]
```

---

## ۲۱. Nested Array و Shallow/Deep Copy

### تعریف ساده
- **Shallow Copy**: فقط سطح اول آرایه کپی می‌شود. اگر آرایه تودرتو باشد، سطوح داخلی همچنان Reference هستند.
- **Deep Copy**: تمام سطوح به طور کامل کپی می‌شوند.

### مثال Shallow Copy
```javascript
const numbers = [1, 2, [3, 4]];
const copy = [...numbers];
copy[2].push(5);
console.log(numbers[2]); // [3, 4, 5] (آرایه اصلی تغییر کرد!)
```

### راه‌حل Deep Copy
1. **`structuredClone()`** (روش مدرن و توصیه‌شده):
   ```javascript
   const deepCopy = structuredClone(numbers);
   ```
2. **JSON Serialization** (روش قدیمی، با محدودیت):
   ```javascript
   const deepCopy = JSON.parse(JSON.stringify(numbers));
   ```
   *محدودیت*: توابع، `undefined`، `Symbol` و `Date` را به درستی کپی نمی‌کند.

---

## ۲۲. پیمایش Array (Iteration)

### حلقه `for` کلاسیک
```javascript
for (let i = 0; i < players.length; i++) {
    console.log(players[i]);
}
```

### حلقه `for...of` (مدرن و خواناتر)
```javascript
const players = ["Haaland", "Rodri", "KDB"];
for (const player of players) {
    console.log(player);
}
```

### متد `forEach()`
```javascript
players.forEach((player, index) => {
    console.log(`${index}: ${player}`);
});
```

---

## ۲۳. مفهوم Callback Function

### تعریف ساده
Callback تابعی است که به عنوان آرگومان به یک تابع دیگر داده می‌شود تا بعداً اجرا شود. در متدهای آرایه، جاوااسکریپت این تابع را روی هر عنصر اجرا می‌کند.

### مثال
```javascript
function printPlayer(player) {
    console.log(player);
}
const players = ["Haaland", "Rodri"];
players.forEach(printPlayer);
```
یا با Arrow Function:
```javascript
players.forEach(player => console.log(player));
```

---

## ۲۴. متد map()

### تعریف ساده
یک آرایه جدید می‌سازد که حاصل اجرای یک تابع روی تک‌تک عناصر آرایه اصلی است.

### مثال واقعی
```javascript
const prices = [10, 20, 30];
const withTax = prices.map(price => price * 1.09);
console.log(withTax); // [10.9, 21.8, 32.7]
console.log(prices); // [10, 20, 30] (تغییر نکرده)
```
**Mutable: No**

---

## ۲۵. متد filter()

### تعریف ساده
یک آرایه جدید شامل فقط عناصری برمی‌گرداند که شرط تابع callback برای آن‌ها `true` باشد.

### مثال واقعی
```javascript
const users = [{name: "Ali", active: true}, {name: "Reza", active: false}];
const activeUsers = users.filter(user => user.active);
console.log(activeUsers); // [{name: "Ali", active: true}]
```
**Mutable: No**

---

## ۲۶. متد reduce()

### تعریف ساده
آرایه را با اعمال یک تابع تجمعی (Accumulator) به یک مقدار واحد کاهش می‌دهد.

### مثال ساده تا پیشرفته
```javascript
const numbers = [1, 2, 3, 4];
// accumulator: مقدار تجمعی، current: عنصر فعلی
const sum = numbers.reduce((accumulator, current) => {
    return accumulator + current;
}, 0); // 0 مقدار اولیه (initialValue) است
console.log(sum); // 10
```
**Mutable: No**

---

## ۲۷. آشنایی با Object

### تعریف ساده
شیء (Object) مجموعه‌ای از جفت‌های **Key-Value** (کلید-مقدار) است. بر خلاف آرایه که با Index مرتب است، Object با نام Property (کلید) دسترسی پیدا می‌کند.

### چرا از Object استفاده می‌کنیم؟
برای مدل‌سازی موجودیت‌های دنیای واقعی که ویژگی‌های مختلفی دارند (مثل یک کاربر با نام، سن و ایمیل).

### مثال (Object Literal)
```javascript
const person = {
    name: "Ali",
    age: 30,
    gender: "Male",
    isStudent: false
};
```
- **Property/Key**: نام ویژگی (مثل `name`).
- **Value**: مقدار ویژگی (مثل `"Ali"`).
- **Method**: اگر مقدار یک Property تابع باشد، به آن Method می‌گویند.

---

## ۲۸. Property و Value

دسترسی به مقادیر به دو روش امکان‌پذیر است:

### Dot Notation (نقطه‌ای)
```javascript
console.log(person.name); // "Ali"
console.log(person.age); // 30
```

### Bracket Notation (کراکتی)
```javascript
console.log(person["name"]); // "Ali"
console.log(person["age"]); // 30
```

---

## ۲۹. Dot Notation و Bracket Notation

### چه زمانی از Bracket استفاده کنیم؟
1. وقتی نام Property شامل فاصله یا کاراکترهای خاص است: `person["first name"]`
2. وقتی نام Property درون یک **متغیر** ذخیره شده است:
   ```javascript
   const propertyName = "age";
   console.log(person[propertyName]); // 30
   // person.propertyName کار نمی‌کند، چون دنبال کلیدی به نام "propertyName" می‌گردد!
   ```

---

## ۳۰. تغییر Property در Object
```javascript
person.age = 31;
console.log(person.age); // 31
```

---

## ۳۱. اضافه کردن Property
```javascript
person.salary = 3000;
console.log(person); // { name: "Ali", age: 31, gender: "Male", isStudent: false, salary: 3000 }
```

---

## ۳۲. حذف Property
با استفاده از عملگر `delete`:
```javascript
delete person.salary;
console.log(person.salary); // undefined
```
*نکته*: استفاده زیاد از `delete` می‌تواند بهینه‌سازی موتور جاوااسکریپت (V8) را کند کند. بهتر است در صورت امکان مقدار را `undefined` کنید یا از ساختار جدید استفاده کنید.

---

## ۳۳. بررسی وجود Property

### روش قدیمی
```javascript
person.hasOwnProperty("name"); // true
```

### روش مدرن و توصیه‌شده (ES2022)
```javascript
Object.hasOwn(person, "name"); // true
```
این روش ایمن‌تر است و حتی اگر Object متد `hasOwnProperty` را Override کرده باشد، درست کار می‌کند.

---

## ۳۴. متد در Object (Object Method)

### تعریف ساده
تابعی که به عنوان مقدار یک Property در Object تعریف شود.

### مثال
```javascript
const person = {
    name: "Ali",
    // روش قدیمی
    walkOld: function() {
        console.log("Walking...");
    },
    // روش مدرن و کوتاه‌تر (Method Shorthand)
    walk() {
        console.log("Walking...");
    }
};
person.walk(); // "Walking..."
```

---

## ۳۵. Object داخل Array
بسیار رایج در داده‌های دریافتی از API.
```javascript
const players = [
    { name: "Haaland", age: 25 },
    { name: "Rodri", age: 30 }
];
console.log(players[0].name); // "Haaland"
```

---

## ۳۶. Array داخل Object
```javascript
const person = {
    name: "Ali",
    hobbies: ["swimming", "playing football", "reading novels"]
};
console.log(person.hobbies[1]); // "playing football"
```

---

## ۳۷. Object تودرتو (Nested Object)
```javascript
const person = {
    name: "Ali",
    address: {
        city: "Sari",
        country: "Iran"
    }
};
console.log(person.address.city); // "Sari"
```

---

## ۳۸. متد Object.keys()
آرایه‌ای از تمام کلیدهای (Property names) قابل شمارش (Enumerable) خودِ شیء را برمی‌گرداند.
```javascript
console.log(Object.keys(person)); // ["name", "age", "gender", "isStudent"]
```
**Mutable: No**

---

## ۳۹. متد Object.values()
آرایه‌ای از تمام مقادیر (Values) شیء را برمی‌گرداند.
```javascript
console.log(Object.values(person)); // ["Ali", 30, "Male", false]
```
**Mutable: No**

---

## ۴۰. متد Object.entries()
آرایه‌ای از آرایه‌های `[key, value]` را برمی‌گرداند.
```javascript
console.log(Object.entries(person)); 
// [["name", "Ali"], ["age", 30], ["gender", "Male"], ["isStudent", false]]
```
**Mutable: No**

---

## ۴۱. حلقه for...in

### تعریف ساده
برای پیمایش کلیدهای (Properties) یک Object استفاده می‌شود.

### مثال
```javascript
for (const key in person) {
    console.log(key, person[key]);
}
```

### تفاوت `for...in` و `for...of`
- `for...in`: برای پیمایش **کلیدهای Object** (و به طور کلی enumerable properties).
- `for...of`: برای پیمایش **مقادیر Iterable** (مثل Array، String، Map).
*نکته*: برای آرایه‌ها، بهتر است از `for...of` یا متدهای آرایه استفاده کنید، زیرا `for...in` ممکن است Propertyهای به ارث رسیده از Prototype را نیز پیمایش کند.

### پیمایش خواناتر با `Object.entries` و `for...of`
```javascript
for (const [key, value] of Object.entries(person)) {
    console.log(`key=${key} value=${value}`);
}
```
این روش مدرن‌تر و ایمن‌تر از `for...in` است.

---

## ۴۲. عملگر Spread و Object

### تعریف ساده
برای کپی کردن یا ادغام Propertyهای چندین Object در یک Object جدید.

### مثال
```javascript
const person = { name: "Ali", age: 30 };
const car = { model: "Benz", year: 2020 };

const concatObject = {
    ...person,
    ...car,
    age: 31 // Override کردن مقدار قبلی
};

console.log(concatObject); // { name: "Ali", age: 31, model: "Benz", year: 2020 }
console.log(person); // { name: "Ali", age: 30 } (تغییر نکرده)
```

### نکات مهم
- **Shallow Copy** است.
- اگر کلیدهای هم‌نام وجود داشته باشند، **آخرین مقدار** مقدار قبلی را Override (بازنویسی) می‌کند.

---

## ۴۳. مفهوم Reference در Object
دقیقاً مشابه آرایه، اشیاء نیز با Reference مقایسه و تخصیص داده می‌شوند.

### مثال
```javascript
const person1 = { name: "Ali" };
const person2 = person1;
person2.name = "Reza";
console.log(person1.name); // "Reza" (تغییر کرد!)
```
**راه‌حل کپی**: `const person2 = { ...person1 };`

---

## ۴۴. Shallow Copy و Deep Copy در Object

- **Shallow Copy**: با `...` (Spread) یا `Object.assign()` ایجاد می‌شود. فقط سطح اول کپی می‌شود.
- **Deep Copy**: با `structuredClone(person)` ایجاد می‌شود. تمام سطوح تودرتو به طور مستقل کپی می‌شوند.

---

## ۴۵. متد Object.assign()

### تعریف ساده
مقادیر تمام Propertyهای قابل شمارش را از یک یا چند Object منبع به یک Object هدف کپی می‌کند.

### مثال
```javascript
const target = { a: 1 };
const source = { b: 2 };
const result = Object.assign(target, source);
console.log(result); // { a: 1, b: 2 }
console.log(target); // { a: 1, b: 2 } (target تغییر کرد - Mutable)
```
*تفاوت با Spread*: برای ایجاد یک Object جدید بدون تغییر منبع، باید هدف را `{}` قرار دهید: `Object.assign({}, obj1, obj2)`. امروزه Spread Operator (`...`) خوانایی بسیار بهتری دارد.

---

## ۴۶. تجزیه یا Destructuring در Array

### تعریف ساده
استخراج مقادیر از آرایه و اختصاص آن‌ها به متغیرهای مجزا در یک خط.

### مثال
```javascript
const players = ["Haaland", "Rodri", "KDB"];
const [first, second, third] = players;
console.log(first); // "Haaland"
```

### امکانات پیشرفته
- **Skip کردن**: `const [first, , third] = players;`
- **Default Value**: `const [a, b, c, d = "Unknown"] = players;`
- **Rest Element**: `const [first, ...rest] = players;` (بقیه عناصر در آرایه `rest` قرار می‌گیرند).

---

## ۴۷. تجزیه یا Destructuring در Object

### مثال
```javascript
const person = { name: "Ali", age: 30 };
const { name, age } = person;
console.log(name); // "Ali"
```

### امکانات پیشرفته
- **Rename**: `const { name: fullName } = person;` (مقدار `name` در متغیر `fullName` ذخیره می‌شود).
- **Default Value**: `const { salary = 0 } = person;`
- **Nested Destructuring**: `const { address: { city } } = person;`
- **Rest Property**: `const { name, ...restInfo } = person;`

---

## ۴۸. کار با Array و Object به صورت ترکیبی

### مثال واقعی
```javascript
const users = [
    { id: 1, name: "Ali", hobbies: ["football", "reading"] },
    { id: 2, name: "Reza", hobbies: ["coding", "gaming"] }
];

// دسترسی:
console.log(users[1].hobbies[0]); // "coding"

// جستجو (Find):
const ali = users.find(u => u.name === "Ali");

// فیلتر (Filter):
const coders = users.filter(u => u.hobbies.includes("coding"));

// تغییر داده (Map):
const names = users.map(u => u.name); // ["Ali", "Reza"]
```

---

## ۴۹. Array of Objects در پروژه‌های واقعی

این ساختار (`[{id: 1, name: "Ali"}, ...]`) استاندارد طلایی برای داده‌های دریافتی از Backend (API) است، زیرا:
1. هر Object یک رکورد (Record) مستقل با شناسه یکتا (`id`) است.
2. پیمایش و فیلتر کردن آن با متدهای آرایه بسیار ساده است.
3. به راحتی به JSON تبدیل و ارسال می‌شود.

---

## ۵۰. Object و JSON

### تعریف ساده
- **JavaScript Object**: ساختار داده در حافظه مرورگر/Node.js.
- **JSON (JavaScript Object Notation)**: یک فرمت متنی استاندارد برای تبادل داده.

### تفاوت‌ها
- در JSON، کلیدها **باید** داخل دابل‌کوتیشن (`" "`) باشند.
- در JSON نمی‌توان از تابع، `undefined` یا `Symbol` استفاده کرد.

### تبدیل
```javascript
const person = { name: "Ali", age: 30 };

// Object به JSON (برای ارسال به سرور)
const jsonString = JSON.stringify(person); 
console.log(jsonString); // '{"name":"Ali","age":30}'

// JSON به Object (پس از دریافت از سرور)
const parsedObj = JSON.parse(jsonString);
console.log(parsedObj.name); // "Ali"
```

---

## ۵۱. مقایسه Array و Object

| ویژگی | Array | Object |
| :--- | :--- | :--- |
| **ساختار** | Ordered Collection (مجموعه مرتب) | Key-Value Collection (مجموعه کلید-مقدار) |
| **دسترسی** | با Index عددی (`arr[0]`) | با Key رشته‌ای یا Symbol (`obj.name`) |
| **طول** | دارای `length` | فاقد `length` (باید از `Object.keys().length` استفاده کرد) |
| **کاربرد اصلی** | لیست‌های مرتب، داده‌های هم‌نوع | مدل‌سازی موجودیت‌ها، دیکشنری‌ها |

---

## ۵۲. مفاهیم Mutable و Immutable

درک این موضوع برای مدیریت حالت (State) در فریم‌ورک‌هایی مثل React حیاتی است.

### Mutable (تغییرپذیر - آرایه/شیء اصلی عوض می‌شود)
- `push`, `pop`, `shift`, `unshift`
- `splice`, `reverse`, `sort`
- `Object.assign()` (روی target)

### Immutable / Non-mutating (تغییرناپذیر - مقدار جدید برمی‌گرداند)
- `slice`, `concat`, `map`, `filter`, `reduce`
- `includes`, `find`, `some`, `every`
- `toSorted`, `toReversed` (ES2023)
- Spread Operator (`[...]`, `{...}`)
- `Object.keys`, `Object.values`, `Object.entries`

---

## ۵۳. اشتباهات رایج (Common Mistakes)

1. **اشتباه گرفتن Index با Length**: آخرین عنصر `arr[arr.length - 1]` است، نه `arr[arr.length]`.
2. **تصور Immutable بودن Array به دلیل `const`**: `const` فقط ارجاع را قفل می‌کند، نه محتوا را.
3. **استفاده اشتباه از `splice`**: فراموش کردن پارامتر `deleteCount` باعث حذف تمام عناصر از نقطه شروع می‌شود.
4. **اشتباه گرفتن `slice` و `splice`**: `slice` برای کپی (بدون تغییر)، `splice` برای جراحی آرایه (با تغییر).
5. **استفاده از `for...in` برای آرایه**: ممکن است ترتیب را تضمین نکند یا Propertyهای اضافی را پیمایش کند. از `for...of` استفاده کنید.
6. **اشتباه گرفتن Object و JSON**: JSON یک رشته (String) است، Object یک ساختار داده در حافظه است.
7. **فراموش کردن Return در `map` یا `filter`**: اگر از `{}` در Arrow Function استفاده کنید، باید `return` را دستی بنویسید.
8. **تغییر ناخواسته آرایه اصلی**: هنگام استفاده از `sort` یا `reverse`، ابتدا با `slice()` یا Spread یک کپی بگیرید.

---

## ۵۴. مثال پروژه‌ای جامع

فرض کنید داده‌های زیر را داریم و می‌خواهیم عملیات مختلفی روی آن انجام دهیم:

```javascript
const players = [
    { name: "Haaland", age: 25, position: "ST", goals: 20 },
    { name: "Rodri", age: 30, position: "CDM", goals: 5 },
    { name: "KDB", age: 34, position: "CM", goals: 10 }
];

// 1. پیدا کردن یک بازیکن خاص
const kdb = players.find(p => p.name === "KDB");

// 2. فیلتر کردن بازیکنان بالای 28 سال
const veterans = players.filter(p => p.age > 28);

// 3. استخراج فقط نام بازیکنان (Map)
const names = players.map(p => p.name); // ["Haaland", "Rodri", "KDB"]

// 4. مرتب‌سازی بر اساس تعداد گل (نزولی) - با ایجاد کپی برای حفظ اصل داده
const sortedByGoals = [...players].sort((a, b) => b.goals - a.goals);

// 5. محاسبه مجموع گل‌ها (Reduce)
const totalGoals = players.reduce((sum, p) => sum + p.goals, 0); // 35

// 6. بررسی اینکه آیا بازیکنی با پست "ST" وجود دارد
const hasStriker = players.some(p => p.position === "ST"); // true

// 7. اضافه کردن بازیکن جدید (Immutable)
const newPlayers = [...players, { name: "Silva", age: 29, position: "CAM", goals: 8 }];

// 8. حذف بازیکن (با فیلتر کردن)
const withoutRodri = players.filter(p => p.name !== "Rodri");

// 9. تغییر اطلاعات یک بازیکن (Immutable Update)
const updatedPlayers = players.map(p => 
    p.name === "Haaland" ? { ...p, goals: 21 } : p
);

// 10. Destructuring در حین پیمایش
for (const { name, goals } of players) {
    console.log(`${name} has ${goals} goals.`);
}

// 11. تبدیل به JSON برای ارسال به سرور
const payload = JSON.stringify(updatedPlayers);
```

---

## ۵۵. مباحث پیشرفته (Advanced)

این بخش برای درک عمیق‌تر موتور جاوااسکریپت است:

1. **Reference Type**: آرایه‌ها و اشیاء در Heap ذخیره می‌شوند و متغیرها فقط آدرس (Pointer) آن‌ها را در Stack نگه می‌دارند.
2. **Prototype**: هر آرایه به طور خودکار متدهایی مثل `map` را از `Array.prototype` به ارث می‌برد. هر Object از `Object.prototype`.
3. **Property Descriptors**: با `Object.getOwnPropertyDescriptor(obj, 'key')` می‌توان ویژگی‌های یک Property مثل `writable`، `enumerable` و `configurable` را دید.
4. **Enumerable Properties**: Propertyهایی که در حلقه‌های `for...in` یا `Object.keys` ظاهر می‌شوند.
5. **Object.freeze()**: شیء را کاملاً Immutable می‌کند (نه اضافه کردن، نه حذف، نه تغییر مقدار). Shallow است.
6. **Object.seal()**: اجازه تغییر مقدار Propertyهای موجود را می‌دهد، اما اضافه یا حذف Property جدید را مسدود می‌کند.
7. **Object.preventExtensions()**: فقط از اضافه کردن Propertyهای جدید جلوگیری می‌کند.
8. **Object.is()**: مقایسه دقیق‌تر از `===` (مثلاً `Object.is(NaN, NaN)` مقدار `true` برمی‌گرداند).
9. **`Object.create(proto)`**: ایجاد یک Object جدید با Prototype مشخص‌شده.

---

## ۵۶. نتیجه‌گیری

- **Array**: برای مجموعه‌های مرتب و لیست‌ها. با متدهای قدرتمندی مثل `map`، `filter` و `reduce` قابل مدیریت است. مراقب متدهای Mutable مثل `splice` و `sort` باشید.
- **Object**: برای مدل‌سازی داده‌های ساختاریافته با کلید-مقدار. دسترسی با `.` یا `[]`.
- **Mutable vs Immutable**: در برنامه‌نویسی مدرن، ترجیح بر ایجاد داده‌های جدید (Immutable) به جای تغییر داده‌های قدیمی است تا از باگ‌های جانبی جلوگیری شود.
- **Reference**: همیشه به یاد داشته باشید که `=` برای آرایه‌ها و اشیاء، مقدار را کپی نمی‌کند، بلکه ارجاع را کپی می‌کند. برای کپی از `...` یا `structuredClone()` استفاده کنید.
- **مسیر بعدی**: پس از تسلط بر این مفاهیم، مطالعه در مورد **Map/Set**، **Destructuring پیشرفته**، و **مدیریت State در React** گام منطقی بعدی است.

---

## ۵۷. تمرین‌های عملی

### صورت سؤالات
1. یک آرایه از اعداد `[1, 2, 3, 4, 5]` بسازید. با استفاده از یک متد، فقط اعداد زوج را در یک آرایه جدید ذخیره کنید.
2. آرایه‌ای از اشیاء شامل `{name, price}` دارید. با استفاده از `map`، یک آرایه جدید بسازید که در آن `price` هر کالا ۱۰٪ افزایش یافته باشد.
3. با استفاده از `reduce`، مجموع قیمت تمام کالاها در آرایه تمرین ۲ را محاسبه کنید.
4. یک Object به نام `student` با Propertyهای `name` و `grade` بسازید. با استفاده از Destructuring، این مقادیر را در دو متغیر جداگانه استخراج کنید و یک مقدار پیش‌فرض برای `grade` در نظر بگیرید.
5. آرایه‌ای شامل `[1, [2, [3, 4]], 5]` دارید. آن را به یک آرایه کاملاً صاف (Flat) تبدیل کنید.
6. تفاوت خروجی `const a = {x: 1}; const b = a; b.x = 2;` با `const a = {x: 1}; const b = {...a}; b.x = 2;` را توضیح دهید.
7. با استفاده از `Object.entries()` و `for...of`، تمام کلیدها و مقادیر یک Object را چاپ کنید.
8. یک آرایه از رشته‌ها دارید. بررسی کنید آیا رشته‌ای با طول بیشتر از ۵ کاراکتر در آن وجود دارد یا خیر (با استفاده از `some`).
9. با استفاده از `splice`، عنصر دوم و سوم یک آرایه ۵ عضوی را حذف کرده و به جای آن‌ها دو عنصر جدید قرار دهید.
10. یک Object تودرتو (Nested) بسازید و با استفاده از `structuredClone` یک Deep Copy از آن ایجاد کنید و ثابت کنید که تغییر در کپی، روی اصلی تأثیر نمی‌گذارد.

---

### پاسخ‌های تشریحی
<details>
<summary>برای مشاهده پاسخ‌ها کلیک کنید</summary>

1. 
```javascript
const nums = [1, 2, 3, 4, 5];
const evens = nums.filter(n => n % 2 === 0); // [2, 4]
```
2. 
```javascript
const items = [{name: "A", price: 100}, {name: "B", price: 200}];
const increased = items.map(item => ({...item, price: item.price * 1.1}));
```
3. 
```javascript
const total = increased.reduce((sum, item) => sum + item.price, 0);
```
4. 
```javascript
const student = {name: "Ali"};
const {name, grade = "A"} = student; // grade برابر "A" می‌شود
```
5. 
```javascript
const nested = [1, [2, [3, 4]], 5];
const flat = nested.flat(Infinity); // [1, 2, 3, 4, 5]
```
6. در حالت اول، `a.x` نیز `2` می‌شود (چون Reference یکسان است). در حالت دوم، `a.x` برابر `1` باقی می‌ماند (چون کپی مستقل ساخته شده است).
7. 
```javascript
const obj = {a: 1, b: 2};
for (const [key, value] of Object.entries(obj)) {
    console.log(`${key}: ${value}`);
}
```
8. 
```javascript
const words = ["hi", "hello", "world"];
const hasLong = words.some(w => w.length > 5); // true ("hello" و "world")
```
9. 
```javascript
const arr = [1, 2, 3, 4, 5];
arr.splice(1, 2, "X", "Y"); // [1, "X", "Y", 4, 5]
```
10. 
```javascript
const original = { info: { id: 1 } };
const copy = structuredClone(original);
copy.info.id = 2;
console.log(original.info.id); // 1 (تغییر نکرده)
```
</details>

---

## ۵۸. منابع (References)

برای مطالعه عمیق‌تر و بررسی مشخصات فنی، از منابع رسمی زیر استفاده کنید:

1. **MDN Web Docs - Arrays**: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
2. **MDN Web Docs - Objects**: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
3. **JavaScript.info - Arrays**: [https://javascript.info/array](https://javascript.info/array)
4. **JavaScript.info - Objects**: [https://javascript.info/object](https://javascript.info/object)
5. **ECMAScript Language Specification**: [https://tc39.es/ecma262/](https://tc39.es/ecma262/)

---
*این سند بر اساس استانداردهای جاوااسکریپت تا سال ۲۰۲۶ (شامل ویژگی‌های ES2022 و ES2023 مانند `Object.hasOwn`، `toSorted` و `findLast`) تدوین شده است.*
