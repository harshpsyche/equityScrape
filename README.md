# equityScrape
Backend Hosted on: abhaya.pythonanywhere.com

Python Version: `3.6`

Django Version: `3.2`
## Python modules required
For django app
```
django
djangorestframework
django-cors-headers
redislite
redis
```
For scraping:
```
bs4
pandas
```
Installed using:
```
pip install requirements.txt
```


NB: redislite is available on a linux system only. 

## Utility files

`dailyJob.py`

    The above file was scheduled as a cron job to run everyday at 18:00 IST on pythonanywhere.com. 

However, it is a free account.
Thus, the url (https://www.bseindia.com/markets/MarketInfo/BhavCopy.aspx
) is not on pythonanywhere's whitelist and hence forbidden from access.

As a workaround for proof of concept:

`uploadfromcsv.py`

    This file loads data from wholedownload.csv and stores it in the redis server at location: "/home/abhaya/redis.db".

## API List

`GET https://abhaya.pythonanywhere.com/downloadW/`

    Download the entire day's data as a csv file.

`GET https://abhaya.pythonanywhere.com/search/?search=<keyword>`
    
    Get JSON response for the sought keyword.

`GET https://abhaya.pythonanywhere.com/downloadC/?search=<keyword>`
    
    Generate a CSV file named: result_<keyword>.csv for the user to download.


