Here’s a comprehensive overview and folder structure for a modern Cucumber BDD Selenium automation framework, following your requirements. This can be used in your README.md and as project guidance.

---

# BDD Selenium Framework

A modern **Cucumber-based BDD Selenium Automation Framework** using Java, Maven, and best practices for scalable UI test automation.

---

## 📁 Folder Structure

```plaintext
bdd-selenium-framework/
├── .github/
│   └── workflows/
│       └── ci.yml                # GitHub Actions CI Pipeline
├── downloads/                    # File download storage
├── logs/                         # Log4j log files
├── reports/                      # Allure or ExtentReports
├── screenshots/                  # Failure screenshots
├── src/
│   ├── main/
│   │   └── java/
│   │       ├── base/
│   │       │   └── BaseTest.java
│   │       ├── config/
│   │       │   ├── ConfigReader.java
│   │       │   └── ConfigModel.java
│   │       ├── drivers/
│   │       │   └── DriverFactory.java
│   │       ├── pages/
│   │       │   └── LoginPage.java
│   │       └── utils/
│   │           ├── LoggerHelper.java
│   │           ├── FileUtil.java
│   │           ├── ExcelUtil.java
│   │           └── PDFUtil.java
│   └── test/
│       ├── java/
│       │   ├── hooks/
│       │   │   └── Hooks.java
│       │   ├── runners/
│       │   │   └── TestRunner.java
│       │   ├── stepDefinitions/
│       │   │   └── LoginSteps.java
│       │   └── assertions/
│       │       └── SoftAssertions.java
│       └── resources/
│           ├── config/
│           │   ├── config.yaml
│           │   └── log4j2.xml
│           ├── features/
│           │   └── login.feature
│           └── testdata/
│               ├── loginData.xlsx
│               └── sample.xml
├── pom.xml                      # Maven config
├── testng.xml                   # Optional
└── README.md                    # Setup + Usage Docs
```

---

## 🚀 Key Features

- **Cucumber BDD**: Write readable Gherkin syntax for features and scenarios.
- **Selenium WebDriver**: Automate browser interactions.
- **Maven Managed**: Easy build and dependency management.
- **Extensible Page Object Model**: Clean separation of page logic.
- **Hooks & Runners**: Customizable test lifecycle.
- **Allure/Extent Reporting**: Visual, actionable test reports.
- **Log4j Logging**: Centralized and configurable logging.
- **Reusable Utilities**: File, Excel, PDF, and logging helpers.
- **Cloud Ready**: Integrate with SauceLabs, BrowserStack, etc.
- **CI/CD**: Ready for GitHub Actions or other CI tools.

---

## 🛠️ Required Dependencies

Add to your `pom.xml` (sample for core):

```xml
<dependencies>
    <!-- Cucumber Java -->
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-java</artifactId>
        <version>7.14.0</version>
    </dependency>
    <!-- Cucumber JUnit -->
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-junit</artifactId>
        <version>7.14.0</version>
        <scope>test</scope>
    </dependency>
    <!-- Selenium Java -->
    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>4.20.0</version>
    </dependency>
    <!-- Log4j2 -->
    <dependency>
        <groupId>org.apache.logging.log4j</groupId>
        <artifactId>log4j-core</artifactId>
        <version>2.23.1</version>
    </dependency>
    <!-- Allure or ExtentReports -->
    <!-- Add one as needed -->
    <!-- ... other dependencies ... -->
</dependencies>
```

> 💡 Adjust versions as per latest releases.

---

## 📝 Example Feature File

**src/test/resources/features/login.feature**
```gherkin
Feature: Login functionality

  Scenario: Successful login with valid credentials
    Given I am on the login page
    When I enter username "user1" and password "pass1"
    Then I should see the dashboard
```

---

## 🏃‍♂️ Running Tests

From project root:

- Run all tests (default browser):  
  ```
  mvn test
  ```

- Run on a specific browser:  
  ```
  mvn test -Dbrowser=chrome
  ```

- Generate Allure Report:  
  ```
  mvn allure:serve
  ```

---

## 🏗️ Adding New Features

1. Add `.feature` files in `src/test/resources/features/`
2. Implement Step Definitions in `src/test/java/stepDefinitions/`
3. Add Page Objects in `src/main/java/pages/`
4. Customize runners in `src/test/java/runners/`

---

## 📄 License

MIT License. See [LICENSE](LICENSE) for details.

---

**Start automating your web apps with robust, maintainable, and scalable BDD tests!**
