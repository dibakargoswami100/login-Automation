# Login-Automation Using Python Selenium

This project demonstrates how to automate the login process for a demo website using Python and Selenium. It includes the use of the [SauceDemo](https://www.saucedemo.com/) website for testing and [SelectorsHub](https://selectorshub.com/) for inspecting and validating web elements.

## Table of Contents

https://github.com/user-attachments/assets/971865f2-d9e6-4b02-a172-2d577b97a709



- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

## Introduction

This project showcases a simple automation script that performs the following tasks:
1. Opens a Firefox browser.
2. Navigates to the SauceDemo login page.
3. Inputs a predefined username and password.
4. Clicks the login button.
5. Verifies that the login is successful by checking the presence of a specific element on the page.

## Features

- Automated login process using Selenium WebDriver.
- Verification of successful login.
- Use of SelectorsHub for easy and accurate selection of web elements.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.x installed on your machine. You can download it [here](https://www.python.org/downloads/).
- `pip` (Python package installer) installed.
- Mozilla Firefox browser installed.
- GeckoDriver installed. You can download it [here](https://github.com/mozilla/geckodriver/releases).

## Installation

1. Clone this repository to your local machine:

    ```sh
    git clone https://github.com/your-username/login-automation.git
    ```

2. Navigate to the project directory:

    ```sh
    cd login-automation
    ```

3. Install the required Python packages:

    ```sh
    pip install -r requirements.txt
    ```

## Usage

1. Open the project directory and locate the script file.

2. Run the script:

    ```sh
    python login_automation.py
    ```

3. The script will launch a Firefox browser, navigate to the SauceDemo login page, and perform the login process automatically.

### Script Details

Here is a brief explanation of the script:

```python
from selenium import webdriver
from selenium.webdriver.common.by import By

# Initialize the Firefox browser
driver = webdriver.Firefox()
driver.maximize_window()

# Set login credentials
username = "standard_user"
password = "secret_sauce"
login_url = "https://www.saucedemo.com/"

# Navigate to the login page
driver.get(login_url)

# Find the username and password fields and input the credentials
username_field = driver.find_element(By.ID, value="user-name")
password_field = driver.find_element(By.ID, value="password")
username_field.send_keys(username)
password_field.send_keys(password)

# Find and click the login button
login_button = driver.find_element(By.ID, value="login-button")
assert not login_button.get_attribute("disabled")
login_button.click()

# Verify successful login
success_element = driver.find_element(By.CSS_SELECTOR, value=".title")
assert success_element.text == "Products"

# Close the browser
driver.quit()
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
