# Swagger\Client\AssetTypeConfigsApi

All URIs are relative to *http://localhost:10010/1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get**](AssetTypeConfigsApi.md#get) | **GET** /{namespace}/assets/{assetType}/templates | 


# **get**
> \Swagger\Client\Model\TemplateBody get($namespace, $asset_type)



get a template for a given asset type

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetTypeConfigsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$asset_type = "asset_type_example"; // string | subtype of Asset, e.g. 'textbooks', 'digitisations', etc.

try { 
    $result = $api_instance->get($namespace, $asset_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AssetTypeConfigsApi->get: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **asset_type** | **string**| subtype of Asset, e.g. &#39;textbooks&#39;, &#39;digitisations&#39;, etc. | 

### Return type

[**\Swagger\Client\Model\TemplateBody**](TemplateBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

