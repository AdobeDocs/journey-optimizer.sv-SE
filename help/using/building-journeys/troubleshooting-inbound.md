---
solution: Journey Optimizer
product: journey optimizer
title: Felsökningsguide för inkommande åtgärder under resor
description: Lär dig hur du felsöker och löser problem med inkommande åtgärder på resor Adobe Journey Optimizer
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: inkommande åtgärder, felsökning, resa, felsökning, självhjälp, kontroll, fel
source-git-commit: e3780d52960b7fbe5ada33cf4de65d22b15e7d1d
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 0%

---


# Felsöka inkommande åtgärder under resor {#troubleshooting-inbound-actions}

Inkommande åtgärder, som upplevelser i appen, på webben och i kodbaserade upplevelser, är viktiga komponenter i [!DNL Journey Optimizer] eftersom de möjliggör personaliserat engagemang med användare under deras resa. Oväntade beteenden kan dock inträffa, t.ex. att inkommande innehåll saknas eller att en profil fortsätter att levereras efter att den har avslutats.

Den här guiden innehåller en stegvis process för att felsöka problem som rör inkommande åtgärder under en resa, så att du kan identifiera och lösa dem oberoende av varandra innan du når ut till supporten.

<!--This guide addresses the two most common scenarios with inbound actions in a journey. They are as follows:

* A profile enters the inbound step, but the user does not receive the expected inbound content.
* A user continues to receive inbound content even after the profile exits the journey.

## Benefits {#benefits}

- Faster issue resolution through self-help.
- Reduced dependency on support teams.
- Improved understanding of inbound action functionality.
- Enhanced customer experience and confidence in using AJO.-->

## Förhandskrav {#prerequisites}

Innan du kan starta felsökningen bör du kontrollera följande:

