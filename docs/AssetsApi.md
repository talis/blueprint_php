# Swagger\Client\AssetsApi

All URIs are relative to *http://localhost:10010/1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addAssetToNode**](AssetsApi.md#addAssetToNode) | **PUT** /{namespace}/nodes/{type}/{id}/assets/{assetType}/{assetId} | 
[**deleteAsset**](AssetsApi.md#deleteAsset) | **DELETE** /{namespace}/assets/{assetType}/{assetId} | 
[**deleteAssets**](AssetsApi.md#deleteAssets) | **DELETE** /{namespace}/assets | Delete assets
[**getAsset**](AssetsApi.md#getAsset) | **GET** /{namespace}/assets/{assetType}/{assetId} | 
[**getAssetsInNode**](AssetsApi.md#getAssetsInNode) | **GET** /{namespace}/nodes/{type}/{id}/assets | 
[**removeAssetFromNode**](AssetsApi.md#removeAssetFromNode) | **DELETE** /{namespace}/nodes/{type}/{id}/assets/{assetType}/{assetId} | 
[**replaceAsset**](AssetsApi.md#replaceAsset) | **PUT** /{namespace}/assets/{assetType}/{assetId} | Replaces the Asset with the data sent in the body
[**searchAssets**](AssetsApi.md#searchAssets) | **GET** /{namespace}/assets | Search assets


# **addAssetToNode**
> \Swagger\Client\Model\AssetBody addAssetToNode($namespace, $type, $id, $asset_type, $asset_id)



Add an asset to the node.  Body must be empty.  Will upsert the asset if it doesn't exist

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$id = "id_example"; // string | id identifying a domain model
$asset_type = "asset_type_example"; // string | subtype of Asset, e.g. 'textbooks', 'digitisations', etc.
$asset_id = "asset_id_example"; // string | id of an asset

try { 
    $result = $api_instance->addAssetToNode($namespace, $type, $id, $asset_type, $asset_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->addAssetToNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **id** | **string**| id identifying a domain model | 
 **asset_type** | **string**| subtype of Asset, e.g. &#39;textbooks&#39;, &#39;digitisations&#39;, etc. | 
 **asset_id** | **string**| id of an asset | 

### Return type

[**\Swagger\Client\Model\AssetBody**](AssetBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteAsset**
> deleteAsset($namespace, $asset_id, $asset_type)



Delete an Asset

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$asset_id = "asset_id_example"; // string | id of an asset
$asset_type = "asset_type_example"; // string | subtype of Asset, e.g. 'textbooks', 'digitisations', etc.

try { 
    $api_instance->deleteAsset($namespace, $asset_id, $asset_type);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->deleteAsset: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **asset_id** | **string**| id of an asset | 
 **asset_type** | **string**| subtype of Asset, e.g. &#39;textbooks&#39;, &#39;digitisations&#39;, etc. | 

### Return type

void (empty response body)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteAssets**
> deleteAssets($namespace)

Delete assets

Delete all assets belonging to the given namespace.

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.

try { 
    $api_instance->deleteAssets($namespace);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->deleteAssets: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 

### Return type

void (empty response body)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getAsset**
> \Swagger\Client\Model\AssetBody getAsset($namespace, $asset_type, $asset_id)



Get details of a given asset

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$asset_type = "asset_type_example"; // string | subtype of Asset, e.g. 'textbooks', 'digitisations', etc.
$asset_id = "asset_id_example"; // string | id of an asset

try { 
    $result = $api_instance->getAsset($namespace, $asset_type, $asset_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->getAsset: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **asset_type** | **string**| subtype of Asset, e.g. &#39;textbooks&#39;, &#39;digitisations&#39;, etc. | 
 **asset_id** | **string**| id of an asset | 

### Return type

[**\Swagger\Client\Model\AssetBody**](AssetBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getAssetsInNode**
> \Swagger\Client\Model\AssetResultSet getAssetsInNode($namespace, $type, $id, $filter_asset_type, $offset, $limit)



Get for assets in the relevant node

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$id = "id_example"; // string | id identifying a domain model
$filter_asset_type = array("filter_asset_type_example"); // string[] | type of asset to return. This filters the results by asset type, but returns all the assets associated with the result.
$offset = new Number(); // Number | index to start result set from
$limit = new Number(); // Number | number of records to return

try { 
    $result = $api_instance->getAssetsInNode($namespace, $type, $id, $filter_asset_type, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->getAssetsInNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **id** | **string**| id identifying a domain model | 
 **filter_asset_type** | [**string[]**](string.md)| type of asset to return. This filters the results by asset type, but returns all the assets associated with the result. | [optional] 
 **offset** | [**Number**](.md)| index to start result set from | [optional] 
 **limit** | [**Number**](.md)| number of records to return | [optional] 

### Return type

[**\Swagger\Client\Model\AssetResultSet**](AssetResultSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **removeAssetFromNode**
> removeAssetFromNode($namespace, $type, $id, $asset_type, $asset_id)



Remove an asset from the relevant node

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$id = "id_example"; // string | id identifying a domain model
$asset_type = "asset_type_example"; // string | subtype of Asset, e.g. 'textbooks', 'digitisations', etc.
$asset_id = "asset_id_example"; // string | id of an asset

try { 
    $api_instance->removeAssetFromNode($namespace, $type, $id, $asset_type, $asset_id);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->removeAssetFromNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **id** | **string**| id identifying a domain model | 
 **asset_type** | **string**| subtype of Asset, e.g. &#39;textbooks&#39;, &#39;digitisations&#39;, etc. | 
 **asset_id** | **string**| id of an asset | 

### Return type

void (empty response body)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **replaceAsset**
> \Swagger\Client\Model\AssetBody replaceAsset($namespace, $asset_id, $asset_type, $body)

Replaces the Asset with the data sent in the body

Wholesale replacement of Asset data: if you were to PUT to:\n  /1/{namespace}/assets/sometype/someid\n\nwith a body of:\n  { type: \"someothertype\", id: \"someotherid\" }\n\nIt would change the Asset's path to:\n  /1/{namespace}/assets/someothertype/someotherid\n\nand\n  /1/{namespace}/assets/sometype/someid\nwould return a 404.\nIt would also update the assets associated with any node.\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$asset_id = "asset_id_example"; // string | id of an asset
$asset_type = "asset_type_example"; // string | subtype of Asset, e.g. 'textbooks', 'digitisations', etc.
$body = new \Swagger\Client\Model\AssetBody(); // \Swagger\Client\Model\AssetBody | asset

try { 
    $result = $api_instance->replaceAsset($namespace, $asset_id, $asset_type, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->replaceAsset: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **asset_id** | **string**| id of an asset | 
 **asset_type** | **string**| subtype of Asset, e.g. &#39;textbooks&#39;, &#39;digitisations&#39;, etc. | 
 **body** | [**\Swagger\Client\Model\AssetBody**](\Swagger\Client\Model\AssetBody.md)| asset | [optional] 

### Return type

[**\Swagger\Client\Model\AssetBody**](AssetBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **searchAssets**
> \Swagger\Client\Model\AssetResultSet searchAssets($namespace, $offset, $limit, $include, $filter_node, $filter_asset_type)

Search assets

This endpoint provides a way to get assets as a pageable result set, based (optionally) on filters.\nThe include parameter can only be set to `nodes`\n\n###### Find all assets in namespace abc\n`/1/abc/assets`\n\n###### Find all lists for abc:\n`/1/abc/assets?filter[assetType]=lists`\n\n###### Find all assets that are related to a given node of DEP101:\n`/1/abc/assets?filter[node]=departments%2Fdep101`\n\n###### Find all assets that are related to both node DEP101 and DEP102:\n`/1/abc/assets?filter[node]=departments%2Fdep101&filter[node]=departments%2Fdep102`\n\n###### Find all assets that are related to either node DEP101 and DEP102:\n`/1/abc/assets?filter[node]=departments%2Fdep101,departments%2Fdep102`\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\AssetsApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$offset = new Number(); // Number | index to start result set from
$limit = new Number(); // Number | number of records to return
$include = array("include_example"); // string[] | comma separated list of elements to hydrate. Can include children, parents, nodes, and/or assets
$filter_node = array("filter_node_example"); // string[] | limit to assets that are related to a node matching type/code
$filter_asset_type = array("filter_asset_type_example"); // string[] | type of asset to return. This filters the results by asset type, but returns all the assets associated with the result.

try { 
    $result = $api_instance->searchAssets($namespace, $offset, $limit, $include, $filter_node, $filter_asset_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AssetsApi->searchAssets: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **offset** | [**Number**](.md)| index to start result set from | [optional] 
 **limit** | [**Number**](.md)| number of records to return | [optional] 
 **include** | [**string[]**](string.md)| comma separated list of elements to hydrate. Can include children, parents, nodes, and/or assets | [optional] 
 **filter_node** | [**string[]**](string.md)| limit to assets that are related to a node matching type/code | [optional] 
 **filter_asset_type** | [**string[]**](string.md)| type of asset to return. This filters the results by asset type, but returns all the assets associated with the result. | [optional] 

### Return type

[**\Swagger\Client\Model\AssetResultSet**](AssetResultSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

