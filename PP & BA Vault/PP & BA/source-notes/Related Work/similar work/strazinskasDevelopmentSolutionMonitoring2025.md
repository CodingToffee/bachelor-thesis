---
Title: Development of a solution for monitoring and recording the state of a sewing machine /
Year: 2025
Authors: Paulius Stražinskas
tags:
  - Similar-Work
Processed: true
---
Zotero PDF Link: [Full Text PDF](zotero://select/library/items/NMADV2TK) 
Related::  

### Persistent Notes 
%% begin notes %% 
**Main Features:**
The proposed system aims to solve the problem of the technological gap in the sewing industry between traditional sewing methods and fully automated sewing processes. Specifically, it addresses the challenge faced by smaller manufacturers who cannot afford expensive new sewing equipment with integrated smart technologies. The system provides a solution to upgrade existing sewing machines with monitoring and recording capabilities to collect data on the machine's state. This enables better optimization of the sewing process, improves production efficiency, and allows smaller companies to implement advanced business methods such as LEAN and Six Sigma without the high cost of new equipment. The system also aims to reduce manufacturing process waste and equipment waste by enabling the use of older machines in a smart factory environment (from [page 1](da://viewer/dtuxbttk0a0c24uw/1) to [page 6](da://viewer/dtuxbttk0a0c24uw/6), [page 11](da://viewer/dtuxbttk0a0c24uw/11)).

- Monitoring and recording the state of sewing machines using sensors.
- Use of current sensors (TA12-200 current transformer and ACS723 hall-effect current sensor) to detect motor current changes, which correlate with sewing machine states such as start, stop, seam length, and stitch speed.
- Use of a magnetic rotary encoder (AS5600) to monitor the angular rotation of the main driving shaft, providing a real-time axis for the sewing machine state.
- Real-time data collection and synchronization using microcontrollers (Arduino Mega2560 and Arduino Uno) and a microcomputer (Raspberry Pi 3B+).
- Non-intrusive sensor installation, especially with the TA12-200 current transformer, which is easier to implement and provides sufficient accuracy.
- Data logging with real-time timestamps for further analysis and optimization.
- The system can differentiate between different seam types and operator actions based on sensor data.
- Designed to be discrete, ergonomic, and easy to implement without disrupting the operator's workflow.

**System Architecture:**

- Sensors (TA12-200 current transformer, ACS723 current sensor, AS5600 rotary encoder) are mounted on the sewing machine at key positions: current sensors on the motor power line and rotary encoder on the main driving shaft.
- Sensor data is collected by Arduino microcontrollers: Arduino Mega2560 handles current sensors, Arduino Uno handles the rotary encoder.
- Both Arduinos communicate with a Raspberry Pi 3B+ microcomputer via serial communication.
- Raspberry Pi 3B+ synchronizes data from multiple microcontrollers, timestamps the data with real-time clock, and stores it for analysis.
- The system uses I2C communication protocol for the rotary encoder and analog/digital inputs for current sensors.
- Data collection is synchronized and logged using multi-threaded programming on the Raspberry Pi.
- The system supports monitoring multiple sewing stations by using multiple microcontrollers connected to a single Raspberry Pi.
- The final system design includes a microcontroller (Arduino Uno), a non-intrusive current transformer (TA12-200), and a Raspberry Pi 3B+ microcomputer for data collection and storage.

This information is detailed primarily from [page 30](da://viewer/dtuxbttk0a0c24uw/30) to [page 49](da://viewer/dtuxbttk0a0c24uw/49) and summarized in the conclusions on [page 53](da://viewer/dtuxbttk0a0c24uw/53).

**Results**
1. Three sensors—TA12-200 current transformer, ACS723 hall-effect current sensor, and AS5600 magnetic rotary encoder—were selected and tested. All three sensors were able to describe the state of the sewing machine, but the current sensors provided more detailed information, including clear indication of when the system is turned on. The TA12-200 current transformer was found to be a non-intrusive sensor with similar accuracy (50mA error range) to the ACS723 (30mA error range) and easier to implement ([page 53](da://viewer/dtuxbttk0a0c24uw/53)).
    
2. Sensor placement was optimized for key parameters describing the system state and operator comfort. Custom mounting brackets were manufactured, and sensor data was verified against higher or equal accuracy equipment, confirming the validity of the data (from [page 33](da://viewer/dtuxbttk0a0c24uw/33) to [page 40](da://viewer/dtuxbttk0a0c24uw/40)).
    
3. A real-time monitoring and recording system was created using microcontrollers (Arduino Mega2560 and Uno) and a Raspberry Pi 3B+ microcomputer for data collection and storage with real-time timestamps. The system successfully correlated sensor data with a predefined sewing action plan, showing that current sensors could indicate machine start/stop, seam length, stitch speed, and automatic end seam. The magnetic encoder could describe seam length but was less effective at detecting seam speed and machine on/off times (from [page 43](da://viewer/dtuxbttk0a0c24uw/43) to [page 48](da://viewer/dtuxbttk0a0c24uw/48)).
    
4. The final system design includes the TA12-200 current transformer, Arduino Uno microcontroller, and Raspberry Pi 3B+ microcomputer, chosen for accuracy, responsiveness, and ease of implementation ([page 49](da://viewer/dtuxbttk0a0c24uw/49)).
    
5. Economically, the system costs approximately 106.17 EUR in parts, significantly less than existing IoT-capable sewing machines averaging 3,305.67 EUR. A hypothetical upgrade of 20 machines with this system would cost about 2,373.4 EUR including labor, compared to 66,113.4 EUR for new machines, saving approximately 63,740 EUR (from [page 50](da://viewer/dtuxbttk0a0c24uw/50) to [page 53](da://viewer/dtuxbttk0a0c24uw/53)).

**Analytics:**

- The collected sensor data is analyzed by comparing current consumption and rotational angle data on a unified real-time axis.
- Current sensor data is used to identify sewing machine states such as machine start/stop, seam length, stitch speed, and automatic end seam.
- The magnetic rotary encoder data provides information on seam length and shaft rotation but is less effective at detecting machine start/stop and high-speed seam changes.
- The system enables classification of different sewing actions based on sensor data patterns, which can be further used in AI-based classification models for process optimization (from [page 45](da://viewer/dtuxbttk0a0c24uw/45) to [page 49](da://viewer/dtuxbttk0a0c24uw/49)).

**Shortcomings**
- Data is collected by sensors and not directly from the machine -> less accurate
- no seperation of concerns, everything concerning prossessing and storage is done in the raspy
- no kind of preprocessing -> exessive amounts of data (sampling rates 50ms, 500ms)
- use of textfiles instead of optimized time series database
 %% end notes %% 

### In-text annotations 



%% Import Date: 2025-07-11T13:06:25.592+02:00 %%
