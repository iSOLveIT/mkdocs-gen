# Mates Studio Release Notes

#### 1.0.14 : May 5, 2022

- Fixed issue when opening projects by double clicking the file

#### 1.0.13 : April 14, 2022

- Changed TIMI-Click to TIMI-MB

#### 1.0.12 : April 5, 2022

- Fixed copy and paste issue in non-touch modules

#### 1.0.10 : February 23, 2022

- Fixed issue with DotMatrix and TextArea not updating

#### 1.0.9 : February 21, 2022

- Added 240x240 page designs
- Added auto update feature
- Increased UART receive buffer size for Commander and Architect projects

#### 1.0.8 : January 15, 2022

- Added 240x240 page designs
- Fixed display issues when image and page background image when there is no other inherent and GCI widget included

#### 1.0.7 : January 05, 2022

- Added 240x240 page designs
- Added swipe event logging system
- Added new functions/commands:
  - *getSwipeEventCount*: counts the number of swipe events that hasn't been read
  - *getNextSwipeEvent*: reads the next swipe event, returns -1 if no event to read

#### 1.0.6 : December 14, 2021

- Added support for REPTOR devices
- Added automatic touch handling for input widgets
- Added different modes for button widgets (toggle, momentary and navigation)
- Added button event log system for momentary buttons
- Added new functions/commands:
  - *getButtonEventCount*: counts the number of button events that hasn't been read
  - *getNextButtonEvent*: reads the next button event, returns -1 if no event to read
- Implemented Query (getButtonEventCount, getNextButtonEvent) command in Control window/tab of Architect and Commander environments

#### 1.0.5 : December 03, 2021

- Prevented input widgets from being used in non-touch modules
- Changed MediaGaugeA to have the thumb option from MediaSlider
- Fixed Commander documentation scroll issue
- Fixed Page designs that uses sliders and knobs as gauges and buttons as leds
- Fixed RotaryGauge behaving as an input widget
- Fixed DLL missing from other Windows PCs

#### 1.0.4 : November 17, 2021

- Fixed Inherent resource updates for gauges

#### 1.0.3 : November 14, 2021

- Fixed MediaGaugeB compile and display error

#### 1.0.1 : November 08, 2021

- Fixed Dot Matrix gradient issue caused by incorrect use of the widget's position
- Fixed Media Gauge D incorrect range computation

#### 1.0.0 : October 13, 2021

**_Initial Public Release_**

*Supported Products*
- TIMI-96
- TIMI-Click
- TIMI-130
- TED-96

*Available Widgets*
- Label
- Scale
- Panel
- Media Panel
- Symbol
- Image
- Led
- Media Led
- Media Color Led
- Fancy Led A
- Led Digits
- Led Spectrum
- Media Spectrum
- Dot Matrix
- Gauge A
- Gauge B
- Gauge C
- Gauge D
- Gauge E
- Gauge F
- Angular Meter
- Ruler Gauge
- Media Gauge A
- Media Gauge B
- Media Gauge C
- Media Gauge D
- Media Thermometer
- Rotary Gauge
- Slide Show
- Animation
- Symbols
- Led Digits
- Scope
- Button A
- Button B
- Switch A
- Switch B
- Media Button
- Fancy Button A
- Slider A
- Slider B
- Slider C
- Slider D
- Slider E
- Slider F
- Media Slider
- Knob
- Media Rotary
- Text Area
- Print Area
