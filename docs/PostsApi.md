# PostsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addPostToQueue**](PostsApi.md#addPostToQueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
[**approvePost**](PostsApi.md#approvePost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
[**createPost**](PostsApi.md#createPost) | **POST** /{workspaceUuid}/posts | Create post
[**deletePost**](PostsApi.md#deletePost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
[**deletePostsBulk**](PostsApi.md#deletePostsBulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
[**getPost**](PostsApi.md#getPost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
[**getPostAnalytics**](PostsApi.md#getPostAnalytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
[**listPosts**](PostsApi.md#listPosts) | **GET** /{workspaceUuid}/posts | List posts
[**retryPostAccount**](PostsApi.md#retryPostAccount) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account
[**schedulePost**](PostsApi.md#schedulePost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
[**updatePost**](PostsApi.md#updatePost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post



## addPostToQueue

Add post to queue

Add an existing post to the smart publishing queue. Each account of the post gets its own
next free queue slot. Returns '422' when the post has no accounts, the posting schedule has no
available times, or provider requirements are not met.

### Example

```bash
postboost-cli addPostToQueue workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **addPostToQueueRequest** | [**AddPostToQueueRequest**](AddPostToQueueRequest.md) |  | [optional]

### Return type

[**ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## approvePost

Approve post

Approve a post that is pending review. The approver may move the post with 'date'/'time'
(read in 'timezone') and set per-account times with 'accounts_schedule'; without them the
post keeps the time it was submitted with. Provider requirements are validated and reported as '422'.

### Example

```bash
postboost-cli approvePost workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **approvePostRequest** | [**ApprovePostRequest**](ApprovePostRequest.md) |  | [optional]

### Return type

[**ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createPost

Create post

Create a new post. Use 'schedule: true' with 'date' and 'time' to schedule,
'schedule_now: true' to publish immediately, or 'queue: true' to add to the
smart publishing queue (each account gets its own queue slot).

'date', 'time' and 'accounts_schedule' are read in 'timezone' when given,
otherwise in the workspace timezone. Use 'accounts_schedule' to give individual
accounts their own departure time.

Post bodies may reference mentions with '{{mention:<reference>}}' (see the
Mentions endpoints). When the post is scheduled, provider requirements (for example
a network that requires media) are validated up front and reported as '422'.

### Example

```bash
postboost-cli createPost workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postInput** | [**PostInput**](PostInput.md) |  |

### Return type

[**Post**](Post.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deletePost

Delete post

Deletes a post. Use 'delete_mode' to control whether to also remove the published content from social platforms.

### Example

```bash
postboost-cli deletePost workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **deletePostRequest** | [**DeletePostRequest**](DeletePostRequest.md) |  | [optional]

### Return type

[**DeleteResult**](DeleteResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deletePostsBulk

Delete posts (bulk)

Delete multiple posts at once.

### Example

```bash
postboost-cli deletePostsBulk workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **deletePostsBulkRequest** | [**DeletePostsBulkRequest**](DeletePostsBulkRequest.md) |  |

### Return type

[**DeleteResult**](DeleteResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getPost

Get post

Returns a single post with all its versions and associated accounts.

### Example

```bash
postboost-cli getPost workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]

### Return type

[**Post**](Post.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getPostAnalytics

Get post analytics

Engagement metrics for a published post across its accounts (also works for trashed posts), with totals, trends and the best-performing account.

### Example

```bash
postboost-cli getPostAnalytics workspaceUuid=value postUuid=value
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


## listPosts

List posts

Returns a paginated list of posts in the workspace.

### Example

```bash
postboost-cli listPosts workspaceUuid=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **page** | **integer** |  | [optional] [default to 1]

### Return type

[**ListPosts200Response**](ListPosts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## retryPostAccount

Retry publishing to one account

Re-publishes a post to a single account whose publishing failed. Returns '422' when the account is not on the post, the post is still publishing, or the account did not fail.

### Example

```bash
postboost-cli retryPostAccount workspaceUuid=value postUuid=value accountUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **accountUuid** | **string** | UUID of the social media account. | [default to null]

### Return type

[**RetryPostAccountResult**](RetryPostAccountResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## schedulePost

Schedule post

Schedule an existing post. Optionally move it with 'date'/'time' (read in 'timezone') and give
accounts their own times with 'accounts_schedule'. Set 'postNow: true' to publish immediately;
publishing starts within the request and any per-account times are dropped.
Provider requirements are validated and reported as '422'.

### Example

```bash
postboost-cli schedulePost workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **schedulePostRequest** | [**SchedulePostRequest**](SchedulePostRequest.md) |  |

### Return type

[**ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updatePost

Update post

Replaces a post's versions, accounts, tags, and scheduling options. The post must not be in a published state.
'timezone' is honoured: 'date', 'time' and 'accounts_schedule' are read in it. When the post stays
scheduled, provider requirements are validated and reported as '422'.

### Example

```bash
postboost-cli updatePost workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **postInput** | [**PostInput**](PostInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

