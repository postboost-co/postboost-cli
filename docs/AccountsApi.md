# AccountsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAccount**](AccountsApi.md#getAccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
[**listAccounts**](AccountsApi.md#listAccounts) | **GET** /{workspaceUuid}/accounts | List accounts



## getAccount

Get account

Returns a single social media account.

### Example

```bash
postboost-cli getAccount workspaceUuid=value accountUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountUuid** | **string** | UUID of the social media account. | [default to null]

### Return type

[**Account**](Account.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listAccounts

List accounts

Returns all social media accounts connected to the workspace, newest first. Optional filters narrow the list.

### Example

```bash
postboost-cli listAccounts workspaceUuid=value  keyword=value  group=value  Specify as:  providers[]=value1 providers[]=value2 providers[]=...  unauthorized=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **keyword** | **string** | Match the account name or username. | [optional] [default to null]
 **group** | **string** | Only accounts in this account group. | [optional] [default to null]
 **providersLeft_Square_BracketRight_Square_Bracket** | [**array[string]**](string.md) | Only accounts of these providers (for example 'instagram', 'linkedin'). | [optional] [default to null]
 **unauthorized** | **boolean** | When 'true', only accounts that need to be reconnected. | [optional] [default to null]

### Return type

[**ListAccounts200Response**](ListAccounts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

