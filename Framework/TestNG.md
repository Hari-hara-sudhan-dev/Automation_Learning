Got it 👍 — you want the **same slide-style explanation** with **@BeforeTest and @AfterTest included**, plus a **real-time example**.

***

# ✅ Updated Slide: Where Annotations Are Used (Real Project)

| Annotation      | Usage in Project                                     |
| --------------- | ---------------------------------------------------- |
| `@BeforeSuite`  | Initialize reports, environment setup, DB connection |
| `@BeforeTest`   | Launch browser, set test-level configuration         |
| `@BeforeClass`  | Initialize WebDriver, page objects                   |
| `@BeforeMethod` | Navigate to application URL / Login setup            |
| `@Test`         | Execute test case (business validation)              |
| `@AfterMethod`  | Logout / Capture screenshot on failure               |
| `@AfterClass`   | Close browser instance                               |
| `@AfterTest`    | Clean up test data, close session                    |
| `@AfterSuite`   | Flush reports, send execution summary                |

***

# ✅ Full Real-Time Example (With BeforeTest & AfterTest)

### 🔹 Scenario: Login Application

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.*;

public class LoginTest {

    WebDriver driver;

    // ✅ Runs once before entire suite
    @BeforeSuite
    public void beforeSuite() {
        System.out.println("Before Suite: Setup reports & DB connection");
    }

    // ✅ Runs before each <test> in XML
    @BeforeTest
    public void beforeTest() {
        System.out.println("Before Test: Launch browser");
        driver = new ChromeDriver();
    }

    // ✅ Runs once before class
    @BeforeClass
    public void beforeClass() {
        System.out.println("Before Class: Maximize browser");
        driver.manage().window().maximize();
    }

    // ✅ Runs before each test method
    @BeforeMethod
    public void beforeMethod() {
        System.out.println("Before Method: Open login page");
        driver.get("https://example.com/login");
    }

    // ✅ Test Case
    @Test
    public void loginTest() {
        System.out.println("Executing Login Test");

        driver.findElement(By.id("username")).sendKeys("user");
        driver.findElement(By.id("password")).sendKeys("password");
        driver.findElement(By.id("loginBtn")).click();
    }

    // ✅ Runs after each test method
    @AfterMethod
    public void afterMethod() {
        System.out.println("After Method: Logout or take screenshot");
    }

    // ✅ Runs after all test methods in class
    @AfterClass
    public void afterClass() {
        System.out.println("After Class: Close browser instance");
        driver.quit();
    }

    // ✅ Runs after each <test> in XML
    @AfterTest
    public void afterTest() {
        System.out.println("After Test: Clean test data / session");
    }

    // ✅ Runs once after entire suite
    @AfterSuite
    public void afterSuite() {
        System.out.println("After Suite: Send report");
    }
}
```

***

# ✅ Execution Flow (Including BeforeTest & AfterTest)

```
@BeforeSuite
@BeforeTest
@BeforeClass
@BeforeMethod
@Test
@AfterMethod
@AfterClass
@AfterTest
@AfterSuite
```

***

# ✅ Key Interview Point 🔥

👉 Difference between important annotations:

* **@BeforeTest**
  → Runs before every `<test>` in `testng.xml`  
  → Used for browser launch

* **@BeforeClass**
  → Runs once before class  
  → Used for driver initialization

* **@BeforeMethod**
  → Runs before each test method  
  → Used for opening URL

***

# ✅ Simple Real-Life Mapping

Think like this:

* `@BeforeSuite` → Start project setup
* `@BeforeTest` → Open browser
* `@BeforeClass` → Prepare test class
* `@BeforeMethod` → Open app
* `@Test` → Perform action
* `@AfterMethod` → Logout
* `@AfterClass` → Close browser
* `@AfterTest` → Cleanup
* `@AfterSuite` → Report

### ✅ What is Assertion in TestNG?

👉 **Assertion** is used to **verify expected vs actual result** in your test.

> If the condition is **true → test passes ✅**  
> If the condition is **false → test fails ❌**

***

# ✅ Simple Definition

> **Assertion is a validation step in TestNG to check whether application behavior is correct or not.**

***

# ✅ Types of Assertions in TestNG

### 1. ✅ Hard Assertion (Most Important)

* If assertion **fails → test stops immediately**
* Remaining code will NOT execute

### Example:

```java
import org.testng.Assert;
import org.testng.annotations.Test;

public class HardAssertionExample {

    @Test
    public void testLogin() {

        String expected = "Home";
        String actual = "Dashboard";

        System.out.println("Before Assertion");

        Assert.assertEquals(actual, expected); // ❌ Fail

        System.out.println("After Assertion"); // ❌ This will NOT run
    }
}
```

***

# ✅ Common Hard Assertions

```java
Assert.assertEquals(actual, expected);
Assert.assertNotEquals(actual, expected);
Assert.assertTrue(condition);
Assert.assertFalse(condition);
Assert.assertNull(object);
Assert.assertNotNull(object);
```

***

# ✅ 2. Soft Assertion

* If assertion fails → test **continues execution**
* At end we must call **assertAll()**

### Example:

```java
import org.testng.asserts.SoftAssert;
import org.testng.annotations.Test;

public class SoftAssertionExample {

    @Test
    public void testProfile() {

        SoftAssert sa = new SoftAssert();

        System.out.println("Before Assertion");

        sa.assertEquals("Hello", "Hi"); // ❌ Fail
        System.out.println("After First Assertion");

        sa.assertTrue(5 > 3); // ✅ Pass
        System.out.println("After Second Assertion");

        sa.assertAll(); // ✅ Important (final result)
    }
}
```

***

# ✅ Real-Time Example (Login Application)

```java
@Test
public void loginTest() {

    driver.get("https://example.com/login");

    driver.findElement(By.id("username")).sendKeys("user");
    driver.findElement(By.id("password")).sendKeys("password");
    driver.findElement(By.id("loginBtn")).click();

    // ✅ Assertion (Validation)
    String expectedTitle = "Dashboard";
    String actualTitle = driver.getTitle();

    Assert.assertEquals(actualTitle, expectedTitle);

    System.out.println("Login Successful");
}
```

***

# ✅ Hard vs Soft Assertion (Interview Table)

| Feature          | Hard Assert          | Soft Assert          |
| ---------------- | -------------------- | -------------------- |
| Failure behavior | Stops execution      | Continues execution  |
| Usage            | Critical validations | Multiple validations |
| Method required  | Direct assert        | `assertAll()` needed |

***

# ✅ Real Project Usage

| Scenario                 | Assertion Used |
| ------------------------ | -------------- |
| Page title validation    | `assertEquals` |
| Button enabled check     | `assertTrue`   |
| Error message validation | `assertEquals` |
| Multiple UI checks       | Soft Assert    |

***

# ✅ Interview Answer (Best)

👉 **What is Assertion?**

> Assertion is used to validate expected and actual results. If the validation fails, the test case will be marked as failed.

***
