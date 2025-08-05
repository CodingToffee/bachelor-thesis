- Sewing Machine was already connected to plc for one signal
- On the sewing machine the right signals had to be set to the right pins
- npn to pnp problem -> optocoupler


**Existing connection**
- signal pin on sewing machine was connected to gnd or 0v of plc
- 12v on sewing machine was connected to signal pin 
- because npn on sewing machine, the current is pulled to the signal pin and only flowing when signal is true


The final signals that are necessary to calculate all of the selected KPIs are "Thread Trimming", "Pressure foot", "Upper shaft rotating" and "Main menu and not sewing". To be able to retrieve these signals they first needed to be assigned in the menu of the machine to the right output pins. The challenge then was to connect the output pins to the input pins of the WAGO PLC. There already was a connection for one signal from the sewing machine. This was implemented during an earlier project and unfortunately the connection was poorly documented. So it turned out to be more confusing then to be helpful. That was because the connection was as follows. The signal pin on sewing machine was connected to 0V of the PLC. The 12V pin of the sewing machine was connected to the signal input connector of the PLC. This made sense when it was found out that the signals of the sewing machine are of type NPN and the PLC only takes PNP signals as input. So it was connected in a way that when the signal turns true it pulls the current through the signal input connector of the PLC, resulting in a high signal. However this implementation was limited to only two signal. Because there is only one 0V connector for two signal input connectors. In total there are two 0V connectors and four signal input connectors. So when there are two 12V pins connected to one 0V connector via the signal input pins, the one active  active signal pulls on the 0V connection and would pull current from both input signal connectors. This would result in invalid signals.

On the left side there is the 12 pin connector of the sewing machine which among other pins holds the signal pins. On the left side there is the PLC input module. The DI1-4 marked connectors  of the PLC are the signal input connectors.

To solve this issue it was necessary to convert the NPN signals of the sewing machine into PNP signals that can be handled by the PLC. For this task an optocoupler was used. The implementation looked as is now described. The signal output pins of the sewing machine were connected to the signal input connectos of the optocoupler, and for each signal input there is also a connection to the 24 V power supply of the sewing machine. On the outputput side of the optocoupler, the signal connectors are connected to the signal input connectors of the PLC. Concurrently the 24 V power supply of the PLC is connected to the VCC input connector of the optocoupler. Also the 0V connector of the PLC is connected to the GND connector of the optocoupler.

**PLC programming**

To make the signal available over the shopfloor network it was necessary to programm the plc to facilitate this. The input signals simply needed to be assigned to a value and then be published over OPC UA.

**PLC topic exploration**
At first only the IP adress and the OPC UA port of the plc were known. To better understand how to retrieve data from it with an OPC UA client, a python script was written. This script took the two givens, establishes a connection and navigates through the OPC UA server's node structure. It  specificially looks for a "DeviceSet" node which is known to typically contain industrial devices like the sewing machine. For each device found it explores variables and child objects. It must be noted that at this point the connection from the previous project was still intact and it was not further explored how it is connected and which additional machines were connected to the PLC. It was done at this time because of a delay in communication with "Brother Internationale Industriemaschinen GmbH". Therefore the knowledge was missing on how to setup the sewing machine signals. So it was decided to already explore on how to communicate to the OPC UA server. 

**Short circuit**
After the connection to the PLC was established for all signals, it was tested if all signals are available. For this purpose the tool UAExpert was used. It is an OPC UA client that provides a user interface for development, testing and monitoring. It was used to monitor the values of the signals. So the actions that should trigger the signals were performed. At the beginning it worked as planned. But after some time one of the signals stopped working and was continiously have the value "false". So the current needed to be measured to determine where the failure lied. During the measuring a short circuit on the printed circuit board (PCB) accured. The reason probably was to accidentally connecting one 24V source with another 24V source through the multimeter.  After this incident none of the signals could be retrieved from the sewing machine anymore. Uppon that it was decided to simulate the OPC UA server and generate test data that mimics the typical sewing process. It was still decided to implement everything in such a way that the sewing machine could be connected to the system once a new PCB would be installed.


