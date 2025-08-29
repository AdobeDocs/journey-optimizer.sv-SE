---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med resehändelser
description: Lär dig hur du arbetar med händelser under dina resor
feature: Journeys, Events
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate, Experienced
keywords: händelser, händelse, resa, definition, start
exl-id: fb3e51b5-4cbb-4949-8992-1075959da67d
source-git-commit: 461bf985a890d0f2f2723241846df0666248eea0
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 20%

---

# Arbeta med resehändelser {#about-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_event_list"
>title="Reseevenemang"
>abstract="En händelse är länkad till en person. Det gäller en persons beteende (t.ex. en person som köpt en produkt, besökt en butik, lämnat en webbplats) eller något som händer med en person (t.ex. en person som uppnått 10 000 kundpoäng). Journey Optimizer lyssnar på enastående händelser under resor för att samordna de bästa nästa åtgärderna."

Använd händelser för att utlösa resorna individuellt och leverera meddelanden i realtid till varje användare när de går in på resan.

I händelsekonfigurationen konfigurerar du de händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API:er för direktuppspelning av inmatning för autentiserade och oautentiserade händelser (t.ex. Adobe Mobile SDK-händelser). Du kan använda flera händelser (i olika steg på en resa) och flera resor kan använda samma händelse.

Händelsekonfigurationen är **obligatorisk** och måste utföras av en datatekniker.

Du kan konfigurera två typer av händelser: **Unitära händelser** och **Affärshändelser**.


