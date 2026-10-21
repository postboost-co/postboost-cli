# FreeToolsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**buildAgentSkill**](FreeToolsApi.md#buildAgentSkill) | **POST** /tools/social-media-agent-skill-builder | Build a SKILL.md, AGENTS.md or system prompt for a social media agent
[**buildHashtagGroups**](FreeToolsApi.md#buildHashtagGroups) | **POST** /tools/hashtag-group-builder | Clean, dedupe and split hashtags into groups that fit a network&#39;s hashtag cap
[**buildUtmUrl**](FreeToolsApi.md#buildUtmUrl) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL
[**calculateAspectRatio**](FreeToolsApi.md#calculateAspectRatio) | **POST** /tools/aspect-ratio-calculator | Calculate an aspect ratio, or the missing side of an image at a given ratio
[**calculateCarouselSlices**](FreeToolsApi.md#calculateCarouselSlices) | **POST** /tools/instagram-carousel-splitter | Split a wide image into seamless Instagram carousel slides
[**calculateCrop**](FreeToolsApi.md#calculateCrop) | **POST** /tools/social-media-image-sizes/crop | Calculate the crop box that fits an image to a social media size
[**calculateEngagementRate**](FreeToolsApi.md#calculateEngagementRate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate
[**calculateInfluencerRate**](FreeToolsApi.md#calculateInfluencerRate) | **POST** /tools/influencer-rate-calculator | Estimate an influencer&#39;s rate for one sponsored deliverable
[**calculateSmmPricing**](FreeToolsApi.md#calculateSmmPricing) | **POST** /tools/social-media-manager-pricing-calculator | Estimate social media manager pricing
[**calculateSocialRoi**](FreeToolsApi.md#calculateSocialRoi) | **POST** /tools/social-media-roi-calculator | Calculate social media ROI
[**calculateXApiCost**](FreeToolsApi.md#calculateXApiCost) | **POST** /tools/x-api-cost-calculator | Calculate the monthly X API cost
[**checkLinkPreview**](FreeToolsApi.md#checkLinkPreview) | **POST** /tools/link-preview-checker | Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags)
[**checkPost**](FreeToolsApi.md#checkPost) | **POST** /tools/social-media-post-checker | Check a post against each network&#39;s publishing rules
[**checkReadability**](FreeToolsApi.md#checkReadability) | **POST** /tools/post-readability-checker | Check the readability of a post: Flesch scores, long sentences and passive hints
[**checkYoutubeThumbnail**](FreeToolsApi.md#checkYoutubeThumbnail) | **POST** /tools/youtube-thumbnail-size-checker | Check a YouTube thumbnail&#39;s ratio, width, file size and format against YouTube&#39;s requirements
[**cleanText**](FreeToolsApi.md#cleanText) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown
[**countCharacters**](FreeToolsApi.md#countCharacters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them
[**findAutomationRecipes**](FreeToolsApi.md#findAutomationRecipes) | **GET** /tools/social-media-automation-recipes | Find n8n, Zapier and Make recipes that automate social media posting through the PostBoost API
[**formatCrossPost**](FreeToolsApi.md#formatCrossPost) | **POST** /tools/cross-post-formatter | Format one post for X, Threads, Bluesky, Mastodon and LinkedIn
[**formatInstagramCaption**](FreeToolsApi.md#formatInstagramCaption) | **POST** /tools/instagram-line-break-generator | Keep blank lines in an Instagram caption with spacer lines, and count it
[**formatLinkedInPost**](FreeToolsApi.md#formatLinkedInPost) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists
[**generateAltText**](FreeToolsApi.md#generateAltText) | **POST** /tools/alt-text-generator | Write alt text for an image with AI (needs a token, spends AI credits)
[**generateBio**](FreeToolsApi.md#generateBio) | **POST** /tools/instagram-bio-generator | Write five profile bios with AI (needs a token, spends AI credits)
[**generateCaption**](FreeToolsApi.md#generateCaption) | **POST** /tools/instagram-caption-generator | Write three post captions for a topic with AI (needs a token, spends AI credits)
[**generateFancyText**](FreeToolsApi.md#generateFancyText) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles
[**generateHashtags**](FreeToolsApi.md#generateHashtags) | **POST** /tools/instagram-hashtag-generator | Generate hashtags for a post topic with AI (needs a token, spends AI credits)
[**generateHooks**](FreeToolsApi.md#generateHooks) | **POST** /tools/hook-generator | Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits)
[**generateLinkedInHeadline**](FreeToolsApi.md#generateLinkedInHeadline) | **POST** /tools/linkedin-headline-generator | Write five LinkedIn profile headlines with AI (needs a token, spends AI credits)
[**generateQrCode**](FreeToolsApi.md#generateQrCode) | **POST** /tools/qr-code-generator | Generate a QR code (SVG) for a link or text, with optional UTM tags
[**generateSocialPostsFromBlog**](FreeToolsApi.md#generateSocialPostsFromBlog) | **POST** /tools/blog-to-social-media | Turn a blog post (URL or text) into one social post per network with AI (needs a token, spends AI credits)
[**generateUsernames**](FreeToolsApi.md#generateUsernames) | **POST** /tools/social-media-username-generator | Generate social media usernames
[**generateYoutubeDescription**](FreeToolsApi.md#generateYoutubeDescription) | **POST** /tools/youtube-description-generator | Write three YouTube video descriptions with AI (needs a token, spends AI credits)
[**generateYoutubeTitles**](FreeToolsApi.md#generateYoutubeTitles) | **POST** /tools/youtube-title-generator | Write five YouTube video titles with AI (needs a token, spends AI credits)
[**getBestTimesToPost**](FreeToolsApi.md#getBestTimesToPost) | **GET** /tools/best-time-to-post | Get the best times to post per network from published studies, with sources
[**getGlossary**](FreeToolsApi.md#getGlossary) | **GET** /tools/social-media-glossary | Look up social media terms: plain-language definitions by category, with sources and related terms
[**getHookTemplates**](FreeToolsApi.md#getHookTemplates) | **GET** /tools/hook-generator/library | Get free hook templates for social media posts, filtered by style and network
[**getImageSizes**](FreeToolsApi.md#getImageSizes) | **GET** /tools/social-media-image-sizes | Get social media image sizes per network, each with its source
[**getSafeZones**](FreeToolsApi.md#getSafeZones) | **POST** /tools/safe-zone-checker | Get the TikTok, Instagram Reels or YouTube Shorts safe zones for a vertical frame
[**getVideoSpecs**](FreeToolsApi.md#getVideoSpecs) | **GET** /tools/social-media-video-specs | Get social media video ratios, resolutions, lengths and file size limits per network, with sources
[**listAwarenessDays**](FreeToolsApi.md#listAwarenessDays) | **GET** /tools/social-media-holiday-calendar | List public holidays, awareness days and social media days by date, country, type and topic, with sources
[**listFreeTools**](FreeToolsApi.md#listFreeTools) | **GET** /tools | List the free tools
[**pickGiveawayWinners**](FreeToolsApi.md#pickGiveawayWinners) | **POST** /tools/giveaway-comment-picker | Pick giveaway winners with a draw anyone can verify
[**pickSocialMediaTool**](FreeToolsApi.md#pickSocialMediaTool) | **POST** /tools/social-media-tool-picker | Match your needs against social media management tools and see what each one misses
[**planContentCalendar**](FreeToolsApi.md#planContentCalendar) | **POST** /tools/social-media-content-calendar-generator | Plan a social media content calendar and get it as CSV and ICS
[**planPostingFrequency**](FreeToolsApi.md#planPostingFrequency) | **POST** /tools/posting-frequency-planner | Plan how often to post on each network
[**previewPost**](FreeToolsApi.md#previewPost) | **POST** /tools/social-media-post-preview | Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook
[**scoreSocialAudit**](FreeToolsApi.md#scoreSocialAudit) | **POST** /tools/social-media-audit-template | Score a social media audit checklist and get the top fixes
[**searchEmoji**](FreeToolsApi.md#searchEmoji) | **POST** /tools/social-media-emoji-picker | Search emoji by name or keyword, to copy and paste into a post
[**splitThread**](FreeToolsApi.md#splitThread) | **POST** /tools/x-thread-maker | Split long text into a thread
[**summarizeReport**](FreeToolsApi.md#summarizeReport) | **POST** /tools/social-media-report-generator | Summarize social media post metrics into a report
[**verifyWebhookSignature**](FreeToolsApi.md#verifyWebhookSignature) | **POST** /tools/webhook-signature-verifier | Verify an HMAC webhook signature



## buildAgentSkill

Build a SKILL.md, AGENTS.md or system prompt for a social media agent

Build a SKILL.md, AGENTS.md or system prompt for a social media agent. The same logic as the free web tool at https://postboost.co/tools/social-media-agent-skill-builder. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli buildAgentSkill
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolBuildAgentSkillRequest** | [**FreeToolBuildAgentSkillRequest**](FreeToolBuildAgentSkillRequest.md) |  |

### Return type

[**FreeToolBuildAgentSkillResponse**](FreeToolBuildAgentSkillResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## buildHashtagGroups

Clean, dedupe and split hashtags into groups that fit a network's hashtag cap

Clean, dedupe and split hashtags into groups that fit a network's hashtag cap. The same logic as the free web tool at https://postboost.co/tools/hashtag-group-builder. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli buildHashtagGroups
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolBuildHashtagGroupsRequest** | [**FreeToolBuildHashtagGroupsRequest**](FreeToolBuildHashtagGroupsRequest.md) |  |

### Return type

[**FreeToolBuildHashtagGroupsResponse**](FreeToolBuildHashtagGroupsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## buildUtmUrl

Build a UTM-tagged campaign URL

Build a UTM-tagged campaign URL. The same logic as the free web tool at https://postboost.co/tools/utm-builder. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli buildUtmUrl
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolBuildUtmUrlRequest** | [**FreeToolBuildUtmUrlRequest**](FreeToolBuildUtmUrlRequest.md) |  |

### Return type

[**FreeToolBuildUtmUrlResponse**](FreeToolBuildUtmUrlResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateAspectRatio

Calculate an aspect ratio, or the missing side of an image at a given ratio

Calculate an aspect ratio, or the missing side of an image at a given ratio. The same logic as the free web tool at https://postboost.co/tools/aspect-ratio-calculator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateAspectRatio
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateAspectRatioRequest** | [**FreeToolCalculateAspectRatioRequest**](FreeToolCalculateAspectRatioRequest.md) |  |

### Return type

[**FreeToolCalculateAspectRatioResponse**](FreeToolCalculateAspectRatioResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateCarouselSlices

Split a wide image into seamless Instagram carousel slides

Split a wide image into seamless Instagram carousel slides. The same logic as the free web tool at https://postboost.co/tools/instagram-carousel-splitter. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateCarouselSlices
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateCarouselSlicesRequest** | [**FreeToolCalculateCarouselSlicesRequest**](FreeToolCalculateCarouselSlicesRequest.md) |  |

### Return type

[**FreeToolCalculateCarouselSlicesResponse**](FreeToolCalculateCarouselSlicesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateCrop

Calculate the crop box that fits an image to a social media size

Calculate the crop box that fits an image to a social media size. The same logic as the free web tool at https://postboost.co/tools/social-media-image-sizes. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateCrop
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateCropRequest** | [**FreeToolCalculateCropRequest**](FreeToolCalculateCropRequest.md) |  |

### Return type

[**FreeToolCalculateCropResponse**](FreeToolCalculateCropResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateEngagementRate

Calculate an engagement rate

Calculate an engagement rate. The same logic as the free web tool at https://postboost.co/tools/engagement-rate-calculator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateEngagementRate
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateEngagementRateRequest** | [**FreeToolCalculateEngagementRateRequest**](FreeToolCalculateEngagementRateRequest.md) |  |

### Return type

[**FreeToolCalculateEngagementRateResponse**](FreeToolCalculateEngagementRateResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateInfluencerRate

Estimate an influencer's rate for one sponsored deliverable

Estimate an influencer's rate for one sponsored deliverable. The same logic as the free web tool at https://postboost.co/tools/influencer-rate-calculator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateInfluencerRate
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateInfluencerRateRequest** | [**FreeToolCalculateInfluencerRateRequest**](FreeToolCalculateInfluencerRateRequest.md) |  |

### Return type

[**FreeToolCalculateInfluencerRateResponse**](FreeToolCalculateInfluencerRateResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateSmmPricing

Estimate social media manager pricing

Estimate social media manager pricing. The same logic as the free web tool at https://postboost.co/tools/social-media-manager-pricing-calculator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateSmmPricing
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateSmmPricingRequest** | [**FreeToolCalculateSmmPricingRequest**](FreeToolCalculateSmmPricingRequest.md) |  |

### Return type

[**FreeToolCalculateSmmPricingResponse**](FreeToolCalculateSmmPricingResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateSocialRoi

Calculate social media ROI

Calculate social media ROI. The same logic as the free web tool at https://postboost.co/tools/social-media-roi-calculator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateSocialRoi
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateSocialRoiRequest** | [**FreeToolCalculateSocialRoiRequest**](FreeToolCalculateSocialRoiRequest.md) |  |

### Return type

[**FreeToolCalculateSocialRoiResponse**](FreeToolCalculateSocialRoiResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculateXApiCost

Calculate the monthly X API cost

Calculate the monthly X API cost. The same logic as the free web tool at https://postboost.co/tools/x-api-cost-calculator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli calculateXApiCost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCalculateXApiCostRequest** | [**FreeToolCalculateXApiCostRequest**](FreeToolCalculateXApiCostRequest.md) |  |

### Return type

[**FreeToolCalculateXApiCostResponse**](FreeToolCalculateXApiCostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## checkLinkPreview

Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags)

Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags). The same logic as the free web tool at https://postboost.co/tools/link-preview-checker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli checkLinkPreview
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCheckLinkPreviewRequest** | [**FreeToolCheckLinkPreviewRequest**](FreeToolCheckLinkPreviewRequest.md) |  |

### Return type

[**FreeToolCheckLinkPreviewResponse**](FreeToolCheckLinkPreviewResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## checkPost

Check a post against each network's publishing rules

Check a post against each network's publishing rules. The same logic as the free web tool at https://postboost.co/tools/social-media-post-checker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli checkPost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCheckPostRequest** | [**FreeToolCheckPostRequest**](FreeToolCheckPostRequest.md) |  |

### Return type

[**FreeToolCheckPostResponse**](FreeToolCheckPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## checkReadability

Check the readability of a post: Flesch scores, long sentences and passive hints

Check the readability of a post: Flesch scores, long sentences and passive hints. The same logic as the free web tool at https://postboost.co/tools/post-readability-checker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli checkReadability
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCheckReadabilityRequest** | [**FreeToolCheckReadabilityRequest**](FreeToolCheckReadabilityRequest.md) |  |

### Return type

[**FreeToolCheckReadabilityResponse**](FreeToolCheckReadabilityResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## checkYoutubeThumbnail

Check a YouTube thumbnail's ratio, width, file size and format against YouTube's requirements

Check a YouTube thumbnail's ratio, width, file size and format against YouTube's requirements. The same logic as the free web tool at https://postboost.co/tools/youtube-thumbnail-size-checker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli checkYoutubeThumbnail
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCheckYoutubeThumbnailRequest** | [**FreeToolCheckYoutubeThumbnailRequest**](FreeToolCheckYoutubeThumbnailRequest.md) |  |

### Return type

[**FreeToolCheckYoutubeThumbnailResponse**](FreeToolCheckYoutubeThumbnailResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## cleanText

Clean AI-written text: dashes, quotes, invisible characters, markdown

Clean AI-written text: dashes, quotes, invisible characters, markdown. The same logic as the free web tool at https://postboost.co/tools/ai-text-cleaner. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli cleanText
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCleanTextRequest** | [**FreeToolCleanTextRequest**](FreeToolCleanTextRequest.md) |  |

### Return type

[**FreeToolCleanTextResponse**](FreeToolCleanTextResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## countCharacters

Count characters as each network counts them

Count characters as each network counts them. The same logic as the free web tool at https://postboost.co/tools/social-media-character-counter. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli countCharacters
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolCountCharactersRequest** | [**FreeToolCountCharactersRequest**](FreeToolCountCharactersRequest.md) |  |

### Return type

[**FreeToolCountCharactersResponse**](FreeToolCountCharactersResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## findAutomationRecipes

Find n8n, Zapier and Make recipes that automate social media posting through the PostBoost API

Find n8n, Zapier and Make recipes that automate social media posting through the PostBoost API. The same logic as the free web tool at https://postboost.co/tools/social-media-automation-recipes. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli findAutomationRecipes  platform=value  trigger=value  q=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **platform** | **string** |  | [optional] [default to null]
 **trigger** | **string** |  | [optional] [default to null]
 **q** | **string** |  | [optional] [default to null]

### Return type

[**FreeToolFindAutomationRecipesResponse**](FreeToolFindAutomationRecipesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## formatCrossPost

Format one post for X, Threads, Bluesky, Mastodon and LinkedIn

Format one post for X, Threads, Bluesky, Mastodon and LinkedIn. The same logic as the free web tool at https://postboost.co/tools/cross-post-formatter. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli formatCrossPost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolFormatCrossPostRequest** | [**FreeToolFormatCrossPostRequest**](FreeToolFormatCrossPostRequest.md) |  |

### Return type

[**FreeToolFormatCrossPostResponse**](FreeToolFormatCrossPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## formatInstagramCaption

Keep blank lines in an Instagram caption with spacer lines, and count it

Keep blank lines in an Instagram caption with spacer lines, and count it. The same logic as the free web tool at https://postboost.co/tools/instagram-line-break-generator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli formatInstagramCaption
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolFormatInstagramCaptionRequest** | [**FreeToolFormatInstagramCaptionRequest**](FreeToolFormatInstagramCaptionRequest.md) |  |

### Return type

[**FreeToolFormatInstagramCaptionResponse**](FreeToolFormatInstagramCaptionResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## formatLinkedInPost

Format a LinkedIn post with bold, italic and lists

Format a LinkedIn post with bold, italic and lists. The same logic as the free web tool at https://postboost.co/tools/linkedin-post-formatter. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli formatLinkedInPost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolFormatLinkedInPostRequest** | [**FreeToolFormatLinkedInPostRequest**](FreeToolFormatLinkedInPostRequest.md) |  |

### Return type

[**FreeToolFormatLinkedInPostResponse**](FreeToolFormatLinkedInPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateAltText

Write alt text for an image with AI (needs a token, spends AI credits)

Write alt text for an image with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/alt-text-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateAltText
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateAltTextRequest** | [**FreeToolGenerateAltTextRequest**](FreeToolGenerateAltTextRequest.md) |  |

### Return type

[**FreeToolGenerateAltTextResponse**](FreeToolGenerateAltTextResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json, multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateBio

Write five profile bios with AI (needs a token, spends AI credits)

Write five profile bios with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-bio-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateBio
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateBioRequest** | [**FreeToolGenerateBioRequest**](FreeToolGenerateBioRequest.md) |  |

### Return type

[**FreeToolGenerateBioResponse**](FreeToolGenerateBioResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateCaption

Write three post captions for a topic with AI (needs a token, spends AI credits)

Write three post captions for a topic with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-caption-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateCaption
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateCaptionRequest** | [**FreeToolGenerateCaptionRequest**](FreeToolGenerateCaptionRequest.md) |  |

### Return type

[**FreeToolGenerateCaptionResponse**](FreeToolGenerateCaptionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateFancyText

Convert text to fancy Unicode styles

Convert text to fancy Unicode styles. The same logic as the free web tool at https://postboost.co/tools/fancy-text-generator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli generateFancyText
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateFancyTextRequest** | [**FreeToolGenerateFancyTextRequest**](FreeToolGenerateFancyTextRequest.md) |  |

### Return type

[**FreeToolGenerateFancyTextResponse**](FreeToolGenerateFancyTextResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateHashtags

Generate hashtags for a post topic with AI (needs a token, spends AI credits)

Generate hashtags for a post topic with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-hashtag-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateHashtags
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateHashtagsRequest** | [**FreeToolGenerateHashtagsRequest**](FreeToolGenerateHashtagsRequest.md) |  |

### Return type

[**FreeToolGenerateHashtagsResponse**](FreeToolGenerateHashtagsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateHooks

Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits)

Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/hook-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateHooks
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateHooksRequest** | [**FreeToolGenerateHooksRequest**](FreeToolGenerateHooksRequest.md) |  |

### Return type

[**FreeToolGenerateHooksResponse**](FreeToolGenerateHooksResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateLinkedInHeadline

Write five LinkedIn profile headlines with AI (needs a token, spends AI credits)

Write five LinkedIn profile headlines with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/linkedin-headline-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateLinkedInHeadline
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateLinkedInHeadlineRequest** | [**FreeToolGenerateLinkedInHeadlineRequest**](FreeToolGenerateLinkedInHeadlineRequest.md) |  |

### Return type

[**FreeToolGenerateLinkedInHeadlineResponse**](FreeToolGenerateLinkedInHeadlineResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateQrCode

Generate a QR code (SVG) for a link or text, with optional UTM tags

Generate a QR code (SVG) for a link or text, with optional UTM tags. The same logic as the free web tool at https://postboost.co/tools/qr-code-generator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli generateQrCode
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateQrCodeRequest** | [**FreeToolGenerateQrCodeRequest**](FreeToolGenerateQrCodeRequest.md) |  |

### Return type

[**FreeToolGenerateQrCodeResponse**](FreeToolGenerateQrCodeResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateSocialPostsFromBlog

Turn a blog post (URL or text) into one social post per network with AI (needs a token, spends AI credits)

Turn a blog post (URL or text) into one social post per network with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/blog-to-social-media. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). Each post spends 1 AI credit of the workspace you name (or your active workspace), so a call costs one credit per platform that comes back; results are not cached.

### Example

```bash
postboost-cli generateSocialPostsFromBlog
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateSocialPostsFromBlogRequest** | [**FreeToolGenerateSocialPostsFromBlogRequest**](FreeToolGenerateSocialPostsFromBlogRequest.md) |  |

### Return type

[**FreeToolGenerateSocialPostsFromBlogResponse**](FreeToolGenerateSocialPostsFromBlogResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateUsernames

Generate social media usernames

Generate social media usernames. The same logic as the free web tool at https://postboost.co/tools/social-media-username-generator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli generateUsernames
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateUsernamesRequest** | [**FreeToolGenerateUsernamesRequest**](FreeToolGenerateUsernamesRequest.md) |  |

### Return type

[**FreeToolGenerateUsernamesResponse**](FreeToolGenerateUsernamesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateYoutubeDescription

Write three YouTube video descriptions with AI (needs a token, spends AI credits)

Write three YouTube video descriptions with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/youtube-description-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateYoutubeDescription
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateYoutubeDescriptionRequest** | [**FreeToolGenerateYoutubeDescriptionRequest**](FreeToolGenerateYoutubeDescriptionRequest.md) |  |

### Return type

[**FreeToolGenerateYoutubeDescriptionResponse**](FreeToolGenerateYoutubeDescriptionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generateYoutubeTitles

Write five YouTube video titles with AI (needs a token, spends AI credits)

Write five YouTube video titles with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/youtube-title-generator. Needs an API token (a scoped key needs the 'ai' ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```bash
postboost-cli generateYoutubeTitles
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGenerateYoutubeTitlesRequest** | [**FreeToolGenerateYoutubeTitlesRequest**](FreeToolGenerateYoutubeTitlesRequest.md) |  |

### Return type

[**FreeToolGenerateYoutubeTitlesResponse**](FreeToolGenerateYoutubeTitlesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getBestTimesToPost

Get the best times to post per network from published studies, with sources

Get the best times to post per network from published studies, with sources. The same logic as the free web tool at https://postboost.co/tools/best-time-to-post. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli getBestTimesToPost  network=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **network** | **string** |  | [optional] [default to null]

### Return type

[**FreeToolGetBestTimesToPostResponse**](FreeToolGetBestTimesToPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getGlossary

Look up social media terms: plain-language definitions by category, with sources and related terms

Look up social media terms: plain-language definitions by category, with sources and related terms. The same logic as the free web tool at https://postboost.co/tools/social-media-glossary. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli getGlossary  q=value  category=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **q** | **string** |  | [optional] [default to null]
 **category** | **string** |  | [optional] [default to null]

### Return type

[**FreeToolGetGlossaryResponse**](FreeToolGetGlossaryResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getHookTemplates

Get free hook templates for social media posts, filtered by style and network

Get free hook templates for social media posts, filtered by style and network. The same logic as the free web tool at https://postboost.co/tools/hook-generator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli getHookTemplates  topic=value  category=value  network=value  search=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **topic** | **string** |  | [optional] [default to null]
 **category** | **string** |  | [optional] [default to null]
 **network** | **string** |  | [optional] [default to null]
 **search** | **string** |  | [optional] [default to null]

### Return type

[**FreeToolGetHookTemplatesResponse**](FreeToolGetHookTemplatesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getImageSizes

Get social media image sizes per network, each with its source

Get social media image sizes per network, each with its source. The same logic as the free web tool at https://postboost.co/tools/social-media-image-sizes. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli getImageSizes  network=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **network** | **string** |  | [optional] [default to null]

### Return type

[**FreeToolGetImageSizesResponse**](FreeToolGetImageSizesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getSafeZones

Get the TikTok, Instagram Reels or YouTube Shorts safe zones for a vertical frame

Get the TikTok, Instagram Reels or YouTube Shorts safe zones for a vertical frame. The same logic as the free web tool at https://postboost.co/tools/safe-zone-checker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli getSafeZones
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolGetSafeZonesRequest** | [**FreeToolGetSafeZonesRequest**](FreeToolGetSafeZonesRequest.md) |  |

### Return type

[**FreeToolGetSafeZonesResponse**](FreeToolGetSafeZonesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getVideoSpecs

Get social media video ratios, resolutions, lengths and file size limits per network, with sources

Get social media video ratios, resolutions, lengths and file size limits per network, with sources. The same logic as the free web tool at https://postboost.co/tools/social-media-video-specs. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli getVideoSpecs  network=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **network** | **string** |  | [optional] [default to null]

### Return type

[**FreeToolGetVideoSpecsResponse**](FreeToolGetVideoSpecsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listAwarenessDays

List public holidays, awareness days and social media days by date, country, type and topic, with sources

List public holidays, awareness days and social media days by date, country, type and topic, with sources. The same logic as the free web tool at https://postboost.co/tools/social-media-holiday-calendar. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli listAwarenessDays  from=value  to=value  country=value  type=value  topic=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **from** | **string** |  | [optional] [default to null]
 **to** | **string** |  | [optional] [default to null]
 **country** | **string** |  | [optional] [default to null]
 **type** | **string** |  | [optional] [default to null]
 **topic** | **string** |  | [optional] [default to null]

### Return type

[**FreeToolListAwarenessDaysResponse**](FreeToolListAwarenessDaysResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listFreeTools

List the free tools

Every free tool the API serves, with its operationId and web page. No token needed.

### Example

```bash
postboost-cli listFreeTools
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**FreeToolList**](FreeToolList.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## pickGiveawayWinners

Pick giveaway winners with a draw anyone can verify

Pick giveaway winners with a draw anyone can verify. The same logic as the free web tool at https://postboost.co/tools/giveaway-comment-picker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli pickGiveawayWinners
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolPickGiveawayWinnersRequest** | [**FreeToolPickGiveawayWinnersRequest**](FreeToolPickGiveawayWinnersRequest.md) |  |

### Return type

[**FreeToolPickGiveawayWinnersResponse**](FreeToolPickGiveawayWinnersResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## pickSocialMediaTool

Match your needs against social media management tools and see what each one misses

Match your needs against social media management tools and see what each one misses. The same logic as the free web tool at https://postboost.co/tools/social-media-tool-picker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli pickSocialMediaTool
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolPickSocialMediaToolRequest** | [**FreeToolPickSocialMediaToolRequest**](FreeToolPickSocialMediaToolRequest.md) |  |

### Return type

[**FreeToolPickSocialMediaToolResponse**](FreeToolPickSocialMediaToolResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## planContentCalendar

Plan a social media content calendar and get it as CSV and ICS

Plan a social media content calendar and get it as CSV and ICS. The same logic as the free web tool at https://postboost.co/tools/social-media-content-calendar-generator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli planContentCalendar
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolPlanContentCalendarRequest** | [**FreeToolPlanContentCalendarRequest**](FreeToolPlanContentCalendarRequest.md) |  |

### Return type

[**FreeToolPlanContentCalendarResponse**](FreeToolPlanContentCalendarResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## planPostingFrequency

Plan how often to post on each network

Plan how often to post on each network. The same logic as the free web tool at https://postboost.co/tools/posting-frequency-planner. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli planPostingFrequency
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolPlanPostingFrequencyRequest** | [**FreeToolPlanPostingFrequencyRequest**](FreeToolPlanPostingFrequencyRequest.md) |  |

### Return type

[**FreeToolPlanPostingFrequencyResponse**](FreeToolPlanPostingFrequencyResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## previewPost

Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook

Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook. The same logic as the free web tool at https://postboost.co/tools/social-media-post-preview. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli previewPost
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolPreviewPostRequest** | [**FreeToolPreviewPostRequest**](FreeToolPreviewPostRequest.md) |  |

### Return type

[**FreeToolPreviewPostResponse**](FreeToolPreviewPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## scoreSocialAudit

Score a social media audit checklist and get the top fixes

Score a social media audit checklist and get the top fixes. The same logic as the free web tool at https://postboost.co/tools/social-media-audit-template. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli scoreSocialAudit
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolScoreSocialAuditRequest** | [**FreeToolScoreSocialAuditRequest**](FreeToolScoreSocialAuditRequest.md) |  |

### Return type

[**FreeToolScoreSocialAuditResponse**](FreeToolScoreSocialAuditResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## searchEmoji

Search emoji by name or keyword, to copy and paste into a post

Search emoji by name or keyword, to copy and paste into a post. The same logic as the free web tool at https://postboost.co/tools/social-media-emoji-picker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli searchEmoji
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolSearchEmojiRequest** | [**FreeToolSearchEmojiRequest**](FreeToolSearchEmojiRequest.md) |  |

### Return type

[**FreeToolSearchEmojiResponse**](FreeToolSearchEmojiResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## splitThread

Split long text into a thread

Split long text into a thread. The same logic as the free web tool at https://postboost.co/tools/x-thread-maker. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli splitThread
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolSplitThreadRequest** | [**FreeToolSplitThreadRequest**](FreeToolSplitThreadRequest.md) |  |

### Return type

[**FreeToolSplitThreadResponse**](FreeToolSplitThreadResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## summarizeReport

Summarize social media post metrics into a report

Summarize social media post metrics into a report. The same logic as the free web tool at https://postboost.co/tools/social-media-report-generator. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli summarizeReport
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolSummarizeReportRequest** | [**FreeToolSummarizeReportRequest**](FreeToolSummarizeReportRequest.md) |  |

### Return type

[**FreeToolSummarizeReportResponse**](FreeToolSummarizeReportResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## verifyWebhookSignature

Verify an HMAC webhook signature

Verify an HMAC webhook signature. The same logic as the free web tool at https://postboost.co/tools/webhook-signature-verifier. No account needed: call it without a token, or with any API token.

### Example

```bash
postboost-cli verifyWebhookSignature
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **freeToolVerifyWebhookSignatureRequest** | [**FreeToolVerifyWebhookSignatureRequest**](FreeToolVerifyWebhookSignatureRequest.md) |  |

### Return type

[**FreeToolVerifyWebhookSignatureResponse**](FreeToolVerifyWebhookSignatureResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

