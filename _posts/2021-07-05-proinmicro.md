---
layout: post
read_time: true
show_date: true
title: Programming in microfluidic device
date:   2021-07-05 00:00:20 -0600
description: Programming language development for microfluidic device
img: posts/20210705/page.png
tags: [programming, microfluidic chips,microfluidic droplet,hydrogel]
author: Lydia Shaw
github:  Lydia Shaw
mathjax: yes
---
I ever wrote some science fictions, in which the mother of protagoist was a scientist that studied in biomedical. In order to study the super power gene, their team found a planet that had 10 times time flows faster than earth. According to Einstein's theory of general relativity, if they studied in this planet, results apparently obtained significantly more. Therefore, their team sent some microfluidic chips that carry human gene to the planet. These microfluidic chips may combine with tissue engineering or embryo engineering using programming to achieve the whole process from cell culture to generation. Although it was just a story written by me, I still wonder whether it can be realized. Recently, I read some articles about the programming used in microfluidic design. It seems like a good potential actually.

## Chip design
 According to author Qingyu Li, a synthesis tool has been developed to design and created microfluidic chips. Users can define different modules through Columba and determine the relationship between modules, and then generate the corresponding design diagram.
Because of the complex structure of biochips, manually designing a biochip involves lots of work, which leads to the need for design automation. Based on this growing demand, Dr.-Ing. Tsun-Ming Tseng developed Columba for automatic design of continuous-flow microfluidic biochips.
However, at presents, users must run the code through the web-based Columba platform by entering the script which is hard to some scientists who do not know how to program. These users may have biology or medical background. Therefore, the question is the syntax of the input script is complex.
Considering this, author designed a programming language to detect whether the user-defined design script is syntactically and logically correct, helping users to find out where corrections are needed, and reducing many unnecessary problems. Users can more easily generate the design of the microfluidic chip through the Cloud Columba platform. In the future, with the development of the Cloud Columba platform, this compiler can continue to expand, helping more biologists to use automated technology to more easily conduct biological experiments.

```
/* one of the javascript files */
function ChamberNode(name,x,y,z,p,s,c,spv) {
this.id=name;
this.x=x;
this.y=y;
this.z=z;
this.pump=p;
this.sieve_valve=s;
this.cell_trap=c;
this.seperate_valve=spv;
this.inflow=[];
this.outflow=[];
 }
m1=new ChamberNode(name,x,y,z,pump,sv,ct,spv)
```

If a multilayer neural network is added in this project, people add some microfluidic chip design as the training datasets, computer even can design chips automatically which would realize what I've written.
## Compositional Hydrogel
The high water content, tissue-like physicochemical properties, and ability to change their volume in response to external stimuli have made hydrogels the materials of choice for many biomedical applications. Due to the popular application such as neural tissues or bone tissues, hydrogel stiffnesses comprising several orders of magnitude, from a few tens of Pa up to megapascals, and a wide biochemical parameter space must be covered. Apparently these two examples have different parameters, and authors tended to develop a programming microfluidic system to solve the missing link that rapidly synthesize, process, and screen thousands of compositionally distinct microgels.
![image](./assets/img/posts/20210705/1.png)
Specifically, they worked from a library of reactive molecular hydrogel building blocks that can be combinatorially mixed to generate an unprecedented diversity of microgel formulations via droplet microfluidics. By programming the flow rates of different inlets supplying individual hydrogel components, they hypothesized that droplet composition can be systematically modulated, resulting in a population of microgels of hugely diverse composition upon crosslinking. Importantly, in order to determine the microgel properties easily after production, they aimed to employ fluorescent labels as proxies for targeted physical and chemical hydrogel parameters. This approach should permit the rapid screening and discovery of specific hydrogel formulations via conventional fluorescence microscopy or flow cytometry.

