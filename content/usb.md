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

{{% details "#### 🗀 Board" %}}

The Circuit Playground (express or bluefruit) circuit board in your robot comes with two motors connected to it (the yellow connectors on **A3** and **A6**). 

These two "analog pins" (**A3** and **A6**) are just two of the connectors you can use on your robot. These are defined in a special library called **board**, and if you want to use them, first do:

```python
import board
```

And then if you want to list all of the connections defined in **board**, do:

```python
dir('board')





To set one to a color, use:

```python
pixels[x] = colors['c']
```

{{% /details %}}

{{% /columns %}}
