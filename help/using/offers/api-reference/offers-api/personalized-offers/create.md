---
title: Skapa personaliserade erbjudanden
description: Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.
source-git-commit: 4ff255b6b57823a1a4622dbc62b4b8886fd956a0
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 7%

---

# Skapa ett personaliserat erbjudande

Ett personaliserat erbjudande är ett anpassningsbart marknadsföringsmeddelande som baseras på regler och begränsningar för behörighet.

Du kan skapa ett anpassat erbjudande genom att göra en POST-förfrågan till API:t [!DNL Offer Library] och samtidigt ange ditt behållar-ID.

## Sidhuvuden för acceptera och innehållstyp

I följande tabell visas giltiga värden som består av fälten *Content-Type* och *Accept* i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Acceptera | `application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1` |
| Content-Type | `application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5"` |

**API-format**

```http
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/instances
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | Behållaren där personaliserade erbjudanden finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**Begäran**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances' \
  -H 'Accept: application/vnd.adobe.platform.xcore.xdm.receipt+json; version=1' \
  -H 'Content-Type: application/schema-instance+json; version=1;  schema="https://ns.adobe.com/experience/offer-management/personalized-offer;version=0.5"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
        "xdm:name": "Sale offer",
        "xdm:status": "draft",
        "xdm:representations": [
            {
                "xdm:components": [
                    {
                        "dc:language": [
                            "en"
                        ],
                        "@type": "https://ns.adobe.com/experience/offer-management/content-component-html",
                        "dc:format": "text/html"
                    }
                ],
                "xdm:placement": "xcore:offer-placement:124e0be5699743d3"
            }
        ],
        "xdm:selectionConstraint": {
            "xdm:startDate": "2020-10-01T16:00:00Z",
            "xdm:endDate": "2021-12-13T16:00:00Z",
            "xdm:eligibilityRule": "xcore:eligibility-rule:124e0faf5b8ee89b"
        },
        "xdm:rank": {
            "xdm:priority": 1
        },
        "xdm:cappingConstraint": {
            "xdm:globalCap": 150
        },
        "xdm:tags": [
            "xcore:tag:124e147572cd7866"
        ]
    }'
```

**Svar**

Ett svar returnerar information om det nya anpassade erbjudandet, inklusive dess unika instans-ID och placering `@id`. Du kan använda instans-ID:t i senare steg för att uppdatera eller ta bort ditt anpassade erbjudande.

```json
{
    "instanceId": "0f4bc230-13df-11eb-bc55-c11be7252432",
    "@id": "xcore:personalized-offer:124e181c8b0d7878",
    "repo:etag": 1,
    "repo:createdDate": "2020-10-21T20:50:32.018624Z",
    "repo:lastModifiedDate": "2020-10-21T20:50:32.018624Z",
    "repo:createdBy": "{CREATED_BY}",
    "repo:lastModifiedBy": "{MODIFIED_BY}",
    "repo:createdByClientId": "{CREATED_CLIENT_ID}",
    "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}"
}
```
