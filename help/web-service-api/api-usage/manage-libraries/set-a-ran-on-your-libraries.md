---
title: Set a rank on your libraries
description: Set a rank on your libraries by using the Places REST API.
exl-id: c922bddc-1587-4da8-acb4-c2d69ce11808
---
# Set a rank on your libraries {#set-rank-on-libraries}

A PUT method that allows you to set a rank order on all of your libraries.

## Request

`PUT https://api-places-dev.adobe.io/places/placesapi/v1/libraries/rank`

## Headers

```-H Content-Type: application/json'  
-H 'Authorization: Bearer <TOKEN>`  
-H 'x-api-key: <API KEY>'  
-H 'x-gw-ims-org-id: <ORGID>'  
-H 'Accept-Language: en-US'
```

## PUT data

```
"library_rank_order": ["dfcc5270-1d6d-4bc9-9cd9-85ecd5ebc12b","ea45781f-26af-44b1-b4f8-43baf5f0fe28"]  
}
```

## Sample response

```
{"library_rank_order" ["dfcc5270-1d6d-4bc9-9cd9-85ecd5ebc12b","ea45781f-26af-44b1-b4f8-43baf5f0fe28"]}
```

## CURL command

```
curl -X PUT `'https://api-places.adobe.io/places/placesapi/v1/libraries/rank'` -H 'x-api-key: <API KEY>' -H 'Authorization: Bearer <TOKEN>' -H 'x-gw-ims-org-id: <ORGID>' -d '{"library_rank_order": ["dfcc5270-1d6d-4bc9-9cd9-85ecd5ebc12b","ea45781f-26af-44b1-b4f8-43baf5f0fe28"]}' -H "Content-Type: application/json"
```

>[!IMPORTANT]
>
>Replace variables such as `<API KEY>`, `<TOKEN>`, and `<ORGID>` with actual values.
