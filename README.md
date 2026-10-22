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
| **Version** | v1.64.2 |

## Quick start

```bash
export POSTBOOST_API_TOKEN="YOUR_API_TOKEN"

# List posts (the token goes in as an Authorization header argument)
./postboost-cli --host https://postboost.co listPosts \
  workspaceUuid="YOUR_WORKSPACE_UUID" \
  "Authorization: Bearer $POSTBOOST_API_TOKEN"

# Show all commands
./postboost-cli --help
```

---

## Documentation for API Endpoints

All URIs are relative to */app/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AIApi* | [**blogToSocial**](docs/AIApi.md#blogtosocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
*AIApi* | [**deleteBrandVoice**](docs/AIApi.md#deletebrandvoice) | **DELETE** /{workspaceUuid}/brand-voice | Delete the brand voice
*AIApi* | [**getAIUsage**](docs/AIApi.md#getaiusage) | **GET** /{workspaceUuid}/usage/ai | AI credit usage
*AIApi* | [**getBrandVoice**](docs/AIApi.md#getbrandvoice) | **GET** /{workspaceUuid}/brand-voice | Get the brand voice
*AIApi* | [**getRepurposeRun**](docs/AIApi.md#getrepurposerun) | **GET** /{workspaceUuid}/ai/repurpose/runs/{runId} | Get a repurpose run
*AIApi* | [**imageAltText**](docs/AIApi.md#imagealttext) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
*AIApi* | [**imageEdit**](docs/AIApi.md#imageedit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
*AIApi* | [**imageGenerate**](docs/AIApi.md#imagegenerate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
*AIApi* | [**imagePrompt**](docs/AIApi.md#imageprompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
*AIApi* | [**imageVariations**](docs/AIApi.md#imagevariations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image
*AIApi* | [**learnBrandVoice**](docs/AIApi.md#learnbrandvoice) | **POST** /{workspaceUuid}/brand-voice/learn | Learn a brand voice from past posts
*AIApi* | [**repurposeContent**](docs/AIApi.md#repurposecontent) | **POST** /{workspaceUuid}/ai/repurpose | Repurpose long-form content into a draft post set with a carousel
*AIApi* | [**updateBrandVoice**](docs/AIApi.md#updatebrandvoice) | **PUT** /{workspaceUuid}/brand-voice | Create or update the brand voice
*AccountGroupsApi* | [**createAccountGroup**](docs/AccountGroupsApi.md#createaccountgroup) | **POST** /{workspaceUuid}/account-groups | Create an account group
*AccountGroupsApi* | [**deleteAccountGroup**](docs/AccountGroupsApi.md#deleteaccountgroup) | **DELETE** /{workspaceUuid}/account-groups/{accountGroupUuid} | Delete an account group
*AccountGroupsApi* | [**getAccountGroup**](docs/AccountGroupsApi.md#getaccountgroup) | **GET** /{workspaceUuid}/account-groups/{accountGroupUuid} | Get an account group
*AccountGroupsApi* | [**listAccountGroups**](docs/AccountGroupsApi.md#listaccountgroups) | **GET** /{workspaceUuid}/account-groups | List account groups
*AccountGroupsApi* | [**updateAccountGroup**](docs/AccountGroupsApi.md#updateaccountgroup) | **PUT** /{workspaceUuid}/account-groups/{accountGroupUuid} | Update an account group
*AccountsApi* | [**connectChannel**](docs/AccountsApi.md#connectchannel) | **POST** /{workspaceUuid}/accounts/connect/{provider} | Connect a Telegram, Discord or Slack channel
*AccountsApi* | [**createConnectLink**](docs/AccountsApi.md#createconnectlink) | **POST** /{workspaceUuid}/accounts/connect-links | Create a connect link
*AccountsApi* | [**createReconnectLink**](docs/AccountsApi.md#createreconnectlink) | **POST** /{workspaceUuid}/accounts/{accountUuid}/reconnect-links | Create a reconnect link
*AccountsApi* | [**getAccount**](docs/AccountsApi.md#getaccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
*AccountsApi* | [**getAccountHealth**](docs/AccountsApi.md#getaccounthealth) | **GET** /{workspaceUuid}/account-health | Account health
*AccountsApi* | [**listAccounts**](docs/AccountsApi.md#listaccounts) | **GET** /{workspaceUuid}/accounts | List accounts
*ActivityApi* | [**listApiActivity**](docs/ActivityApi.md#listapiactivity) | **GET** /{workspaceUuid}/activity | List API activity
*AgentsApi* | [**approveAgentProposal**](docs/AgentsApi.md#approveagentproposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/approve | Approve and apply an agent proposal
*AgentsApi* | [**createAgent**](docs/AgentsApi.md#createagent) | **POST** /{workspaceUuid}/agents | Switch on a background agent
*AgentsApi* | [**deleteAgent**](docs/AgentsApi.md#deleteagent) | **DELETE** /{workspaceUuid}/agents/{agentUuid} | Delete a background agent
*AgentsApi* | [**getAgentRun**](docs/AgentsApi.md#getagentrun) | **GET** /{workspaceUuid}/agent-runs/{runUuid} | Get an agent run with its proposals
*AgentsApi* | [**listAgentProposals**](docs/AgentsApi.md#listagentproposals) | **GET** /{workspaceUuid}/agent-proposals | List agent proposals (approval queue)
*AgentsApi* | [**listAgentRuns**](docs/AgentsApi.md#listagentruns) | **GET** /{workspaceUuid}/agents/{agentUuid}/runs | Run history of an agent
*AgentsApi* | [**listAgents**](docs/AgentsApi.md#listagents) | **GET** /{workspaceUuid}/agents | List background agents
*AgentsApi* | [**rejectAgentProposal**](docs/AgentsApi.md#rejectagentproposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/reject | Reject an agent proposal
*AgentsApi* | [**runAgent**](docs/AgentsApi.md#runagent) | **POST** /{workspaceUuid}/agents/{agentUuid}/run | Run a background agent now
*AgentsApi* | [**updateAgent**](docs/AgentsApi.md#updateagent) | **PUT** /{workspaceUuid}/agents/{agentUuid} | Update a background agent
*AnalyticsApi* | [**createReportExport**](docs/AnalyticsApi.md#createreportexport) | **POST** /{workspaceUuid}/reports/exports | Create a report export
*AnalyticsApi* | [**downloadReportExport**](docs/AnalyticsApi.md#downloadreportexport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid}/download | Download a report file
*AnalyticsApi* | [**getAccountAnalytics**](docs/AnalyticsApi.md#getaccountanalytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
*AnalyticsApi* | [**getAnalyticsSummary**](docs/AnalyticsApi.md#getanalyticssummary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
*AnalyticsApi* | [**getBestPostingTimes**](docs/AnalyticsApi.md#getbestpostingtimes) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
*AnalyticsApi* | [**getPostAnalytics_0**](docs/AnalyticsApi.md#getpostanalytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*AnalyticsApi* | [**getPostingTimes**](docs/AnalyticsApi.md#getpostingtimes) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap
*AnalyticsApi* | [**getReportBranding**](docs/AnalyticsApi.md#getreportbranding) | **GET** /{workspaceUuid}/report-branding | Get the report branding
*AnalyticsApi* | [**getReportExport**](docs/AnalyticsApi.md#getreportexport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid} | Get a report export
*AnalyticsApi* | [**listReportExports**](docs/AnalyticsApi.md#listreportexports) | **GET** /{workspaceUuid}/reports/exports | List report exports
*AnalyticsApi* | [**updateReportBranding**](docs/AnalyticsApi.md#updatereportbranding) | **PUT** /{workspaceUuid}/report-branding | Update the report branding
*AnalyticsApi* | [**uploadReportBrandingLogo**](docs/AnalyticsApi.md#uploadreportbrandinglogo) | **POST** /{workspaceUuid}/report-branding/logo | Upload the report logo
*CompetitorsApi* | [**addCompetitor**](docs/CompetitorsApi.md#addcompetitor) | **POST** /{workspaceUuid}/competitors | Track a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/CompetitorsApi.md#deletecompetitor) | **DELETE** /{workspaceUuid}/competitors/{competitorId} | Stop tracking a competitor
*CompetitorsApi* | [**getCompetitor**](docs/CompetitorsApi.md#getcompetitor) | **GET** /{workspaceUuid}/competitors/{competitorId} | Get a competitor
*CompetitorsApi* | [**listCompetitors**](docs/CompetitorsApi.md#listcompetitors) | **GET** /{workspaceUuid}/competitors | List competitors
*FreeToolsApi* | [**buildAgentSkill**](docs/FreeToolsApi.md#buildagentskill) | **POST** /tools/social-media-agent-skill-builder | Build a SKILL.md, AGENTS.md or system prompt for a social media agent
*FreeToolsApi* | [**buildHashtagGroups**](docs/FreeToolsApi.md#buildhashtaggroups) | **POST** /tools/hashtag-group-builder | Clean, dedupe and split hashtags into groups that fit a network&#39;s hashtag cap
*FreeToolsApi* | [**buildLinkedinCarousel**](docs/FreeToolsApi.md#buildlinkedincarousel) | **POST** /tools/linkedin-carousel-maker | Turn text into LinkedIn carousel (PDF document) slides
*FreeToolsApi* | [**buildUtmUrl**](docs/FreeToolsApi.md#buildutmurl) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL
*FreeToolsApi* | [**calculateAspectRatio**](docs/FreeToolsApi.md#calculateaspectratio) | **POST** /tools/aspect-ratio-calculator | Calculate an aspect ratio, or the missing side of an image at a given ratio
*FreeToolsApi* | [**calculateCarouselSlices**](docs/FreeToolsApi.md#calculatecarouselslices) | **POST** /tools/instagram-carousel-splitter | Split a wide image into seamless Instagram carousel slides
*FreeToolsApi* | [**calculateCrop**](docs/FreeToolsApi.md#calculatecrop) | **POST** /tools/social-media-image-sizes/crop | Calculate the crop box that fits an image to a social media size
*FreeToolsApi* | [**calculateEngagementRate**](docs/FreeToolsApi.md#calculateengagementrate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate
*FreeToolsApi* | [**calculateInfluencerRate**](docs/FreeToolsApi.md#calculateinfluencerrate) | **POST** /tools/influencer-rate-calculator | Estimate an influencer&#39;s rate for one sponsored deliverable
*FreeToolsApi* | [**calculateSmmPricing**](docs/FreeToolsApi.md#calculatesmmpricing) | **POST** /tools/social-media-manager-pricing-calculator | Estimate social media manager pricing
*FreeToolsApi* | [**calculateSocialRoi**](docs/FreeToolsApi.md#calculatesocialroi) | **POST** /tools/social-media-roi-calculator | Calculate social media ROI
*FreeToolsApi* | [**calculateXApiCost**](docs/FreeToolsApi.md#calculatexapicost) | **POST** /tools/x-api-cost-calculator | Calculate the monthly X API cost
*FreeToolsApi* | [**checkLinkPreview**](docs/FreeToolsApi.md#checklinkpreview) | **POST** /tools/link-preview-checker | Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags)
*FreeToolsApi* | [**checkPost**](docs/FreeToolsApi.md#checkpost) | **POST** /tools/social-media-post-checker | Check a post against each network&#39;s publishing rules
*FreeToolsApi* | [**checkReadability**](docs/FreeToolsApi.md#checkreadability) | **POST** /tools/post-readability-checker | Check the readability of a post: Flesch scores, long sentences and passive hints
*FreeToolsApi* | [**checkYoutubeThumbnail**](docs/FreeToolsApi.md#checkyoutubethumbnail) | **POST** /tools/youtube-thumbnail-size-checker | Check a YouTube thumbnail&#39;s ratio, width, file size and format against YouTube&#39;s requirements
*FreeToolsApi* | [**cleanText**](docs/FreeToolsApi.md#cleantext) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown
*FreeToolsApi* | [**countCharacters**](docs/FreeToolsApi.md#countcharacters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them
*FreeToolsApi* | [**findAutomationRecipes**](docs/FreeToolsApi.md#findautomationrecipes) | **GET** /tools/social-media-automation-recipes | Find n8n, Zapier and Make recipes that automate social media posting through the PostBoost API
*FreeToolsApi* | [**formatCrossPost**](docs/FreeToolsApi.md#formatcrosspost) | **POST** /tools/cross-post-formatter | Format one post for X, Threads, Bluesky, Mastodon and LinkedIn
*FreeToolsApi* | [**formatInstagramCaption**](docs/FreeToolsApi.md#formatinstagramcaption) | **POST** /tools/instagram-line-break-generator | Keep blank lines in an Instagram caption with spacer lines, and count it
*FreeToolsApi* | [**formatLinkedInPost**](docs/FreeToolsApi.md#formatlinkedinpost) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists
*FreeToolsApi* | [**generateAltText**](docs/FreeToolsApi.md#generatealttext) | **POST** /tools/alt-text-generator | Write alt text for an image with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateBio**](docs/FreeToolsApi.md#generatebio) | **POST** /tools/instagram-bio-generator | Write five profile bios with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateCaption**](docs/FreeToolsApi.md#generatecaption) | **POST** /tools/instagram-caption-generator | Write three post captions for a topic with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateFancyText**](docs/FreeToolsApi.md#generatefancytext) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles
*FreeToolsApi* | [**generateHashtags**](docs/FreeToolsApi.md#generatehashtags) | **POST** /tools/instagram-hashtag-generator | Generate hashtags for a post topic with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateHooks**](docs/FreeToolsApi.md#generatehooks) | **POST** /tools/hook-generator | Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateLinkedInHeadline**](docs/FreeToolsApi.md#generatelinkedinheadline) | **POST** /tools/linkedin-headline-generator | Write five LinkedIn profile headlines with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateQrCode**](docs/FreeToolsApi.md#generateqrcode) | **POST** /tools/qr-code-generator | Generate a QR code (SVG) for a link or text, with optional UTM tags
*FreeToolsApi* | [**generateSocialPostsFromBlog**](docs/FreeToolsApi.md#generatesocialpostsfromblog) | **POST** /tools/blog-to-social-media | Turn a blog post (URL or text) into one social post per network with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateSocialPostsFromVideo**](docs/FreeToolsApi.md#generatesocialpostsfromvideo) | **POST** /tools/youtube-to-social-posts | Turn a YouTube video&#39;s captions into an X thread and social captions with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateUsernames**](docs/FreeToolsApi.md#generateusernames) | **POST** /tools/social-media-username-generator | Generate social media usernames
*FreeToolsApi* | [**generateYoutubeDescription**](docs/FreeToolsApi.md#generateyoutubedescription) | **POST** /tools/youtube-description-generator | Write three YouTube video descriptions with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**generateYoutubeTitles**](docs/FreeToolsApi.md#generateyoutubetitles) | **POST** /tools/youtube-title-generator | Write five YouTube video titles with AI (needs a token, spends AI credits)
*FreeToolsApi* | [**getBestTimesToPost**](docs/FreeToolsApi.md#getbesttimestopost) | **GET** /tools/best-time-to-post | Get the best times to post per network from published studies, with sources
*FreeToolsApi* | [**getGlossary**](docs/FreeToolsApi.md#getglossary) | **GET** /tools/social-media-glossary | Look up social media terms: plain-language definitions by category, with sources and related terms
*FreeToolsApi* | [**getHookTemplates**](docs/FreeToolsApi.md#gethooktemplates) | **GET** /tools/hook-generator/library | Get free hook templates for social media posts, filtered by style and network
*FreeToolsApi* | [**getImageSizes**](docs/FreeToolsApi.md#getimagesizes) | **GET** /tools/social-media-image-sizes | Get social media image sizes per network, each with its source
*FreeToolsApi* | [**getSafeZones**](docs/FreeToolsApi.md#getsafezones) | **POST** /tools/safe-zone-checker | Get the TikTok, Instagram Reels or YouTube Shorts safe zones for a vertical frame
*FreeToolsApi* | [**getVideoSpecs**](docs/FreeToolsApi.md#getvideospecs) | **GET** /tools/social-media-video-specs | Get social media video ratios, resolutions, lengths and file size limits per network, with sources
*FreeToolsApi* | [**listAwarenessDays**](docs/FreeToolsApi.md#listawarenessdays) | **GET** /tools/social-media-holiday-calendar | List public holidays, awareness days and social media days by date, country, type and topic, with sources
*FreeToolsApi* | [**listFreeTools**](docs/FreeToolsApi.md#listfreetools) | **GET** /tools | List the free tools
*FreeToolsApi* | [**pickGiveawayWinners**](docs/FreeToolsApi.md#pickgiveawaywinners) | **POST** /tools/giveaway-comment-picker | Pick giveaway winners with a draw anyone can verify
*FreeToolsApi* | [**pickSocialMediaTool**](docs/FreeToolsApi.md#picksocialmediatool) | **POST** /tools/social-media-tool-picker | Match your needs against social media management tools and see what each one misses
*FreeToolsApi* | [**planContentCalendar**](docs/FreeToolsApi.md#plancontentcalendar) | **POST** /tools/social-media-content-calendar-generator | Plan a social media content calendar and get it as CSV and ICS
*FreeToolsApi* | [**planPostingFrequency**](docs/FreeToolsApi.md#planpostingfrequency) | **POST** /tools/posting-frequency-planner | Plan how often to post on each network
*FreeToolsApi* | [**previewPost**](docs/FreeToolsApi.md#previewpost) | **POST** /tools/social-media-post-preview | Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook
*FreeToolsApi* | [**scoreSocialAudit**](docs/FreeToolsApi.md#scoresocialaudit) | **POST** /tools/social-media-audit-template | Score a social media audit checklist and get the top fixes
*FreeToolsApi* | [**searchEmoji**](docs/FreeToolsApi.md#searchemoji) | **POST** /tools/social-media-emoji-picker | Search emoji by name or keyword, to copy and paste into a post
*FreeToolsApi* | [**splitThread**](docs/FreeToolsApi.md#splitthread) | **POST** /tools/x-thread-maker | Split long text into a thread
*FreeToolsApi* | [**summarizeReport**](docs/FreeToolsApi.md#summarizereport) | **POST** /tools/social-media-report-generator | Summarize social media post metrics into a report
*FreeToolsApi* | [**verifyWebhookSignature**](docs/FreeToolsApi.md#verifywebhooksignature) | **POST** /tools/webhook-signature-verifier | Verify an HMAC webhook signature
*HashtagGroupsApi* | [**createHashtagGroup**](docs/HashtagGroupsApi.md#createhashtaggroup) | **POST** /{workspaceUuid}/hashtag-groups | Create a hashtag group
*HashtagGroupsApi* | [**deleteHashtagGroup**](docs/HashtagGroupsApi.md#deletehashtaggroup) | **DELETE** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Delete a hashtag group
*HashtagGroupsApi* | [**getHashtagGroup**](docs/HashtagGroupsApi.md#gethashtaggroup) | **GET** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Get a hashtag group
*HashtagGroupsApi* | [**listHashtagGroups**](docs/HashtagGroupsApi.md#listhashtaggroups) | **GET** /{workspaceUuid}/hashtag-groups | List hashtag groups
*HashtagGroupsApi* | [**updateHashtagGroup**](docs/HashtagGroupsApi.md#updatehashtaggroup) | **PUT** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Update a hashtag group
*InboxApi* | [**approveInboxReplyDraft**](docs/InboxApi.md#approveinboxreplydraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/approve | Approve and send a reply draft
*InboxApi* | [**createInboxReplyDraft**](docs/InboxApi.md#createinboxreplydraft) | **POST** /{workspaceUuid}/inbox/conversations/{conversationId}/drafts | Draft a reply
*InboxApi* | [**deleteInboxReplyDraft**](docs/InboxApi.md#deleteinboxreplydraft) | **DELETE** /{workspaceUuid}/inbox/drafts/{draftId} | Withdraw a reply draft
*InboxApi* | [**getInboxConversation**](docs/InboxApi.md#getinboxconversation) | **GET** /{workspaceUuid}/inbox/conversations/{conversationId} | Get an inbox conversation
*InboxApi* | [**getInboxReplyDraft**](docs/InboxApi.md#getinboxreplydraft) | **GET** /{workspaceUuid}/inbox/drafts/{draftId} | Get a reply draft
*InboxApi* | [**listInboxConversations**](docs/InboxApi.md#listinboxconversations) | **GET** /{workspaceUuid}/inbox/conversations | List inbox conversations
*InboxApi* | [**listInboxReplyDrafts**](docs/InboxApi.md#listinboxreplydrafts) | **GET** /{workspaceUuid}/inbox/drafts | List reply drafts
*InboxApi* | [**rejectInboxReplyDraft**](docs/InboxApi.md#rejectinboxreplydraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/reject | Reject a reply draft
*InboxApi* | [**updateInboxConversation**](docs/InboxApi.md#updateinboxconversation) | **PATCH** /{workspaceUuid}/inbox/conversations/{conversationId} | Update an inbox conversation
*InboxApi* | [**updateInboxReplyDraft**](docs/InboxApi.md#updateinboxreplydraft) | **PUT** /{workspaceUuid}/inbox/drafts/{draftId} | Edit a reply draft
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
*MediaApi* | [**uploadMediaBase64**](docs/MediaApi.md#uploadmediabase64) | **POST** /{workspaceUuid}/media/base64 | Upload media (base64 JSON)
*MentionsApi* | [**createMention**](docs/MentionsApi.md#createmention) | **POST** /{workspaceUuid}/mentions | Create mention
*MentionsApi* | [**deleteMention**](docs/MentionsApi.md#deletemention) | **DELETE** /{workspaceUuid}/mentions/{mentionId} | Delete mention
*MentionsApi* | [**getMention**](docs/MentionsApi.md#getmention) | **GET** /{workspaceUuid}/mentions/{mentionId} | Get mention
*MentionsApi* | [**listMentions**](docs/MentionsApi.md#listmentions) | **GET** /{workspaceUuid}/mentions | List mentions
*MentionsApi* | [**updateMention**](docs/MentionsApi.md#updatemention) | **PUT** /{workspaceUuid}/mentions/{mentionId} | Update mention
*PostingScheduleApi* | [**getPostingSchedule**](docs/PostingScheduleApi.md#getpostingschedule) | **GET** /{workspaceUuid}/posting-schedule | Get the posting schedule
*PostingScheduleApi* | [**getRecommendedPostingTimes**](docs/PostingScheduleApi.md#getrecommendedpostingtimes) | **GET** /{workspaceUuid}/posting-schedule/recommended | Get recommended posting times
*PostingScheduleApi* | [**listQueueSlots**](docs/PostingScheduleApi.md#listqueueslots) | **GET** /{workspaceUuid}/queue/slots | List upcoming queue slots
*PostingScheduleApi* | [**resetAccountPostingSchedule**](docs/PostingScheduleApi.md#resetaccountpostingschedule) | **DELETE** /{workspaceUuid}/posting-schedule/{accountId} | Reset an account schedule
*PostingScheduleApi* | [**updatePostingSchedule**](docs/PostingScheduleApi.md#updatepostingschedule) | **PUT** /{workspaceUuid}/posting-schedule | Set the posting schedule
*PostsApi* | [**addPostToQueue**](docs/PostsApi.md#addposttoqueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
*PostsApi* | [**approvePost**](docs/PostsApi.md#approvepost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
*PostsApi* | [**createPost**](docs/PostsApi.md#createpost) | **POST** /{workspaceUuid}/posts | Create post
*PostsApi* | [**createRecyclingRule**](docs/PostsApi.md#createrecyclingrule) | **POST** /{workspaceUuid}/recycling-rules | Create a recycling rule
*PostsApi* | [**createRssFeed**](docs/PostsApi.md#createrssfeed) | **POST** /{workspaceUuid}/rss-feeds | Add an RSS feed
*PostsApi* | [**deletePost**](docs/PostsApi.md#deletepost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
*PostsApi* | [**deletePostsBulk**](docs/PostsApi.md#deletepostsbulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
*PostsApi* | [**deleteRecyclingRule**](docs/PostsApi.md#deleterecyclingrule) | **DELETE** /{workspaceUuid}/recycling-rules/{ruleUuid} | Delete a recycling rule
*PostsApi* | [**deleteRssFeed**](docs/PostsApi.md#deleterssfeed) | **DELETE** /{workspaceUuid}/rss-feeds/{feedUuid} | Delete an RSS feed
*PostsApi* | [**getPost**](docs/PostsApi.md#getpost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
*PostsApi* | [**getPostAnalytics**](docs/PostsApi.md#getpostanalytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*PostsApi* | [**getRecyclingRule**](docs/PostsApi.md#getrecyclingrule) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid} | Get a recycling rule
*PostsApi* | [**getRssFeed**](docs/PostsApi.md#getrssfeed) | **GET** /{workspaceUuid}/rss-feeds/{feedUuid} | Get an RSS feed
*PostsApi* | [**listPosts**](docs/PostsApi.md#listposts) | **GET** /{workspaceUuid}/posts | List posts
*PostsApi* | [**listRecyclingRules**](docs/PostsApi.md#listrecyclingrules) | **GET** /{workspaceUuid}/recycling-rules | List recycling rules
*PostsApi* | [**listRecyclingRuns**](docs/PostsApi.md#listrecyclingruns) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid}/runs | List a recycling rule&#39;s runs
*PostsApi* | [**listRssFeeds**](docs/PostsApi.md#listrssfeeds) | **GET** /{workspaceUuid}/rss-feeds | List RSS feeds
*PostsApi* | [**pollRssFeed**](docs/PostsApi.md#pollrssfeed) | **POST** /{workspaceUuid}/rss-feeds/{feedUuid}/poll | Check an RSS feed now
*PostsApi* | [**recyclePost**](docs/PostsApi.md#recyclepost) | **POST** /{workspaceUuid}/posts/{postUuid}/recycle | Recycle a post on an interval
*PostsApi* | [**retryPostAccount**](docs/PostsApi.md#retrypostaccount) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account
*PostsApi* | [**schedulePost**](docs/PostsApi.md#schedulepost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
*PostsApi* | [**updatePost**](docs/PostsApi.md#updatepost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
*PostsApi* | [**updateRecyclingRule**](docs/PostsApi.md#updaterecyclingrule) | **PUT** /{workspaceUuid}/recycling-rules/{ruleUuid} | Update, pause or resume a recycling rule
*PostsApi* | [**updateRssFeed**](docs/PostsApi.md#updaterssfeed) | **PUT** /{workspaceUuid}/rss-feeds/{feedUuid} | Update, pause or resume an RSS feed
*PostsApi* | [**validatePost**](docs/PostsApi.md#validatepost) | **POST** /{workspaceUuid}/posts/validate | Validate post (dry run)
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
*TemplatesApi* | [**createTemplate**](docs/TemplatesApi.md#createtemplate) | **POST** /{workspaceUuid}/templates | Create a template
*TemplatesApi* | [**deleteTemplate**](docs/TemplatesApi.md#deletetemplate) | **DELETE** /{workspaceUuid}/templates/{templateId} | Delete a template
*TemplatesApi* | [**getTemplate**](docs/TemplatesApi.md#gettemplate) | **GET** /{workspaceUuid}/templates/{templateId} | Get a template
*TemplatesApi* | [**listTemplates**](docs/TemplatesApi.md#listtemplates) | **GET** /{workspaceUuid}/templates | List templates
*TemplatesApi* | [**updateTemplate**](docs/TemplatesApi.md#updatetemplate) | **PUT** /{workspaceUuid}/templates/{templateId} | Update a template
*UsersApi* | [**createUser**](docs/UsersApi.md#createuser) | **POST** /panel/users | Create user
*UsersApi* | [**deleteUser**](docs/UsersApi.md#deleteuser) | **DELETE** /panel/users/{userId} | Delete user
*UsersApi* | [**deleteUsersBulk**](docs/UsersApi.md#deleteusersbulk) | **DELETE** /panel/users | Delete users (bulk)
*UsersApi* | [**getUser**](docs/UsersApi.md#getuser) | **GET** /panel/users/{userId} | Get user
*UsersApi* | [**listUsers**](docs/UsersApi.md#listusers) | **GET** /panel/users | List users
*UsersApi* | [**updateUser**](docs/UsersApi.md#updateuser) | **PUT** /panel/users/{userId} | Update user
*WebhooksApi* | [**createWebhookSubscription**](docs/WebhooksApi.md#createwebhooksubscription) | **POST** /{workspaceUuid}/webhooks/subscriptions | Subscribe a webhook
*WebhooksApi* | [**deleteWebhookSubscription**](docs/WebhooksApi.md#deletewebhooksubscription) | **DELETE** /{workspaceUuid}/webhooks/subscriptions/{subscriptionUuid} | Unsubscribe a webhook
*WebhooksApi* | [**listWebhookSubscriptions**](docs/WebhooksApi.md#listwebhooksubscriptions) | **GET** /{workspaceUuid}/webhooks/subscriptions | List webhook subscriptions
*WorkspacesApi* | [**addUserToWorkspace**](docs/WorkspacesApi.md#addusertoworkspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
*WorkspacesApi* | [**createApiKey**](docs/WorkspacesApi.md#createapikey) | **POST** /{workspaceUuid}/api-keys | Create a scoped API key
*WorkspacesApi* | [**createResellerClient**](docs/WorkspacesApi.md#createresellerclient) | **POST** /{workspaceUuid}/clients | Create a client workspace
*WorkspacesApi* | [**createWorkspace**](docs/WorkspacesApi.md#createworkspace) | **POST** /panel/workspaces | Create workspace
*WorkspacesApi* | [**deleteApiKey**](docs/WorkspacesApi.md#deleteapikey) | **DELETE** /{workspaceUuid}/api-keys/{apiKeyId} | Revoke a scoped API key
*WorkspacesApi* | [**deleteWorkspace**](docs/WorkspacesApi.md#deleteworkspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
*WorkspacesApi* | [**deleteWorkspacesBulk**](docs/WorkspacesApi.md#deleteworkspacesbulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
*WorkspacesApi* | [**getWorkspace**](docs/WorkspacesApi.md#getworkspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
*WorkspacesApi* | [**getWorkspaceAICredits**](docs/WorkspacesApi.md#getworkspaceaicredits) | **GET** /panel/workspaces/{workspaceUuid}/ai-credits | Get workspace AI credits
*WorkspacesApi* | [**getXUsage**](docs/WorkspacesApi.md#getxusage) | **GET** /{workspaceUuid}/usage/x | X (Twitter) usage
*WorkspacesApi* | [**listApiKeys**](docs/WorkspacesApi.md#listapikeys) | **GET** /{workspaceUuid}/api-keys | List scoped API keys
*WorkspacesApi* | [**listMyWorkspaces**](docs/WorkspacesApi.md#listmyworkspaces) | **GET** /workspaces | List my workspaces
*WorkspacesApi* | [**listResellerClients**](docs/WorkspacesApi.md#listresellerclients) | **GET** /{workspaceUuid}/clients | List client workspaces
*WorkspacesApi* | [**listWorkspaces**](docs/WorkspacesApi.md#listworkspaces) | **GET** /panel/workspaces | List workspaces
*WorkspacesApi* | [**removeUserFromWorkspace**](docs/WorkspacesApi.md#removeuserfromworkspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
*WorkspacesApi* | [**updateWorkspace**](docs/WorkspacesApi.md#updateworkspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
*WorkspacesApi* | [**updateWorkspaceUser**](docs/WorkspacesApi.md#updateworkspaceuser) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace

---

## Links

- Docs and quick start: https://postboost.co/docs/quickstart
- API reference: https://postboost.co/docs/api
- MCP server for AI agents: https://postboost.co/docs/mcp
- All PostBoost open-source projects: https://github.com/postboost-co
- Awesome PostBoost: https://github.com/postboost-co/awesome-postboost

## Authentication

Create an API token in PostBoost under **Settings → Access Tokens** and pass it as a Bearer token. Never commit tokens; read them from an environment variable such as `POSTBOOST_API_TOKEN`.

## Contributing

This Bash CLI is generated from the [PostBoost OpenAPI spec](https://postboost.co/docs/api). Bugs and feature requests: open an issue in [postboost-cli](https://github.com/postboost-co/postboost-cli/issues). Generated code is overwritten on every release, so fixes usually land in the spec or the generator templates; see [CONTRIBUTING.md](CONTRIBUTING.md).

Security issues: see [SECURITY.md](SECURITY.md). Questions: hi@postboost.co.

## License

MIT, see [LICENSE](LICENSE).

---

## Links

- Docs and quick start: https://postboost.co/docs/quickstart
- API reference: https://postboost.co/docs/api
- MCP server for AI agents: https://postboost.co/docs/mcp
- All PostBoost open-source projects: https://github.com/postboost-co
- Awesome PostBoost: https://github.com/postboost-co/awesome-postboost

## Authentication

Create an API token in PostBoost under **Settings → Access Tokens** and pass it as a Bearer token. Never commit tokens; read them from an environment variable such as `POSTBOOST_API_TOKEN`.

## Contributing

This Bash CLI is generated from the [PostBoost OpenAPI spec](https://postboost.co/docs/api). Bugs and feature requests: open an issue in [postboost-cli](https://github.com/postboost-co/postboost-cli/issues). Generated code is overwritten on every release, so fixes usually land in the spec or the generator templates; see [CONTRIBUTING.md](CONTRIBUTING.md).

Security issues: see [SECURITY.md](SECURITY.md). Questions: hi@postboost.co.

## License

MIT, see [LICENSE](LICENSE).
