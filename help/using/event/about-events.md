---
title: Om händelser
description: Läs mer om evenemang
feature: Händelser
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: a25264cb43f77671c29f18522110fd85d0155697
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 48%

---

# Om händelser{#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Om händelser"
>abstract="En händelse är länkad till en person. Den är relaterad till en persons beteende (till exempel om en person köpt en produkt, besökt en butik eller lämnat en webbplats) eller något som händer relaterat till en person (en person som till exempel har nått 10 000 lojalitetspoäng). Detta är vad [!DNL Journey Optimizer] läser av i resor för att orkestrera bästa åtgärder."

Med händelsekonfigurationen kan du definiera vilken information som [!DNL Journey Optimizer] ska tas emot som händelser. Du kan använda flera händelser (i olika steg på en resa) och flera resor kan använda samma händelse.

>[!CAUTION]
>
>Händelsekonfigurationen är **obligatorisk** och måste utföras av en **teknisk användare**.

Du kan konfigurera två typer av händelser:

* **Unitaryevents:**  dessa händelser är kopplade till en person. De rör en persons beteende (t.ex. en person som köpt en produkt, besökt en butik, lämnat en webbplats) eller något som händer relaterat till en person (en person som till exempel har nått 10 000 lojalitetspoäng). Detta är vad [!DNL Journey Optimizer] läser av i resor för att orkestrera bästa åtgärder. Enhetshändelser kan vara regelbaserade eller systemgenererade. Mer information om hur du skapar en enhetshändelse finns på den här [sidan](../event/about-creating.md).

* **** Företag: en affärshändelse är en händelse som, i motsats till en enhetshändelse, inte är kopplad till en viss profil. Det kan till exempel vara en nyhetsvarning, en idrottsuppdatering, en flygändring eller inställd flygning, en inventeringsuppdatering, väderhändelser osv. Även om dessa händelser inte är specifika för en profil kan de vara av intresse för ett valfritt antal profiler: enskilda abonnerar på särskilda nyhetsämnen, flygpassagerare, kunder som är intresserade av en produkt som inte finns i lager osv. Affärshändelser är alltid regelbaserade. När du släpper en affärshändelse under en resa läggs automatiskt en **Läs segment**-aktivitet till direkt efter. Mer information om hur du skapar en affärshändelse finns på den här [sidan](../event/about-creating-business.md).


>[!NOTE]
>
>Om du redigerar en händelse som används i ett utkast eller en resa i realtid kan du bara ändra namn eller beskrivning eller lägga till fält för nyttolast. Vi begränsar strikt utgåvan av utkast eller resor i realtid för att undvika att resor avbryts.

## Händelse-ID-typ{#event-id-type}

För affärshändelser är händelse-ID-typen alltid regelbaserad.

För unitära händelser finns det två typer av händelse-ID:

* **Regelbaserade** händelser: Den här händelsetypen genererar inget eventID. Med den enkla uttrycksredigeraren definierar du helt enkelt en regel som ska användas av systemet för att identifiera de relevanta händelserna som utlöser dina resor. Den här regeln kan baseras på alla fält som är tillgängliga i händelsenyttolasten, till exempel profilens plats eller antalet objekt som läggs till i profilens kundvagn.

   >[!CAUTION]
   >
   >En begränsningsregel definieras för regelbaserade händelser. Det begränsar antalet kvalificerade händelser som en resa kan behandla till 5 000 per sekund för en viss organisation (ORG). Det motsvarar Journey Optimizer SLA. Läs den här [sidan](https://helpx.adobe.com/se/legal/product-descriptions/journey-orchestration.html).

* **Systemgenererade** händelser: Dessa händelser kräver ett eventID. Det här eventID-fältet genereras automatiskt när händelsen skapas. Systemet som skickar händelsen ska inte generera ett ID utan det ska skicka det som finns i nyttolastförhandsvisningen.

Journey Optimizer kräver att händelser direktuppspelas eller grupperas i Adobe Experience Platform. Dessa data behöver inte nödvändigtvis gå till realtidsprofilen. Om du vill använda händelserna för segmentering eller sökning i en separat resa rekommenderar vi att du aktiverar datauppsättningen för profil.

## Datacykel {#section_r1f_xqt_pgb}

Händelser är POST API-anrop. Händelser skickas till Adobe Experience Platform via API:er för direktuppspelning. URL-destinationen för händelser som skickas via API:er för transaktionsmeddelanden kallas för ett &quot;inlet&quot;. Händelsers nyttolast följer XDM-formateringen.

Nyttolasten innehåller den information som krävs för att Streaming Ingakes API:er ska fungera (i huvudet) och den information som krävs för att [!DNL Journey Optimizer] ska kunna arbeta och information som ska användas på resor (i brödtexten, till exempel mängden en övergiven vagn). Det finns två lägen för strömningsinmatning – autentiserad och ej autentiserad. Se [den här länken](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) för mer information om API:er för strömningsinmatning.

Efter att ha anlänt via API:er för direktuppspelning av inmatning flödar händelserna till en intern tjänst som kallas Pipeline och sedan i Adobe Experience Platform. Om händelseschemat har tjänstflaggan realtidskundprofil aktiverad och ett datauppsättnings-ID som även har flaggan realtidskundprofil flödar det in i tjänsten realtidskundprofil.

För systemgenererade händelser filtrerar pipelinen händelser som har en nyttolast som innehåller [!DNL Journey Optimizer] händelse-ID:n (se processen för att skapa händelsen nedan) som tillhandahålls av [!DNL Journey Optimizer] och som ingår i händelsens nyttolast. För regelbaserade händelser identifierar systemet händelsen med eventID-villkoret. [!DNL Journey Optimizer] läser av dessa händelser och motsvarande resa aktiveras.
