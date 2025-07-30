The System Architecture was designed in accordance to the Three Tier Architecture Pattern from the IIRA mentioned in the Foundation Chapter. The Three Tier Architecture was selected due to a clear seperation of concerns between edge, platform and enterprise tiers which enables better maintainability. Also the further development of the seperate components is simplified and less error prone in this way. Another advantage of the selected architecture pattern is the seamless integration of additional devices and services. Devices could simply be added in Node-RED as long as they are connected to the shopfloor network. Services could be integrated at the platform or enterprise tier without major changes to the existing system, allowing for flexible expansion and adaptation to new requirements.

The following figure illustrates the architecture.]]![[system_overview.drawio(1).png]]
The sewing machines signal outputs are wired to the PLC. The PLC provides these signals over OPC UA reachable via the shopfloor network. Node-RED has multiple functions in this architecture. First it serves as a kind of IoT gateway that gathers the data from different sources. In this case only the data from the PLC. But it also shall do some processing of the data.  The data is then send to the Database. And from there it can be queried with the dashboarding solution.




**You might describe the rationale for choosing the Three Tier Architecture Pattern, referencing its benefits such as modularity, scalability, and maintainability. It could be useful to explain how each tier (presentation, logic, data) is realized in your system, mapping concrete components (e.g., Node-RED, database, dashboard) to these layers.**
The Three Tier Architecture was selected due to a clear seperation of concerns between edge, platform and enterprise tiers which enables better maintainability. Also the further development of the seperate components is simplified and less error prone in this way. Another advantage of the selected architecture pattern is the seamless integration of additional devices and services. Devices could simply be added in Node-RED as long as they are connected to the shopfloor network. Services could be integrated at the platform or enterprise tier without major changes to the existing system, allowing for flexible expansion and adaptation to new requirements.

- clear separation of concerns between edge, platform, and enterprise tiers
- modularity and maintainability of system components
- scalable integration of additional devices and services

You could discuss the communication protocols in more detail, for example, why OPC UA was selected for PLC communication, and what advantages it offers in terms of interoperability and security.

It may be helpful to mention data flow and data integrity. You could describe how data is validated, processed, and stored, and what measures are in place to ensure reliability and consistency.

You might also address security considerations, such as how access to the PLC, Node-RED, and the database is controlled, and what authentication or encryption mechanisms are used.

If relevant, you could discuss scalability and extensibility. For example, how could the system be expanded to support more machines, additional data sources, or new dashboard features?

Finally, you could briefly mention monitoring and error handling. How does the system detect and respond to failures or anomalies in data collection or processing?

These points would help to provide a more comprehensive and practice-oriented description of your system architecture.