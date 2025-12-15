---
solution: Journey Optimizer
product: journey optimizer
title: Granska och aktivera en kampanj
description: Lär dig granska och aktivera kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Intermediate
keywords: kampanj, granskning, validering, aktivering, aktivering, optimering
exl-id: 86f35987-f0b7-406e-9ae6-0e4a2e651610
source-git-commit: a5d8f10c8751d6be47f5423aea576e16590b86d6
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---


# Kör en API-utlöst kampanj {#execute}

När kampanjen har aktiverats måste du hämta den genererade cURL-exempelbegäran och använda den i API:t för att skapa din nyttolast och utlösa kampanjen.

## Måste läsas {#must-read}

* **Kampanjens start-/slutdatum** - Om du har konfigurerat ett specifikt start- och/eller slutdatum när du skapar kampanjen kommer den inte att köras utanför dessa datum och API-anrop misslyckas.

* **Tidsgräns för anrop** - Anropet till REST API:t för interaktiv meddelandekörning har en tidsgräns på 60 sekunder. Det finns dock interna försök om det skulle uppstå oväntade tidsgränser för att garantera leveransen.

## Utlös kampanjen {#trigger}

1. Öppna kampanjen och kopiera och klistra sedan in nyttolastbegäran från avsnittet **[!UICONTROL cURL request]**. Den här nyttolasten innehåller alla personaliseringsvariabler (profil och kontext) som används i meddelandet. Den blir tillgänglig när kampanjen är live.

   ![](assets/api-triggered-curl.png)

   >[!IMPORTANT]
   >
   >Slutpunkterna i cURL-avsnittet skiljer sig åt mellan standardkampanjer och [kampanjer med hög genomströmning](../campaigns/api-triggered-high-throughput.md).

1. Använd denna cURL-begäran i API:erna för att bygga upp din nyttolast och utlösa kampanjen. Mer information finns i [API-dokumentationen för interaktiv meddelandekörning](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution), där alla slutpunkter för standard- och högflödeskampanjer listas.

   Exempel på API-anrop finns också på [den här sidan](https://developer.adobe.com/journey-optimizer-apis/references/messaging-samples/).

## Felsökning {#troubleshooting}

### Fördröjningar för e-postleverans {#delivery-delays}

Om leveranstiden för e-post överstiger förväntningarna bör du undersöka potentiella avbrott eller prestandaproblem med externa tjänster, som leverantörer av molninfrastruktur eller e-postleverantörer. Journey Optimizer loggar in tidsstämplar för avsändning av postmeddelanden, som kan hjälpa till att avgöra om förseningar inträffar längre fram i leveransflödet.

### Azure Cosmos DB-autentiseringsfel (500 internt serverfel) {#cosmosdb-auth-errors}

Om **500 interna serverfel** inträffar när API-utlösta kampanjer utlöses och systemloggarna visar ett **403 Forbidden** -fel från Azure Cosmos DB med ett meddelande som:

_&quot;Åtkomsten till ditt konto har återkallats eftersom Azure Cosmos DB-tjänsten inte kan hämta AAD-autentiseringstoken för kontots standardidentitet&quot;_

Det här felet inträffar vanligtvis när Azure-tjänstens huvudnamn som krävs för Cosmos DB-autentisering har inaktiverats, tagits bort eller felkonfigurerats.

+++Så här löser du det här problemet

1. **Verifiera din Azure-tjänstens huvudnamn** - Kontrollera att din Azure-tjänstens huvudnamn eller hanterade identitet är aktiverad och inte har inaktiverats eller tagits bort i din Azure Active Directory.

1. **Kontrollera behörigheter** - Bekräfta att tjänstens huvudnamn har de behörigheter som krävs för att komma åt Azure Key Vault- och Cosmos-databasresurserna. Tjänstens huvudnamn måste ha lämpliga rolltilldelningar för att kunna autentisera med Azure Cosmos DB.

1. **Granska Azure Cosmos DB CMK-konfiguration** - Om du använder kundhanterade nycklar (CMK) kan du läsa [felsökningsguiden för Azure Cosmos DB CMK](https://learn.microsoft.com/en-us/azure/cosmos-db/cmk-troubleshooting-guide#azure-active-directory-token-acquisition-error){target="_blank"} för att få mer information om hur du återställer AAD-tokenvärvet.

1. **Återaktivera och testa** - När konfigurationen har korrigerats aktiverar du tjänstens huvudnamn om det inaktiverades och testar om dina API-anrop för transaktionskampanj för att bekräfta att autentiseringen lyckades och att meddelanden levererades.

>[!NOTE]
>
>Problemet orsakas vanligtvis av en felkonfiguration eller oavsiktlig inaktivering av det Azure-tjänsthuvudkonto som krävs för Cosmos DB-autentisering. Om tjänstens huvudnamn är aktiverat och korrekt konfigurerat kommer detta fel inte att uppstå i framtiden.

+++
