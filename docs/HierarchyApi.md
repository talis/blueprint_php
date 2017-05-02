# Swagger\Client\HierarchyApi

All URIs are relative to *http://localhost:10010/1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addNode**](HierarchyApi.md#addNode) | **POST** /{namespaceIncGlobal}/nodes | 
[**bulkUpload**](HierarchyApi.md#bulkUpload) | **POST** /{namespace}/nodes.csv | 
[**deleteNode**](HierarchyApi.md#deleteNode) | **DELETE** /{namespace}/nodes/{type}/{id} | 
[**deleteNodes**](HierarchyApi.md#deleteNodes) | **DELETE** /{namespaceIncGlobal}/nodes | Delete nodes
[**exportHierarchy**](HierarchyApi.md#exportHierarchy) | **GET** /{namespace}/nodes.csv | 
[**getAncestors**](HierarchyApi.md#getAncestors) | **GET** /{namespace}/nodes/{type}/{id}/ancestors | Get ancestor nodes
[**getChildren**](HierarchyApi.md#getChildren) | **GET** /{namespace}/nodes/{type}/{id}/children | Get child nodes
[**getDescendants**](HierarchyApi.md#getDescendants) | **GET** /{namespace}/nodes/{type}/{id}/descendants | Get descendant nodes
[**getNode**](HierarchyApi.md#getNode) | **GET** /{namespace}/nodes/{type}/{id} | 
[**getParents**](HierarchyApi.md#getParents) | **GET** /{namespace}/nodes/{type}/{id}/parents | Get parent nodes
[**replaceNode**](HierarchyApi.md#replaceNode) | **PUT** /{namespace}/nodes/{type}/{id} | 
[**searchNodes**](HierarchyApi.md#searchNodes) | **GET** /{namespaceIncGlobal}/nodes | Search nodes
[**updateNode**](HierarchyApi.md#updateNode) | **PATCH** /{namespace}/nodes/{type}/{id} | 


# **addNode**
> \Swagger\Client\Model\NodeBody addNode($namespace_inc_global, $body)



Add a node

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace_inc_global = "namespace_inc_global_example"; // string | identifier namespacing the blueprint. `global` is a special namespace which references data from all blueprints in the call.
$body = new \Swagger\Client\Model\NodeBody(); // \Swagger\Client\Model\NodeBody | node

try { 
    $result = $api_instance->addNode($namespace_inc_global, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->addNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace_inc_global** | **string**| identifier namespacing the blueprint. `global` is a special namespace which references data from all blueprints in the call. | 
 **body** | [**\Swagger\Client\Model\NodeBody**](\Swagger\Client\Model\NodeBody.md)| node | 

### Return type

[**\Swagger\Client\Model\NodeBody**](NodeBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **bulkUpload**
> bulkUpload($namespace)



Send operations to modify nodes in bulk, to be applied/rejected as a single transaction.\nFormat will be:\n\n  OLD NODE TYPE, OLD NODE ID, NEW NODE TYPE, NEW NODE ID, PARENTS, TITLE, DESCRIPTION, DOMAIN IDS, STUDENT NUMBERS\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.

try { 
    $api_instance->bulkUpload($namespace);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->bulkUpload: ', $e->getMessage(), "\n";
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

 - **Content-Type**: text/plain, application/octet-stream
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteNode**
> deleteNode($namespace, $id, $type)



Delete a node

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$id = "id_example"; // string | id identifying a domain model
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.

try { 
    $api_instance->deleteNode($namespace, $id, $type);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->deleteNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **id** | **string**| id identifying a domain model | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 

### Return type

void (empty response body)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteNodes**
> deleteNodes($namespace_inc_global)

Delete nodes

Delete all nodes belonging to the given namespace.

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace_inc_global = "namespace_inc_global_example"; // string | identifier namespacing the blueprint. `global` is a special namespace which references data from all blueprints in the call.

try { 
    $api_instance->deleteNodes($namespace_inc_global);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->deleteNodes: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace_inc_global** | **string**| identifier namespacing the blueprint. `global` is a special namespace which references data from all blueprints in the call. | 

### Return type

void (empty response body)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **exportHierarchy**
> exportHierarchy($namespace)



Download the blueprint's nodes in CSV format\nFormat will be:\n\n  OLD NODE TYPE, OLD NODE ID, NEW NODE TYPE, NEW NODE ID, PARENTS, TITLE, DESCRIPTION, DOMAIN IDS, STUDENT NUMBERS\n\nOLD NODE TYPE and OLD NODE ID are left intentionally blank to allow direct upload of the output back into the bulk importer\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.

try { 
    $api_instance->exportHierarchy($namespace);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->exportHierarchy: ', $e->getMessage(), "\n";
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

# **getAncestors**
> \Swagger\Client\Model\NodeResultSet getAncestors($id, $namespace, $type, $offset, $limit)

Get ancestor nodes

A proxy for finding ancestors of a given node, equivalent to\n`/1/abc/nodes?filter[descendant]=department%2Fdep101`\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$id = "id_example"; // string | id identifying a domain model
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$offset = new Number(); // Number | index to start result set from
$limit = new Number(); // Number | number of records to return

try { 
    $result = $api_instance->getAncestors($id, $namespace, $type, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->getAncestors: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| id identifying a domain model | 
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **offset** | [**Number**](.md)| index to start result set from | [optional] 
 **limit** | [**Number**](.md)| number of records to return | [optional] 

### Return type

[**\Swagger\Client\Model\NodeResultSet**](NodeResultSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getChildren**
> \Swagger\Client\Model\NodeResultSet getChildren($id, $namespace, $type, $offset, $limit)

Get child nodes

A proxy for finding children of a given node, equivalent to\n`/1/abc/nodes?filter[parent]=department%2Fdep101`\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$id = "id_example"; // string | id identifying a domain model
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$offset = new Number(); // Number | index to start result set from
$limit = new Number(); // Number | number of records to return

try { 
    $result = $api_instance->getChildren($id, $namespace, $type, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->getChildren: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| id identifying a domain model | 
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **offset** | [**Number**](.md)| index to start result set from | [optional] 
 **limit** | [**Number**](.md)| number of records to return | [optional] 

### Return type

[**\Swagger\Client\Model\NodeResultSet**](NodeResultSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getDescendants**
> \Swagger\Client\Model\NodeResultSet getDescendants($id, $namespace, $type, $offset, $limit)

Get descendant nodes

A proxy for finding descendants of a given node, equivalent to\n`/1/abc/nodes?filter[ancestor]=department%2Fdep101`\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$id = "id_example"; // string | id identifying a domain model
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$offset = new Number(); // Number | index to start result set from
$limit = new Number(); // Number | number of records to return

try { 
    $result = $api_instance->getDescendants($id, $namespace, $type, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->getDescendants: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| id identifying a domain model | 
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **offset** | [**Number**](.md)| index to start result set from | [optional] 
 **limit** | [**Number**](.md)| number of records to return | [optional] 

### Return type

[**\Swagger\Client\Model\NodeResultSet**](NodeResultSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getNode**
> \Swagger\Client\Model\NodeBody getNode($namespace, $id, $type, $include)



Get details of a given node

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$id = "id_example"; // string | id identifying a domain model
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$include = array("include_example"); // string[] | comma separated list of elements to hydrate. Can include children, parents, nodes, and/or assets

try { 
    $result = $api_instance->getNode($namespace, $id, $type, $include);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->getNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **id** | **string**| id identifying a domain model | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **include** | [**string[]**](string.md)| comma separated list of elements to hydrate. Can include children, parents, nodes, and/or assets | [optional] 

### Return type

[**\Swagger\Client\Model\NodeBody**](NodeBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getParents**
> \Swagger\Client\Model\NodeResultSet getParents($id, $namespace, $type, $offset, $limit)

Get parent nodes

A proxy for finding parents of a given node, equivalent to\n`/1/abc/nodes?filter[child]=department%2Fdep101`\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$id = "id_example"; // string | id identifying a domain model
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.
$offset = new Number(); // Number | index to start result set from
$limit = new Number(); // Number | number of records to return

try { 
    $result = $api_instance->getParents($id, $namespace, $type, $offset, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->getParents: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| id identifying a domain model | 
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 
 **offset** | [**Number**](.md)| index to start result set from | [optional] 
 **limit** | [**Number**](.md)| number of records to return | [optional] 

### Return type

[**\Swagger\Client\Model\NodeResultSet**](NodeResultSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **replaceNode**
> \Swagger\Client\Model\NodeBody replaceNode($namespace, $id, $body, $type)



Replaces the node with the data sent in the body

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$id = "id_example"; // string | id identifying a domain model
$body = new \Swagger\Client\Model\NodeBody(); // \Swagger\Client\Model\NodeBody | node
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.

try { 
    $result = $api_instance->replaceNode($namespace, $id, $body, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->replaceNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **id** | **string**| id identifying a domain model | 
 **body** | [**\Swagger\Client\Model\NodeBody**](\Swagger\Client\Model\NodeBody.md)| node | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 

### Return type

[**\Swagger\Client\Model\NodeBody**](NodeBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **searchNodes**
> \Swagger\Client\Model\NodeResultSet searchNodes($namespace_inc_global, $offset, $limit, $include, $filter_asset, $filter_node_type, $filter_child, $filter_parent, $filter_ancestor, $filter_descendant, $filter_has_assets, $filter_asset_type, $filter_from, $filter_to, $q_node, $q_child, $q_parent, $q_descendant, $q_ancestor, $filter_asset_node)

Search nodes

This endpoint is a really flexible way to ask questions about the hierarchy.\nThe includes parameter can be set to either parents, children, assets.\n\nExamples:\n\n###### Find all nodes for abc:\n`/1/abc/nodes`\n\n###### Find all modules for abc:\n`/1/abc/nodes?filter[nodeType]=Modules`\n\n###### Find all nodes that are descendants of DEP101:\n`/1/abc/nodes?filter[descendant]=departments%2Fdep101`\n\n###### Find all nodes that are descendants of DEP101 or DEP102:\n`/1/abc/nodes?filter[descendant]=departments%2Fdep101,departments%2Fdep102`\n\n###### Find all nodes that are descendants of DEP101 and DEP102:\n`/1/abc/nodes?filter[descendant]=departments%2Fdep101&filter[descendant]=departments%2Fdep102``\n\n###### Find all Departments that are ancestors of ABF203:\n`/1/abc/nodes?filter[descendant]=modules%2Fabf203&filter[nodeType]=Departments` # <= case insensitive\n\n###### Find all nodes with list assets that are descendants of DEP101 for abc:\n`/1/abc/nodes?filter[nodeType]=Modules&filter[ancestor]=departments%2FDEP101&filter[hasAssets]=true&filter[assetType]=Lists`\n\n###### Globally, find all modules that have no list assets\n`/1/global/nodes?filter[nodeType]=Modules&filter[hasAssets]=false&filter[assetType]=Lists`\n\n###### Find all nodes of type modules during 2015 that have no assets. Note a node's valid_from/valid_to just need to overlap from/to to qualify\n`/1/global/nodes?filter[nodeType]=Modules&filter[hasAssets]=false&filter[from]=20150101&filter[to]=20151231`\n\n###### Find all nodes of type modules with assets which are also related to DEP101.\n`/1/global/nodes?filter[nodeType]=Modules&filter[asset.node]=departments%2Fdep101`\n

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace_inc_global = "namespace_inc_global_example"; // string | identifier namespacing the blueprint. `global` is a special namespace which references data from all blueprints in the call.
$offset = new Number(); // Number | index to start result set from
$limit = new Number(); // Number | number of records to return
$include = array("include_example"); // string[] | comma separated list of elements to hydrate. Can include children, parents, nodes, and/or assets
$filter_asset = array("filter_asset_example"); // string[] | limit to nodes that have an asset matching type/code
$filter_node_type = array("filter_node_type_example"); // string[] | type of nodes to return
$filter_child = array("filter_child_example"); // string[] | limit to nodes with children matching type/code
$filter_parent = array("filter_parent_example"); // string[] | limit to nodes with parent matching type/code
$filter_ancestor = array("filter_ancestor_example"); // string[] | limit to nodes with ancestor matching type/code
$filter_descendant = array("filter_descendant_example"); // string[] | limit to nodes with descendant matching type/code
$filter_has_assets = true; // bool | limit to either nodes that have assets (true) nodes that have no assets (false) or omit to consider both nodes with and without assets
$filter_asset_type = array("filter_asset_type_example"); // string[] | type of asset to return. This filters the results by asset type, but returns all the assets associated with the result.
$filter_from = new \DateTime(); // \DateTime | limit to results valid after this date, format is  ISO8601 date
$filter_to = new \DateTime(); // \DateTime | limit to results valid before this date, format is  ISO8601
$q_node = "q_node_example"; // string | query term(s) to search for nodes.  Allows wildcard searching with '*'
$q_child = "q_child_example"; // string | query id/title terms to search for child nodes.  Allows wildcard searching with '*'
$q_parent = "q_parent_example"; // string | query id/title terms to search for parent nodes.  Allows wildcard searching with '*'
$q_descendant = "q_descendant_example"; // string | query id/title terms to search for descendant nodes.  Allows wildcard searching with '*'
$q_ancestor = "q_ancestor_example"; // string | query id/title terms to search for ancestor nodes.  Allows wildcard searching with '*'
$filter_asset_node = array("filter_asset_node_example"); // string[] | limit to nodes that have an asset related to another node matching type/code

try { 
    $result = $api_instance->searchNodes($namespace_inc_global, $offset, $limit, $include, $filter_asset, $filter_node_type, $filter_child, $filter_parent, $filter_ancestor, $filter_descendant, $filter_has_assets, $filter_asset_type, $filter_from, $filter_to, $q_node, $q_child, $q_parent, $q_descendant, $q_ancestor, $filter_asset_node);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->searchNodes: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace_inc_global** | **string**| identifier namespacing the blueprint. `global` is a special namespace which references data from all blueprints in the call. | 
 **offset** | [**Number**](.md)| index to start result set from | [optional] 
 **limit** | [**Number**](.md)| number of records to return | [optional] 
 **include** | [**string[]**](string.md)| comma separated list of elements to hydrate. Can include children, parents, nodes, and/or assets | [optional] 
 **filter_asset** | [**string[]**](string.md)| limit to nodes that have an asset matching type/code | [optional] 
 **filter_node_type** | [**string[]**](string.md)| type of nodes to return | [optional] 
 **filter_child** | [**string[]**](string.md)| limit to nodes with children matching type/code | [optional] 
 **filter_parent** | [**string[]**](string.md)| limit to nodes with parent matching type/code | [optional] 
 **filter_ancestor** | [**string[]**](string.md)| limit to nodes with ancestor matching type/code | [optional] 
 **filter_descendant** | [**string[]**](string.md)| limit to nodes with descendant matching type/code | [optional] 
 **filter_has_assets** | **bool**| limit to either nodes that have assets (true) nodes that have no assets (false) or omit to consider both nodes with and without assets | [optional] 
 **filter_asset_type** | [**string[]**](string.md)| type of asset to return. This filters the results by asset type, but returns all the assets associated with the result. | [optional] 
 **filter_from** | **\DateTime**| limit to results valid after this date, format is  ISO8601 date | [optional] 
 **filter_to** | **\DateTime**| limit to results valid before this date, format is  ISO8601 | [optional] 
 **q_node** | **string**| query term(s) to search for nodes.  Allows wildcard searching with &#39;*&#39; | [optional] 
 **q_child** | **string**| query id/title terms to search for child nodes.  Allows wildcard searching with &#39;*&#39; | [optional] 
 **q_parent** | **string**| query id/title terms to search for parent nodes.  Allows wildcard searching with &#39;*&#39; | [optional] 
 **q_descendant** | **string**| query id/title terms to search for descendant nodes.  Allows wildcard searching with &#39;*&#39; | [optional] 
 **q_ancestor** | **string**| query id/title terms to search for ancestor nodes.  Allows wildcard searching with &#39;*&#39; | [optional] 
 **filter_asset_node** | [**string[]**](string.md)| limit to nodes that have an asset related to another node matching type/code | [optional] 

### Return type

[**\Swagger\Client\Model\NodeResultSet**](NodeResultSet.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateNode**
> \Swagger\Client\Model\NodeBody updateNode($namespace, $id, $body, $type)



Perform a partial update of a node

### Example 
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth2
Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$api_instance = new Swagger\Client\Api\HierarchyApi();
$namespace = "namespace_example"; // string | identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores.
$id = "id_example"; // string | id identifying a domain model
$body = new \Swagger\Client\Model\NodeBody(); // \Swagger\Client\Model\NodeBody | node
$type = "type_example"; // string | subtype of Node, e.g. 'modules', 'departments', etc.

try { 
    $result = $api_instance->updateNode($namespace, $id, $body, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HierarchyApi->updateNode: ', $e->getMessage(), "\n";
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **string**| identifier namespacing the blueprint. It must start with a letter or underscore and can only be followed by letters, numbers and underscores. | 
 **id** | **string**| id identifying a domain model | 
 **body** | [**\Swagger\Client\Model\NodeBody**](\Swagger\Client\Model\NodeBody.md)| node | 
 **type** | **string**| subtype of Node, e.g. &#39;modules&#39;, &#39;departments&#39;, etc. | 

### Return type

[**\Swagger\Client\Model\NodeBody**](NodeBody.md)

### Authorization

[oauth2](../README.md#oauth2)

### HTTP reuqest headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.api+json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

