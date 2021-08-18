---
layout: post
read_time: true
show_date: true
title: "Python Crawler Exercise-Manga files of bilibili"
date:   2021-08-06 12:32:20 -0600
description: Using 
img: posts/20210806/cover.png
tags: [python, crawler]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
Recently, I bought some manga from Bilibili, which is the biggest manga website in China. However, after reading the whole pages, I noticed that, I can view all the pages but I can not download these images which disappointed me. You know that feeling right? When you buy something, even if you use it, edit it, but it never ever belong to you own belongings. You even can not read it off-line which was so bad. I hate this feeling. Therefore, can we use some programming to get these manga images?

The answer is yes, of course! By using crawler, you can get what you want. However, it is undeniable that, you can not share what you obtain by running crawler, and can not sell it commercially. Do not forget IP protection!

### So what is Crawler?

According to the defination of Wiki, a crawler is a program that visits Web sites and reads their pages and other information in order to create entries for a search engine index.Crawlers apparently gained the name because they crawl through a site a page at a time, following the links to other pages on the site until all pages have been read. 

For python crawler, we should use the package  `requests`,so we install the package at first.
```
pip install requests
```
The following codes are an example try to illustrate the whole process.
```javascript
import requests
from lxml import html
url='https://movie.douban.com/' #website you want to crawl
page=requests.Session().get(url) 
tree=html.fromstring(page.text) 
result=tree.xpath('//td[@class="title"]//a/text()') #data requires to obtain
 print(result)
```
The following is result after running.
```
['看不见的客人',
 '斯隆女士',
 '美女与野兽',
 '契克',
 '分裂',
 '莎士比亚外传',
 '八月',
 '休斯顿，我们有麻烦了！',
 '古城一线牵',
 '被操纵的城市']
 ```
This example is the easiest one to understand for noob programmer just like me. So before crawling, we first should make two simple points:
1. The URL of the crawler.
2. The content(data) that needs to be crawled

The first step, the crawler's URL, in this example, we used Douban. I don't know why people so like Douban that it always suffers crawler by multiple programmers no matter old man or noob.

The second part is the content (data) that needs to be crawled.
It may also be the most difficult place for novices. This part of the code is to get the data.

`'//td[@class="title"]//a/text()'`
So how to get the this?

The first step: Access the website you want to crawl.
The second step: Press F12 on keyboard or use the hot key ctrl+shift+I (Chrome explorer) to enter the Developer mode.

![image](.\assets\img\posts\20210806\douban.jpg)

Then you can find some codes, most of them are HTML language.

![image](.\assets\img\posts\20210806\press.jpg)
Then we will find this button, that can select an element in the page to inspect it.
![image](.\assets\img\posts\20210806\xinshiji.jpg)
I chose one of the movie and click it, them we can see the specific information and codes there. This button can location the codes of element automatically.
So in this picture, we can see the `<td>`and `</td>` which is familiar with our codes in example.

in this code,`//Td[@class=”title”]//a/text()`

//td:  is equivalent to specifying a large directory;
[@class=”title”]:  is equivalent to the designated small directory;
//a: is equivalent to the smallest directory;
/text(): is to extract the data.
Therefore, for the image following,
![image](.\assets\img\posts\20210806\li.jpg)

we can use `result=tree.xpath('//li[@class="title"]//a/text()')`

### Manga exercise
Now we know how to crawl the page, so we can try another website. At that time, I turned my eyes to Tencent, which is a famous manga website in China.
By using the method mentioned above, I can find the location of images in HTML. 

![image](.\assets\img\posts\20210806\tecent.jpg)

