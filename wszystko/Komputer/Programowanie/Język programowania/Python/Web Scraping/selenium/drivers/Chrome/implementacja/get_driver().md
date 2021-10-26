# przykładowa implementacja chrome w [[Selenium - python]]
```py
from selenium import webdriver

def get_driver(): 
 options = webdriver.ChromeOptions()
 options.add_argument('--ignore-certificate-errors')
 options.add_argument('--incognito')
 options.add_argument("--window-size=800,600")
 options.add_argument("--remote-debugging-port=8000")
 
 dev_tools = pychrome.Browser(url="http://localhost:8000")
 path_to_chrome = r"D:\__path_programs\web_drivers\chromedriver"
 driver = webdriver.Chrome(path_to_chrome, options=options)
 
 return driver, dev_tools
 ```
 
 
## szczegóły:
> [[selenium -chrome - options|options]]

