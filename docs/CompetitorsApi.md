# CompetitorsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addCompetitor**](CompetitorsApi.md#addCompetitor) | **POST** /{workspaceUuid}/competitors | Track a competitor
[**deleteCompetitor**](CompetitorsApi.md#deleteCompetitor) | **DELETE** /{workspaceUuid}/competitors/{competitorId} | Stop tracking a competitor
[**getCompetitor**](CompetitorsApi.md#getCompetitor) | **GET** /{workspaceUuid}/competitors/{competitorId} | Get a competitor
[**listCompetitors**](CompetitorsApi.md#listCompetitors) | **GET** /{workspaceUuid}/competitors | List competitors



## addCompetitor

Track a competitor

Starts tracking a public Instagram business or creator account from one of your Instagram accounts
(connected through a Facebook Page). Returns '202' at once; followers, snapshots and recent media
appear after the background import. '409' if that account already tracks the username. Admins and members only (not viewers).

### Example

```bash
postboost-cli addCompetitor workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **competitorInput** | [**CompetitorInput**](CompetitorInput.md) |  |

### Return type

[**AddCompetitor202Response**](AddCompetitor202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteCompetitor

Stop tracking a competitor

Deletes the competitor with its snapshots and media. Admins and members only (not viewers).

### Example

```bash
postboost-cli deleteCompetitor workspaceUuid=value competitorId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **competitorId** | **integer** | The competitor 'id'. | [default to null]

### Return type

(empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getCompetitor

Get a competitor

The competitor with daily follower snapshots for the last 90 days and its 12 most recent posts.

### Example

```bash
postboost-cli getCompetitor workspaceUuid=value competitorId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **competitorId** | **integer** | The competitor 'id'. | [default to null]

### Return type

[**GetCompetitor200Response**](GetCompetitor200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listCompetitors

List competitors

Instagram business or creator accounts the workspace tracks, by follower count.

### Example

```bash
postboost-cli listCompetitors workspaceUuid=value  account_id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountId** | **integer** | Only competitors tracked from this Instagram account 'id'. | [optional] [default to null]

### Return type

[**ListCompetitors200Response**](ListCompetitors200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

