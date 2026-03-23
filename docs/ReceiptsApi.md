# ReceiptsApi

All URIs are relative to */app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createReceipt**](ReceiptsApi.md#createReceipt) | **POST** /panel/receipts | Create receipt
[**deleteReceipt**](ReceiptsApi.md#deleteReceipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt
[**deleteReceiptsBulk**](ReceiptsApi.md#deleteReceiptsBulk) | **DELETE** /panel/receipts | Delete receipts (bulk)
[**getReceipt**](ReceiptsApi.md#getReceipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt
[**listReceipts**](ReceiptsApi.md#listReceipts) | **GET** /panel/receipts | List receipts
[**updateReceipt**](ReceiptsApi.md#updateReceipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt



## createReceipt

Create receipt

Creates a billing receipt record for a workspace. Admin only.

### Example

```bash
postboost-cli createReceipt
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **receiptInput** | [**ReceiptInput**](ReceiptInput.md) |  |

### Return type

[**Receipt**](Receipt.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteReceipt

Delete receipt

Permanently deletes a single receipt. Admin only.

### Example

```bash
postboost-cli deleteReceipt receiptUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **receiptUuid** | **string** | UUID of the receipt. | [default to null]

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## deleteReceiptsBulk

Delete receipts (bulk)

Permanently deletes one or more receipt records. Admin only.

### Example

```bash
postboost-cli deleteReceiptsBulk
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **deleteReceiptsBulkRequest** | [**DeleteReceiptsBulkRequest**](DeleteReceiptsBulkRequest.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## getReceipt

Get receipt

Returns a single receipt by UUID. Admin only.

### Example

```bash
postboost-cli getReceipt receiptUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **receiptUuid** | **string** | UUID of the receipt. | [default to null]

### Return type

[**Receipt**](Receipt.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## listReceipts

List receipts

Returns a paginated list of billing receipts. Filter by workspace UUID or invoice number. Admin only.

### Example

```bash
postboost-cli listReceipts  workspace_uuid=value  invoice_number=value  page=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workspaceUuid** | **string** |  | [optional] [default to null]
 **invoiceNumber** | **string** |  | [optional] [default to null]
 **page** | **integer** | Page number (15 items per page). | [optional] [default to 1]

### Return type

[**ListReceipts200Response**](ListReceipts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not Applicable
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## updateReceipt

Update receipt

Updates a receipt's transaction details, amount, or payment date. Admin only.

### Example

```bash
postboost-cli updateReceipt receiptUuid=value
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **receiptUuid** | **string** | UUID of the receipt. | [default to null]
 **receiptUpdateInput** | [**ReceiptUpdateInput**](ReceiptUpdateInput.md) |  |

### Return type

**map**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

