# TagsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createTag**](TagsApi.md#createTag) | **POST** /{workspaceUuid}/tags | Create tag
[**deleteTag**](TagsApi.md#deleteTag) | **DELETE** /{workspaceUuid}/tags/{tagUuid} | Delete tag
[**getTag**](TagsApi.md#getTag) | **GET** /{workspaceUuid}/tags/{tagUuid} | Get tag
[**listTags**](TagsApi.md#listTags) | **GET** /{workspaceUuid}/tags | List tags
[**updateTag**](TagsApi.md#updateTag) | **PUT** /{workspaceUuid}/tags/{tagUuid} | Update tag



## createTag

Create tag

Creates a new color-coded tag in the workspace for organizing posts.

### Example

```bash
postboost-cli createTag workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **tagInput** | [**TagInput**](TagInput.md) |  |

### Return type

[**Tag**](Tag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteTag

Delete tag

Permanently deletes a tag. Posts that had this tag attached are unaffected.

### Example

```bash
postboost-cli deleteTag workspaceUuid=value tagUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **tagUuid** | **string** | UUID of the tag. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getTag

Get tag

Returns a single tag by UUID.

### Example

```bash
postboost-cli getTag workspaceUuid=value tagUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **tagUuid** | **string** | UUID of the tag. | [default to null]

### Return type

[**Tag**](Tag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listTags

List tags

Returns all tags defined in the workspace.

### Example

```bash
postboost-cli listTags workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListTags200Response**](ListTags200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateTag

Update tag

Updates a tag's name or color.

### Example

```bash
postboost-cli updateTag workspaceUuid=value tagUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **tagUuid** | **string** | UUID of the tag. | [default to null]
 **tagInput** | [**TagInput**](TagInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

