# ActivityApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**listApiActivity**](ActivityApi.md#listApiActivity) | **GET** /{workspaceUuid}/activity | List API activity



## listApiActivity

List API activity

Every write request ('POST', 'PUT', 'DELETE') made through the API in this workspace, newest
first, with the client that made it and its outcome. Kept for 90 days. Send an
'X-PostBoost-Client' header (for example 'my-agent/1.2') to label your requests; otherwise
the 'User-Agent' is recorded.

### Example

```bash
postboost-cli listApiActivity workspaceUuid=value  outcome=value  client=value  since=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **outcome** | [**ApiActivityOutcome**](.md) |  | [optional] [default to null]
 **client** | **string** | Client label prefix, for example 'mcp'. | [optional] [default to null]
 **since** | **string** | Only entries at or after this time (UTC). | [optional] [default to null]
 **page** | **integer** |  | [optional] [default to 1]

### Return type

[**ListApiActivity200Response**](ListApiActivity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

