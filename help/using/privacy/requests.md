---
solution: Journey Optimizer
product: journey optimizer
title: Förfrågningar om användarens information
description: Läs mer om sekretesskrav och Privacy Service.
feature: Privacy
role: User
level: Intermediate
exl-id: 19ec3410-761e-4a9c-a277-f105fc446d7a
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 2%

---

# Förfrågningar om användarens information {#track-changes}

Adobe Experience Platform **Privacy Service** innehåller ett RESTful-API och användargränssnitt som hjälper dig att hantera kunddataförfrågningar. Med Privacy Service kan ni skicka in förfrågningar om åtkomst till och radering av personuppgifter från Adobe Experience Cloud-program, vilket underlättar automatiserad efterlevnad av juridiska och organisatoriska sekretessbestämmelser.

Sekretessförfrågningar kan skapas och hanteras från menyn **[!UICONTROL Requests]**.

![](assets/requests.png)

Mer information om Privacy Service och hur du skapar och hanterar sekretessförfrågningar finns i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=sv){target="_blank"}.

<!--* [Privacy Service overview](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=sv-SE)
* [Managing privacy jobs in the Privacy Service UI](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=sv-SE)-->

## Hantera enskilda dataförfrågningar som du kan skicka till Adobe Journey Optimizer {#data-privacy-requests}

Du kan skicka enskilda förfrågningar om åtkomst till och radering av konsumentdata från Adobe Journey Optimizer på två sätt:

