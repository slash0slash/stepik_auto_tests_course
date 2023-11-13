# stepik_auto_tests_course
it's my homework for course


>>> import time
>>> import math
>>> from selenium import webdriver
>>> from selenium.webdriver.common.by import By
>>> from selenium.webdriver.support.ui import WebDriverWait
>>> from selenium.webdriver.support import expected_conditions as EC
>>> driver = webdriver.Chrome()
>>> link = "https://suninjuly.github.io/explicit_wait2.html"
>>> try:
...     driver.get(link)
...     price = WebDriverWait(driver, 12).until(
...         EC.text_to_be_present_in_element((By.ID, "price"), "100")
...     )
...     button = driver.find_element(By.CSS_SELECTOR, 'button#book.btn.btn-primary')
... finally:
...     button.click()
...     button1 = driver.find_element(By.CSS_SELECTOR, 'button#solve.btn.btn-primary')
...     driver.execute_script("return arguments[0].scrollIntoView(true);", button1)
...     num = driver.find_element(By.CSS_SELECTOR, 'span#input_value.nowrap')
...     x = num.text
...     def calc(x):
...         return str(math.log(abs(12*math.sin(int(x)))))
...     y = calc(x)
...     input = driver.find_element(By.CSS_SELECTOR, 'input#answer.form-control')
...     input.send_keys(y)
...     button2 = driver.find_element(By.CSS_SELECTOR, 'button#solve.btn.btn-primary')
...     button2.click()