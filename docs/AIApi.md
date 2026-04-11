# AIApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**blogToSocial**](AIApi.md#blogToSocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
[**imageAltText**](AIApi.md#imageAltText) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
[**imageEdit**](AIApi.md#imageEdit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
[**imageGenerate**](AIApi.md#imageGenerate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
[**imagePrompt**](AIApi.md#imagePrompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
[**imageVariations**](AIApi.md#imageVariations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image



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


## imageAltText

Generate alt text for a media image using AI

Analyzes an existing workspace media item and generates accessible alt text.
The alt text is saved back to the media record.
Costs 1 AI credit per call.

### Example

```bash
postboost-cli imageAltText workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **imageAltTextInput** | [**ImageAltTextInput**](ImageAltTextInput.md) |  |

### Return type

[**ImageAltText200Response**](ImageAltText200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## imageEdit

Edit an existing media image using AI

Edits an existing workspace media item using the source image and a text
prompt. Optionally accepts a mask (transparent areas are replaced).
Saves results to the media library. Credits: 'count × credit_weight'.

### Example

```bash
postboost-cli imageEdit workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **imageEditInput** | [**ImageEditInput**](ImageEditInput.md) |  |

### Return type

[**ImageGenerate200Response**](ImageGenerate200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## imageGenerate

Generate social media images from a caption

Generates one or more images and saves them immediately to the workspace
media library.

**Standard mode** (recommended): provide 'caption' + 'platform'. PostBoost
builds a professional image prompt internally using platform-specific
templates. No prompt engineering required.

**Developer mode**: provide 'prompt' directly to bypass prompt building.
If both 'caption' and 'prompt' are sent, standard mode runs.

Credits: 'count x credit_weight' (default: 5 per image).

### Example

```bash
postboost-cli imageGenerate workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **imageGenerateInput** | [**ImageGenerateInput**](ImageGenerateInput.md) |  |

### Return type

[**ImageGenerate200Response**](ImageGenerate200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## imagePrompt

Build an optimized image prompt from a social media caption

Builds a professional image generation prompt from a caption and platform.
No image is generated. Use this to preview the prompt before calling
'image-generate'. Costs 1 AI credit per call.

When 'image-generate' builds the prompt internally (standard mode),
no credit is charged for the prompt step.

### Example

```bash
postboost-cli imagePrompt workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **imagePromptInput** | [**ImagePromptInput**](ImagePromptInput.md) |  |

### Return type

[**ImagePrompt200Response**](ImagePrompt200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## imageVariations

Generate variations of an existing media image

Creates one or more variations of an existing workspace media item.
Saves results to the media library.
Credits: 'count × credit_weight'.

### Example

```bash
postboost-cli imageVariations workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **imageVariationsInput** | [**ImageVariationsInput**](ImageVariationsInput.md) |  |

### Return type

[**ImageVariations200Response**](ImageVariations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

