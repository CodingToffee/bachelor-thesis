### Introduction Components

First, you might begin with a general **background** of the topic. This section could briefly introduce industrial sewing machines and the general concept of performance measurement in manufacturing. It sets the stage for your specific research.

- Industrial Sewing machines play a crucial role in the textile industry where they are usually employed in the last step of production to assemble the end product. It is a step where the most human labor is required, which often makes it a critical factor for both production efficiency and product quality. Therefore it is particularly appropriate to apply performance measurement techniques to it. Performance measurement describes the "[...] process of quantifying the efficiency and effectiveness of action." \cite{neelyPerformanceMeasurementSystem1995} Often this is done using KPIs as it is also standardized in the ISO 22400 for operations management and production.

Second, you should clearly state the **problem statement**. This involves identifying the current challenges or gaps in performance measurement for industrial sewing machines that your thesis aims to address. For instance, you might highlight a lack of real-time data or inefficient measurement methods.

- In recent years automatic system for performance measurement on sewing machines have become more popular. However these still face some challenges that were often not addressed. First, many systems rely on the cloud which imposes problems like higher latency and ongoing costs. Second, standards and frameworks are often not being used which makes the systems harder to scale and to maintain. Third, frequently other works focus on retrofitting sewing machines and not using the data provided by the machine resulting in inaccurate results. Fourth, predominantly there is a lack of software architecture that makes use of services, therefore making scalability even harder.

Third, define the **objective** of your thesis. This section should explicitly state what you intend to achieve with your research and implementation. For example, your objective might be to design and implement a system that provides accurate and timely performance data.

- The objective of this thesis is to lay out a replicable way of designing and implementing a performance measurement system with a sewing machine as an example. This includes giving an overview over standards frameworks and technologies as well as showing how to choose the appropriate one and then implementing it. The system proposed in this thesis aims to use open source software for as much of the technologies used as possible and be easily scalable. The result shall be a dashboard that provides the most important KPIs (such as: cycle time, OEE, setup time, down time) in real-time.

Fourth, outline the **scope** of your work. This clarifies what aspects of performance measurement you will focus on and what will be excluded. It helps manage expectations and defines the boundaries of your project.

- The scope of this work is limited to a Brother sewing machine of type UF-8910 which is connected to a WAGO PLC of type 750-8101 PFC100 CS 2ETH which employs the OPC-UA protocol for data transmission to the network. The expected data flow and signals are simulated and do not stem from the physical sewing machine and plc. The sewing machine is part of a shopfloor that is used for workshops where industry customers can gain insight into productivity and quality enhancements within production environments through digitization. The system proposed in this thesis will also be used as a showcase and therefore shall have visualizations that show the real-time capabilities vividly. Only those KPIs shall be derived that only need querying from the database and don't need further post-processing.

Fifth, discuss the **relevance and motivation** behind your thesis. Explain why this research is important, both academically and practically. You could emphasize the potential benefits for the industry, such as improved efficiency or reduced downtime.

- The relevance of this thesis stems from the growing demand for data-driven decision-making to optimize efficiency and reduce costs especially in the higly competitive garment industry. Performance measurement systems enable production management to identify bottlenecks and reduce downtime. They also provide actionable insights that support targeted coaching of the operators. This thesis also contributes to the knowledge base about IoT based monitoring systems through its focus on replicable methods. This as well as the focus on open source technology makes the system architecture well suited for small and medium sized companies with limited resources.

Sixth, provide a brief **overview of the methodology** you will employ. This section does not need to be detailed but should give the reader an idea of your approach, such as whether you will use a design science approach or an empirical study.

- This thesis employs a design-science approach where the artifact is the performance measurement system for the sewing machine. But it also uses a literature review to give an overview over the related work as well as about frameworks, standards and technologies. To further apply the right technology solutions, a structured technology selection process is being developed and followed.

Finally, include a **structure of the thesis**. This section guides the reader through the subsequent chapters, providing a roadmap of your document. You might briefly describe the content of each major chapter

- In the following the structure of the thesis will be explained. First in the foundations technologies, frameworks, standards and other groundwork is explained on which the thesis build upon. In the related work section papers that discuss similar systems are reviewed and used to give examples to better position the system proposed in this thesis. After that the section requirements and system design is explaining needs for such a system and which KPIs and technologies were chosen. Based on that the system can be implemented which follows thereafter.  Following is the evaluation which gives an overview over the strengths and limitations. Finally in the outlook and conclusion a summary of the work is given and further advancements of the system are being discussed. 


### Bullet points about the project
- Performance Measurement for Sewing Machine
- Open source -> independent from big tech regarding current political landscape
- Make use of Standards and Frameworks
- scalability -> easily extensible to multiple machines 
- Dashboard for visualisation
- showcase -> show what is possible
- 