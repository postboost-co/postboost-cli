# PostingScheduleApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getPostingSchedule**](PostingScheduleApi.md#getPostingSchedule) | **GET** /{workspaceUuid}/posting-schedule | Get the posting schedule
[**getRecommendedPostingTimes**](PostingScheduleApi.md#getRecommendedPostingTimes) | **GET** /{workspaceUuid}/posting-schedule/recommended | Get recommended posting times
[**listQueueSlots**](PostingScheduleApi.md#listQueueSlots) | **GET** /{workspaceUuid}/queue/slots | List upcoming queue slots
[**resetAccountPostingSchedule**](PostingScheduleApi.md#resetAccountPostingSchedule) | **DELETE** /{workspaceUuid}/posting-schedule/{accountId} | Reset an account schedule
[**updatePostingSchedule**](PostingScheduleApi.md#updatePostingSchedule) | **PUT** /{workspaceUuid}/posting-schedule | Set the posting schedule



## getPostingSchedule

Get the posting schedule

The queue's posting times: per weekday, a list of clock times in the schedule's timezone.
'account_id=0' is the workspace schedule. An account without its own schedule follows the
workspace one ('inherited: true', 'source_account_id: 0'). Posts added to the queue take the next free time.

### Example

```bash
postboost-cli getPostingSchedule workspaceUuid=value  account_id=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountId** | **integer** | '0' (default) for the workspace schedule, or an account 'id'. | [optional] [default to 0]

### Return type

[**GetPostingSchedule200Response**](GetPostingSchedule200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getRecommendedPostingTimes

Get recommended posting times

Suggested posting times from past engagement, in the schedule's timezone. 'has_data' is false
until there is enough analytics history.

### Example

```bash
postboost-cli getRecommendedPostingTimes workspaceUuid=value  account_id=value  slots_per_day=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountId** | **integer** | '0' (default) for the workspace schedule, or an account 'id'. | [optional] [default to 0]
 **slotsPerDay** | **integer** | Times to suggest per day (1 to 6). | [optional] [default to null]

### Return type

[**RecommendedPostingTimes**](RecommendedPostingTimes.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listQueueSlots

List upcoming queue slots

The queue read forward: upcoming posting times, filled by scheduled posts where they land on one.
Page with 'after' set to the previous 'next_cursor'.

### Example

```bash
postboost-cli listQueueSlots workspaceUuid=value  account_id=value  after=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountId** | **integer** | '0' (default) for the workspace schedule, or an account 'id'. | [optional] [default to 0]
 **after** | **string** | Start after this time ('Y-m-d H:i:s', UTC), from 'next_cursor'. | [optional] [default to null]

### Return type

[**QueueSlots**](QueueSlots.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## resetAccountPostingSchedule

Reset an account schedule

Removes the account's own schedule so it follows the workspace schedule again. Workspace admins only.

### Example

```bash
postboost-cli resetAccountPostingSchedule workspaceUuid=value accountId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **accountId** | **integer** | The account 'id'. | [default to null]

### Return type

[**GetPostingSchedule200Response**](GetPostingSchedule200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updatePostingSchedule

Set the posting schedule

Sets the workspace schedule ('account_id: 0') or gives one account its own schedule. Send all seven
weekdays (ids 1 to 6 for Monday to Saturday, 0 for Sunday). Workspace admins only.

### Example

```bash
postboost-cli updatePostingSchedule workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postingScheduleInput** | [**PostingScheduleInput**](PostingScheduleInput.md) |  |

### Return type

[**GetPostingSchedule200Response**](GetPostingSchedule200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

