# HashtagGroupsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createHashtagGroup**](HashtagGroupsApi.md#createHashtagGroup) | **POST** /{workspaceUuid}/hashtag-groups | Create a hashtag group
[**deleteHashtagGroup**](HashtagGroupsApi.md#deleteHashtagGroup) | **DELETE** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Delete a hashtag group
[**getHashtagGroup**](HashtagGroupsApi.md#getHashtagGroup) | **GET** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Get a hashtag group
[**listHashtagGroups**](HashtagGroupsApi.md#listHashtagGroups) | **GET** /{workspaceUuid}/hashtag-groups | List hashtag groups
[**updateHashtagGroup**](HashtagGroupsApi.md#updateHashtagGroup) | **PUT** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Update a hashtag group



## createHashtagGroup

Create a hashtag group

Saves a named set of hashtags (up to 3000 characters). Admins and members only (not viewers).

### Example

```bash
postboost-cli createHashtagGroup workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **hashtagGroupInput** | [**HashtagGroupInput**](HashtagGroupInput.md) |  |

### Return type

[**CreateHashtagGroup201Response**](CreateHashtagGroup201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteHashtagGroup

Delete a hashtag group

Admins and members only (not viewers).

### Example

```bash
postboost-cli deleteHashtagGroup workspaceUuid=value hashtagGroupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **hashtagGroupId** | **string** | The hashtag group 'id'. | [default to null]

### Return type

(empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getHashtagGroup

Get a hashtag group

One hashtag group.

### Example

```bash
postboost-cli getHashtagGroup workspaceUuid=value hashtagGroupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **hashtagGroupId** | **string** | The hashtag group 'id'. | [default to null]

### Return type

[**CreateHashtagGroup201Response**](CreateHashtagGroup201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listHashtagGroups

List hashtag groups

Saved hashtag sets of the workspace, newest first. Paginated with 'page' and 'per_page' (default 100).

### Example

```bash
postboost-cli listHashtagGroups workspaceUuid=value  page=value  per_page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **page** | **integer** | Page number (1-based). | [optional] [default to 1]
 **perPage** | **integer** | Items per page, 1-100. | [optional] [default to 100]

### Return type

[**ListHashtagGroups200Response**](ListHashtagGroups200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateHashtagGroup

Update a hashtag group

Admins and members only (not viewers).

### Example

```bash
postboost-cli updateHashtagGroup workspaceUuid=value hashtagGroupId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **hashtagGroupId** | **string** | The hashtag group 'id'. | [default to null]
 **hashtagGroupInput** | [**HashtagGroupInput**](HashtagGroupInput.md) |  |

### Return type

[**CreateHashtagGroup201Response**](CreateHashtagGroup201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

