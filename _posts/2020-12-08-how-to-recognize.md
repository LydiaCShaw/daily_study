---
layout: post
read_time: true
show_date: true
title: How to recognize the different movements of the hand? 
date:   2020-12-08 08:00:20 -0600
description: How to recognize the different movements of the hand? 
img: posts/20201208/6.png
tags: [EMG, feature extraction, signal processing]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
## Signal processing
When we get the signal from the electrode like the following picture shown, in order to get more clearly wave, we pass it through the filter to eliminate the noise. That is an EMG signal sample, it has some peaks, and the yellow line means one can divide the signal into windows of different sizes. MUP means motor unit potential which can see it as the feature vector, which would distinguish different kinds of signals, and finally combine them for the classifier do the next work. 
![image](https://raw.githubusercontent.com/HEU-F8-PRACTICE/stor/master/20210708/ab6b558efba54a249c9680e83194a852/ab6b558efba54a249c9680e83194a852.png)

The images are ten motions of our hands.Different motions means different  signals, and what we should do is making computers distinguish them and let the prosthesis do the same motions.
## Feature values
Common feature values are divided into time  and frequency domain,the transformation may be considered such as short time Fourier, wavelet transform and so on. At that time, we can see the figure on the left hand side is power spectrum density of EMG signals.
![image](./assets/img/posts/20201208/2.png)
To the naked eye, the waves is almost similar. Therefore, just using the PSD is not enough. So how to do the next work? 
Firstly we choose the wavelet transform and calculate values such as Continuous wavelet coefficients, and the second one is Fourier transform. Cfai means admissibility condition, which we use of a wide variety of mother wavelet functions, and they need to satisfy it. I just try to explain the progress of feature extraction,  so the specific values would not be considered at that time.

## Wavelet transform
So just now I mentioned the method of transformation, yeah, we use the wavelet transform, so that is a decomposition tree, in this case, we choose the forth decomposition level so that we can get the signal better.
![image](https://raw.githubusercontent.com/HEU-F8-PRACTICE/stor/master/20210708/69f634941e2ab1882aa7025349330339/69f634941e2ab1882aa7025349330339.png)
## Signal decomposition
Now, we can see, that is the image of segmented EMG in a 256-points window from one subject performing 10 hand motions, when we do the feature extraction, 40 segmented signals for each motion had been prepared, and the flow chart is so clearly that we can see the next step, we just need to calculate the six values and combine them, the specific functions I have illustrated on the right hand side. 
![image](https://raw.githubusercontent.com/HEU-F8-PRACTICE/stor/master/20210708/f17de97f4d876d19da84771d01866648/f17de97f4d876d19da84771d01866648.png)
To make it easier to analyse, normalization of six features are supposed to be added in the step, and finally we can get the feature vectors.

## Feature extraction

![image](https://raw.githubusercontent.com/HEU-F8-PRACTICE/stor/master/20210708/2d2e066ffdd11499959f69dc2c6d0dbc/2d2e066ffdd11499959f69dc2c6d0dbc.png)
Now,the figure on the left hand side is six feature values. All these features are normalized to make the calculations consistent. SA feature was one of the features showing better classification performance for  EMG signals comparing to the others. 
Therefore,it was considered the main feature to define the mother wavelet matrix. And the matrix is shown on the right hand side, the horizontal/vertical numbers corresponds to 10 motions respectfully. Then, we can get the feature vectors after determining the  matrix.

![image](https://raw.githubusercontent.com/HEU-F8-PRACTICE/stor/master/20210708/8f7116c2a1802b461aa594a6e17868eb/8f7116c2a1802b461aa594a6e17868eb.png)
## Conclusion
We know that different movements have different signals. By doing the feature extraction, one can obtained some values which can distingish these movements. This is still useful for people with disabilities who have missing parts of their upper limbs.
A surgical technique called targeted muscle reinnervation (TMR) transfers residual arm nerves to alternative muscle sites. After reinnervation, these target muscles produce electromyogram  signals on the surface of the skin that can be measured and used to control prosthetic arms.
After surgery, patients’ nerve can be transplanted to other place, such as biceps or triceps,therefore, EMG signals would be similar which can be recognized using these method. Therefore, it is necessary to recognize the signals of these 10 motions so that computers can recognize these signals to help the patient complete the action.


