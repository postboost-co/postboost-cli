# AnalyticsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAccountAnalytics**](AnalyticsApi.md#getAccountAnalytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
[**getAnalyticsSummary**](AnalyticsApi.md#getAnalyticsSummary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
[**getBestPostingTimes**](AnalyticsApi.md#getBestPostingTimes) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
[**getPostAnalytics_0**](AnalyticsApi.md#getPostAnalytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
[**getPostingTimes**](AnalyticsApi.md#getPostingTimes) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap



## getAccountAnalytics

Get account analytics

Analytics for one account. 'type' selects one of the tabs the account supports (listed in 'tabs' of the response); returns '422' when the account does not support analytics.

### Example

```bash
postboost-cli getAccountAnalytics workspaceUuid=value accountUuid=value  period=value  date_from=value  date_to=value  type=value  page=value  per_page=value  sort_by=value  sort_dir=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountUuid** | **string** | UUID of the social media account. | [default to null]
 **period** | **string** | Preset reporting period. Ignored when 'date_from' and 'date_to' are given. | [optional] [default to this_month]
 **dateFrom** | **string** | Start of a custom range (Y-m-d). Required with 'date_to'; the range may span at most 366 days. | [optional] [default to null]
 **dateTo** | **string** | End of a custom range (Y-m-d). Required with 'date_from'; must not be before it. | [optional] [default to null]
 **type** | **string** | Analytics tab. Defaults to the account's default tab. | [optional] [default to null]
 **page** | **integer** | Page for list-style tabs (for example per-post metrics). | [optional] [default to 1]
 **perPage** | **integer** |  | [optional] [default to null]
 **sortBy** | **string** |  | [optional] [default to null]
 **sortDir** | **string** |  | [optional] [default to desc]

### Return type

[**AccountAnalytics**](AccountAnalytics.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAnalyticsSummary

Get analytics summary

Cross-platform summary (followers, growth, posts, leaderboard, posting streak) over every account that supports analytics, for a preset period or a custom date range.

### Example

```bash
postboost-cli getAnalyticsSummary workspaceUuid=value  period=value  date_from=value  date_to=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **period** | **string** | Preset reporting period. Ignored when 'date_from' and 'date_to' are given. | [optional] [default to this_month]
 **dateFrom** | **string** | Start of a custom range (Y-m-d). Required with 'date_to'; the range may span at most 366 days. | [optional] [default to null]
 **dateTo** | **string** | End of a custom range (Y-m-d). Required with 'date_from'; must not be before it. | [optional] [default to null]

### Return type

[**AnalyticsSummary**](AnalyticsSummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getBestPostingTimes

Get best posting times

The next recommended date and time per account, on or after 'from' (never in the past), within the next 14 days.

### Example

```bash
postboost-cli getBestPostingTimes workspaceUuid=value  Specify as:  accounts[]=value1 accounts[]=value2 accounts[]=...  from=value  timezone=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountsLeft_Square_BracketRight_Square_Bracket** | [**array[string]**](string.md) | Account UUIDs. Defaults to every account in the workspace. | [optional] [default to null]
 **from** | **string** | Earliest date to recommend (Y-m-d). Defaults to now. | [optional] [default to null]
 **timezone** | **string** | Timezone for 'from' and the returned times. Defaults to the workspace timezone. | [optional] [default to null]

### Return type

[**BestPostingTimes**](BestPostingTimes.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getPostAnalytics_0

Get post analytics

Engagement metrics for a published post across its accounts (also works for trashed posts), with totals, trends and the best-performing account.

### Example

```bash
postboost-cli getPostAnalytics_0 workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]

### Return type

[**PostAnalytics**](PostAnalytics.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getPostingTimes

Get posting times heatmap

Engagement scores per weekday and hour, merged across the given accounts (all accounts when none is given), in the requested timezone. Also returns up to three recommended slots.

### Example

```bash
postboost-cli getPostingTimes workspaceUuid=value  Specify as:  accounts[]=value1 accounts[]=value2 accounts[]=...  timezone=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountsLeft_Square_BracketRight_Square_Bracket** | [**array[string]**](string.md) | Account UUIDs. Defaults to every account in the workspace. | [optional] [default to null]
 **timezone** | **string** | Timezone the grid is expressed in. Defaults to the workspace timezone. | [optional] [default to null]

### Return type

[**PostingTimes**](PostingTimes.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

