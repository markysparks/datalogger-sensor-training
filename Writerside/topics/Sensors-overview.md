
# Sensors overview

In the Met Office we use a variety of sensors to measure meteorological parameters such as temperature,
wind speed, pressure etc. Whilst these sensors can vary greatly in design and the technology used to measure
these parameters, they can be divided into two categories based upon how they present their data output to
the end user; **analogue** or **digital**. The type of output determines how we can connect to and record data
from the sensor.

## Analogue sensors

This type of sensor outputs a voltage, current, resistance or frequency pulse that varies proportionally and
in a predictable manner with parameter being measured. This output has to accurately measured and then
converted to an actual reading (e.g. temperature, humidity, wind speed) by e.g. a datalogger. Example of
output ranges include 0-20mV and 0-1v for a voltage output. The sensor may have a built-in amplifier to lift
the output to a more easily measurable range such as 0-5v.

### Examples of analogue sensors

* HMP110 humidity sensor outputs 0v at 0% humidity and 1v at 100% humidity. This sensor can also be configured
  to output a digital reading. Two analogue outputs are provided, one for humidity and the other for
  temperature from the inbuilt Pt1000 electrical resistance sensing element.
  ![HMP110 Humidity and temperature probe](HMP110.jpeg){ width=200 }
* CMP10 solar radiation pyranometer. A thermopile sensing element generates a 0-20 millivolt output from
  incoming short wave solar radiation. No analogue signal amplification occurs. This device is also available
  in a digital version.
  ![CMP10 Solar radiation sensor](CMP10.jpeg){ width=200 }
* Pt100 temperature sensor. This consists of a film of platinum embedded in a protective sheath, whose
  electrical resistance varies in a known manner with temperature. The "Pt" refers to platinum and the "100"
  refers to its resistance at 0°C in ohms. As temperature increases, the resistance increases in a precisely
  defined, linear manner.
  ![TempVue10](TempVue10.png){ width=400 }

## Digital sensors

