---
title: Leverera erbjudanden
description: Beslutshantering är en samling tjänster och gränssnittsprogram som gör det möjligt för marknadsförare att skapa och leverera personaliserade erbjudanden för slutanvändare i alla kanaler och i alla tillämpningar med hjälp av logiska funktioner och beslutsregler.
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 692d0aae-6fa1-40b8-a35f-9845d78317a3
source-git-commit: a2f4a7f7b08cce3980eab71fea0b2704975087ca
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 2%

---

# Leverera erbjudanden med hjälp av besluts-API {#decisioning-api}

Med Beslutshantering kan ni skapa och leverera personaliserade erbjudandeupplevelser för slutanvändare i alla kanaler och i alla tillämpningar med hjälp av logiska funktioner och beslutsregler. Ett erbjudande är ett marknadsföringsmeddelande som kan ha kopplade regler som anger vem som kan se erbjudandet.

Du kan skapa och leverera erbjudanden genom att göra en förfrågan till POSTEN [!DNL Decisioning] API.

Den här självstudiekursen kräver en fungerande förståelse av API:er, särskilt när det gäller beslutshantering. Mer information finns i [Utvecklarhandbok för API för beslutshantering](../getting-started.md). Den här självstudien kräver också att du har ett unikt placerings-ID och värde för besluts-ID tillgängligt. Om du inte har fått dessa värden kan du gå till självstudiekurserna för [skapa en placering](../offers-api/placements/create.md) och [skapa ett beslut](../activities-api/activities/create.md).

➡️  [Upptäck den här funktionen i en video](#video)

## Sidhuvuden för acceptera och innehållstyp {#accept-and-content-type-headers}

I följande tabell visas giltiga värden som utgör *Content-Type* och *Acceptera* fält i begärandehuvudet:

| Rubriknamn | Värde |
| ----------- | ----- |
| Acceptera | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"` |
| Content-Type | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"` |

## API-begäran {#request}

### API-format

```https
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/decisions
```

| Parameter | Beskrivning | Exempel |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | Slutpunktssökvägen för databas-API:er. | `https://platform.adobe.io/data/core/ode/` |
| `{CONTAINER_ID}` | Behållaren där besluten finns. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

### Begäran

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/ode/e0bd8463-0913-4ca1-bd84-6309134ca1f6/decisions' \
  -H 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
  -H 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"'
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
  -d '{
        "xdm:propositionRequests": [
            {
              "xdm:placementId": "xcore:offer-placement:ffed0456",
              "xdm:activityId": "xcore:offer-activity:ffed0123",
              "xdm:itemCount": 2
            },
            {
              "xdm:placementId": "xcore:offer-placement:ffed0012",
              "xdm:activityId": "xcore:offer-activity:fffc0789"
            }
        ],
        "xdm:profiles": [
            {
              "xdm:identityMap": {
                "SWCUSTID": [
                {
                    "xdm:id": "123@abc.com"
                }
                ]
            },
            "xdm:decisionRequestId": "0AA00002-0000-1224-c0de-cjf98Csj43"
            }
        ],
        "xdm:allowDuplicatePropositions": {
            "xdm:acrossActivities": true,
            "xdm:acrossPlacements": true
        },
        "xdm:mergePolicy": {
            "xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"
        },
        "xdm:responseFormat": {
            "xdm:includeContent": true,
            "xdm:includeMetadata": {
            "xdm:activity": [
                "name"
            ],
            "xdm:option": [
                "name"
            ],
            "xdm:placement": [
                "name"
            ]
            }
        }
      }'
