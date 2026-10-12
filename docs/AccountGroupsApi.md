# AccountGroupsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createAccountGroup**](AccountGroupsApi.md#createAccountGroup) | **POST** /{workspaceUuid}/account-groups | Create an account group
[**deleteAccountGroup**](AccountGroupsApi.md#deleteAccountGroup) | **DELETE** /{workspaceUuid}/account-groups/{accountGroupUuid} | Delete an account group
[**getAccountGroup**](AccountGroupsApi.md#getAccountGroup) | **GET** /{workspaceUuid}/account-groups/{accountGroupUuid} | Get an account group
[**listAccountGroups**](AccountGroupsApi.md#listAccountGroups) | **GET** /{workspaceUuid}/account-groups | List account groups
[**updateAccountGroup**](AccountGroupsApi.md#updateAccountGroup) | **PUT** /{workspaceUuid}/account-groups/{accountGroupUuid} | Update an account group



## createAccountGroup

Create an account group

Creates a named set of accounts of this workspace. Admins and members only (not viewers).

### Example

```bash
postboost-cli createAccountGroup workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountGroupInput** | [**AccountGroupInput**](AccountGroupInput.md) |  |

### Return type

[**CreateAccountGroup201Response**](CreateAccountGroup201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteAccountGroup

Delete an account group

Deletes the group, not its accounts. Admins and members only (not viewers).

### Example

```bash
postboost-cli deleteAccountGroup workspaceUuid=value accountGroupUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountGroupUuid** | **string** | The account group 'uuid'. | [default to null]

### Return type

(empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAccountGroup

Get an account group

One account group.

### Example

```bash
postboost-cli getAccountGroup workspaceUuid=value accountGroupUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountGroupUuid** | **string** | The account group 'uuid'. | [default to null]

### Return type

[**CreateAccountGroup201Response**](CreateAccountGroup201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listAccountGroups

List account groups

Named sets of accounts, sorted by name, with their account ids. Pass 'account_ids' as 'accounts' when you create a post to publish to the whole group. Paginated with 'page' and 'per_page' (default 100). A key limited to some accounts only sees groups whose accounts are all among its accounts, and 'meta.total' counts only those.

### Example

```bash
postboost-cli listAccountGroups workspaceUuid=value  page=value  per_page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **page** | **integer** | Page number (1-based). | [optional] [default to 1]
 **perPage** | **integer** | Items per page, 1-100. | [optional] [default to 100]

### Return type

[**ListAccountGroups200Response**](ListAccountGroups200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateAccountGroup

Update an account group

Replaces the name and the accounts of the group (accounts you leave out are removed). Admins and members only (not viewers).

### Example

```bash
postboost-cli updateAccountGroup workspaceUuid=value accountGroupUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountGroupUuid** | **string** | The account group 'uuid'. | [default to null]
 **accountGroupInput** | [**AccountGroupInput**](AccountGroupInput.md) |  |

### Return type

[**CreateAccountGroup201Response**](CreateAccountGroup201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

