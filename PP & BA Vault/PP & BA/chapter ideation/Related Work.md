2.2 Related Work / State of the Art

**Introduction**

This section will give an overview over similar solutions for sewing machines, how data for monitoring is collected and processed and about how performance measurement is done in manufacturing in general. In particular the different kinds of metrics on which the solutions build, sensor types to collect them, data processing and storage as well as analytics will be investigated. This helps to comprehend the current state of the art, identify gaps in existing solutions and to position this work in the landscape of automated performance measurement systems. This review seeks to highlight potential limitations and opportunities, both technical (e.g., hardware, software, integration) and architectural (e.g., standards, frameworks, open-source approaches), that may influence the implementation of performance measurement systems.

**Jung et al.** \cite{jungRemoteSensingSewing2020} propose a system for analyzing the level of skill of sewing machine operators and the level of difficulty of the sewing tasks. It is similar to this work in that it analyzes the cycle time per piece. This is done by using power consumption data of the sewing machines as base metric. For that they use a power monitoring system that is connected to the machines power plug without any modifications to the sewing machine. The data is then transmitted to a cloud server via wireless communication. Through the use of pattern analysis algorithms the quantity and time of work are then being determined. The strength of this system lies in the non intrusive nature PMS. The disadvantage of this solution is the need for enough sample data to produce accurate results.
**Another** system that uses power consumption measurement was proposed by Strazinskas \cite{strazinskasDevelopmentSolutionMonitoring2025}. He used current sensors to detect motor current changes which are directly linked to sewing machine states like start, stop, seam length, stitch speed. The sensor is connected to an Arduino Uno microcontroller which transmits the received data to a Raspberry Pi 3B+ microcomputer. This microcomputer is doing the central data collection and storage. The data is stored in files which is one of the disadvantages of this system because it is not as efficient as storing it in an optimized time series database. Therefore in comparison more space is needed and further processing of the data is slower. Also no preprocessing is implemented which could minimize the amount of data to be processed which further enhances the need for memory. Strazinskas also says that the use of the current sensor produces some measurement errors and noise in the data.  
**While** taking a different approach, the system proposed by Quoc et al. \cite{quocApplyingIoTOperations2025} similarly relies on not further described IoT devices connected to the machine. The data of these devices is than transmitted to the cloud and integrated with the enterprises Management Information System (MIS) so that it can be used for resource allocation optimization. Based on this a visualization is created that shows the open positions of a contract and how much of it has already been produced.
**A different** approach is introduced by Wedanage et al. \cite{wedanageFogAssistedIndustrial2022} who use a mobile application to capture cycle times of the sewing step. The data is structured in a JSON format and published via MQTT under a certain topic. A fog node, implemented using a Cisco IR829 industrial router, is subscribed to the topic and processes the data through a Java application. This application also writes the data to a RethinkDB database, which is open source and especially designed for realtime applications. The fog node already does local data analytics. In the cloud the data from all the fog nodes is combined to provide real-time alerts and real-time analytics through dashboards which visualize cumulative average cycle times per member compared to takt time(maximum time allowed to produce one product in order to meet customer demand). Through the use of fog computing this system is highly scalable because computing is distributed between the fog nodes. This also enables the system to have real time data analytics and less bandwidth usage. A disadvantage of this system is that it still needs manual input from the operators which is prone to mistakes. Also no historical analytics is performed although the basis for it is already there.
Another disadvantage of this system and of the systems proposed by Jung et al. and Quoc et al. is the use of a cloud which raises several concerns like data security, latency and ongoing costs. 
All the discussed systems have the advantage that they can be used to retrofit older machines and are of non intrusive nature.

Beyond these closely related implementations, a broader perspective is provided by Tambare et al. \cite{tambarePerformanceMeasurementSystem2022}, who reviews various approaches to performance measurement systems. First they discuss two important standards. The ISA-95 standard outlines entities at the shop floor level, where information technology systems such as ERP, CRM, cloud platforms, and SQL databases interact with operational technology components like sensors, actuators, microcontrollers, SCADA systems, and PLCs. Its use is the formalisation of production processes. The ISO 22400 on the other hand is used for formalization of the performance metrics. It gives a framework for defining, calculating and sharing KPI's including their context, formula, unit of measure, range, and intended audience. The researchers go on to highlight the Scania case study, in which these two standards are being used, as an example of the practical application of international standards for performance measurement in a smart manufacturing context.
This case study by Samir et al. \cite{samirKeyPerformanceIndicators2018} will now be examined in more detail. The system is composed of many independent self-contained computational units which are each capable of performing independent computations and are able to collaborate with each other. The software used to process and distribute the data is build as a Service Oriented Architecture (SOA), therefore having multiple services which are independent from each other and each having special responsibilities. The communication between the units is facilitated by an Enterprise Service Bus (ESB). The architecture further applies an Event-Driven Architecture (EDA) where events trigger services. This shall tackle the problem of communication delays. The KPIs are designed using the ISO 22400 standard and the IS-95 is used to facilitate automated interfaces between enterprise and control systems.

Taken together, these studies illustrate a variety of approaches to IoT-based machine monitoring, each with specific strengths and limitations.
In contrast to the systems in these studies the system in this thesis is build to work with a modern sewing machine that provides an interface to extract data directly from the machine. It is also supposed to give a better overview over multiple facets of the production through various KPIs that will be discussed later.
The system proposed in this thesis aims to incorporate the strengths of the discussed systems while mitigating the weaknesses of them. It is also designed to lean more towards the system proposed in the case study by implementing standards and service oriented software. Therefore enabling better scalability and maintainability. 


**End**
- systems aims to mitigate disadvantages of closely related systems while incorporating established standards mentioned in the review
- go towards a SOA









**Overview of Existing Performance Measurement Systems for Industrial Sewing Machines**

- **Summarize published systems or commercial solutions specifically for sewing machines, if available.**

- **Highlight their main features, architectures, and reported results.**

**Performance Measurement in Broader Industrial Contexts**

- **Discuss notable systems for other industrial machines (e.g., CNC, injection molding) that are relevant or have inspired your approach.**
- **Focus on how these systems handle data collection, analysis, and visualization.**

**Comparison of Approaches and Technologies**

- **Compare the technologies, architectures, and methodologies used in related work (e.g., sensor types, data transmission, analytics).**
- **Point out trends (e.g., shift to edge computing, adoption of time series databases).**

**Identified Gaps and Limitations in Existing Work**

- **Discuss shortcomings in current solutions (e.g., lack of real-time feedback, limited to specific machine types, poor scalability, insufficient analytics).**
- **Highlight what is missing for sewing machine applications.**

**How Your Work Differs / Advances the State of the Art**

- **Briefly state the unique aspects of your system (e.g., tailored for sewing machines, specific KPIs, integration with modern IoT platforms, improved usability, etc.).**
- **Set up the motivation for your design and implementation choices.**