```

| Egenskap | Beskrivning | Exempel |
| -------- | ----------- | ------- |
| `xdm:propositionRequests` | Det här objektet innehåller placerings- och beslutsidentifierare. |
| `xdm:propositionRequests.xdm:placementId` | Den unika placeringsidentifieraren. | `"xdm:placementId": "xcore:offer-placement:ffed0456"` |
| `xdm:propositionRequests.xdm:activityId` | Den unika beslutsidentifieraren. | `"xdm:activityId": "xcore:offer-activity:ffed0123"` |
| `xdm:itemCount` | Antalet erbjudanden som ska returneras. Det högsta antalet är 30. | `"xdm:itemCount": 2` |
| `xdm:profiles` | Det här objektet innehåller information om profilen som beslutet begärs för. För en API-begäran innehåller detta en profil. |
| `xdm:profiles.xdm:identityMap` | Det här objektet innehåller en uppsättning slutanvändaridentiteter baserat på ID:ts namnutrymmesintegrationskod. Identitetskartan kan innehålla mer än en identitet för varje namnutrymme. Mer information om namnutrymmen finns i [den här sidan](../../../segment/get-started-identity.md). | `Email: [{"xdm:id": "123@abc.com"}]` |
| `xdm:profiles.xdm:decisionRequestId` | Det ID som genereras av klienten som kan användas för att unikt identifiera en profilbeslutsbegäran. Detta ID återkommer i svaret och påverkar inte resultatet av beslutet. | `"xdm:decisionRequestId": "0AA00002-0000-1224-c0de-cjf98Csj43"` |
| `xdm:allowDuplicatePropositions` | Det här objektet är kontrollstrukturen för reglerna för borttagning av dubbletter. Det består av en serie flaggor som anger om samma alternativ kan föreslås i en viss dimension. En flagga som är inställd på true innebär att dubbletter tillåts och ska inte tas bort i den kategori som flaggan anger. En flagga som är inställd på false innebär att beslutsmotorn inte ska göra samma förslag över dimensionen och i stället välja nästa bästa alternativ för ett av delbesluten. |
| `xdm:allowDuplicatePropositions.xdm:acrossActivities` | Om värdet är true kan flera beslut tilldelas samma alternativ. | `"xdm:acrossActivities": true` |
| `xdm:allowDuplicatePropositions.xdm:acrossPlacements` | Om värdet är true kan flera placeringar tilldelas samma alternativ. | `"xdm:acrossPlacements": true` |
| `xdm:mergePolicy.xdm:id` | Identifierar den sammanfogningsprincip som styr de data som returneras av tjänsten för profilåtkomst. Om ingen anges i begäran skickas ingen åtkomsttjänst för profiler via Beslutshantering, annars skickas ID:t som tillhandahålls av anroparen. | `"xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"` |
| `xdm:responseFormat` | En uppsättning flaggor som formaterar svarsinnehållet. |
| `xdm:responseFormat.xdm:includeContent` | Ett booleskt värde som, om det anges till `true`, innehåller innehåll i svaret. | `"xdm:includeContent": true` |
| `xdm:responseFormat.xdm:includeMetadata` | Ett objekt som används för att ange vilka ytterligare metadata som returneras. Om den här egenskapen inte inkluderas `xdm:id` och `repo:etag` returneras som standard. | `name` |
| `xdm:responseFormat.xdm:activity` | Den här flaggan identifierar den specifika metadatainformationen som returneras för `xdm:activity`. | `name` |
| `xdm:responseFormat.xdm:option` | Den här flaggan identifierar den specifika metadatainformationen som returneras för `xdm:option`. | `name`, `characteristics` |
| `xdm:responseFormat.xdm:placement` | Den här flaggan identifierar den specifika metadatainformationen som returneras för `xdm:placement`. | `name`, `channel`, `componentType` |

### Svar

Ett lyckat svar returnerar information om ditt förslag, inklusive dess unika `xdm:propositionId`.

```json
{
  "xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8",
  "xdm:propositions": [
    {
      "xdm:activity": {
        "xdm:id": "xcore:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement": {
        "xdm:id": "xcore:placement:ffed0456",
        "repo:etag": 1
      },
      "xdm:options": [
        {
          "xdm:id": "xcore:personalized-option:ccc0111",
          "repo:etag": 3,
          "@type": "https://ns.adobe.com/experience/decisioning/content-component-html-template",
          "xdm:content": "<html>some html</html>"
        },
        {
          "xdm:id": "xcore:personalized-option:ccc0222",
          "repo:etag": 5,
          "@type": "https://ns.adobe.com/experience/decisioning/content-component-html-template",
          "xdm:content": "<html>hello, world</html>",
          "xdm:score": 45.65
        }
      ]
    },
    {
      "xdm:activity": {
        "xdm:id": "xcore:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement": {
        "xdm:id": "xcore:placement:ffed0789",
        "repo:etag": 2
      },
      "xdm:fallback": {
        "xdm:id": "xcore:fallback:ccc0222",
        "repo:etag": 5,
        "@type": "https://ns.adobe.com/experience/decisioning/content-component-imagelink",
        "dc:format": "image/png",
        "xdm:deliveryURL": "https://cdn.adobe.com/content/1445323-1134331.png",
        "xdm:content": "https://www.adobe.com/index2.html"
      }
    }
  ],
  "ode:createDate": 1566497582038
}
```

| Egenskap | Beskrivning | Exempel |
| -------- | ----------- | ------- |
| `xdm:propositionId` | Den unika identifieraren för den förslagsenhet som är associerad med en XDM DecisionEvent. | `"xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8"` |
| `xdm:propositions` | Det här objektet innehåller ett enda beslutsförslag. Flera alternativ kan returneras för beslutet. Om inga alternativ hittas returneras beslutets reserverbjudande. Enstaka beslutsförslag innehåller alltid antingen `options` egenskap eller `fallback` -egenskap. Om det finns en `options` får inte vara tom. |
| `xdm:propositions.xdm:activity` | Det här objektet innehåller den unika identifieraren för ett beslut. | `"xdm:id": "xcore:activity:ffed0123"` |
| `xdm:propositions.xdm:placement` | Det här objektet innehåller den unika identifieraren för en offertplacering. | `"xdm:id": "xcore:placement:ffed0456"` |
| `xdm:propositions.xdm:options` | Det här objektet innehåller ett enda alternativ, inklusive dess unika identifierare. Om det finns kan objektet inte vara tomt. | `xdm:id": "xcore:personalized-option:ccc0111` |
| `xdm:propositions.xdm:options.@type` | Definierar komponenttypen. `@type` fungerar som bearbetningsavtal för kunden. När upplevelsen är sammanställd söker dispositionen efter de komponenter som har en viss typ. | `https://ns.adobe.com/experience/offer-management/content-component-imagelink` |
| `xdm:propositions.xdm:content` | Svarsinnehållets format. | Svarsinnehållet kan vara: `text`, `html block`, eller `image link` |
| `xdm:score` | Poängen för ett alternativ som beräknas som ett resultat av en rangordningsfunktion som är kopplad till alternativet eller beslutet. Detta fält returneras av API:t om en rangordningsfunktion är involverad i att fastställa poängen för ett erbjudande under rangordningen. | `"xdm:score": 45.65` |
| `xdm:propositions.xdm:fallback` | Det här objektet innehåller ett enda reserverbjudande, inklusive dess unika identifierare. | `"xdm:id": "xcore:fallback:ccc0222"` |
| `xdm:propositions.xdm:fallback.dc:format` | Resursens fysiska eller digitala manifestation. Formatet bör vanligtvis innehålla resursens medietyp. Formatet kan användas för att avgöra vilken programvara, maskinvara eller annan utrustning som behövs för att visa eller använda resursen. Vi rekommenderar att du väljer ett värde från ett styrt vokabulär, till exempel listan med [Internetmedietyper](http://www.iana.org/assignments/media-types/) definiera datormedieformat. | `"dc:format": "image/png"` eller `"image/jpeg"` |
| `xdm:propositions.xdm:fallback.xdm:deliveryURL` | En valfri URL för att läsa resursen från ett leveransnätverk eller en tjänstslutpunkt. Den här URL:en används för att komma åt resursen offentligt från en användaragent. | `https://d37yhxrr0p3l3l.cloudfront.net/0fd0f090-a148-11ea-89e3-f1f2ad52f7e8/urn:aaid:sc:US:a68c86a6-9295-4940-a083-11916b665500/0/40d78a12-f8b6-3f07-8e67-7cb8ae2cc7ec` |
| `ode:createDate` | Den tid då beslutssvarsmeddelandet skapades. Detta representeras som epoktid. | `"ode:createDate": 1566497582038` |

**Svarskoder**

Tabellen nedan visar alla koder som kan returneras i svaret:

| Code | Beskrivning |
|  ---  |  ---  |
| 200 | Lyckades. Beslut har fattats om vissa verksamheter |
| 400 | Ogiltig begärandeparameter. Servern kan inte tolka begäran på grund av felaktig syntax. |
| 403 | Otillåten, otillräcklig behörighet. |
| 422 | Enhet som inte kan bearbetas. Syntaxen för begäran är korrekt, men på grund av semantiska fel kan den inte behandlas. |
| 429 | För många förfrågningar. Användaren har skickat för många begäranden under en viss tid. |
| 500 | Internt serverfel. Servern påträffade ett oväntat tillstånd som gjorde att den inte kunde slutföra begäran. |
| 503 | Tjänsten är inte tillgänglig på grund av serveröverbelastning. Servern kan för närvarande inte hantera begäran på grund av en tillfällig överbelastning. |

## Videokurs {#video}

Följande video är avsedd att ge stöd för din förståelse av komponenterna i Beslutshantering.

>[!NOTE]
>
>Den här videon gäller för Offera decisioningens programtjänst som är byggd på Adobe Experience Platform. Det ger dock allmän vägledning om hur man använder Erbjudandet inom ramen för Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329919/?quality=12)

## Nästa steg {#next-steps}

Genom att följa den här API-guiden har du skapat och levererat erbjudanden med [!DNL Decisions] API. Mer information finns i [Översikt över beslutsfattandet](../../../offers/get-started/starting-offer-decisioning.md).
