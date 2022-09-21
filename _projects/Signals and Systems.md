---
layout: page
title: Signals and Systems Course Projects
description: Different mini projects implemented as the course projects in the signals and systems course
img: assets/img/signal.png
importance: 4
category: AI
---
In this project a series of implementations were done related to the signals and systems course. The list of the projects are as bellow.

## Projects
- [Signal Plotting](https://github.com/mahvash-siavashpour/signals-and-systems/tree/master/signal-plotting)
- [Discrete Convolve](https://github.com/mahvash-siavashpour/signals-and-systems/tree/master/discrete-convolve)
- [Fourier Series](https://github.com/mahvash-siavashpour/signals-and-systems/tree/master/fourier-series)
- [Voice Code](https://github.com/mahvash-siavashpour/signals-and-systems/tree/master/voice-code)

### Signal Plotting
Using this implementation it is possible to plot functions both descrete and continouse. It is a simple code that used numpy and matplotlib python libraries.

### Discrete Convolve
Discrete convolve in a very importatnt mathematical tool used in signal processing. In this project a python code is written that implements this mathematical method. Some of the outputs of this project in illustrated:
<br>
{% include figure.html path="assets/img/convolve1.png" title="convolve" class="img-fluid rounded z-depth-1" %}
<br>
{% include figure.html path="assets/img/convolve2.png" title="convolve" class="img-fluid rounded z-depth-1" %}
<br>

### Fourier Series
Fourier series can be written as the summation of sinus and cosinus. If we follow this summation to the k=c, we will obtain an approximation of the signal x(t). The bigger the c, the more accurate the approximation. I have tested two function with k=10 and here are some of the approximations along the way.
<br>
{% include figure.html path="assets/img/ft1.png" title="ft" class="img-fluid rounded z-depth-1" %}
<br>
{% include figure.html path="assets/img/ft2.png" title="ft" class="img-fluid rounded z-depth-1" %}
<br>
{% include figure.html path="assets/img/ft3.png" title="ft" class="img-fluid rounded z-depth-1" %}
<br>
{% include figure.html path="assets/img/ft4.png" title="ft" class="img-fluid rounded z-depth-1" %}
<br>

### Voice Code
In this project a set of audios were given which had ASCII codes encoded in their frequency domain. In order to decode these audios first they were read and then the frequency domain data was extracted using apropriate functions. The codes started at the frequency of 300 KHz. A 64 bit code was extracted from each of these files.
