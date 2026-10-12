# WebhooksApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createWebhookSubscription**](WebhooksApi.md#createWebhookSubscription) | **POST** /{workspaceUuid}/webhooks/subscriptions | Subscribe a webhook
[**deleteWebhookSubscription**](WebhooksApi.md#deleteWebhookSubscription) | **DELETE** /{workspaceUuid}/webhooks/subscriptions/{subscriptionUuid} | Unsubscribe a webhook
[**listWebhookSubscriptions**](WebhooksApi.md#listWebhookSubscriptions) | **GET** /{workspaceUuid}/webhooks/subscriptions | List webhook subscriptions



## createWebhookSubscription

Subscribe a webhook

Registers a callback URL for the given events, the way n8n, Zapier and Make instant triggers
do. Deliveries are 'POST' requests with a JSON body (see [Webhooks](/webhooks) for the
payload), signed with the returned 'secret' in 'X-Signature' (HMAC-SHA256 of the raw body,
hex encoded) and attempted up to 3 times. Only public 'https://' URLs are accepted. The
'secret' is in this response only. Workspace admins only.

### Example

```bash
postboost-cli createWebhookSubscription workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **webhookSubscriptionInput** | [**WebhookSubscriptionInput**](WebhookSubscriptionInput.md) |  |

### Return type

[**CreateWebhookSubscription201Response**](CreateWebhookSubscription201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteWebhookSubscription

Unsubscribe a webhook

Deletes the webhook and stops its deliveries. Workspace admins only.

### Example

```bash
postboost-cli deleteWebhookSubscription workspaceUuid=value subscriptionUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **subscriptionUuid** | **string** | UUID of the webhook subscription. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listWebhookSubscriptions

List webhook subscriptions

The workspace's webhooks, newest first: subscriptions created through this API and the ones
added in **Settings → Webhooks**. Secrets are never returned here. Workspace admins only;
needs the 'webhooks' plan capability and, for scoped keys, the 'webhooks' ability.

### Example

```bash
postboost-cli listWebhookSubscriptions workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListWebhookSubscriptions200Response**](ListWebhookSubscriptions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

