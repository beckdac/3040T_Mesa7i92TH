# 3040T_Mesa7i92TH
linuxcnc config for a 3040T controlled via MESA 7i92TH

## important note for this config and home made pendant
From this [page](https://hackaday.io/project/6776-3040-cnc-milling-machine-mods):
* To enter into a mode connect momentarily either P3.0/P3.1/P3.2 to GND while spindle enable is off. P3.0 is dial, P3.1 is PWM and P3.2 is +/- buttons mode. Now enable the spindle and control the speed. To control the speed in +/- buttons mode, P3.0 is + and P3.2 is -.

* P3.6, P5.4 and P5.5 are serial pins that go to a seven segment driver IC, looks to be TM1638. P3.6 is CLK, P5.4 is DIO and P5.5 is STB. From what I've decoded on my oscilloscope, the display says which mode you are in, current state of the spindle (on/off) and the spindle set speed represented as a percentage. Data in the image below is reversed, should have been LSB. 0xC0, 0x73, 0x89, 0xC2, 0x06, 0x89, 0xC4, 0x40... If the TM1638 is used, more buttons might be available.
