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

***

✅ If you want next, I can convert this into:

* **Interview cheat sheet PDF**
* OR **diagram (flowchart) for easy understanding**
