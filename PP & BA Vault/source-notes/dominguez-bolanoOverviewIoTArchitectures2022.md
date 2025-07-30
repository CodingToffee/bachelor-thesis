---
Title: "An overview of IoT architectures, technologies, and existing open-source projects" 
Year: 2022 
Authors: Tomás Domínguez-Bolaño, Omar Campos, Valentín Barral, Carlos J. Escudero, José A. García-Naya 
Tags: Internet of Things, Architecture, IoT platforms, IoT software, Open-source
---
Zotero PDF Link: [Volltext](zotero://select/library/items/FULCESCK) 
Related::  

### Persistent Notes 
%% begin notes %% 
Mot important protocols that where mentioned are: matter, http, CoAP, MQTT, AMQP
 %% end notes %% 

### In-text annotations 

 <mark class="hltr-yellow">"1. Matter [40] is a recent protocol being developed by a working group within the Connectivity Standards Alliance (CSA, formerly the Zigbee Alliance). This working group is promoted by important companies such as Amazon, Apple, Google, and Comcast, among many others. The objective of the working group is the development of a new, royalty-free connectivity standard to increase compatibility among smart home products, with security as a fundamental design principle, simplifying development for manufacturers and increasing compatibility for consumers [41]."</mark> [Page 6](zotero://open-pdf/library/items/FULCESCK?page=6&annotation=Q5NYL9ET) 
 
 
Protocols 
 
 <mark class="hltr-yellow">"The Hypertext Transfer Protocol (HTTP) [42] is the base of the communications for the World Wide Web. It is a generic stateless protocol which follows the client–server model, and can be used for many different tasks beyond its use in the World Wide Web. In the IoT world, we can use HTTP to exchange data with a plain publish model or with a polling model. 3. The Constrained Application Protocol (CoAP) [43] is a specialized protocol intended for use in constrained environments (e.g., low-power devices or lossy networks). According to its specification, CoAP is designed for machine to machine (M2M) applications such as smart energy and building automation [43]. CoAP follows a client–server model, similar to HTTP, and in fact, it can be easily adapted to communicate with HTTP endpoints. Hence, in the same way as with HTTP, CoAP can be used to exchange data with a plain publish model or with a polling model. 4. Message Queuing Telemetry Transport (MQTT) [44] is a lightweight publisher-subscriber protocol. According to its specification, MQTT is ideal for M2M and IoT contexts where a small code footprint is required and/or network bandwidth is at a premium [44]. 5. Advanced Message Queuing Protocol (AMQP). There are two widely used versions of AMQP: AMQP 0-9-1 [45], and AMQP 1.0 [46]. For AMQP it is important to consider its version because their specifications differ significantly. On the one hand, the AMQP 0-9-1 protocol follows a publish–subscriber model, defining the interoperability clients and messaging middleware servers (‘‘brokers’’), and thus the only supported data exchange model is the publish–subscriber one. Compared to MQTT, an AMQP 0-9-1 broker uses queues to store received messages from which the consumers should read them (usually one consumer per queue), but MQTT does not use queues, instead it just simply forwards the received messages to the corresponding subscribers. On the other hand, the AMQP 1.0 protocol simply specifies the reliable exchange of business messages between two parties, without requiring a broker, although one may be used. Thus, the AMQP 1.0 protocol can be used to exchange data with a plain publish model, a publisher-subscriber model, or a polling model."</mark> [Page 7](zotero://open-pdf/library/items/FULCESCK?page=7&annotation=CSWZ252P) 
 
 
Protocols 
 


%% Import Date: 2025-03-26T15:09:58.835+01:00 %%
