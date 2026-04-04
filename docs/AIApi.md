# AIApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**blogToSocial**](AIApi.md#blogToSocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post



## blogToSocial

Generate social media captions from a blog post

Generates platform-specific social media captions from a blog post URL or
directly provided title and excerpt. Each platform generates one caption,
which consumes one AI credit from the workspace's monthly allowance.

**Input modes** (at least one required):
- **URL mode**: provide 'url' and the API scrapes the blog content automatically, including detecting the featured image via 'og:image'.
- **Direct mode**: provide 'title' and 'excerpt' directly (no scraping).

If both are provided, direct values take priority.

When 'create_post' is 'true', a draft post is created in the workspace with
per-account caption versions. If an image is available (from 'image_url' or
the scraped 'og:image'), it is imported into the workspace media library and
attached to the draft post.

### Example

```bash
postboost-cli blogToSocial workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **blogToSocialInput** | [**BlogToSocialInput**](BlogToSocialInput.md) |  |

### Return type

[**BlogToSocial200Response**](BlogToSocial200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

