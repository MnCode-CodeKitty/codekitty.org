+++
title = "Code your robot"
description = "Code your robot over USB"
keywords = ["robot","usb","python"]
+++

{{% columns %}}


**Hook up your USB cable, then click connect**

*Choose the connection with ACM in the name*

{{% xterm %}}

<--->
&nbsp; <br />
&nbsp; <br />
&nbsp; <br />

&nbsp; &nbsp; **(Click below for Instructions:)**

{{% details "### 🗀 Code Kitty module" %}}

#### To use (import): 
```python 
from codekitty import *
```

{{% details "#### 🗀 Moving" %}}

```python 
go(x)
```
drive forward for *x* seconds

```python 
back(x)
```
drive backward for *x* seconds

```python
left(x)
```
turn left for *x* seconds

```python
right(x)
```
turn right for *x* seconds

{{% /details %}}

{{% details "#### 🗀 Sounds" %}}
```python 
meow()
```
Have your kitty robot say "meow"

```python 
purr()
```
Have your kitty robot purrr (happy kitty!)

```python 
beep()
```
make a beep sound

{{% /details %}}

{{% details "#### 🗀 Colors" %}}

To use colors, use a value in the *colors[]* dictionary

```python
colors['c']
```
use a color (replace *c* with the name of the color)

```python
for c in colors[]: print c
```
list all the colors in colors[]

{{% /details %}}

{{% details "#### 🗀 Lights" %}}

- There are ten led lights called *Neopixels* on your robot.
- They are numbered 0-9 (not 1-10!) in a circle starting with the one to the left of the USB jack, and going around *counterclockwise*.
- *Note: setting a pixel to **black** turns it off!*

To set one to a color, use:

```python
pixels[x] = colors['c']
```

*where **x** is a number between 0 and 9, and **c** is the name of a color in colors[]*

To set them ALL, you can use a for() loop:

```python
for i in range(10):
  j=i-1
  pixels[j] = colors['*c*']
```

*(replace c with the name of the color)*

{{% /details %}}

{{% /columns %}}
