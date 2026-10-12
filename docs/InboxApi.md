# InboxApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**approveInboxReplyDraft**](InboxApi.md#approveInboxReplyDraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/approve | Approve and send a reply draft
[**createInboxReplyDraft**](InboxApi.md#createInboxReplyDraft) | **POST** /{workspaceUuid}/inbox/conversations/{conversationId}/drafts | Draft a reply
[**deleteInboxReplyDraft**](InboxApi.md#deleteInboxReplyDraft) | **DELETE** /{workspaceUuid}/inbox/drafts/{draftId} | Withdraw a reply draft
[**getInboxConversation**](InboxApi.md#getInboxConversation) | **GET** /{workspaceUuid}/inbox/conversations/{conversationId} | Get an inbox conversation
[**getInboxReplyDraft**](InboxApi.md#getInboxReplyDraft) | **GET** /{workspaceUuid}/inbox/drafts/{draftId} | Get a reply draft
[**listInboxConversations**](InboxApi.md#listInboxConversations) | **GET** /{workspaceUuid}/inbox/conversations | List inbox conversations
[**listInboxReplyDrafts**](InboxApi.md#listInboxReplyDrafts) | **GET** /{workspaceUuid}/inbox/drafts | List reply drafts
[**rejectInboxReplyDraft**](InboxApi.md#rejectInboxReplyDraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/reject | Reject a reply draft
[**updateInboxConversation**](InboxApi.md#updateInboxConversation) | **PATCH** /{workspaceUuid}/inbox/conversations/{conversationId} | Update an inbox conversation
[**updateInboxReplyDraft**](InboxApi.md#updateInboxReplyDraft) | **PUT** /{workspaceUuid}/inbox/drafts/{draftId} | Edit a reply draft



## approveInboxReplyDraft

Approve and send a reply draft

Sends the draft to the network (optionally with an edited 'body'). Ends as 'sent', or 'failed' with
'error'. Needs the 'publish' ability; the API key that wrote the draft cannot approve it
('403', 'code: self_approval'). A draft is sent at most once: approving again returns '409'. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli approveInboxReplyDraft workspaceUuid=value draftId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **draftId** | **string** | The draft 'id'. | [default to null]
 **inboxReplyDraftApprove** | [**InboxReplyDraftApprove**](InboxReplyDraftApprove.md) |  | [optional]

### Return type

[**CreateInboxReplyDraft201Response**](CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createInboxReplyDraft

Draft a reply

Proposes a reply. Nothing is posted: a person approves the draft in the app (Reply drafts page) or
another API key with the 'publish' ability approves it. 'in_reply_to' defaults to the latest incoming
message. The body limit depends on the network (Bluesky 300, Mastodon 500, LinkedIn 1250, Google 4000).
Needs the 'write' ability. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli createInboxReplyDraft workspaceUuid=value conversationId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **conversationId** | **string** | The conversation 'id'. | [default to null]
 **inboxReplyDraftInput** | [**InboxReplyDraftInput**](InboxReplyDraftInput.md) |  |

### Return type

[**CreateInboxReplyDraft201Response**](CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteInboxReplyDraft

Withdraw a reply draft

Deletes a pending draft. '409' once it was reviewed. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli deleteInboxReplyDraft workspaceUuid=value draftId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **draftId** | **string** | The draft 'id'. | [default to null]

### Return type

(empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getInboxConversation

Get an inbox conversation

The conversation with its 50 most recent messages, oldest first. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli getInboxConversation workspaceUuid=value conversationId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **conversationId** | **string** | The conversation 'id'. | [default to null]

### Return type

[**GetInboxConversation200Response**](GetInboxConversation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getInboxReplyDraft

Get a reply draft

One draft. Poll it to see whether it was approved and sent. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli getInboxReplyDraft workspaceUuid=value draftId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **draftId** | **string** | The draft 'id'. | [default to null]

### Return type

[**CreateInboxReplyDraft201Response**](CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listInboxConversations

List inbox conversations

Comments, mentions and reviews on your accounts, most recent activity first, 25 per page.
Available for Bluesky, Mastodon, LinkedIn Pages and Google Business Profile. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli listInboxConversations workspaceUuid=value  status=value  account_id=value  provider=value  unread=value  sentiment=value  ai_label=value  since=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **status** | **string** | Conversation status. | [optional] [default to null]
 **accountId** | **integer** | Account 'id'. | [optional] [default to null]
 **provider** | **string** | Network, for example 'bluesky'. | [optional] [default to null]
 **unread** | **boolean** | Only unread ('true') or read ('false') conversations. | [optional] [default to null]
 **sentiment** | **string** | AI sentiment. | [optional] [default to null]
 **aiLabel** | **string** | AI label. | [optional] [default to null]
 **since** | **string** | Only conversations with activity at or after this time. | [optional] [default to null]
 **page** | **integer** | Page number. | [optional] [default to 1]

### Return type

[**ListInboxConversations200Response**](ListInboxConversations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listInboxReplyDrafts

List reply drafts

Reply drafts, newest first, 25 per page. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli listInboxReplyDrafts workspaceUuid=value  status=value  conversation_id=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **status** | **string** | Draft status. | [optional] [default to null]
 **conversationId** | **string** | Only drafts for this conversation 'id'. | [optional] [default to null]
 **page** | **integer** | Page number. | [optional] [default to 1]

### Return type

[**ListInboxReplyDrafts200Response**](ListInboxReplyDrafts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## rejectInboxReplyDraft

Reject a reply draft

Rejects a pending draft; nothing is sent. Needs the 'publish' ability. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli rejectInboxReplyDraft workspaceUuid=value draftId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **draftId** | **string** | The draft 'id'. | [default to null]

### Return type

[**CreateInboxReplyDraft201Response**](CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateInboxConversation

Update an inbox conversation

Marks the conversation open or resolved, read or unread. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli updateInboxConversation workspaceUuid=value conversationId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **conversationId** | **string** | The conversation 'id'. | [default to null]
 **inboxConversationUpdate** | [**InboxConversationUpdate**](InboxConversationUpdate.md) |  |

### Return type

[**GetInboxConversation200Response**](GetInboxConversation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateInboxReplyDraft

Edit a reply draft

Changes the text of a pending draft. '409' once it was reviewed. Requires the inbox API to be enabled for the workspace (otherwise '404'). Admins and members only.

### Example

```bash
postboost-cli updateInboxReplyDraft workspaceUuid=value draftId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **draftId** | **string** | The draft 'id'. | [default to null]
 **inboxReplyDraftEdit** | [**InboxReplyDraftEdit**](InboxReplyDraftEdit.md) |  |

### Return type

[**CreateInboxReplyDraft201Response**](CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