* Via **Privacy Service-gränssnittet**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=sv-SE){target="_blank"}
* Via **Privacy Service API**. [Läs mer](https://experienceleague.adobe.com/sv/docs/experience-platform/privacy/api/overview){target="_blank"}
  <!--More specific information on Privacy Service API [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/#_blank).-->

Privacy Service stöder två typer av förfrågningar: **dataåtkomst** och **dataradering**.

Ange **Adobe Journey Optimizer** från användargränssnittet (eller **CJM** som produktkod i API:t) för **åtkomstbegäranden**.

För **borttagningsbegäranden** måste du, förutom **Adobe Journey Optimizer**-begäran, även skicka borttagningsbegäranden till **tre tjänster i uppströmmen** för att förhindra att Journey Optimizer återställer borttagna data. Om dessa tjänster i det överordnade flödet inte anges kommer Adobe Journey Optimizer-begäran att förbli i tillståndet&quot;bearbetar&quot; tills begäranden om borttagning för de överordnade tjänsterna skapas.

De tre tjänsterna är:

* Profil (produktkod: &quot;profileService&quot;)
* AEP Data Lake (produktkod:&quot;AdobeCloudPlatform&quot;)
* Identitet (produktkod: &quot;identity&quot;)

>[!NOTE]
>
>Den här handboken beskriver bara hur du gör sekretessförfrågningar för [!UICONTROL Adobe Journey Optimizer].
>
>* Om du även planerar att göra sekretessförfrågningar för sjön med plattformsdata kan du läsa den här [handboken](https://experienceleague.adobe.com/sv/docs/experience-platform/catalog/privacy) förutom den här självstudiekursen.
>
>* Kundprofil i realtid finns i den här [guiden](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/privacy).
>* Identitetstjänsten finns i den här [handboken](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/privacy).
>
>Om du vill ta bort eller få åtkomst till en begäran måste du anropa dessa enskilda system för att se till att förfrågningarna hanteras av var och en av dem. En sekretessbegäran till [!DNL Adobe Journey Optimizer] tar inte bort data från alla dessa system.

## Skapa begäranden om åtkomst och borttagning

### Förhandskrav

Om du vill göra en begäran om åtkomst- och borttagningsdata för Adobe Journey Optimizer måste du ha:

* ett Adobe-organisations-ID
* en identitetsidentifierare för den person du vill agera på och motsvarande namnutrymmen. Mer information om identitetsnamnutrymmen i Adobe Journey Optimizer och Experience Platform finns i [översikten över identitetsnamnrymden](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/features/namespaces).

>[!IMPORTANT]
>
>När du skickar sekretessförfrågningar måste du ange [!DNL '**Adobe Journey Optimizer**] som målproduktnamn och **alla identitetsnamnutrymmen** (t.ex. &#39;E-post&#39;, &#39;ECID&#39; eller &#39;Loyalty ID&#39;) som är associerade med profildata som behöver nås eller tas bort. Om du inte uttryckligen tar med produktnamnet och alla tillämpliga namnutrymmen tas data inte bort från [!DNL Adobe Journey Optimizer] för Delete-begäranden.

### Obligatoriska fältvärden i Journey Optimizer för API-begäranden

```json
"companyContexts":
    "namespace": imsOrgID
    "value": <Your Adobe Organization ID Value>

"users":
    "action": either access or delete

    "userIDs":
        "namespace": e.g. email, aaid, ecid, etc.
        "type": standard
        "value": <Data Subject's Identity Identifier>

"include":
    CJM (which is the Adobe product code for Adobe Journey Optimizer)
    profileService (product code for Profile)
    AdobeCloudPlatform (product code for AEP Data Lake)
    identity (product code for Identity)

"regulation":
    gdpr, ccpa, pdpa, lgpd_bra, or nzpa_nzl (which is the privacy regulation that applies to the request)
```


### Exempel på GDPR-åtkomstbegäran:

Från gränssnittet:

![](assets/accessrequest.png){width="60%" align="center"}

Via API:

```json
// JSON Request
{
   "companyContexts":[
      {
         "namespace":"imsOrgID",
         "value":"745F37C35E4B776E0A49421B@AdobeOrg"
      }
   ],
   "users":[
      {
         "action":[
            "access"
         ],
         "userIDs":[
            {
               "namespace":"ecid",
               "value":"38400000-8cf0-11bd-b23e-10b96e40000d",
               "type":"standard"
            },
            {
               "namespace":"email",
               "value":"johndoe4@gmail.com",
               "type":"standard"
            }
         ]
      }
   ],
   "include":[
      "CJM"
   ],
   "regulation":"gdpr"
}
```

```json
// JSON Response
{
    "requestId": "17163122360480365RX-705",
    "totalRecords": 1,
    "jobs": [
        {
            "jobId": "e709b1f4-1796-11ef-b422-eddd0aebc40d",
            "customer": {
                "user": {
                    "key": "John Doe",
                    "action": [
                        "access"
                    ],
                    "userIDs": [
                        {
                            "namespace": "ecid",
                            "value": "38400000-8cf0-11bd-b23e-10b96e40000d",
                            "type": "standard",
                            "namespaceId": 4,
                            "isDeletedClientSide": false
                        },
                        {
                            "namespace": "email",
                            "value": "johndoe4@gmail.com",
                            "type": "standard",
                            "namespaceId": 6,
                            "isDeletedClientSide": false
                        }
                    ]
                }
            }
        }
    ]
}
```

### Exempel på GDPR-borttagningsbegäran:

Från gränssnittet:

![](assets/deleterequest.png){width="60%" align="center"}

Via API:

```json
// JSON Request
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "745F37C35E4B776E0A49421B@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
          "delete"
      ],
      "userIDs": [
        {
          "namespace": "ecid",
          "value": "38400000-8cf0-11bd-b23e-10b96e40000d",
          "type": "standard"
        },
                {
          "namespace": "email",
          "value": "johndoe4@gmail.com",
          "type": "standard"
        }
      ]
    }
  ],
  "include": [
    "CJM", "profileService", "AdobeCloudPlatform", "identity"
  ],
  "regulation": "gdpr"
}
```

```json
// JSON Response
{
    "requestId": "17163122360480365RX-705",
    "totalRecords": 1,
    "jobs": [
        {
            "jobId": "e709b1f4-1796-11ef-b422-eddd0aebc40d",
            "customer": {
                "user": {
                    "key": "John Doe",
                    "action": [
                        "delete"
                    ],
                    "userIDs": [
                        {
                            "namespace": "ecid",
                            "value": "38400000-8cf0-11bd-b23e-10b96e40000d",
                            "type": "standard",
                            "namespaceId": 4,
                            "isDeletedClientSide": false
                        },
                        {
                            "namespace": "email",
                            "value": "johndoe4@gmail.com",
                            "type": "standard",
                            "namespaceId": 6,
                            "isDeletedClientSide": false
                        }
                    ]
                }
            }
        }
    ]
}
```
