# AccountsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**connectChannel**](AccountsApi.md#connectChannel) | **POST** /{workspaceUuid}/accounts/connect/{provider} | Connect a Telegram, Discord or Slack channel
[**createReconnectLink**](AccountsApi.md#createReconnectLink) | **POST** /{workspaceUuid}/accounts/{accountUuid}/reconnect-links | Create a reconnect link
[**getAccount**](AccountsApi.md#getAccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
[**getAccountHealth**](AccountsApi.md#getAccountHealth) | **GET** /{workspaceUuid}/account-health | Account health
[**listAccounts**](AccountsApi.md#listAccounts) | **GET** /{workspaceUuid}/accounts | List accounts



## connectChannel

Connect a Telegram, Discord or Slack channel

Connects a channel that uses a bot token or a webhook URL instead of a login. The credentials
are checked against the network first, stored encrypted and never returned. Connecting the same
channel again updates it ('200') instead of adding a second account. Workspace admins only;
counts toward the plan's social account limit.

- **telegram**: 'bot_token' from @BotFather and 'chat' (the channel's '@username', or its
  numeric id such as '-1001234567890' for a private channel). The bot must be an administrator
  of the channel allowed to post messages.
- **discord**: 'webhook_url' from Channel settings → Integrations → Webhooks
  ('https://discord.com/api/webhooks/…').
- **slack**: 'webhook_url' of an incoming webhook ('https://hooks.slack.com/services/…') and an
  optional display 'name'. Slack posts cannot be deleted from PostBoost, and images must be
  publicly reachable.

Webhook URLs on any other host are refused ('422') before any request is made.

### Example

```bash
postboost-cli connectChannel workspaceUuid=value provider=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **provider** | **string** |  | [default to null]
 **connectChannelInput** | [**ConnectChannelInput**](ConnectChannelInput.md) |  |

### Return type

[**ChannelAccount**](ChannelAccount.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createReconnectLink

Create a reconnect link

Creates a single-use link (valid 7 days) that lets someone without a PostBoost login, such as
an agency's client, re-authorize this one account on its network. The link only refreshes the
connection of this account; signing in as a different profile or page changes nothing.
Workspace admins only. Available for Facebook Pages, Instagram, Threads, LinkedIn, TikTok,
YouTube and Pinterest. Returns '404' while the feature is not enabled on this instance.

### Example

```bash
postboost-cli createReconnectLink workspaceUuid=value accountUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountUuid** | **string** | UUID of the social media account. | [default to null]

### Return type

[**ReconnectLink**](ReconnectLink.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


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


## getAccountHealth

Account health

Pre-flight health of every account in the workspace: whether it is authorized and holds an
access token, how much of its daily post cap (per UTC day, scheduled, awaiting approval
and published posts) is used today, and its connection health: predicted token expiry,
latest publish outcome and where to reconnect it. The 'account.token_expiring' and
'account.disconnected' webhooks report changes as they happen.

### Example

```bash
postboost-cli getAccountHealth workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**GetAccountHealth200Response**](GetAccountHealth200Response.md)

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

