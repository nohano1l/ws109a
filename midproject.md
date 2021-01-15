## 爬蟲
* picture
![爬蟲結果](https://raw.githubusercontent.com/nohano1l/ws109a/master/1.png)
* code1
```
import requests
from bs4 import BeautifulSoup
url = 'https://travel.ettoday.net/category/%E6%A1%83%E5%9C%92/'
r = requests.get(url)
sp = BeautifulSoup(r.text,'html.parser')
titles = sp.find_all("h3", itemprop="headline")
for title in titles:
    print(title.select_one("a").getText())
```
* code2
```
import json
with open('homework.json',mode='r',encoding='UTF-8')as file:
    a=json.load(file)
for item in a:
    print("威力彩期數:" + item['威力彩期數:'] + " 第幾期:" + item['第幾期'] + " 開出順序:" + item['開出順序:'] + " 大小順序:" + item['大小順序:'] + " 第幾區:" + item['第幾區'])
```
