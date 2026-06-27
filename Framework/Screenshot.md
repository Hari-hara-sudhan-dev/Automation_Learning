In **Selenium**, screenshots can be taken in different ways depending on what you want to capture. Here are the **main types of screenshots**:

***

# ✅ 1. Full Page Screenshot

Captures the entire visible browser window.

### ✔ Example:

```java
File src = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
```

### ✔ Use Case:

* Capture entire page (visible area)
* Debug UI issues

***

# ✅ 2. Element Screenshot

Captures only a specific web element (button, image, form, etc.).

### ✔ Example:

```java
WebElement element = driver.findElement(By.id("logo"));
File src = element.getScreenshotAs(OutputType.FILE);
```

### ✔ Use Case:

* Validate UI components
* Capture logos, input fields, buttons

***

# ✅ 3. Full Page (Scrolling Screenshot)

Captures the **entire webpage including scrollable content** (beyond visible screen).

### ✔ Tools:

* Selenium 4 (Chrome DevTools)
* AShot library

### ✔ Example (AShot):

```java
Screenshot screenshot = new AShot()
        .shootingStrategy(ShootingStrategies.viewportPasting(100))
        .takeScreenshot(driver);
```

### ✔ Use Case:

* Long pages (e.g., reports, dashboards)

***

# ✅ 4. Screenshot on Test Failure

Automatically captures screenshot when test fails.

### ✔ Example:

```java
@AfterMethod
public void captureFailure(ITestResult result) {
    if (result.getStatus() == ITestResult.FAILURE) {
        File src = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
    }
}
```

### ✔ Use Case:

* Debug failed test cases
* Reporting

***