Here, authors presented a powerful microfluidic platform to generate combinatorial microgels with varying elasticity, biochemical composition, or both. An automated droplet microfluidics approach was employed to precisely mix fluorescently labeled hydrogel building blocks on chip via modulation of flow rates, resulting in the generation of microgels with highly controlled and modular composition.
This approach will be useful for the screening of multifactorial cell culture microenvironments for stem cell biology or cancer research. Furthermore, the versatility of this approach permits the generation of microgel formulations “on-demand,” permitting formulations to be targeted during the microbead production and without prior setup. Overall, this technique could provide rapid exploration of hydrogel formulations and give rise to novel compositions and applications of hydrogels, whether as microbeads or bulk gels.

## Droplet programming
Droplet microfluidics has become an indispensable tool for biomedical research and lab-on-a-chip applications owing to its unprecedented throughput, precision, and cost-effectiveness. Although droplets can be generated and screened in a high-throughput manner, the inability to label the inordinate amounts of droplets hinders identifying the individual droplets after generation. 

<iframe width="640" height="360" src="https://www.youtube.com/embed/GmXhiuj9w6k?list=PLnD4WkNzClnzyW9R23ErUUFK_8MPa2_mO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
Herein, they demonstrate an acoustofluidic platform that enables on-demand, real-time dispensing, and deterministic coding of droplets based on their volumes. By dynamically splitting the aqueous flow using an oil jet triggered by focused traveling surface acoustic waves, a sequence of droplets with deterministic volumes can be continuously dispensed at a throughput of 100 Hz. These sequences encode barcoding information through the combination of various droplet lengths. 
As a proof-of-concept, they encoded droplet sequences into end-to-end packages (e.g., a series of 50 droplets), which consisted of an address barcode with binary volumetric combinations and a sample package with consistent volumes for hosting analytes. This acoustofluidics-based, deterministic droplet coding technique enables the tagging of droplets with high capacity and high error-tolerance, and can potentially benefit various applications involving single cell phenotyping and multiplexed screening.
To efficiently exploit the potential of several millions of droplets that can be considered as individual bioreactors in microfluidic experiments, methods to encode different experimental conditions in droplets are needed(Svensson et al.,2019). The approach presented here is based on coencapsulation of colored polystyrene beads with biological samples. The decoding of the droplets, as well as content quantification, are performed by automated analysis of triggered images of individual droplets in-flow using bright-field microscopy.
 The decoding strategy combines bead classification using a random forest classifier and Bayesian inference to identify different codes and thus experimental conditions. 
 Antibiotic susceptibility testing of nine different antibiotics and the determination of the minimal inhibitory concentration of a specific antibiotic against a laboratory strain of Escherichia coli are presented as a proof-of-principle.
 It is demonstrated that this method allows successful encoding and decoding of 20 different experimental conditions within a large droplet population of more than 105 droplets per condition. The decoding strategy correctly assigns 99.6% of droplets to the correct condition and a method for the determination of minimal inhibitory concentration using droplet microfluidics is established. The current encoding and decoding pipeline can readily be extended to more codes by adding more bead colors or color combinations.
 
## Reference
 [1]Qingyu Li.(2019) Programming Language Development for Microfluidic Design.Technical University of Munich Department of Informatics
[2]S. Allazetta, A. Negro, M. P. Lutolf.(2017).Microfluidic Programming of Compositional Hydrogel Landscapes. Macromol. Rapid Commun.1700255.
[3]Svensson, C. M., Shvydkiv, O., Dietrich, S., Mahler, L., Weber, T., Choudhary, M., Tovar, M., Figge, M. T., & Roth, M. (2019). Coding of Experimental Conditions in Microfluidic Droplet Assays Using Colored Beads and Machine Learning Supported Image Analysis. Small (Weinheim an der Bergstrasse, Germany), 15(4), e1802384. https://doi.org/10.1002/smll.201802384
[4]Peiran Zhang ,Wei Wang,,Hai Fu,Joseph Rich, Xingyu Su, Hunter Bachman, Jianping Xia, Jinxin Zhang,a   Shuaiguo Zhao,Jia Zhou and  Tony Jun Huang.(2020) Deterministic droplet coding via acoustofluidics..Lab on a Chip(23)