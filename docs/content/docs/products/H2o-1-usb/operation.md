---
title: Operation
weight: 20
---
# SaveH2o

{{< hint info >}}
**Saving water saves lives.**
{{< /hint >}}

This is the *User's Guide* for the alfa test version of **H2o-1-usb** prototype that passed all dry-tests at *developer's lab*. The [manufacturing workflow](https://opsdog.com/categories/workflows/production) is expected as follows:

- **Product planning**: which product to make?
- **Manufacturing Engineering**: which components/software to use?
- **Manufacturing Assembly**: set up the facility for production runs.
- **Quality Assurance**: inspecting products after manufacturing.
- **Facility Management**: maintaining the manufacturing facility.

We are now at **Manufacturing Engineering** stage. After passed the [dry alfa tests](https://github.com/SaveH2o/arduino/issues/3) at the *developer's lab*, the **H2o-1-usb** prototype expects to be submitted to [wet alfa tests](https://github.com/SaveH2o/arduino/issues/4) at the *product's lab*.

The objective is to measure/verify/certify product behaviour, evaluate its market potential, and create valuable reports to feedback developers and product managers to start the **Manufacturing Assembly** phase.

## H2o-1-usb

- Model: H2o-1-usb
- Hardware: h2o-1-usb-r1
- Firmware: h2o-1-v0.032 available on [github](https://github.com/SaveH2o/arduino).

### Alerts

- 2-short-beeps: hello after power on reset
- 3-short-beeps: leak alarm
- led turn on together with buzzer beeps

### Programmable parameters

- start alarm 30 s after running non-stop (alarm_count = 30L)
- stop for 60 s to clear alarm/non-stop status (stop_filter = 60L)

### Real time data logging 

The **H2o-1-usb** is equipped with a serial port that issues a real time data logging of water flow speed for testing and supervisory activities. In order to activate it, run the *Arduino IDE* and launch the Serial Monitor by:
- digiting CTRL-SHIFT-M at the keyboard or
- selecting *Tools | Serial Monitor* from the menu.

The prototype h2o-1-v0.03 generate a real-time series of data with measures of the periods of the pulses generated by the water flow sensor. The following parameters apply, in order to support several water flows sensors with minimal changes in the software:

- *periodcount* is the period of the pulse generated by flow sensor
- *lapcount* = 4 pulses/turn for [YF-S201](https://www.aliexpress.com/item/32958118358.html) Water Flow Sensor
- *unit* = 4 us, is the unit time of each count

Then, the rotation speed of water flow sensor internal wheel can be measured by the following formula:

{{< katex >}}
\begin{aligned}
   periodtime&=periodcount*lapcount*unit \\
   &=periodcount*4*4\mu s \\
   &=periodcount*16*10^{-6} \,s \\

   frequency&=\frac{1}{periodtime} \,Hz
\end{aligned}
{{< /katex >}}


If there´s no water flowing on the sensor, the screen shows a stop count, as shown below. The sample rate is one line per second:

![image](https://user-images.githubusercontent.com/86032/93905605-894b4f80-fcd1-11ea-8e28-fb4930ef299d.png)

When water starts flowing, the screen shows samples, containing the periods of the pulses sent by the sensor. For the [YF-S201](https://www.aliexpress.com/item/32958118358.html) sensor, each pulse means that 1/4 of internal wheel rotation has ocurred. The time unit, or the resolution of this measure is 4 microseconds.

![image](https://user-images.githubusercontent.com/86032/93906287-64a3a780-fcd2-11ea-8994-4dd9c836be19.png)

At the above log, the first *periodcount* shows 1.520.477.425. Multiplying it for 4 us, we conclude the water flow has stopped for 608 seconds. 

If the water keep flowing, after non-stop count reaches a programmable count (*30* for alfa test), the alarm is activated with a continuous 3-short-beeps. The real time log keep showing *periodcounts*, as shown below.

![image](https://user-images.githubusercontent.com/86032/93910478-85223080-fcd7-11ea-880d-b0dabf160154.png)

The alarm is automatically reset after water flow stops for 60 seconds.

![image](https://user-images.githubusercontent.com/86032/93911225-81db7480-fcd8-11ea-96c2-0e1ba29c92eb.png)

All these parameters expect to be set/programmed by user. We should decide the best values/proceedings to apply.