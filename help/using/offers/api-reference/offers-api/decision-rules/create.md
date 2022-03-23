---
title: Skapa en beslutsregel
description: Beslutsregler läggs till i ett personaliserat erbjudande och tillämpas på en profil för att avgöra vem som är berättigad.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 6a05efca-31bd-46d5-998d-ff3038d9013f
source-git-commit: 353aaf2bc4f32b1b0d7bfc2f7f4f48537cc79df4
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 7%

---

# Skapa en beslutsregel {#create-decision-rule}

Beslutsregler läggs till i ett personaliserat erbjudande och tillämpas på en profil för att avgöra vem som är berättigad.

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör *Content-Type* och *Acceptera* fält i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Acceptera | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3"` |

**API-format**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där beslutsreglerna finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Begäran**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/eligibility-rule;version=0.3"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
        "xdm:name": "Sales rule",
        "description": "Decisioning rule for sales",
        "condition": {
            "type": "PQL",
            "format": "pql/text",
            "value": "profile.person.name.firstName.equals(\"Joe\", false)"
        },
        "xdm:definedOn": {
            "profile": {
                "xdm:schema": {
                    "$ref": "https://ns.adobe.com/xdm/context/profile_union",
                    "version": "1"
                },
                "xdm:referencePaths": [
                    "person.name.firstName"
                ]
            }
        }
    }'
```

**Svar**

Ett godkänt svar returnerar information om den nya beslutsregeln, inklusive dess unika instans-ID och placering `@id`. Du kan använda instans-ID:t i senare steg för att uppdatera eller ta bort din beslutsregel. Du kan använda din unika beslutsregel `@id` i en senare självstudiekurs för att skapa personaliserade erbjudanden.

```json
{
    "instanceId": "eaa5af90-13d9-11eb-9472-194dee6dc381",
    "@id": "xcore:eligibility-rule:124e0faf5b8ee89b",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-21T20:13:43.048666Z",
    "repo:lastModifiedDate": "2020-10-21T20:13:43.048666Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
