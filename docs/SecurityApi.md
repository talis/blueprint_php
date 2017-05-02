# Swagger\Client\SecurityApi

All URIs are relative to *http://localhost:10010/1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getPublicCertificate**](SecurityApi.md#getPublicCertificate) | **GET** /keys/public | 


# **getPublicCertificate**
> getPublicCertificate()



Return public key that is used to verify signed data

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\SecurityApi();

try { 
    $api_instance->getPublicCertificate();
} catch (Exception $e) {
    echo 'Exception when calling SecurityApi->getPublicCertificate: ', $e->getMessage(), "\n";
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: text/plain

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

