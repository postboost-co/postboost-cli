# MentionsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createMention**](MentionsApi.md#createMention) | **POST** /{workspaceUuid}/mentions | Create mention
[**deleteMention**](MentionsApi.md#deleteMention) | **DELETE** /{workspaceUuid}/mentions/{mentionId} | Delete mention
[**getMention**](MentionsApi.md#getMention) | **GET** /{workspaceUuid}/mentions/{mentionId} | Get mention
[**listMentions**](MentionsApi.md#listMentions) | **GET** /{workspaceUuid}/mentions | List mentions
[**updateMention**](MentionsApi.md#updateMention) | **PUT** /{workspaceUuid}/mentions/{mentionId} | Update mention



## createMention

Create mention

Adds a person or page to the mention book. When one of the submitted identities already
belongs to a stored mention, that mention is reused and the identities are added to it
(status '200' instead of '201').

### Example

```bash
postboost-cli createMention workspaceUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **mentionInput** | [**MentionInput**](MentionInput.md) |  |
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

### Return type

[**CreateMention201Response**](CreateMention201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteMention

Delete mention

Removes a mention from the mention book. 'success' is false when nothing was deleted.

### Example

```bash
postboost-cli deleteMention workspaceUuid=value mentionId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **mentionId** | **string** | The mention's 'id' (a UUID). | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getMention

Get mention

Returns a single mention with its identities.

### Example

```bash
postboost-cli getMention workspaceUuid=value mentionId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **mentionId** | **string** | The mention's 'id' (a UUID). | [default to null]

### Return type

[**CreateMention201Response**](CreateMention201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listMentions

List mentions

Returns a paginated list of the workspace's mention book, ranked, with each entry's network identities.

### Example

```bash
postboost-cli listMentions workspaceUuid=value  q=value  per_page=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **q** | **string** | Search keyword. | [optional] [default to null]
 **perPage** | **integer** |  | [optional] [default to 25]
 **page** | **integer** |  | [optional] [default to 1]

### Return type

[**ListMentions200Response**](ListMentions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateMention

Update mention

Replaces the mention's name, avatar and identities. Identities for providers not in the payload are removed. An identity already held by another mention returns '422'.

### Example

```bash
postboost-cli updateMention workspaceUuid=value mentionId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **mentionId** | **string** | The mention's 'id' (a UUID). | [default to null]
 **mentionInput** | [**MentionInput**](MentionInput.md) |  |

### Return type

[**CreateMention201Response**](CreateMention201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

