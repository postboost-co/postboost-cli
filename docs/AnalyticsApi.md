# AnalyticsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createReportExport**](AnalyticsApi.md#createReportExport) | **POST** /{workspaceUuid}/reports/exports | Create a report export
[**downloadReportExport**](AnalyticsApi.md#downloadReportExport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid}/download | Download a report file
[**getAccountAnalytics**](AnalyticsApi.md#getAccountAnalytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
[**getAnalyticsSummary**](AnalyticsApi.md#getAnalyticsSummary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
[**getBestPostingTimes**](AnalyticsApi.md#getBestPostingTimes) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
[**getPostAnalytics_0**](AnalyticsApi.md#getPostAnalytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
[**getPostingTimes**](AnalyticsApi.md#getPostingTimes) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap
[**getReportBranding**](AnalyticsApi.md#getReportBranding) | **GET** /{workspaceUuid}/report-branding | Get the report branding
[**getReportExport**](AnalyticsApi.md#getReportExport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid} | Get a report export
[**listReportExports**](AnalyticsApi.md#listReportExports) | **GET** /{workspaceUuid}/reports/exports | List report exports
[**updateReportBranding**](AnalyticsApi.md#updateReportBranding) | **PUT** /{workspaceUuid}/report-branding | Update the report branding
[**uploadReportBrandingLogo**](AnalyticsApi.md#uploadReportBrandingLogo) | **POST** /{workspaceUuid}/report-branding/logo | Upload the report logo



## createReportExport

Create a report export

Generates a report for a period (default 'last_month') or a custom 'date_from'/'date_to'
range: a branded PDF (summary, accounts, top 10 posts; the header uses the report branding)
or a CSV with one row per published post and account ('dataset: posts', default) or per
account ('dataset: accounts'). CSV files are UTF-8 with a byte order mark. At most 500 posts
per report. The file is ready when the call returns; fetch it from 'download_url' with the
same token. Admins and members only; 20 per minute.

### Example

```bash
postboost-cli createReportExport workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **reportExportInput** | [**ReportExportInput**](ReportExportInput.md) |  |

### Return type

[**CreateReportExport201Response**](CreateReportExport201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## downloadReportExport

Download a report file

The PDF or CSV file. '410' once it expired (7 days) or if the export failed.

### Example

```bash
postboost-cli downloadReportExport workspaceUuid=value exportUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **exportUuid** | **string** | UUID of the report export. | [default to null]

### Return type

**binary**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/pdf, text/csv, application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


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


## getReportBranding

Get the report branding

The white-label header of the workspace's PDF reports. Unset fields are 'null'; the workspace name is used then.

### Example

```bash
postboost-cli getReportBranding workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**GetReportBranding200Response**](GetReportBranding200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getReportExport

Get a report export

### Example

```bash
postboost-cli getReportExport workspaceUuid=value exportUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **exportUuid** | **string** | UUID of the report export. | [default to null]

### Return type

[**CreateReportExport201Response**](CreateReportExport201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listReportExports

List report exports

The workspace's latest 50 report exports, newest first. Files can be downloaded for 7 days.

### Example

```bash
postboost-cli listReportExports workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListReportExports200Response**](ListReportExports200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateReportBranding

Update the report branding

Name, colour and footer of PDF reports. Fields you leave out keep their value. Upload the logo with 'uploadReportBrandingLogo'. Admins and members only.

### Example

```bash
postboost-cli updateReportBranding workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **reportBrandingInput** | [**ReportBrandingInput**](ReportBrandingInput.md) |  |

### Return type

[**GetReportBranding200Response**](GetReportBranding200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## uploadReportBrandingLogo

Upload the report logo

PNG or JPEG, up to 1 MB (SVG is not accepted). Replaces the current logo. Admins and members only.

### Example

```bash
postboost-cli uploadReportBrandingLogo workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **logo** | **binary** |  | [default to null]

### Return type

[**GetReportBranding200Response**](GetReportBranding200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

