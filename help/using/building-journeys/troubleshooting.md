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
source-git-commit: fa46397b87ae3a81cd016d95afd3e09bb002cfaa
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 42%

---

# Felsök din resa {#troubleshooting}

I det här avsnittet får du lära dig hur du felsöker resor innan du testar eller publicerar. Alla kontroller som anges nedan kan utföras medan resan är i testläge eller när den är live. Rekommendationen är att göra alla kontroller nedan i testläget och sedan gå vidare till publiceringen. Läs mer om testläget på [den här sidan](../building-journeys/testing-the-journey.md).

Som administratör kan du även testa dina anpassade åtgärdskonfigurationer genom att göra riktiga API-anrop direkt från användargränssnittet. Läs mer på [den här sidan](../action/troubleshoot-custom-action.md).

## Kontrollera om det finns fel före testning {#checking-for-errors-before-testing}

Kontrollera att alla aktiviteter är konfigurerade korrekt innan du testar och publicerar din resa. Du kan inte utföra tester eller publikationer om fel fortfarande upptäcks av systemet.


### Fel i aktiviteter {#activity-errors}

Fel visas med en varningssymbol på själva aktiviteterna på arbetsytan. Placera markören på utropstecknet för att visa felmeddelandet. Om du väljer aktiviteten visas raden med en varning. Exempel:

* om ett obligatoriskt fält är tomt visas ett fel

  ![](assets/journey63.png)

* på arbetsytan visas en varning när två aktiviteter är frånkopplade

  ![](assets/canvas-disconnected.png)

### Fel under resan {#canvas-errors}

Fel visas också från knappen **[!UICONTROL Alerts]** ovanför arbetsytan. Med den här knappen kan du se fel som upptäcks av systemet och som förhindrar aktivering av testläget eller publicering av resan.

Systemet identifierar två typer av problem: **fel** och **varningar**. Fel blockerar publicering och testaktivering. Varningar indikerar potentiella problem som inte blockerar testaktivering eller publicering. En beskrivning av problemet och ett ID från felloggen med typen ERR_XXX_XXX visas. Detta kan hjälpa till att identifiera problemet.

![](assets/journey-error-and-warning.png)

<!--Most of the time, errors detected by the system are linked to errors visible on the activities but they can also relate to other issues. In all cases, check alerts and resolve the issue using to the error description. If you cannot identify the issue, use the **[!UICONTROL Copy details]** button to store the alerts, and send them to your administrator.-->

Fel och varningar som är globala för resan visas först i listan. Fel och varningar som rör specifika aktiviteter listas därefter per aktivitetsordning eller när de dyker upp i resan från vänster till höger. Längst ned i listan med varningar kan du med knappen **[!UICONTROL Copy details]** kopiera teknisk information om resan som är användbar för att felsöka problemen.

### Lägg till en alternativ sökväg {#canvas-add-path}

Du kan definiera en reservåtgärd om ett fel uppstår för följande reseaktiviteter: **[!UICONTROL Condition]** och **[!UICONTROL Action]**.

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få det att fortsätta är att lösa problemet. För att undvika att avbryta resan kan du även kontrollera alternativet **[!UICONTROL Add an alternative path in case of a timeout or an error]** i aktivitetens egenskaper. Läs mer i [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).


## Kontrollera att händelser skickas korrekt {#checking-that-events-are-properly-sent}

Startpunkten för en resa är alltid en händelse. Du kan utföra tester med verktyg som Postman.

Du kan kontrollera om API-anropet som skickas via dessa verktyg skickas korrekt eller inte. Om du får tillbaka ett fel innebär det att ditt anrop har ett problem. Kontrollera nyttolasten igen, rubriken (och särskilt ditt organisations-ID) och destinationswebbadressen. Du kan fråga administratören om vilken webbadress som ska användas.

Händelser skjuts inte direkt från källan till resor. Resorna förlitar sig faktiskt på Adobe Experience Platform API:er för direktuppspelning. Om det gäller händelserelaterade problem kan du därför läsa [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=sv-SE){target="_blank"} för felsökning av API:er för direktuppspelning.

Om din resa inte kan aktivera testläge med felet `ERR_MODEL_RULES_16` kontrollerar du att händelsen som används innehåller ett [identitetsnamnutrymme](../audience/get-started-identity.md) när du använder en kanalåtgärd.

Identitetsnamnutrymmet används för att unikt identifiera testprofilerna. Om e-post till exempel används för att identifiera testprofilerna bör identitetsnamnområdet **E-post** markeras. Om den unika identifieraren är telefonnumret bör identitetsnamnområdet **Telefon** väljas.

## Kontrollera om personer kommer in på resan {#checking-if-people-enter-the-journey}

Reserapporter mäter människors inträde på en resa i realtid.

Om du lyckas skicka evenemanget men inte ser något inträde på resan innebär det att något går fel mellan det skickade evenemanget och det mottagande evenemanget under resan.

Du kan börja felsöka med frågorna nedan:

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

## Kontrollera hur människor navigerar genom resan {#checking-how-people-navigate-through-the-journey}

Reserapportering mäter enskilda personers framsteg inom en resa. Det är enkelt att identifiera var och varför en person stoppats.

Här följer några saker att kontrollera:

* Är det på grund av ett tillstånd som utesluter personen i fråga? Villkoret kan till exempel vara &quot;kön = man&quot; och personen är en kvinna. Den här kontrollen kan utföras av en företagsanvändare om villkoret inte är för komplext.
* Är orsaken att ett anrop till en datakälla inte svarar? När resan är i testläge kan denna information visas i testlägets loggar. När resan är live kan en administratör testa direktanrop till datakällan och kontrollera svaret som tas emot. En administratör kan även göra dubbletter av resan och testa den.

## Kontrollera att meddelanden har skickats {#checking-that-messages-are-sent-successfully}

Om enskilda personer flödar rätt väg på resan men inte får meddelanden som de ska ta emot, kan du kontrollera om:

* [!DNL Journey Optimizer] har tagit hänsyn till begäran om att skicka meddelandet. Affärsanvändare kan komma åt meddelandet som ska skickas och kontrollera om tidpunkten för den senaste körningen motsvarar körningstiden för din resa. De kan även kontrollera de senaste API-anropen/händelserna som tagits emot.
* [!DNL Journey Optimizer] har skickat meddelandet. Kontrollera reserapporteringen för att se till att det inte finns några fel.

Om ett meddelande skickas via en anpassad åtgärd är det enda som kan kontrolleras under resan att anropet till den anpassade åtgärdens system leder till ett fel eller inte. Om anropet till det externa system som är kopplat till den anpassade åtgärden inte leder till ett fel, men inte leder till att ett meddelande skickas, bör vissa undersökningar utföras på den externa datorns sida.
