# NodeAttributes

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**title** | **string** |  | [optional] 
**description** | **string** | A more detailed description of the node | [optional] 
**valid_from** | [**\DateTime**](Date.md) | The node is judged invalid before this date. Should be an ISO8601 date | [optional] 
**valid_to** | [**\DateTime**](Date.md) | The node is judged invalid after this date. Should be an ISO8601 date | [optional] 
**student_numbers** | [**Number**](Number.md) |  | [optional] 
**domain_ids** | **string[]** | Additional identifiers linked to the external domain of the hierarchy, for example JACS code. Allows comparisons between hierarchies. | [optional] 
**reminder_date** | [**\DateTime**](Date.md) | Reminder date for redemption period nodes, should be an ISO8601 date. Drop if we can get additionalProperties working. | [optional] 
**deadline** | [**\DateTime**](Date.md) | Deadline date for redemption period nodes, should be an ISO8601 date. Drop if we can get additionalProperties working. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


