
You can click the Preview link to take a look at your changes.
--->
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import time

# Set the path to your Chrome driver
chrome_driver_path = 'path/to/your/chromedriver'

# Set your Facebook username and password
username = 'your_facebook_username'
password = 'your_facebook_password'

# URL of the Facebook page you want to like
page_url = 'https://www.facebook.com/your_page_url'

# Initialize Chrome driver
driver = webdriver.Chrome(chrome_driver_path)

# Open Facebook login page
driver.get("https://www.facebook.com")

# Wait for the login page to load
time.sleep(2)

# Find the username and password input fields and fill them
username_field = driver.find_element_by_id("email")
username_field.send_keys(username)

password_field = driver.find_element_by_id("pass")
password_field.send_keys(password)

# Click on the login button
login_button = driver.find_element_by_id("loginbutton")
login_button.click()

# Wait for the home page to load after login
time.sleep(5)

# Go to the Facebook page you want to like
driver.get(page_url)

# Wait for the page to load
time.sleep(3)

# Find the like button and click it
like_button = driver.find_element_by_xpath("//div[@aria-label='Like']")
like_button.click()

# Close the browser
driver.quit()
