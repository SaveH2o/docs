---
title: Specifications
weight: 30
---
# SaveH2o

{{< hint info >}}
**Saving water saves lives.**
{{< /hint >}}

## H2o-1-usb

- Model: H2o-1-usb
- Hardware: h2o-1-usb-r1
- Firmware: h2o-1-v0.032 available on [github](https://github.com/SaveH2o/arduino).

The H2o-1-usb is **ready for manufacturing**, based on the following components:

- **1. CPU board**: Pro mini Atmega328P
- **2. SB serial converter**: USB 2.0 to UART TTL Serial Converter
- **3. Active Buzzer**: 5V DC with 85 dB noise output

## 1. Pro mini Atmega328P

- [Pro Mini 328 Mini ATMEGA328 3.3V 8MHz 5V 16Mhz](https://pt.aliexpress.com/item/32672852945.html).
- Arduino Compatible Nano CP2102 FT232RL.
- Open hardware component, many vendors are available.

![chip](https://store-cdn.arduino.cc/usa/catalog/product/cache/1/image/500x375/f8876a31b63532bbba4e781c30024a0a/e/0/e000025_iso.jpg)

- **Specs**: https://store.arduino.cc/usa/arduino-pro-mini
- **Getting Started:**: https://www.arduino.cc/en/Guide/ArduinoProMini
- **Software**: https://www.arduino.cc/en/Main/Software
- **Online IDE**: https://create.arduino.cc/editor

### Technical Specs

- **Microcontroller**:	ATmega328
- **Board Power Supply**:	3.35 -12 V (3.3V model) or 5 - 12 V (5V model)
- **Circuit Operating Voltage**:	3.3V or 5V (depending on model)
- **Digital I/O Pins**:	14
- **PWM Pins**:	6
- **UART**:	1
- **SPI**:	1
- **I2C**:	1
- **Analog Input Pins**:	6
- **External Interrupts**:	2
- **DC Current per I/O Pin**:	40 mA
- **Flash Memory**:	32KB of which 2 KB used by bootloader
- **SRAM**:	2 KB
- **EEPROM**:	1 KB
- **Clock Speed**:	8 MHz (3.3V versions) or 16 MHz (5V versions)

### Schematics

![image](https://user-images.githubusercontent.com/86032/89669657-3bf85780-d8b6-11ea-81cb-c118255e6033.png)

## 2. USB 2.0 to UART TTL Serial Converter

- CP2102 USB 2.0 to UART TTL 5PIN Module Serial Converter
- Many [compatible products](https://pt.aliexpress.com/item/32650176124.html) available.

![image](https://user-images.githubusercontent.com/86032/93827472-b51df500-fc3f-11ea-8a16-edda6fe1f689.png)

## 3. Active Buzzer

- Operating voltage: 4 to 8 VDC
- Operating current: 30mA
- Sound output (10cm): 85dB
- Frequency: 2300±300 Hz
- Operating temperature: -27 to +70 °C
- Material: ABS
- Color: Black
- Dimensions: 11,8 x 9mm

## Connections between components

### Water Flow Sensor

- **YF-S201 VCC**: connected to D9 (PB1/OC1A)
- **YF-S201 Signal**: connected to D8 (PB0/ICP)
- **YF-S201 GND**: connected to GND

### Active Buzzer

- **Buzzer +**: connected to D7 (PD7/AIN1)
- **Buzzer -**: connected to GND

### CPU & Converter

- **Converter RX**: connected to CPU TX
- **Converter TX**: connected to CPU RX
- **Converter DTR**: connected to CPU PC6/RESET
