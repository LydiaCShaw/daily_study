---
layout: post
read_time: true
show_date: true
title:  Microfluidic Device and Stem cells
date:   2021-04-25 13:32:20 -0600
description: Microfluidic device can finish some manipulation so that it is applied in stem cells study.
img: posts/20210425/microfluidic chips.png 
tags: [microfluidic chips, stem cells, microfluidic device]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
I chose the topic of microfluidic device and stem cells study as my assignment. In recent days, I read some articles and wrote something new for me.

## What is microfluidic device?

Microfluidic device belongs to a type of micro device that finish some manipulation such as sample pretreatment, delivery, reaction, separation, detection and analysis. Due to its small fluid volumes (μL,nL,pL), utilizing microfluidic device to bioanalysis can reduce device size. The unique advantages are fast analysis speed, short response time, low amount of samples and waste and particular physical consequences of micro-scale fluid flow make it popular in biomedical field nowadays.

<center><img src='./assets/img/posts/20210425/microfluidic chips2.png'></center>
The core technique of microfluidic device is microfluidic chip. Meanwhile, a device set also needs medium reservoir, pump etc. The microfluidic chip mainly includes inlets, outlets and microchannel. The microchannel part can be designed different pattern depending on different requirements.

## What is stem cells?

Stem cells(SCs) are originated from two main sources, adult body tissues and embryos.it is available to differentiate any kind of cells and it proliferates indefinitely in vitro. 
<center><img src='./assets/img/posts/20210425/stem cells.png'></center>
Depending on different sources, researchers can extract and culture embryonic stem cells (ESCs) from embryos. As figure shown, as the level of stem cells declines, their capabilities are getting weaker and weaker. Compared to ESCs, these multipotency stem cells lose some abilities, which means they can only differentiate partly categories of cells. For example, hematopoietic stem cells (HSCs) produce blood and immune cells; neural stem cells (NSCs) can differentiate different kinds of neurons, Mesenchymal stem cells (MSCs) can be differentiated into osteoblasts, adipocytes, and chondrocytes etc.

## Why choose microfluidic chips?
When SCs are in vivo, they are in a 3D dynamic microenvironment. At that time, these cells can interact with surrounding cells or extracellular matrix (ECM) easily. They are exposed to low oxygen content and growth factor gradients which is very important to cell behaviors including differentiation, interaction, metabolism, apoptosis, self-renewal,etc. 
The interaction between cells and environment provides some signals for regulating cell responses. Different signals represent different cell responses. Considering this mechanism, it is difficult to simulate these different signals in vitro culture. In traditional approaches, we may use two-dimensional culture. At that time, it is difficult to simulate real biomechanics such as fluid flow and shear stress.Therefore, in vitro experiment often trigger unexpected differentiation and death rate is high. When stem cells are in microfluidic channel, the channel can provide a real 3D microenvironment for stem cells.
## Microchannel Design
Microchannel design is the first step. Before we fabricate microfluidic device, we may imagine what channel we want. Channel design is highly related to the experiment purpose.
<center><img src='./assets/img/posts/20210425/microchannel.png'></center>
Picture 1,2 and 3 are common microfluidic platforms in experiment. Authors tend to utilize this kind of microfluidic platforms to analyze various properties and behaviors of cells. For example, device in picture 1 is often used to study biophysical regulation of SCs. Authors developed the micropores combined with multichannel so that it is easier to analyze cell properties. Device in picture 2 is often used to study the dynamics of intercellular communication between two kinds of cells. Microdroplet device in picture 3 was developed to avoid contamination.
Concentration gradient generators in 4,5 was developed for simulating the biochemical microenvironment in vivo. It has been proved that a wide range of biological process including proliferation, migration, differentiation are determined by the gradient of specific molecular cues.
## Fabrication Methods
The picture shown the fabrication process of a multilayer microfluidic device to study cell migration. The photoresist they used is SU-8, which is a negative photoresist. They wanted to made two master with different thick, exposed to UV light and developed.
<center><img src='./assets/img/posts/20210425/fabrication.png'></center>
After obtaining two masters, they made two molds, mold A and mold B. The material of mold is PDMS. PDMS were poured on master 1 to obtain the mold A. After the mold cures, remove PDMS housing and punch a hole into the port with a biopsy puncher, insert a PEG tube into the port and seal it with a compression fitting. 
The inner layer is PEG hydrogel. It was made by using PEGDA and photoinitiator exposing UV light. The photocrosslink response occurred and PEG hydrogel can be obtained. 
Meanwhile, mold b was obtained using the same method.  The difference is mold B would directly primed PEG hydrogel into the port and do not use master 2. Mold B also needs photocrosslink. 
When this procedure finished, two molds were spliced together. Align and contact mold A with mold B, the crosssection is 3D microchannel.

