# HPLC Formulation Controller Firmware

## Overview

The Controller is the embedded system responsible for controlling  all the Hplc Formulation hardware including pumps, valves, actuators and sensors.
The communication interface between the Controller and external systems will be USB (Ethernet option is available). 
Status messages containing a complete state representation of the hardware (sensor values, pump pressure, valve positions) will be periodically sent over the communication port. All commands will be sent to the Controller embedded system over the USB port. 
