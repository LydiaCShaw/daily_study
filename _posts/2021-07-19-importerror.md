---
layout: post
read_time: true
show_date: true
title: ImportError: cannot import name 'xx' from
date:   2021-07-19 21:32:20 -0600
description: there was an error when I was programming
img: posts/20210719/errors.jpg
tags: [python, errors,pandas]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
Recently, I applied the spinal imaging dataset from [Tianchi](https://tianchi.aliyun.com/competition/gameList/activeList). I wanna tried the U-net algrithm that learned in CSDN. However, when I imported package pandas, there was a problem called: *ImportError: cannot import name 'DtypeArg' from 'pandas._typing'*. 
![errorimage](.\assets\img\posts\20210719\error.jpg)

I was so confused and tried to searched the reason online.  In CSDN, I found one bloger said another error called:*ImportError: cannot import name 'wb'*. Although they were not the same problem, I guessed that both of them were resulted by the version of pandas.

Afterwards, I viewed the explanation of google. Apparently, since in 0.19.0, pandas no longer supports `pandas.io.data` or `pandas.io.wb`, so one must replace his imports from `pandas.io` with those from `pandas_datareader`
![googleimage](.\assets\img\posts\20210719\google.png)
I checked my version immediately after reading this, it was 1.3.0. The pandas.io package was not available at all.
![version](.\assets\img\posts\20210719\version.jpg)
Therefore, insteading of only importing pandas, the alternative method is using pandas_datareader.
```
from pandas.io import data, wb #becomes
from pandas_datareader import data, wb
```
Meanwhile, one required to install relative package:
```
pip install pandas_datareader
```

Then, import it:
```
from pandas_datareader import data, wb
```

After that, we also need to change the codes in program. However, after replacing that, the error still occured again. It was because we had different problems, may be I need another import sentence rather than import data or wb from pandas_datareader. I traced the program, and found it ever run the `pandas.io.excel`,where mentioned line 144 of `__init__.py` in pandas.
![144line](.\assets\img\posts\20210719\line144.jpg)

I did not know why it still imported 'pandas.io.api' in version of 1.3.0. Even I did not know why it happened, because this project included so many files which was complicated to analyze where was wrong. Afterwards, I run the 3 lines program to checked what was wrong:
![newtry](.\assets\img\posts\20210719\newtry.jpg)
I started a new python file called newtry.py. In normal case, it would output the results:
```
Empty DataFrame
Columns: []
Index: []
```
However, the error occured again. I guess it caused by version problem. And now I am still trying.
I will update the situation if I have any other breakthrough or try.

