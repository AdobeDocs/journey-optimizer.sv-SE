---
solution: Journey Optimizer
product: journey optimizer
title: Felsökning av resor
description: Lär dig hur du felsöker fel under resor
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: felsökning, felsökning, resa, kontroll, fel
exl-id: 03fbc4f4-b0a8-46d5-91f9-620685b11493
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 80%

---

# Felsök din resa{#troubleshooting}

I det här avsnittet lär du dig att felsöka resor innan de testas eller publiceras. Alla kontroller som anges nedan kan utföras medan resan är i testläge eller när den är live. Rekommendationen är att göra alla kontroller nedan i testläget och sedan gå vidare till publiceringen. Läs [den här sidan](../building-journeys/testing-the-journey.md).

## Kontrollera om det finns fel före testning{#checking-for-errors-before-testing}

Kontrollera att alla aktiviteter är konfigurerade korrekt innan du testar och publicerar din resa. Du kan inte utföra tester eller publikationer om fel fortfarande upptäcks av systemet.

Fel visas med en varningssymbol på själva aktiviteterna på arbetsytan. Placera markören på utropstecknet för att visa felmeddelandet. Klicka på aktiviteten för att se raden i felet med en varning. Om till exempel ett obligatoriskt fält är tomt visas ett fel.

![](assets/journey63.png)

Om till exempel två aktiviteter inte är kopplade visas en varning på arbetsytan.

![](assets/canvas-disconnected.png)

Bredvid växlingsknappen **[!UICONTROL Test]** och knappen **[!UICONTROL Publish]** kan ett varningstecken visas. Det här varningstecknet visar fel som upptäckts av systemet och förhindrar aktivering av testläget eller publicering av resan. Vanligtvis är fel som upptäcks av systemet länkade till fel som visas i aktiviteterna. Ibland är de dock länkade till andra problem. I det här fallet kan du visa dem och försöka identifiera problemet med hjälp av felbeskrivningen. Om du inte kan identifiera problemet kan du kopiera informationen och skicka den till administratören eller till supporten. Observera att fel som blockerar testet och publikationen är snarlika.

Systemet upptäcker två typer av problem – fel och varningar. Fel blockerar publicering och testaktivering. Varningar indikerar potentiella problem som inte blockerar testaktivering eller publicering. En beskrivning av problemet och ett ID från felloggen med typen ERR_XXX_XXX visas. Detta hjälper teknisk support att identifiera problemet.

Två olika färger kan visas på tecknet bredvid växlingsknappen **[!UICONTROL Test]** och knappen **[!UICONTROL Publish]**. Vid fel visas tecknet i rött. Vid varningar visas tecknet i orange.

![](assets/journey75.png)

Fel och varningar som är globala för resan visas först i listan. Fel och varningar som rör specifika aktiviteter listas därefter per aktivitetsordning eller när de dyker upp i resan från vänster till höger. Med knappen **[!UICONTROL Copy details]** kopieras teknisk information om resan som supportteamet kan använda för att felsöka.

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få den att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).

## Kontrollera att händelser skickas korrekt{#checking-that-events-are-properly-sent}

Startpunkten för en resa är alltid en händelse. Du kan utföra tester med verktyg som Postman.

Du kan kontrollera om API-anropet som skickas via dessa verktyg skickas korrekt eller inte. Om du får tillbaka ett fel innebär det att ditt anrop har ett problem. Kontrollera nyttolasten igen, rubriken (och särskilt ditt organisations-ID) och destinationswebbadressen. Du kan fråga administratören om vilken webbadress som ska användas.

Händelser skjuts inte direkt från källan till resor. Resorna är beroende av Adobe Experience Platform API:er för direktuppspelning. Om det gäller händelserelaterade problem kan du därför hänvisa till [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html){target="_blank"} för felsökning av API:er för direktuppspelning.

## Kontrollera om personer kommer in på resan{#checking-if-people-enter-the-journey}

Reserapporter mäter människors inträde på en resa i realtid.

Om händelsen skickas men inte har inträde i resan betyder det att något gått fel mellan den skickade händelsen och den mottagna händelsen i resan.

Här följer några saker som administratören bör kontrollera:

* Är du säker på att resan, där du förväntar dig att den inkommande händelsen ska vara, är i testläge eller live?
* Sparade du händelsen innan du kopierade nyttolasten från dess förhandsvisning?
* Innehåller händelsens nyttolast ett händelse-ID?
* Angav du rätt URL?
* Har du följt nyttolastens struktur gällande API:er för strömningsinmatning med hjälp av förhandsgranskningen av nyttolastens struktur i händelsens konfigurationsfönster? Läs [den här sidan](../event/about-creating.md#preview-the-payload).
* Använde du rätt nyckelvärdepar i huvudet på din händelse?

  ```
  X-gw-ims-org-id - your organization's ID
  Content-type - application/json
  ```

## Kontrollera hur människor navigerar genom resan{#checking-how-people-navigate-through-the-journey}

Reserapportering mäter enskilda personers framsteg inom en resa. Det är enkelt att identifiera var och varför en person stoppats.

Här följer några saker att kontrollera:

* Är det på grund av ett tillstånd som utesluter personen i fråga? Villkoret kan till exempel vara &quot;kön = man&quot; och personen är en kvinna. Den här kontrollen kan utföras av en företagsanvändare om villkoret inte är för komplext.
* Är orsaken att ett anrop till en datakälla inte svarar? När resan är i testläge kan denna information visas i testlägets loggar. När resan är live kan en administratör testa direktanrop till datakällan och kontrollera svaret som tas emot. En administratör kan även göra dubbletter av resan och testa den.

## Kontrollera att meddelanden har skickats{#checking-that-messages-are-sent-successfully}

Om enskilda personer flödar rätt väg i resan, men inte får meddelanden som de bör få, kan du kontrollera om:

* [!DNL Journey Optimizer] har tagit hänsyn till begäran om att skicka meddelandet. Affärsanvändare kan komma åt meddelandet som ska skickas och kontrollera om tidpunkten för den senaste körningen motsvarar körningstiden för din resa. De kan även kontrollera de senaste API-anropen/händelserna som tagits emot.
* [!DNL Journey Optimizer] har skickat meddelandet. Kontrollera reserapporteringen för att se till att det inte finns några fel.

Om ett meddelande skickas via en anpassad åtgärd är det enda som kan kontrolleras i resan det faktum att anropet till den anpassade åtgärdens system leder till ett fel eller inte. Det kan hända att anropet till det externa system som är kopplat till den anpassade åtgärden inte leder till ett fel men inte heller leder till att ett meddelande skickas. I dessa fall bör undersökningar utföras på det externa systemet.
