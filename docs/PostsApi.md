# PostsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addPostToQueue**](PostsApi.md#addPostToQueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
[**approvePost**](PostsApi.md#approvePost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
[**createPost**](PostsApi.md#createPost) | **POST** /{workspaceUuid}/posts | Create post
[**createRecyclingRule**](PostsApi.md#createRecyclingRule) | **POST** /{workspaceUuid}/recycling-rules | Create a recycling rule
[**createRssFeed**](PostsApi.md#createRssFeed) | **POST** /{workspaceUuid}/rss-feeds | Add an RSS feed
[**deletePost**](PostsApi.md#deletePost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
[**deletePostsBulk**](PostsApi.md#deletePostsBulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
[**deleteRecyclingRule**](PostsApi.md#deleteRecyclingRule) | **DELETE** /{workspaceUuid}/recycling-rules/{ruleUuid} | Delete a recycling rule
[**deleteRssFeed**](PostsApi.md#deleteRssFeed) | **DELETE** /{workspaceUuid}/rss-feeds/{feedUuid} | Delete an RSS feed
[**getPost**](PostsApi.md#getPost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
[**getPostAnalytics**](PostsApi.md#getPostAnalytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
[**getRecyclingRule**](PostsApi.md#getRecyclingRule) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid} | Get a recycling rule
[**getRssFeed**](PostsApi.md#getRssFeed) | **GET** /{workspaceUuid}/rss-feeds/{feedUuid} | Get an RSS feed
[**listPosts**](PostsApi.md#listPosts) | **GET** /{workspaceUuid}/posts | List posts
[**listRecyclingRules**](PostsApi.md#listRecyclingRules) | **GET** /{workspaceUuid}/recycling-rules | List recycling rules
[**listRecyclingRuns**](PostsApi.md#listRecyclingRuns) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid}/runs | List a recycling rule&#39;s runs
[**listRssFeeds**](PostsApi.md#listRssFeeds) | **GET** /{workspaceUuid}/rss-feeds | List RSS feeds
[**pollRssFeed**](PostsApi.md#pollRssFeed) | **POST** /{workspaceUuid}/rss-feeds/{feedUuid}/poll | Check an RSS feed now
[**recyclePost**](PostsApi.md#recyclePost) | **POST** /{workspaceUuid}/posts/{postUuid}/recycle | Recycle a post on an interval
[**retryPostAccount**](PostsApi.md#retryPostAccount) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account
[**schedulePost**](PostsApi.md#schedulePost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
[**updatePost**](PostsApi.md#updatePost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
[**updateRecyclingRule**](PostsApi.md#updateRecyclingRule) | **PUT** /{workspaceUuid}/recycling-rules/{ruleUuid} | Update, pause or resume a recycling rule
[**updateRssFeed**](PostsApi.md#updateRssFeed) | **PUT** /{workspaceUuid}/rss-feeds/{feedUuid} | Update, pause or resume an RSS feed
[**validatePost**](PostsApi.md#validatePost) | **POST** /{workspaceUuid}/posts/validate | Validate post (dry run)



## addPostToQueue

Add post to queue

Add an existing post to the smart publishing queue. Each account of the post gets its own
next free queue slot. Returns '422' when the post has no accounts, the posting schedule has no
available times, or provider requirements are not met. The guardrails check the saved post as
publishing at the queue slot it will get (the earliest next free slot of its accounts), as on
create: '409' duplicate (override with 'X-Allow-Duplicate: true'), '422' account cannot publish,
'429' daily cap on that slot's UTC day or X cap.

### Example

```bash
postboost-cli addPostToQueue workspaceUuid=value postUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]
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
postboost-cli approvePost workspaceUuid=value postUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]
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

**First comment and threads.** A version's 'content' is an ordered array. Item 0 is
the post. Add a second item to publish a first comment on Facebook Page, Instagram and
LinkedIn, or to continue a thread on X, Threads, Bluesky, Mastodon and Pixelfed:

'''json
{
  \"accounts\": [12],
  \"schedule_now\": true,
  \"versions\": [{
    \"account_id\": 0,
    \"is_original\": true,
    \"content\": [
      { \"body\": \"Our API 1.8 is live.\", \"media\": [345] },
      { \"body\": \"Full changelog: https://postboost.co/docs/changelog/\" }
    ]
  }]
}
'''

The comment is posted right after the post goes live. If the comment fails, the post
stays published and the account's entry on the post reports the error.

### Example

```bash
postboost-cli createPost workspaceUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postInput** | [**PostInput**](PostInput.md) |  |
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

### Return type

[**CreatePost201Response**](CreatePost201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createRecyclingRule

Create a recycling rule

Recycles one post ('post_uuid') or a tag pool ('type: tag_pool' + 'tag_uuid') every
'interval_days'. The first run is 'start_at', or one interval from now. Copies are never
published immediately: 'placement: queue' (default) takes each account's next free queue slot,
'same_time' schedules at the source post's time of day, 'draft' leaves a draft.

Copies pass the same guardrails as posts created through the API (duplicate guard,
per-account daily caps, disconnected accounts, X monthly allowance). A refused copy is not
created; the run is logged with the guard's code (see the runs endpoint). X accounts are
left out of copies because X rejects repeated text. Admins and members only.

### Example

```bash
postboost-cli createRecyclingRule workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **recyclingRuleInput** | [**RecyclingRuleInput**](RecyclingRuleInput.md) |  |

### Return type

[**CreateRecyclingRule201Response**](CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createRssFeed

Add an RSS feed

Checks the feed every 30 minutes and turns each item published after the feed was added into
a post for 'account_ids': a draft ('mode: draft', default), a queued post ('mode: queue'), or a
queued post awaiting approval ('mode: needs_approval': it gets the next free queue slot and
publishes only after someone approves it).
The text comes from 'template' with '{title}', '{link}' and '{summary}' placeholders. Each
item becomes at most one post, at most 'max_items_per_run' per check and 20 per workspace per
day. Posts pass the same guardrails as API-created posts. Only public http(s) URLs are
accepted. Admins and members only.

### Example

```bash
postboost-cli createRssFeed workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **rssFeedInput** | [**RssFeedInput**](RssFeedInput.md) |  |

### Return type

[**CreateRssFeed201Response**](CreateRssFeed201Response.md)

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


## deleteRecyclingRule

Delete a recycling rule

Deletes the rule and its run log. Copies it already created stay. Admins and members only.

### Example

```bash
postboost-cli deleteRecyclingRule workspaceUuid=value ruleUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **ruleUuid** | **string** | UUID of the recycling rule. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteRssFeed

Delete an RSS feed

Stops the feed. Posts it already created stay. Admins and members only.

### Example

```bash
postboost-cli deleteRssFeed workspaceUuid=value feedUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **feedUuid** | **string** | UUID of the RSS feed. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
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


## getRecyclingRule

Get a recycling rule

### Example

```bash
postboost-cli getRecyclingRule workspaceUuid=value ruleUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **ruleUuid** | **string** | UUID of the recycling rule. | [default to null]

### Return type

[**CreateRecyclingRule201Response**](CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getRssFeed

Get an RSS feed

### Example

```bash
postboost-cli getRssFeed workspaceUuid=value feedUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **feedUuid** | **string** | UUID of the RSS feed. | [default to null]

### Return type

[**CreateRssFeed201Response**](CreateRssFeed201Response.md)

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


## listRecyclingRules

List recycling rules

Evergreen recycling rules of the workspace, newest first. A rule copies a post (or the least
recently recycled published post with a tag) every 'interval_days' and places the copy in the
queue. Copies are ordinary posts: they show in the calendar and the queue.

### Example

```bash
postboost-cli listRecyclingRules workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListRecyclingRules200Response**](ListRecyclingRules200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listRecyclingRuns

List a recycling rule's runs

The latest 100 runs of the rule, newest first: the copy each run created, or why it skipped
('source_unavailable', 'no_eligible_post', 'no_accounts', 'queue_full',
'x_skipped_identical_text', or a guardrail code such as 'duplicate_post' or
'account_daily_cap_reached').

### Example

```bash
postboost-cli listRecyclingRuns workspaceUuid=value ruleUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **ruleUuid** | **string** | UUID of the recycling rule. | [default to null]

### Return type

[**ListRecyclingRuns200Response**](ListRecyclingRuns200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listRssFeeds

List RSS feeds

RSS and Atom feeds whose new items become posts, newest first.

### Example

```bash
postboost-cli listRssFeeds workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListRssFeeds200Response**](ListRssFeeds200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## pollRssFeed

Check an RSS feed now

Reads the feed immediately instead of waiting for the next check. Limited to 6 calls per minute. Admins and members only.

### Example

```bash
postboost-cli pollRssFeed workspaceUuid=value feedUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **feedUuid** | **string** | UUID of the RSS feed. | [default to null]

### Return type

[**PollRssFeed200Response**](PollRssFeed200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## recyclePost

Recycle a post on an interval

Shortcut for creating a 'post' recycling rule for this post. Same body as
'createRecyclingRule' without 'type', 'post_uuid' and 'tag_uuid'. Admins and members only.

### Example

```bash
postboost-cli recyclePost workspaceUuid=value postUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **recyclingRuleSettings** | [**RecyclingRuleSettings**](RecyclingRuleSettings.md) |  |

### Return type

[**CreateRecyclingRule201Response**](CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## retryPostAccount

Retry publishing to one account

Re-publishes a post to a single account whose publishing failed. Returns '422' when the account is not on the post, the post is still publishing, or the account did not fail.

### Example

```bash
postboost-cli retryPostAccount workspaceUuid=value postUuid=value accountUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **accountUuid** | **string** | UUID of the social media account. | [default to null]
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

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
Provider requirements are validated and reported as '422'. The guardrails check the saved post at
the time it would publish, as on create: '409' duplicate (override with 'X-Allow-Duplicate: true'),
'422' account cannot publish, '429' daily or X cap.

### Example

```bash
postboost-cli schedulePost workspaceUuid=value postUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postUuid** | **string** | UUID of the post. | [default to null]
 **schedulePostRequest** | [**SchedulePostRequest**](SchedulePostRequest.md) |  |
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

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

[**UpdatePost200Response**](UpdatePost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateRecyclingRule

Update, pause or resume a recycling rule

Changes the interval, limit, placement or accounts, or pauses ('active: false') and resumes
the rule. Fields you leave out keep their value. A rule that reached 'max_runs' resumes only
with a higher 'max_runs'. Admins and members only.

### Example

```bash
postboost-cli updateRecyclingRule workspaceUuid=value ruleUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **ruleUuid** | **string** | UUID of the recycling rule. | [default to null]
 **recyclingRuleUpdate** | [**RecyclingRuleUpdate**](RecyclingRuleUpdate.md) |  |

### Return type

[**CreateRecyclingRule201Response**](CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateRssFeed

Update, pause or resume an RSS feed

Fields you leave out keep their value. Resuming ('active: true') clears the error backoff. Admins and members only.

### Example

```bash
postboost-cli updateRssFeed workspaceUuid=value feedUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **feedUuid** | **string** | UUID of the RSS feed. | [default to null]
 **rssFeedUpdate** | [**RssFeedUpdate**](RssFeedUpdate.md) |  |

### Return type

[**CreateRssFeed201Response**](CreateRssFeed201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## validatePost

Validate post (dry run)

Runs everything create-post checks without creating anything: request validation,
network requirements (text length, media count and type, links) for every given account,
whether or not the post is scheduled, and the guardrails (duplicate content, daily caps,
account health). Always answers '200'; read 'valid'. Any workspace member, including
viewers, may call it. Recommended agent loop: account health, validate, then create.

### Example

```bash
postboost-cli validatePost workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **postInput** | [**PostInput**](PostInput.md) |  |

### Return type

[**PreflightResult**](PreflightResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

