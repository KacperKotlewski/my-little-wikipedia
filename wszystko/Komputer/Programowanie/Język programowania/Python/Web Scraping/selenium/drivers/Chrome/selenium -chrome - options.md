# opcje w chrome [[Selenium - python|selenium]]

inicjalizacja opcji:
```py
options = webdriver.ChromeOptions()
```

dodawanie [[#argumenty|argumentów]]:
```py
options.add_argument(your_argument)
```

dodawanie [[#argumenty experymentalne|argumentów eksperymentalnych]]:
```py
options.add_experimental_option(your_argument, value)
```

## argumenty:
- ``--ignore-certificate-errors`` - ignoruje jeżeli certyfikaty się nie zgadzają
- ``--incognito`` - otwiera przeglądarkę w incognito
- ``--window-size=800,600`` - ustawia konkretną wielkość okna
- ``start-maximized`` - wypełnia ekran
- ``--auto-open-devtools-for-tabs`` - otwiera dev tools'y (f12)
- ``--remote-debugging-port=8000`` - utworzenie portu pozwalającego na kontrole i debbuging
- ``--headless`` - otwiera się w tle (nie ma jej nawet na pasku zadań, tylko w procesach)

## argumenty experymentalne:
- ``excludeSwitches``
	- ``["enable-automation"]``
- ``useAutomationExtension``
	- True/False