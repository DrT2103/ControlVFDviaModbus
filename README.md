# ControlVFDviaModbus
**Control *invt* GD20 via Modbus RTU interface using QModBus <img src="https://i.imgur.com/sC8b9XM.png" width="30" height="30">**
  
<img src="https://i.imgur.com/9zXzKIT.png" width="674" height="200">  

## Modbus Introduction
### Modbus Protocol
**Modbus protocol** is **a software protocol and common language** which is applied in the electrical controller. With this protocol, the controller can communicate with other devices via network (the channel of signal transmission or the physical layer, such as RS485). And with this industrial standard, the controlling devices of different manufacturers can be connected to an industrial network for the convenient of being monitored. There are two transmission modes for Modbus protocol: ASCII mode and RTU (Remote Terminal Units)
mode. On one Modbus network, all devices should select same transmission mode and their basic parameters, such as baud rate, digital bit, check bit, and stopping bit should have no difference.  
**Modbus network** is a controlling network with **single-master and multiple slaves**, which means that there is only one device performs as the master and the others are the slaves on one Modbus network. The master means the device which has active talking right to sent message to Modbus network for the controlling and inquiring to other devices. The slave means the passive device which sends data message to the Modbus network only after receiving the controlling or inquiring message (command) form the master (response).  
<img src="https://i.imgur.com/KCe2jkL.png" width="600" height="412">  
After the master sends message, there is a period of time left for the controlled or inquired slaves to response, which ensure there is only one slave sends message to the master at a time for the avoidance of singles impact.
*The Modbus protocol of the GD20 invt inverter is RTU mode and the physical layer is 2-wire RS485*

### RS-232 and RS-485
**RS-232** and **RS-485** are electrical standards which are widely used in industrial communication devices.  
**RS-232** is used for short distance **point-to-point** communication, the same is valid for RS-422, which is a bidirectional extension of RS232 for industrial environments, that also supports longer distances.  
**RS-485** can be used for **multipoint communication** (i.e. multiple devices connected to the same signal cable), employing the Master-Slave paradigm (one master and n fixed address slaves).

### Modbus History
Since a Distributed Control System (DCS) became very expensive to purchase and maintain due to the cost of expensive cabling that had to be run from every sensor and actuator back to the central location, a company called Molly Kahn invented the first programmable logic controller (PLC) which were much cheaper but a very powerful control system device. However, PLC's were located at different points in the plant hence there needed to be a way for the various PLC's to communicate with each other and share their data.  
In **1979**, **Modicon** came up with the Modbus which stands for Modicon Field Bus using the Modbus Protocol. It’s primary purpose was, of course, to exchange data between PLCs and other devices on the production floor. At that time, Modicon published the standard as a **free open standard**. In 1977 Modicon was acquired by Gould Electronics who subsequently sold the company to AEG in 1989. Then in 1994, AEG and Groupe Schneider combined forming AEG Schneider Automation and in 1996 this became solely owned by Groupe Schneider which was renamed as **Schneider Electric** in 1999.
Since then Modbus was one of the oldest fieldbuses on the market and still the **most popular** and **most supported** protocol in industrial applications nowadays.

## About QModBus
QModBus is a free Qt-based implementation of a ModBus master application. A graphical user interface allows easy communication with ModBus slaves over serial line interface. QModBus also includes a bus monitor for examining all traffic on the bus.
#### Technical details
* Supports RTU mode of ModBus protocol
* Parameters of serial port fully configurable
* Bus monitor for examining all traffic on the bus
* Backend based on [libmodbus](https://github.com/stephane/libmodbus/)
* Supports both Linux and Windows

## Modbus Wiring and Voltage Specifications
The interface of 2-wire RS485 works on semiduplex and its data signal applies differential transmission (or balance transmission). It uses **twisted pairs**, one of which is defined as A (+) and the other is defined as B (-).
* If the electrical level is among **+2V~+6V**, it is logic “**1**”
* If the electrical level is among **-2V~-6V**; it is logic “**0**”.  
*485+ on the terminal board corresponds to A and 485- to B.*

## PC-Inverter Communication via Modbus
### Start/Stop motor

### Control with Traperzoidal Profile and Urgent Braking
#### Constant Torque load
The GD20 series (here using model *GD20-0R7G-S2*) with "G" stand for constant torque load which is described as the *graph* below  
<img src="https://i.imgur.com/bQIA239.png" width="400" height="400">  
Constant torque loads require the same amount of torque at low speeds as at high speeds.  
For example, if the speed increases by 50%, then the power required to drive the operation will increase 50% while the torque remains constant.

### Sampling Motor Speed

### Multiple Motors Synchronization using PID

## References
[1] Modbus: http://www.espacemoteurs.com/catalogue/V-MANUEL-GD20.pdf  
[2] Modbus History:  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- https://www.youtube.com/watch?v=OuM28tp5wXc&list=PLkNSEPvX820DURNp8MTTr-dIyBS1OsjV_&index=4  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- https://instrumentationtools.com/modbus/  
[3] RS-232 & RS-485: http://jamod.sourceforge.net/kbase/protocol.html  
[4] QModBus: http://qmodbus.sourceforge.net/  
[5] Constant Torque load: https://www.se.com/ww/en/faqs/FA105387/  
[6]   