# Signature method

Alibaba Cloud Dedicated Host \(DDH\) uses request signatures to identify the API caller. This ensures data security when you call API operations. When you initiate HTTP or HTTPS API requests, the requests must include the signature information. This topic describes how to sign a request.

## Step 1: Construct a canonicalized query string

1.  Sort the request parameters. Construct a canonicalized query string by arranging the request parameters in alphabetical order. These request parameters include all common parameters and operation-specific parameters except `Signature`. For more information, see [Common request parameters](/intl.en-US/API Reference/Common parameters.md).

    **Note:** If a request is submitted by using the GET method, the request parameters are specified after the question mark \(`?`\) and separated with ampersands \(`&`\) in the URL.

2.  Encode parameters. Encode the request parameters and parameter values by using the UTF-8 character set and following the [RFC 3986](http://tools.ietf.org/html/rfc3986) specification. The following encoding rules are used:
    -   Letters, digits, hyphens \(`-`\), underscores \(`_`\), periods \(`.`\), and tildes \(`~`\) do not need to be encoded.
    -   Other characters must be percent-encoded in the `%XY` format. `XY` represents the ASCII code of a character in hexadecimal notation. For example, double quotation marks \(`"`\) are encoded as `%22`.
    -   Extended UTF-8 characters are encoded in the `%XY%ZA...` format.
    -   Spaces must be encoded as `%20`. Do not encode spaces as plus signs \(`+`\).

        This encoding format is slightly different from the MIME encoding format `application/x-www-form-urlencoded`.

        If you are using the Java standard library `Java.net.URLEncoder`, you can use `PercentEncode` to encode the request parameters. Then, replace plus signs \(`+`\) with `%20`, asterisks \(`*`\) with `%2A`, and `%7E` with a tilde \(`~`\) to obtain the encoded string.

        ```
        private static final String ENCODING = "UTF-8";
        private static String percentEncode(String value) throws UnsupportedEncodingException {
        return value ! = null ? URLEncoder.encode(value, ENCODING).replace("+", "%20").replace("*", "%2A").replace("%7E", "~") : null;
        }
        ```

3.  Use equal signs \(`=`\) to separate request parameters and their values.
4.  Use ampersands \(`&`\) to concatenate different request parameters. Note that the order of the parameters must be the same as the order used in [Step 1](#li_sort_params).

You can obtain a canonicalized query string \(CanonicalizedQueryString\) that follows the [Request syntax](/intl.en-US/API Reference/Request method.md).

## Step 2: Construct a signature string

1.  Construct a string-to-sign `StringToSign`. You can use `percentEncode` to process the canonicalized query string constructed in Step 1. The following rules are used:

    ```
    StringToSign=
      HTTPMethod + "&" + //HTTPMethod: the HTTP method used to make the request, such as GET.
      percentEncode("/") + "&" + // percentEncode("/"): Encode the forward slash (/) in UTF-8 as %2F.
      percentEncode(CanonicalizedQueryString) //Encode the canonicalized query string created in Step 1.
    ```

2.  Calculate the HMAC-SHA1 value of the string-to-sign [StringToSign](http://www.ietf.org/rfc/rfc2104.txt) based on the `RFC 2104` specification. The Java Base64 encoding scheme is used in this example.

    ```
    Signature = Base64( HMAC-SHA1( AccessSecret, UTF-8-Encoding-Of(StringToSign) ) )
    ```

    **Note:** When you calculate the signature, the key specified in RFC 2104 is your `AccessKeySecret` with an ampersand \(`&`\) whose ASCII value is 38. For more information, see [Create an AccessKey]().

3.  Encode the [Signature](http://tools.ietf.org/html/rfc3986) parameter based on the `RFC 3986` specification and add the encoded signature to the canonicalized query string.

## Example 1: Concatenate parameters

The [DescribeDedicatedHosts](/intl.en-US/API Reference/Dedicated hosts/DescribeDedicatedHosts.md) operation is called in this example to show how to construct a signature by concatenating parameters. If AccessKeyID is set to `testid` and AccessKeySecret to `testsecret`, you can proceed to the following signature process:

1.  Construct a canonicalized query string.

    ```
    http://ecs.aliyuncs.com/?Timestamp=2016-02-23T12%3A46%3A24Z&Format=XML&AccessKeyId=testid&Action=DescribeDedicatedHosts&SignatureMethod=HMAC-SHA1&SignatureNonce=3ee8c1b8-xxxx-xxxx-xxxx-xxxxxxxxxx&Version=2014-05-26&SignatureVersion=1.0
    ```

2.  Construct the string-to-sign `StringToSign`.

    ```
    GET&%2F&AccessKeyId%3Dtestid%26Action%3DDescribeDedicatedHosts%26Format%3DXML%26SignatureMethod%3DHMAC-SHA1%26SignatureNonce%3D3ee8c1b8-xxxx-xxxx-xxxx-xxxxxxxxx%26SignatureVersion%3D1.0%26Timestamp%3D2016-02-23T12%253A46%253A24Z%26Version%3D2014-05-26
    ```

3.  Calculate the signature value. If `AccessKeySecret` is set to testsecret, the key used for calculation is `testsecret&`. The calculated signature is `OLeaidS1JvxuMvnyHOwuJ%2BuX5qY%3D`. In this example, the JavaBase64 encoding scheme is used.

    ```
    Signature = Base64( HMAC-SHA1( AccessSecret, UTF-8-Encoding-Of(StringToSign) ) )
    ```

4.  Add the [Signature=OLeaidS1JvxuMvnyHOwuJ%2BuX5qY%3D](http://tools.ietf.org/html/rfc3986) string that has been encoded based on `RFC 3986` to the URL in [Step 1](#li_StringToRequest).

    ```
    http://ecs.aliyuncs.com/?SignatureVersion=1.0&Action=DescribeDedicatedHosts&Format=XML&SignatureNonce=3ee8c1b8-xxxx-xxxx-xxxx-xxxxxxxxx&Version=2014-05-26&AccessKeyId=testid&Signature=OLeaidS1JvxuMvnyHOwuJ%2BuX5qY%3D&SignatureMethod=HMAC-SHA1&Timestamp=2016-02-23T12%253A46%253A24Z
    ```


After you obtain the new URL in [Step 4](#li_final_url), you can use a browser, cURL, or wget to initiate an HTTP request to call the `DescribeDedicatedHosts` operation to query the details of one or more dedicated hosts.

## Example 2: Use the standard library of the programming language

The [DescribeDedicatedHosts](/intl.en-US/API Reference/Dedicated hosts/DescribeDedicatedHosts.md) operation is called in this example to show how to construct the signature by using the standard library. This example assumes that AccessKeyID is set to `testid` and AccessKeySecret is set to `testsecret`, and all request parameters are placed in a Java `Map<String, String>` object.

1.  Predefine the encoding method.

    ```
    private static final String ENCODING = "UTF-8";
    private static String percentEncode(String value) throws UnsupportedEncodingException {
      return value ! = null ? URLEncoder.encode(value, ENCODING).replace("+", "%20").replace("*", "%2A").replace("%7E", "~") : null;
    }
    ```

2.  Predefine the time format for the `Timestamp` parameter. The `Timestamp` parameter must conform to the [ISO8601](/intl.en-US/API Reference/Appendix/ISO 8601 Time Format.md) specification and must be in UTC+0.

    ```
    private static final String ISO8601_DATE_FORMAT = "yyyy-MM-dd'T'HH:mm:ss'Z'";
    private static String formatIso8601Date(Date date) {
      SimpleDateFormat df = new SimpleDateFormat(ISO8601_DATE_FORMAT);
      df.setTimeZone(new SimpleTimeZone(0, "GMT"));
      return df.format(date);
    }
    ```

3.  Construct the canonicalized query string.

    ```
    final String HTTP_METHOD = "GET";
    Map parameters = new HashMap();
    // Specify request parameters.
    parameters.put("Action", "DescribeDedicatedHosts");
    parameters.put("Version", "2014-05-26");
    parameters.put("AccessKeyId", "testid");
    parameters.put("Timestamp", formatIso8601Date(new Date()));
    parameters.put("SignatureMethod", "HMAC-SHA1");
    parameters.put("SignatureVersion", "1.0");
    parameters.put("SignatureNonce", UUID.randomUUID().toString());
    parameters.put("Format", "XML");
    // Sort the request parameters.
    String[] sortedKeys = parameters.keySet().toArray(new String[]{});
    Arrays.sort(sortedKeys);
    final String SEPARATOR = "&";
    //Construct a stringToSign string.
    StringBuilder stringToSign = new StringBuilder();
    stringToSign.append(HTTP_METHOD).append(SEPARATOR);
    stringToSign.append(percentEncode("/")).append(SEPARATOR);
    StringBuilder canonicalizedQueryString = new StringBuilder();
    for(String key : sortedKeys) {
    // Encode the key and value.
      canonicalizedQueryString.append("&")
      .append(percentEncode(key)).append("=")
      .append(percentEncode(parameters.get(key)));
    }
    // Encode the canonicalized query string.
    stringToSign.append(percentEncode(
      canonicalizedQueryString.toString().substring(1)));
    ```

4.  Calculate the signature. If `AccessKeySecret` is set to testsecret, the key used for calculation is `testsecret&`. The calculated signature is `OLeaidS1JvxuMvnyHOwuJ%2BuX5qY%3D`.

    ```
    //The following sample code shows how to calculate the signature:
    final String ALGORITHM = "HmacSHA1";
    final String ENCODING = "UTF-8";
    key = "testsecret&";
    Mac mac = Mac.getInstance(ALGORITHM);
    mac.init(new SecretKeySpec(key.getBytes(ENCODING), ALGORITHM));
    byte[] signData = mac.doFinal(stringToSign.getBytes(ENCODING));
    String signature = new String(Base64.encodeBase64(signData));
    ```

    Encode the Signature parameter based on the [RFC 3986](http://tools.ietf.org/html/rfc3986) specification. Add the Signature parameter to the URL. You can then obtain the following new URL:

    ```
    http://ecs.aliyuncs.com/?SignatureVersion=1.0&Action=DescribeDedicatedHosts&Format=XML&SignatureNonce=3ee8c1b8-xxxx-xxxx-xxxxx-xxxxx&Version=2014-05-26&AccessKeyId=testid&Signature=OLeaidS1JvxuMvnyHOwuJ%2BuX5qY%3D&SignatureMethod=HMAC-SHA1&Timestamp=2016-02-23T12%253A46%253A24Z
    ```

5.  Send HTTP requests by using a browser, cURL, or wget.

    By default, the response is in the following XML format: If you set Format to `JSON`, then the response is in the JSON format. For more information, see [Responses](/intl.en-US/API Reference/Request method.md).

    ```
    <DescribeDedicatedHostsResponse>
      <PageNumber>1</PageNumber>
      <DedicatedHosts>
        <DedicatedHost>
          <DedicatedHostId>dh-2xxxxxxxxxxxxx</DedicatedHostId>
          <ChargeType>PostPaid</ChargeType>
          <Description/>
          <ResourceGroupId/>
          <SupportedInstanceTypeFamilies>
            <SupportedInstanceTypeFamily>ecs.se1ne</SupportedInstanceTypeFamily>
          </SupportedInstanceTypeFamilies>
          <Instances/>
          <Cores>32</calCores>
          <ZoneId>cn-beijing-c</ZoneId>
          <CreationTime>2018-08-13T07:59Z</CreationTime>
          <Sockets>2</Sockets>
          <Status>Available</Status>
          <DedicatedHostType>ddh.se1ne</DedicatedHostType>
          <RegionId>cn-beijing</RegionId>
          <DedicatedHostName>myDDH</DedicatedHostName>
          <SaleCycle/>
          <AutoReleaseTime/>
          <Capacity>
            <AvailableVcpus>56</AvailableVcpus>
            <TotalMemory>448.0</TotalMemory>
            <TotalVcpus>56</TotalVcpus>
            <AvailableLocalStorage>0</AvailableLocalStorage>
            <TotalLocalStorage>0</TotalLocalStorage>
            <LocalStorageCategory/>
            <AvailableMemory>448.0</AvailableMemory>
          </Capacity>
          <OperationLocks/>
          <MachineId>d7xxxxxxxxxxxxxxxxxdb</MachineId>
          <ExpiredTime>2999-09-08T16:00Z</ExpiredTime>
        </DedicatedHost>
        <DedicatedHost>
          <DedicatedHostId>dh-2xxxxxxxxxxxxx</DedicatedHostId>
          <ChargeType>PostPaid</ChargeType>
          <Description/>
          <ResourceGroupId/>
          <SupportedInstanceTypeFamilies>
            <SupportedInstanceTypeFamily>ecs.se1ne</SupportedInstanceTypeFamily>
          </SupportedInstanceTypeFamilies>
          <Instances/>
          <Cores>32</Cores>
          <ZoneId>cn-beijing-c</ZoneId>
          <CreationTime>2018-08-13T07:59Z</CreationTime>
          <Sockets>2</Sockets>
          <Status>Available</Status>
          <DedicatedHostType>ddh.se1ne</DedicatedHostType>
          <RegionId>cn-beijing</RegionId>
          <DedicatedHostName>myDDH</DedicatedHostName>
          <SaleCycle/>
          <AutoReleaseTime/>
          <Capacity>
            <AvailableVcpus>56</AvailableVcpus>
            <TotalMemory>448.0</TotalMemory>
            <TotalVcpus>56</TotalVcpus>
            <AvailableLocalStorage>0</AvailableLocalStorage>
            <TotalLocalStorage>0</TotalLocalStorage>
            <LocalStorageCategory/>
            <AvailableMemory>448.0</AvailableMemory>
          </Capacity>
          <OperationLocks/>
          <MachineId>fxxxxxxxxxxxxxxx6ca6</MachineId>
          <ExpiredTime>2999-09-08T16:00Z</ExpiredTime>
        </DedicatedHost>
      </DedicatedHosts>
      <TotalCount>2</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>C9E9EA51-6B74-409E-BA40-107126A200D4</RequestId>
    </DescribeDedicatedHostsResponse>
    ```


