{\rtf1\ansi\ansicpg1251\cocoartf2708
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww28600\viewh14900\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 >>> import time\
>>> import math\
>>> from selenium import webdriver\
>>> from selenium.webdriver.common.by import By\
>>> from selenium.webdriver.support.ui import WebDriverWait\
>>> from selenium.webdriver.support import expected_conditions as EC\
>>> driver = webdriver.Chrome()\
>>> link = "https://suninjuly.github.io/explicit_wait2.html"\
>>> try:\
...     driver.get(link)\
...     price = WebDriverWait(driver, 12).until(\
...         EC.text_to_be_present_in_element((By.ID, "price"), "100")\
...     )\
...     button = driver.find_element(By.CSS_SELECTOR, 'button#book.btn.btn-primary')\
... finally:\
...     button.click()\
...     button1 = driver.find_element(By.CSS_SELECTOR, 'button#solve.btn.btn-primary')\
...     driver.execute_script("return arguments[0].scrollIntoView(true);", button1)\
...     num = driver.find_element(By.CSS_SELECTOR, 'span#input_value.nowrap')\
...     x = num.text\
...     def calc(x):\
...         return str(math.log(abs(12*math.sin(int(x)))))\
...     y = calc(x)\
...     input = driver.find_element(By.CSS_SELECTOR, 'input#answer.form-control')\
...     input.send_keys(y)\
...     button2 = driver.find_element(By.CSS_SELECTOR, 'button#solve.btn.btn-primary')\
...     button2.click()}