## 3.1 Requirements Analysis
To choose the right technologies and design the system, first the requirements need to be clear. In this chapter these requirements will be listed and explained. To have a clear understanding of what the requirements mean, a framework by Prof. Dr.-Ing. Thomas Siepmann is used that is described in the following figure.

![[GetImage.png]]

Also the keywords have the following meaning

| Keyword                           | Explanation                                                                               |
| --------------------------------- | ----------------------------------------------------------------------------------------- |
| MUST                              | Lawfully binding                                                                          |
| SHOULD                            | Optional, recommended                                                                     |
| WILL                              | Planned for next release, not included in current scope                                   |
| <"process word>                   | System behavior, highly important to use unambiguous words, that are binding              |
| <Object & Addition of the object> | E.g. other systems, ability of other systems, and everything else that adds clarification |
| <whom?>                           | E.g. user, admin, user-group etc.                                                         |
This framework is primarely made to describe functional requirements. But it is less applicable for non-functional requirements. Therefore in the case of the latter, the requirements are formulated in a way that leans toward this framework. In this way it still provides some clarity about how binding a requirement is.

.....not quite sure about this
Therefore a new template is being proposed especially for the formulation of non-functional requirements. The first three keywords must be used. The last two can be used addtitionally to make the requirement more concrete.

![[non-functional-req-framework 1.jpg]]
.....
### Requirements for the System
#### Functional
- The system must show KPIs that are relevant for the sewing process
- The system should show aditional KPIs that are relevant for the manufacturing industry in general
- The system must present these KPIs in a visual manner that provides information about the classification of the current value e.g. with colors and thresholds
- The system must provide the user with the ability to change the timeframe on which the KPIs are calculated
- The system should show graphs with historical data
#### Non-Functional
- The system must make use of open source software where possible
- The system must be capable to generate all of the KPIs from the machine-data without installing any additional sensors
- The system must be designed in a way that makes it easily scalable
- The system must be deployable with minimal effort
- The system must be capable to retrieve raw data via opc-ua
- The system should make use of existing patterns, frameworks and solutions were possible
- The system should update the KPIs in real-time (<10s)
- The system must be able to run on a local machine and therefore independent of any cloud service
- The system must provide the user with the ability to access the dashboard from within the shopfloor network

## IoT Platform Selection Framework

The raw data coming from the plc had to be processed, stored and visualized. IoT Platforms come in handy because they can do all of these things plus often many more.  They satisfy the requirements for an easily scalable system and to make use of existing solutions. To be sure that a platform is selected which also satisfies other requirements and is not in conflict with any necessary requirement, a decision support framework was developed. This framework is inspired by the one proposed by Gustin et al. 
. They chose a bunch of criteria and gave these criteria a category. The categories were "Knock-out", "DM"(Device Management), "Hosting", "General", "Effort". Each category then got a weight assigned with exception of the Knock-Out category which indicates that a criteria tagged with it needs to be met otherwise the platform will not be further considered. The weights are percentages which in sum are 100 percent. The rating of each platform is then calculated with this fomula:
![[Pasted image 20250721090037.png]]
Where $f_i$ is the fulfillment factor.  
The differences in the newly developed framework are as follows. The criteria are flexible and should be altered according to the requirements, as Gustin et al. focus on device management which in this work plays no role. The categories were changed to "Knock-Out", "High-", "Mid-", "Low Importance". This way they are not bound to a topic, but can be freely assigned as to which criteria are considered more or less important. The weights of the categories are simply 1 for low-, 2 for mid-, 3 for high importance. The new formula for calculating the score of the platforms is also simpler:
si = sum of weight * fullfillment degree
The fulfillment factor is usually binary. Either a criteria is met or not. But for some it can also be a fraction. For example it is desirable that the platforms support various additional communication protocols other than opc-ua. Namely HTTP, MQTT, CoAP, AMQP. If a platform only supports one of these it would get a quarter point. If the later is the case then it will be made clear in the following explanation. The fullfillment of the criteria was determined the same way as the researchers did. It was looked into the documentation, website or github of the platform. If Information about the availability of the criterion was found it got the point. If no Information was found it was regarded as non existent.
In the following each criteria will be explained. Some of them were taken from the paper by Gustin et al. if they seamed to be useful. Others were created based on the requirements.

**Availability of Documentation**
Category: Knock-Out
To be able to implement the solution, deploy it and work with it, it is highly important to have the documentation in English. This criterion originates from the work of Gustin et al.

**Cloud independence**
Category: Knock-Out
This is one of the criteria stemming directly from the requirements.

**Ability to process raw data and derive KPI's from it**
Category: Knock-Out
To be able to visualize the KPIs, the data first needs to be processed and then KPIs have to be calculated upon it. This criterion relates to the requirement to calculate KPIs.

**OPC-UA capability**
Category: Knock-Out
This is one of the criteria stemming directly from the requirements. 

**Dashboarding Capabilities**
Category: High
To be able to visualize the KPIs the plattform needs to have these capabilities. This criterion relates to the requirement to be able to visualize KPIs.

**Actively Maintained**
Category: High
Ensures that the plattform stays secure and stays compatible with evolving technologies and standards. 
This criterion emerges from the requirement for open source software.

**Completion of Server SW**
Category: High
This criterion gives information about the ease of installing the software. If a docker image is provided a 1 is given if only source code is available a 0 is given. This criterion is taken from Gustin et al.

**Development of the server-side application**
Category: High
This criterion describes how easy it is to create rules and process data within the application. If a rule engine (low code) is provided 1 point is given. If an sdk is provided 0.5 points are given. This criterion stems from Gustin et al.

**Examples for Server-side implementation**
Category: High
These examples show step by step how the server-side implementation is done and what the end result respectively appears to be.This further speed up the implementation process. 
This criterion stems from Gustin et al.

