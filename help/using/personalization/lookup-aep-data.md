---
solution: Journey Optimizer
product: journey optimizer
title: Använd Adobe Experience Platform-data för personalisering (beta)
description: Lär dig hur du använder Adobe Experience Platform-data för personalisering.
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare
hidefromtoc: true
hide: true
exl-id: 2fc10fdd-ca9e-46f0-94ed-2d7ea4de5baf
source-git-commit: a03541b5f1d9c799c30bf1d38b6f187d94c21dff
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Använd Adobe Experience Platform-data för personalisering (beta) {#aep-data}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande endast tillgänglig som en privat betaversion.
>
>För närvarande är den bara tillgänglig för **e-postkanalen** och för testning i den icke-produktionssandlåda som du har angett för Adobe och för de datauppsättningar som begärts för betaversionen.

Med Journey Optimizer kan du utnyttja data från Adobe Experience Platform i personaliseringsredigeraren för att [anpassa ditt innehåll](../personalization/personalize.md). Stegen är följande:

1. Öppna personaliseringsredigeraren, som är tillgänglig i alla sammanhang där du kan definiera personalisering, till exempel meddelanden. [Lär dig arbeta med personaliseringsredigeraren](../personalization/personalization-build-expressions.md)

1. Navigera till hjälpfunktionslistan och lägg till hjälpfunktionen **datasetLookup** i kodfönstret.

   ![](assets/aep-data-helper.png)

1. Den här funktionen har en fördefinierad syntax som gör att du kan anropa fält från Adobe Experience Platform datamängder. Syntaxen är följande:

   ```
   {{entity.datasetId="datasetId" id="key" result="store"}}
   ```

   * **entity.datasetId** är ID:t för den datauppsättning som du arbetar med.
   * **id** är ID:t för källkolumnen som ska kopplas till den primära identiteten för sökdatauppsättningen.

     >[!NOTE]
     >
     >Det värde som anges för det här fältet kan antingen vara ett fält-ID (*profile.couponValue*), ett fält som skickas i en resthändelse (*context.travel.events.event_ID.couponValue*) eller ett statiskt värde (*couponAbcd*). I vilket fall som helst använder systemet värdet och sökningen i datauppsättningen för att kontrollera om den matchar en nyckel.

   * **result** är ett godtyckligt namn som du måste ange för att kunna referera till alla fältvärden som du kommer att hämta från datauppsättningen. Det här värdet används i koden för att anropa varje fält.

   +++Var hämtar du ett datauppsättnings-ID?

   Datauppsättnings-ID kan hämtas i Adobe Experience Platform användargränssnitt. Lär dig hur du arbetar med datauppsättningar i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#view-datasets){target="_blank"}.

   ![](assets/aep-data-dataset.png)

+++

1. Anpassa syntaxen efter dina behov. I det här exemplet vill vi hämta data om passagerarnas flygningar. Syntaxen är följande:

   ```
   {{entity.datasetId="1234567890abcdtId" id=profile.upcomingFlightId result="flight"}}
   ```

   * Vi arbetar i datauppsättningen med ID:t &quot;1234567890abcdtId&quot;,
   * Fältet som vi vill använda för att skapa en koppling med uppslagsuppsättningen är *profile.upcomingFlightId*,
   * Vi vill inkludera alla fältvärden under &quot;flight&quot;-referensen.

1. När syntaxen som ska anropas i Adobe Experience Platform-datauppsättningen har konfigurerats kan du ange vilka fält du vill hämta. Syntaxen är följande:

   ```
   {{result.fieldId}}
   ```

   * **result** är det värde som du har tilldelat parametern **result** i hjälpfunktionen **MultiEntity**. I det här exemplet &quot;flight&quot;.
   * **fieldID** är ID:t för det fält som du vill hämta. Detta ID visas i Adobe Experience Platform användargränssnitt när du bläddrar bland datauppsättningarna. Expandera avsnittet nedan för att visa ett exempel:

     +++Var ska ett fält-ID hämtas?

     Fält-ID:n kan hämtas när en datauppsättning förhandsgranskas i Adobe Experience Platform användargränssnitt. Lär dig hur du förhandsgranskar datauppsättningar i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide#preview){target="_blank"}.

     ![](assets/aep-data-field.png)

+++

   I det här exemplet vill vi använda information om passagerarnas tid och port för ombordstigning. Därför lägger vi till följande två rader:

   * `{{flight._myorg.booking.boardingTime}}`
   * `{{flight._myorg.booking.gate}}`

1. Nu när koden är klar kan du slutföra innehållet som vanligt och testa det med knappen **Simulera innehåll** för att kontrollera personaliseringen. [Lär dig hur du förhandsgranskar och testar innehåll](../content-management/preview-test.md)


   ![](assets/aep-data-sample.png)
