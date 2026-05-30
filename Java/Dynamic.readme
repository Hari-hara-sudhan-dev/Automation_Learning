## ✅ What is a Dynamic Attribute in Selenium?

A **dynamic attribute** is an attribute of a web element whose value **keeps changing every time the page loads or refreshes**.

***

## ✅ Example

```html
<input id="user_12345" type="text">
<input id="user_67890" type="text">
```

👉 Here, the **id value changes** (`user_12345`, `user_67890`)  
So, `id` is a **dynamic attribute**

***

## ✅ Why it is a problem?

* You **cannot use exact match locators**

```java
//input[@id='user_12345']  ❌ (will fail next time)
```

***

## ✅ How to Handle Dynamic Attributes

### 🔹 1. Use `contains()`

```java
driver.findElement(By.xpath("//input[contains(@id,'user')]"));
```

***

### 🔹 2. Use `starts-with()`

```java
driver.findElement(By.xpath("//input[starts-with(@id,'user')]"));
```

***

### 🔹 3. Use stable attributes (better option)

```java
driver.findElement(By.xpath("//input[@type='text']"));
```

***

### 🔹 4. CSS Selector with contains (`*`)

```java
driver.findElement(By.cssSelector("input[id*='user']"));
```

***

## ✅ Real-Time Example

```html
<button id="login_98765">Login</button>
```

✅ Best XPath:

```java
//button[contains(@id,'login')]
```

***

## ✅ Interview Answer (Short)

> A dynamic attribute is an attribute whose value changes frequently, like IDs generated dynamically. We handle it using XPath functions like `contains()` and `starts-with()` or by using stable attributes.

***

## ✅ Quick Tip

👉 Always:

* Avoid full dynamic values
* Use partial matching (`contains`)
* Prefer stable attributes if available

***

If you want, I can give **real website examples where dynamic attributes are tricky** 👍