```javascript
import requests
from lxml import etree
from selenium import webdriver
from time import sleep
from bs4 import BeautifulSoup
from selenium.webdriver.chrome.options import Options
import os

download_path = './manhua'
#Access Tencent Manga
url = 'https://ac.qq.com/'
#send request to web
data = requests.get(url).text
#change the format to xpath which can be recognised
html = etree.HTML(data)
#extract the address for every manga
comic_list = html.xpath('//a[@class="in-rank-name"]/@href')
print(comic_list)
#Traverse the extracted information
for comic in comic_list:
    #拼接成为漫画目录页的网址
    comic_url = url + str(comic)
    #从漫画目录页提取信息
    url_data = requests.get(comic_url).text
    #准备用xpath语法提取信息
    data_comic = etree.HTML(url_data)
    #提取漫画名--text（）为提取文本内容
    name_comic = data_comic.xpath("//h2[@class='works-intro-title ui-left']/strong/text()")
    #Extract address of every page
    item_list = data_comic.xpath("//span[@class='works-chapter-item']/a/@href")
    print(name_comic)
    print(item_list)
    #Create files using the name of manga
    os.makedirs('comic/' + str(name_comic))
    #将一本漫画的每一章地址遍历
    for item in item_list:
        #拼接每一章节的地址
        item_url = url + str(item)
        print(item_url)
        #请求每一章节的信息
        page_mes = requests.get(item_url).text
        #准备使用xpath提取内容
        page_ming = etree.HTML(page_mes)
        #extract chapter name
        page_name = page_ming.xpath('//span[@class="title-comicHeading"]/text()')
        print(page_name)
        #再以章节名命名一个文件夹
        os.makedirs('comic/' + str(name_comic) + '/' + str(page_name))


        #设置谷歌无界面浏览器
        chrome_options = Options()
        chrome_options.add_argument('--headless')
        chrome_options.add_argument('--disable-gpu')
        #webdriver位置
        path = r'/home/jmhao/chromedriver'
        #浏览器参数设置
        browser = webdriver.Chrome(executable_path=path, options=chrome_options)
        #开始请求第一个章节的网址
        browser.get(item_url)
        #设置延时,为后续做缓冲
        sleep(2)
        browser.get_screenshot_as_file(str(page_name) + ".png")
        #尝试执行下列代码
        try:
            #设置自动下滑滚动条操作
            for i in range(1, 100):
                #滑动距离设置
                js = 'var q=document.getElementById("mainView").scrollTop = ' + str(i * 1000)
                #执行滑动选项
                browser.execute_script(js)
                #延时,使图片充分加载
                sleep(2)
            sleep(2)
            #将打开的界面截图保存,证明无界面浏览器确实打开了网页
            browser.get_screenshot_as_file(str(page_name) + ".png")
            #获取当前页面源码
            data = browser.page_source
            #在当前文件夹下创建html文件,并将网页源码写入
            fh = open("dongman.html", "w", encoding="utf-8")
            #写入操作
            fh.write(data)
            #关掉无界面浏览器
            fh.close()

            #下面的操作为打开保存的html文件,提取其中的图片信息,并保存到文件夹中

            #用beautifulsoup打开本地文件
            html_new = BeautifulSoup(open('dongman.html', encoding='utf-8'), features='html.parser')
            #提取html文件中的主体部分
            soup = html_new.find(id="mainView")
            #设置变量i,方便为保存的图片命名
            i = 0
            #提取出主体部分中的img标签（因为图片地址保存在img标签中）
            for items in soup.find_all("img"):
                #提取图片地址信息
                item = items.get("src")
                #请求图片地址
                comic_pic = requests.get(item).content
                #print(comic_pic)
                #尝试提取图片,若发生错误则跳过
                try:
                    #打开文件夹,将图片存入
                    with open('comic/' + str(name_comic) + '/' + str(page_name) + '/' + str(i + 1) + '.jpg', 'wb') as f:
                        print('正在下载第 ', (i + 1), ' 张图片中')
                        print('正在下载' , str(name_comic) , '-' , str(page_name) , '- 第' , (i+1) , '张图片')
                        #写入操作
                        f.write(comic_pic)
                        #更改图片名,防止新下载的图片覆盖原图片
                        i += 1
                #若上述代码执行报错,则执行此部分代码
                except Exception as err:
                    #跳过错误代码
                    pass
        # 若上述代码执行报错（大概率是由于付费漫画）,则执行此部分代码
        except Exception as err:
            #跳过错误代码
            pass

```
When I tried to run this program, I encountered an error. PyCharm told me:`selenium.common.exceptions.WebDriverException: Message: 'chromedriver' executable needs to be in PATH.` So I searched on google to sovle the problem.

