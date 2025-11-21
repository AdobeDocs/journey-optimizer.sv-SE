---
solution: Journey Optimizer
product: journey optimizer
title: Skicka e-post endast på vardagar
description: Lär dig hur du konfigurerar en resa för att skicka e-post endast på vardagar i Adobe Journey Optimizer
feature: Journeys, Use Cases, Email
topic: Content Management
role: User
level: Intermediate
keywords: resa, användningsfall, veckodagar, villkor, e-post, schemaläggning
version: Journey Orchestration
hide: true
hidefromtoc: true
source-git-commit: 46a46fb25c1ef985a0bdea8974aa009e3699c7a3
workflow-type: tm+mt
source-wordcount: '1791'
ht-degree: 0%

---

# Skicka e-post endast på vardagar {#send-emails-only-on-weekdays}

Det här användningsexemplet visar hur du konfigurerar en resa i Adobe Journey Optimizer som endast skickar e-post på vardagar (måndag till fredag). För profiler som går in på resan på helger (lördag eller söndag) köas e-postmeddelanden automatiskt och skickas på måndag vid en viss tidpunkt. Detta säkerställer ett optimalt engagemang genom att leverera meddelanden under arbetsveckan.

## Använd ärendeöversikt

**Utmaningen**: Kontrollera att e-post endast skickas på veckodagar, även om profiler kan komma in på resan på helger. För helgbidrag ska e-postmeddelanden ställas i kö och skickas på måndag vid en viss tidpunkt.

**Lösning**: Använd en villkorsaktivitet för att identifiera veckodagen. För helgposter väntar du på aktiviteter med anpassade formler med e-postadressen tills måndag. Veckodagsposter fortsätter direkt till e-postsändningssteget.

Den här metoden visar hur du använder en villkorsaktivitet för att kontrollera om den aktuella dagen är lördag eller söndag, implementera vänteaktiviteter med anpassade formler för helgposter, skicka e-postmeddelanden i kö för måndag vid en viss timme och skicka e-postmeddelanden direkt för veckodagsposter (måndag-fredag).

Den här metoden är idealisk för e-postkampanjer från företag till företag, professionella nyhetsbrev och kommunikation, affärsrelaterade meddelanden, arbetsrelaterade produktuppdateringar och alla marknadsföringskampanjer där slutleverans inte är önskvärd.

