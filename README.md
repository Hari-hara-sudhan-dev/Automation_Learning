Here is your **complete README.md–style interview preparation file** ✅  
✅ Includes:

* Typed + image questions
* Clean Q\&A
* Crisp **10+ yrs level keywords**
* Well-structured Markdown

***

# 📘 Selenium + TestNG + Java Interview Guide (README)

***

# ✅ 1. Selenium Basics

### ❓ What is Selenium?

**Answer:**

* Open-source automation tool
* Used for web application testing
* Supports cross-browser and cross-platform

***

### ❓ What is WebDriver?

**Answer:**

* Interface to automate browsers
* Uses browser drivers (ChromeDriver, GeckoDriver)

***

### ❓ Cross Browser vs Cross Platform

**Answer:**

* Cross Browser → Chrome, Firefox, Edge
* Cross Platform → Windows, Linux, Mac

***

### ❓ Advantages of Selenium

**Answer Keywords:**

* Open source
* Multi-browser support
* Language support (Java, Python)
* Integration with TestNG/JUnit

***

# ✅ 2. Locators & XPath

### ❓ Types of Locators

**Answer:**

* id ✅ (fastest)
* name
* className
* tagName
* linkText
* XPath ✅
* CSS Selector ✅

***

### ❓ What is XPath?

**Answer:**

* XML path to locate elements
* Used for dynamic elements

***

### ❓ Absolute vs Relative XPath

**Answer:**

* Absolute → full path (not recommended ❌)
* Relative → flexible & stable ✅

***

### ❓ CSS vs XPath

**Answer:**

* CSS → faster ✅
* XPath → flexible, supports parent traversal ✅

***

### ❓ Chained Locator vs Relative Locator

**Answer:**

* Chained → multiple `findElement()`
* Relative (Selenium 4) → `above(), below(), near()`

***

# ✅ 3. WebDriver Commands

### ❓ get() vs navigate()

**Answer:**

* get() → load page
* navigate() → back, forward, refresh

***

### ❓ close() vs quit()

**Answer:**

* close() → current window
* quit() → entire browser

***

### ❓ findElement vs findElements

**Answer:**

* findElement → single element
* findElements → list (empty list if not found ✅)

***

# ✅ 4. Actions & User Interaction

### ❓ Mouse Hover

```java
Actions a = new Actions(driver);
a.moveToElement(ele).perform();
```

***

### ❓ Action Class Methods

* click()
* doubleClick()
* contextClick()
* dragAndDrop()
* moveToElement()

***

### ❓ perform()

* Executes the action ✅

***

# ✅ 5. Dropdown Handling

```java
Select s = new Select(ele);
s.selectByIndex();
s.selectByValue();
s.selectByVisibleText();
```

***

# ✅ 6. Waits (VERY IMPORTANT)

### ❓ Types of Wait

* Implicit wait
* Explicit wait ✅
* Fluent wait

***

### ❓ Implicit Wait

* Global wait applied to all elements

***

### ❓ Explicit Wait

```java
WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
wait.until(ExpectedConditions.visibilityOf(element));
```

***

### ❓ Why Thread.sleep() not recommended

* Static wait ❌
* Slows execution

***

# ✅ 7. Windows, Alerts, Frames

### ❓ Multiple Windows

```java
Set<String> handles = driver.getWindowHandles();
driver.switchTo().window(handle);
```

***

### ❓ Alerts

* accept()
* dismiss()
* sendKeys()

***

### ❓ Frames

```java
driver.switchTo().frame(index);
driver.switchTo().defaultContent();
```

***

# ✅ 8. Advanced Selenium

### ❓ JavaScriptExecutor

* Used when Selenium fails
* Scroll / Click hidden elements

***

### ❓ Shadow DOM

```java
element.getShadowRoot();
```

***

### ❓ Dynamic Elements (6 types)

* Dynamic ID
* AJAX
* Hidden elements
* Dynamic tables
* Changing attributes
* Shadow DOM

***

### ❓ Stale Element

* DOM refreshed  
  **Solution:** Re-locate element

***

### ❓ Broken Links

* Collect all `<a>` tags
* Validate HTTP response

***

### ❓ Canvas

* Cannot use Selenium locators
* Use JavaScriptExecutor

***

# ✅ 9. TestNG

### ❓ What is TestNG?

* Testing framework

***

### ❓ Execution Flow

```
Suite → Test → Class → Method
```

***

### ❓ Annotations

* @Test
* @BeforeMethod
* @AfterMethod
* @BeforeClass

***

### ❓ Retry Failed Tests

```java
implements IRetryAnalyzer
```

***

### ❓ Priority

```java
@Test(priority=1)
```

***

### ❓ Dependency

```java
@Test(dependsOnMethods="login")
```

***

### ❓ Assertions

* Hard → stops execution
* Soft → continues (`assertAll()`)

***

### ❓ Reports

* index.html
* emailable-report.html
* testng-results.xml

***

# ✅ 10. Framework & POM

### ❓ What is Framework?

* Structured automation setup

***

### ❓ Base Class

**Keywords:**

* Driver setup
* Config
* Utilities

***

### ❓ POM (Page Object Model)

* Separate locators & actions
* Improves maintainability ✅

***

### ❓ PageFactory

```java
@FindBy(id="username")
WebElement user;
```

***

# ✅ 11. Selenium Grid

### ❓ What is Selenium Grid?

* Parallel execution across machines

***

### ❓ Hub & Node

* Hub → central
* Node → execution machines

***

### ❓ RemoteWebDriver

* Execute tests remotely

***

### ❓ DesiredCapabilities

* Browser config
* In Selenium 4 → replaced by Options

***

# ✅ 12. Java Core

### ❓ JVM, JRE, JDK

* JVM → executes bytecode
* JRE → runtime
* JDK → development tools

***

### ❓ ArrayList vs LinkedList

| Feature       | ArrayList | LinkedList |
| ------------- | --------- | ---------- |
| Access        | Fast ✅    | Slow       |
| Insert/Delete | Slow      | Fast ✅     |

***

### ❓ Exception Handling

```java
try {
} catch(Exception e) {
} finally {
}
```

***

### ❓ throw vs throws

* throw → explicitly throw exception
* throws → declare exception

***

### ❓ OOPS

* Encapsulation
* Inheritance
* Polymorphism
* Abstraction

***

### ❓ String vs StringBuilder vs StringBuffer

* String → immutable
* StringBuilder → fast, mutable ✅
* StringBuffer → thread-safe

***

# ✅ 13. Scenario-Based

### ❓ Element not clickable

* Use Explicit Wait
* Use JavaScriptExecutor

***

### ❓ Dynamic Table

* Loop using XPath

***

### ❓ AJAX handling

* Wait for visibility/text

***

### ❓ File Download

* Verify file in local directory

***

### ❓ Flaky Tests

* Improve waits
* Improve locators

***

# ✅ 14. High-Level (10+ Years Answers)

### ❓ Framework you designed?

* Hybrid framework
* POM + TestNG + Utilities
* Extent reports
* Config driven

***

### ❓ Handle UI changes

* Centralized locators
* Update page class only

***

### ❓ Mentor juniors

* Code reviews
* Best practices
* Stable locators

***

# ✅ ✅ FINAL TIP

✅ Speak like this in interview:

* “I prefer Explicit Wait for stability”
* “I use POM-based hybrid framework”
* “Dynamic elements handled using XPath functions”

***

# 🚀 You are now interview ready (95–100%)

***

If you want next level:
👉 Say **“advanced README with project explanation”**  
I will add:

* Real project answer
* Manager round questions
* Deep scenario answers

🔥 That will make you *selection-ready*
