# WorkspacesApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addUserToWorkspace**](WorkspacesApi.md#addUserToWorkspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
[**createWorkspace**](WorkspacesApi.md#createWorkspace) | **POST** /panel/workspaces | Create workspace
[**deleteWorkspace**](WorkspacesApi.md#deleteWorkspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
[**deleteWorkspacesBulk**](WorkspacesApi.md#deleteWorkspacesBulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
[**getWorkspace**](WorkspacesApi.md#getWorkspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
[**listWorkspaces**](WorkspacesApi.md#listWorkspaces) | **GET** /panel/workspaces | List workspaces
[**removeUserFromWorkspace**](WorkspacesApi.md#removeUserFromWorkspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
[**updateWorkspace**](WorkspacesApi.md#updateWorkspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
[**updateWorkspaceUser**](WorkspacesApi.md#updateWorkspaceUser) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace



## addUserToWorkspace

Add user to workspace

Adds an existing user to the workspace with a specified role. Admin only.

### Example

```bash
postboost-cli addUserToWorkspace workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **workspaceUserInput** | [**WorkspaceUserInput**](WorkspaceUserInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createWorkspace

Create workspace

Create a new workspace. Admin only.

### Example

```bash
postboost-cli createWorkspace
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceInput** | [**WorkspaceInput**](WorkspaceInput.md) |  |

### Return type

[**Workspace**](Workspace.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteWorkspace

Delete workspace

Permanently deletes a single workspace and all its associated data. Admin only.

### Example

```bash
postboost-cli deleteWorkspace workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteWorkspacesBulk

Delete workspaces (bulk)

Permanently deletes one or more workspaces and all their associated data. Admin only.

### Example

```bash
postboost-cli deleteWorkspacesBulk
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **deleteWorkspacesBulkRequest** | [**DeleteWorkspacesBulkRequest**](DeleteWorkspacesBulkRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getWorkspace

Get workspace

Returns a single workspace by UUID including its subscription status. Admin only.

### Example

```bash
postboost-cli getWorkspace workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**Workspace**](Workspace.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listWorkspaces

List workspaces

Returns a paginated list of all workspaces. Admin only.

### Example

```bash
postboost-cli listWorkspaces  keyword=value  subscription_status=value  access_status=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **keyword** | **string** |  | [optional] [default to null]
 **subscriptionStatus** | **string** |  | [optional] [default to null]
 **accessStatus** | **string** |  | [optional] [default to null]
 **page** | **integer** | Page number (15 items per page). | [optional] [default to 1]

### Return type

[**ListWorkspaces200Response**](ListWorkspaces200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## removeUserFromWorkspace

Remove user from workspace

Removes a user's access to the workspace. The user account is not deleted. Admin only.

### Example

```bash
postboost-cli removeUserFromWorkspace workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **removeUserFromWorkspaceRequest** | [**RemoveUserFromWorkspaceRequest**](RemoveUserFromWorkspaceRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateWorkspace

Update workspace

Updates a workspace's name, color, or access status. Admin only.

### Example

```bash
postboost-cli updateWorkspace workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **workspaceInput** | [**WorkspaceInput**](WorkspaceInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateWorkspaceUser

Update user role in workspace

Changes a user's role or permissions within the workspace. Admin only.

### Example

```bash
postboost-cli updateWorkspaceUser workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **workspaceUserInput** | [**WorkspaceUserInput**](WorkspaceUserInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

