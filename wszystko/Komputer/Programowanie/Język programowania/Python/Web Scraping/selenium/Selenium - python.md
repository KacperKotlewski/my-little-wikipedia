# Selenium [[Python]]
selenium jest technologią wykorzystującą [[Web driver]]'y aby automatycznie przechodzić po stronach tak jak programista nakarze


## użycie
W pierwszej kolejności zaimportuj [[Web driver]] z selenium:
```py
from selenium import webdriver
```

następnie wybierz [[Web driver]]:

- [**Firefox**]() 

> ```py
> browser = webdriver.Firefox(path, options, desired_capabilities)
> ```

> [download](https://github.com/mozilla/geckodriver/releases)
> 
> [[firefox driver options|options]]

- [**Chrome**]() 

> ```py
> browser = webdriver.Chrome(path, options, desired_capabilities)
> ```

> [download](https://chromedriver.chromium.org/downloads)
> 
> [[selenium -chrome - options|otions]]
> 
>[[get_driver()|przykładowa implementacja]]
