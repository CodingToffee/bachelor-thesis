For the KPI selection there are two requirements that need to be fulfilled. First there need to be some KPIs that are relevant for the sewing process. Second there need to be KPIs that are relevant for manufacturing companies in general. Also these KPIs need to be able to be computed based on the available signals. So it was first determined which supporting elements can be calculated based on the signals. And more generally speaking which observations can be made based on the available signals. It is important to note that only four of the signals can be made available.

First of all it was noted that based on the signals thread trimming, pressure foot and main shaft rotating a production pattern that could be observed could also be measured. The pattern is as follows. First the pressure foot is lifted because the worker needs to insert the material. Then the pressure foot is lowered so that it puts pressure on the material. Then the worker would start sewing, resulting in the main shaft rotating signal being true. Then this signal would change to false when the seam is finished. After that the pressure foot would be lifted again to remove the workpiece. While it is removed the thread would get trimmed. Finally the pressure would be lowered again indicating the end of the pattern.
Based on this pattern the duration of the pure working time on the sewing machine could be measured.
Based on the thread trimming signal it could be measured how many pieces are produced, by simply counting the events when this signal turns true. By measuring the duration from one thread trimming signal until the next the cycle time could be measured. 
By simply measuring the time that the upper shaft is rotating it could be determined how long the machine is used for just sewing.
The signal "other than homescreen" could indicate that the setup of the machine is currently being changed.
The signal "homescreen and not sewing" can be used to observe the activation of the machine. One could think that it is simply the inverted state of the "upper shaft rotating" signal. This is the case when the machine is turned on. But when the machine is turned off all signals are false. Therefore the transition from all signals being false to "homescreen and not sewing" being true and the other signals being still false would indicate the activation of the machine. This could be used to measure setup time until the first pattern arises.

------
Also when only the signal "homescreen and not sewing" is active, that means that the machine is in idle state. Therefore it can be measured how long the machine is in idle state.

**Base Calculations**
To have a better overview of the supporting elements, they are listed below with their respective formula.

Planned Downtime
Usuall the planned downtime would also include planned maintenance etc. but we don't have that so only the breaks are considered planned downtime. Although technically it is not a kind of downtime. But for illustrative purposes it will be considered downtime.




**Describe the KPIs that can be calculated based on these observations**
Based on these supporting elements the basic KPIs can be calculated.
There are going to be some KPIs that were mentioned in sewing performance measurement studies. These are Performance, Availability and OEE. But these KPIs are not solely interesting for the textile industry because they are also relevant in general for production. Some of the KPIs are just averages of supporting elements. They shall help to identify the reasons behind the values of higher level KPIs.


**KPIs that are only averages and mean**
The remaining KPIs are encompass only simple averages. The Cycle Time is divided by pieces and therefore resulting in the average cycle time per piece. The setup time is divided by shifts 

**Average Cycle Time**
The Cycle Time is summed up over all produced units and then devided by that count. 
Average Cycle Time = total cycle time / produced quantity

**Average Setup Time**
The setup time is summed up over all shifts and then devided by the count of shifts.
Average Setup Time = total setup time / nr of shifts

**Average Idle Time**
The idle time is summed up and then devided by the count of shifts in the timeframe, resulting in the average idle time per shift.
Average Idle Time = total idle time / nr. of shifts

**Mean Time to Repair**
The time to repair is summed up and then devided by the count of failure events.
Mean Time to Repair = total time to repair / failure events

**Mean Time to Failure**
The time to failure is summed up and then devided by the count of failure events.
Mean Time to Failure = total time to failure / failure events

**Mean Operating Time between Failures**
The OTBF is summed up and devided by the count of failure events.
Mean Operating Time between Failures = total operating time between failures / failure events

**Average Actual Operating Time**
The APT is summed up and devided by the count of shifts in the timeframe, resulting in the average actual operating time per shift.
Average Actual Operating Time = total actual operating time / nr of shifts

**Comprehensive KPIs**
According to Kang et al., based on the Basic KPIs, comprehenisve KPIs can be calculated.

**OEE**
Overall Equipment Effectiveness (OEE) is formally defined as a comprehensive metric quantifying the total performance of a given piece of equipment. It integrates factors of availability, performance, and quality to provide a holistic assessment of operational efficiency. Bluntly said "[...]the degree to which the equipment is doing what it is supposed to do ." \cite{muchiriPerformanceMeasurementUsing2008}
Overall Equipment Effectiveness = Availability * Performance Efficiency * Quality Rate

**NEE**