➡️ [Upptäck den här funktionen i en video](#video)

## Enhetshändelser {#unitary-events}

Händelsen **Unitary** är länkad till en person. De rör en persons beteende (t.ex. en person som köpt en produkt, besökt en butik, lämnat en webbplats) eller något som händer med en person (t.ex. en person som uppnått 10 000 förmånspoäng). Det här är vad [!DNL Journey Optimizer] lyssnar på under resor för att samordna de bästa nästa åtgärderna. Enhetshändelser kan vara regelbaserade eller systemgenererade. Mer information om hur du skapar en enhetshändelse finns på [sidan](../event/about-creating.md).

Enhetsresor (som inleds med en händelse eller en publikation) innehåller ett skyddsräcke som förhindrar att resorna aktiveras felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras tillfälligt som standard i 5 minuter. Om en händelse till exempel utlöser en resa vid 12:01 för en viss profil och en annan tar emot vid 12:03 (oavsett om det är samma händelse eller en annan som utlöser samma resa) startar den resan inte igen för den här profilen.

## Affärshändelser {#business-events}

**Business**-händelser är inte länkade till en viss profil. Det kan till exempel vara en nyhetsvarning, en idrottsuppdatering, en flygändring eller inställd flygning, en inventeringsuppdatering, väderhändelser osv. Även om dessa händelser inte är specifika för en profil kan de vara av intresse för ett obegränsat antal profiler: individer som abonnerar på särskilda nyhetsfrågor, passagerare på ett flyg, kunder som är intresserade av en produkt som inte finns i lager osv. Affärshändelser är alltid regelbaserade. När du släpper en affärshändelse under en resa läggs automatiskt en **Läs målgrupp** -aktivitet till efter.Lär dig hur du skapar en affärshändelse [på den här sidan](../event/about-creating-business.md).


## Händelse-ID-typ {#event-id-type}

För **business**-händelser är händelse-ID-typen alltid regelbaserad.

Det finns två typer av händelse-ID för **unitary**-händelser:

* **Regelbaserade** händelser: Den här händelsetypen genererar inget eventID. Med den enkla uttrycksredigeraren definierar du helt enkelt en regel som ska användas av systemet för att identifiera de relevanta händelserna som utlöser dina resor. Den här regeln kan baseras på alla fält som är tillgängliga i händelsenyttolasten, till exempel profilens plats eller antalet objekt som läggs till i profilens kundvagn.

  >[!CAUTION]
  >
  >En begränsningsregel definieras för regelbaserade händelser. Det begränsar antalet kvalificerade händelser som en resa kan bearbeta till 5 000 per sekund för en viss organisation. Det motsvarar Journey Optimizer SLA:er. Se din Journey Optimizer-licens och [Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html).

* **Systemgenererade** händelser: Dessa händelser kräver ett eventID. Det här eventID-fältet genereras automatiskt när händelsen skapas. Systemet som skickar händelsen ska inte generera ett ID utan det ska skicka det som finns i nyttolastförhandsvisningen.

>[!NOTE]
>
>Journey Optimizer kräver att händelser direktuppspelas till datainsamlingens bastjänst (DCCS) för att kunna utlösa en resa. Händelser som är inkapslade i batch eller händelser från interna Journey Optimizer-datauppsättningar (meddelandefeedback, e-postspårning osv.) kan inte användas för att utlösa en resa. Om du inte kan få direktuppspelade händelser ska du skapa en målgrupp baserat på dessa händelser och använda aktiviteten **Läs målgrupp** i stället. Målgruppskvalificering kan tekniskt sett användas, men kan orsaka problem längre fram i kedjan baserat på de åtgärder som används. Dessa data behöver inte nödvändigtvis gå till realtidsprofilen. Om du vill använda händelserna för segmentering rekommenderar vi att du aktiverar datauppsättningen för profilen.

## Datacykel {#data-cycle}

Händelser är POST API-anrop. Händelser skickas till Adobe Experience Platform via API:er för direktuppspelning. URL-destinationen för händelser som skickas via API:er för transaktionsmeddelanden kallas för ett &quot;inlet&quot;. Händelsers nyttolast följer XDM-formateringen.

Nyttolasten innehåller information som krävs för att API:er för direktuppspelning av inmatning ska fungera (i huvudet) och den information som krävs för att [!DNL Journey Optimizer] ska kunna arbeta och information som ska användas på resor (i brödtexten, till exempel, mängden övergiven vagn). Det finns två lägen för strömningsinmatning – autentiserad och ej autentiserad. Se [den här länken](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html){target="_blank"} för mer information om API:er för strömningsinmatning.

Efter att ha kommit via API:er för direktuppspelning av inmatning flödar händelserna till en intern tjänst som kallas Pipeline och sedan i Adobe Experience Platform. Om händelseschemat har tjänstflaggan realtidskundprofil aktiverad och ett datauppsättnings-ID som även har flaggan realtidskundprofil flödar det in i tjänsten realtidskundprofil.

För systemgenererade händelser filtrerar pipelinen händelser som har en nyttolast som innehåller [!DNL Journey Optimizer] eventID:n (se processen för att skapa händelser nedan) som tillhandahålls av [!DNL Journey Optimizer] och ingår i händelsens nyttolast. För regelbaserade händelser identifierar systemet händelsen med eventID-villkoret. [!DNL Journey Optimizer] läser av dessa händelser och motsvarande resa aktiveras.

## Uppdatera och ta bort en händelse {#update-event}


För att undvika att bryta befintliga resor kan du bara ändra namn, beskrivning eller lägga till nyttolastfält när du redigerar en händelse som används i en utkast, live eller stängd resa.

Händelser som används i Live-, Draft- eller Closed-resor kan inte tas bort. Om du vill ta bort en händelse som används måste du stoppa resor som använder den och/eller ta bort den från de utkast till resor där den används. Du kan kontrollera fältet **[!UICONTROL Used in]**. Här visas antalet resor som använder den aktuella händelsen. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa en lista över motsvarande resor.

## Instruktionsfilmer {#video}

Lär dig hur du konfigurerar en händelse, anger slutpunkten för direktuppspelning och nyttolasten för en händelse.

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12)

Förstå tillämpliga användningsexempel för affärshändelser. Lär dig hur du bygger en resa med hjälp av ett affärsevenemang och vilka bästa metoder som ska användas.

>[!VIDEO](https://video.tv.adobe.com/v/334234?quality=12)
