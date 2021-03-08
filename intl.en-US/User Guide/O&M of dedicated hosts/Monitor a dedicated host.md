# Monitor a dedicated host

You can view the resource usage of a dedicated host and configure alert rules in the Cloud Monitor console. This allows you to monitor the running status of a dedicated host.

## View the resource usage of a dedicated host

1.  Log on to the [Cloud Monitor console](https://cloudmonitor.console.aliyun.com).

2.  In the left-side navigation pane, click **Cloud products**.

3.  In the **Elastic calculation** section, click **Dedicated Host**.

4.  On the **Dedicated Host** page, select the region and ID of the instance that you want to view.

5.  View the resource usage of a dedicated host.

    You can view the monitoring data of the last 30 days. Cloud Monitor monitors the computing, networking, and storage resources of a dedicated host. The following table describes the metrics.

    |Resource type|Metric|Unit|Description|
    |-------------|------|----|-----------|
    |Computing resource|UserCpuUtilization|%|The average CPU usage of all the ECS instances on a dedicated host|
    |Networking resource|UserNetworkRxPPS|PPS|The sum of inbound packets of all the ECS instances on a dedicated host per second|
    |UserNetworkTxPPS|PPS|The sum of outbound packets of all the ECS instances on a dedicated host per second|
    |UserNetworkRxBandwidth|bit/s|The total inbound bandwidth of all the ECS instances on a dedicated host per second|
    |UserNetworkTxBandwidth|bit/s|The total outbound bandwidth of all the ECS instances on a dedicated host per second|
    |Storage resource|The read capacity of virtual machines running on a dedicated host|IOPS|The total number of requests that read data from the disks of all the ECS instances on a dedicated host|
    |UserDiskWriteIOPS|IOPS|The total number of requests that write data to the disks of all the ECS instances on a dedicated host|
    |UserDiskReadBPS|Byte/s|The total number of bytes that are read from the disks of all the ECS instances on a dedicated host|
    |UserDiskWriteBPS|Byte/s|The total number of bytes that are written to the disks of all the ECS instances on a dedicated host|


## Create an alert rule for a dedicated host

You must create alert contacts and alert contact groups before you create alert rules. For more information, see [Create an alert contact or alert group](/intl.en-US/Alarm service/Alert contacts/Create an alert contact or alert group.md).

1.  Move the pointer over the metric for which you want to create an alert rule. Click the ![Create an alert rule](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5334915161/p212965.png) icon in the upper-right corner.

2.  Associate an alert rule with a dedicated host.

    By default, the current dedicated host is associated with the alert rule. However, you can change the associated dedicated host.

    -   To associate the alert rule with other dedicated hosts, select a region from the **Region** list. Then, select one or more dedicated hosts from the **Dedicated Host** list.
    -   To associate the alert rule with all dedicated hosts, select **All Resources** from the **Resource Range** list.
3.  Configure the alert rule.

    The following table describes the parameters of a sample alert rule.

    |Region|Example|Description|
    |------|-------|-----------|
    |**Rule Name**|ddhxxx-cpu|The alert rule monitors the average CPU usage of all the ECS instances on the dedicated host.|
    |**Rule Description**|    -   UserCpuUtilization
    -   1-minute cycle
    -   Continue for three cycles
    -   Value
    -   \>=
    -   80%
|If the average CPU usage of all the ECS instances on the dedicated host is greater than or equal to 80% for three consecutive 1-minute cycles, an alert is triggered.|
    |**Mute for**|30 minutes|If the alert conditions are still met 30 minutes after the first alert, another alert notification is sent.|
    |**Effective Period**|19:00 to 20:59|Specifies whether to trigger alerts only between 19:00 and 21:00.|

4.  Configure a notification method.

    1.  Select a contact group from the **Contact Group** list. Click ![Move To](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5334915161/p217470.png). The selected contact group is displayed in the **Selected Groups** list.

    2.  Select an alert level.

        The alert level determines the notification method. The following three alert levels are supported:

        -   Critical. If a critical alert occurs, a notification is sent to specified recipients by using a voice call, text message, DingTalk message, and an email.
        -   Warning. If a warning alert occurs, a notification is sent to specified recipients by using a text message, DingTalk message, and an email.
        -   Info. If an info alert occurs, a notification is sent to specified recipients by using an email and a DingTalk message.
    3.  Set other optional parameters.

        The following parameters are optional:

        -   **Auto Scaling**: Specify a scaling rule that is automatically executed when an alert is triggered.
        -   **Log Service**: Specify a region, project, and Logstore. If an alert is triggered, the alert information is written to the Logstore.
        -   **Email Subject**: The default email subject is Product Name + Metric Name + Instance ID.
        -   **Email Remark**: Enter the email description.
        -   **HTTP CallBack**: Enter a URL that is accessible from the Internet. Cloud Monitor sends HTTP POST requests to push alert messages to this URL.
        For more information, see [Create a threshold-triggered alert rule](/intl.en-US/Alarm service/Alarm rules/Create a threshold-triggered alert rule.md).


