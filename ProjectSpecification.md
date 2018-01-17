# Radio Collar Tracking / Real time DSP

## Project Chapter

### Project Overview
Radio Collar Tracking is a project that helps Biologist tracking marked animal faster. Drone with a radio signal capturing unit is used to capture any radio waves that might emitted by radio collar in a given area. 

Currently the drone only logs raw IQ signal on board. And Biologist needs to wait for the drone flying back and analyze the data on computer. A 20-min flight can generate several gigabytes raw data which takes computer around 10 min to analyze and visualize the signal, (analyzing time is throttled mainly by IO.) Therefore, a real time DSP can saves tons of IO time and let biologist knows the signal source faster.

### Project Objectives
1. Migrate the IQ data processing code from computer to embeded system.
2. Currently IQ data processing can only target selected frequency, need to make processing can target any frequencies since there can be a lot of collars in the field.
3. Make drone autonomously control its flight. It can flies back early when enough data can be used to pinpoint the signal. (Tentative Goal)

### Risk, Feasibility
1. As CS major I do not have any experience with data processing, little knowledge on fourier transform needed for DSP.
2. The on-board chip may not have enough power to analyze signals in realtime.
3. Current drone platform does not support autonomous flight.

## Group Management
Chenxu Jiang

I am the only one on the team, and I need to find teammates. 

Otherwise I will switch to another group.

## Project Development

### HardWare
1. Existed x86 Intel Embedded Board would be mounted on the drone collecting raw radio data, and GPS data and timestamp them. Real time DSP would also take place on the board.
2. Existed USRP B200 collecting raw radio signal.
3. Existed GPS Chip collecting GPS data.
4. Possiblily pair of ZigBee Modules are needed if communication with ground needed to take place. (Cost $50 per module, availble with Amazon Prime 2-day shipping)

### Software
1. Board is running linux; Coding with standard C and POSIX functions.
2. If communications are going to be implemented, need to Coding with high level language that can control the COM serial port and need to be cross platform.

### Testing
1. There are existed flight raw data; Streaming the disk data as the radio signal and compare the real time processed data and computer processed data can be used to test the first objectives.
2. The second and third test data can possibily be tested with several real radio collars and test in a wide open field.

### Documentation
Documnetation would be updated in another README file but mostly the task is to migrate the code which already comes with documentation.

## Project Schedule
- Week 2: Understand IQ signal and Fourier Transform, the foundamentals of DSP
- Week 3,4,5: Migrate the existed code from dump data DSP to real time DSP.
- Week 6,7: Add functions that process the data for unknown frequency (currently dump data DSP can only select and analyze specified frequency signal strength.)
- Week 8, 9 10: Check if we can make drone do autonomous flight which saves even more time.
