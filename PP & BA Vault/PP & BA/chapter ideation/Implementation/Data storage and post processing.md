**Database setup**
In Influxdb a bucket needs to be set up for the project. A bucket is comparable to what a schema is in a relational DBMS. The bucket is configured with a retention policy and access rights. The retention policy controls for how long data is hold in the bucket. An initial bucket was created where the data is streamed into from Node-RED. At first an unlimited retention policy was configured for this bucket. Later due to concerns for a too large amount of data it was decided to reduce the retention policy to 1 day. After one day the data of the initial bucket is being aggregated and stored in a seperat bucket with unlimited retention policy. The amount of data to be stored there is signifcantly reduced through the aggregation. The aggregations happen in so called tasks, which can be set to be triggered after a certain time interval or through cron syntax which enables the setting of a certain time at which the aggregation happens regularly. The latter is used in this implementation. The reason for that is, that it is important that the aggregation happens between the shift ending and the starting of the next shift. This is because a lot of time aggregations are being done that rely on detecting the start and the end of an event. If the aggregation would be happening in between those events the result would be falsified. The aggregation could also be done every eight hours which would equals the duration of a shift. But due to the legal framework explained in the foundations, the daily aggregation is applied. The aggregation every eight hours would lead to the collection of data that could be traced back to a single worker. When aggregating data over a whole day it encompasses three shifts and therefore no conclusions can be drawn from it about the individual performance of a worker. A nice side effect of that is, that the amount of data that needs to be stored is reduced by two third.
The aggregations are performed using the flux querie language. In the developtment process the aggregations were developed in flux notebooks. These notebooks are similar to jupyter notebooks and can be used in the web UI of the InfluxDB DBMS. Cells for flux queries and additional cells for visualizing the result or displaying the resulting table(s) can be added to the notebook. This way the correct working of the querie can easily be verified. The details about the verification of the results will be described in the Evalution chapter. The results of the aggregations encompass all of the supporting elements.



**Flux Query Language**
The flux query language can look quite different compared to SQL like query languages. Therefore the basics of Flux querying are being explained here. The first step always is to select the bucket of which the data should be used processed as seen in the first row. In every succeeding row the "|>" (pipe forward) is being used. This operater signals that the result of the preceeding operation is being used in the next operation. In the second row the timeframe of the desired data is being specified. This is also typical to do at the beginning to reduce the amount of data and therefore processing time. Additionally the succeeding filtering operations serve a similar purpose and enable the focus on only the relevant data. The measurement is a logical grouping of the data and contains multiple tags and fields. Fields consist of a name and a value and their characteristic is that they change over time. Further processing of the data usually happens after the filtering. There is no limit on how many operations can be chained together. The count operation in this example is one of many aggregate functions that reduce the amount of values to only one. The map function can be used to apply a function on every row. At the end of a query the final result is returned and in this case it is written to another bucket.


**Postprocessing queries**
In this subsection it will be briefly explained how the aggregations for all the supporting elements are being queried.

Processed Quantity
The sum over all thread trimming events where the value is true is being calculated.

Actual Downtime
The downtime events are determined by summing up idle or machine off times that have a longer duration than a set threshold. It must be kept in mind, that sometimes a worker goes to the toilet or takes a little break. So the threshold was set to ten minutes initally. It is then filtered for all events where all signals except for "main_menu_not_sewing" are fals. The latter can be true (idle) or false (machine off). All remaining entries that lie above the theshold are then summed up.

Actual Production Time
The duration of all events where the pattern tag is true is being summed up.

Actual Cycle Time
The duration between two cycle times is measured and summed up. To be sure that no break or downtime event is included in this, the same threshold as in the downtime measurement is applied to filter the values.

Setup Time
The duration from the machine being off to the first sewing event is being measured and summed op for all shifts of the day. The machine being off is characterized by all signals having the value false. The sewing event is characterized by only the "sewing_active" signal being true. 

Idle Time
The duration of all events where all signals except for the "main_menu_not_sewing" are false is measured and summed up. The duration of the break is subtracted. Of course there still could be downtime events contained in these events. But the downtime is simply subtracted in later queries.

Failure Events
All events where all signals are false except for "main_menu_not_sewing" which can be true or false are being filtered out. Then the threshold filter is applied again. The number of events are then counted.

The remaining maintenance elements are left out because they build upon some of the supporting elements like actual down and production time. All of the supporting elements that are "Planned" where also not mentioned, because they cannot be queried but must be defined. 