**Supports MQTT, HTTP, CoAP, AMQP**
Category: Medium
It would greatly enhance the scalibility of the system if these protocols were supported because more different machines, gateways or microcontrollers could be connected. This criterion relates to the requirement to have a system that is scalable with minimal effort.

**Availability of Tutorials**
Category: Medium
Tutorials help to better understand the plattform and how to use it and therefore speed up the development process. This criterion stems from Gustin et al.

**Fault detection**
Category: Low
This feature allows for information about abnormal behaviour or fault conditions of the machine. Thereby helping to trouble shoot if problems arise. It would be a nice to have feature but does not directly serve the purpose of the system.
This criterion is taken from Gustin et al.

**Heartbeat Monitor**
Category: Low
This feature performs a periodic check if the connected machine is still online and functioning. Thereby it would help to detect device connectivity issues and ensure system reliability.
It is also a nice to have feature but does not directly serve the purpose of the systems.
This criterion is taken from Gustin et al.

### Selection of Platforms to evaluate
The Platforms to evaluate were taken from various papers that themselve evaluted IoT Platforms. From Gustin et al. all open source platforms that they mentioned were taken. These are openBalen, Thingsboard, Kapua, OpenRemote, Ubuntu Core, FIWARE, OpenMTC, Mainflux, DeviceHive. In another study \cite{turkiEvaluatingOpenSource2024} only open source IoT Platforms were evaluated by there github statistiks. Considered were the stars that were given by users, health, contributors, open issues, closed issues and releases. Because of the more objective nature of this rating, only the top five IoT Platforms were selected. It was limited to this number because it would have been simply too time consuming to evaluate all of the platforms. The top five platforms from this paper are Thingsboard, Dgiot, Mainflux, OpenRemote, IotSharp.  Only two of them were in disjunction with those selected from Gustin et al.'s work. During the research Node-RED was a platform that showed up quite frequently but was not mentioned in the reviewed evaluations. It was also mentioned by a co-worker and so it was also taken into consideration. Also UMH was selected for evaluation because it builds upon strong open source tools like Grafana and Apache Kafka and supports a broad range of protocols.


The results of the calculations are shown in the following table. Only the ones that were not knocked out are shown there.

**{Table}**

The points for Node-RED, ThingsBoard, and UMH were closely aligned, indicating comparable suitability among the three. Therefore they were further investigated as to what their system requirements are. Out of the three, UMH has the highest demands with a need for 200 GB of persistent memory, 16 GB of RAM and a quad core CPU \cite{UMHInstallationRequirements}. This could not be met with the server, which has a specification of 100 GB persistent memory, 8 GB of RAM and an eight core CPU. For Thingsboard only the required minimum amount of RAM is specified with 4 GB \cite{thingsboardInstallingThingsBoardCE}. For  Node-RED no official system requirements are listed. But it is mentioned that it can run on a raspberryPi \cite{RunningNodeREDLocally}. Also some users reported that they ran it on a raspberryPi 2 \cite{NodeRedMinimun2020} which has only 1 GB of RAM and a 900 MHz quad core CPU as well as \cite{ltdBuyRaspberryPi}. Du to being the seemingly most lightweight solution as well as having the highest score in the initial evaluation Node-Red was selected as IoT Platform for the system in development.


## Database Selection

To store the data it was necessary to select a suitable DBMS. In the theoretical foundations it was already layed out why a time series database is in regards to IoT streaming data superior to a relational database. The selection of the Timeseries Database Management System (TS-DBMS) was done in a not as sophisticated manner as of the IoT Platform. The reason  simply lies in the time constraint for the project. It was looked up which are the most prominent TS-DBMSs on db-engines.com which is a website dedicated to determining the popularity of DBMSs. The following metrics have an influence on the popularity ranking: Number of mentions on websites; general intrest in the system, measured with google trends; number of related questions and posts on well known IT Q&A sites; the number of job offers in which the system is mentioned; number of mentions on professional networks; number of mentions on social networks \cite{DBEnginesRankingMethod}.On this website InfluxDB has the highest score in the ranking for TS-DBMS which is 22.65 as of July 2025. This is more than thrice of the score of the second ranking TS-DBMS which is Prometheus with a score of 7.12 as of July 2025. This observation also lined up with influxdb representing TS-DBMSs in the comparison mentioned in the fundamentals were it outperformed the RDBMS in terms of read and write speed as well as in terms of storage efficiency. But also Rudak et al. \cite{rudakovComparisonTimeSeries2023} found out that it is superior to other TS-DBMSs like MongoDB and TimescaleDB regarding read and write speed. 
It was then determined if InfluxDB is capable of handling boolean values. This was validated in the documentation \cite{WriteDataInfluxDB}. Also it was determined if InfluxDB is supported by Node-RED. The Package that was found (node-red-contrib-influxdb 0.7.0) only supports InfluxDB 1.x and 2.0. Before that it was also discovered that InfluxDB 3 Core is limited to querying only the latest 72 hours which was deemed insufficient due to the requirement of being able to calculate historical KPIs. As a result of these findings, InfluxdDB v2 was selected, which is compatible with Node-RED and enables unlimited querying windows.

## Dashboard Tool Selection

It was first planned to utilize the dashboarding capabilities of the selected IoT Platform Node-RED. 
But it seemed like this node-RED feature is not often used for visualisation. Rather another Software called Grafana was very prominent in use cases like the one of this work. So it was decided to use Grafana for building dashboards to visualize the KPIs. This way the probability that other co-workers would be familiar with  the solution was higher and a hand-over would be less complicated. The decision was further confirmed by Rani \as rs who states it being highly appropriate for time series visualisation and monitoring. He also highlights it being well integratable with numerous databases of which one is InfluxDB.





