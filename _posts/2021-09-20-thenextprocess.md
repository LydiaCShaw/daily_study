---
layout: post
read_time: true
show_date: true
title: " The afterwards process in clinic"
date:   2021-09-20 12:32:20 -0600
description: 
img: posts/stock/20210925_cover.jpg
tags: [circuit, PCB, chips, sensor, canfit]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
The last article I mentioned about the whole process of assessment in our lab, but what about the next stage in clinic? I ever displayed an image of treatment protocol to illustrate the next stage, so when the cobb's angle measured was between 20-45，we may provide the brace to patients.

We normally used IPad Mini connected to the 3D scanner spectra from Vorum to scan patient. After we attach all the markers, then we ask patient sit on a special seat and  begin to scan several times so that the 3D model can be recorded.

<iframe width="970" height="545" src="https://www.youtube.com/embed/x2ubKxnPxcA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

After that, we also should measure some body data such as chest circumference, waist circumference and hip circcumference.

Afterwards, we used the software [Canfit](https://vorum.com/canfit-op-cad-software/) which is a computer-aided design (CAD) software application empowers you to quickly design all types of custom prosthetic and orthotic devices. Uniquely easy to learn and anatomically correct, it will have you reaping the full benefits of digital O&P technology in short order.


The complete Vorum integrated CAD/CAM solution for prosthetics and orthotics includes 3D scanners, computer-aided shape modification software, automated carvers, and 3D printer integration.

![image](.\assets\img\posts\stock\20210925_canfit.jpg)

<iframe width="642" height="361" src="https://www.youtube.com/embed/5-twUWOFoto" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

After fitting the model relying on the measurement data, we mainly extend and smooth it, also reduce the size to add some force in right place.

Then the model exported can be 3D printed in hospital. We also made some pads and the attached on the model. The raw material of brace is heated in an oven so that it can be soft and stick tightly to the outer of the 3D printed model.

About the material, I will talk about next time. The main topic will be 'some common material that used in P&O'

The purpose of research, we used the brace not only study but also give them to real patients. The fact is that, there are some patients really obtaining some improvement, we checked the follow up cases and did the comparison during one or two week depending on the severity of the patients and found the cobb's angel measured on X-ray images reduced.

For these reasons, we can conclude that the brace is useful for most of patients especially for these patients who has a flexible spine. However, for the specific force or mechanism is not clear until now.

Therefore, we added the sensor that can measure pressure and temperature on the brace connected to bluetooth and used the cell phone to recorded the force and temperture.

Although we did that, one still can not determine what action patients did and can not find any relationship except knowing whether they put on the brace on time.

Because the curve of real body, the brace ought to fit the curve as well, it is difficult to put the sensor on the brace. The wrong place cannot record the right force worked on the patients. We can not compare which patients obtain the best force as well for the position of sensor is different depending on the shape of brace.

In addition, the sensor is very sensitive, our co-researcher sent some from Canada but 2 of them have broken with unknown reason. To know what happen and whether we can fix it, I open the sensor and tried to see the circuit of chips.

Due to the emergence of PCB circuit boards, today's electrical appliances have very tiny and delicate circuit designs. The sensor has 7 units in total, and you can see there are a lot of Shorthands on the board.

![image](.\assets\img\posts\stock\20210925_1.png)

Therefore, firstly, I want to illustrate some shorthands on PCB board.

The common shorthands are shown as below:
```
ESD: protection time
ET: transformer or transistor
J: connector
TP: test point
M: module
U: integrated circuit
BOOT: upgrade program
ADDR: address
AE: antenna
B: battery
C: capacitor
CRT: negative tube
L: inductance
R: resistance
```

![image](.\assets\img\posts\stock\20210925_2.png)
The unit 1 is a bluetooth connection called [Bluetooth NRG](https://pdf1.alldatasheet.com/datasheet-pdf/view/1006984/STMICROELECTRONICS/BLUENRG-2.html) , for the insulation layer on the chip, I can not detect the voltage or current at all, but I found the inner structure, we will explore more about this chip.


![image](.\assets\img\posts\stock\20210925_3.png)
![image](.\assets\img\posts\stock\20210925_4.png)
The unit 2 is a pressure sensor called [FSL500NS](https://www.ebay.com/itm/HONEYWELL-Force-Sensor-FSS-Series-FSS1500NST-FS1500NS-/132992282247?_ul=IN) which is very expensive. And I have measured the voltage and current it works well.


![image](.\assets\img\posts\stock\20210925_5.png)
Unit 3 is very small, I can not check chip number, but presumably thermocouple temperature transducer. I found a similar one called [AD590JRZ](https://hkcn.rs-online.com/web/p/temperature-humidity-sensor-ics/1832070p/?cm_mmc=HK-PLA-DS3A-_-google-_-PLA_HK_CN_Semiconductors_Whoop-_-(HK:Whoop!)+Temperature+%26+Humidity+Sensor+ICs-_-1832070P&matchtype=&pla-805203104560&gclid=EAIaIQobChMIq83W8uj98gIV1) which can afford 55 to +150 °C ±5°C, 8-Pin SOIC N

Unit 4 called FWAG, but no found the record on Google, presumably flash memory. Unit 5 and 6 are also small and I can not check chip number.

Unit 7 is 25SNRG which is a chip for store memory, and I checked it working well.![image](.\assets\img\posts\stock\20210925_6.png)

We have applied the sensor to patients and got the txt format data when they came back. 
![image](.\assets\img\posts\stock\20210925_7.png)
![image](.\assets\img\posts\stock\20210925_8.png)
![image](.\assets\img\posts\stock\20210925_9.png)
![image](.\assets\img\posts\stock\20210925_10.png)

I used excel and MATLAB draw some graphs but an interesting incident was that all the sensor just recorded the data at most 3 days, and then they stopped. What's worse is that one of them just recorded one day only. But the manufacturer claimed that it can recorded the data at least 3 months.

We want to know what happened and we will discuss more in the next stage.


