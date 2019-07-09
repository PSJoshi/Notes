## Logs vs Metrics
### What are logs
A log message is system generated set of data when an event has happended and it describes the event. Log data contain details about the event such as what resource was accessed, who accessed it and the time. Each event in a system is going to have different sets of data in the message. In general, there are five different categories of logs - informational, debug, warning, error and alert.

### What are metrics
While logs are about specific event, metrics are a measurement at a point in time for the system. This can have value, timestamp and identifier(tag). While logs may be collected at any time after event has happened, metrics are typically collected at a fixed time interval known as resolution. The collection of data is referred to as time-series metric and can be visualized in different types of graphs such as guages, counters and timers.
Although measurement of health of system can be stored in performance log file, it is costly to collect health of system. A metric will normalize log file data and the size of metric file will be a fraction of size of entire log file.

In summary, a log is an event that happened and a metric is a measurement of the health of a system.

Based on nice explanation from - https://www.sumologic.com/blog/logs-metrics-overview/
Another interesting take on log vs metrics is here - https://whiteink.com/2019/logs-vs-metrics-a-false-dichotomy/
