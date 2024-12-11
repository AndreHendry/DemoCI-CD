Web Automation Project

Overview

This project is a test automation framework built using Java, Selenium, and Cucumber. It is designed for automating web applications, focusing on login workflows and cart functionality, using the SauceDemo demo website.

The framework uses the Page Object Model (POM) design pattern, ensuring modularity and maintainability. It includes:

Gradle for build automation.

JUnit 5 as the testing framework.

Cucumber for Behavior-Driven Development (BDD).

WebDriverManager for managing browser drivers.

Features

Modular structure for easy test maintenance.

Hooks for pre-test setup and post-test teardown.

Utility functions for common tasks like WebDriver initialization and random data generation.

Cucumber step definitions mapped to feature files.

Custom assertions using AssertJ.

Prerequisites

Ensure you have the following installed:

Java 11 or higher

Gradle 7.x or higher

IDE like IntelliJ IDEA or Eclipse

Project Structure

├── src
│   ├── main
│   │   └── java
│   │       └── helper
│   │           └── Utility.java  # Contains reusable helper methods
│   └── test
│       ├── java
│       │   ├── stepDef
│       │   │   ├── Hooks.java   # Test setup and teardown
│       │   │   └── WebStep.java # Step definitions
│       │   └── pages
│       │       └── WebPage.java # Page Object Model implementation
│       └── resources
│           └── features
│               └── Login.feature  # Feature files
├── build.gradle                  # Gradle build script
└── README.md                     # Project documentation

Setup Instructions

Clone the repository:

git clone <repository-url>

Navigate to the project directory:

cd web-automation-project

Build the project:

gradle build

Running Tests

Run All Tests

gradle test

Run API Tests Only

gradle apiTest

Run Tests with Specific Tags

gradle test -Dcucumber.filter.tags="@web"

Key Components

build.gradle

Defines the dependencies and tasks for the project, including Cucumber and Selenium integrations.

Hooks.java

Manages test setup and teardown logic, such as initializing and quitting the WebDriver.

Utility.java

Provides helper methods for tasks like:

Launching WebDriver.

Generating random test data.

Accessing JSON schema files.

WebPage.java

Encapsulates web page interactions, implementing the Page Object Model (POM). Includes methods for actions like:

Logging in.

Adding items to the cart.

Validating elements on the page.

Feature Files

Written in Gherkin syntax, defining test scenarios for:

Login workflows.

Cart functionality.

WebStep.java

Maps Gherkin steps from feature files to Java methods, interacting with WebPage.

Sample Scenario

Feature: Test Automation Web

@web
Scenario: Test login web normal
Given open web login page
And user input username "standard_user"
And user input password "secret_sauce"
And user click login button
And user will see icon cart in homepage

Dependencies

Selenium: Browser automation.

Cucumber: BDD framework.

JUnit 5: Testing framework.

WebDriverManager: Manages browser drivers.

AssertJ: Fluent assertions.

Custom Tasks

apiTest

Runs API-specific tests and generates a Cucumber HTML report.

gradle apiTest

Reporting

Cucumber generates an HTML report for executed scenarios, saved in the report/ directory.

Future Enhancements

Add cross-browser testing support.

Integrate CI/CD pipelines (e.g., Jenkins, GitHub Actions).

Add support for data-driven testing using external data sources.

Contributing

Fork the repository.

Create a feature branch:

git checkout -b feature/new-feature

Commit your changes:

git commit -m "Add new feature"

Push the branch:

git push origin feature/new-feature

Open a pull request.