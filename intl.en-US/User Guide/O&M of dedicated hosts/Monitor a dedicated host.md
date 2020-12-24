# Monitor a dedicated host

You can view the resource usage of a dedicated host and configure alarm rules in the CloudMonitor console. This allows you to monitor the running status of a dedicated host.

## View the resource usage of a dedicated host

1.  Log on to the [CloudMonitor console](https://cloudmonitor.console.aliyun.com).

2.  In the left-side navigation pane, choose **Dashboard** \> **Dashboards**.

3.  Select **Dedicated Host** from the **Product** list.

4.  Select a region and a dedicated host from the **Dedicated Host** list.

5.  View the resource usage of a dedicated host.

    You can view the monitoring data from the last 30 days. CloudMonitor monitors the computing, networking, and storage resources of a dedicated host. The following table describes the metrics.

    |Resource type|Metric|Unit|Description|
    |-------------|------|----|-----------|
    |Computing resource|UserCpuUtilization|%|The average CPU usage of all the ECS instances on a dedicated host|
    |Networking resource|UserNetworkRxPPS|PPS|The sum of inbound packets of all the ECS instances on a dedicated host per second|
    |UserNetworkTxPPS|PPS|The sum of outbound packets of all the ECS instances on a dedicated host per second|
    |UserNetworkRxBandwidth|bit/s|The total inbound throughput of all the ECS instances on a dedicated host|
    |UserNetworkTxBandwidth|bit/s|The total outbound throughput of all the ECS instances on a dedicated host|
    |Storage resource|UserDiskReadIOPS|IOPS|The total number of requests that read data from the disks of all the ECS instances on a dedicated host|
    |UserDiskWriteIOPS|IOPS|The total number of requests that write data from the disks of all the ECS instances on a dedicated host|
    |UserDiskWriteBPS|Byte/s|The total number of bytes that are read from the disks of all the ECS instances on a dedicated host|
    |UserDiskWriteBPS|Byte/s|The total number of bytes that are written from the disks of all the ECS instances on a dedicated host|


## Create an alarm rule for a dedicated host

You must create alarm contacts and alarm contact groups before you create alarm rules. For more information, see [t116866.md\#](/intl.en-US/Alarm service/Alert contacts/Create an alert contact or alert group.md).

1.  Move the pointer over the metric for which you want to create an alarm rule. Click the ![Create an alarm rule for a dedicated host](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9653909951/p103594.png) icon in the upper-right corner.

2.  Associate an alarm rule with a dedicated host.

    By default, the current dedicated host is associated with the alarm rule. However, you can change the associated dedicated host.

    -   Associate the alarm rule with other dedicated hosts: Select a region from the **Region** list. Then select one or more dedicated hosts from the **Dedicated Host** list.
    -   Associate the alarm rule with all dedicated hosts: Select **All Resources** from the **Resource Range** list.
3.  Configure the alarm rule.

    The following table describes the parameters of a sample alarm rule.

    |Section|Example|Description|
    |-------|-------|-----------|
    |**Alarm Rule**|ddhxxx-cpu|The alarm rule monitors the average CPU usage of all the ECS instances on the dedicated host.|
    |**Rule Description**|    -   UserCpuUtilization
    -   1-minute cycle
    -   Continue for 3 periods
    -   Value
    -   \>=
    -   80%
|If the average CPU usage of all the ECS instances on the dedicated host is greater than or equal to 80% for three consecutive 1-minute cycles, an alarm is triggered.|
    |**Mute for**|30 minutes|If the alarm conditions are still met 30 minutes after the first alarm, another alarm is triggered.|
    |**Effective Period**|19:00 to 20:59|Specifies whether to issue alarms only between 19:00 and 21:00.|

4.  Configure a notification method.

    1.  Select a contact group from the **Contact Group** list. The selected contact group is displayed in the **Selected Groups** list.

    2.  Select an alarm level.

        The alarm level determines the notification method. The following three alarm levels are supported:

        -   Phone + Text Message + Email + DingTalk \(Critical\)
        -   Test Message + Email + DingTalk \(Warning\)
        -   Email + DingTalk \(Info\)
    3.  Set other optional parameters.

        The following parameters are optional:

        -   **Auto Scaling**: Specify a scaling rule that is automatically executed when an alarm is triggered.
        -   The default email subject is Product Name + Metric Name + Instance ID.
        -   **Email Remark**: Enter additional email information.
        -   **HTTP CallBack**: Enter a URL that is accessible from the Internet. CloudMonitor sends HTTP POST requests to push alarm messages to this URL.
        For more information, see [t115255.md\#](/intl.en-US/Alarm service/Alarm rules/Create an event-triggered alert rule.md).


