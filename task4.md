# Задание 4

import time
import requests
from bs4 import BeautifulSoup

while True:
    r = requests.get('https://habr.com/ru/all/')
    s = BeautifulSoup(r.text, 'lxml')
    for n, title in enumerate(s.find_all('a', {'class':'post__title_link'})):
        print(str(n+1) + '. ' + title.text + '\n' + title.attrs['href'] + '\n')
    time.sleep(300)
    
    
[Вернуться](index.md)
