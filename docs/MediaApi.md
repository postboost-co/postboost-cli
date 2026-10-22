# MediaApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**abortChunkedUpload**](MediaApi.md#abortChunkedUpload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
[**completeChunkedUpload**](MediaApi.md#completeChunkedUpload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
[**createMediaFolder**](MediaApi.md#createMediaFolder) | **POST** /{workspaceUuid}/media/folders | Create media folder
[**deleteMediaBulk**](MediaApi.md#deleteMediaBulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
[**deleteMediaFolder**](MediaApi.md#deleteMediaFolder) | **DELETE** /{workspaceUuid}/media/folders/{folderUuid} | Delete media folder
[**getMedia**](MediaApi.md#getMedia) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
[**getRemoteUploadStatus**](MediaApi.md#getRemoteUploadStatus) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
[**initiateChunkedUpload**](MediaApi.md#initiateChunkedUpload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
[**initiateRemoteUpload**](MediaApi.md#initiateRemoteUpload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
[**listMedia**](MediaApi.md#listMedia) | **GET** /{workspaceUuid}/media | List media
[**listMediaFolders**](MediaApi.md#listMediaFolders) | **GET** /{workspaceUuid}/media/folders | List media folders
[**updateMedia**](MediaApi.md#updateMedia) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
[**updateMediaFolder**](MediaApi.md#updateMediaFolder) | **PUT** /{workspaceUuid}/media/folders/{folderUuid} | Update media folder
[**uploadChunk**](MediaApi.md#uploadChunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
[**uploadMedia**](MediaApi.md#uploadMedia) | **POST** /{workspaceUuid}/media | Upload media (binary)
[**uploadMediaBase64**](MediaApi.md#uploadMediaBase64) | **POST** /{workspaceUuid}/media/base64 | Upload media (base64 JSON)



## abortChunkedUpload

Abort chunked upload

Cancel an in-progress chunked upload session and clean up uploaded chunks.

### Example

```bash
postboost-cli abortChunkedUpload workspaceUuid=value uploadUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **uploadUuid** | **string** |  | [default to null]

### Return type

(empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## completeChunkedUpload

Complete chunked upload

Signal that all chunks have been uploaded. Returns the final media object. A video may come back with 'is_processing' set to 'true' while its conversion runs.

### Example

```bash
postboost-cli completeChunkedUpload workspaceUuid=value uploadUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **uploadUuid** | **string** |  | [default to null]
 **completeChunkedUploadRequest** | [**CompleteChunkedUploadRequest**](CompleteChunkedUploadRequest.md) |  | [optional]

### Return type

[**Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createMediaFolder

Create media folder

Creates a folder at the top level or under 'parent'. The name must be unique among its siblings.

### Example

```bash
postboost-cli createMediaFolder workspaceUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **createMediaFolderRequest** | [**CreateMediaFolderRequest**](CreateMediaFolderRequest.md) |  |
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

### Return type

[**MediaFolder**](MediaFolder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteMediaBulk

Delete media (bulk)

Delete one or more media items by their numeric IDs or UUIDs (both may be mixed, up to 500 per request). Deleting a media item also removes it from every post that uses it, including scheduled posts; those posts publish without it (or fail where the network requires media).

### Example

```bash
postboost-cli deleteMediaBulk workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **deleteMediaBulkRequest** | [**DeleteMediaBulkRequest**](DeleteMediaBulkRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteMediaFolder

Delete media folder

Deletes a folder. By default its media and sub-folders move up to the folder's parent; with 'delete_media' set to true every media item below the folder is deleted as well. Deleting a media item also removes it from every post that uses it, including scheduled posts; those posts publish without it (or fail where the network requires media).

### Example

```bash
postboost-cli deleteMediaFolder workspaceUuid=value folderUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **folderUuid** | **string** | UUID of the media folder. | [default to null]
 **deleteMediaFolderRequest** | [**DeleteMediaFolderRequest**](DeleteMediaFolderRequest.md) |  | [optional]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getMedia

Get media

Returns a single media asset.

### Example

```bash
postboost-cli getMedia workspaceUuid=value mediaUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **mediaUuid** | **string** | UUID of the media asset. | [default to null]

### Return type

[**Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getRemoteUploadStatus

Get remote upload status

Poll a background download started by 'initiateRemoteUpload' until 'status' is 'completed' or 'failed'.
'status' moves from 'pending' to 'downloading' and 'processing', and ends as 'completed' (with 'media')
or 'failed' (with 'error'). The final result is returned once: after a 'completed' or 'failed' response the download id is
forgotten and later polls return '404', as do ids older than one hour.

### Example

```bash
postboost-cli getRemoteUploadStatus workspaceUuid=value downloadId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **downloadId** | **string** |  | [default to null]

### Return type

[**GetRemoteUploadStatus200Response**](GetRemoteUploadStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## initiateChunkedUpload

Initiate chunked upload

Start a chunked upload session for large files. Returns an 'upload_uuid',
'chunk_size', and 'total_chunks' to use for subsequent chunk requests.

### Example

```bash
postboost-cli initiateChunkedUpload workspaceUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **initiateChunkedUploadRequest** | [**InitiateChunkedUploadRequest**](InitiateChunkedUploadRequest.md) |  |
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

### Return type

[**InitiateChunkedUpload201Response**](InitiateChunkedUpload201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## initiateRemoteUpload

Initiate remote upload

Download a file from a remote URL into the media library.
A file under 10 MB (or one whose server does not send its size) is downloaded during the request:
the response has 'status: completed' and the 'media' object, or 'status: failed' and an 'error'.
A larger file downloads in the background: the response has 'status: pending' and a 'download_id';
poll 'getRemoteUploadStatus' with it until 'status' is 'completed' or 'failed'.

### Example

```bash
postboost-cli initiateRemoteUpload workspaceUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **initiateRemoteUploadRequest** | [**InitiateRemoteUploadRequest**](InitiateRemoteUploadRequest.md) |  |
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

### Return type

[**InitiateRemoteUpload200Response**](InitiateRemoteUpload200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listMedia

List media

Returns a paginated list of media assets in the workspace library. Without 'folder'
every item is listed, whatever folder it is filed in. A 'keyword' search always looks at
the whole library and ignores 'folder' and 'favorite'.

### Example

```bash
postboost-cli listMedia workspaceUuid=value  page=value  limit=value  folder=value  Specify as:  mime_types[]=value1 mime_types[]=value2 mime_types[]=...  type=value  keyword=value  usage=value  favorite=value  sort=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **page** | **integer** | Page number. | [optional] [default to 1]
 **limit** | **integer** | Items per page. Values below 1 fall back to 50; values above 100 are capped at 100. | [optional] [default to 50]
 **folder** | **string** | Media folder UUID, or 'root' for items not filed in any folder. | [optional] [default to null]
 **mimeTypesLeft_Square_BracketRight_Square_Bracket** | [**array[string]**](string.md) | Only these MIME types (for example 'image/png'). | [optional] [default to null]
 **type** | **string** | Only this media type. | [optional] [default to null]
 **keyword** | **string** | Search media by name. | [optional] [default to null]
 **usage** | **string** | Filter by how the media is used in posts. | [optional] [default to null]
 **favorite** | **boolean** | When 'true', only media the caller marked as favorite. | [optional] [default to null]
 **sort** | **string** |  | [optional] [default to newest]

### Return type

[**ListMedia200Response**](ListMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listMediaFolders

List media folders

Returns the whole folder tree of the media library in one response (not paginated). Rebuild the tree from each folder's 'parent'.

### Example

```bash
postboost-cli listMediaFolders workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListMediaFolders200Response**](ListMediaFolders200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateMedia

Update media

Update the name, alt text, or folder of a media asset. Only the keys present in the body
are written. Sending 'folder: null' moves the item to the library root; omitting 'folder'
leaves it where it is.

### Example

```bash
postboost-cli updateMedia workspaceUuid=value mediaUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **mediaUuid** | **string** | UUID of the media asset. | [default to null]
 **updateMediaRequest** | [**UpdateMediaRequest**](UpdateMediaRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateMediaFolder

Update media folder

Renames a folder and/or moves it. Sending 'parent' moves the folder (null = top level); omitting it keeps the current parent. A folder cannot be moved into itself or one of its descendants.

### Example

```bash
postboost-cli updateMediaFolder workspaceUuid=value folderUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **folderUuid** | **string** | UUID of the media folder. | [default to null]
 **mediaFolderInput** | [**MediaFolderInput**](MediaFolderInput.md) |  |

### Return type

[**MediaFolder**](MediaFolder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## uploadChunk

Upload a chunk

Upload a single chunk of a chunked upload session.

### Example

```bash
postboost-cli uploadChunk workspaceUuid=value uploadUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **uploadUuid** | **string** |  | [default to null]
 **chunk** | **binary** |  | [default to null]
 **chunkIndex** | **integer** | Zero-based index of this chunk. | [default to null]

### Return type

[**UploadChunk201Response**](UploadChunk201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## uploadMedia

Upload media (binary)

Upload a file directly as multipart form data. Images and videos, plus a PDF (up to 100 MB)
for LinkedIn document posts: a post that attaches a PDF must have it as the only media item
and may only go to LinkedIn profiles and pages.

### Example

```bash
postboost-cli uploadMedia workspaceUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **file** | **binary** | The file to upload. | [default to null]
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]
 **altText** | **string** | Alternative text for accessibility. | [optional] [default to null]
 **folder** | **string** | UUID of the media folder to file the upload in. Omit or null for the library root. | [optional] [default to null]

### Return type

[**Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## uploadMediaBase64

Upload media (base64 JSON)

Upload a file as base64 inside a JSON body, for agents and tools that cannot send multipart
form data. The decoded file is checked exactly like 'POST media' (allowed types and size
limits; a PDF is accepted for LinkedIn document posts). Decoded size is capped at 20 MB; for
larger files use remote upload by URL or chunked upload.

### Example

```bash
postboost-cli uploadMediaBase64 workspaceUuid=value Idempotency-Key:value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **mediaBase64Input** | [**MediaBase64Input**](MediaBase64Input.md) |  |
 **idempotencyKey** | **string** | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and
body within 24 hours returns the stored response with 'Idempotent-Replayed: true' and has no further
effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] [default to null]

### Return type

[**Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