1. Konfigurera en **Assurance**-session. Läs mer i [Adobe Experience Platform Assurance-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"}.

1. Navigera till resan som innehåller den inkommande åtgärden för att hämta resenamnet och versions-ID:t.

   >[!NOTE]
   >
   >ID för reseversion finns i URL:en efter *resa/* (till exempel: *86232fb1-2932-4036-8198-55dfec606fd7*).

   ![](assets/troubleshoot-inbound-retrieve-journey-id.png)

1. Klicka på den inkommande åtgärden för att visa information om den. Hämta etiketten och ID för den inkommande åtgärden.

   ![](assets/troubleshoot-inbound-retrieve-action-id.png)

1. Hämta profilens namnutrymme och ID för att identifiera problem med profilen som påträffas. Beroende på din konfiguration kan namnutrymmet vara till exempel ECID, e-post eller kund-ID. Lär dig hur du söker efter en profil i [Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/profile/ui/user-guide#browse-identity){target="_blank"}.

## Scenario 1: Användaren har inte fått det inkommande innehållet {#scenario-1}

I det här scenariot har en profil påbörjat den inkommande åtgärden under resan, men även efter 30 minuter visas inte motsvarande inkommande innehåll i enheten/klienten vid konfigurationsstartssteget.


### Förkontroller {#pre-checks}

1. **Inkommande data för resa har aktiverats för profilinmatning**

   Den inkommande åtgärden använder datamängden **Inbound** för inkommande trafik för profiluppdateringarna under körningen. Kontrollera att datauppsättningen är aktiverad för profiler i den aktuella sandlådan. [Läs mer om datauppsättningar](../data/get-started-datasets.md)

2. **&#39;joai&#39;-identitet har definierats i plattformsidentiteter**

   Den inkommande åtgärden använder namnutrymmet **(**) i profilen `segmentMembership` för att aktivera profilen för det inkommande steget. Kontrollera att den har definierats i Plattformsidentiteter för sandlådan. Läs mer om [Experience Platform identitetstjänst](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home){target="_blank"}

### Felsökningssteg {#debugging-steps}

Tabellen nedan visar den sekvens av felsökningssteg som du kan följa:

![](assets/troubleshoot-inbound-scenario-1-steps.png){width="70%" align="center"}

### Steg 1: Kontrollera om enheten/klienten tar emot innehållet från Edge Network {#step-1}

Börja med att kontrollera om enheten/klienten hämtar det förväntade innehållet.

>[!BEGINTABS]

>[!TAB Kanal i appen]

1. Gå till [Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"}-sessionen och välj avsnittet **[!UICONTROL In-App Messaging]** i den vänstra panelen.

1. Klicka på listrutan **[!UICONTROL Messages]** på fliken **[!UICONTROL Messages on Device]** och sök efter ett meddelande med resenamnet följt av meddelandet - i appen. Om det finns något betyder det att meddelandet i appen finns på enheten/klienten och problemet kan vara relaterat till utlösaren i appen.

1. Om meddelandet inte hittas togs meddelandet inte emot av enheten/klienten. Gå till [nästa steg](#step-2) för ytterligare felsökning.

>[!TAB Webbkanal]

Gå till sidan och kontrollera nätverksfliken eller kontrollera Edge svarsnyttolast i avsnittet **[!UICONTROL Edge Delivery]** i [Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"} -sessionen.

>[!TAB Kodbaserad upplevelsekanal]

Utför en begäran med [Adobe API](https://developer.adobe.com/data-collection-apis/docs/api/) och kontrollera Edge svarsnyttolast i avsnittet **[!UICONTROL Edge Delivery]** i [Assurance](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/tutorials/using-assurance){target="_blank"} -sessionen.

>[!ENDTABS]

#### Steg 2: Kontrollera om Edge Network returnerar innehållet {#step-2}

Det här steget är att se till att Edge Network returnerar förväntat inkommande innehåll som ska återges på enheten/klienten.

När en profil anger en inkommande åtgärd för en resa kvalificeras den automatiskt till ett särskilt målgruppssegment (i namnutrymmet **joai**) som motsvarar åtgärden för inkommande resa.

När en klient skickar en begäran till Edge Network för en viss profil och yta kvalificerar sig profilen för att ta emot innehåll för åtgärder för inkommande trafik som riktas mot den ytan endast om profilen för närvarande är medlem i motsvarande **joai** -segment.

Följ stegen nedan för att felsöka Edge Network-beteendet.

1. Öppna vyn **[!UICONTROL Edge Delivery]** i Assurance-sessionen. Den här vyn innehåller information om hur den inkommande åtgärden körs på Edge Network-servern. Läs mer i [Experience Platform-dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}.

   <!--![](assets/troubleshoot-inbound-scenario-1-edge-delivery.png)-->

1. Kontrollera om den Edge-aktivitet som motsvarar den inkommande åtgärden finns i avsnitten **[!UICONTROL Qualified Activities]** eller **[!UICONTROL Unqualified Activities]**:

   * Om den profil som är kvalificerad för åtgärden för inkommande resa finns i avsnittet **Kvalificerade aktiviteter**, och innehållet ska returneras.
   * Om profilen finns i avsnittet **Okvalificerade aktiviteter** kvalificerades den inte för åtgärden för inkommande resa. Mer information finns i skälen till uteslutningen.
   * Om det inte finns något avsnitt i **inget av dem** uppstod antingen ett problem med att publicera åtgärden för inkommande trafik till Edge Network, eller så matchade URI:n för begärd yta inte kanalkonfigurationsinställningarna för den inkommande åtgärden.

   >[!NOTE]
   >
   >Om du vill hitta din Edge-aktivitet i **Assurance** -sessionen söker du efter aktiviteten där **[!UICONTROL audienceNamespace]** är **joai** och **[!UICONTROL audienceSegmentId]** är `<JourneyVersionID>_<JourneyAction ID>` (till exempel: *86232fb1-2932-4036-8198-55dfec606fc d7_708f718d-8503-4427-ad8d-8e28979b554c*).

1. Om din aktivitet finns i avsnittet **[!UICONTROL Unqualified Activities]** och exkluderingsorsaken är *&#39;Segment är inte aktivt&#39;*, betyder det att Edge Network leveransserver inte tror att profilen är en del av det relevanta **joai**-målgruppssegmentet.

   Du kan dubbelkontrollera om **joai** -segmentet finns i Edge Network-leveransserverns vy över profilen genom att öppna **segmentsMap** -elementet i profilavsnittet och leta efter om **joai** -segmentets ID finns.

1. Om Edge Network-leveransservern inte kan se profilen som i det relevanta **joai**-segmentet går du till nästa steg.<!--use the Platform Profile viewer UI to check if the expected **joai** segment is in a realized state in the Edge profile. Learn more in the [Experience Platform Profile UI documentation](https://experienceleague.adobe.com/en/docs/experience-platform/profile/ui/user-guide){target="_blank"}-->

#### Steg 3: Kontrollera om medlemskapet har spridits till Edge Network {#step-3}

Det här steget är att verifiera att Edge-profilen uppdaterades korrekt när profilen angavs i den inkommande reseåtgärden och profilen kvalificerades i motsvarande **joai**-segment.

När en profil är kvalificerad i ett **joai**-segment uppdateras profilen först på hubben och sedan projiceras segmentmedlemskapet för Edge-profilen för användning av Edge Network leveransserver.

>[!NOTE]
>
>Spridningen från Hub till Edge kan ta upp till 15-30 minuter från det att profilen uppdateras på hubben.

Följ stegen nedan för att kontrollera om **joai**-segmentet finns i Edge-profilens `segmentMembership` -attribut.

1. Navigera till menyn **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** i den vänstra navigeringsrutan i [!DNL Journey Optimizer] och bläddra till profilen med namnutrymme och ID. Läs mer om [Kundprofiler i realtid](../audience/get-started-profiles.md)

1. Välj fliken **[!UICONTROL Attributes]** och välj vyn **[!UICONTROL Edge]**.
   <!--cannot see Hub/Edge wiews for the profile-->

1. Klicka på **[!UICONTROL View JSON]** för att öppna JSON-vyn för profilen.

   ![](assets/troubleshoot-inbound-profile-view-json.png)

1. Gå till attributet **[!UICONTROL segmentMembership]** och kontrollera om segment-ID:t `<JourneyVersionID>_<ActionID>` finns i namnutrymmet **joai** och om det är i statusen **[!UICONTROL realized]** <!--or existing?-->.

   ![](assets/troubleshoot-inbound-profile-json-realized.png)

   * Om den finns betyder det att det **joai** -segment som motsvarar åtgärden för inkommande trafik spreds korrekt till Edge-profilen.

   * Om den inte visas i vyn för Edge Network-leveransservern kan det bero på ett problem med hur leveransservern läser in Edge-profilen.

1. Om segment-ID:t **joai** inte finns eller om det är i läget **[!UICONTROL exited]** betyder det att det inte har spridits till Edge (än). Vänta 15 till 30 minuter tills `segmentMembership`-värdena sprids från hubben till Edge.

<!--The next step is to check whether the audience segment is present in the profile on the Hub.-->

#### Steg 4: Kontrollera om det finns ett medlemskap för joai-målgruppen i profilen på navet {#step-4}

Det här steget är att verifiera att hubbprofilen uppdaterades korrekt när profilen angavs i åtgärden för inkommande resa och profilen kvalificerades i motsvarande **joai**-segment.

>[!NOTE]
>
>Inmatningen av **joai**-segmentmedlemskapet i hubbprofilen kan ta upp till 15-30 minuter från det att profilen angav åtgärden för inkommande resa.

Följ stegen nedan för att kontrollera om **joai**-segmentet finns i navprofilens `segmentMembership` -attribut.

1. Navigera till menyn **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** i den vänstra navigeringsrutan i [!DNL Journey Optimizer] och bläddra till profilen med namnutrymme och ID. Läs mer om [Kundprofiler i realtid](../audience/get-started-profiles.md)

1. Välj fliken **[!UICONTROL Attributes]** och välj vyn **[!UICONTROL Hub]**.
   <!--cannot see Hub/Edge wiews for the profile-->

1. Klicka på **[!UICONTROL View JSON]** för att öppna JSON-vyn för profilen.

1. Gå till attributet **[!UICONTROL segmentMembership]** och kontrollera om segment-ID:t `<JourneyVersionID>_<ActionID>` finns i namnutrymmet **joai** och om det är i statusen **[!UICONTROL realized]** <!--or existing?-->.

   * Om det finns betyder det att det **joai**-segment som motsvarar åtgärden för inkommande resa är korrekt inkapslat i hubbprofilen.

   * Om den inte hittas i Edge-profilen efter minst 30 minuter kan det bero på ett problem med Edge projektionssystem.

1. Om segment-ID:t **joai** inte finns eller om det är i läget **[!UICONTROL exited]** betyder det att profilen inte (ännu) har kvalificerats korrekt till det speciella **joai** -målgruppssegmentet vid inträde i motsvarande inkommande reseåtgärd.

   >[!NOTE]
   >
   >Kom ihåg att det kan ta upp till 15-30 minuter innan värdena `segmentMembership` hämtas till profilen på hubben.

#### Steg 5: Om klienten/enheten fortfarande inte får det förväntade innehållet {#step-5}

Om du har gått igenom alla steg ovan och inte ser det förväntade beteendet efter att ha väntat i 30 till 60 minuter på att segmentmedlemskapet ska sprida sig till Edge Network kontaktar du Adobe kundtjänst eller din Adobe-representant.

Inkludera så mycket information du kan från felsökningsstegen, till exempel:

* det steg där du ser det oväntade beteendet,
* ID för reseversion.
* ID för reseåtgärd.
* hela Assurance trace,
* JSON-vyn av Edge-profilen,
* JSON-vyn av navprofilen,
* osv.

## Scenario 2: Användaren tar fortfarande emot inkommande innehåll även efter att profilen har avslutat resan {#scenario-2}

Det här scenariot är omvänt för [scenario 1](#scenario-1). När en profil avslutar en resa bör den inte längre kvalificera sig för målgruppssegmenten **joai** som motsvarar de inkommande åtgärderna under resan.

Gå igenom samma felsökningssteg som för [Scenario 1](#debugging-steps) för att kontrollera om hubbprofilen, Edge-profilen och Edge Network leveransserver korrekt återspeglar segmentmedlemskapsstatusen för det relevanta **joai**-segmentet och om klienten inte längre tar emot det inkommande innehållet.

<!--
## Additional Notes {#additional-notes}

- **Propagation Time:** Segment membership updates can take up to 15-30 minutes to propagate from the Hub to the Edge Network.
- **Support:** If issues persist after following the steps, open a support ticket with details such as:
  - Journey Version ID and Journey Action ID.
  - Assurance trace.
  - JSON views of Edge and Hub profiles.
  - Debugging observations.

## Reference Section {#reference-section}

- [Assurance Setup Guide](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/tutorials/using-assurance)
- [Adobe Experience Platform Documentation](https://experienceleague.adobe.com/docs/experience-platform/home.html)
- [Streaming Ingestion APIs Troubleshooting](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html)

## Warnings and Notes {#warnings-and-notes}

> **Warning:** Ensure the `joai` namespace is correctly configured in Platform Identities. Misconfiguration can lead to qualification issues for inbound actions.

> **Note:** Segment membership updates may take up to 30 minutes to propagate. Plan debugging sessions accordingly.

## Cross-References {#cross-references}

- [Testing the Journey](../building-journeys/testing-the-journey.md)
- [Using the Journey Designer](../building-journeys/using-the-journey-designer.md#paths)
- [Troubleshooting Custom Actions](../action/troubleshoot-custom-action.md)
-->