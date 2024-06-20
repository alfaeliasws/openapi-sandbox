# {{classname}}

All URIs are relative to *https://{environment}.programmerzamannow.com/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**TodolistGet**](TodolistApi.md#TodolistGet) | **Get** /todolist | Get All Todolist
[**TodolistPost**](TodolistApi.md#TodolistPost) | **Post** /todolist | Create new Todolist
[**TodolistTodolistIdDelete**](TodolistApi.md#TodolistTodolistIdDelete) | **Delete** /todolist/{todolistId} | Delete Existing Todolist
[**TodolistTodolistIdPut**](TodolistApi.md#TodolistTodolistIdPut) | **Put** /todolist/{todolistId} | Update Existing Todolist

# **TodolistGet**
> []Todolist TodolistGet(ctx, optional)
Get All Todolist

Return active todolist, completed or deleted todolist will not be shown

### Required Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***TodolistApiTodolistGetOpts** | optional parameters | nil if no parameters

### Optional Parameters
Optional parameters are passed through a pointer to a TodolistApiTodolistGetOpts struct
Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **includeDone** | **optional.Bool**| include done todo list in the result | [default to true]
 **name** | **optional.String**| search todolist by name | 

### Return type

[**[]Todolist**](array.md)

### Authorization

[TodolistAuth](../README.md#TodolistAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **TodolistPost**
> Todolist TodolistPost(ctx, body)
Create new Todolist

Creating new empty todolist

### Required Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
  **body** | [**CreateOrUpdateTodolist**](CreateOrUpdateTodolist.md)|  | 

### Return type

[**Todolist**](Todolist.md)

### Authorization

[TodolistAuth](../README.md#TodolistAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **TodolistTodolistIdDelete**
> InlineResponse200 TodolistTodolistIdDelete(ctx, todolistId)
Delete Existing Todolist

Delete todolist from database

### Required Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
  **todolistId** | **string**| which todolist (by id) that will be updated | 

### Return type

[**InlineResponse200**](inline_response_200.md)

### Authorization

[TodolistAuth](../README.md#TodolistAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **TodolistTodolistIdPut**
> Todolist TodolistTodolistIdPut(ctx, body, todolistId)
Update Existing Todolist

Update todolist that is active or empty

### Required Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
  **body** | [**CreateOrUpdateTodolist**](CreateOrUpdateTodolist.md)|  | 
  **todolistId** | **string**| which todolist (by id) that will be updated | 

### Return type

[**Todolist**](Todolist.md)

### Authorization

[TodolistAuth](../README.md#TodolistAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

