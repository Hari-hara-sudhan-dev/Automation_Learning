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
Here is a **clear and real-time DataProvider example in TestNG** (important for interviews ✅)

***

# ✅ What is DataProvider in TestNG?

👉 **DataProvider is used to run the same test with multiple sets of data**

> Instead of writing multiple test methods, you can pass data dynamically.

***

# ✅ Basic Syntax

```java
@DataProvider(name = "dataName")
public Object[][] methodName() {
    return new Object[][] {
        {"data1", "data2"},
        {"data3", "data4"}
    };
}
```

***

# ✅ Simple Example

```java
import org.testng.annotations.DataProvider;
import org.testng.annotations.Test;

public class DataProviderExample {

    @DataProvider(name = "loginData")
    public Object[][] getData() {
        return new Object[][] {
            {"user1", "pass1"},
            {"user2", "pass2"},
            {"user3", "pass3"}
        };
    }

    @Test(dataProvider = "loginData")
    public void loginTest(String username, String password) {
        System.out.println("Username: " + username);
        System.out.println("Password: " + password);
    }
}
```

***

# ✅ Output

```
Username: user1 Password: pass1
Username: user2 Password: pass2
Username: user3 Password: pass3
```

👉 Same test runs **3 times** ✅

***

# ✅ Real-Time Example (Selenium Login)

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.*;

public class LoginTest {

    WebDriver driver;

    @BeforeMethod
    public void setup() {
        driver = new ChromeDriver();
        driver.get("https://example.com/login");
    }

    @Test(dataProvider = "loginData")
    public void loginTest(String username, String password) {

        driver.findElement(By.id("username")).sendKeys(username);
        driver.findElement(By.id("password")).sendKeys(password);
        driver.findElement(By.id("loginBtn")).click();

        System.out.println("Login attempted with: " + username);
    }

    @DataProvider(name = "loginData")
    public Object[][] getLoginData() {
        return new Object[][] {
            {"validUser", "validPass"},
            {"invalidUser", "invalidPass"},
            {"testUser", "testPass"}
        };
    }

    @AfterMethod
    public void tearDown() {
        driver.quit();
    }
}
```

***

# ✅ Parallel Execution with DataProvider 🔥

```java
@DataProvider(name = "loginData", parallel = true)
```

👉 Runs test data **in parallel threads**

***

# ✅ Using DataProvider from Another Class

```java
@Test(dataProvider = "loginData", dataProviderClass = DataClass.class)
```

***

# ✅ Real Project Usage

| Scenario              | Use                          |
| --------------------- | ---------------------------- |
| Login testing         | Multiple username/password   |
| Form testing          | Different input combinations |
| API testing           | Multiple payloads            |
| Cross-data validation | Data-driven testing          |

***

# ✅ Interview Answer (Best)

👉 **What is DataProvider?**

> DataProvider in TestNG is used to supply multiple sets of test data to a test method, allowing the same test to run multiple times with different inputs.

***

# ✅ Key Points

✔ Returns **Object\[]\[]**  
✔ Each row = one test execution  
✔ Reduces code duplication  
✔ Supports parallel execution ✅

***

✅ If you want next:

* Read data from **Excel using DataProvider (very important)**
* OR **Difference between DataProvider vs Parameter in TestNG**
### ✅ Parameterization in TestNG

👉 **Parameterization** means passing values to test cases **from outside the code** (like XML file), instead of hardcoding.

> Helps to run the same test with different inputs ✅

***

# ✅ Types of Parameterization in TestNG

1. **Using `@Parameters` (testng.xml)**
2. **Using `@DataProvider`** ✅ (you already learned this)

***

# ✅ 1. Parameterization using `@Parameters` (XML)

***

## ✅ Step 1: Write Test Class

```java
import org.testng.annotations.Parameters;
import org.testng.annotations.Test;

public class LoginTest {

