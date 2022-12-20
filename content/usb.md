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

{{% details "#### 🗀 The ```codekitty``` module" %}} 

**To use (import):**

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

*Note: The color **black** sets the color to *off*.  This is especially useful for the Neopixels...

{{% /details %}}

{{% details "#### 🗀 Lights" %}}
The CircuitPlayground board in your robot has **ten multi-color LED lights** called *Neopixels*.
The Neopixels are numbered starting at 0 (**zero**) on the light to the left of the USB port, and going around counterclockwise. This means the pixels are numbered **0-9 and not 1-10**.

To use them, you specify which pixel (as a number 1-10) you want to work on, and then what color to make it. For example, to set the third LED to blue:
```python
pixels[2] = colors["blue"]
```

If you want to set *all* of the pixels, you can use the special *fill* method. For example, to set all the pixels to purple:
```python
pixels.fill(colors["purple"])
```

{{% /details %}}
{{% /details %}}


{{% details "#### 🗀 Time and Sleep" %}}
One (very) common task you will do when coding is to have your program **wait** a little bit. One of the built-in modules, **time**, contains a function called **sleep**.

For example, to have your program wait for two and a half seconds, first import the **sleep** function:

```python
from time import sleep
```

Then call **sleep** with an argument of *3* (for *3 seconds*):
```python
time.sleep(3)
```
{{% /details %}}
{{% details "#### 🗀 Sensors" %}}
A sensor is a device that measures something. Your CircuitPlayground board has 15 built-in sensors! Click the sections below to see how to use some of the sensors on your board:

{{% details "#### 🗀 Motion" %}}
The motion sensor on your CircuitPlayground board is called an *accelerometer*. They measure movement along the **X** (side-to-side), **Y** (forward/backward), and **Z** (up/down) axis. This requires a little bit of setup in your code, but allows you to do some really cool things!

If you want to see the values coming from the motion sensor, try this code:

```python
import time
import board
import adafruit_lis3dh
import busio

i2c = busio.I2C(board.ACCELEROMETER_SCL, board.ACCELEROMETER_SDA)
lis3dh = adafruit_lis3dh.LIS3DH_I2C(i2c, address=0x19)
lis3dh.range = adafruit_lis3dh.RANGE_8_G

while True:
    x, y, z = lis3dh.acceleration
    print((x, y, z))
    time.sleep(0.1)
```
{{% /details %}}

{{% details "#### 🗀 Light" %}}
There is a light sensor built in to your CircuitPlayground too! While it's not a *camera* and can't actually *see*, it can detect how much light there is.
To read the value of the light sensor into a *light* variable, use:
```python
import board
import analogio

light = analogio.AnalogIn(board.LIGHT)
print(light.value)
```
{{% /details %}}

{{% details "#### 🗀 Buttons" %}}
Your CircuitPlayground board has two buttons which you use in your code! The buttons are called Button_A and Button_B. For example, if you want to have Button_A turn on the red LED on your board, use:

```python
import time
import board
import digitalio

led = digitalio.DigitalInOut(board.D13)
led.switch_to_output()

button = digitalio.DigitalInOut(board.BUTTON_A)
button.switch_to_input(pull=digitalio.Pull.DOWN)

while True:
    if button.value:
        led.value = True
    else:
        led.value = False

    time.sleep(0.01)
```

{{% /details %}}


{{% /details %}}

{{% details "#### 🗀 Learn More" %}}
There is **so** much more you can do with your robot, and with the CircuitPlayground board in it! 

For way more details and tons of fun example projects, check out 

[Adafruit's Circuit Playground Bluefruit page!](https://learn.adafruit.com/adafruit-circuit-playground-bluefruit/circuitpython-playground)

{{% /details %}}


{{% /columns %}}
