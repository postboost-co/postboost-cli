# WorkspacesApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addUserToWorkspace**](WorkspacesApi.md#addUserToWorkspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
[**createApiKey**](WorkspacesApi.md#createApiKey) | **POST** /{workspaceUuid}/api-keys | Create a scoped API key
[**createResellerClient**](WorkspacesApi.md#createResellerClient) | **POST** /{workspaceUuid}/clients | Create a client workspace
[**createWorkspace**](WorkspacesApi.md#createWorkspace) | **POST** /panel/workspaces | Create workspace
[**deleteApiKey**](WorkspacesApi.md#deleteApiKey) | **DELETE** /{workspaceUuid}/api-keys/{apiKeyId} | Revoke a scoped API key
[**deleteWorkspace**](WorkspacesApi.md#deleteWorkspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
[**deleteWorkspacesBulk**](WorkspacesApi.md#deleteWorkspacesBulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
[**getWorkspace**](WorkspacesApi.md#getWorkspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
[**getWorkspaceAICredits**](WorkspacesApi.md#getWorkspaceAICredits) | **GET** /panel/workspaces/{workspaceUuid}/ai-credits | Get workspace AI credits
[**getXUsage**](WorkspacesApi.md#getXUsage) | **GET** /{workspaceUuid}/usage/x | X (Twitter) usage
[**listApiKeys**](WorkspacesApi.md#listApiKeys) | **GET** /{workspaceUuid}/api-keys | List scoped API keys
[**listMyWorkspaces**](WorkspacesApi.md#listMyWorkspaces) | **GET** /workspaces | List my workspaces
[**listResellerClients**](WorkspacesApi.md#listResellerClients) | **GET** /{workspaceUuid}/clients | List client workspaces
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


## createApiKey

Create a scoped API key

Creates a least-privilege API key for the calling user, bound to this workspace. Pick the
abilities it gets and, optionally, the accounts it may act on. The plain key is in
'data.token' of this response only; store it safely.

| Ability | Allows |
|---|---|
| 'read' | Every 'GET', plus the 'posts/validate' dry run |
| 'write' | Creating and changing drafts, media, tags, mentions, the brand voice |
| 'publish' | Scheduling, queueing, publishing now, approving and retrying posts, and editing a post that is already scheduled |
| 'ai' | The '/ai/*' endpoints, running agents and turning on agent AI review (they also need AI credits) |
| 'webhooks' | Webhook subscription endpoints |

A scoped key is refused on other workspaces, on the admin panel, on API key management
and on the app's built-in MCP endpoint (use '/mcp/postboost'). With 'account_ids', it may
only name those accounts (in the URL, 'accounts', 'account_ids' or post versions), cannot
touch posts on other accounts, and 'GET accounts' / 'GET posts' only list matching items
(pagination counts are computed before that filter). Workspace admins only, called with
an unscoped key.

### Example

```bash
postboost-cli createApiKey workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **apiKeyInput** | [**ApiKeyInput**](ApiKeyInput.md) |  |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createResellerClient

Create a client workspace

Creates a client workspace on the Reseller client plan, with the caller as its owner and
admin, and links it to this workspace. Fails with '422' and 'code: client_limit_reached' once
the plan's client limit is used (archived clients do not count). Archive clients on the
Client workspaces page. Workspace admins with an unscoped key only.

### Example

```bash
postboost-cli createResellerClient workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **resellerClientInput** | [**ResellerClientInput**](ResellerClientInput.md) |  |

### Return type

[**CreateResellerClient201Response**](CreateResellerClient201Response.md)

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


## deleteApiKey

Revoke a scoped API key

Revokes a scoped key bound to this workspace. It stops working at once. Workspace admins only, called with an unscoped key.

### Example

```bash
postboost-cli deleteApiKey workspaceUuid=value apiKeyId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **apiKeyId** | **integer** | The key's 'id' from 'GET api-keys'. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
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


## getWorkspaceAICredits

Get workspace AI credits

Returns whether the workspace can use AI credits, its remaining balance, and whether the balance is low. Admin only.

### Example

```bash
postboost-cli getWorkspaceAICredits workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**AICredits**](AICredits.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getXUsage

X (Twitter) usage

The workspace's X posts this calendar month (UTC) against its monthly X allowance. Every thread
part is one X post; a part with a link also counts as a link post. Once enforcement is switched
on ('enforced: true'), scheduling to X is refused when the allowance is used up ('429',
'code: x_monthly_cap_reached') and X posts that come due fail with \"Monthly X allowance
reached\". Until then usage is tracked only. Other networks are not affected. See the X policy
in the developer docs.

### Example

```bash
postboost-cli getXUsage workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**XUsage**](XUsage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listApiKeys

List scoped API keys

Scoped API keys bound to this workspace, newest first. The secret is never shown again
after creation. Workspace admins only, called with an unscoped key (a scoped key gets
'403' with 'code: insufficient_scope').

### Example

```bash
postboost-cli listApiKeys workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listMyWorkspaces

List my workspaces

Returns the workspaces the authenticated user belongs to, most recently updated first, with the caller's role in each. Use a returned 'uuid' as 'workspaceUuid'.

### Example

```bash
postboost-cli listMyWorkspaces
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListMyWorkspaces200Response**](ListMyWorkspaces200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listResellerClients

List client workspaces

Client workspaces this workspace created on the Reseller plan, active first, then archived.
'accounts_needing_reconnect' counts accounts whose connection must be renewed. 'meta' gives
the active clients and the plan's client limit. Workspace admins with an unscoped key only;
other workspaces get '403' with 'code: not_a_reseller'.

### Example

```bash
postboost-cli listResellerClients workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListResellerClients200Response**](ListResellerClients200Response.md)

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

Updates a workspace's name, owner, or access status. Admin only. 'hex_color' is accepted but ignored.

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

