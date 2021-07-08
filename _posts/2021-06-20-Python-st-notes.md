---
layout: post
read_time: true
show_date: true
title:  Python Self-Study Notes
date:   2021-06-20 08:00:20 -0600
description: Python Self Study Notes 1
img: posts/20210620/python.jpg 
tags: [python, programming, coding]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
大學的時候學過C，C++，實訓時做過HTML，javascript是做app時學以致用的，唯有python我從未接觸過。python在國內大火那年我在上大三，因此學校的課程中並沒有安排這一語言的課程。在圖書館自習的時候，偶然去了地下一樓，看到了兩本Python的書籍，翻看了定價發現竟要650港幣，實屬有點貴。也因為我打字本身就快，在看書自學的時候，隨手就做了筆記。沒想到的是，就這樣日積月累的過程中，整本書都被我打了出來。
這也說得通，至少代碼是一定要手敲一邊進程序來了解運行結果的。本是一本word文檔，我決定全部發到網上，以便隨時溫習。


學習python要下載一些軟件，我下載了書中推介的Anaconda3。Anaconda中比較有用的是它的Jupyter Notebook編譯環境。利用這個，從程式碼的建立到執行所有步驟都能夠一氣呵成，也不必非要建立sample.py文檔來練習，非常方便。
在開始選單中選擇Anaconda中的Jupyter Notebook啟動 會以Web瀏覽器顯示
當Web瀏覽器畫面啟動後，按下File標籤右邊的New按鈕，然後選擇Python即可。
由於我手打的整本書太長，因此另做了[書的鏈接](https://cdn.jsdelivr.net/gh/HEU-F8-PRACTICE/stor@master/20210708/9b5c3a90e9cc977b94e73704f30e5c43/9b5c3a90e9cc977b94e73704f30e5c43.pdf)，密碼是pyly666
由於pdf版本不好用來粘貼代碼，因此以下精簡，只保留代碼在本頁，其餘內容全部在書中，不做過多解釋
# Chapter 1
## 1.1 

```
輸入：>>>開始學習\     #在互動模式中，在列尾輸入\然後按下enter
...Python！        #當下一列出現...後，可以繼續輸入程序
```
輸出：‘開始學習Python！’

## 1.2  

```
print(“顯示反斜線:\\”)
print(“顯示單引號:\’”)
```
執行畫面：
顯示反斜線:\
顯示單引號:’

```
“ “ “歡迎來到             #使用三個引號夾起表示換列的字串
Python！” ” ”
=
“歡迎來到\nPython！”    #與含有\n的換列字串效果相同
```
# Chapter 2
## 2.2
```
name=“東京”
sale=10
print(name,“營業據點的銷售量為”，sale，“萬元。”）
```
輸出：東京營業據點的銷售量為10萬元。
## 2.4
```javascript
price=50 
num=10 
total=price*num 
print("singal price",price,"yuan") 
print("sale number",num) 
print("in total",total,"yuan") 
 
total=total-100 
print("in total after off%",total,"yuan")
```
## 2.5
```javascript
value=input('  ')
value=input("please enter:") 
print("you entered:",value)
```
```javascript
num1=input("num1:") 
num2=input("num2:") 
num3=num1+num2 
print(num1,"+",num2,"=",num3) 
 
result: 
num1:5 
num2:10 
5+10=510
```
# Chapter 3
**語法：
if条件式：
    叙述句1
    叙述句2
     **
```javascript
sale=int(input('enter sale:')) 
 
if sale>=100 : 
    print("sale well") 
print("end")
```
if ~elif~else
```javascript
if condition1: 
    statement1 
    statement2 
    ... 
elif condition2: 
    statement1 
    statement2 
    ... 
elif condition3: 
    ... 
... 
 
else: 
    ...
```
复杂条件式的判断与处理
```javascript
sale=int(input(" ")) 
num=int(input("")) 
 
if sale>=100 and num>=30: 
    print("sell very well") 
 
elif sale>=100: 
    print("sell well") 
elif sale>=50: 
    print("sell not bad") 
else: 
    prinnt("sell bad") 
 
print("process end")
```
## 3.2 
**語法：
for 變量 in 能夠反復處理的資料
...**
在for敘述中，可以利用這種方式來進行重複處理。
```
for i in range(12) 
     print(i+1,"file for month")
 ```
range(個數)的指定方式，其實是range(起始值，結束值，間隔數)的簡略寫法。因此，以上也可寫作
```
for i in range(1,13) 
     print(i,"file for month")
```
不省略間隔數：
```
for i in range(1,13,1) 
    print(i,"file for month")
```
熟練掌握range()後，就能操控各種反復處理的方式
```for i in range(0,10,2)```
這樣可以得到0 2 4 6 8
```for i in range(0,10,-2)```
間隔數可以指定為負數，當間隔數指定為-2時，就會得到跳過一個數字的遞減值，10 8 6 4 2，順序是反的

**語法：
while 條件式
...**
```javascript
i=1 
while i<=12: 
    print(i,"file for month") 
    i=i+1
```
## 3.3 
```javascript
for i in range(5): 
    for j in range(3): 
        print("i is",i,"j is",j) 
```
```javascript
v=False 
 
for i in range(5): 
    for j in range(5): 
    if v is False: 
        print("*",end="") 
        v=True 
    ekse: 
        print("_",end="") 
        v=Flase 
    print() 
 
result: 
*_*_* 
_*_*_ 
*_*_* 
_*_*_ 
*_*_*
```
## 3.4
```javascript
num=int(input("file processed until __ month")) 
 
for i in range(12): 
    print(i+1,"file for month") 
    if(i+1)==num: 
        break
```
```javascript
num=int(input("file processed pass __ month")) 
 
for i in range(12): 
 
    if(i+1)==num: 
        continue 
    print(i+1,"file for month") 
 
result:(1~12) 3  
1 file for month  
2 file for month  
4 file for month  
5 file for month  
6 file for month  
7 file for month  
8 file for month  
9 file for month  
10 file for month  
11 file for month  
12 file for month
```
# Chapter 4
## 4.2
```javascript
sale=[80,60,22,50,75] 
print("list length is",len(sale),"list is :",sale) 
 
print("add 100 in the end of sale") 
sale.append(100) 
print("list is:",sale) 
 
print("insert 25 in sale[2]") 
sale.insert(2,25) 
print("list is:",sale) 
 
print("delete the first one") 
del sale[0] 
print("list is:",sale) 
 
print("delete 22") 
sale.remove(22) 
print("list is:",sale)
```
## 4.3
```javascript
data1=[1,2,3,4,5] 
data2=list(data1) 
print(data1) 
print(data2) 
 
data1[0]=10 
 
print(data1) 
print(data2)
```
## 4.4
```
it=iter(data) 
print(next(it)) 
print(next(it)) 
... 
rv=reversed(data) 
print(next(rv)) 
print(next(rv)) 
...
```
## 4.5 
**語法：元素的打包
zip(串列A，串列B，...)
enumerate(串列名稱)  可以將元素值與索引值合併起來**
```javascript
city=['Beijing','Shanghai','Guangdong','Shenyang'] 
sale=[80,60,22,50,73] 
 
print('City:',city,'.') 
print('Sale:',sale,'.') 
 
print('zip the file') 
 
for d in zip(city,sale): 
    print(d) 
 
print('zip the file and index') 
 
for d in enumerate(city): 
    print(d) 
 ```

result: 
City:['Beijing','Shanghai','Guangdong','Shenyang']. 
Sale:[80,60,22,50,73]. 
zip the file 
('Beijing',80) 
('Shanghai',60) 
('Guangdong',22) 
('Shenyang',50) 
zip the file and index 
(0,'Beijing') 
(1,'Shanghai') 
(2,'Guangdong') 
(3,'Shenyang')

**語法：解包
for 變數1，變數2，... in 串列名稱：**
```javascript
city=['Beijing','Shanghai','Guangdong','Shenyang'] 
sale=[80,60,22,50,75] 
 
print('City:',city,'.') 
print('Sale:',sale,'.') 
 
print('zip the file') 
 
for d in zip(city,sale): 
    print(d) 
 
print('unpack the file') 
 
for c,s in zip(city,sale): 
    print('city:',c,'sale',s)
```
**語法：串列的推導式
[表達式 for 變數 in 串列 if 條件]**
```javascript
data=[1,2,3,4,5] 
print('the file is:',data,'.') 
 
ndata=[n*2 for n in data if n!=3] 
print('the file is:',ndata,'.')
```
# Chapter 5
## 5.3 
**语法：变更字典的元素
字典名称[键值]=元素值
语法：新增字典的元素
字典名称[键值]=元素值**
```javascript
sale={a:80,b=60,c=40,d=20}
k=input(“enter the new key”)
if k in sale:
    print(“the word you type has existed in the dictionary”)
else:
    d=int(input(“enter the file”))
    sale[k]=d
    print(“the file of “,k,”has been added ”,d)

k=input(“enter the key that you want to change:”)
if k in sale:
    print(”the file of”,k,”is:”,sale[k])
    d=int(input(“enter the file:”))
    sale[k]=d
    print(“the file of “,k,”has been changed to”, sale[k])
else:
    print(“no found ”,k)

k=input(“enter the key you want to deflate:”)
if k in sale:
    print(“the file of”,k,”is;”,sale[k])
    del sale[k]
    print(“the file has been delayed”)
else:
    print(“no found the file of “,k)
```
## 5.4 
**语法：
字典名称.keys()... 逐一取得键值
字典名称.values()... 逐一取得元素值
字典名称.items()... 逐一取得键值，元素值的元组**
```javascript
sale={a:80,b:60,c:40,d:20}
print(“the file is:”,sale)

print(“display the key”.)
for k in sale.key():
    print(k,end=“\t”)
print()

print(“display the key and value”)
for i in sale.items():
    print(i,end=“”)
print()
```
**语法：更新字典
字典名称.update(新增的字典名称)**
```javascript
sale1={"Beijing":80,"Shanghai":20,"Shenzhen":60} 
sale2={"Guangdong":22,"Shenyang":95,"Nanjing":50} 
 
print("the file of 1 is:",sale1) 
print("the file of 2 is:",sale2) 
 
print("update file 1 using sale2") 
sale.update(sale2) 
 
print("file 1 is:",sale1)
```
## 5.5
**語法：集合元素的新增、刪除
集合名稱.add()
集合名稱.remove()**
```javascript
city={"Beijing","Shanghai","Shenyang","Guangdong"} 
 
d=input("please enter the file you want to add") 
if d in city: 
    print("this file has existed.") 
else: 
    city.add(d) 
    print("the file changed to:",city) 
 
d=input("please enter the file you want to delate") 
if d in city: 
   city.remove(d) 
   print("the file has delated already") 
else: 
   print("not found this file.")
```
```javascript
cityA={"Shenyang","Beijing","Guangdong","Shanghai"} 
cityB={"Nanjing","Shanghai","Jiangsu"} 
 
print("City A includes:") 
print("City B includes:") 
 
print("the common file is:",cityA&cityB) 
print("the file only exist in A",cityA-cityB) 
print("the file only exist in B",cityB-cityA) 
print("all the files are:",cityA|cityB)
```
# Chapter 6
## 6.3
```javascript
def sell(place): 
    print(place,"start selling") 
 
shop="Beijing" 
sell(shop)
```
```javascript
def sell(place,num): 
    print(place,"start selling",num,'yuan') 
 
shop="Beijing" 
money=5 
sell(shop,money)
```
```javascript
#true 
def func1(a,b,c,d=2,e=10): 
 
#false 
def func1(a,b=2,c,d,e=10): 
 
func1(10,5,20) 
func1(10,5,20,30) 
func1(10,5,20,30,50)
```
## 6.4
```javascript
def sell(place,price,num): 
    print(place,"sale for",num,"componies",price,"million products.") 
 
    tt=price*num 
    return tt 
 
total= sell("Beijing",100,5) 
 
print("the total sales are:",total,"million dollars")
```
返回多個傳回值
```javascript
def sell(): 
   y=2018 
   m=10 
   d=1 
   print(y,"year",m,"month",d"day will begin to sell.") 
 
   return y,m,d 
 
sy,sm,sd=sell() 
 
print("stop selling",sy,sm,sd)
```
## 6.5
```javascript
def append(): 
    print("add new file") 
def update(): 
    print("change the file") 
def delete(): 
    print("delate the file") 
 
list=[append,update,delete]  
/*function can be value of list*/ 
 
res=int(input("please enter the operation code(0-2)")) 
 
if 0<=res and res<len(list): 
    list[res]() 
/*values of list can call the function*/ 
/* [ ]  means index*/ 
 ```
 ```
Operation results: 
please enter the operation code(0-2) 
1 
change the file
```
**語法：lambda運算子
lambda 引數：表達式**
```javascript
data=[1,2,3,4,5] 
 
for d in map(lambda x:x*2,data): 
 
    print(d) 
 
operation results: 
2 4 6 8 10
```
語法：map()函數
map(函數，可迭代物件)
```javascript
data=[1,2,3,4,5] 
for d in [x*2 for x in data]: 
    print(d)
```
用裝飾器在函數中新增功能
```javascript
def deco(func): 
    def wrapper... 
        ... 
        return ... 
    return wrapper
```
語法：裝飾器
@裝飾其他物件並用來新增功能的函數名稱
def 被新增功能的函數名稱：
```javascript
def deco(func): /* 外側函數接收原本的函數並把它視為引數*/ 
    def wrapper(x): 
        wx="---"+x+"---" 
        return func(wx) /*執行內側函數處理的同時，也會處理原來的函數 */ 
    return wrapper /* 外側函數會將內側函數當成傳回值返回*/ 
 
@deco /* 指定裝飾器*/ 
def printmsg(x): 
    print("you entered:",x) /*可以在函數中新增功能 */ 
 
str=input("please enter the message:") 
 
printmsg(str) /*呼叫函數後 */
```
執行結果：
Please enter the message: hello
You entered: ---hello---
## 6.6
```javascript
a=0 
def funcB(): 
    b=1 
    print("it can be used variable a and b in funcB") 
    print("the variable a is:",a) 
    print("the variable b is:",b) 
    #print("the variable c is:",c) 
 
def funC(): 
    c=2 
    print("it can be used variable a and c in funcC") 
    print("the variable a is:",a) 
    #print("the variable b is:",b) 
    print("the variable c is:",c) 
 
print("it can be used variable a outside the function") 
print("the variable a is:",a) 
#print("the variable b is:",b) 
#print("the variable c is:",c) 
 
funcB() 
funcC()
```
## 6.7

```javascript
a=0 
 
def func(): 
    global a 
    b=0 
    print("variable a is:",a,"variable b is:",b) 
 
    a=a+1 
    b=b+1 
 
for i in range(5) 
    func()
```
執行結果：
variable a is: 0  variable b is: 0
variable a is: 1  variable b is: 0
variable a is: 2  variable b is: 0
variable a is: 3  variable b is: 0
variable a is: 4  variable b is: 0
# Chapter 7
## 7.1
语法：类别的定义
class 类别名称：
    def 方法名称(self, 引数列表 ):
        self.变数名称=...
        ...
        return 叙述
```javascript
class person:
    def getname(self):
        return self.name
    def getage(self):
        return self.age
```
语法：属性的利用
实体物件名称.资料属性名称
实体物件名称.方法名称（引数列表）
```javascript
class Person:  ①定義類別
    def getName(self): 
        return self.name 
 
    def getAge(self): 
        return self.age 
 
pr=Person()     ②建立實體物件
pr.name="Sheung"     ③將值指定給資料屬性
pr.age=24 
 
n=pr.getName() 
a=pr.getAge()         ③呼叫方法
 
print("Miss/Mr",n,"age",a)
```
建立多個實體物件
```javascript
class Person: 
    def getName(self): 
        return self.name 
 
    def getAge(self): 
        return self.age 
 
pr1=Person() 
pr1.name="Sheung" 
pr1.age=24 
n1=pr1.getName() 
a1=pr1.getAge() 
 
pr2=Person() 
pr2.name="Hu" 
pr2.age=29 
n2=pr2.getName() 
a2=pr2.getAge() 
 
print("Ms/Mr",n1,age,a1) 
print("Ms/Mr",n2,age,a2)
```
## 7.2
語法：建構子
def__init__(self,引數列表):
....
```javascript
def__init__(self,name,age): 
    self.name=name 
    self.age=age 
 
pr=person("Sheung",24)
```
```javascript
class Person: 
    def__init__(self,name,age): 
        self.name=name 
        self.age=age 
 
    def getName(self): 
        return self.name 
 
    def getAge(self): 
        return self.age 
 
pr=Person("Sheung",24) 
 
n=pr.getName() 
a=pr.getAge() 
 
print("Mr/Ms",n, age,a)
```
## 7.3
```javascript
class Person(): 
    count=0  /* 屬於整個類別的值的資料屬性（類別變量）*/ 
    ... 
    def getName(self): 
        return self.name 
        /*每個實體物件都格子有一個值的資料屬性（實體變量） */
```
要定義返回類別變量count值的類別方法。
```javascript
@classmethod 
def getCount(cls): /*將類別名稱傳遞給第一個引數 */ 
    return cls.count 
    /* 可以使用類別名稱*/
```
類別變量：
Person.count  附加類別名稱來表示類別變量
類別方法：
Person.getCount() 附加類別名稱並呼叫
```javascript
class Person(): 
    count=0 
 
    def__init__(self,name,age): 
        Person.count=Person.count+1 
 
        self.name=name 
        self.age=age 
 
    def getName(self): 
        return self.name 
 
    def getAge(self): 
        return self.age 
 
    @classmethod 
    def getCount(cls): 
        return cls.count 
 
pr1=Person("Sheung",24) 
pr2=Person("Shang",23) 
 
print("Mr/Ms",pr1.getName(),"age",pr1.getAge) 
print("Mr/Ms",pr2.getName(),"age",pr2.getAge) 
print("number of people in total:",Person.getCount())
```
## 7.5
語法：定義衍生類別
class 衍生類別名稱（基礎類別名稱）：
...
def 在衍生類別中新增的方法（self,引數列表）：
    self.在衍生類別中新增的資料屬性=值
    ...
```javascript
class Customer(Person): /* 定義衍生類別*/ 
    def__init__(self,nm,ag,ad,tl): /* 這是衍生類別的建構子*/ 
        super().__init__(nm,ag) /* 為了將基礎類別的資料屬性初始化，而呼叫基礎類別的建構子 */ 
        self.adr=ad /* 新增資料屬性 */ 
        self.tel=tl 
 
    def getName(self): /*可以覆寫基礎類別的方法 */ 
        self.name="Customer"+self.name 
        return self.name 
 
    def getAdr(self): 
        return self.adr 
 
    def getTel(self): 
        return self.tel
```
語法：多重繼承
class Customer (Person,Account):
...
```javascript
class Person(): 
    ... 
    def getName(self): 
        return self.name 
 
class Customer(Person): 
    ... 
    def getName(self): 
    self.name="Customer"+self.name 
        return self.name
```
覆寫
```javascript
class Person: 
    def __init__(self,name,age): 
        self.name=name 
        self.age=age 
 
    def getName(self): 
        return self.name 
    def getAge(self): 
        return self.age 
class Customer(Person): 
    def __init__(self,nm,ag,ad,tl): 
        super().__init__(nm,ag) 
 
       self.adr=ad 
       self.tel=tl 
 
    def getName(self): 
        self.name="Customer"+self.name 
        return self.name 
    def getAdr(self): 
        return self.adr 
    def getTel(self): 
        return self.tel 
 
pr=Customer("Sheung",18,"LydiaCShaw@gmail.com","852-6881xxxx") 
nm=pr.getName() 
ag=pr.getAge() 
ad=pr.getAdr() 
tl=pr.getTel() 
 
print("Mr/Ms",nm,"age",ag) 
print("mail:",ad,"tel:",tl)
```
執行結果
Mr/Ms Customer Sheung age 18
mail: LydiaCShaw@gmail.com tel: 852-6882xxxx
## 7.6
```javascript
class Person: 
    ... 
    def __str__(self): /* 一旦定義既有名稱的方法__str__0 ...*/ 
        str="Mr/Ms"+self.name /* 就可以對str()函數的行為加以定義*/ 
        return str
```
定義運算子的處理
```javascript
class A: 
    ... 
    def __add__(self,other): 
        return self.num+ other.num 
a1=A(1) 
a2=A(2) 
print(a1+a2)
```
## 7.7
```javascript
myclass.py 
 
class Person: 
   def __init__(self,name,age): 
       self.name=name 
       self.age=age 
    def getName(self): 
        return self.name 
    def getAge(self): 
        return self.age 
 
class Customer(Person): 
   def__init__(self,nm,ag,ad,tl): 
       super().__init__(nm,ag) 
 
       self.adr=ad 
       self.tel=tl 
 
    def getName(self): 
        self.name="Dear"+self.name 
        return self.name 
    def getAdr(self): 
        return self.adr 
    def getTel(self): 
        return self.tel 
 
sample6.py 
 
import myclass /*匯入其他的模組（檔案） */ 
 
pr=myclass.Customer("Sheung",18,"LydiaCShaw@gmail.com","852-68816430")  /*呼叫其他模組（檔案）的類別 */  
nm=pr.getName() 
ag=pr.gerAge() 
ad=pr.getAdr() 
tl=pr.getTel() 
 
print("Mr/Ms",nm,"age",ag,"E-mail",ad,"Tel:",tl,".")
```
語法：直接引入
from 模組名稱 import 函數名稱或類別名稱
```javascript
from myclass import Customer 
    ... 
pr=Customer("Sheung",18,"LydiaCShaw@gmail.com","852-68816430") 
 
print("Mr/Ms",nm,"age",ag,"E-mail",ad,"Tel:",tl,".")
```
# Chapter 8

```javascript
str=input("please enter the string") 
 
print("the string is:",str,".") 
print("acquire the string of index 0",str[0]) 
print("reverse the string",str[::-1]) 
print("the length of string is:",len(str),".")
```
執行結果：
Please enter the string ->Hello~everyone
The string is: Hello~everyone
Acquire the string of index 0: H
Reverse the string enoyreve~olleH
The length of string is: 14
```javascript
str=input("please enter:") 
 
print("string is:",str) 
print("change to upper case:",str.upper()) 
print("change to lower case:",str.lower())
```
執行結果：
Please enter: Hello
String is: Hello
Change to upper case: HELLO
Change to lower case: hello

格式化字串
```javascript
word0=input("please enter the first word:") 
word1=input("please enter the second word:") 
word2=input("please enter the third word:") 
 
print("{0}is a{1}{2}.{2}.".format(word0,word1,word2)) 
 
num0=int(input("please enter the number:")) 
num1=int(input("please enter the money:")) 
 
print("{0:<}products{1:>10}yuan".format(num0,num1))
```
執行結果
Please enter the first word: today
Please enter the second word: good
Please enter the third word: day

Today is a good day.day.
Please enter the number: 10
Please enter the money: 10000
10 products              10,000yuan

搜尋字串
```javascript
str=input("enter the string:") 
key=input("enter the key word you want to search:") 
res=str.find(key) 
if res !=-1: 
    print(key,"existed in",str,"at",res,"position") 
else: 
    print(key,"was not found in",str)
```
執行結果：
Enter the string: Hello
Enter the key word you want to search: o
O existed in Hello at 4 position.
字串的取代
```javascript
str1=input("enter the string") 
old=input("enter the string you want to be replaced") 
new=input("enter the string you want to replace") 
if olf in str1: 
   str2=str1.replace(old,new) 
   print("instead of",str2) 
else: 
   print(str1+"this string can not found"+old)
```
執行結果：
Enter the string 午安，你好
Enter the string you want to be replaced 午安
Enter the string you want to replace 晚安
Instead of 晚安，你好
## 8.2 
語法：利用正規表示式
import re
語法：投過正規表示式來檢索
用來表示編譯後模式的變量=re.compile(模式)  ①編譯模式字串
用來表示編譯後模式的變量.search(檢索對象字串)  ②進行檢索
```javascript
import re 
ptr=["Apple","GoodBye","Thankyou"] 
str=["Hello","GoodBye","Thankyou"] 
for valueptr in ptr: 
    print("------") 
    pattern=re.compile(valueptr) 
    for valuestr in str: 
        res=pattern.search(valuestr) 
        if res is not None: 
            m="yes" 
 
        else: 
            m="no" 
        msg="(pattern)"+valueptr+"(string)"+valuestr+"(match)"+m 
        print(msg)
```
------
(pattern)Apple(string)Hello(match) no
(pattern)Apple(string)GoodBye(match) no
(pattern)Apple(string)Thankyou(match) no

------
(pattern)GoodBye(string)Hello(match) no
(pattern)GoodBye(string)GoodBye(match) yes
(pattern)GoodBye(string)Thankyou(match) no

------
(pattern)Thankyou(string)Hello(match) no
(pattern)Thankyou(string)GoodBye(match) no
(pattern)Thankyou(string)Thankyou(match) yes

表示字串開始與結束的正規表示式
```javascript
import re 
ptr=["TXT","^TXT","TXT$","^TXT$"] 
str=["TXT","TXTT","TXTTT","TTXT"] 
 
for valueptr in ptr: 
    print("------") 
    pattern=re.compile(valueptr) 
    for valuestr in str: 
        res=pattern.search(valuestr) 
        if res is not None: 
            m="yes" 
        else: 
            m="no" 
        msg="(pattern)"+valueptr+"(string)"+valuestr+"(match)"+m 
        print(msg)
```
```
執行結果：
------
(pattern)TXT(string)TXT(match) yes
(pattern)TXT(string)TXTT(match) yes
(pattern)TXT(string)TXTTT(match) yes
(pattern)TXT(string)TTXT(match) yes
------
(pattern)^TXT(string)TXT(match) yes
(pattern)^TXT(string)TXTT(match) yes
(pattern)^TXT(string)TXTTT(match) yes
(pattern)^TXT(string)TTXT(match) no
------
(pattern)TXT$(string)TXT(match) yes
(pattern)TXT$(string)TXTT(match) no
(pattern)TXT$(string)TXTTT(match) no
(pattern)TXT$(string)TTXT(match) yes
------

(pattern)^TXT$(string)TXT(match) yes
(pattern)^TXT$(string)TXTT(match) no
(pattern)^TXT$(string)TXTTT(match) no
(pattern)^TXT$(string)TTXT(match) no
```
表示1個字元的正規表示式
```javascript
import re 
ptr=["TXT.","TXT..",".TXT","..TXT"] 
str=["TXT","TXTT","TXTTT","TTXT","TTTXT"] 
 
for valueptr in ptr: 
    print("------") 
    pattern=re.compile(valueptr) 
    for valuestr in str: 
        res=pattern.search(valuestr) 
        if res is not None: 
            m="yes" 
        else: 
            m="no" 
        msg="pattern"+valueptr+"string"+valuestr+"match"+m 
        print(msg)
```
```
執行結果：
------
(pattern)TXT.(string)TXT(match) no
(pattern)TXT.(string)TXTT(match) yes
(pattern)TXT.(string)TXTTT(match) yes
(pattern)TXT.(string)TTXT(match) no
(pattern)TXT.(string)TTTXT(match) no
------
(pattern)TXT..(string)TXT(match) no
(pattern)TXT..(string)TXTT(match) no
(pattern)TXT..(string)TXTTT(match) yes
(pattern)TXT..(string)TTXT(match) no
(pattern)TXT..(string)TTTXT(match) no
------
(pattern).TXT(string)TXT(match) no
(pattern).TXT(string)TXTT(match) no
(pattern).TXT(string)TXTTT(match) no
(pattern).TXT(string)TTXT(match) yes
(pattern).TXT(string)TTTXT(match) yes
------
(pattern)..TXT(string)TXT(match) no
(pattern)..TXT(string)TXTT(match) no
(pattern)..TXT(string)TXTTT(match) no
(pattern)..TXT(string)TTXT(match) no
(pattern)..TXT(string)TTTXT(match) yes
```
使用代表字元類別的正規表示式
```javascript
import re 
ptr=["[012]","[0-3]","[^012]"] 
str=["0","1","2","3"] 
 
for valueptr in ptr: 
    print("------") 
    pattern=re.compile(valueptr) 
    for valuestr in str: 
        res=pattern.search(valuestr) 
        if res is not None: 
            m="yes" 
        else: 
            m="no" 
        msg="pattern"+valueptr+"string"+valuestr+"match"+m 
        print(msg)
```
```
執行結果：
------
(pattern)[012](string)0(match) yes
(pattern)[012](string)1(match) yes
(pattern)[012](string)2(match) yes
(pattern)[012](string)3(match) no
------
(pattern)[0-3](string)0(match) yes
(pattern)[0-3](string)1(match) yes
(pattern)[0-3](string)2(match) yes
(pattern)[0-3](string)3(match) yes
------
(pattern)[^012](string)0(match) no
(pattern)[^012](string)1(match) no
(pattern)[^012](string)2(match) no
(pattern)[^012](string)3(match) yes
```
表示重複的正規表示式
```javascript
import re 
ptr=["T*","T+","T?","T{3}"] 
str=["X","TT","TTT","TTTT"] 
 
for valueptr in ptr: 
    print("------") 
    pattern=re.compile(valueptr) 
    for valuestr in str: 
        res=pattern.search(valuestr) 
        if res is not None: 
            m="yes" 
        else: 
            m="no" 
        msg="pattern"+valueptr+"string"+valuestr+"match"+m 
        print(msg)
```
```
執行結果：
------
(pattern)T*(string)X(match) yes
(pattern)T*(string)TT(match) yes
(pattern)T*(string)TTT(match) yes
(pattern)T*(string)TTTT(match) yes
------
(pattern)T+(string)X(match)no
(pattern)T+(string)TT(match) yes
(pattern)T+(string)TTT(match) yes
(pattern)T+(string)TTTT(match) yes
------
(pattern)T?(string)X(match) yes
(pattern)T?(string)TT(match) yes
(pattern)T?(string)TTT(match) yes
(pattern)T?(string)TTTT(match) yes
------
(pattern)T{3}(string)X(match) no
(pattern)T{3}(string)TT(match) no
(pattern)T{3}(string)TTT(match) yes
(pattern)T{3}(string)TTTT(match) yes
```
表示群組化和選擇的正規表示式
```javascript
import re 
ptr=["(TXT)+","TXT|XTX"] 
str=["TX","TXT","XTX","TXTXT"] 
 
for valueptr in ptr: 
    print("------") 
    pattern=re.compile(valueptr) 
    for valuestr in str: 
        res=pattern.search(valuestr) 
        if res is not None: 
            m="yes" 
        else: 
            m="no" 
        msg="pattern"+valueptr+"string"+valuestr+"match"+m 
        print(msg)
```
```
執行結果：
------
(pattern)(TXT)+(string)TX(match) no
(pattern)(TXT)+(string)TXT(match) yes
(pattern)(TXT)+(string)XTX(match) no
(pattern)(TXT)+(string)TXTXT(match) yes
------
(pattern)TXT|XTX(string)TX(match) no
(pattern)TXT|XTX(string)TXT(match) yes
(pattern)TXT|XTX(string)XTX(match) yes
(pattern)TXT|XTX(string)TXTXT(match) yes
```
正規表示式的方法
```javascript
import re 
ptr="\\.(csv|html|py)$" 
str=["sample.csv","sample.exe","test.py","index.html"] 
 
pattern=re.compile(ptr) 
for valuestr in str: 
    res=pattern.sub(".txt",valuestr) 
    msg="(before instead)"+valuestr+"(after instead)"+res 
    print(msg)
```
```
執行結果：
(before instead) sample.csv (after instead) sample.txt
(before instead) sample.exe (after instead) sample.txt
(before instead) test.py (after instead) test.txt
(before instead) index.html (after instead) index.txt
```
# Chapter 9
## 9.1
寫入到文字檔案
```javascript
f=open("sample.txt","w") 
f.write("hello\\n") 
f.write("goodbye\\n") 
f.close()
```
讀取文字檔案
```javascript
f=open("sample.txt","r") /*在讀取模式中開啟檔案 */ 
lines=f.readlines()/*讀取所有的列 */ 
for line in lines: /* 逐列反復取出*/ 
    print(line,end="")/* 並加以顯示*/ 
f.close()
```
## 9.2
Sample.csv
```
Beijing,pencil,25
Beijing,rubber,30
Shanghai,notebook,56
Shenyang,ruler,100
Guangzhou,notebook,73
```

```javascript
import csv 
f=open("sample.csv","r") 
rd=csv.reader(f) 
for row in rd: 
    for col in row: 
        print(col, end",") 
    print() 
f.close()
```
執行結果：
Beijing,pencil,25,
Beijing,rubber,30,
Shanghai,notebook,56,
Shenyang,ruler,100,
Guangzhou,notebook,73,

寫入CSV檔案
```javascript
w=csv.writer(f) 
w.writerow(["Beijing","rubber"]) 
w.writerows([["Beijing","ruler"],["Shanghai","notebook"]])
```
## 9.3
sample4.json
```
{ 
    "North": 
        { 
            "Beijing":50 
            "Shenyang":40 
        }, 
    "South": 
        { 
            "Shanghai":30 
            "Guangzhou":20 
        } 
}
```
sample4.py->read JSON file
```javascript
import json 
f=open("sample.json","r") 
data=json.load(f) 
print(data) 
f.close()
```
## 9.4
*例外處理的敘述*
語法：例外處理
try:
    檢查例外發生的敘述
    ...
except 例外類別的名稱:
發生例外時的處理敘述
...
else:
沒有發生例外時的處理敘述
...
finally:
最後一定會處理的敘述
...
```javascript
try: 
    f=open("sample.txt","r") 
    except FileNotFounfError: 
    print("can not open the file") 
else: 
    lines=f.readlines() 
    for line in lines: 
        print(line,end="") 
    f.close() 
finally: 
    print("proceed")
```
## 9.5
取得指定路徑的資訊
```javascript
import os 
import os.path 
curdir=os.listdir(".") 
for name in curdir: 
    print(os.path.abspath(name),end=",") 
    if(os.path.isfile(name)): 
        print("which is file") 
    else: 
        print("which is dictionary") 
print()
```
## 9.6
語法：利用日期時間資訊
import datetime
```javascript
import datetime 
dt=datetime.datetime.now() 
print("now is",dt) 
print("year",dt.year) 
print("month",dt.month) 
print("day",dt.day) 
dt=dt+datetime.timedelta(days=1) 
print("after 1 day is",dt)
```
執行結果：
Now is 2021-07-06 17:25:14.595045
Year 2021
Month 07
Day 06
Adter 1 day is 2021-07-07 17:25:14.595045

指定日期時間的格式
```javascript
import datetime 
dt=datetime.datetime.now() 
str=dt.strftime("%c") 
print("now is",str) 
dt=dt+datetime.timedelta(days=1) 
str=dt.strftime("%Y-%m-%d") 
print("tomorrow is",str)
```
Now is Sun Feb 9 16:26:57 2020
Tomorrow is 2020-02-10
# Chapter 10
## 10.2
建立表格
```
CREATE TABLE product(
    Name CHAR(20),price INT
)
```
在表格中新增資料
```
INSERT INTO product
VALUES(“pencil”,80)
```
從表格查詢資料
```SELECT* FROM product```
顯示整個表格

```javascript
import sqlite3 /* 為了使用資料庫而匯入的模組*/  
conn=sqlite3.connect("pdb.db") /* 連接資料庫*/  
c=conn.cursor() /* 取得資料指標*/  
c.execute("DROP TABLE IF EXISTS product") /*建立表格*/  
c.execute("CREATE TABLE product(name CHAR(20), price INT)") /*新增資料 */  
c.execute("INSERT INTO product VALUES('pencil',80)")  
c.execute("INSERT INTO product VALUES('rubber',50)")  
c.execute("INSERT INTO product VALUES('ruler',200)")  
 
conn.commit() /*提交 */  
itr=c.execute("SELECT * FROM product") /*取出表格中的所有資料 */ 
for row in str: 
     print(row) /* 顯示出取出的資料*/ 
conn.close() /*關閉資料庫 */
```
## 10.3
WHERE條件
```
SELECT *
FROM  product
WHERE  price>=200
```
```javascript
import sqlite3 
conn=sqlite3.connect("pdb.db") 
c=conn.cursor() 
itr=c.execute("SELECT * FROM product WHERE price>=200") 
for row in itr: 
    print(row) 
conn.close()
```
字串檢索
```
SELECT *
FROM  product
WHERE  name='pencil'
```
檢索部分資料
```
SELECT *
FROM product
WHERE name LIKE '%pen%'
```
依照值大小排序
```
SELECT *
FROM product
ORDER BY price
```
此外，要由大到小排序時，要在最後加上DESC
```
SELECT *
FROM product
ORDER BY price DESC
```
以上白框部分皆可以替換sample10.py中c.execute裡的部分。
## 10.4 
語法：讀取URL的模組
import urllib.request
```javascript
import urllib.request.urlopen("https://www.lydiashaw.asia") 
html=page.read() 
str=html.decode() 
print(str)
```
解析HTML
```javascript
import urllib.request 
from html.parser import HTMLParser 
 
class SampleHTMLParser(HTMLParser): 
    def __init__(self): 
        HTMLParser.__init__(self) 
        self.title=False 
 
    def handle_starttag(self,tag,attrs): 
        if tag=="title": 
            self.title=True 
 
    def handle_data(self,data): 
        if self.title is True: 
            print("title:",data) 
            self.title=False 
 
page=urllib.request.urlopen("http://www.lydiashaw.asia") 
html=page.read() 
str=html.decode() 
 
p= SampleHTMLParser() 
p.feed(str) 
p.close()
```
執行結果：
title:Lydia Shaw|Main Page

# Chapter 11
## 11.2
語法：統計指標的模組
import statistics
```javascript
import statistics 
data=[8,17,0,11,6,21,16,6,17,11,7,9,6,13,12,16,3,14,13,12] 
print("mean",statistics.mean(data)) 
print("median",statistics.median(data)) 
print("mode",statistics.mode(data)) 
print("pvariance",statistics.pvariance(data)) 
print("pstdev",statistics.pstdev(data))
```
執行結果：
mean 10.9
median 11.5
mode 6
pvariance 26.49
pstdev 5.146843692983108
## 11.3
語法：繪製圖表
import matplotlib.pyplot as plt
```javascript
import matplotlib.pyplot as plt 
data=[8,17,0,11,6,21,16,6,17,11,7,9,6,13,12,16,3,14,13,12] 
plt.title("Histogram") 
plt.xlabel("value") 
plt.ylabel("frequency") 
plt.hist(data) 
plt.show()
```
![results](./assets/img/posts/20210620/1.png)

## 11.4 
繪製散佈圖
```javascript
import random 
import matplotlib.pyplot as plt 
x=[] 
y=[] 
for i in range(100): 
    x.append(random.uniform(0,50)) 
    y.append(random.uniform(0,50)) 
 
plt.scatter(x,y) 
plt.show()
```
![results](./assets/img/posts/20210620/2.png)
## 11.5
繪製數學相關的圖表
語法：math模組的使用
import math
```javascript
import math 
import matplotlib.pyplot as plt 
x=[] 
s=[] 
c=[] 
for i in range(50): 
    x.append(i*0.05*math.pi) 
    s.append(math.sin(x[i])) 
    c.append(math.cos(x[i])) 
 
plt.title("sin/cos function") 
plt.xlabel("rad") 
plt.ylabel("value") 
plt.grid(True) 
 
plt.plot(x,s,label="sin") 
plt.plot(x,c,label="cos") 
plt.legend() 
plt.show()
```
![results](./assets/img/posts/20210620/3.png)
## 11.6 
使用NumPy模組

**語法：利用NumPy
import numpy as np**
```javascript
import numpy as np 
import matplotlib.pyplot as plt 
x=np.arange(0.0,2.5,0.05)* np.pi 
s=np.sin(x) 
c=np.cos(x) 
plt.title("sin/cos functions") 
plt.xlabel("rad") 
plt.ylabel("value") 
plt.grid(True) 
 
plt.plot(x,s,label="sin") 
plt.plot(x,c,label="cos") 
plt.legend() 
plt.show()
```
![results](./assets/img/posts/20210620/4.png)
# Chapter 12
進行線性回歸
**語法：進行線性回歸的模組
from sklearn import linear_model**
```javascript
from sklearn import datasets 
from sklearn import linear_model 
from sklearn.model_selection import train_test_split 
import matplotlib.pyplot as plt 
import numpy as np 
 
np.random.seed(0)   /*設定亂數種子*/
x,y=datasets.make_regression(n_samples=100,n_features=1,noise=30)  /*事先準備線性回歸的資料*/
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.3) /* 區分訓練和測試數據*/
e=linear_model.LinearRegression()  /*取得用於回歸的實體物件*/
e.fit(x_train,y_train)  /*取得適合的模型*/
print("regression coefficient",e.coef_)  /*取得回歸模型*/
print("intercept",e.intercept_) 
y_pred=e.predict(x_test)   /*用測試資料進行預測*/
print("score according to the train data",e.score(x_train,y_train))  /*評估模型對於訓練資料的適合度*/
print("score according to the test data",e.score(x_test,y_test))  /*評估模型對於測試資料的適合度*/
plt.scatter(x_train,y_train,label="train") 
plt.scatter(x_test,y_test,label="test") 
plt.plot(x_test,y_pred,color="magenta") 
plt.legend() 
plt.show()
```
![results](./assets/img/posts/20210620/5.png)
## 12.3 
進行聚類分析
語法：用於進行聚類分析的模組
from sklearn import cluster
```javascript
from sklearn import datasets 
from sklearn import cluster 
import matplotlib.pyplot as plt 
 
data,label=datasets.make_blobs(n_samples=500,n_features=2,centers=5) 
e=cluster.KMeans(n_clusters=5) 
e.fit(data) 
print(e.labels_) 
print(e.cluster_centers_) 
plt.scatter(data[:,0],data[:,1],marker="o",c=e.labels_,edgecolor="k") 
plt.scatter(e.cluster_centers_[:,0],e.cluster_centers_[:,1],marker="x") 
plt.show()
```
![results](./assets/img/posts/20210620/6.png)
