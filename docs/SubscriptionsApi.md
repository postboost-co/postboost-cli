# SubscriptionsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addGenericSubscription**](SubscriptionsApi.md#addGenericSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription
[**cancelSubscription**](SubscriptionsApi.md#cancelSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription
[**changeSubscriptionPlan**](SubscriptionsApi.md#changeSubscriptionPlan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan
[**checkoutSubscription**](SubscriptionsApi.md#checkoutSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout
[**createSubscription**](SubscriptionsApi.md#createSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription
[**deleteSubscription**](SubscriptionsApi.md#deleteSubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription
[**getSubscription**](SubscriptionsApi.md#getSubscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription
[**removeGenericSubscription**](SubscriptionsApi.md#removeGenericSubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription
[**resumeSubscription**](SubscriptionsApi.md#resumeSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription
[**updateSubscription**](SubscriptionsApi.md#updateSubscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription



## addGenericSubscription

Add generic subscription

Assigns a non-Stripe (generic) subscription plan to the workspace, optionally granting a trial period. Used for AppSumo-style lifetime deals. Admin only.

### Example

```bash
postboost-cli addGenericSubscription workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **addGenericSubscriptionRequest** | [**AddGenericSubscriptionRequest**](AddGenericSubscriptionRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## cancelSubscription

Cancel subscription

Cancels the workspace's Stripe subscription at the end of the current billing period. Admin only.

### Example

```bash
postboost-cli cancelSubscription workspaceUuid=value
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


## changeSubscriptionPlan

Change subscription plan

Switches the workspace to a different Stripe plan. Optionally prorates the change and bills immediately. Admin only.

### Example

```bash
postboost-cli changeSubscriptionPlan workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **changeSubscriptionPlanRequest** | [**ChangeSubscriptionPlanRequest**](ChangeSubscriptionPlanRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## checkoutSubscription

New subscription checkout

Returns a Stripe Checkout URL for a new subscription.

### Example

```bash
postboost-cli checkoutSubscription workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **checkoutSubscriptionRequest** | [**CheckoutSubscriptionRequest**](CheckoutSubscriptionRequest.md) |  |

### Return type

[**CheckoutSubscription200Response**](CheckoutSubscription200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createSubscription

Create subscription

Manually creates a subscription record for the workspace (for external billing integrations). Admin only.

### Example

```bash
postboost-cli createSubscription workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **subscriptionInput** | [**SubscriptionInput**](SubscriptionInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteSubscription

Delete subscription

Removes the subscription record from the workspace. Admin only.

### Example

```bash
postboost-cli deleteSubscription workspaceUuid=value
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


## getSubscription

Get subscription

Returns the active subscription for the workspace, or 'null' if none exists. Admin only.

### Example

```bash
postboost-cli getSubscription workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**Subscription**](Subscription.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## removeGenericSubscription

Remove generic subscription

Removes the generic (non-Stripe) subscription from the workspace. Admin only.

### Example

```bash
postboost-cli removeGenericSubscription workspaceUuid=value
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


## resumeSubscription

Resume subscription

Resumes a previously canceled subscription before it expires. Admin only.

### Example

```bash
postboost-cli resumeSubscription workspaceUuid=value
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


## updateSubscription

Update subscription

Updates the plan ID, status, or trial/pause dates of an existing subscription. Admin only.

### Example

```bash
postboost-cli updateSubscription workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **subscriptionUpdateInput** | [**SubscriptionUpdateInput**](SubscriptionUpdateInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

