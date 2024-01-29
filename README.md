About Selenium: 

Selenium is a set of tools for automating software testing in web applications. With it, we can simulate user actions in interaction with the browser. The main idea is to ensure that these applications are behaving as expected. Initial studies involve basic tasks such as interacting with page elements, locating elements through selectors, navigating between pages, and performing simple checks.

The Task:

The script involves automating the process of accepting 'cookies' on the "Petz" page. In addition to locating the element through a CSS selector, it performs the click action.

Objectives:

- Basic understanding of the tool;
- Visual feedback;
- Correct use of methods and classes syntax.

Challenges: 

The page experiences slow loading, causing delays in the display of elements, and elements appear dynamically—meaning they are added or modified after the initial load. Locating and executing the click action becomes challenging. 

We encapsulated the logic of waiting and retrieving the element in the 'wait_and_get_element' function. This function utilizes 'WebDriverWait' to wait until the element is present on the page before proceeding, ensuring that interactions occur at the appropriate time, even during extended loading times.

Tools:

- Selenium
- Jupyter Notebook (Anaconda)
- Python

Step by Step:

Importing modules and classes from Selenium:

```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.action_chains import ActionChains
from selenium.common.exceptions import TimeoutException
```

1. **PetzPage Class:**
   - We create a class called `PetzPage`.
   - This class stores attributes and methods related to interacting with the web page.
2. **Constructor Method:**
   - The class has a constructor method `__init__` that is automatically executed when an object of the class is created.
   - The constructor receives a `driver` parameter, representing the web browser object to be used for interaction.
3. **aceitar_cookies Method:**
   - Inside the class, there is the `aceitar_cookies` method.
   - This method is responsible for accepting cookies on the web page.
4. **Flow of the aceitar_cookies Method:**
   - The method looks for the cookies element using the `By.ID` locator with the value `'onetrust-accept-btn-handler'`.
   - We use the `wait_and_get_element` method defined in the `PetzPage` class to wait until the element identified by `cookies_aparece_localiza` is present on the page.
   - The method uses the `WebDriverWait` function from Selenium to wait for the presence of the element before proceeding.
   - If the element is found, it uses `ActionChains` to scroll to the element.
   - Next, it searches for the accept cookies button again and, if found, performs a click using `ActionChains`.