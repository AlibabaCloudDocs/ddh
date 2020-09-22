# Request method

To send a Dedicated Host \(DDH\) API request, you can send an HTTP GET request to the DDH endpoint. You must add the request parameters that correspond to the called API operation. After you call the operation, the system returns a response. The request and response are encoded in UTF-8.

## Request syntax

DDH API operations use the Remote Procedure Call \(RPC\) protocol. You can call API operations by sending HTTP GET requests.

The following request syntax is used:

```
http://Endpoint/?Action=xx&Parameters
```

where:

-   Endpoint: the endpoint of the DDH API is ecs.aliyuncs.com.
-   Action: the name of the operation that you want to perform. For example, to query the details of one or more dedicated hosts, you must set the Action parameter to [DescribeDedicatedHosts](/intl.en-US/API Reference/Dedicated hosts/DescribeDedicatedHosts.md).
-   Version: the version of the API. The version of the DDH API is 2014-05-26.
-   Parameters: the request parameters for the operation. Separate multiple parameters with ampersands \(`&`\).

    Request parameters include both common request parameters and operation-specific parameters. Common parameters include the API version number and identity verification information. For more information, see [Common parameters](/intl.en-US/API Reference/Common parameters.md) and [Signature method](/intl.en-US/API Reference/Signature method.md).


In the following sample, the [DescribeDedicatedHosts](/intl.en-US/API Reference/Dedicated hosts/DescribeDedicatedHosts.md) operation is called to query the details of the dedicated hosts in a region.

**Note:** The sample requests in the DDH API reference are formatted for better readability.

```
https://ecs.aliyuncs.com/?Action=DescribeDedicatedHost
&Format=xml
&Version=2014-05-26
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&TimeStamp=2012-06-01T12:00:00Z
&RegionId=cn-hangzhou
...
```

## Responses

Responses can be returned in the JSON or XML format. The default response format is XML. To change the format, you can specify the `Format` common parameter in requests. For more information, see [Common parameters](/intl.en-US/API Reference/Common parameters.md). The sample responses provided in DDH API Reference are formatted with newlines and indentations for better readability. However, the actual returned results do not have newlines or indentations.

API responses use the HTTP response format. HTTP status codes from 200 to 299 indicate a successful call. Examples:

-   XML format

    ```
    <?xml version="1.0" encoding="UTF-8"?> <!--The root node of the response-->
    <ActionResponse> <!--Returned request ID-->
        <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId> <!--Response data-->
    </ActionResponse>
    ```

-   JSON format

    ```
    {
        "RequestId": "4C467B38-3910-447D-87BC-AC049166F216" /* Response data */
    }
    ```


HTTP status codes from 400 to 499 or from 500 to 599 indicate a successful call. Examples:

-   XML format

    ```
    <?xml version="1.0" encoding="UTF-8"? ><!--The root node of the response-->
    <Error>
        <RequestId>540CFF28-407A-40B5-B6A5-74Bxxxxxxxxx</RequestId> <!-- Request ID -->
        <HostId>ecs.aliyuncs.com</HostId> <!-- Service endpoint -->
        <Code>MissingParameter.CommandId</Code> <!-- Error code -->
        <Message>The input parameter "CommandId" that is mandatory for processing this request is not supplied. </Message> <! --Error message-->
    </Error>
    ```

-   JSON format

    ```
    {
        "RequestId": "540CFF28-407A-40B5-B6A5-74Bxxxxxxxxx", /* Request ID */
        "HostId": "ecs.aliyuncs.com",/* Service Endpoint */
        "Code": "MissingParameter.CommandId",/* Error code */
        "Message": "The input parameter "CommandId" that is mandatory for processing this request is not supplied." /* Error message */
    }
    ```


If an error occurs when you call an API operation, you can troubleshoot the error based on the returned error code. For more information, see [Common error codes](/intl.en-US/API Reference/Common parameters.mdsection_commonErrorCodes) or visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Ecs). If the error persists, you can [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) and provide the HostId and RequestId.