➡️ Se videosjälvstudien [steg för steg](#how-to-video)

>[!NOTE]
>
>För att implementera det här användningsfallet behöver du en aktiv Adobe Journey Optimizer-instans med en konfigurerad [e-postkanalsyta](../configuration/channel-surfaces.md), en [målgrupp](../audience/about-audiences.md) eller [händelse](../event/about-events.md) som utlöser resan, samt en grundläggande förståelse för [resevillkor](condition-activity.md) och [uttryck](expression/expressionadvanced.md).





## Implementeringssteg

### Steg 1: Skapa din resa

1. Navigera till **[!UICONTROL Journey Management]** > **[!UICONTROL Journeys]** i Adobe Journey Optimizer.

1. Klicka på **[!UICONTROL Create Journey]** för att skapa en ny resa. [Läs mer om att skapa resor](journey-gs.md)

1. Konfigurera resans egenskaper:
   * **Namn**: E-postkampanj varje vecka
   * **Beskrivning**: Skickar e-post endast på veckodagar (måndag-fredag)
   * Ange lämpligt namnutrymme för ditt användningsfall

[Läs mer om reseegenskaper](journey-properties.md)

1. Välj ingångspunkt för resan:
   * **[Läs målgrupp](read-audience.md)**: För batchkampanjer som riktar sig till en viss målgrupp
   * **[Händelse](../event/about-events.md)**: För körningar som utlösts i realtid baserat på kundbeteende

### Steg 2: Lägg till en villkorsaktivitet för att kontrollera veckodagen

Direkt efter att resan påbörjats lägger du till en **[!UICONTROL Condition]**-aktivitet för att kontrollera om den aktuella dagen är lördag eller söndag. Det innebär att arbetsflödet grenas i enlighet därmed.

1. Dra och släpp en **[!UICONTROL Condition]**-aktivitet på arbetsytan efter startpunkten. [Läs mer om villkorsaktiviteter](condition-activity.md)

1. Klicka på villkorsaktiviteten för att öppna dess konfigurationspanel.

1. Välj **[!UICONTROL Condition type]** i avsnittet **[!UICONTROL Data Source Condition]**. [Läs mer om villkorstyper](condition-activity.md#data_source_condition)

   ![Konfigurerar lördagsvillkoret i uttrycksredigeraren](assets/weekday-email-uc-condition-expression.png)


### Steg 3: Konfigurera villkoret för att identifiera lördag

Skapa den första villkorssökvägen för att identifiera lördagsbidrag.

1. Klicka på **[!UICONTROL Advanced mode]** för att öppna uttrycksredigeraren. [Läs mer om uttrycksredigeraren](expression/expressionadvanced.md)

1. Ange följande uttryck för att kontrollera om den aktuella dagen är lördag:

   ```javascript
   dayOfWeek(now()) == 7
   ```

   Detta använder funktionen `dayOfWeek()` med `now()` för att hämta den aktuella dagen. [Läs mer om datumfunktioner](functions/date-functions.md)


1. Klicka på **[!UICONTROL Ok]** för att spara villkoret.

1. Ange den här sökvägen som &quot;lördag&quot;.

### Steg 4: Lägg till en andra villkorssökväg för söndag

1. Klicka på **[!UICONTROL Add a path]** i villkorsaktiviteten för att skapa ett andra villkor.

1. I uttrycksredigeraren för den andra sökvägen anger du:

   ```javascript
   dayOfWeek(now()) == 1
   ```

   Detta kontrollerar om den aktuella dagen är söndag.

1. Ange den här sökvägen som &quot;söndag&quot;.

1. Kontrollera **[!UICONTROL Show path for other cases than the one(s) above]** om du vill skapa en sökväg för veckodagsposter (måndag-fredag).


>[!NOTE]
>
>Funktionen `dayOfWeek()` returnerar ett heltal som representerar veckodagen, där 1 är söndag och 7 är lördag. Detta följer ISO-8601-standarden för dagnumrering.

### Steg 5: Konfigurera vänteaktiviteter för helgposter

För profiler som kommer in på lördag eller söndag använder du Vänteaktiviteter med anpassade formler för att fördröja e-postmeddelandet till måndag till önskad timme.


**För lördagssökvägen:**

1. Lägg till en **[!UICONTROL Wait]**-aktivitet. [Läs mer om väntande aktiviteter](wait-activity.md)

1. Välj **[!UICONTROL Duration]** som vänttyp.

1. Klicka på **[!UICONTROL Advanced mode]** om du vill ange en anpassad formel.

1. Ange följande formel som ska vänta till måndag 09:

   ```javascript
   toDuration("PT" + (48 - getHourOfDay(now())) + "H")
   ```

   Eller använd den här alternativa formeln:

   ```javascript
   setHours(nowWithDelta(2, "days"), 9)
   ```

   ![Resa med tre villkorssökvägar - lördag, söndag och veckodagar](assets/weekday-email-uc-paths.png)

   **Förklaring**: Den här formeln beräknar väntetiden från lördag till måndag klockan 9. Värdet X=2 representerar 2 dagar framåt (lördag + 2 dagar = måndag). [Läs mer om datumfunktioner](functions/date-functions.md#nowWithDelta)

**För söndagssökvägen:**

1. Lägg till en **[!UICONTROL Wait]**-aktivitet.

1. Välj **[!UICONTROL Duration]** som vänttyp.

1. Klicka på **[!UICONTROL Advanced mode]** om du vill ange en anpassad formel.

1. Ange följande formel som ska vänta till måndag 09:

   ```javascript
   setHours(nowWithDelta(1, "days"), 9)
   ```

   **Förklaring**: Den här formeln väntar 1 dag (söndag + 1 dag = måndag) och ställer in tiden till 9:00. Värdet X=1 representerar 1 dag framåt och H=9 representerar 9.

>[!TIP]
>
>Du kan anpassa timparametern (H) när du vill att e-postmeddelandet ska skickas på måndag. Ändra till exempel 9 till 10 för 10 eller 14 för 2 PM.

### Steg 6: Konfigurera veckodagssökvägen

För **veckodagssökvägen** (måndag-fredag):

1. Fortsätt direkt för att lägga till en **[!UICONTROL Email]**-åtgärdsaktivitet. Ingen vänteaktivitet behövs för veckodagsposter. [Läs mer om e-poståtgärder](journeys-message.md)

1. Konfigurera ditt e-postmeddelande:
   * Välj eller skapa ditt [e-postinnehåll](../email/get-started-email-design.md)
   * Konfigurera [e-postparametrarna](../email/email-settings.md)
   * Konfigurera [personalisering](../personalization/personalize.md) efter behov

1. Lägg till en **[!UICONTROL End]**-aktivitet efter e-postmeddelandet.

### Steg 7: Sammanfoga helgsökvägar till e-post

Efter Wait-aktiviteterna på båda lördag- och söndagsvägarna sammanfogar du dem till samma e-postaktivitet:

1. Lägg till en **[!UICONTROL Email]**-åtgärd från aktiviteten Vänta på lördag.

1. Anslut till samma e-poståtgärd från aktiviteten Vänta på söndag.

1. Sökvägen för veckodag bör även följa den här e-poståtgärden.

### Steg 8: Testa din resa

Innan du publicerar testar du kundens reselogik noggrant i Adobe Journey Optimizer testläge för att bekräfta att allt fungerar som förväntat:

1. Klicka på knappen **[!UICONTROL Test]** längst upp till höger.

1. Aktivera testläge. [Lär dig hur du testar din resa](testing-the-journey.md)

1. Skapa [testprofiler](../audience/creating-test-profiles.md) med simulerade starttider på olika veckodagar:
   * **Lördagsinträde**: Verifiera att profilen följer lördagssökvägen, väntar och får e-post på måndag den angivna timmen
   * **Sönsterpost**: Verifiera att profilen följer söndagssökvägen, väntar och tar emot e-post på måndag den angivna timmen
   * **Måndag-fredag**: Verifiera att e-postmeddelanden skickas omedelbart utan väntan

1. Granska visualiseringen av resan för att säkerställa att profilerna följer rätt villkorsstyrda sökvägar (lördag, söndag eller veckodag).

1. Kontrollera om resan innehåller fel eller varningar. [Läs om felsökning av resor](troubleshooting.md)

1. Kontrollera att Wait-formlerna beräknar rätt varaktighet för den önskade måndagsleveranstiden.

>[!IMPORTANT]
>
>Testa alltid kundens logik noggrant innan du publicerar till produktion. Använd testläge för att simulera olika inmatningsscenarier och validera att helgposter är korrekt köade för måndagsleverans. [Läs mer om hur du testar resan ](testing-the-journey.md)

### Steg 9: Publicera din resa

När testningen är klar:

1. Klicka på **[!UICONTROL Publish]** längst upp till höger.

1. Bekräfta publikationen. [Läs mer om publiceringsresor](publish-journey.md)

1. Övervaka reseprestanda med hjälp av [reserapportering](report-journey.md) och [liverapporter](../reports/journey-live-report.md).

## Bästa praxis och överväganden

+++**Optimera arbetsflödet med förbättrade formler**

Om du vill förbättra arbetsflödet och hantera mer komplexa affärsbehov kan du utöka formlerna så att de omfattar helger, tidszoner eller specifika arbetstimmar efter den grundläggande veckodagskontrollen. Justera timparametern (H) i Wait-formeln så att den matchar din optimala sändningstid. Om till exempel 10:00 visar bättre engagemangsfrekvens ändrar du formeln så att den använder timmen 10. För stöd för flera tidszoner bör du överväga att skapa separata resor för olika geografiska regioner för att säkerställa måndagsleverans i varje mottagares lokala tidszon.

+++

+++**Hantering av tidszoner**

Funktionen `now()` och körningen av resan använder den tidszon som konfigurerats på resenivån. Se till att resetidszonen matchar dina behov genom att konfigurera detta i reseegenskaperna före publicering ([Läs mer om tidszonshantering](timezone-management.md)). Om målgruppen sträcker sig över flera tidszoner bör du tänka på att veckodagskontrollen sker i kundens konfigurerade tidszon, inte i mottagarens lokala tidszon. För tidszonsspecifik leverans skapar du separata resor för olika regioner eller använder tidszonsinställningarna i aktiviteten Läs målgrupp.

+++

+++**Resepost och timing**

För gruppresor schemalägger [Läs målgruppen](read-audience.md#schedule) att utlösas vid en tidpunkt som passar din målgrupp - tidiga morgonexekveringar (t.ex. 6:00 AM) är vanliga för affärskommunikation. För händelsebaserade resor utvärderas villkoret omedelbart när händelsen tas emot, och profiler som anges på helger väntar automatiskt till måndag ([Läs mer om händelser](../event/about-events.md)). Se till att dina [inställningar för tidsgräns för resa](journey-properties.md#timeout) har plats för den maximala vänteperioden (upp till 2 dagar från lördag till måndag).

+++

+++**Testning är nödvändigt**

Så som det betonas i implementeringsguiden ska du alltid testa din reselogik för att bekräfta att allt fungerar som det ska. Använd **Testläge** för att simulera olika startscenarier utan att skicka riktiga e-postmeddelanden. Testa alla tre sökvägarna (lördagsposter, söndagsposter och veckodagsposter), kontrollera att beräkningarna av väntetiden är korrekta, bekräfta att måndagsleveransen sker vid den angivna timmen och kontrollera visualiseringen av resan för att säkerställa rätt väg.

+++

+++**Återinträde och frekvens**

För återkommande kampanjer konfigurerar du inställningarna för **[!UICONTROL Re-entrance]** korrekt ([Läs mer om inställningarna för återinträde](entry-management.md)). Om profilerna kan återinträda på resan kontrolleras varje gång varje dag, vilket säkerställer att alla helgposter alltid är köade på måndag. Överväg att lägga till [regler för frekvensbegränsning](../conflict-prioritization/journey-capping.md) för att undvika överskjutande meddelanden om profiler kan registrera sig ofta.

+++

## Avancerade varianter

+++**Specifik dagmålinriktning**

Ändra villkoret om du endast vill skicka e-post på en viss dag (t.ex. tisdagar och torsdagar):

```javascript
dayOfWeek(now()) == 3 or dayOfWeek(now()) == 5
```

För alla andra dagar lägger du till en Wait-aktivitet som beräknar antalet dagar till nästa tisdag eller torsdag.

+++

+++**Olika sändningstider för olika dagar**

Du kan skapa flera sökvägar med olika Vänteformler för olika helgsbeteenden. Använd till exempel `nowWithDelta(4, "days")` för leverans lördag till onsdag eller `nowWithDelta(2, "days")` för leverans söndag till tisdag. Detta ger större flexibilitet i sändningsplanen.

+++

+++**Leverans under kontorstid**

Justera timparametern i din Wait-formel för att försäkra dig om leverans under kontorstid. För leverans klockan 2 i stället för 09:

```javascript
setHours(nowWithDelta(1, "days"), 14)
```

Du kan också lägga till ett andra villkor efter väntetiden för att kontrollera om den aktuella tiden är inom kontorstid innan du skickar.

+++

+++**Undantag för helgdag**

Om du vill utesluta helger lägger du till en extra sökväg som söker efter specifika datum:

```javascript
toDateTimeOnly(now()) == toDateTimeOnly("2024-12-25T00:00:00")
```

Om villkoret matchar en semester lägger du till en Wait-aktivitet som fördröjs till nästa arbetsdag. [Läs mer om funktioner för datumjämförelse](functions/date-functions.md)

+++

## Relaterade ämnen

* [Om villkorsaktiviteter](condition-activity.md) - Lär dig hur du skapar olika sökvägar i din resa
* [Användningsvillkor i en resa](conditions.md) - Detaljerad guide om resevillkor
* [Vänteaktivitet](wait-activity.md) - Konfigurera väntetider och formler
* [Datumfunktioner](functions/date-functions.md) - Fullständig referens för datum- och tidsfunktioner
* [Uttrycksredigeraren](expression/expressionadvanced.md) - Skapa komplexa uttryck
* [Testa din resa](testing-the-journey.md) - Verifiera reselogik före publicering
* [Tidszonshantering](timezone-management.md) - Hantera olika tidszoner under resor
* [Bästa praxis på resan](journey-gs.md#best-practices) - Rekommenderade strategier för resedesign

## Instruktionsvideo

Lär dig hur du skickar e-post endast på vardagar med Adobe Journey Optimizer. I den här videon visas hur du stegvis implementerar villkorsaktiviteter och väntar-formler för att placera helgposter i kö för måndagsleverans.

>[!VIDEO](https://video.tv.adobe.com/v/3469330?quality=12&learn=on)

## Ytterligare resurser

* [Dokumentation för uttrycksredigeraren](expression/expressionadvanced.md) - Bygg och validera reseuttryck
* [Resedesignerguide](using-the-journey-designer.md) - bemästra arbetsytan
* [Översikt över användningsfall under resan](jo-use-cases.md) - Utforska fler resemönster och exempel
* [Community-blogginlägg: Så här skickar du e-post endast på veckodagar](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/how-to-send-emails-only-on-weekdays-in-adobe-journey-optimizer/ba-p/760400){target="_blank"} - Ursprungligt blogginlägg med detaljerade exempel

