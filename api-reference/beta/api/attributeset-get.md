---
title: "Get attributeSet"
description: "Read the properties and relationships of an attributeSet object."
author: "rolyon"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Get attributeSet
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of an [attributeSet](../resources/attributeset.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|CustomSecAttributeAssignment.ReadWrite.All, CustomSecAttributeDefinition.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|CustomSecAttributeAssignment.ReadWrite.All, CustomSecAttributeDefinition.ReadWrite.All|

The signed-in user must also be assigned one of the following [directory roles](/azure/active-directory/roles/permissions-reference):

+ Attribute Assignment Reader
+ Attribute Definition Reader
+ Attribute Assignment Administrator
+ Attribute Definition Administrator

By default, Global Administrator and other administrator roles do not have permissions to define, read, or assign custom security attributes.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /directory/attributeSets/{attributeSetId}
```

## Optional query parameters
This method supports the `$select` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and an [attributeSet](../resources/attributeset.md) object in the response body.

## Examples

### Example: Get an attribute set

The following example gets a single attribute set named `Engineering`.

#### Request
<!-- {
  "blockType": "request",
  "name": "get_attributeset_single"
}
-->
``` http
GET https://graph.microsoft.com/beta/directory/attributeSets/Engineering
```

#### Response

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.attributeSet"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#directory/attributeSets/$entity",
    "description": "Attributes for engineering team",
    "id": "Engineering",
    "maxAttributesPerSet": 25
}
```
