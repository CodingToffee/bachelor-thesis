- Sewing Machine was already connected to plc for one signal
- On the sewing machine the right signals had to be set to the right pins
- npn to pnp problem -> optocoupler


**Existing connection**
- signal pin on sewing machine was connected to gnd or 0v of plc
- 12v on sewing machine was connected to signal pin 
- because npn on sewing machine, the current is pulled to the signal pin and only flowing when signal is true


The final signals that are necessary to calculate all of the selected KPIs are "Thread Trimming", "Pressure foot", "Upper shaft rotating" and "Main menu and not sewing". To be able to retrieve these signals they first needed to be assigned in the menu of the machine to the right output pins. The challenge then was to connect the output pins to the input pins of the WAGO PLC. There already was a connection for one signal from the sewing machine. This turned out to be more confusing then to be helpful. That was because the connection was as follows. The signal pin on sewing machine was connected to 0V of the PLC. The 12V pin of the sewing machine was connected to the signal input connector of the PLC. This made sense when it was found out that the signals of the sewing machine are of type NPN and the PLC only takes PNP signals as input. So it was connected in a way that when the signal turns true it pulls the current through the signal input connector of the PLC, resulting in a high signal. However this implementation was limited to only two signal. Because there is only one 0V connector for two signal input connectors. In total there are two 0V connectors and four signal input connectors. So when there are two 12V pins connected to one 0V connector via the signal input pins, the one active  active signal pulls on the 0V connection and would pull current from both input signal connectors. This would result in invalid signals.


