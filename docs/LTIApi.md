# Swagger\Client\LTIApi

All URIs are relative to *http://localhost:10010/1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**namespaceIntegrationsLti1IntegrationIdAssetsAssetTypeAssetIdPost**](LTIApi.md#namespaceIntegrationsLti1IntegrationIdAssetsAssetTypeAssetIdPost) | **POST** /{namespace}/integrations/lti1/{integrationId}/assets/{assetType}/{assetId} | 


# **namespaceIntegrationsLti1IntegrationIdAssetsAssetTypeAssetIdPost**
> namespaceIntegrationsLti1IntegrationIdAssetsAssetTypeAssetIdPost($namespace, $integration_id, $asset_type, $asset_id, $lti_message_type, $lti_version, $resource_link_id, $oauth_consumer_key, $oauth_consumer_key2, $oauth_signature_method, $oauth_signature_method2, $oauth_timestamp, $oauth_timestamp2, $oauth_version, $oauth_version2, $oauth_nonce, $oauth_nonce2, $oauth_signature, $oauth_signature2)



LTI launch url for integration

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\LTIApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$integration_id = "integration_id_example"; // string | id of an integration
$asset_type = "asset_type_example"; // string | subtype of Asset, e.g. 'textbooks', 'digitisations', etc.
$asset_id = "asset_id_example"; // string | id of an asset
$lti_message_type = "lti_message_type_example"; // string | LTI launch data message type, must be 'basic-lti-launch-request'
$lti_version = "lti_version_example"; // string | LTI launch version, must be 'LTI-1p0'
$resource_link_id = "resource_link_id_example"; // string | LTI resource_link_id parameters
$oauth_consumer_key = "oauth_consumer_key_example"; // string | OAuth 1.0 consumer_key parameters
$oauth_consumer_key2 = "oauth_consumer_key_example"; // string | OAuth 1.0 consumer_key parameters
$oauth_signature_method = "oauth_signature_method_example"; // string | OAuth 1.0 signature method, must be 'HMAC-SHA1'
$oauth_signature_method2 = "oauth_signature_method_example"; // string | OAuth 1.0 signature method, must be 'HMAC-SHA1'
$oauth_timestamp = 56; // int | OAuth 1.0 timestamp of request
$oauth_timestamp2 = 56; // int | OAuth 1.0 timestamp of request
$oauth_version = new Number(); // Number | OAuth 1.0 version, must be '1.0'
$oauth_version2 = new Number(); // Number | OAuth 1.0 version, must be '1.0'
$oauth_nonce = "oauth_nonce_example"; // string | OAuth 1.0 Nonce
$oauth_nonce2 = "oauth_nonce_example"; // string | OAuth 1.0 Nonce
$oauth_signature = "oauth_signature_example"; // string | OAuth 1.0 request signature
$oauth_signature2 = "oauth_signature_example"; // string | OAuth 1.0 request signature

try { 
    $api_instance->namespaceIntegrationsLti1IntegrationIdAssetsAssetTypeAssetIdPost($namespace, $integration_id, $asset_type, $asset_id, $lti_message_type, $lti_version, $resource_link_id, $oauth_consumer_key, $oauth_consumer_key2, $oauth_signature_method, $oauth_signature_method2, $oauth_timestamp, $oauth_timestamp2, $oauth_version, $oauth_version2, $oauth_nonce, $oauth_nonce2, $oauth_signature, $oauth_signature2);
} catch (Exception $e) {
    echo 'Exception when calling LTIApi->namespaceIntegrationsLti1IntegrationIdAssetsAssetTypeAssetIdPost: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **integration_id** | **string**| id of an integration | 
 **asset_type** | **string**| subtype of Asset, e.g. &#39;textbooks&#39;, &#39;digitisations&#39;, etc. | 
 **asset_id** | **string**| id of an asset | 
 **lti_message_type** | **string**| LTI launch data message type, must be &#39;basic-lti-launch-request&#39; | 
 **lti_version** | **string**| LTI launch version, must be &#39;LTI-1p0&#39; | 
 **resource_link_id** | **string**| LTI resource_link_id parameters | 
 **oauth_consumer_key** | **string**| OAuth 1.0 consumer_key parameters | [optional] 
 **oauth_consumer_key2** | **string**| OAuth 1.0 consumer_key parameters | [optional] 
 **oauth_signature_method** | **string**| OAuth 1.0 signature method, must be &#39;HMAC-SHA1&#39; | [optional] 
 **oauth_signature_method2** | **string**| OAuth 1.0 signature method, must be &#39;HMAC-SHA1&#39; | [optional] 
 **oauth_timestamp** | [**int**](.md)| OAuth 1.0 timestamp of request | [optional] 
 **oauth_timestamp2** | [**int**](.md)| OAuth 1.0 timestamp of request | [optional] 
 **oauth_version** | [**Number**](.md)| OAuth 1.0 version, must be &#39;1.0&#39; | [optional] 
 **oauth_version2** | [**Number**](.md)| OAuth 1.0 version, must be &#39;1.0&#39; | [optional] 
 **oauth_nonce** | **string**| OAuth 1.0 Nonce | [optional] 
 **oauth_nonce2** | **string**| OAuth 1.0 Nonce | [optional] 
 **oauth_signature** | **string**| OAuth 1.0 request signature | [optional] 
 **oauth_signature2** | **string**| OAuth 1.0 request signature | [optional] 

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP reuqest headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: text/html

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

