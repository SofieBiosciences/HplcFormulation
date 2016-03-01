# Hplc Formulation - Controller Requirements
**Rev:** 1.0
The requirements drive the [Hplc Formulation - Controller Architecture]
(https://github.com/SofieBiosciences/HplcFormulation/issues/2)
This document describes the firmware and hardware design requirements for the Hplc Formulation Embedded System (Controller).

## 1. System Requirements
- **Req 1:** The Hplc Formulation Embedded System (Controller) will be able to received commands from the Hplc Formulation Software (PC) and command the Hplc Formulation hardware accordingly
- **Req 2:** The Controller will send back status messages, to the Software, describing the state of each hardware component at a frequency that allows the Software to appropriately characterize the Hardware state
- **Req 3:** The Controller shall be the Hplc Formulation module embedded system responsible for all hardware control
- **Req 4:** The Controller shall include a pcb board with an ARM based processor running the firmware responsible for all Hplc Formulation active hardware control
- **Req 5:** The Firmware running on the Controller shall communicate with the Hplc Formulation Hardware as well as the Hplc Formulation Software running on a separate PC

## 2. Hardware Requirements
### 2.1. PCB Board Design
- **Req 1:** The Controller pcb board shall have appropriate communication interfaces for all Hplc Formulation hardware components requiring active control (pressure reg, valves, sensors ...etc)
- **Req 2:** Interfaces shall ultimately connect with the appropriate communication ports on the ARM based processor embedded on the Controller pcb (I2C, SPI, Serial, Analog, Digital ports ... etc)
- **Req 3:** All hardware power interfaces shall be connected to the pc board
- **Req 4:**  The Controller pcb board shall supply power to each hardware interface
- **Req 5:** The Controller pcb shall have the required power source interfaces to supply power to each hardware interface
- **Req 6:** The power interfaces must have separate connectors for each voltage type (example: 5V and 24V power should not be routed through the same connector)
- **Req 7:** The Controller ARM processor shall be an LPC1768 unless hardware requirements dictate otherwise
- **Req 8:** The pcb design shall leverage existing circuit design and connectors from Sofie Biosciences Elixys Synthesizer pcb board wherever appropriate
- **Req 9:** Connectors / Interfaces must be common off the shelf parts available through established electronics parts vendors (Digikey, Mouser ...etc)

### 2.2. Interface Configuration and Hardware Specs
See Sofie Biosciences Hplc [Pure-Form - Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e) document for part numbers and specs
- **Req 1:** Board shall include 8 Solenoid Valve interfaces (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 2:** Board shall include 5 Pressure Valve interfaces (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 3:** Board shall include 1 3 Way Solenoid Valve interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 4:** Board shall include 1 Dual High Pressure Selector Valve interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 5:** Board shall include 1 Low Pressure Selector Valve interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 6:** Board shall include 1 Temperature Controller interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 7:** Board shall include 1 Pressure Regulator interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 8:** Board shall include 3 Liquid Sensor interfaces (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 9:** Board shall include 5 Radiation Sensor interfaces (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 10:** Board shall include 1 Radiation Detector interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 11:** Board shall include 1 UV Detector interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 12:** Board shall include 1 Video Input interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 13:** Board shall include 1 Video Output interfaces (Comm only)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 14:** Board shall include 1 Hplc Pump interface (Comm only)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 15:** Board shall include 1 Video Camera Input interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)
- **Req 16:** Board shall include 1 Video Camera Output interface (Power + Comm)
  * **Part Info:** See [Pure-Form Design Requirements](https://drive.google.com/a/sofiebio.com/folderview?id=0B1BFeufwtxPcNHVwQnVGSERicUU&usp=sharing_eid&ts=56d5034e)

### 2.3. Safety / Shielding / Debugging
- **Req 1:** The pcb board must be designed to protect against Electro Static Discharge (ESD)
- **Req 2:** The pcb board must be designed to ensure integrity of all communication interfaces to Software and to Hardware in order to mitigate the effects of interference from noise sources
- **Req 3:** The pcb board must be equipped with appropriate test loops / pads to measure ground, power source voltages and appropriate hardware signal lines


### 2.4. PC / Software - Communication
- **Req 1:** The Controller pcb shall have a female USB (type A) interface / port that is appropriately connected to the ARM based processor and will allow communication with a host PC
- **Req 2:** The Controller pcb shall have a female ethernet interface / port that is appropriately connected to the ARM processor and will allow communication with a host PC
- **Req 3:** The primary communication interface shall be USB
- **Req 4:** The secondary communication interface shall be Ethernet
- **Req 5:** The Controller must have a built in USB Flash Programmer, allowing a user to easily re-program the ARM chip firmware from a PC over USB

## 3. Firmware Requirements
- **Req 1:** The Firmware shall be able to receive commands from the client over the primary and secondary communication interface
- **Req 2:** The Firmware shall be developed for an ARM based processor / microcontroller
- **Req 3:**  The Firmware shall be developed on the mbed.org cloud compiler / IDE
- **Req 4:** The Firmware logic shall follow a Round Robin Architecture (see Architecture document)
- **Req 5:** The Firmware shall have a global status structure that will store all the appropriate hardware state data (pressure, valve states, sensor readings)
- **Req 6:** The Firmware shall have a run command method that matches the client command to the appropriate hardware api routines
- **Req 7:** The Firmware must periodically send back to the client the state of the hardware, stored in the global status structure
- **Req 8:** The Firmware shall have an API for each hardware component
- **Req 9:** The hardware API shall be composed of a hardware driver and a hardware abstraction class inheriting from the driver
- **Req 10:** The hardware API shall define methods and attributes necessary to provide full control over the hardware functionality or at least a much as is required to run the Hplc Formulation module
- **Req 11:** The hardware abstraction class shall have, at a minimum, one method, called update, that updates the global status structure with the particular hardware state
- **Req 12:** The hardware abstraction class update method shall also check that the particular hardware state matches the hardware setpoints and if not then send the appropriate commands via the hardware driver to reach that setpoint
- **Req 13:** The firmware must be written in such a way that the secondary communication interface can be used with no changes to the hardware API

### 3.1. Performance
- **Req 1:** The frequency of state feedback to the client (Req 7) must be at least 10 Hz
- **Req 2:** The execution time of a hardware routine command (Req 6) must not exceed the period of the state feedback to the client 