## Surface Modification
Considering some cell adhesion peptides such as RGD peptides can respond to external stimuli and transmit signals to the cytoskeleton, affecting cell behaviors. 
Some authors proposed to add some substrates in hydrogel or coat on the PDMS surface. Therefore, when they fabricate microchip, surface modification is one of the procedure. Some studies proved it made sense. For example, when PDA was coated on PDMS surface, the biocompatibility would increase so that the chip is more stable. Adding collagen type 1 can improve cell adhesion. Adding PAAc can enhance the ability of specific differentiation.
<center><img src='./assets/img/posts/20210425/modification.png'></center>

## Biomedical Application
It can be widely used for SC analysis in biophysical regulation, cell-cell interaction,biochemical regulation and adhesive ligands regulation,etc. Meanwhile, it can also be used in SC culture, differentiation,building extracellular scaffolds and tissue engineering.
<center><img src='./assets/img/posts/20210425/application1.png'></center>
In recent years, some new functional hydrogels have been developed to construct extracellular scaffolds for SC culture. Microfluidic devices can use hydrogels as a more physiologically 3D matrix. 
By utilizing microchips for precise manipulation, cell-containing hydrogels can be fabricated to diverse geometric shapes and structures. The images shown the whole procedure of scaffold fabrication.
It used microdroplet, SCs incorporated during the formation of scaffold, a 3D notwork can be built which promotes cell migration and proliferation and leads to rapid regeneration of skin tissue in the experiment.
<center><img src='./assets/img/posts/20210425/application2.png'></center>
Organs-on-a-chip are based on microfluidic cell culture to simulate the physiological functions of tissues and organs just using the smallest functional unit that can summarize the function of tissue and organ.
Precisely controlling the differentiation of SCs in a microfluidic microenvironment can realize tissue engineering and the development of organs-on-a-chip. In order to realize heart-on-a-chip, the patient’s cardiomyocytes were extracted, using IPSCs technology combined with tissue engineering to produce a similar condition in the body on the chip so that the pathogenesis were identified successfully.
Another example is vascular on a chip. Authors constructed a 3D functional and perfusible microvascular network which is composed of human endothelial cells and MSCs phenotype transitioning to parietal cells. Unfortunately, this microvascular network did not have a functional role. After adding angiopoietin, the system generated perfusible capillaries.
The right hand side pictures are extrusion 3D bioprinting technique. It has two material PDMS microfluidic printhead with integrated pneumatic valves and coaxial flow focusing extruder capable of generating hydrogel fibers.
Integration with a 3-axis positioning system and custom software enables a variety of multimaterial structures to be fabricated just like 5 and 6 picture shown.
Meanwhile, the Flow control over the ratio of hydrogel and crosslinker flow rate enables sequenced 2-material fibers in 7th picture yellow and read with on-the-fly control over fiber diameter. 
## Conclusion
Retrospecting articles, microfluidic techniques still have great potential especially on the extracellular scaffolds and tissue engineering.It is expected that more and more microfluidic devices and microchannel design. The future development may focus on lab-on-a-chip which is towards monolithic organs and clinical applications.
Although some microvascular network and human skin can be obtained according some research mentioned above, the main problem is that due to the size limitations, it is difficult to realize large tissues and organs in microfluidic channels, which may require to combine with other techniques. Although advanced microfluidic technology faces some challenges, due to its 3D properties, it will become a useful tools for SC study.
## Reference
[1]D.-K. Kang, J. Lu, D.-K. Kang, J. Lu, W. Zhang, E. Chang, M.A. Eckert, M.M. Ali& W. Zhao.(2013). Microfluidic devices for stem cell analysis.Woodhead Publishing Series in Biomaterials.11,388-441.ISBN 9780857096975,
https://doi.org/10.1533/9780857097040.3.388.
[2]Keller G. (2005). Embryonic stem cell differentiation: emergence of a new era in biology and medicine. Genes & development, 19(10), 1129–1155. https://doi.org/10.1101/gad.1303605
[3]Hashemzadeh, H., Allahverdi, A., Sedghi, M., Vaezi, Z., Tohidi Moghadam, T., Rothbauer, M., Fischer, M. B., Ertl, P., & Naderi-Manesh, H. (2020). PDMS Nano-Modified Scaffolds for Improvement of Stem Cells Proliferation and Differentiation in Microfluidic Platform. Nanomaterials (Basel, Switzerland), 10(4), 668. https://doi.org/10.3390/nano10040668
[4]Cuchiara, M. P., Allen, A. C., Chen, T. M., Miller, J. S., & West, J. L. (2010). Multilayer microfluidic PEGDA hydrogels. Biomaterials, 31(21), 5491–5497. https://doi.org/10.1016/j.biomaterials.2010.03.031
[5]Geiger, B &Bershadsky,A.(2002).Exploring the neighborhood: adhesion-coupled cell mechanosensors.Cell.110(2),139-42.
[6]Menon, N. V., Chuah, Y. J., Phey, S., Zhang, Y., Wu, Y., Chan, V., & Kang, Y. (2015). Microfluidic Assay To Study the Combinatorial Impact of Substrate Properties on Mesenchymal Stem Cell Migration. ACS applied materials & interfaces, 7(31), 17095–17103. https://doi.org/10.1021/acsami.5b03753
[7]Chuah, Y. J., Koh, Y. T., Lim, K., Menon, N. V., Wu, Y., & Kang, Y. (2015). Simple surface engineering of polydimethylsiloxane with polydopamine for stabilized mesenchymal stem cell adhesion and multipotency. Scientific reports, 5, 18162. https://doi.org/10.1038/srep18162
[8]Mahadik, B. P., Pedron Haba, S., Skertich, L. J., & Harley, B. A. (2015). The use of covalently immobilized stem cell factor to selectively affect hematopoietic stem cell activity within a gelatin hydrogel. Biomaterials, 67, 297–307. https://doi.org/10.1016/j.biomaterials.2015.07.042
[9]Chuah, Y. J., Kuddannaya, S., Lee, M. H., Zhang, Y., & Kang, Y. (2015). The effects of poly(dimethylsiloxane) surface silanization on the mesenchymal stem cell fate. Biomaterials science, 3(2), 383–390. https://doi.org/10.1039/c4bm00268g
[10]Song W, Wang X, Lu H, Kawazoe N, Chen G. (2012).Exploring adipogenic differentiation of a single stem cell on poly(acrylic acid) and polystyrene micropatterns. Soft Matter 8(32), 8429.
[11]Khademhosseini, A., Ferreira, L., Blumling, J., 3rd, Yeh, J., Karp, J. M., Fukuda, J., & Langer, R. (2006). Co-culture of human embryonic stem cells with murine embryonic fibroblasts on microwell-patterned substrates. Biomaterials, 27(36), 5968–5977. https://doi.org/10.1016/j.biomaterials.2006.06.035
[12]Hui, E. E., & Bhatia, S. N. (2007). Micromechanical control of cell-cell interactions. Proceedings of the National Academy of Sciences of the United States of America, 104(14), 5722–5726. https://doi.org/10.1073/pnas.0608660104
[13]N. L. Jeon, S. K. W. Dertinger, D. T. Chiu, I. S. Choi, A. D. Stroock, & G. M. Whitesides.(2000). Generation of Solution and Surface Gradients Using Microfluidic Systems. Langmuir, 16, 8311-8316.
[24]Irimia, D., Geba, D. A., & Toner, M. (2006). Universal microfluidic gradient generator. Analytical chemistry, 78(10), 3472–3477. https://doi.org/10.1021/ac0518710
[25]X.Z. Niu, F. Gielen, J.B. Edel& A.J. Demello.(2008). A microdroplet dilutor for high-throughput screening.Nat Chem, 3. 437-442
[16]Shamloo, A., Ma, N., Poo, M. M., Sohn, L. L., & Heilshorn, S. C. (2008). Endothelial cell polarization and chemotaxis in a microfluidic device. Lab on a chip, 8(8), 1292–1299. https://doi.org/10.1039/b719788h
[17]M. Yamada& M. Seki. (2005). Hydrodynamic filtration for on-chip particle concentration and classification utilizing microfluidics. Lab Chip, 5 ,1233-1239.
[18]H.B. Wei, B.H. Chueh, H.L. Wu, E.W. Hall& C.W. Li, R. Schirhagl, J.M. Lin, R.N. Zare.(2011). Particle sorting using a porous membrane in a microfluidic device.Lab Chip, 11,238-245
[19]Titmarsh, D. M., Glass, N. R., Mills, R. J., Hidalgo, A., Wolvetang, E. J., Porrello, E. R., Hudson, J. E., & Cooper-White, J. J. (2016). Induction of Human iPSC-Derived Cardiomyocyte Proliferation Revealed by Combinatorial Screening in High Density Microbioreactor Arrays. Scientific reports, 6, 24637. https://doi.org/10.1038/srep24637
[20]Matsumura, T., Tatsumi, K., Noda, Y., Nakanishi, N., Okonogi, A., Hirano, K., Li, L., Osumi, T., Tada, T., & Kotera, H. (2014). Single-cell cloning and expansion of human induced pluripotent stem cells by a microfluidic culture device. Biochemical and biophysical research communications, 453(1), 131–137. https://doi.org/10.1016/j.bbrc.2014.09.081
[21]Alessandri K, Feyeux M&Gurchenkov B.(2016). A 3D printed microfluidic device for production of functionalized hydrogel microcapsules for culture and differentiation of human neuronal stem cells (hNSC). Lab Chip 16(9), 1593–1604.
[22]Pavesi A, Adriani G, Rasponi M, Zervantonakis IK, Fiore GB&Kamm RD.(2015). Controlled electromechanical cell stimulation on-a-chip. Sci. Rep. 5, 11800
[23]Griffin, D. R., Weaver, W. M., Scumpia, P. O., Di Carlo, D., & Segura, T. (2015). Accelerated wound healing by injectable microporous gel scaffolds assembled from annealed building blocks. Nature materials, 14(7), 737–744. https://doi.org/10.1038/nmat4294
[24]Jeon JS, Bersini S& Whisler JA. (2014)Generation of 3D functional microvascular networks with human mesenchymal stem cells in microfluidic systems. Integr. Biol. (Camb.) 6(5), 555–563 .
[25]Davoodi, Elham & Sarikhani, Einollah & Montazerian, Hossein & Ahadian, Samad & Costantini, Marco & Swieszkowski, Wojciech & Willerth, Stephanie & Walus, Konrad & Mofidfar, Mohammad & Toyserkani, Ehsan & Khademhosseini, Ali & Ashammakhi, Nureddin. (2020). Extrusion and Microfluidic‐Based Bioprinting to Fabricate Biomimetic Tissues and Organs. Advanced Materials Technologies. 5. 1901044. 10.1002/admt.201901044.