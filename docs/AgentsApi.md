# AgentsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**approveAgentProposal**](AgentsApi.md#approveAgentProposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/approve | Approve and apply an agent proposal
[**createAgent**](AgentsApi.md#createAgent) | **POST** /{workspaceUuid}/agents | Switch on a background agent
[**deleteAgent**](AgentsApi.md#deleteAgent) | **DELETE** /{workspaceUuid}/agents/{agentUuid} | Delete a background agent
[**getAgentRun**](AgentsApi.md#getAgentRun) | **GET** /{workspaceUuid}/agent-runs/{runUuid} | Get an agent run with its proposals
[**listAgentProposals**](AgentsApi.md#listAgentProposals) | **GET** /{workspaceUuid}/agent-proposals | List agent proposals (approval queue)
[**listAgentRuns**](AgentsApi.md#listAgentRuns) | **GET** /{workspaceUuid}/agents/{agentUuid}/runs | Run history of an agent
[**listAgents**](AgentsApi.md#listAgents) | **GET** /{workspaceUuid}/agents | List background agents
[**rejectAgentProposal**](AgentsApi.md#rejectAgentProposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/reject | Reject an agent proposal
[**runAgent**](AgentsApi.md#runAgent) | **POST** /{workspaceUuid}/agents/{agentUuid}/run | Run a background agent now
[**updateAgent**](AgentsApi.md#updateAgent) | **PUT** /{workspaceUuid}/agents/{agentUuid} | Update a background agent



## approveAgentProposal

Approve and apply an agent proposal

Applies the proposal at once: 'hold_post' moves the post back to draft, 'edit_caption'
replaces the caption, 'retry_account' saves the shortened caption (if any) on that account's
version and publishes that account again, 'reconnect_account' only records the decision.
When the post was edited, deleted or left the schedule since the proposal was made (for
'retry_account': the account is no longer failed, the post is publishing, or the plan does
not allow scheduling), nothing changes and the proposal becomes 'stale'. Admins and members
only.

### Example

```bash
postboost-cli approveAgentProposal workspaceUuid=value proposalUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **proposalUuid** | **string** |  | [default to null]
 **agentProposalDecision** | [**AgentProposalDecision**](AgentProposalDecision.md) |  | [optional]

### Return type

[**ApproveAgentProposal200Response**](ApproveAgentProposal200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## createAgent

Switch on a background agent

Creates an agent (one per type per workspace). It first runs within five minutes, then on its
'schedule'. **Pre-publish checker** looks at posts scheduled in the next 'horizon_hours' and
proposes holding (back to draft) posts that would fail: disconnected accounts, network
requirements, daily caps, the X allowance and links that answer an error. It proposes caption
edits that drop 'banned_phrases'. With 'ai_review: true' it also asks AI to review up to
'max_ai_reviews_per_run' posts per run (one AI credit each). **Failed-post fixer** looks at
posts that failed on an account in the last 'lookback_hours' and proposes, per post and
account, 'reconnect_account' (the account's token expired), or 'retry_account', with a
caption trimmed to the network limit when the text is over it. One open proposal per post
and account. It uses no AI. Admins and members only.

### Example

```bash
postboost-cli createAgent workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **workspaceAgentInput** | [**WorkspaceAgentInput**](WorkspaceAgentInput.md) |  |

### Return type

[**CreateAgent201Response**](CreateAgent201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteAgent

Delete a background agent

Removes the agent. Its run history and proposals stay. Admins and members only.

### Example

```bash
postboost-cli deleteAgent workspaceUuid=value agentUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **agentUuid** | **string** |  | [default to null]

### Return type

[**DeleteAgent200Response**](DeleteAgent200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getAgentRun

Get an agent run with its proposals

### Example

```bash
postboost-cli getAgentRun workspaceUuid=value runUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **runUuid** | **string** |  | [default to null]

### Return type

[**RunAgent202Response**](RunAgent202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listAgentProposals

List agent proposals (approval queue)

Proposals of all agents in the workspace, newest first. Defaults to 'pending'.

### Example

```bash
postboost-cli listAgentProposals workspaceUuid=value  status=value  per_page=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **status** | **string** |  | [optional] [default to pending]
 **perPage** | **integer** |  | [optional] [default to 20]
 **page** | **integer** |  | [optional] [default to null]

### Return type

[**ListAgentProposals200Response**](ListAgentProposals200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listAgentRuns

Run history of an agent

Runs of the agent, newest first, with what each checked and proposed and the AI credits it used.

### Example

```bash
postboost-cli listAgentRuns workspaceUuid=value agentUuid=value  per_page=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **agentUuid** | **string** |  | [default to null]
 **perPage** | **integer** |  | [optional] [default to 20]
 **page** | **integer** |  | [optional] [default to null]

### Return type

[**ListAgentRuns200Response**](ListAgentRuns200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listAgents

List background agents

Background agents switched on for the workspace. Agents run on a schedule, record every run
and never change a post themselves: each change is a proposal that a workspace admin or
member approves. Available types: 'pre_publish_checker', 'failed_post_fixer'.

### Example

```bash
postboost-cli listAgents workspaceUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]

### Return type

[**ListAgents200Response**](ListAgents200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## rejectAgentProposal

Reject an agent proposal

Records the rejection (and optional note); nothing changes on the post. Admins and members only.

### Example

```bash
postboost-cli rejectAgentProposal workspaceUuid=value proposalUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **proposalUuid** | **string** |  | [default to null]
 **agentProposalDecision** | [**AgentProposalDecision**](AgentProposalDecision.md) |  | [optional]

### Return type

[**ApproveAgentProposal200Response**](ApproveAgentProposal200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## runAgent

Run a background agent now

Queues a run outside the schedule ('trigger: manual'). Six per hour. Admins and members only.

### Example

```bash
postboost-cli runAgent workspaceUuid=value agentUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **agentUuid** | **string** |  | [default to null]

### Return type

[**RunAgent202Response**](RunAgent202Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateAgent

Update a background agent

Changes the name, schedule, settings or 'enabled'. Settings you leave out keep their value. Admins and members only.

### Example

```bash
postboost-cli updateAgent workspaceUuid=value agentUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** | UUID of the workspace. | [default to null]
 **agentUuid** | **string** |  | [default to null]
 **workspaceAgentUpdate** | [**WorkspaceAgentUpdate**](WorkspaceAgentUpdate.md) |  |

### Return type

[**CreateAgent201Response**](CreateAgent201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

