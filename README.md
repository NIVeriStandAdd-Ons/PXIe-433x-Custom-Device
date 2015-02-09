## PXIe-433x Custom Device ##

----------

**This custom device should not be used with NI VeriStand 2012 or later because 433x devices can now be used natively in NI VeriStand 2012+ without the need of a custom device.**

----------

**PXIe-433x Custom Device** allows users to use the PXIe-433x (at this time, 4330 and 4331) devices inside NI VeriStand.  This functionality is commonly used for strain, pressure, or torque measurements of a physical system.

### Operational modes ###
#### Monitoring  ####
Runs the data acquisition in a separate loop from the primary control loop. This can be higher performance, but the data acquired will be reported from the device 2-50 iterations after the physical phenomenon occurred. High latency.

#### Control ####
Runs the data acquisition within the primary control loop in Hardware Timed Single Point (HWTSP) mode. Control mode will limit your loop rates to ~700 Hz for 4330 and ~2500 Hz for 4331, but provides a very low latency sampling of the I/O for a control loop.

Use control mode for low latency acquisition. If there is already a different timing master in the system (DAQ, FPGA, etc), then no further setup it necessary for the custom device. If there is NOT already a timing master in the system, you must set this device as the timing master in the system to use it in control mode. Visit the controller page and chassis page to do so.

### LabVIEW Version ###

LabVIEW 2011

### Built Availability ###

No builds are provided.

### Quality, Limitations ###

This IP should be considered mature. The IP has been used worldwide by several customers in deployed applications since 2010.

However, as the custom device relies on timing & sync features of products and PXI backplane routing (which have undergone several changes since 2012) newer versions of NI VeriStand may have issues with this custom device.

### Dependencies ###

This custom device requires DAQmx 9.1 or later for monitoring mode and 9.3 or later for control mode

### License ###

*This repository and any materials provided by NI therein are provided AS IS. NI DISCLAIMS ANY AND ALL LIABILITIES FOR AND MAKES NO WARRANTIES, EITHER EXPRESS OR IMPLIED, INCLUDING WITHOUT LIMITATION ANY WARRANTIES OF MERCHANTABILITY, FITNESS FOR  PARTICULAR PURPOSE, OR NON-INFRINGEMENT OF INTELLECTUAL PROPERTY. NI shall have no liability for any direct, indirect, incidental, punitive, special, or consequential damages for your use of the repository or any materials contained therein.*
