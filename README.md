# PostBoost Bash CLI

Official Bash CLI for the [PostBoost API](https://postboost.co/docs/api), auto-generated from the OpenAPI spec.

## Install

```bash
curl -LO https://github.com/postboost-co/postboost-cli/releases/latest/download/postboost-cli.tar.gz
tar xzf postboost-cli.tar.gz
```

| | |
|---|---|
| **Releases** | [github.com/postboost-co/postboost-cli/releases](https://github.com/postboost-co/postboost-cli/releases) |
| **GitHub** | [postboost-co/postboost-cli](https://github.com/postboost-co/postboost-cli) |
| **Docs** | [postboost.co/docs/api](https://postboost.co/docs/api) |
| **Version** | v1.8.0 |

## Quick start

```bash
export POSTBOOST_API_TOKEN="YOUR_API_TOKEN"

# List posts
./postboost-cli listPosts --workspaceUuid "YOUR_WORKSPACE_UUID"

# Show all commands
./postboost-cli --help
```

---

## Documentation for API Endpoints

All URIs are relative to */app/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AIApi* | [**blogToSocial**](docs/AIApi.md#blogtosocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
*AIApi* | [**imageAltText**](docs/AIApi.md#imagealttext) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
*AIApi* | [**imageEdit**](docs/AIApi.md#imageedit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
*AIApi* | [**imageGenerate**](docs/AIApi.md#imagegenerate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
*AIApi* | [**imagePrompt**](docs/AIApi.md#imageprompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
*AIApi* | [**imageVariations**](docs/AIApi.md#imagevariations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image
*AccountsApi* | [**getAccount**](docs/AccountsApi.md#getaccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
*AccountsApi* | [**listAccounts**](docs/AccountsApi.md#listaccounts) | **GET** /{workspaceUuid}/accounts | List accounts
*AnalyticsApi* | [**getAccountAnalytics**](docs/AnalyticsApi.md#getaccountanalytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
*AnalyticsApi* | [**getAnalyticsSummary**](docs/AnalyticsApi.md#getanalyticssummary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
*AnalyticsApi* | [**getBestPostingTimes**](docs/AnalyticsApi.md#getbestpostingtimes) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
*AnalyticsApi* | [**getPostAnalytics_0**](docs/AnalyticsApi.md#getpostanalytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*AnalyticsApi* | [**getPostingTimes**](docs/AnalyticsApi.md#getpostingtimes) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap
*MediaApi* | [**abortChunkedUpload**](docs/MediaApi.md#abortchunkedupload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
*MediaApi* | [**completeChunkedUpload**](docs/MediaApi.md#completechunkedupload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
*MediaApi* | [**createMediaFolder**](docs/MediaApi.md#createmediafolder) | **POST** /{workspaceUuid}/media/folders | Create media folder
*MediaApi* | [**deleteMediaBulk**](docs/MediaApi.md#deletemediabulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
*MediaApi* | [**deleteMediaFolder**](docs/MediaApi.md#deletemediafolder) | **DELETE** /{workspaceUuid}/media/folders/{folderUuid} | Delete media folder
*MediaApi* | [**getMedia**](docs/MediaApi.md#getmedia) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
*MediaApi* | [**getRemoteUploadStatus**](docs/MediaApi.md#getremoteuploadstatus) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
*MediaApi* | [**initiateChunkedUpload**](docs/MediaApi.md#initiatechunkedupload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
*MediaApi* | [**initiateRemoteUpload**](docs/MediaApi.md#initiateremoteupload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
*MediaApi* | [**listMedia**](docs/MediaApi.md#listmedia) | **GET** /{workspaceUuid}/media | List media
*MediaApi* | [**listMediaFolders**](docs/MediaApi.md#listmediafolders) | **GET** /{workspaceUuid}/media/folders | List media folders
*MediaApi* | [**updateMedia**](docs/MediaApi.md#updatemedia) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
*MediaApi* | [**updateMediaFolder**](docs/MediaApi.md#updatemediafolder) | **PUT** /{workspaceUuid}/media/folders/{folderUuid} | Update media folder
*MediaApi* | [**uploadChunk**](docs/MediaApi.md#uploadchunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
*MediaApi* | [**uploadMedia**](docs/MediaApi.md#uploadmedia) | **POST** /{workspaceUuid}/media | Upload media (binary)
*MentionsApi* | [**createMention**](docs/MentionsApi.md#createmention) | **POST** /{workspaceUuid}/mentions | Create mention
*MentionsApi* | [**deleteMention**](docs/MentionsApi.md#deletemention) | **DELETE** /{workspaceUuid}/mentions/{mentionId} | Delete mention
*MentionsApi* | [**getMention**](docs/MentionsApi.md#getmention) | **GET** /{workspaceUuid}/mentions/{mentionId} | Get mention
*MentionsApi* | [**listMentions**](docs/MentionsApi.md#listmentions) | **GET** /{workspaceUuid}/mentions | List mentions
*MentionsApi* | [**updateMention**](docs/MentionsApi.md#updatemention) | **PUT** /{workspaceUuid}/mentions/{mentionId} | Update mention
*PostsApi* | [**addPostToQueue**](docs/PostsApi.md#addposttoqueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
*PostsApi* | [**approvePost**](docs/PostsApi.md#approvepost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
*PostsApi* | [**createPost**](docs/PostsApi.md#createpost) | **POST** /{workspaceUuid}/posts | Create post
*PostsApi* | [**deletePost**](docs/PostsApi.md#deletepost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
*PostsApi* | [**deletePostsBulk**](docs/PostsApi.md#deletepostsbulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
*PostsApi* | [**getPost**](docs/PostsApi.md#getpost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
*PostsApi* | [**getPostAnalytics**](docs/PostsApi.md#getpostanalytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*PostsApi* | [**listPosts**](docs/PostsApi.md#listposts) | **GET** /{workspaceUuid}/posts | List posts
*PostsApi* | [**retryPostAccount**](docs/PostsApi.md#retrypostaccount) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account
*PostsApi* | [**schedulePost**](docs/PostsApi.md#schedulepost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
*PostsApi* | [**updatePost**](docs/PostsApi.md#updatepost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
*ReceiptsApi* | [**createReceipt**](docs/ReceiptsApi.md#createreceipt) | **POST** /panel/receipts | Create receipt
*ReceiptsApi* | [**deleteReceipt**](docs/ReceiptsApi.md#deletereceipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt
*ReceiptsApi* | [**deleteReceiptsBulk**](docs/ReceiptsApi.md#deletereceiptsbulk) | **DELETE** /panel/receipts | Delete receipts (bulk)
*ReceiptsApi* | [**getReceipt**](docs/ReceiptsApi.md#getreceipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt
*ReceiptsApi* | [**listReceipts**](docs/ReceiptsApi.md#listreceipts) | **GET** /panel/receipts | List receipts
*ReceiptsApi* | [**updateReceipt**](docs/ReceiptsApi.md#updatereceipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt
*SubscriptionsApi* | [**addGenericSubscription**](docs/SubscriptionsApi.md#addgenericsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription
*SubscriptionsApi* | [**cancelSubscription**](docs/SubscriptionsApi.md#cancelsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription
*SubscriptionsApi* | [**changeSubscriptionPlan**](docs/SubscriptionsApi.md#changesubscriptionplan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan
*SubscriptionsApi* | [**checkoutSubscription**](docs/SubscriptionsApi.md#checkoutsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout
*SubscriptionsApi* | [**createSubscription**](docs/SubscriptionsApi.md#createsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription
*SubscriptionsApi* | [**deleteSubscription**](docs/SubscriptionsApi.md#deletesubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription
*SubscriptionsApi* | [**getSubscription**](docs/SubscriptionsApi.md#getsubscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription
*SubscriptionsApi* | [**removeGenericSubscription**](docs/SubscriptionsApi.md#removegenericsubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription
*SubscriptionsApi* | [**resumeSubscription**](docs/SubscriptionsApi.md#resumesubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription
*SubscriptionsApi* | [**updateSubscription**](docs/SubscriptionsApi.md#updatesubscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription
*TagsApi* | [**createTag**](docs/TagsApi.md#createtag) | **POST** /{workspaceUuid}/tags | Create tag
*TagsApi* | [**deleteTag**](docs/TagsApi.md#deletetag) | **DELETE** /{workspaceUuid}/tags/{tagUuid} | Delete tag
*TagsApi* | [**getTag**](docs/TagsApi.md#gettag) | **GET** /{workspaceUuid}/tags/{tagUuid} | Get tag
*TagsApi* | [**listTags**](docs/TagsApi.md#listtags) | **GET** /{workspaceUuid}/tags | List tags
*TagsApi* | [**updateTag**](docs/TagsApi.md#updatetag) | **PUT** /{workspaceUuid}/tags/{tagUuid} | Update tag
*UsersApi* | [**createUser**](docs/UsersApi.md#createuser) | **POST** /panel/users | Create user
*UsersApi* | [**deleteUser**](docs/UsersApi.md#deleteuser) | **DELETE** /panel/users/{userId} | Delete user
*UsersApi* | [**deleteUsersBulk**](docs/UsersApi.md#deleteusersbulk) | **DELETE** /panel/users | Delete users (bulk)
*UsersApi* | [**getUser**](docs/UsersApi.md#getuser) | **GET** /panel/users/{userId} | Get user
*UsersApi* | [**listUsers**](docs/UsersApi.md#listusers) | **GET** /panel/users | List users
*UsersApi* | [**updateUser**](docs/UsersApi.md#updateuser) | **PUT** /panel/users/{userId} | Update user
*WorkspacesApi* | [**addUserToWorkspace**](docs/WorkspacesApi.md#addusertoworkspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
*WorkspacesApi* | [**createWorkspace**](docs/WorkspacesApi.md#createworkspace) | **POST** /panel/workspaces | Create workspace
*WorkspacesApi* | [**deleteWorkspace**](docs/WorkspacesApi.md#deleteworkspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
*WorkspacesApi* | [**deleteWorkspacesBulk**](docs/WorkspacesApi.md#deleteworkspacesbulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
*WorkspacesApi* | [**getWorkspace**](docs/WorkspacesApi.md#getworkspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
*WorkspacesApi* | [**getWorkspaceAICredits**](docs/WorkspacesApi.md#getworkspaceaicredits) | **GET** /panel/workspaces/{workspaceUuid}/ai-credits | Get workspace AI credits
*WorkspacesApi* | [**listMyWorkspaces**](docs/WorkspacesApi.md#listmyworkspaces) | **GET** /workspaces | List my workspaces
*WorkspacesApi* | [**listWorkspaces**](docs/WorkspacesApi.md#listworkspaces) | **GET** /panel/workspaces | List workspaces
*WorkspacesApi* | [**removeUserFromWorkspace**](docs/WorkspacesApi.md#removeuserfromworkspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
*WorkspacesApi* | [**updateWorkspace**](docs/WorkspacesApi.md#updateworkspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
*WorkspacesApi* | [**updateWorkspaceUser**](docs/WorkspacesApi.md#updateworkspaceuser) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace
