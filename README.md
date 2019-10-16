# zhihu_spdier-
实现自动登陆知乎

from selenium import webdriver

from selenium.webdriver.chrome.options import Options

import time

chrome_options = Options()

chrome_options.add_experimental_option("debuggerAddress", "127.0.0.1:9222")


browser = webdriver.Chrome(executable_path="C:\chromedriver.exe")
#browser = webdriver.Chrome(chrome_options=chrome_options)

browser.get("https://www.zhihu.com/signin?next=%2F")


time.sleep(3)


password_login = browser.find_element_by_xpath(".//div[@class='SignFlow-tab']")
password_login.click()
phone = browser.find_element_by_xpath(".//input[@name='username']")
password = browser.find_element_by_xpath(".//input[@name='password']")

phone.send_keys("知乎账号")

password.send_keys("知乎密码")

login = browser.find_element_by_xpath(".//button[@class='Button SignFlow-submitButton Button--primary Button--blue']")
login.click()