According some authors blog, I found one recorded the [answer](https://blog.csdn.net/weixin_37185329/article/details/80493281).

1. First, I need to download Chromedriver. After downloading, I will get a chromedriver.exe file.
2. Copy `chromedriver.exe` to the Google browser directory (such as C:\Program Files\Google\Chrome\Application) and the python root directory (C:\Python27).
3. Add the Google Chrome environment variable to the path (C:\Users\HD003\AppData\Local\Google\Chrome\Application).

Actually, to my disappointed, after I followed these steps above, this problem still occured. However, it really worked. You can see the file in the python path, which means we did extract some information from website. As for this error, may be because Tencent had some methods to avoid the crawler so we can not just easily using this methods to extract what we want.

Another case was Bilibili, which is the biggest manga website in China.
And it is much more complicated. Asynchronous loading means we can not obtain all the source if we do not view all the pages of manga, which is a method to avoid crawler.

![image](.\assets\img\posts\20210806\01.jpg)
Only when I turn page, images can be loaded successfully. So we need set time delay.
Now I want to show the codes that can successfully run and extract the manga.

```javascript
import os
import time

import requests
import json
from pprint import pprint
from index_decode import decode_index_data

download_path = './manhua'
headers = {
    "accept": "application/json, text/plain, */*",
    "accept-language": "zh-CN,zh;q=0.9,en;q=0.8",
    "content-type": "application/json;charset=UTF-8",
    "origin": "https://manga.bilibili.com",
    "user-agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.61 Safari/537.36",
    "cookie":"_uuid=B600653B-3070-7339-BEC3-85640D98D0EB79635infoc; buvid3=115B671D-DF80-4536-BB55-2BBAE2E277A6143088infoc; buivd_fp=115B671D-DF80-4536-BB55-2BBAE2E277A6143088infoc; buvid_fp_plain=115B671D-DF80-4536-BB55-2BBAE2E277A6143088infoc; PVID=1; CURRENT_FNVAL=80; blackside_state=1; rpdid=|(JRu))uYkRR0J'uY|mkluuYl; buvid_fp=115B671D-DF80-4536-BB55-2BBAE2E277A6143088infoc; bili_jct=a240c8a62ae83f46df6eeb4d8854264e; DedeUserID=6497541; DedeUserID__ckMd5=08096d56cfab7760; sid=iygtl40h; CURRENT_QUALITY=0; bp_video_offset_6497541=550214967374380852; bp_t_offset_6497541=550215688926794143; fingerprint3=5774ab3c82ed4bec8474967f60f94bdd; fingerprint=e04d479b6e9900d85dff01f253b6e2bd; fingerprint_s=ba6a9b82a54cc0df8c22656e5a770eff; Hm_lvt_6ab26a3edfb92b96f655b43a89b9ca70=1627036768,1627041627,1628354183; Hm_lvt_a69e400ba5d439df060bf330cd092c0d=1627036768,1627041627,1628354183; Hm_lpvt_6ab26a3edfb92b96f655b43a89b9ca70=1628354193; Hm_lpvt_a69e400ba5d439df060bf330cd092c0d=1628356978"
}
headers_cdn = {
    'Host': 'manga.hdslb.com',
    'Origin': 'https://manga.bilibili.com',
}


def download_manga_all(comic_id: int):
    url = "https://manga.bilibili.com/twirp/comic.v2.Comic/ComicDetail?device=pc&platform=web"
    res = requests.post(url,
                        json.dumps({
                            "comic_id": comic_id
                        }), headers=headers)
    data = json.loads(res.text)['data']
    comic_title = data['title']
    root_path = os.path.join(download_path, comic_title)
    if not os.path.exists(root_path):
        os.makedirs(root_path)
    for ep in data['ep_list']:
        if not ep['is_locked']:
            print('downloading ep:', ep['short_title'], ep['title'])
            download_manga_episode(ep['id'], root_path)
            pass
        pass
    pass


def download_manga_episode(episode_id: int, root_path: str):
    res = requests.post('https://manga.bilibili.com/twirp/comic.v1.Comic/GetEpisode?device=pc&platform=web',
                        json.dumps({
                            "id": episode_id
                        }), headers=headers)
    data = json.loads(res.text)
    # comic_title = data['data']['comic_title']
    short_title = data['data']['short_title']
    # title = comic_title + '_' + short_title + '_' + data['data']['title']
    title = short_title + '_' + data['data']['title']
    comic_id = data['data']['comic_id']
    print('正在下载：', title)

    # 获取索引文件cdn位置
    res = requests.post('https://manga.bilibili.com/twirp/comic.v1.Comic/GetImageIndex?device=pc&platform=web',
                        json.dumps({
                            "ep_id": episode_id
                        }), headers=headers)
    data = json.loads(res.text)
    index_url = 'https://manga.hdslb.com' + data['data']['path']
    print('获取索引文件cdn位置:', index_url)
    # 获取索引文件
    res = requests.get(index_url)
    # 解析索引文件
    pics = decode_index_data(comic_id, episode_id, res.content)
    # print(pics)
    ep_path = os.path.join(root_path, title)
    if not os.path.exists(ep_path):
        os.makedirs(ep_path)
    for i, e in enumerate(pics):
        url = get_image_url(e)
        print(i, e)
        res = requests.get(url)
        with open(os.path.join(ep_path, str(i) + '.jpg'), 'wb+') as f:
            f.write(res.content)
            pass
        if i % 4 == 0 and i != 0:
            time.sleep(2)
            pass
        pass
    pass


def get_image_url(img_url):
    # 获取图片token
    res = requests.post('https://manga.bilibili.com/twirp/comic.v1.Comic/ImageToken?device=pc&platform=web',
                        json.dumps({
                            "urls": json.dumps([img_url])
                        }), headers=headers)
    data = json.loads(res.text)['data'][0]
    url = data['url'] + '?token=' + data['token']
    return url
    pass


if __name__ == "__main__":
    download_manga_all(29579)
    # download_manga_episode(562016, os.path.join(download_path, '第 1 话 龙争虎斗'))
    # get_image_url('/bfs/manga/f311955085404cab705e881d0a81204098967c1e.jpg')
    pass

```
Result:

![image](.\assets\img\posts\20210806\03.jpg)

### Reference
[1] a_achengsong, CSDN, https://blog.csdn.net/csqazwsxedc/article/details/68498842
[2]yangjzhong, CSDN
https://blog.csdn.net/weixin_37185329/article/details/80493281

 
 
