# ControlVFDviaModbus
**Control *invt* GD20 via Modbus RTU interface using QModBus <img src="https://i.imgur.com/sC8b9XM.png" width="30" height="30">**
<img src="https://i.imgur.com/9zXzKIT.png" width="977" height="290">  

## Modbus Introduction
### Modbus Protocol
**Modbus protocol** is **a software protocol and common language** which is applied in the electrical controller. With this protocol, the controller can communicate with other devices via network (the channel of signal transmission or the physical layer, such as RS485). And with this industrial standard, the controlling devices of different manufacturers can be connected to an industrial network for the convenient of being monitored. There are two transmission modes for Modbus protocol: ASCII mode and RTU (Remote Terminal Units)
mode. On one Modbus network, all devices should select same transmission mode and their basic parameters, such as baud rate, digital bit, check bit, and stopping bit should have no difference.  
**Modbus network** is a controlling network with **single-master and multiple slaves**, which means that there is only one device performs as the master and the others are the slaves on one Modbus network. The master means the device which has active talking right to sent message to Modbus network for the controlling and inquiring to other devices. The slave means the passive device which sends data message to the Modbus network only after receiving the controlling or inquiring message (command) form the master (response).  
<img src="https://i.imgur.com/KCe2jkL.png" width="600" height="412">  
After the master sends message, there is a period of time left for the controlled or inquired slaves to response, which ensure there is only one slave sends message to the master at a time for the avoidance of singles impact.
*The Modbus protocol of the GD20 invt inverter is RTU mode and the physical layer is 2-wire RS485*

### Modbus History
Since a Distributed Control System (DCS) became very expensive to purchase and maintain due to the cost of expensive cabling that had to be run from every sensor and actuator back to the central location, a company called Molly Kahn invented the first programmable logic controller (PLC) which were much cheaper but a very powerful control system device. However, PLC's were located at different points in the plant hence there needed to be a way for the various PLC's to communicate with each other and share their data.  
In **1979**, **Modicon** came up with the Modbus which stands for Modicon Field Bus using the Modbus Protocol. It’s primary purpose was, of course, to exchange data between PLCs and other devices on the production floor. At that time, Modicon published the standard as a **free open standard**. In 1977 Modicon was acquired by Gould Electronics who subsequently sold the company to AEG in 1989. Then in 1994, AEG and Groupe Schneider combined forming AEG Schneider Automation and in 1996 this became solely owned by Groupe Schneider which was renamed as **Schneider Electric** in **1999**.
Since then Modbus was one of the oldest fieldbuses on the market and still the most popular and most supported protocol in industrial applications nowadays.

### Driver for Modbus Protocol

## Modbus Wiring and Voltage Specifications

## PC-Inverter Communication with Modbus
### Start/Stop motor

### Control with Traperzoidal Profile and Urgent Braking

### Sampling Motor Speed

### Multiple Motors Synchronization using PID

## References
[1] Modbus Introduction: http://www.espacemoteurs.com/catalogue/V-MANUEL-GD20.pdf  
[2] Modbus History:  
	* https://www.youtube.com/watch?v=OuM28tp5wXc&list=PLkNSEPvX820DURNp8MTTr-dIyBS1OsjV_&index=4  
	* https://instrumentationtools.com/modbus/  
[3]  
[4]  
[5]  