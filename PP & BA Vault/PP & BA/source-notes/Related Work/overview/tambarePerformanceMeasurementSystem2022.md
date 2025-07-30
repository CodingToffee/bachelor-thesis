---
Title: "Performance Measurement System and Quality Management in Data-Driven Industry 4.0: A Review"
Year: 2022
Authors: Parkash Tambare, Chandrashekhar Meshram, Cheng-Chi Lee, Rakesh Jagdish Ramteke, Agbotiname Lucky Imoize
tags:
  - Industry
  - "4.0"
  - cyber–physical
  - production
  - system
  - performance
  - measurement
  - system
  - Quality
  - "4.0"
  - Review
  - IoT
---
Zotero PDF Link: [PDF](zotero://select/library/items/H643K5E3) 
Related::  

### Persistent Notes 
%% begin notes %% 
**Discussed Performance Measurement Systems**
1. **ISA-95 Standard-Based Systems**  
    The ISA-95 (ANSI/ISA-95) standard provides a framework for integrating enterprise and control systems. It defines a functional hierarchy for production, ranging from physical processes and sensors (Level 0 and 1) to process control (Level 2), manufacturing operations management (Level 3), and business planning/logistics (Level 4). The Manufacturing Operation Center (MOC), developed using ISA-95 standards, is highlighted as a practical implementation. The MOC enables real-time monitoring and enhancement of plant performance by contextualizing shop floor data from various sources (e.g., sensors, PLCs, SCADA) and presenting it through pre-built dashboards with predefined KPIs such as Overall Equipment Effectiveness (OEE), equipment downtime, and production loss analysis. This system bridges the gap between disconnected production floor data and enterprise-level systems, facilitating in-depth performance analysis and root cause investigation (from [page 9](da://viewer/dmhjngp8ywcshhuh/9) to [page 10](da://viewer/dmhjngp8ywcshhuh/10)).
    
2. **ISO 22400 Standard-Based Systems**  
    The ISO 22400 standard specifies Key Performance Indicators (KPIs) for manufacturing operations management. It provides a structured approach to defining, calculating, and sharing KPIs, including their context, formula, unit of measure, range, and intended audience. The standard is supported by KPI-ML, an XML schema for recording and exchanging KPI knowledge. ISO 22400 is used to define KPIs for different types of manufacturing (batch, continuous, discrete) and is often implemented in conjunction with ISA-95. Common KPIs under this standard include First Pass Yield, Throughput Rate, Availability, OEE, and Energy Consumption. The review also presents a case study of the Scania Pedal Car Line, where ISO 22400 was used to implement KPIs for performance measurement, demonstrating the practical application of the standard in a smart manufacturing context (from [page 10](da://viewer/dmhjngp8ywcshhuh/10) to [page 13](da://viewer/dmhjngp8ywcshhuh/13)).

**Architectures:**

- **Cyber–Physical Production System (CPPS):** A core architecture in Industry 4.0, integrating IoT, embedded network systems, cloud computing, big data, and AI to enable smart factories ([page 2](da://viewer/dmhjngp8ywcshhuh/2)).
- **ISA-95 Functional Hierarchy:** Describes the integration of enterprise and control systems, with a layered approach from physical processes (Level 0) to business planning and logistics (Level 4) ([page 9](da://viewer/dmhjngp8ywcshhuh/9), [page 10](da://viewer/dmhjngp8ywcshhuh/10)).
- **Manufacturing Operation Center (MOC):** An implementation based on ISA-95, providing real-time visibility and contextualization of shop floor data, integrating data from sensors, PLCs, SCADA, and enterprise systems into dashboards for performance monitoring (from [page 9](da://viewer/dmhjngp8ywcshhuh/9) to [page 10](da://viewer/dmhjngp8ywcshhuh/10)).

**Technologies:**

- **Internet of Things (IoT):** Enables connectivity and data exchange between machines, sensors, and systems, forming the backbone of CPPS ([page 2](da://viewer/dmhjngp8ywcshhuh/2), [page 5](da://viewer/dmhjngp8ywcshhuh/5)).
- **Big Data and Analytics:** Used for real-time data collection, analysis, and predictive maintenance, supporting both performance measurement and quality management ([page 2](da://viewer/dmhjngp8ywcshhuh/2), [page 14](da://viewer/dmhjngp8ywcshhuh/14)).
- **Artificial Intelligence (AI) and Machine Learning (ML):** Applied for advanced analytics, prescriptive and predictive insights, and automation of quality and maintenance processes ([page 2](da://viewer/dmhjngp8ywcshhuh/2), [page 14](da://viewer/dmhjngp8ywcshhuh/14)).
- **Cloud Computing:** Facilitates scalable data storage, processing, and application development for smart manufacturing ([page 2](da://viewer/dmhjngp8ywcshhuh/2), [page 15](da://viewer/dmhjngp8ywcshhuh/15)).
- **Industrial Standards:**
    - **ISA-95:** For integrating enterprise and control systems, defining production and automation components ([page 9](da://viewer/dmhjngp8ywcshhuh/9)).
    - **ISO 22400:** For defining and structuring KPIs in manufacturing, including the use of KPI-ML (an XML schema for KPI data exchange) ([page 10](da://viewer/dmhjngp8ywcshhuh/10), [page 11](da://viewer/dmhjngp8ywcshhuh/11)).
    - **LNS Quality 4.0 Framework:** Defines 11 axes for digital quality management, including data, analytics, connectivity, collaboration, app development, scalability, management systems, compliance, culture, leadership, and competency (from [page 14](da://viewer/dmhjngp8ywcshhuh/14) to [page 15](da://viewer/dmhjngp8ywcshhuh/15)).

**Scania Case Study**
The Scania case study, as presented in the document, focuses on the implementation of ISO 22400 standards to measure performance in the Scania Pedal Car Line, which serves as a showcase for new systems, tools, and innovative technologies in a smart factory environment. The case study illustrates the transition from manual data collection to an automated, data-driven approach enabled by cyber–physical systems (CPS) and advanced connectivity.

Key aspects of the Scania case study include:

- **Data Acquisition**: The Power Focus PLC System by Atlas Copco is used to automate the manufacturing process. This system connects multiple controllers via Ethernet, enabling real-time monitoring and control of production activities. Data is event-driven and collected from various tools, particularly those used for bolt tightening, and is transmitted as structured strings for further analysis.
    
- **Data Identification**: The implementation of ISO 22400 provides a standardized framework for defining and calculating Key Performance Indicators (KPIs). The standards ensure uniform definitions for each data point, allowing for consistent and reliable performance measurement across the production line.
    
- **Data Planning**: Extracted data is used to calculate a range of KPIs, including first pass yield, availability, throughput rate, downtime, OEE (Overall Equipment Effectiveness), scrap ratio, count, goal, and takt time. New KPIs are developed in accordance with the specifications of both ISA-95 and ISO 22400.
    
- **Impact**: The case study demonstrates how the integration of smart devices and CPS enables more sophisticated, automated, and accurate performance measurement compared to traditional manual methods. This leads to improved visibility, efficiency, and decision-making in the production process.
    

The Scania case study exemplifies the practical application of international standards for performance measurement in a smart manufacturing context, highlighting the benefits of digital transformation and the use of advanced industrial technologies.
 %% end notes %% 

### In-text annotations 



%% Import Date: 2025-07-11T16:35:38.174+02:00 %%