    @Test
    @Parameters({"username", "password"})
    public void loginTest(String user, String pass) {
        System.out.println("Username: " + user);
        System.out.println("Password: " + pass);
    }
}
```

***

## ✅ Step 2: Define parameters in `testng.xml`

```xml
<suite name="TestSuite">

    <test name="LoginTest">

        <parameter name="username" value="admin"/>
        <parameter name="password" value="admin123"/>

        <classes>
            <class name="LoginTest"/>
        </classes>

    </test>

</suite>
```

***

## ✅ Output

```
Username: admin
Password: admin123
```

***

# ✅ 2. Real-Time Example (Selenium Login)

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.*;

public class LoginTest {

    WebDriver driver;

    @BeforeMethod
    public void setup() {
        driver = new ChromeDriver();
        driver.get("https://example.com/login");
    }

    @Test
    @Parameters({"username", "password"})
    public void loginTest(String user, String pass) {

        driver.findElement(By.id("username")).sendKeys(user);
        driver.findElement(By.id("password")).sendKeys(pass);
        driver.findElement(By.id("loginBtn")).click();

        System.out.println("Login with: " + user);
    }

    @AfterMethod
    public void tearDown() {
        driver.quit();
    }
}
```

***

# ✅ Important Points

✔ Values come from **testng.xml**  
✔ Good for **basic data passing**  
✔ Cannot handle large datasets ❌

***

# ✅ @Optional Parameter (Important 🔥)

```java
@Test
@Parameters({"username"})
public void test(@Optional("defaultUser") String user) {
    System.out.println(user);
}
```

👉 If value not in XML → default is used ✅

***

# ✅ DataProvider vs Parameters (Interview 🔥)

| Feature          | @Parameters | @DataProvider |
| ---------------- | ----------- | ------------- |
| Source           | testng.xml  | Java method   |
| Data size        | Small       | Large ✅       |
| Multiple sets    | No          | Yes ✅         |
| Parallel support | Limited     | Yes ✅         |

***

# ✅ Real Project Usage

| Scenario                          | Method Used       |
| --------------------------------- | ----------------- |
| Environment config (URL, browser) | `@Parameters` ✅   |
| Login data, test data             | `@DataProvider` ✅ |

***

# ✅ Interview Answer (Perfect)

👉 **What is Parameterization?**

> Parameterization in TestNG is a technique used to pass inputs to test methods from external sources like testng.xml, making tests flexible and reusable.

***

# ✅ Simple Understanding

* `@Parameters` → Single input from XML
* `@DataProvider` → Multiple inputs from code

***
### ✅ Apache POI – Only Syntax (Read & Write)

***

# ✅ Read Excel Syntax

```java
FileInputStream fis = new FileInputStream("file.xlsx");
XSSFWorkbook workbook = new XSSFWorkbook(fis);
XSSFSheet sheet = workbook.getSheet("Sheet1");

int rows = sheet.getPhysicalNumberOfRows();

for (int i = 0; i < rows; i++) {
    XSSFRow row = sheet.getRow(i);

    for (int j = 0; j < row.getPhysicalNumberOfCells(); j++) {
        XSSFCell cell = row.getCell(j);
        System.out.print(cell.toString() + " ");
    }
    System.out.println();
}

workbook.close();
fis.close();
```

***

# ✅ Write Excel Syntax

```java
XSSFWorkbook workbook = new XSSFWorkbook();
XSSFSheet sheet = workbook.createSheet("Sheet1");

XSSFRow row = sheet.createRow(0);
row.createCell(0).setCellValue("Username");
row.createCell(1).setCellValue("Password");

FileOutputStream fos = new FileOutputStream("output.xlsx");
workbook.write(fos);

fos.close();
workbook.close();
```

***

✅ Done — only syntax as requested 👍


✅ If you want next, I can show:

* **Real framework example with browser parameterization (Chrome/Edge) 🔥**
* OR **Excel-driven parameterization (most asked in interviews)**


