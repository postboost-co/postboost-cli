# TemplatesApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createTemplate**](TemplatesApi.md#createTemplate) | **POST** /{workspaceUuid}/templates | Create a template
[**deleteTemplate**](TemplatesApi.md#deleteTemplate) | **DELETE** /{workspaceUuid}/templates/{templateId} | Delete a template
[**getTemplate**](TemplatesApi.md#getTemplate) | **GET** /{workspaceUuid}/templates/{templateId} | Get a template
[**listTemplates**](TemplatesApi.md#listTemplates) | **GET** /{workspaceUuid}/templates | List templates
[**updateTemplate**](TemplatesApi.md#updateTemplate) | **PUT** /{workspaceUuid}/templates/{templateId} | Update a template



## createTemplate

Create a template

Creates a post template: a name and one or more content items (body plus media ids from the media library). Admins and members only (not viewers).

### Example

```bash
postboost-cli createTemplate workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **templateInput** | [**TemplateInput**](TemplateInput.md) |  |

### Return type

[**CreateTemplate201Response**](CreateTemplate201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteTemplate

Delete a template

Admins and members only (not viewers).

### Example

```bash
postboost-cli deleteTemplate workspaceUuid=value templateId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **templateId** | **string** | The template 'id'. | [default to null]

### Return type

(empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getTemplate

Get a template

One template.

### Example

```bash
postboost-cli getTemplate workspaceUuid=value templateId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **templateId** | **string** | The template 'id'. | [default to null]

### Return type

[**CreateTemplate201Response**](CreateTemplate201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listTemplates

List templates

Post templates of the workspace, newest first. The same templates as the Templates page in the app. Paginated with 'page' and 'per_page' (default 100).

### Example

```bash
postboost-cli listTemplates workspaceUuid=value  page=value  per_page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **page** | **integer** | Page number (1-based). | [optional] [default to 1]
 **perPage** | **integer** | Items per page, 1-100. | [optional] [default to 100]

### Return type

[**ListTemplates200Response**](ListTemplates200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateTemplate

Update a template

Replaces the name and content of a template. Admins and members only (not viewers).

### Example

```bash
postboost-cli updateTemplate workspaceUuid=value templateId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **templateId** | **string** | The template 'id'. | [default to null]
 **templateInput** | [**TemplateInput**](TemplateInput.md) |  |

### Return type

[**CreateTemplate201Response**](CreateTemplate201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

