# UsersApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createUser**](UsersApi.md#createUser) | **POST** /panel/users | Create user
[**deleteUser**](UsersApi.md#deleteUser) | **DELETE** /panel/users/{userId} | Delete user
[**deleteUsersBulk**](UsersApi.md#deleteUsersBulk) | **DELETE** /panel/users | Delete users (bulk)
[**getUser**](UsersApi.md#getUser) | **GET** /panel/users/{userId} | Get user
[**listUsers**](UsersApi.md#listUsers) | **GET** /panel/users | List users
[**updateUser**](UsersApi.md#updateUser) | **PUT** /panel/users/{userId} | Update user



## createUser

Create user

Creates a new user account on the platform. Admin only.

### Example

```bash
postboost-cli createUser
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **userInput** | [**UserInput**](UserInput.md) |  |

### Return type

[**User**](User.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteUser

Delete user

Permanently deletes a user account. Returns 400 if you attempt to delete your own account. Admin only.

### Example

```bash
postboost-cli deleteUser userId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **userId** | **integer** | ID of the user. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteUsersBulk

Delete users (bulk)

Permanently deletes one or more user accounts. You cannot delete your own account. Admin only.

### Example

```bash
postboost-cli deleteUsersBulk
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **deleteUsersBulkRequest** | [**DeleteUsersBulkRequest**](DeleteUsersBulkRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getUser

Get user

Returns a single user account by ID. Admin only.

### Example

```bash
postboost-cli getUser userId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **userId** | **integer** | ID of the user. | [default to null]

### Return type

[**User**](User.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listUsers

List users

Returns a paginated list of all users on the platform. Optionally filter by name or email. Admin only.

### Example

```bash
postboost-cli listUsers  keyword=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **keyword** | **string** | Search by name or email. | [optional] [default to null]
 **page** | **integer** | Page number (15 items per page). | [optional] [default to 1]

### Return type

[**ListUsers200Response**](ListUsers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateUser

Update user

Updates a user's name, email, admin status, or password. Admin only.

### Example

```bash
postboost-cli updateUser userId=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **userId** | **integer** | ID of the user. | [default to null]
 **userUpdateInput** | [**UserUpdateInput**](UserUpdateInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

