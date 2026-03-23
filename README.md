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
| **Version** | v1.4.0 |

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
*AccountsApi* | [**getAccount**](docs/AccountsApi.md#getaccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
*AccountsApi* | [**listAccounts**](docs/AccountsApi.md#listaccounts) | **GET** /{workspaceUuid}/accounts | List accounts
*MediaApi* | [**abortChunkedUpload**](docs/MediaApi.md#abortchunkedupload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
*MediaApi* | [**completeChunkedUpload**](docs/MediaApi.md#completechunkedupload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
*MediaApi* | [**deleteMediaBulk**](docs/MediaApi.md#deletemediabulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
*MediaApi* | [**getMedia**](docs/MediaApi.md#getmedia) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
*MediaApi* | [**getRemoteUploadStatus**](docs/MediaApi.md#getremoteuploadstatus) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
*MediaApi* | [**initiateChunkedUpload**](docs/MediaApi.md#initiatechunkedupload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
*MediaApi* | [**initiateRemoteUpload**](docs/MediaApi.md#initiateremoteupload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
*MediaApi* | [**listMedia**](docs/MediaApi.md#listmedia) | **GET** /{workspaceUuid}/media | List media
*MediaApi* | [**updateMedia**](docs/MediaApi.md#updatemedia) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
*MediaApi* | [**uploadChunk**](docs/MediaApi.md#uploadchunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
*MediaApi* | [**uploadMedia**](docs/MediaApi.md#uploadmedia) | **POST** /{workspaceUuid}/media | Upload media (binary)
*PostsApi* | [**addPostToQueue**](docs/PostsApi.md#addposttoqueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
*PostsApi* | [**approvePost**](docs/PostsApi.md#approvepost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
*PostsApi* | [**createPost**](docs/PostsApi.md#createpost) | **POST** /{workspaceUuid}/posts | Create post
*PostsApi* | [**deletePost**](docs/PostsApi.md#deletepost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
*PostsApi* | [**deletePostsBulk**](docs/PostsApi.md#deletepostsbulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
*PostsApi* | [**getPost**](docs/PostsApi.md#getpost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
*PostsApi* | [**listPosts**](docs/PostsApi.md#listposts) | **GET** /{workspaceUuid}/posts | List posts
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
*WorkspacesApi* | [**listWorkspaces**](docs/WorkspacesApi.md#listworkspaces) | **GET** /panel/workspaces | List workspaces
*WorkspacesApi* | [**removeUserFromWorkspace**](docs/WorkspacesApi.md#removeuserfromworkspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
*WorkspacesApi* | [**updateWorkspace**](docs/WorkspacesApi.md#updateworkspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
*WorkspacesApi* | [**updateWorkspaceUser**](docs/WorkspacesApi.md#updateworkspaceuser) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace
