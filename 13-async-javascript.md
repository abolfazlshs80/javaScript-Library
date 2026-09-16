# قوانین کلی آموزش

## زبان

* تمام توضیحات فارسی باشند.
* اصطلاحات مهم انگلیسی را داخل پرانتز نیز بنویس.
* زبان ساده و مناسب افراد مبتدی باشد.
* ابتدا مفهوم را با زبان ساده توضیح بده.
* سپس مثال ساده ارائه کن.
* بعد کد را خط‌به‌خط توضیح بده.
* سپس خروجی را نشان بده.
* در انتهای هر بخش نکات مهم را جمع‌بندی کن.
* از توضیحات بیش از حد پیچیده در بخش‌های مقدماتی خودداری کن.
* در بخش‌های پیشرفته وارد جزئیات فنی JavaScript شو.

محتوا باید مستقیماً قابل استفاده در فایل Markdown و README یک GitHub Repository باشد.

---


در ابتدای مطلب یک Table of Contents کامل ایجاد کن و برای تمام Headingها لینک داخلی معتبر ایجاد کن.

ساختار کلی:

1. [مقدمه](#مقدمه)
2. [Synchronous و Asynchronous](#synchronous-و-asynchronous)
3. [چرا Asynchronous Programming مهم است؟](#چرا-asynchronous-programming-مهم-است)
4. [Blocking و Non-Blocking](#blocking-و-non-blocking)
5. [Callback چیست؟](#callback-چیست)
6. [Callback Function](#callback-function)
7. [Callback در عملیات Asynchronous](#callback-در-عملیات-asynchronous)
8. [setTimeout و Callback](#settimeout-و-callback)
9. [Callback Hell](#callback-hell)
10. [مشکلات Callback](#مشکلات-callback)
11. [Promise چیست؟](#promise-چیست)
12. [Promise States](#promise-states)
13. [Creating a Promise](#creating-a-promise)
14. [resolve و reject](#resolve-و-reject)
15. [then](#then)
16. [catch](#catch)
17. [finally](#finally)
18. [Promise Chaining](#promise-chaining)
19. [Returning Promise](#returning-promise)
20. [Error Handling](#error-handling)
21. [Promise.all](#promiseall)
22. [Promise.allSettled](#promiseallsettled)
23. [Promise.race](#promiserace)
24. [Promise.any](#promiseany)
25. [Promise.resolve](#promiseresolve)
26. [Promise.reject](#promisereject)
27. [async Function](#async-function)
28. [await](#await)
29. [async/await و Promise](#asyncawait-و-promise)
30. [try/catch در async/await](#trycatch-در-asyncawait)
31. [اجرای Sequential و Concurrent](#اجرای-sequential-و-concurrent)
32. [Event Loop و Promise](#event-loop-و-promise)
33. [Microtask Queue](#microtask-queue)
34. [Task Queue و Microtask Queue](#task-queue-و-microtask-queue)
35. [Fetch API و Promise](#fetch-api-و-promise)
36. [Promisification](#promisification)
37. [Callback API به Promise API](#callback-api-به-promise-api)
38. [اشتباهات رایج](#اشتباهات-رایج)
39. [Best Practices](#best-practices)
40. [مثال عملی](#مثال-عملی)
41. [تمرین‌ها](#تمرینها)
42. [جمع‌بندی](#جمع‌بندی)
43. [منابع معتبر](#منابع-معتبر)

---

# 1. مقدمه

ابتدا توضیح بده:

JavaScript چیست و چرا هنگام کار با مواردی مانند:

* API
* HTTP Request
* File
* Database
* Timer
* User Interaction
* Network Request

نیاز به Asynchronous Programming داریم.

توضیح بده که JavaScript در اجرای کدهای طولانی یا منتظر ماندن برای عملیات خارجی چگونه رفتار می‌کند.

---

# 2. Synchronous و Asynchronous

ابتدا مفهوم Synchronous را بسیار ساده توضیح بده.

مثال:

```javascript
console.log("A");
console.log("B");
console.log("C");
```

خروجی را توضیح بده.

سپس مفهوم Asynchronous را توضیح بده:

```javascript
console.log("A");

setTimeout(() => {
    console.log("B");
}, 1000);

console.log("C");
```

خروجی را مشخص کن:

```text
A
C
B
```

و به زبان ساده توضیح بده چرا `B` آخر چاپ می‌شود.

---

# 3. Blocking و Non-Blocking

توضیح بده:

* Blocking چیست؟
* Non-Blocking چیست؟
* چرا عملیات Asynchronous معمولاً برای جلوگیری از Block شدن جریان اصلی اجرای برنامه استفاده می‌شوند؟
* آیا `async` به معنی اجرای همزمان روی چند Thread است؟
* تفاوت Asynchronous و Parallel را توضیح بده.

این قسمت را با مثال ساده آموزش بده.

---

# 4. Callback چیست؟

تعریف دقیق و ساده Callback ارائه کن.

توضیح بده:

> Callback یک Function است که به Function دیگری داده می‌شود تا در زمان مناسب اجرا شود.

مثال:

```javascript
function greet(name, callback) {
    console.log("Hello " + name);
    callback();
}

function finish() {
    console.log("Finished");
}

greet("Ali", finish);
```

خط‌به‌خط توضیح بده.

---

# 5. Callback Function

توضیح بده:

* Function به عنوان Argument
* Anonymous Function
* Arrow Function به عنوان Callback
* Named Callback
* Callback با پارامتر

مثال:

```javascript
function processUser(name, callback) {
    callback(name);
}

processUser("Ali", function(name) {
    console.log(name);
});
```

سپس با Arrow Function:

```javascript
processUser("Ali", (name) => {
    console.log(name);
});
```

تفاوت آنها را توضیح بده.

---

# 6. Callback در عملیات Asynchronous

مثال واقعی با `setTimeout` ایجاد کن:

```javascript
function getData(callback) {
    setTimeout(() => {
        callback("Data received");
    }, 1000);
}

getData((data) => {
    console.log(data);
});
```

توضیح بده:

* Function چه زمانی اجرا می‌شود؟
* Callback چه زمانی اجرا می‌شود؟
* چرا Function اصلی منتظر نمی‌ماند؟
* Callback چگونه نتیجه عملیات را دریافت می‌کند؟

---

# 7. Callback Hell

مثال ساده Callback Hell ایجاد کن:

```javascript
getUser((user) => {
    getOrders(user, (orders) => {
        getProducts(orders, (products) => {
            getPayment(products, (payment) => {
                console.log(payment);
            });
        });
    });
});
```

توضیح بده:

* Callback Hell چیست؟
* چرا به آن Pyramid of Doom نیز گفته می‌شود؟
* مشکل خوانایی
* مشکل Error Handling
* مشکل نگهداری
* مشکل تست کردن

سپس توضیح بده Promise چگونه این مشکل را کاهش می‌دهد.

---

# 8. Promise چیست؟

Promise را بسیار ساده توضیح بده.

تعریف کن که Promise نماینده نتیجه‌ای است که ممکن است **الان آماده نباشد ولی در آینده مشخص شود**.

توضیح بده Promise سه حالت اصلی دارد:

```text
pending
fulfilled
rejected
```

همچنین مفهوم:

```text
settled
```

را توضیح بده.

طبق مستندات MDN، Promise نشان‌دهنده تکمیل یا شکست نهایی یک عملیات Asynchronous و نتیجه آن است.

---

# 9. Promise States

با نمودار متنی توضیح بده:

```text
          ┌──────────────┐
          │    Pending   │
          └──────┬───────┘
                 │
          ┌──────┴───────┐
          ↓              ↓
     Fulfilled        Rejected
```

توضیح بده:

* Pending
* Fulfilled
* Rejected
* Settled

و اینکه Promise بعد از Fulfilled یا Rejected دوباره به حالت دیگری برنمی‌گردد.

---

# 10. Creating a Promise

نحوه ساخت Promise را توضیح بده:

```javascript
const promise = new Promise((resolve, reject) => {

});
```

توضیح بده:

* `Promise`
* `new`
* Executor Function
* `resolve`
* `reject`

---

# 11. resolve

مثال:

```javascript
const promise = new Promise((resolve, reject) => {
    resolve("Success");
});
```

توضیح بده:

* resolve چه کاری انجام می‌دهد؟
* Promise چگونه Fulfilled می‌شود؟
* مقدار Resolve شده کجا قرار می‌گیرد؟

---

# 12. reject

مثال:

```javascript
const promise = new Promise((resolve, reject) => {
    reject("Something went wrong");
});
```

توضیح بده:

* reject چیست؟
* Promise چگونه Rejected می‌شود؟
* تفاوت Error و Reject را توضیح بده.

---

# 13. then

مثال:

```javascript
promise.then((result) => {
    console.log(result);
});
```

توضیح بده:

* `.then()` چیست؟
* Callback داخل آن چه زمانی اجرا می‌شود؟
* پارامتر Callback چیست؟

همچنین فرم:

```javascript
promise.then(
    (result) => {},
    (error) => {}
);
```

را توضیح بده.

---

# 14. catch

مثال:

```javascript
promise
    .then((result) => {
        console.log(result);
    })
    .catch((error) => {
        console.error(error);
    });
```

توضیح بده:

* `catch()` چیست؟
* چه خطاهایی را می‌تواند دریافت کند؟
* چرا معمولاً Error Handling را در انتهای Chain انجام می‌دهیم؟

---

# 15. finally

مثال:

```javascript
promise
    .then((result) => {
        console.log(result);
    })
    .catch((error) => {
        console.error(error);
    })
    .finally(() => {
        console.log("Finished");
    });
```

توضیح بده:

* `finally()` چیست؟
* چه زمانی اجرا می‌شود؟
* تفاوت آن با `then()` و `catch()`

---

# 16. Promise Chaining

Promise Chaining را کامل آموزش بده.

مثال:

```javascript
Promise.resolve(10)
    .then((value) => {
        return value * 2;
    })
    .then((value) => {
        return value + 5;
    })
    .then((value) => {
        console.log(value);
    });
```

خروجی را توضیح بده.

توضیح بده چرا `then()` یک Promise جدید برمی‌گرداند.

---

# 17. Returning Promise

این مفهوم را بسیار دقیق آموزش بده:

```javascript
function getUser() {
    return fetch("/api/user");
}
```

و:

```javascript
getUser()
    .then((response) => {
        return response.json();
    })
    .then((user) => {
        console.log(user);
    });
```

توضیح بده چرا `return` در Promise Chain مهم است و مفهوم **Floating Promise** را نیز معرفی کن.

---

# 18. Error Handling

روش‌های مدیریت خطا را آموزش بده:

### Promise

```javascript
promise
    .then(...)
    .catch(...)
```

### async/await

```javascript
try {
    
} catch(error) {

}
```

تفاوت این دو روش را توضیح بده.

همچنین تفاوت:

```javascript
throw new Error("...");
```

و:

```javascript
reject(new Error("..."));
```

را توضیح بده.

---

# 19. Promise.all

به‌صورت کامل توضیح بده:

```javascript
Promise.all([
    promise1,
    promise2,
    promise3
]);
```

توضیح بده:

* چه زمانی استفاده می‌شود؟
* آیا عملیات‌ها به‌صورت Sequential اجرا می‌شوند؟
* اگر یکی Reject شود چه اتفاقی می‌افتد؟
* ترتیب Resultها چگونه است؟

مثال واقعی با چند API ارائه کن.

---

# 20. Promise.allSettled

توضیح بده:

```javascript
Promise.allSettled([
    promise1,
    promise2,
    promise3
]);
```

تفاوت آن با `Promise.all()` را توضیح بده.

مثال:

```javascript
[
    { status: "fulfilled", value: ... },
    { status: "rejected", reason: ... }
]
```

---

# 21. Promise.race

توضیح بده:

```javascript
Promise.race([
    promise1,
    promise2
]);
```

توضیح بده:

* اولین Promise چه معنایی دارد؟
* اگر اولین Promise Reject شود چه می‌شود؟
* کاربردهای واقعی

---

# 22. Promise.any

توضیح بده:

```javascript
Promise.any([
    promise1,
    promise2,
    promise3
]);
```

تفاوت آن با:

* `Promise.all`
* `Promise.race`
* `Promise.allSettled`

را توضیح بده.

همچنین `AggregateError` را معرفی کن.

---

# 23. Promise.resolve

توضیح بده:

```javascript
Promise.resolve(10);
```

و:

```javascript
Promise.resolve(existingPromise);
```

چه تفاوتی دارند؟

---

# 24. Promise.reject

توضیح بده:

```javascript
Promise.reject(new Error("Failed"));
```

و نحوه مدیریت آن با `catch()` را نشان بده.

---

# 25. async Function

توضیح بده:

```javascript
async function getData() {
    return "Hello";
}
```

نکته بسیار مهم:

توضیح بده که یک `async function` **همیشه Promise برمی‌گرداند**، حتی اگر داخل آن یک مقدار معمولی `return` شود. این رفتار در مستندات MDN نیز صراحتاً توضیح داده شده است.

مثال:

```javascript
async function test() {
    return 10;
}

console.log(test());
```

و توضیح بده چرا خروجی یک Promise است.

---

# 26. await

توضیح بده:

```javascript
const result = await promise;
```

و اینکه:

* `await` چه کاری انجام می‌دهد؟
* نتیجه Promise را چگونه دریافت می‌کند؟
* اگر Promise Reject شود چه اتفاقی می‌افتد؟
* `await` در کجا قابل استفاده است؟

توضیح بده که `await` اجرای کل JavaScript را متوقف نمی‌کند؛ بلکه اجرای همان async function را تا مشخص شدن Promise نتیجه به تعویق می‌اندازد.

---

# 27. async/await

مثال Promise:

```javascript
getUser()
    .then((user) => {
        return getOrders(user);
    })
    .then((orders) => {
        console.log(orders);
    });
```

سپس همان مثال با async/await:

```javascript
async function loadData() {
    const user = await getUser();
    const orders = await getOrders(user);

    console.log(orders);
}
```

توضیح بده چرا `async/await` خوانایی کدهای Promise-based را افزایش می‌دهد.

---

# 28. try/catch با async/await

مثال:

```javascript
async function loadData() {
    try {
        const data = await getData();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}
```

توضیح بده:

* `try`
* `catch`
* `finally`
* Error propagation

---

# 29. Sequential vs Concurrent

این موضوع بسیار مهم است.

مثال Sequential:

```javascript
const user = await getUser();
const orders = await getOrders();
const products = await getProducts();
```

توضیح بده چه زمانی این روش درست است.

سپس مثال Concurrent:

```javascript
const [users, products] = await Promise.all([
    getUsers(),
    getProducts()
]);
```

توضیح بده چرا اگر عملیات‌ها به یکدیگر وابسته نباشند، اجرای Concurrent می‌تواند مناسب‌تر باشد. MDN نیز برای عملیات مستقل، استفاده از `Promise.all()` را به‌جای انتظار ترتیبی پیشنهاد می‌کند.

---

# 30. Event Loop و Promise

یک بخش کامل درباره ارتباط Promise با Event Loop ایجاد کن.

توضیح بده:

```text
Call Stack
   ↓
Web APIs / Host APIs
   ↓
Task Queue
   ↓
Microtask Queue
   ↓
Event Loop
```

سپس توضیح بده که Promise Callbackها در Microtask Queue قرار می‌گیرند.

---

# 31. Microtask Queue

این مثال را تحلیل کن:

```javascript
console.log("1");

Promise.resolve().then(() => {
    console.log("2");
});

console.log("3");
```

خروجی را مشخص کن:

```text
1
3
2
```

و دلیل آن را توضیح بده.

---

# 32. Task Queue و Microtask Queue

مثال:

```javascript
console.log("1");

setTimeout(() => {
    console.log("2");
}, 0);

Promise.resolve().then(() => {
    console.log("3");
});

console.log("4");
```

خروجی را مشخص کن و توضیح بده چرا:

```text
1
4
3
2
```

است.

تفاوت:

* Task
* Microtask
* `setTimeout`
* Promise Callback

را توضیح بده.

MDN توضیح می‌دهد که Callbackهای Promise به‌عنوان Microtask پردازش می‌شوند، در حالی که Callbackهای `setTimeout()` در Task Queue قرار می‌گیرند.

---

# 33. Fetch API

یک بخش عملی با `fetch()` ایجاد کن.

مثال:

```javascript
fetch("https://example.com/data")
    .then((response) => {
        return response.json();
    })
    .then((data) => {
        console.log(data);
    })
    .catch((error) => {
        console.error(error);
    });
```

سپس همان مثال را با async/await بنویس:

```javascript
async function getData() {
    try {
        const response = await fetch("https://example.com/data");
        const data = await response.json();

        console.log(data);
    } catch (error) {
        console.error(error);
    }
}
```

نکته مهم:

توضیح بده که `fetch()` برای خطاهای HTTP مانند 404 یا 500 لزوماً Promise را Reject نمی‌کند و باید `response.ok` یا `response.status` بررسی شود.

---

# 34. Promisification

توضیح بده Promisification چیست.

یعنی تبدیل APIهای Callback-based به Promise-based.

مثال:

```javascript
function oldApi(callback) {
    setTimeout(() => {
        callback(null, "Data");
    }, 1000);
}
```

سپس آن را تبدیل کن:

```javascript
function newApi() {
    return new Promise((resolve, reject) => {
        oldApi((error, data) => {
            if (error) {
                reject(error);
            } else {
                resolve(data);
            }
        });
    });
}
```

سپس استفاده:

```javascript
newApi()
    .then((data) => {
        console.log(data);
    });
```

این مفهوم را با مثال واقعی توضیح بده.

---

# 35. مقایسه Callback، Promise و async/await

یک مقایسه آموزشی ایجاد کن.

مثلاً:

### Callback

```javascript
getUser((user) => {
    getOrders(user, (orders) => {
        console.log(orders);
    });
});
```

### Promise

```javascript
getUser()
    .then((user) => getOrders(user))
    .then((orders) => {
        console.log(orders);
    });
```

### async/await

```javascript
async function load() {
    const user = await getUser();
    const orders = await getOrders(user);

    console.log(orders);
}
```

سپس توضیح بده که این سه روش چه ارتباطی با یکدیگر دارند.

---

# 36. اشتباهات رایج

حداقل 20 اشتباه رایج را توضیح بده.

مانند:

* فراموش کردن `return` در `.then()`
* استفاده اشتباه از `await`
* تصور اینکه `async` باعث اجرای موازی می‌شود
* استفاده Sequential از Promiseهای مستقل
* نداشتن Error Handling
* اشتباه گرفتن `Promise.all()` با `Promise.allSettled()`
* استفاده نادرست از `Promise.race()`
* فراموش کردن `await response.json()`
* تصور اینکه `fetch()` برای HTTP 404 Reject می‌شود
* Nest کردن بی‌دلیل `.then()`
* ساختن Promise بدون نیاز
* استفاده بی‌دلیل از `new Promise()`
* فراموش کردن اینکه `async function` یک Promise برمی‌گرداند
* فراموش کردن `await`
* Floating Promise
* اشتباه در ترتیب اجرای Microtask و Task

---

# 37. Best Practices

یک بخش کامل برای Best Practices ایجاد کن.

مواردی مانند:

* استفاده از async/await برای خوانایی بهتر
* استفاده صحیح از Promise Chain
* مدیریت مناسب Error
* استفاده از `Promise.all()` برای عملیات مستقل
* جلوگیری از Callback Hell
* جلوگیری از Promiseهای Floating
* عدم استفاده غیرضروری از `new Promise()`
* نام‌گذاری مناسب Functionهای Async
* استفاده مناسب از `try/catch`
* جلوگیری از Sequential Await غیرضروری

را توضیح بده.

---

# 38. مثال عملی کامل

یک مثال واقعی نسبتاً بزرگ ایجاد کن.

سناریو:

```text
دریافت User
    ↓
دریافت Orders
    ↓
دریافت Products
    ↓
نمایش اطلاعات
```

ابتدا با Callback پیاده‌سازی کن.

سپس با Promise.

سپس با async/await.

در نهایت تفاوت سه پیاده‌سازی را توضیح بده.

---

# 39. مثال Concurrent

یک مثال واقعی طراحی کن:

```text
User Profile
Products
Notifications
Statistics
```

که مستقل از یکدیگر هستند.

ابتدا روش اشتباه Sequential:

```javascript
const profile = await getProfile();
const products = await getProducts();
const notifications = await getNotifications();
```

سپس روش مناسب‌تر:

```javascript
const [
    profile,
    products,
    notifications
] = await Promise.all([
    getProfile(),
    getProducts(),
    getNotifications()
]);
```

زمان اجرای فرضی را نیز توضیح بده تا تفاوت آنها برای مبتدی قابل درک باشد.

---

# 40. تمرین‌ها

حداقل:

### 🟢 Beginner

10 تمرین

### 🟡 Intermediate

10 تمرین

### 🔴 Advanced

10 تمرین

تمرین‌ها باید شامل:

* Callback
* setTimeout
* Promise
* resolve/reject
* then/catch
* Promise Chaining
* Promise.all
* Promise.allSettled
* Promise.race
* Promise.any
* async/await
* try/catch
* Event Loop
* Microtask
* Fetch

باشند.

در ابتدا جواب تمرین‌ها را نشان نده.

در انتهای فصل بخش:

```markdown
# پاسخ تمرین‌ها
```

ایجاد کن.

---

# 41. بخش Debugging

یک بخش جداگانه برای Debug کردن Async JavaScript ایجاد کن.

توضیح بده چگونه:

* Promiseهای Pending را بررسی کنیم.
* Errorهای Async را پیدا کنیم.
* `console.log()` را در نقاط مختلف قرار دهیم.
* ترتیب اجرای کد را بررسی کنیم.
* Async Stack Trace را در Browser DevTools بررسی کنیم.

---

# 42. جمع‌بندی

در پایان یک نقشه ذهنی ساده ارائه کن:

```text
Asynchronous JavaScript
        │
        ├── Callback
        │     └── Callback Hell
        │
        ├── Promise
        │     ├── Pending
        │     ├── Fulfilled
        │     ├── Rejected
        │     ├── then
        │     ├── catch
        │     ├── finally
        │     └── Chaining
        │
        └── async / await
              ├── async
              ├── await
              ├── try/catch
              └── Promise.all
```

سپس یک خلاصه کوتاه از هر مفهوم ارائه کن.

---

# 43. نکات پیشرفته

در انتها یک بخش Advanced Topics ایجاد کن و موارد زیر را معرفی کن:

* Promise Resolution Procedure
* Thenable
* Microtask
* Job Queue
* Event Loop
* Promise Flattening
* Promise Assimilation
* Error Propagation
* Concurrency
* Cancellation
* AbortController
* Async Iteration
* `for await...of`
* Async Generator

برای این موارد در ابتدا توضیح کوتاه و ساده بده و سپس اگر لازم بود مثال ارائه کن.

---

# 44. استاندارد کدنویسی

تمام کدها داخل Code Block باشند:

```javascript
async function getUser() {
    const response = await fetch("/api/user");
    return response.json();
}
```

خروجی را در صورت امکان نشان بده:

```text
User loaded
```

بعد از هر مثال این ساختار را رعایت کن:

### کد

```javascript
// code
```

### خروجی

```text
// output
```

### توضیح

توضیح ساده و مرحله‌به‌مرحله.

### نکته مهم

یک نکته کلیدی مربوط به مثال.

---

# 45. اصلاح کدهای اشتباه

اگر در مثال‌های ارائه‌شده اشتباه Syntax یا Conceptual وجود داشت:

1. ابتدا نسخه صحیح کد را بنویس.
2. سپس مشکل کد قبلی را توضیح بده.
3. دلیل درست بودن نسخه اصلاح‌شده را بیان کن.
4. خروجی صحیح را مشخص کن.

هیچ رفتار JavaScript را حدس نزن.

در موارد حساس به استاندارد، از منابع معتبر ECMAScript و MDN استفاده کن.

---

# 46. منابع معتبر

در پایان حتماً بخش:

# منابع معتبر

ایجاد کن.

حداقل از منابع زیر استفاده کن:

### MDN Web Docs

برای:

* Promise
* async function
* await
* Callbacks
* Asynchronous JavaScript
* Fetch
* Microtasks

از صفحات مرتبط MDN استفاده کن.

### ECMAScript Specification

برای توضیحات عمیق‌تر درباره رفتار استاندارد Promise و JavaScript از Specification رسمی ECMAScript استفاده کن.

### JavaScript.info

برای:

* Callbacks
* Promise
* Promise Chaining
* Error Handling
* Promise API
* Promisification
* Microtasks
* Async/Await

استفاده کن.

برای هر منبع **لینک مستقیم و معتبر** قرار بده و از لینک‌های جعلی یا نامطمئن استفاده نکن.

---


بعد از مطالعه این فصل، یک فرد مبتدی باید بتواند:

* مفهوم Synchronous را توضیح دهد.
* مفهوم Asynchronous را بفهمد.
* Callback را تعریف کند.
* Callback Function بنویسد.
* Callback Hell را تشخیص دهد.
* Promise را بسازد.
* Promise States را توضیح دهد.
* از `resolve` و `reject` استفاده کند.
* از `then`، `catch` و `finally` استفاده کند.
* Promise Chain بسازد.
* خطاهای Promise را مدیریت کند.
* `Promise.all()` را استفاده کند.
* تفاوت `all`، `allSettled`، `race` و `any` را بداند.
* `async function` را درک کند.
* `await` را به‌درستی استفاده کند.
* `try/catch` را با async/await استفاده کند.
* Sequential و Concurrent را تشخیص دهد.
* ارتباط Promise و Event Loop را بفهمد.
* Microtask Queue را درک کند.
* با `fetch()` کار کند.
* Callback API را به Promise API تبدیل کند.
* کدهای Async JavaScript را Debug کند.
* و در نهایت بتواند بین Callback، Promise و async/await ارتباط مفهومی برقرار کند.

محتوا باید **از ساده‌ترین مفهوم شروع شود و به مفاهیم پیشرفته برسد**؛ به‌گونه‌ای که خواننده بدون مطالعه منابع دیگری بتواند مسیر یادگیری Asynchronous JavaScript را طی کند.


### ASSISTANT

این مستند به‌صورت مرحله‌به‌مرحله و از مقدماتی تا پیشرفته طراحی شده است تا شما را به تسلط کامل بر برنامه‌نویسی ناهمگام (Asynchronous) در جاوااسکریپت برساند.

---

## فهرست مطالب

1. [مقدمه](#1-مقدمه)
2. [Synchronous و Asynchronous](#2-synchronous-و-asynchronous)
3. [چرا Asynchronous Programming مهم است؟](#3-چرا-asynchronous-programming-مهم-است)
4. [Blocking و Non-Blocking](#4-blocking-و-non-blocking)
5. [Callback چیست؟](#5-callback-چیست)
6. [Callback Function](#6-callback-function)
7. [Callback در عملیات Asynchronous](#7-callback-در-عملیات-asynchronous)
8. [setTimeout و Callback](#8-settimeout-و-callback)
9. [Callback Hell](#9-callback-hell)
10. [مشکلات Callback](#10-مشکلات-callback)
11. [Promise چیست؟](#11-promise-چیست)
12. [Promise States](#12-promise-states)
13. [Creating a Promise](#13-creating-a-promise)
14. [resolve و reject](#14-resolve-و-reject)
15. [then](#15-then)
16. [catch](#16-catch)
17. [finally](#17-finally)
18. [Promise Chaining](#18-promise-chaining)
19. [Returning Promise](#19-returning-promise)
20. [Error Handling](#20-error-handling)
21. [Promise.all](#21-promiseall)
22. [Promise.allSettled](#22-promiseallsettled)
23. [Promise.race](#23-promiserace)
24. [Promise.any](#24-promiseany)
25. [Promise.resolve](#25-promiseresolve)
26. [Promise.reject](#26-promisereject)
27. [async Function](#27-async-function)
28. [await](#28-await)
29. [async/await و Promise](#29-asyncawait-و-promise)
30. [try/catch در async/await](#30-trycatch-در-asyncawait)
31. [اجرای Sequential و Concurrent](#31-اجرای-sequential-و-concurrent)
32. [Event Loop و Promise](#32-event-loop-و-promise)
33. [Microtask Queue](#33-microtask-queue)
34. [Task Queue و Microtask Queue](#34-task-queue-و-microtask-queue)
35. [Fetch API و Promise](#35-fetch-api-و-promise)
36. [Promisification](#36-promisification)
37. [Callback API به Promise API](#37-callback-api-به-promise-api)
38. [اشتباهات رایج](#38-اشتباهات-رایج)
39. [Best Practices](#39-best-practices)
40. [مثال عملی](#40-مثال-عملی)
41. [تمرین‌ها](#41-تمرینها)
42. [بخش Debugging](#42-بخش-debugging)
43. [جمع‌بندی](#43-جمع‌بندی)
44. [نکات پیشرفته](#44-نکات-پیشرفته)
45. [استاندارد کدنویسی و اصلاح کدهای اشتباه](#45-استاندارد-کدنویسی-و-اصلاح-کدهای-اشتباه)
46. [منابع معتبر](#46-منابع-معتبر)
47. [پاسخ تمرین‌ها](#47-پاسخ-تمرینها)

---

## 1. مقدمه

جاوااسکریپت (JavaScript) یک زبان برنامه‌نویسی **تک‌نخی (Single-threaded)** است، به این معنی که فقط می‌تواند یک کار را در یک لحظه انجام دهد. هنگام کار با مواردی مانند:
* درخواست‌های شبکه (API / HTTP Request / Network Request)
* خواندن یا نوشتن فایل (File / Database)
* تایمرها (Timer)
* تعامل کاربر (User Interaction)

اگر جاوااسکریپت بخواهد منتظر تکمیل این عملیات بماند، کل برنامه متوقف (Freeze) می‌شود. برای جلوگیری از این اتفاق، از **برنامه‌نویسی ناهمگام (Asynchronous Programming)** استفاده می‌کنیم تا عملیات‌های زمان‌بر در پس‌زمینه انجام شوند و جریان اصلی برنامه (Main Thread) آزاد بماند.

---

## 2. Synchronous و Asynchronous

### Synchronous (همگام)
کدها خط‌به‌خط و به ترتیب اجرا می‌شوند. خط بعدی تا زمانی که خط قبلی تمام نشود، اجرا نمی‌شود.

### کد
```javascript
console.log("A");
console.log("B");
console.log("C");
```
### خروجی
```text
A
B
C
```
### توضیح
هر دستور بلافاصله پس از دستور قبلی اجرا می‌شود.

### Asynchronous (ناهمگام)
اجازه می‌دهد یک عملیات شروع شود و قبل از تکمیل آن، کدهای بعدی اجرا شوند.

### کد
```javascript
console.log("A");

setTimeout(() => {
    console.log("B");
}, 1000);

console.log("C");
```
### خروجی
```text
A
C
B
```
### توضیح
دستور `setTimeout` یک عملیات ناهمگام را شروع می‌کند و بلافاصله به خط بعدی (`console.log("C")`) می‌رود. بعد از ۱ ثانیه، تابع داخل `setTimeout` اجرا شده و "B" چاپ می‌شود.
### نکته مهم
جاوااسکریپت برای عملیات زمان‌بر منتظر نمی‌ماند؛ آن را به محیط میزبان (مثل مرورگر یا Node.js) می‌سپارد و به اجرای کدهای بعدی ادامه می‌دهد.

---

## 3. چرا Asynchronous Programming مهم است؟

بدون برنامه‌نویسی ناهمگام، درخواست به یک سرور کند می‌تواند باعث قفل شدن رابط کاربری (UI) شود. کاربر نمی‌تواند کلیک کند یا اسکرول نماید تا زمانی که پاسخ سرور برسد. Asynchronous این تجربه کاربری را روان نگه می‌دارد.

---

## 4. Blocking و Non-Blocking

* **Blocking (مسدودکننده)**: عملیاتی که اجرای کدهای بعدی را متوقف می‌کند (مثل یک حلقه `while` بی‌نهایت یا خواندن همگام فایل بزرگ).
* **Non-Blocking (غیرمسدودکننده)**: عملیاتی که شروع می‌شود و برنامه بلافاصله به خط بعدی می‌رود (مثل `setTimeout` یا `fetch`).

### آیا `async` به معنی اجرای همزمان روی چند Thread است؟
**خیر.** جاوااسکریپت تک‌نخی است. Asynchronous به معنی **Parallel (موازی/چندنخی)** نیست، بلکه به معنی مدیریت هوشمندانه زمان انتظار است. عملیات موازی (Parallel) یعنی استفاده از چند هسته CPU همزمان (مثل Web Workers)، اما Asynchronous یعنی "منتظر نمان، بعداً خبرش را بده".

---

## 5. Callback چیست؟

**Callback (تابع بازفراخوانی)** تابعی است که به عنوان آرگومان به تابع دیگری داده می‌شود تا در زمان مناسب (معمولاً پس از تکمیل یک عملیات) اجرا شود.

> Callback یک Function است که به Function دیگری داده می‌شود تا در زمان مناسب اجرا شود.

### کد
```javascript
function greet(name, callback) {
    console.log("Hello " + name);
    callback();
}

function finish() {
    console.log("Finished");
}

greet("Ali", finish);
```
### خروجی
```text
Hello Ali
Finished
```
### توضیح
1. تابع `greet` با آرگومان‌های `"Ali"` و تابع `finish` صدا زده می‌شود.
2. ابتدا "Hello Ali" چاپ می‌شود.
3. سپس `callback()` اجرا می‌شود که همان تابع `finish` است و "Finished" را چاپ می‌کند.

---

## 6. Callback Function

توابع می‌توانند به چند شکل به عنوان Callback پاس داده شوند:

### کد
```javascript
function processUser(name, callback) {
    callback(name);
}

// 1. Named Callback (تابع نام‌گذاری شده)
function printName(name) {
    console.log(name);
}
processUser("Ali", printName);

// 2. Anonymous Function (تابع ناشناس)
processUser("Reza", function(name) {
    console.log(name);
});

// 3. Arrow Function (تابع پیکانی - مدرن و رایج)
processUser("Sara", (name) => {
    console.log(name);
});
```
### خروجی
```text
Ali
Reza
Sara
```
### نکته مهم
Arrow Functionها علاوه بر کوتاهی کد، مشکل تغییر مقدار `this` را نیز در بسیاری از مواقع حل می‌کنند.

---

## 7. Callback در عملیات Asynchronous

### کد
```javascript
function getData(callback) {
    console.log("در حال دریافت داده...");
    setTimeout(() => {
        callback("Data received");
    }, 1000);
}

getData((data) => {
    console.log(data);
});
console.log("این خط زودتر اجرا می‌شود");
```
### خروجی
```text
در حال دریافت داده...
این خط زودتر اجرا می‌شود
Data received
```
### توضیح
تابع `getData` اجرا می‌شود، `setTimeout` را تنظیم می‌کند و بلافاصله تمام می‌شود. خط بعدی (`این خط زودتر...`) اجرا می‌شود. پس از ۱ ثانیه، موتور جاوااسکریپت Callback را اجرا می‌کند.

---

## 8. setTimeout و Callback

`setTimeout` یک Web API است که یک Callback را پس از گذشت حداقل زمان مشخص‌شده (به میلی‌ثانیه) به صف اجرا اضافه می‌کند.

---

## 9. Callback Hell

وقتی چندین عملیات ناهمگام به یکدیگر وابسته باشند، Callbackها درون هم تودرتو (Nested) می‌شوند.

### کد
```javascript
getUser((user) => {
    getOrders(user, (orders) => {
        getProducts(orders, (products) => {
            getPayment(products, (payment) => {
                console.log(payment);
            });
        });
    });
});
```
### توضیح
* به این ساختار **Pyramid of Doom (هرم مرگ)** نیز می‌گویند.
* **مشکل خوانایی**: کد به سمت راست هل داده می‌شود.
* **مشکل Error Handling**: مدیریت خطا در هر سطح بسیار دشوار است.
* **مشکل نگهداری و تست**: تغییر یک بخش، کل ساختار تودرتو را تحت تأثیر قرار می‌دهد.

---

## 10. مشکلات Callback

1. خوانایی پایین (Callback Hell).
2. مدیریت خطای پیچیده (باید در هر مرحله خطا را چک کرد).
3. معکوس بودن کنترل (Inversion of Control): شما کنترل اجرای Callback را به تابع دیگری می‌سپارید و مطمئن نیستید چند بار یا کی اجرا می‌شود.

---

## 11. Promise چیست؟

**Promise (وعده)** یک شیء (Object) در جاوااسکریپت است که نماینده‌ی نتیجه‌ی یک عملیات ناهمگام است که **الان آماده نیست، اما در آینده مشخص می‌شود** (یا موفقیت‌آمیز خواهد بود یا با شکست مواجه می‌شود).

طبق مستندات MDN، Promise نشان‌دهنده تکمیل یا شکست نهایی یک عملیات Asynchronous و نتیجه آن است.

---

## 12. Promise States

یک Promise همیشه در یکی از حالت‌های زیر است:

```text
          ┌──────────────┐
          │    Pending   │ (در انتظار)
          └──────┬───────┘
                 │
          ┌──────┴───────┐
          ↓              ↓
     Fulfilled        Rejected
     (موفق)           (شکست)
          \              /
           └─────┬──────┘
                 ↓
              Settled
           (تعیین تکلیف شده)
```
* **Pending**: حالت اولیه، نه موفق شده و نه شکست خورده.
* **Fulfilled**: عملیات با موفقیت تکمیل شده است.
* **Rejected**: عملیات با خطا مواجه شده است.
* **Settled**: وضعیت نهایی (یا Fulfilled یا Rejected).
### نکته مهم
وقتی یک Promise به حالت Fulfilled یا Rejected برسد، **دیگر هرگز تغییر وضعیت نمی‌دهد** (Immutable).

---

## 13. Creating a Promise

### کد
```javascript
const promise = new Promise((resolve, reject) => {
    // Executor Function (تابع اجرایی)
    // عملیات ناهمگام اینجا انجام می‌شود
});
```
### توضیح
* `new Promise`: یک شیء Promise جدید می‌سازد.
* **Executor Function**: تابعی که بلافاصله توسط سازنده Promise اجرا می‌شود. دو پارامتر دارد: `resolve` و `reject`.

---

## 14. resolve و reject

### resolve
### کد
```javascript
const promise = new Promise((resolve, reject) => {
    resolve("Success");
});
```
### توضیح
`resolve` Promise را به حالت **Fulfilled** تغییر می‌دهد و مقدار `"Success"` را به عنوان نتیجه موفقیت‌آمیز ذخیره می‌کند.

### reject
### کد
```javascript
const promise = new Promise((resolve, reject) => {
    reject("Something went wrong");
});
```
### توضیح
`reject` Promise را به حالت **Rejected** تغییر می‌دهد. تفاوت آن با `throw new Error` این است که `reject` یک مقدار را به عنوان دلیل شکست برمی‌گرداند، در حالی که `throw` یک استثنا (Exception) پرتاب می‌کند (هرچند در Promise، `throw` خودکار به `reject` تبدیل می‌شود).

---

## 15. then

### کد
```javascript
const promise = new Promise((resolve) => resolve("Hello"));

promise.then((result) => {
    console.log(result);
});

// یا با دو آرگومان
promise.then(
    (result) => { console.log("Success:", result); },
    (error) => { console.log("Error:", error); }
);
```
### خروجی
```text
Hello
Success: Hello
```
### توضیح
متد `.then()` دو آرگومان اختیاری (تابع) می‌گیرد: اولی برای حالت Fulfilled و دومی برای حالت Rejected. این توابع زمانی اجرا می‌شوند که Promise تسویه (Settle) شود.

---

## 16. catch

### کد
```javascript
const promise = new Promise((resolve, reject) => {
    reject("Network Error");
});

promise
    .then((result) => {
        console.log(result);
    })
    .catch((error) => {
        console.error("Caught:", error);
    });
```
### خروجی
```text
Caught: Network Error
```
### توضیح
`.catch()` دقیقاً مشابه `.then(null, errorHandler)` عمل می‌کند. هر خطایی که در Promise یا در زنجیره `.then()` رخ دهد، به نزدیک‌ترین `.catch()` هدایت می‌شود. به همین دلیل معمولاً در انتهای زنجیره قرار می‌گیرد.

---

## 17. finally

### کد
```javascript
let isLoading = true;

const promise = new Promise((resolve) => resolve("Data"));

promise
    .then((result) => console.log(result))
    .catch((error) => console.error(error))
    .finally(() => {
        isLoading = false;
        console.log("Operation finished, loading stopped.");
    });
```
### خروجی
```text
Data
Operation finished, loading stopped.
```
### توضیح
`.finally()` بدون توجه به موفقیت یا شکست Promise اجرا می‌شود. برای پاک‌سازی (Cleanup) مثل مخفی کردن اسپینر لودینگ ایده‌آل است. مقدار بازگشتی آن معمولاً نادیده گرفته می‌شود.

---

## 18. Promise Chaining

زیبایی Promiseها در زنجیره‌سازی (Chaining) است، زیرا `.then()` همیشه یک **Promise جدید** برمی‌گرداند.

### کد
```javascript
Promise.resolve(10)
    .then((value) => {
        return value * 2; // 20
    })
    .then((value) => {
        return value + 5; // 25
    })
    .then((value) => {
        console.log(value);
    });
```
### خروجی
```text
25
```
### توضیح
هر `.then()` مقدار بازگشتی خود را درون یک Promise جدید قرار می‌دهد و به `.then()` بعدی پاس می‌دهد.

---

## 19. Returning Promise

اگر درون `.then()` یک Promise دیگر `return` شود، زنجیره منتظر تکمیل آن Promise داخلی می‌ماند.

### کد
```javascript
function getUser() {
    return Promise.resolve({ id: 1, name: "Ali" });
}

function getOrders(user) {
    return Promise.resolve(["Order 1", "Order 2"]);
}

getUser()
    .then((user) => {
        console.log("User:", user.name);
        return getOrders(user); // Return a new Promise
    })
    .then((orders) => {
        console.log("Orders:", orders);
    });
```
### خروجی
```text
User: Ali
Orders: [ 'Order 1', 'Order 2' ]
```
### نکته مهم (Floating Promise)
اگر `return` را فراموش کنید، Promise داخلی اجرا می‌شود اما زنجیره اصلی منتظر آن نمی‌ماند و مقدار `undefined` به مرحله بعد می‌رود. به این حالت **Floating Promise** (Promise شناور) می‌گویند که یک باگ رایج است.

---

## 20. Error Handling

### در Promise
### کد
```javascript
Promise.reject(new Error("Failed"))
    .then(() => console.log("This will be skipped"))
    .catch((error) => console.error("Caught in Promise:", error.message));
```

### در async/await
### کد
```javascript
async function handleError() {
    try {
        throw new Error("Async Failed");
    } catch (error) {
        console.error("Caught in try/catch:", error.message);
    }
}
handleError();
```
### توضیح
`throw new Error` یک استثنا پرتاب می‌کند که در Promise به `reject` تبدیل می‌شود و در `async/await` توسط `catch` گرفته می‌شود.

---

## 21. Promise.all

برای اجرای **چندین Promise به صورت همزمان (Concurrent)** و منتظر ماندن برای تکمیل **همه** آن‌ها استفاده می‌شود.

### کد
```javascript
const p1 = Promise.resolve(1);
const p2 = Promise.resolve(2);
const p3 = Promise.reject("Error in p3");

Promise.all([p1, p2])
    .then((results) => console.log("All results:", results))
    .catch((error) => console.error("At least one failed:", error));
```
### خروجی
```text
All results: [ 1, 2 ]
```
### توضیح
* عملیات‌ها به صورت موازی شروع می‌شوند.
* اگر **حتی یکی** Reject شود، کل `Promise.all` بلافاصله Reject می‌شود (Fail-fast).
* ترتیب آرایه نتایج، دقیقاً مطابق ترتیب آرایه ورودی است، نه ترتیب تکمیل عملیات.

---

## 22. Promise.allSettled

برخلاف `Promise.all`، این متد منتظر می‌ماند تا **همه** Promiseها تسویه (Settle) شوند، چه موفق و چه ناموفق.

### کد
```javascript
const p1 = Promise.resolve("Success");
const p2 = Promise.reject("Failed");

Promise.allSettled([p1, p2]).then((results) => {
    console.log(results);
});
```
### خروجی
```text
[
  { status: 'fulfilled', value: 'Success' },
  { status: 'rejected', reason: 'Failed' }
]
```
### توضیح
برای زمانی مناسب است که می‌خواهید نتیجه تمام عملیات را بدانید، حتی اگر برخی شکست بخورند (مثل آپلود همزمان چند فایل).

---

## 23. Promise.race

به محض اینکه **اولین** Promise تسویه شود (چه موفق، چه ناموفق)، نتیجه آن را برمی‌گرداند و بقیه را نادیده می‌گیرد.

### کد
```javascript
const fast = new Promise(resolve => setTimeout(() => resolve("Fast"), 100));
const slow = new Promise(resolve => setTimeout(() => resolve("Slow"), 500));

Promise.race([fast, slow]).then(console.log);
```
### خروجی
```text
Fast
```
### توضیح
کاربرد اصلی: پیاده‌سازی Timeout برای درخواست‌های شبکه (اگر درخواست در زمان مشخصی پاسخ نداد، Reject شود).

---

## 24. Promise.any

برخلاف `race`، این متد منتظر **اولین Promise موفق (Fulfilled)** می‌ماند. اگر همه Reject شوند، یک `AggregateError` پرتاب می‌کند.

### کد
```javascript
const p1 = Promise.reject("Error 1");
const p2 = Promise.resolve("Success 2");
const p3 = Promise.reject("Error 3");

Promise.any([p1, p2, p3])
    .then((result) => console.log("First success:", result))
    .catch((error) => console.error("All failed:", error.errors));
```
### خروجی
```text
First success: Success 2
```

---

## 25. Promise.resolve

یک Promise که از قبل Fulfilled شده است را برمی‌گرداند.

### کد
```javascript
const p = Promise.resolve(10);
p.then(val => console.log(val)); // 10

// اگر یک Promise موجود را پاس دهید، همان را برمی‌گرداند
const existing = Promise.resolve("Test");
console.log(Promise.resolve(existing) === existing); // true
```

---

## 26. Promise.reject

یک Promise که از قبل Rejected شده است را برمی‌گرداند.

### کد
```javascript
Promise.reject(new Error("Failed"))
    .catch(err => console.error(err.message));
```
### خروجی
```text
Failed
```

---

## 27. async Function

کلمه کلیدی `async` قبل از یک تابع، به جاوااسکریپت می‌گوید که این تابع همیشه یک **Promise** برمی‌گرداند.

### کد
```javascript
async function test() {
    return 10;
}

console.log(test());
```
### خروجی
```text
Promise { 10 }
```
### توضیح
حتی اگر یک مقدار معمولی (مثل 10) را `return` کنید، جاوااسکریپت آن را به صورت خودکار درون `Promise.resolve(10)` قرار می‌دهد.

---

## 28. await

کلمه کلیدی `await` فقط درون توابع `async` مجاز است. این کلمه اجرای **همان تابع async** را متوقف می‌کند تا Promise حل شود، اما کل موتور جاوااسکریپت را مسدود نمی‌کند.

### کد
```javascript
async function getData() {
    const result = await Promise.resolve("Data Loaded");
    console.log(result);
}
getData();
console.log("This runs after getData is called, but before await finishes");
```
### خروجی
```text
This runs after getData is called, but before await finishes
Data Loaded
```
### نکته مهم
`await` باعث می‌شود کد بعد از خود، شبیه به یک Callback در `.then()` رفتار کند و به Event Loop سپرده شود.

---

## 29. async/await و Promise

`async/await` در واقع یک **Syntactic Sugar (شکر نحوی)** روی Promiseها است.

### کد (Promise)
```javascript
getUser()
    .then((user) => getOrders(user))
    .then((orders) => console.log(orders));
```
### کد (async/await)
```javascript
async function loadData() {
    const user = await getUser();
    const orders = await getOrders(user);
    console.log(orders);
}
```
### توضیح
نسخه `async/await` خوانایی بسیار بالاتری دارد و شبیه به کد Synchronous به نظر می‌رسد، در حالی که در پس‌زمینه همچنان از Promise استفاده می‌کند.

---

## 30. try/catch در async/await

برای مدیریت خطا در `async/await` از بلوک `try/catch` استفاده می‌شود که معادل `.catch()` در Promise است.

### کد
```javascript
async function loadData() {
    try {
        const data = await Promise.reject("Network Error");
        console.log(data);
    } catch (error) {
        console.error("Error caught:", error);
    } finally {
        console.log("Cleanup");
    }
}
loadData();
```
### خروجی
```text
Error caught: Network Error
Cleanup
```

---

## 31. اجرای Sequential و Concurrent

این یکی از مهم‌ترین مفاهیم برای عملکرد (Performance) است.

### Sequential (ترتیبی - کندتر اگر وابسته نباشند)
### کد
```javascript
async function loadSequential() {
    const user = await getUser();       // 1 ثانیه
    const orders = await getOrders();   // 1 ثانیه
    const products = await getProducts(); // 1 ثانیه
    // مجموع زمان: 3 ثانیه
}
```

### Concurrent (همزمان - سریع‌تر)
### کد
```javascript
async function loadConcurrent() {
    const [user, orders, products] = await Promise.all([
        getUser(),      // شروع همزمان
        getOrders(),    // شروع همزمان
        getProducts()   // شروع همزمان
    ]);
    // مجموع زمان: 1 ثانیه (زمان طولانی‌ترین عملیات)
}
```
### نکته مهم
اگر عملیات‌ها به یکدیگر وابسته نیستند، **همیشه** از `Promise.all` برای اجرای Concurrent استفاده کنید. MDN نیز این روش را برای عملیات مستقل پیشنهاد می‌کند.

---

## 32. Event Loop و Promise

موتور جاوااسکریپت از یک **Event Loop** برای مدیریت اجرا استفاده می‌کند:

```text
Call Stack (پشته فراخوانی)
   ↓ (خالی می‌شود)
Microtask Queue (صف ریزوظایف: Promise.then, queueMicrotask)
   ↓ (کاملاً خالی می‌شود)
Task Queue / Macrotask Queue (صف وظایف: setTimeout, setInterval, I/O)
   ↓
Event Loop بررسی می‌کند: اگر Call Stack خالی است، ابتدا تمام Microtaskها را اجرا کن، سپس یک Macrotask را اجرا کن.
```

---

## 33. Microtask Queue

### کد
```javascript
console.log("1");

Promise.resolve().then(() => {
    console.log("2");
});

console.log("3");
```
### خروجی
```text
1
3
2
```
### توضیح
`console.log("1")` و `console.log("3")` همگام (Synchronous) هستند و بلافاصله اجرا می‌شوند. Callback مربوط به Promise در **Microtask Queue** قرار می‌گیرد و پس از خالی شدن Call Stack، قبل از هر Macrotask دیگری اجرا می‌شود.

---

## 34. Task Queue و Microtask Queue

### کد
```javascript
console.log("1");

setTimeout(() => {
    console.log("2");
}, 0);

Promise.resolve().then(() => {
    console.log("3");
});

console.log("4");
```
### خروجی
```text
1
4
3
2
```
### توضیح
1. `1` و `4` همگام هستند و اول اجرا می‌شوند.
2. `setTimeout` Callback خود را در **Task Queue** قرار می‌دهد.
3. `Promise.then` Callback خود را در **Microtask Queue** قرار می‌دهد.
4. Event Loop اولویت را به **Microtask Queue** می‌دهد، پس `3` چاپ می‌شود.
5. سپس **Task Queue** بررسی می‌شود و `2` چاپ می‌شود.

---

## 35. Fetch API و Promise

`fetch` یک Web API مدرن برای درخواست‌های شبکه است که بر پایه Promise بنا شده است.

### کد (با Promise)
```javascript
fetch("https://jsonplaceholder.typicode.com/users/1")
    .then((response) => {
        if (!response.ok) throw new Error("HTTP Error");
        return response.json();
    })
    .then((data) => console.log(data.name))
    .catch((error) => console.error(error));
```

### کد (با async/await)
```javascript
async function getUserData() {
    try {
        const response = await fetch("https://jsonplaceholder.typicode.com/users/1");
        if (!response.ok) throw new Error(`HTTP Error: ${response.status}`);
        const data = await response.json();
        console.log(data.name);
    } catch (error) {
        console.error(error);
    }
}
getUserData();
```
### نکته مهم
`fetch` فقط در صورت شکست شبکه (Network Failure) Promise را Reject می‌کند. برای خطاهای HTTP مثل 404 یا 500، Promise **Fulfilled** می‌شود، اما `response.ok` برابر `false` خواهد بود. بنابراین همیشه باید `response.ok` را بررسی کنید.

---

## 36. Promisification

**Promisification** فرآیند تبدیل یک تابع که از Callback استفاده می‌کند به تابعی که Promise برمی‌گرداند.

### کد
```javascript
// 1. Callback API قدیمی
function oldApi(callback) {
    setTimeout(() => {
        callback(null, "Data from old API");
    }, 500);
}

// 2. Promisification
function newApi() {
    return new Promise((resolve, reject) => {
        oldApi((error, data) => {
            if (error) {
                reject(error);
            } else {
                resolve(data);
            }
        });
    });
}

// 3. استفاده
newApi().then(data => console.log(data));
```
### خروجی
```text
Data from old API
```
### توضیح
این الگو در Node.js برای تبدیل توابع ماژول `fs` (مثل `fs.readFile`) به نسخه Promise-based (مثل `fs.promises.readFile`) بسیار رایج است.

---

## 37. Callback API به Promise API (مقایسه نهایی)

### Callback
```javascript
getUser((user) => {
    getOrders(user, (orders) => {
        console.log(orders);
    });
});
```
### Promise
```javascript
getUser()
    .then(user => getOrders(user))
    .then(orders => console.log(orders));
```
### async/await
```javascript
async function load() {
    const user = await getUser();
    const orders = await getOrders(user);
    console.log(orders);
}
```
### توضیح
هر سه روش یک کار را انجام می‌دهند، اما `async/await` خوانایی و قابلیت نگهداری کد را به سطح کد همگام (Synchronous) می‌رساند.

---

## 38. اشتباهات رایج

1. **فراموش کردن `return` در `.then()`**: باعث می‌شود مقدار `undefined` به مرحله بعد برود.
2. **استفاده از `await` خارج از تابع `async`**: باعث خطای Syntax می‌شود (مگر در Top-level await در ماژول‌ها).
3. **تصور اینکه `async` باعث اجرای موازی می‌شود**: `async` به تنهایی کد را موازی نمی‌کند، فقط اجازه `await` می‌دهد.
4. **استفاده Sequential از Promiseهای مستقل**: `await a(); await b();` به جای `Promise.all([a(), b()])`.
5. **نداشتن Error Handling**: فراموش کردن `.catch()` یا بلوک `try/catch`.
6. **اشتباه گرفتن `Promise.all()` با `Promise.allSettled()`**: اولی با یک خطا کل عملیات را لغو می‌کند.
7. **استفاده نادرست از `Promise.race()`**: انتظار برای موفقیت، در حالی که `race` با اولین خطا هم پایان می‌یابد.
8. **فراموش کردن `await response.json()`**: باعث می‌شود به جای داده، شیء Response چاپ شود.
9. **تصور اینکه `fetch()` برای HTTP 404 Reject می‌شود**: `fetch` فقط برای خطای شبکه Reject می‌شود.
10. **Nest کردن بی‌دلیل `.then()`**: ایجاد Callback Hell با Promiseها.
11. **ساختن Promise بدون نیاز**: استفاده از `new Promise` وقتی `Promise.resolve` کافی است.
12. **Floating Promise**: فراخوانی یک تابع async بدون `await` یا `.catch()` که خطاهای آن گم می‌شود.
13. **فراموش کردن اینکه `async function` یک Promise برمی‌گرداند**: انتظار مقدار مستقیم به جای `.then()`.
14. **استفاده از `await` در حلقه `forEach`**: `forEach` منتظر `await` نمی‌ماند. باید از `for...of` استفاده کرد.
15. **پرتاب خطای همگام در تابع async**: که ممکن است توسط `.catch()` زنجیره گرفته نشود اگر قبل از اولین `await` باشد (بهتر است کل بلوک در `try` باشد).
16. **عدم درک ترتیب اجرای Microtask و Task**: انتظار برای اجرای `setTimeout` قبل از `Promise.then`.
17. **Modify کردن شیء اصلی در زنجیره Promise**: باعث Side Effectهای پیش‌بینی‌نشده می‌شود.
18. **استفاده از `async` در Constructor کلاس**: Constructorها نمی‌توانند async باشند (باید یک متد `init` async ساخت).
19. **فراموش کردن `response.ok` در `fetch`**: که منجر به پردازش صفحات خطای HTML به جای JSON می‌شود.
20. **استفاده از `Promise.all` برای عملیات وابسته**: وقتی عملیات دوم به خروجی عملیات اول نیاز دارد، باید Sequential باشد.

---

## 39. Best Practices

* **خوانایی**: ترجیحاً از `async/await` به جای زنجیره‌های طولانی `.then()` استفاده کنید.
* **مدیریت خطا**: همیشه برای `async/await` از `try/catch` و برای Promiseها از `.catch()` در انتهای زنجیره استفاده کنید.
* **عملیات مستقل**: برای درخواست‌های مستقل از `Promise.all()` استفاده کنید تا زمان اجرا کاهش یابد.
* **جلوگیری از Floating Promise**: همیشه یا `await` کنید یا `.catch()` را فراخوانی کنید.
* **عدم استفاده غیرضروری از `new Promise()`**: اگر API از قبل Promise برمی‌گرداند، آن را در `new Promise` نپیچید (Anti-pattern).
* **نام‌گذاری**: توابع Async را با افعالی مثل `fetch...`، `load...` یا `get...` نام‌گذاری کنید.
* **حلقه‌ها**: برای استفاده از `await` در حلقه، به جای `forEach` از `for...of` استفاده کنید.

---

## 40. مثال عملی کامل

سناریو: دریافت User، سپس Orders، سپس Products و نمایش آن‌ها.

### کد (Callback - قدیمی)
```javascript
function getUserCb(cb) { setTimeout(() => cb({id: 1}), 100); }
function getOrdersCb(user, cb) { setTimeout(() => cb(["Order1"]), 100); }
function getProductsCb(orders, cb) { setTimeout(() => cb(["ProductA"]), 100); }

getUserCb((user) => {
    getOrdersCb(user, (orders) => {
        getProductsCb(orders, (products) => {
            console.log("Callback Result:", products);
        });
    });
});
```

### کد (Promise)
```javascript
function getUser() { return new Promise(r => setTimeout(() => r({id: 1}), 100)); }
function getOrders(user) { return new Promise(r => setTimeout(() => r(["Order1"]), 100)); }
function getProducts(orders) { return new Promise(r => setTimeout(() => r(["ProductA"]), 100)); }

getUser()
    .then(user => getOrders(user))
    .then(orders => getProducts(orders))
    .then(products => console.log("Promise Result:", products))
    .catch(err => console.error(err));
```

### کد (async/await - مدرن)
```javascript
async function loadData() {
    try {
        const user = await getUser();
        const orders = await getOrders(user);
        const products = await getProducts(orders);
        console.log("Async/Await Result:", products);
    } catch (error) {
        console.error("Error:", error);
    }
}
loadData();
```
### خروجی (هر سه)
```text
Callback Result: [ 'ProductA' ]
Promise Result: [ 'ProductA' ]
Async/Await Result: [ 'ProductA' ]
```
### توضیح
نسخه `async/await` ساختار خطی و تمیزی دارد، در حالی که نسخه Callback دچار تورفتگی عمیق است.

---

## 41. مثال Concurrent

سناریو: دریافت پروفایل، محصولات و اعلان‌ها که **مستقل** از یکدیگر هستند. هر کدام ۱ ثانیه طول می‌کشند.

### کد (روش اشتباه Sequential)
```javascript
async function loadDashboardBad() {
    console.time("Sequential");
    const profile = await getProfile();       // 1s
    const products = await getProducts();     // 1s
    const notifications = await getNotifications(); // 1s
    console.timeEnd("Sequential"); // حدود 3000ms
}
```

### کد (روش صحیح Concurrent)
```javascript
async function loadDashboardGood() {
    console.time("Concurrent");
    const [profile, products, notifications] = await Promise.all([
        getProfile(),
        getProducts(),
        getNotifications()
    ]);
    console.timeEnd("Concurrent"); // حدود 1000ms
}

// توابع کمکی فرضی
function getProfile() { return new Promise(r => setTimeout(() => r("Profile"), 1000)); }
function getProducts() { return new Promise(r => setTimeout(() => r("Products"), 1000)); }
function getNotifications() { return new Promise(r => setTimeout(() => r("Notifications"), 1000)); }

loadDashboardGood();
```
### خروجی
```text
Concurrent: 1005.123ms
```
### توضیح
با `Promise.all`، هر سه درخواست همزمان شروع می‌شوند. زمان کل برابر با زمان طولانی‌ترین درخواست (۱ ثانیه) است، نه مجموع آن‌ها (۳ ثانیه).

---

## 42. تمرین‌ها

### 🟢 Beginner
1. یک تابع بنویسید که با `setTimeout` پس از ۲ ثانیه "Hello World" چاپ کند.
2. یک Promise بسازید که پس از ۱ ثانیه با مقدار "Success" resolve شود.
3. یک Promise بسازید که بلافاصله با یک Error reject شود.
4. از `.then()` برای چاپ نتیجه یک Promise موفق استفاده کنید.
5. از `.catch()` برای مدیریت خطای یک Promise ردشده استفاده کنید.
6. یک تابع `async` بنویسید که عدد ۵ را برگرداند و نتیجه `console.log` آن را نشان دهید.
7. یک تابع `async` بنویسید که یک Promise را `await` کند و نتیجه را چاپ کند.
8. از `Promise.resolve(10)` استفاده کنید و نتیجه را در `.then` چاپ کنید.
9. یک `try/catch` درون یک تابع `async` بنویسید که یک خطا را `throw` کند.
10. تفاوت خروجی `console.log` قبل و بعد از یک `setTimeout` با زمان ۰ را توضیح دهید.

### 🟡 Intermediate
11. یک زنجیره Promise بسازید که عدد ۲ را بگیرد، در ۳ ضرب کند، سپس ۵ واحد به آن اضافه کند و چاپ کند.
12. تابعی بنویسید که یک Callback API فرضی را به Promise تبدیل کند (Promisification).
13. با استفاده از `Promise.all` دو درخواست فرضی را همزمان اجرا و نتایج را چاپ کنید.
14. با استفاده از `Promise.race` یک Timeout سفارشی برای یک Promise بسازید.
15. نشان دهید که چگونه `fetch` برای یک URL نامعتبر (بدون خطای شبکه) Reject نمی‌شود و چگونه باید `response.ok` را چک کرد.
16. یک حلقه `for...of` بنویسید که روی آرایه‌ای از URLها iterate کند و آن‌ها را به صورت Sequential با `await` fetch کند.
17. کدی بنویسید که در آن یک Floating Promise ایجاد شود و سپس آن را اصلاح کنید.
18. از `Promise.allSettled` استفاده کنید و وضعیت (status) هر نتیجه را چاپ کنید.
19. تفاوت بین `throw new Error()` درون یک تابع همگام و `return Promise.reject()` را در یک زنجیره `.then` نشان دهید.
20. یک تابع `async` بنویسید که در بلوک `finally` یک متغیر وضعیت (مثل `isLoading`) را تغییر دهد.

### 🔴 Advanced
21. یک تابع بنویسید که `Promise.any` را شبیه‌سازی کند (با استفاده از `Promise.all` و شمارنده).
22. کدی بنویسید که ترتیب دقیق چاپ اعداد ۱ تا ۶ را با ترکیب `console.log`، `setTimeout` و `Promise.resolve().then` پیش‌بینی و اثبات کند.
23. از `AbortController` برای لغو یک درخواست `fetch` پس از ۱ ثانیه استفاده کنید.
24. یک Async Generator تابع بنویسید و با حلقه `for await...of` روی آن iterate کنید.
25. یک تابع `delay(ms)` بنویسید که یک Promise برگرداند و برای ایجاد وقفه در کد async استفاده شود.
26. کدی بنویسید که نشان دهد چگونه یک خطای پرتاب‌شده در یک `.then` بدون `catch` محلی، به انتهای زنجیره منتقل می‌شود.
27. یک تابع بنویسید که آرایه‌ای از توابع async را بگیرد و آن‌ها را به صورت Sequential (یکی پس از دیگری) اجرا کند (نه با Promise.all).
28. توضیح دهید و نشان دهید که چرا `await Promise.resolve().then(...)` قبل از `setTimeout(..., 0)` اجرا می‌شود.
29. یک Promise را طوری بنویسید که اگر تا ۵۰۰ میلی‌ثانیه resolve نشد، خودکار reject شود (با استفاده از `Promise.race`).
30. یک کلاس بنویسید که یک متد `init` async داشته باشد، زیرا Constructor نمی‌تواند async باشد.

---

## 43. بخش Debugging

برای دیباگ کردن کدهای Async:
1. **بررسی Promiseهای Pending**: در Chrome DevTools، به تب "Sources" بروید و در بخش "Scope" یا با تایپ کردن متغیر در Console، وضعیت `[[PromiseState]]` را چک کنید.
2. **Async Stack Traces**: در DevTools مرورگر، وقتی خطایی رخ می‌دهد، Stack Trace به طور خودکار توابع async فراخوانی‌شده را به هم متصل می‌کند (در تنظیمات DevTools گزینه "Enable async stack traces" فعال باشد).
3. **استفاده از `console.log`**: قبل و بعد از هر `await` لاگ بگذارید تا متوجه شوید کد در کدام مرحله متوقف یا شکست می‌خورد.
4. **ترتیب اجرا**: با ترکیب `console.log` و `setTimeout`، درک خود از Event Loop را در کد واقعی تست کنید.
5. **Unhandled Promise Rejection**: همیشه مراقب هشدارهای زرد رنگ Console با عنوان "Uncaught (in promise)" باشید، زیرا نشان‌دهنده Floating Promiseهای شکست‌خورده هستند.

---

## 44. جمع‌بندی

```text
Asynchronous JavaScript
        │
        ├── Callback
        │     └── Callback Hell (Pyramid of Doom)
        │
        ├── Promise
        │     ├── States: Pending, Fulfilled, Rejected, Settled
        │     ├── Methods: .then(), .catch(), .finally()
        │     ├── Chaining: Returning values or new Promises
        │     └── Combinators: Promise.all, .allSettled, .race, .any
        │
        └── async / await
              ├── async: Always returns a Promise
              ├── await: Pauses execution inside the async function
              ├── Error Handling: try / catch / finally
              └── Concurrency: Using Promise.all for independent tasks
```
**خلاصه**: از Callback برای سادگی اولیه، از Promise برای مدیریت بهتر خطا و زنجیره‌سازی، و از `async/await` برای خوانایی نهایی و کدی شبیه به Synchronous استفاده کنید.

---

## 45. نکات پیشرفته

* **Thenable**: هر شیئی که متد `then` داشته باشد. Promiseها می‌توانند Thenableها را جذب (Assimilate) کنند.
* **Microtask / Job Queue**: صفی با اولویت بالا که Promiseها و `queueMicrotask` در آن قرار می‌گیرند و قبل از Task Queue (مثل `setTimeout`) اجرا می‌شوند.
* **Promise Flattening**: اگر یک Promise، یک Promise دیگر را resolve کند، جاوااسکریپت به صورت بازگشتی آن‌ها را باز می‌کند تا به یک مقدار نهایی برسد.
* **Cancellation**: Promiseهای بومی قابلیت لغو (Cancel) ندارند. برای لغو عملیات (مثل fetch) باید از `AbortController` استفاده کرد.
* **Async Iteration**: استفاده از `for await (const item of asyncIterable)` برای پیمایش داده‌های ناهمگام (مثل خواندن Stream فایل).
* **Async Generator**: توابعی با علامت `async function*` که می‌توانند با `yield` مقادیر را به صورت ناهمگام تولید کنند.

---

## 46. استاندارد کدنویسی و اصلاح کدهای اشتباه

### کد اشتباه رایج
```javascript
async function fetchUser() {
    const response = fetch("https://api.example.com/user");
    const data = response.json(); // خطا: response یک Promise است، نه شیء Response
    console.log(data);
}
```
### مشکل کد قبلی
تابع `fetch` یک Promise برمی‌گرداند. بدون `await`، متغیر `response` یک شیء Promise است، نه پاسخ HTTP. فراخوانی `.json()` روی آن باعث خطا می‌شود.

### کد اصلاح‌شده
```javascript
async function fetchUser() {
    try {
        const response = await fetch("https://api.example.com/user");
        if (!response.ok) throw new Error("Network response was not ok");
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error("Fetch error:", error);
    }
}
```
### دلیل درست بودن نسخه اصلاح‌شده
استفاده از `await` تضمین می‌کند که متغیر `response` حاوی شیء پاسخ واقعی است. بررسی `response.ok` از خطاهای HTTP جلوگیری می‌کند و `try/catch` خطاهای شبکه یا Parsing را مدیریت می‌کند.

---

## 47. منابع معتبر

### MDN Web Docs
* [Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)
* [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* [async function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
* [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
* [Event Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)

### ECMAScript Specification
* [ECMAScript Promise Specification](https://tc39.es/ecma262/#sec-promise-objects)
* [ECMAScript AsyncFunction Objects](https://tc39.es/ecma262/#sec-async-function-objects)

### JavaScript.info
* [Callbacks](https://javascript.info/callbacks)
* [Promise](https://javascript.info/promise-basics)
* [Promise Chaining](https://javascript.info/promise-chaining)
* [Microtasks](https://javascript.info/microtask-queue)
* [Async/Await](https://javascript.info/async-await)
* [Promisification](https://javascript.info/promisification)

---

## پاسخ تمرین‌ها

<details>
<summary>🟢 Beginner (کلیک کنید)</summary>

1. `setTimeout(() => console.log("Hello World"), 2000);`
2. `new Promise(resolve => setTimeout(() => resolve("Success"), 1000));`
3. `new Promise((resolve, reject) => reject(new Error("Fail")));`
4. `Promise.resolve("OK").then(res => console.log(res));`
5. `Promise.reject("Err").catch(err => console.log(err));`
6. `async function f() { return 5; } console.log(f()); // Promise { 5 }`
7. `async function f() { console.log(await Promise.resolve(10)); } f();`
8. `Promise.resolve(10).then(v => console.log(v));`
9. `async function f() { try { throw new Error("X"); } catch(e) { console.log(e.message); } } f();`
10. `console.log` اول اجرا می‌شود، سپس `setTimeout` به Task Queue می‌رود و بعد از اتمام کد همگام اجرا می‌شود.
</details>

<details>
<summary>🟡 Intermediate (کلیک کنید)</summary>

11. `Promise.resolve(2).then(v => v*3).then(v => v+5).then(console.log); // 11`
12. `const promisify = (fn) => (...args) => new Promise((res, rej) => fn(...args, (err, data) => err ? rej(err) : res(data)));`
13. `Promise.all([fetch('url1'), fetch('url2')]).then(res => console.log(res));`
14. `Promise.race([fetch('url'), new Promise((_, rej) => setTimeout(() => rej(new Error('Timeout')), 1000))]);`
15. `const res = await fetch('url'); if (!res.ok) throw new Error(res.status);`
16. `for (const url of urls) { const res = await fetch(url); }`
17. اشتباه: `doAsync();` (بدون await/catch). اصلاح: `await doAsync();` یا `doAsync().catch(console.error);`
18. `Promise.allSettled([Promise.resolve(1), Promise.reject('e')]).then(console.log);`
19. هر دو باعث می‌شوند زنجیره به `.catch` بعدی بپرد، اما `throw` یک استثنا است و `reject` یک مقدار.
20. `async function f() { try { await p(); } finally { isLoading = false; } }`
</details>

<details>
<summary>🔴 Advanced (کلیک کنید)</summary>

21. با شمارنده‌ای که تعداد rejectها را بشمارد و اگر به طول آرایه رسید، `AggregateError` پرتاب کند.
22. `console.log(1); Promise.resolve().then(() => console.log(2)); console.log(3); setTimeout(() => console.log(4), 0); Promise.resolve().then(() => console.log(5)); console.log(6);` خروجی: 1, 3, 6, 2, 5, 4.
23. `const controller = new AbortController(); setTimeout(() => controller.abort(), 1000); fetch(url, { signal: controller.signal });`
24. `async function* gen() { yield await Promise.resolve(1); } for await (const v of gen()) console.log(v);`
25. `const delay = ms => new Promise(res => setTimeout(res, ms));`
26. `Promise.resolve().then(() => { throw new Error("X"); }).catch(err => console.log(err));`
27. `async function runSeq(fns) { for (const fn of fns) await fn(); }`
28. زیرا Promise Callbackها در Microtask Queue هستند و `setTimeout` در Task Queue. Microtaskها اولویت بالاتری دارند.
29. `Promise.race([myPromise, new Promise((_, rej) => setTimeout(() => rej(new Error('Timeout')), 500))])`
30. `class MyClass { constructor() { this.init(); } async init() { await this.loadData(); } }`
</details>

---
*این مستند برای استفاده مستقیم در فایل `README.md` یک Repository آموزشی بهینه‌سازی شده است.*