These sensors transmit an actual reading of the parameter being measured e.g. `21.3` often in the form of
an [ASCII](#glossary) formatted text string e.g.

`T= 21.3 C  H= 79 % P= 1012.5 hPa`

but the data could also be in a binary format message or protocol e.g. ModBus, UMB. The electrical interface
to the sensor could be [RS232](#glossary) or [RS485](#glossary). Internally the sensor will make an analogue
measurement but this is processed onboard the sensor so that an actual reading is presented to the user.

### Examples of digital sensors

* PTB330 pressure transmitter - RS232 interface with ASCII string of the format:

`P1  1007.14 ***.* * 1007.2 1007.1 1007.1 000E8`

This instrument normally has 3 pressure sensing
elements so that a mean value can be provided in addition to each individual pressure reading. Excessive
differences between the readings can be used to flag a suspect sensor. The unit can also be specified with a
built-in display screen as well as optional analogue and RS485 outputs.

![PTB330](PTB330.jpeg){ width=200 }
* Thies ultrasonic wind sensor - RS485 full duplex (4-wire) with ASCII string output of wind direction and
  speed.
  ![Thies ultrasonic](thies_ultrasonic.jpeg){ width=200 }
* Lufft SHM31 snow depth sensor - RS485 half duplex, snow depth readings are requested from the instrument
  using the [UMB](#glossary) binary or ASCII protocols. Additionally, many other parameters such as laser
  temperature, measurement distance etc. can be requested from the instrument.
  ![Lufft SHM31](lufft_shm31.jpeg){ width=200 }

## Analogue vs. Digital

All the sensors we've mentioned so far can be considered analogue as far as the measurement of a
meteorological parameter is concerned. This should not be surprising since we are usually measuring analogue
changes in the atmosphere. What we refer to as a digital sensor is merely an analogue sensor with extra
built-in electronics and processing to make the analogue measurement and transmit an actual reading. In fact,
digital sensors are more properly called 'instruments' since they consist of more than just an analogue
sensing element.

Such instruments are easier to connect to another digital device such as a PC since most computers don't have
the electrical interfaces required to accurately measure small voltages, current or resistance, but they do
normally need some configuration before use. Analogue sensors tend to be simpler and don't require
configuration and setup, however you need to connect them to a specialist device such as a datalogger that has
the electrical interfaces that can measure analogue inputs accurately and stably. The conversion to a usable,
digital value is then done by the dataloggers internal processing, usually under the control of a datalogger
program.

These days, many sensors can provide both digital and analogue outputs.

## Analogue Sensor interfacing

## Digital sensor interfacing to a PC

### Serial settings

### RS232 connections

### RS485 connections

## Glossary

A glossary of various terms used on this webpage:

Sensor
: A sensor is a device that detects and responds to changes in physical conditions like heat, light, sound,
pressure, magnetism or motion and converts them into a measurable signal. Sensors measure physical quantities
and convert them into signals which can be read by observers or by instruments.

Interface
: An electrical interface is a shared boundary that allows the transfer of electrical signals between two
electrical devices or systems. It establishes the standards for how voltage levels, frequencies, and signal
durations are transmitted across the connection.

ASCII
: ASCII (American Standard Code for Information Interchange) is a character encoding standard that represents
English letters, digits, and other basic symbols through a binary code. It assigns a unique numeric value to
each character and symbol, allowing computers and other devices to communicate and process text data in a
standard format. ASCII is commonly used for text files and communication protocols.

RS232
: RS-232 (Recommended Standard 232) is a widely used communication standard for serial transmission of data
between devices (e.g. a digital sensor and computer). It defines the electrical and mechanical characteristics
of the interface, including signal levels, timing, and connector pin-outs.
Some key aspects of RS-232 include:
- Uses +/-12V voltage levels for logic 0 and 1 signals instead of TTL standard 0-5V.
- Asynchronous serial communication where data is transmitted one bit at a time over a single line.
- Common baud rates include 110, 300, 1200, 2400, 9600, 19200, 38400, 57600 and 115200 bits per second.

RS485
: RS-485 is a standard defining the electrical characteristics of drivers and receivers for use in serial
communications systems. It allows for multipoint connections and can communicate over long distances. RS-485
uses differential signaling to transmit data signals over a pair of wires. This gives it several advantages
over single-ended signaling schemes like RS-232, including better noise immunity and ability to interface
multiple devices using a bus topology. RS485 allows for half-duplex communication, where data can be
transmitted and received on the same pair of wires
- Common baud rates include 110, 300, 1200, 2400, 9600, 19200, 38400, 57600 and 115200 bits per second.

Full duplex, half duplex
: When using an RS485 electrical interface, full duplex mode allows simultaneous transmission and reception of
data, enabling bidirectional communication between devices (using 4 wires). In contrast, half duplex mode only
allows one-way communication at a time, with devices taking turns transmitting and receiving data (uses 2
wires).

ModBus
: Modbus is a communication protocol used in industrial automation to establish communication between
electronic devices. It enables the exchange of data between a master device (like a computer or controller)
and multiple slave devices (such as sensors, actuators, or other controllers) over serial lines or TCP/IP
networks. Modbus is widely adopted due to its simplicity, versatility, and interoperability across various
manufacturers' devices. Modbus defines a protocol data unit (PDU) that is independent of the lower layer
protocols in the protocol stack and allows for the mapping of the Modbus protocol on specific buses or
networks.

UMB
: The Lufft UMB (Universal Measurement Bus) protocol is a communication protocol used by Lufft environmental
sensors to transmit measurement data. It defines a standard format for sensors to send measurements and status
information in a binary or ASCII format. The UMB protocol uses a colon ':' as a block separator and addresses
each sensor with its unique UMB address. It allows for flexible connection of multiple sensors to a single
datalogger or converter unit.

Datalogger
: A data logger is an electronic device that records data over time from one or more external sources such as
sensors. Data loggers measure and record parameters such as temperature, humidity, voltage, pressure and more.
They are commonly used for monitoring environmental conditions, equipment performance and other
industrial/scientific applications. Data loggers are small, portable devices that store recorded data
internally on memory cards or remotely transfer the data to a computer or cloud for viewing and analysis.