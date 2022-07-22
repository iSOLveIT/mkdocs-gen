---
tags:
  - Commander
  - Architect
  - Python
---

# BBM Python Mates Controller Library


## Introduction

This library is developed to easily control Breadboard Mates modules from any computer that can run Python and connects with a BBM display module using a BBM Programmer or similar. This is based on the [Python Mates Controller library](python-mates-controller.md). Therefore, all methods are directly derived from it.


## Supported Devices

This library is developed for Python3 and designed to be used with any operating system as long as it is supported by the `pyserial` library and the BBM display module is connected using a BBM Programmer.


## Installation

This library can be installed from the Python Packaging Index (PyPI) by running the command:

``` bash
pip3 install bbm-mates-controller
```


## Constructors

This section serves to provide brief discussion about the constructors that can be used to initialize the library.


### MatesController(portName, resetFunction, debugStream, debugFileLength)

Constructs all the necessary attributes associated with an instance
of a Mates Controller Object.

| Parameters | Type | Description                                                            |
|:----------:|:----:| ---------------------------------------------------------------------- |
| portName   | str  | the name of the port to be opened. Example: `/dev/ttyUSB0` for Linux   |
| debugStream<br/>(optional) | io.TextIOWrapper | text file object to write debugging code to, supply of none will result in no debugging. Ex. `sys.stdout`, `open('log.txt', 'r+')` |
| debugFileLength<br/>(optional) | int | determines the extent of debug history kept with respect to lines in a file, given a circular log. O indicates full history kept with no circular logging. Users must be careful here to manage storage space effectively |

!!! note

    If a debug file is specified, it should be opened using either 'w+' or 'r+' before running the begin() function of this library.

??? example

    === "Simple"

        ``` py
        # Creates a new instance named 'mates' which utilizes: 
        #  - COM10 as the serial port
        #  - with no reset function and no output stream
        MatesController mates = MatesController("COM10") 
        ```

    === "Specify Debug Output"

        ``` py
        # Creates a new instance named 'mates' which utilizes: 
        #  - COM7 as the serial port
        #  - output_file as debug file stream
        #  - debugFileLength of zero indicating no circular logging
        MatesController mates = MatesController("COM7", debugStream=output_file, debugFileLength=0) 
        ```

        
## Methods

All methods are carried over from [Python Mates Controller library](python-mates-controller.md#methods) instance.