## Choice of Platforms to evaluate
To have a selection of widely used open source IoT platforms to choose from, the ones mentioned by [[gustin2022]] and [[turki2024]] were selected. Which are:

- DeviceHive
- Mainflux
- FIWARE
- Kapua
- OpenBalena
- openMTC
- OpenRemote
- Thingsboard
- Ubuntu Core
- Dgiot
- IoT Sharp
- Nodered
- UMH

## Explanation of the evaluation process
The evaluation process is heavily inspired by the one used by [[gustin2022]] because it mentions a broad selektion of criteria that cover all aspects important to this project as well as a lot of additional criteria. Because it seams rather complex, only some criteria (which are fitting to this project) were chosen and the evaluation technic was simplified. The criteria were also altered to our needs.

### Criteria and their weighting
The criteria also get a weight which stands for the importance of the criterion.

| Group                    | Criterion                                            | Weight |
| ------------------------ | ---------------------------------------------------- | ------ |
| Effort of Implementation | Availability of Documentation                        | KO     |
| Hosting                  | Cloud independence                                   | KO     |
| General                  | Dashboarding Capabilities                            | High   |
| Effort of Implementation | Tutorials                                            | Medium |
| General                  | Actively Maintained                                  | High   |
| General                  | OPC-UA capability                                    | Medium |
| General                  | Fault detection                                      | Medium |
| General                  | Heartbeat monitor                                    | Medium |
| Effort of Implementation | Completion of Server SW                              | High   |
| Effort of Implementation | Development of Server SW                             | High   |
| Effort of Implementation | Examples for Server-side implementation              | Medium |
| General                  | Ability to process raw data and derive KPI's from it | KO     |
Additionally it will be evaluated which of the four common protocols are supported (HTTP, MQTT, CoAP, AMQP)
##### Weights
- Knock-Out: One platform does not meet this and and they are out
- High: Multiplied by 3
- Medium: Multiplied by 2
- Low: Multiplied by 1

##### Deleted criteria

| Group    | Criterion                       | Reason                                                                                                                                                                                           |
| -------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Security | Encryption of Data Traffic      | There was consistently no information available and usually depends on the protocol used to connect to the gateway / devices                                                                     |
| General  | Operating Costs                 | Since the application only needs to scale to up to approximately 25 to 50 devices, the operating costs of the solution won't have much weight. The work of calculating it would not be worth it. |
| Security | Encryption of Databases         | Usually an extern database is used. So it depends on the used database.                                                                                                                          |
| Security | Backup of Databases             | as above                                                                                                                                                                                         |
| General  | Scalability to up to 50 devices | This is a tiny number that every solution can handle                                                                                                                                             |
| General  | Scalability - message troughput | Often no information could be found. Also for this small project it is not that relevant.                                                                                                        |


#### Further explanation of some criteria and their evaluation

##### Data processing & analytics
- 1 Point for basic capabilities needed for this project


# Scoring Results

5 Platforms were not entirely evaluated for the following reasons:

| Platform    | Reason                                            |
| ----------- | ------------------------------------------------- |
| Kapua       | Terrible Documentation                            |
| DeviceHive  | Documentation Website not reachable               |
| Ubuntu Core | Rather an OS for IoT Devices than an IoT Platform |
| Dgiot       | Documentation in Chinese                          |
| IoTSharp    | Documentation Website not reachable               |

The scores of the remaining platforms are as follows:

| Platform    | Knock Out | Score |
| ----------- | --------- | ----- |
| Thingsboard |           | 22,5  |
| OpenBalena  | KO        |       |
| Node-Red    |           | 23    |
| Kapua       | KO        |       |
| DeviceHive  | KO        |       |
| Mainflux    | KO        |       |
| FIWARE      |           | 19    |
| openMTC     | KO        |       |
| OpenRemote  |           | 12    |
| Ubuntu Core | KO        |       |
| Dgiot       | KO        |       |
| IoTSharp    | KO        |       |
| UMH         |           | 22,5  |
The exact composition of the scores can be found [here]([IoT Platform Evaluation.xlsx](https://itagroupde-my.sharepoint.com/:x:/r/personal/n_harrje_ita-academy_de/_layouts/15/Doc.aspx?sourcedoc=%7BF59EF4D0-645B-4786-BA7E-75B097DF621F%7D&file=IoT%20Platform%20Evaluation.xlsx&action=default&mobileredirect=true&DefaultItemOpen=1&ct=1743492254206&wdOrigin=OFFICECOM-WEB.MAIN.EDGEWORTH&cid=45941f4d-e469-46f7-bbc6-b99541c3fc30&wdPreviousSessionSrc=HarmonyWeb&wdPreviousSession=fd834ed8-55c7-4553-ab48-7862ff76f2a7))

Therefore only three platforms were taken into further consideration
- Thingsboard
- Node-red
- UMH
Of which UMH has tremendous hardware requirements that can not be met by our vms.
Usually the data would be retrieved from the kepware gateway via mqtt. In that case Thingsboard and node-red would work. But currently the license is expired. That means for thingsboard the gateway would also needed to be implemented to be able to connect through opc-ua. Also there seems to be more flexibility when working with node-red.