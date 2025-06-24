---
solution: Journey Optimizer
product: journey optimizer
title: Använd Adobe Experience Platform-data i  [!DNL Journey Optimizer]  (Beta)
description: Lär dig hur du använder Adobe Experience Platform datamängder i [!DNL Journey Optimizer] Funktioner för beslutsfattande och personalisering.
badge: label="Beta" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare
source-git-commit: 7e378cbda6ee2379a8bd795588c328cb14107aa4
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Använd Adobe Experience Platform-data i [!DNL Journey Optimizer] {#aep-data}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande tillgänglig för alla kunder som en betaversion.
>
>Om du vill använda den här funktionen måste du först godkänna betavillkoren för din organisation.

Med Journey Optimizer kan du utnyttja data från Adobe Experience Platform i [!DNL Journey Optimizer]. För att göra detta måste datauppsättningar som behövs för sökpersonalisering först aktiveras via ett API-anrop enligt beskrivningen nedan. När du är klar kan du använda deras data med [!DNL Journey Optimizer]-personalisering och beslutsfunktioner.

## Beta begränsningar och riktlinjer {#guidelines}

Läs följande begränsningar och riktlinjer innan du börjar:

* **Datauppsättningsstorleken** är begränsad till 5 GB för produktionsdatamängder och 1 GB för dev sandbox-datamängder
* **Högst 50 datauppsättningar kan aktiveras** för sökning per organisation när som helst.
* **Antalet poster** är begränsat till 5 miljoner i produktionsdatamängder och 1 MB i dev sandbox-datamängder.
* **Dataanvändningsetiketter och -tvång** används inte för närvarande för datauppsättningar som har aktiverats för sökning.
* **Datauppsättningar som är aktiverade för sökning och används för personalisering är inte skyddade från borttagning**. Det är upp till dig att hålla reda på vilka datauppsättningar som används för personalisering för att säkerställa att de inte tas bort eller tas bort.
* **Dataanvändningsetiketter och -tvång** används inte för närvarande för datauppsättningar som har aktiverats för sökning.

## Aktivera en datauppsättning för datasökning {#enable}

För att kunna utnyttja data från datauppsättningen för personalisering måste du använda ett API-anrop för att hämta dess status och aktivera sökningstjänsten.

### Förhandskrav {#prerequisites-enable}

* Följ anvisningarna i [den här dokumentationen](https://developer.adobe.com/journey-optimizer-apis/references/authentication/) för att konfigurera miljön för att skicka API-kommandon.
* Utvecklarprojektet måste ha Adobe Journey Optimizer- och Adobe Experience Platform-API:erna tillagda i projektet.

  ![](assets/aep-data-api.png)

* Du måste ha behörighet att hantera datauppsättningar som en del av din roll.
* Schemat som datauppsättningen baseras på måste innehålla en **primär identitet** som kan fungera som söknyckeln.

### API-anropsstruktur {#call}

```
curl -s -XPATCH "https://platform.adobe.io/data/core/entity/lookup/dataSets/${DATASET_ID}/${ACTION}" \ -H "Authorization: Bearer ${ACCESS_TOKEN}" \ -H "x-api-key: ${API_KEY}" \ -H "x-gw-ims-org-id: ${IMS_ORG}" \ -H "x-sandbox-name: ${SANDBOX_NAME}"
```

Var:

* **URL** är `https://platform.adobe.io/data/core/entity/lookup/dataSets/${DATASET_ID}/${ACTION}`
* **Datauppsättnings-ID** är den datauppsättning som du vill aktivera.
* **Åtgärd** har aktiverats eller inaktiverats.
* **Åtkomsttoken** kan hämtas från utvecklarkonsolen.
* **API-nyckeln** kan hämtas från utvecklarkonsolen.
* **IMS-organisation** är din Adobe-organisation.
* **Sandlådenamn** är namnet på sandlådan som datauppsättningen finns i (d.v.s. prod, dev.s.).

>[!NOTE]
>
>Om du får ett felmeddelande nedan när du försöker aktivera datauppsättningar kan du försöka ta bort Adobe Journey Optimizer API:er från ditt utvecklarkonsolprojekt och sedan lägga till dem igen.
>
>```
>
>"error_code": "403003", 
>"message": "Api Key is invalid"
>
>```

När en datauppsättning har aktiverats för sökning med ett API-anrop kan du använda dess data med personalisering och beslutsfunktioner för [!DNL Journey Optimizer].

* [Använd Adobe Experience Platform-data för personalisering](../personalization/aep-data-perso.md)
* [Använd Adobe Experience Platform-data för beslut](../experience-decisioning/aep-data-exd.md)
