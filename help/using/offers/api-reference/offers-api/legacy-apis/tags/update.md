---
title: Uppdatera samlingskvalificerare
description: Med en samling kvalificerare kan ni ordna och sortera genom era erbjudanden på ett bättre sätt.
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: ef95a51b-1f14-470e-8229-3564bff9c67b
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 1%

---

# Uppdatera en samlingskvalificerare {#update-collection-qualifier}

Du kan ändra eller uppdatera en samlingskvalificerare (som tidigare kallades &quot;tagg&quot;) i behållaren genom att göra en PATCH-begäran till API:t [!DNL Offer Library].

Mer information om JSON Patch, inklusive tillgängliga åtgärder, finns i den officiella [JSON Patch-dokumentationen](https://jsonpatch.com/).

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som omfattar fälten *Content-Type* och *Accept* i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Acceptera | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/tag;version=0.1"` |

**API-format**

```http
PATCH /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Beskrivning | Exempel |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där taggarna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | Instans-ID för taggen som du vill uppdatera. | `d48fd160-13dc-11eb-bc55-c11be7252432` |

**Begäran**

```shell
curl -X PATCH \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/d48fd160-13dc-11eb-bc55-c11be7252432' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/vnd.adobe.platform.xcore.patch.hal+json; version=1; schema="https://ns.adobe.com/experience/offer-management/tag;version=0.1"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'\
  -d '[
        {
          "op": "replace",
          "path": "/_instance/xdm:name",
          "value": "Sales and promotions for the holidays"
        }
    ]'
```

| Parameter | Beskrivning |
| --------- | ----------- |
| `op` | Åtgärdsanropet som används för att definiera den åtgärd som krävs för att uppdatera anslutningen. Åtgärderna är: `add`, `replace`, `remove`, `copy` och `test`. |
| `path` | Sökvägen till den parameter som ska uppdateras. |
| `value` | Det nya värdet som du vill uppdatera parametern med. |

**Svar**

Ett lyckat svar returnerar den uppdaterade informationen om samlingskvalificeraren, inklusive dess unika instans-ID och samlingskvalificerare `@id`.

```json
{
    "instanceId": "d48fd160-13dc-11eb-bc55-c11be7252432",
    "@id": "xcore:tag:124e147572cd7866",
    "repo:etag": 2,
    "repo:createdDate": "2023-10-21T20:34:34.486296Z",
    "repo:lastModifiedDate": "2023-10-21T20:36:31.782607Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
