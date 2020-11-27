# Overview

This topic describes how to make API requests. You can call API operations by sending HTTP or HTTPS GET requests based on URLs.

## Limits

You can create only a specified number and specified types of dedicated hosts. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md).

If API descriptions, optional parameter values, or available specifications conflict with the resource or specification limits described in the Limits topic, the limits prevails.

## Developer options

You can call an API operation by using the following methods:

-   \(Recommended\) Programming language-specific [SDKs](https://github.com/aliyun) for the API.
-   Alibaba Cloud [OpenAPI Explorer](https://api.aliyun.com/)
-   Configure Alibaba Cloud CLI. For more information, see [What is Alibaba Cloud CLI?]().
-   URL-based API requests.

    **Note:** To send URL requests to the API, you must complete the authentication process and prepare the URL for every request. For more information, see [Request method](/intl.en-US/API Reference/Request method.md).


You can skip the authentication process by using the SDK, CLI, or API Explorer to call API operations.

**Note:** When you call an API operation by using Alibaba Cloud CLI or SDKs, you must delete periods \(.\) from request parameters. For example, you must use `SystemDiskCategory` instead of `SystemDisk.Category`.

## Request syntax

The request URL consists of different parameters and has a fixed syntax. The URL contains common parameters, your signature, and operation-specific parameters. Sample URL requests are provided in every API reference topic. However, these topics do not describe how to encode URLs. You must encode the related URL before you make a request. For more information, see [Request method](/intl.en-US/API Reference/Request method.md), [Common parameters](/intl.en-US/API Reference/Common parameters.md), and [Signature method](/intl.en-US/API Reference/Signature method.md).

The system returns the request result based on your signature verification. The response parameters are displayed if the API call is successful. An error message appears if the API call fails. You can resolve the error based on the common error codes and operation-specific error codes.

DDH shares the same endpoint with Elastic Compute Service \(ECS\). For more information, see [Request syntax](/intl.en-US/API Reference/Getting started/Request syntax.md).

