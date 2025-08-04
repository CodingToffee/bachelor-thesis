- Sewing Machine was already connected to plc for one signal
- On the sewing machine the right signals had to be set to the right pins
- npn to pnp problem -> optocoupler


**Existing connection**
- signal pin on sewing machine was connected to gnd or 0v of plc
- 12v on sewing machine was connected to signal pin 
- because npn on sewing machine, the current is pulled to the signal pin and only flowing when signal is true


The final signals that are necessary to calculate all of the selected KPIs are "Thread Trimming", "Pressure foot", "Upper shaft rotating" and "Main menu and not sewing". To be able to retrieve these signals they first needed to be assigned in the menu of the machine to the right output pins. The challenge then was to connect the output pins to the input pins of the WAGO PLC. There already was a connection for one signal from the sewing machine. This was implemented during an earlier project and unfortunately the connection was poorly documented. So it turned out to be more confusing then to be helpful. That was because the connection was as follows. The signal pin on sewing machine was connected to 0V of the PLC. The 12V pin of the sewing machine was connected to the signal input connector of the PLC. This made sense when it was found out that the signals of the sewing machine are of type NPN and the PLC only takes PNP signals as input. So it was connected in a way that when the signal turns true it pulls the current through the signal input connector of the PLC, resulting in a high signal. However this implementation was limited to only two signal. Because there is only one 0V connector for two signal input connectors. In total there are two 0V connectors and four signal input connectors. So when there are two 12V pins connected to one 0V connector via the signal input pins, the one active  active signal pulls on the 0V connection and would pull current from both input signal connectors. This would result in invalid signals.

To solve this issue it was necessary to convert the NPN signals of the sewing machine into PNP signals that can be handled by the PLC. For this task an optocoupler was used. The implementation looked as is now described. The signal output pins of the sewing machine were connected to the signal input connectos of the optocoupler, and for each signal input there is also a connection to the 24 V power supply of the sewing machine. On the outputput side of the optocoupler, the signal connectors are connected to the signal input connectors of the PLC. Concurrently the 24 V power supply of the PLC is connected to the VCC input connector of the optocoupler. Also the 0V connector of the PLC is connected to the GND connector of the optocoupler.



