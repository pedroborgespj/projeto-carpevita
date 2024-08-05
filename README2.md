# Project README: Robot Framework + Selenium WebDriver

## Table of Contents

1. [Introduction](#introduction)
2. [Robot Framework Basics](#robot-framework-basics)
3. [Selenium WebDriver](#selenium-webdriver)
4. [Page Objects](#page-objects)
5. [Project Structure](#project-structure)
6. [Setup Instructions](#setup-instructions)
7. [Running the Tests](#running-the-tests)
8. [Generating the Report](#generating-the-report)
9. [Contributing](#contributing)
10. [License](#license)

---

## Introduction

This project utilizes Robot Framework and Selenium WebDriver to perform automated test cases on web applications. The results of these tests are then processed to generate an Excel file containing detailed data on the test case actions, time spent for each test case, and averages.

## Robot Framework Basics

**Robot Framework** is a generic open-source automation framework for acceptance testing, acceptance test-driven development (ATDD), and robotic process automation (RPA).

### Key Concepts

- **Test Suite**: A collection of test cases.
- **Test Case**: A single unit of testing.
- **Keyword**: Reusable functions that represent actions to be performed in the tests.
- **Variables**: Store values to be used in the test cases and keywords.

### Example Test Case

```robot
*** Settings ***
Library           SeleniumLibrary

*** Variables ***
${URL}            http://example.com
${BROWSER}        Chrome

*** Test Cases ***
Example Test Case
    Open Browser    ${URL}    ${BROWSER}
    Click Element   id=example-id
    [Teardown]      Close Browser
```
## Selenium WebDriver

**Selenium WebDriver** is a web automation tool that allows you to programmatically control a web browser. It is widely used for browser automation and testing purposes.

### Basic Selenium Commands

- **Open Browser**: Opens a new browser instance.
- **Click Element**: Clicks an element on the webpage.
- **Input Text**: Inputs text into a text field.
- **Close Browser**: Closes the browser instance.

## Page Objects

The **Page Object Model (POM)** is a design pattern that enhances test maintenance and reduces code duplication by encapsulating web page elements and actions in separate classes.

## Project Structure

```plaintext
project-folder/
├── tests/
│   └── example_test.robot
├── pages/
│   └── login_page.py
├── resources/
│   └── keywords.robot
├── scripts/
│   └── report_generator.py
├── output/
│   └── output.xml
├── README.md
└── requirements.txt
```

## Setup Instructions

### Install Python

Download and install Python from [python.org](https://www.python.org/downloads/).

### Install Robot Framework and Selenium Library

Open a terminal and run the following commands:

```bash
pip install robotframework
pip install robotframework-seleniumlibrary
pip install pandas
pip install openpyxl
```

## Running the Tests

To run the test cases, navigate to the project directory and execute:

```bash
robot tests/example_test.robot
```

## Generating the Report

After running the tests, use the provided script to generate an Excel report from the output XML:

```bash
python scripts/report_generator.py output/output.xml output/report.xlsx
```

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a pull request.
