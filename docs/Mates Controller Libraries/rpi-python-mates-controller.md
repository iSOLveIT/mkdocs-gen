---
tags:
  - Commander
  - Architect
  - Python
  - Raspberry Pi
---

# Raspberry Pi Python Mates Controller Library


## Introduction

This library is developed to easily control Breadboard Mates modules from a Raspberry Pi Computer. This is based on the [Python Mates Controller library](python-mates-controller.md). Therefore, all methods are directly derived from it.


## Supported Devices

This library is developed for Python3 and designed to be used with any Raspberry Pi with the BBM display module connected to the GPIO pins. It is possible to connect BBM display modules to Raspberry Pi via USB connection using a BBM Programmer or similar. However, for this case, it is recommended to use the [BBM Python Mates Controller Library](bbm-python-mates-controller.md) instead.


## Installation

This library can be installed from the Python Packaging Index (PyPI) by running the command:

``` bash
pip3 install rpi-mates-controller
```


## Constructors

This section serves to provide brief discussion about the constructors that can be used to initialize the library.


### MatesController(portName, resetFunction, debugStream, debugFileLength)

Constructs all the necessary attributes associated with an instance
of a Mates Controller Object.

| Parameters | Type | Description                                                            |
|:----------:|:----:| ---------------------------------------------------------------------- |
| portName   | str  | the name of the port to be opened. Example: `/dev/ttyUSB0` for Linux   |
| resetPinIndex<br/>(optional) | int, str | index of pin connected to reset pin of Mates device             |
| resetActiveHigh<br/>(optional) | bool | whether the reset pin is driven from logic low or logic high to reset the device |
| debugStream<br/>(optional) | io.TextIOWrapper | Text file object to write debugging code to, supply of none will result in no debugging. Ex. `sys.stdout`, `open('log.txt', 'r+')` |
| debugFileLength<br/>(optional) | int | Determines the extent of debug history kept with respect to lines in a file, given a circular log. O indicates full history kept with no circular logging. Users must be careful here to manage storage space effectively |

!!! note

    If a debug file is specified, it should be opened using either 'w+' or 'r+' before running the begin() function of this library.

??? example

    === "Simple"

        ``` py
        # Creates a new instance named 'mates' which utilizes: 
        #  - /dev/ttyS0 as the serial port
        #  - with default reset pin (4) and no output stream
        MatesController mates = MatesController("/dev/ttyS0") 
        ```

    === "Specify Reset Pin and Mode"

        ``` py
        # Creates a new instance named 'mates' which utilizes: 
        #  - /dev/ttyS0 as the serial port
        #  - pin 4 as the reset pin
        #  - LOW pulse as active pulse
        MatesController mates = MatesController("/dev/ttyS0", resetPinIndex=4, resetActiveHigh=False)
        ```

    === "Specify Debug Output"

        ``` py
        # Creates a new instance named 'mates' which utilizes: 
        #  - /dev/ttyS0 as the serial port
        #  - output_file as debug file stream
        #  - debugFileLength of zero indicating no circular logging
        MatesController mates = MatesController("/dev/ttyS0", debugStream=output_file, debugFileLength=0)
        ```


## Methods

All methods are carried over from [Python Mates Controller library](python-mates-controller.md#methods) instance.