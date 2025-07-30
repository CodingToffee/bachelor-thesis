---
Title: Fog Assisted Industrial IoT Module for Cycle Time Capturing in Apparel Industry
Year: 2022
Authors: Dinindu Koliya Harshanath Webadu Wedanage, Gallage Malith Thiwanka
tags:
  - Apparel
  - industry
  - Data
  - analysis
  - Decision
  - making
  - Floors
  - Fog
  - node
  - Industrial
  - IoT
  - Industries
  - Internet
  - of
  - things
  - Key
  - performance
  - indicator
  - Mobile
  - applications
  - Real-time
  - systems
  - Similar-Work
---
Zotero PDF Link: [Full Text PDF](zotero://select/library/items/YFW9PSLY) 
Related::  

### Persistent Notes 
%% begin notes %% 
**Architecture**
1. Mobile application – used by machine operators or team members to capture cycle time from the production floor.
2. Business administration (BA) application – used by administrators or planners to upload plan data such as takt time and style information to the system.
3. Dashboard – displays real-time operation information including Yamazumi charts for performance analysis and alerts.
4. Fog node – a decentralized computing infrastructure that processes data locally to reduce bandwidth usage and latency. It includes a Java application for backend operations, a message broker (HIVEMQ) for MQTT messaging, and a RethinkDB database for data storage.

**Results**
- The Business Administration (BA) application is used to send line information, style information, and takt time to mobile applications, with data saved in local storage before sending ([page 3](da://viewer/dxx6lyivh7has3kq/3)).
- The mobile application requires takt time to operate; it automatically updates takt time if previously fed. Users record cycle time by tapping a button at the start of each cycle, with the last three cycle times and status displayed ([page 4](da://viewer/dxx6lyivh7has3kq/4)).
- If a user exceeds takt time three consecutive times, a warning status is displayed; otherwise, the status remains excellent ([page 4](da://viewer/dxx6lyivh7has3kq/4)).
- Dashboards located at each production line visualize real-time data analytics through Yamazumi charts, showing cumulative average cycle time per member for the current and previous day ([page 4](da://viewer/dxx6lyivh7has3kq/4)).
- The Yamazumi chart provides alerts by changing bar colors when users exceed takt time, displays current time, style, and takt time assigned to the line, and updates whenever a user presses the button ([page 4](da://viewer/dxx6lyivh7has3kq/4)).
- Users exceeding takt time are shown in red, while those within takt time are shown in blue; a yellow dotted line indicates takt time, and a green bar shows the previous day's performance threshold ([page 4](da://viewer/dxx6lyivh7has3kq/4)).
- Takt time and style can be changed at any time using the BA application ([page 4](da://viewer/dxx6lyivh7has3kq/4)).

**Sensor Types:** The paper does not explicitly mention specific sensor types but describes the use of mobile devices mounted at the front of the dancing module to capture cycle time events from team members ([page 2](da://viewer/dxx6lyivh7has3kq/2)).
**Data Transmission Methods:** The system uses the Message Queuing Telemetry Transport (MQTT) protocol over WebSockets for messaging between mobile applications, business administration applications, dashboards, and the fog node. MQTT is chosen for being lightweight and faster than HTTP. The fog node uses a message broker (HIVEMQ) to handle publish/subscribe messaging (from [page 2](da://viewer/dxx6lyivh7has3kq/2) to [page 3](da://viewer/dxx6lyivh7has3kq/3)).
**Analytics:** The fog node performs short-term analytics on the data locally to reduce latency and bandwidth usage. Real-time alerts and real-time analytics are provided through dashboards displaying Yamazumi charts, which visualize cumulative average cycle times per member compared to takt time. This supports key performance indicators (KPIs) for continuous production improvement. The system enables near-real-time data-driven insights with minimal latency and offline operability due to fog computing
 %% end notes %% 

**Technology Trends mentioned**
- fog computing
- rethinkDB Document based db for realtime web

**Shortcoming of this Approach**
- still manual input is needed (button press) -> leads to inaccurate data
- analytics are limited to simple performance visualisations and don't calculate kpi's
- no data aggregation for  historical analytics
- still depends on the cloud

### In-text annotations 

 <mark class="hltr-yellow">"The module’s four main components include the mobile application, which captures cycle time from the user-end, business administration application designed to get the business and planned information to the system, dashboard and the fog node."</mark> [Page 352](zotero://open-pdf/library/items/YFW9PSLY?page=352&annotation=68KV3AS8) 
 
 
 <mark class="hltr-yellow">"The foremost drawbacks of the current system are not providing real-time data analytics, heavy bandwidth usage, and dashboards are not operable when there is poor internet connectivity. As a solution for these issues, “Fog Computing” is introduced."</mark> [Page 353](zotero://open-pdf/library/items/YFW9PSLY?page=353&annotation=QACUW9W3) 
 
 
 <mark class="hltr-yellow">"Cisco IR829 industrial router has been chosen as the fog node that processes all the mobile applications’ requests. Message Queuing Telemetry Transport (MQTT) has been usedas the messaging protocol since it is a very lightweight and faster-messaging protocol than HyperText Transfer Protocol (HTTP). HIVEMQ is used as the MQTT message broker.RethinkDB is an open-source document database that is used to store data. A java application is developed to process messages sent by mobile/business administration applications and manage the fog node’s local database to operate backend services."</mark> [Page 353](zotero://open-pdf/library/items/YFW9PSLY?page=353&annotation=RKBK6QV8) 
 
 


%% Import Date: 2025-07-11T10:32:50.531+02:00 %%
