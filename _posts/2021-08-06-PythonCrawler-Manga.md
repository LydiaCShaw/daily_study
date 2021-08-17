---
layout: post
read_time: true
show_date: true
title: "Python Crawler Exercise-Manga files of bilibili"
date:   2021-08-06 12:32:20 -0600
description: Using 
img: 20210806/cover.png
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
Now we know how to crawl the website, so we can try another website. So I turned my eyes to Bilibili, which is the biggest manga website in China.
By using the method mentioned above, I can find the location of images in HTML, however, observing the codes, we can find the website of bilibili is much more complicated. Asynchronous loading means we can not obtain all the source if we do not view all the pages of manga, which is a method to avoid crawler.

![image](.\assets\img\posts\20210806\01.jpg)
Only when I turn page, images can be loaded successfully.


### Reference
[1] a_achengsong, CSDN, https://blog.csdn.net/csqazwsxedc/article/details/68498842


 
 
