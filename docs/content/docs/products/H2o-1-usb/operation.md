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


- 
- start alarm 30 s after running non-stop (alarm_count = 30L)
- stop for 60 s to clear alarm/non-stop status (stop_filter = 60L)