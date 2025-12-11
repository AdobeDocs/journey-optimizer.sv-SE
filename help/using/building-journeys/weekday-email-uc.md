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
source-git-commit: 970712614b0d4da37d9ecbe45701f93147b1428c
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 0%

---

# Skicka e-post endast på vardagar {#send-emails-only-on-weekdays}

Det här användningsexemplet visar hur du konfigurerar en resa i Adobe Journey Optimizer som endast skickar e-post på vardagar (måndag till fredag). För profiler som går in på resan på helger (lördag eller söndag) köas e-postmeddelanden automatiskt och skickas på måndag vid en viss tidpunkt. Detta säkerställer ett optimalt engagemang genom att leverera meddelanden under arbetsveckan.

## Använd ärendeöversikt

**Utmaningen**: Kontrollera att e-post endast skickas på veckodagar, även om profiler kan komma in på resan på helger. För helgbidrag ska e-postmeddelanden ställas i kö och skickas på måndag vid en viss tidpunkt.

**Lösning**: Använd en villkorsaktivitet för att identifiera veckodagen. För helgposter väntar du på aktiviteter med anpassade formler med e-postadressen tills måndag. Veckodagsposter fortsätter direkt till e-postsändningssteget.

Den här metoden visar hur du använder en villkorsaktivitet för att kontrollera om den aktuella dagen är lördag eller söndag, implementera vänteaktiviteter med anpassade formler för helgposter, skicka e-postmeddelanden i kö för måndag vid en viss timme och skicka e-postmeddelanden direkt för veckodagsposter (måndag-fredag).

Den här metoden är idealisk för e-postkampanjer från företag till företag, professionella nyhetsbrev och kommunikation, affärsrelaterade meddelanden, arbetsrelaterade produktuppdateringar och alla marknadsföringskampanjer där slutleverans inte är önskvärd.

>[!NOTE]
>
>För att implementera det här användningsfallet behöver du en aktiv Adobe Journey Optimizer-instans med en konfigurerad [e-postkanalsyta](../configuration/channel-surfaces.md), en [målgrupp](../audience/about-audiences.md) eller [händelse](../event/about-events.md) som utlöser resan, samt en grundläggande förståelse för [resevillkor](condition-activity.md) och [uttryck](expression/expressionadvanced.md).


## Implementeringssteg

### Steg 1: Skapa din resa

1. Navigera till **[!UICONTROL Journey Management]** > **[!UICONTROL Journeys]** i Adobe Journey Optimizer.

1. Klicka på **[!UICONTROL Create Journey]** för att [skapa en ny resa](journey-gs.md).

1. Konfigurera [reseegenskaperna](journey-properties.md).

1. Välj ingångspunkt för resan:
   * **[Läs målgrupp](read-audience.md)**: För batchkampanjer som riktar sig till en viss målgrupp
   * **[Händelse](../event/about-events.md)**: För körningar som utlösts i realtid baserat på kundbeteende

### Steg 2: Lägg till en villkorsaktivitet för att kontrollera veckodagen

Direkt efter att resan påbörjats lägger du till en **[!UICONTROL Condition]**-aktivitet för att kontrollera om den aktuella dagen är lördag eller söndag. Det innebär att arbetsflödet grenas i enlighet därmed.

1. Dra och släpp en [**[!UICONTROL Condition]**&#x200B;aktivitet &#x200B;](condition-activity.md) på arbetsytan efter startpunkten.

1. Klicka på aktiviteten **[!UICONTROL Condition]** för att öppna dess konfigurationspanel.

1. Välj **[!UICONTROL Time condition]** som villkorstyp.

1. Välj **[!UICONTROL Day of the week]** som tidsfiltreringsalternativ.

1. För den **första sökvägen (lördag)** väljer du endast **lördag**. Ange den här sökvägen som &quot;lördag&quot;.

1. Klicka på **[!UICONTROL Add a path]** om du vill skapa ett andra villkor.

1. För den **andra sökvägen (söndag)** markerar du **[!UICONTROL Day of the week]** och väljer endast **söndag**. Ange den här sökvägen som &quot;söndag&quot;.

   ![Konfigurerar lördags- och söndagsvillkoren i uttrycksredigeraren](assets/weekday-email-uc-condition-expression.png)


1. Kontrollera **[!UICONTROL Show path for other cases than the one(s) above]** om du vill skapa en sökväg för veckodagsposter (måndag-fredag).

>[!NOTE]
>
>Den tidszon som används för veckodagsutvärderingen definieras på resenivån i reseegenskaperna, inte på villkorsnivå. Resan [timezone](timezone-management.md) som används i formeln är den konfigurerade tidszonen för resan, inte mottagarens.

### Steg 3: Konfigurera vänteaktiviteter för helgposter

För profiler som kommer in på lördag eller söndag använder du **[!UICONTROL Wait]**-aktiviteter med anpassade formler för att fördröja e-postmeddelandet till måndag vid önskad timma.

Använd följande formel i aktiviteten **[!UICONTROL Wait]**:

```javascript
toDateTimeOnly(setHours(nowWithDelta(X, "days"), H))
```

Var:

* **X** är antalet dagar att vänta:
   * Använd **2** i lördags (vänta till måndag)
   * Använd **1** på söndag (vänta till måndag)
* **H** är den timme som du vill skicka (t.ex. **9** för 9 AM)


**Exempel för lördag:**

```javascript
toDateTimeOnly(setHours(nowWithDelta(2, "days"), 9))
```

**Exempel för söndag:**

```javascript
toDateTimeOnly(setHours(nowWithDelta(1, "days"), 9))
```

Så här implementerar du detta under din resa:

1. Lägg till en **-aktivitet efter villkoret på** lördagssökvägen **[!UICONTROL Wait]**.

1. Välj **[!UICONTROL Duration]** som vänttyp.

1. Klicka på **[!UICONTROL Advanced mode]** för att ange den anpassade formeln.

1. Ange: `toDateTimeOnly(setHours(nowWithDelta(2, "days"), 9))`

   ![Resa med tre villkorssökvägar - lördag, söndag och veckodagar](assets/weekday-email-uc-paths.png)

1. Upprepa samma steg för **söndagssökvägen** med: `toDateTimeOnly(setHours(nowWithDelta(1, "days"), 9))`

>[!TIP]
>
>För mer komplexa arbetstider (t.ex. om du bara skickar mellan 09:00 och 17:00 på vardagar) kan du förbättra formeln och villkoren ytterligare.

### Steg 4: Veckodagsgren

För profiler som kommer in måndag till fredag går du vidare till e-poststeget som vanligt.

1. Gå direkt till **Veckodagssökvägen** (den andra ärendesökvägen) och lägg till en **[!UICONTROL Email]**-åtgärdsaktivitet. Ingen **[!UICONTROL Wait]**-aktivitet behövs för veckodagsposter.

1. Konfigurera e-postmeddelandet efter behov.

### Steg 5: Slutför hela reseflödet

Efter **[!UICONTROL Wait]**-aktiviteterna på både lördag- och söndagssökvägar ska alla tre sökvägarna (lördag, söndag och veckodagar) flöda till samma **[!UICONTROL Email]**-åtgärdsaktivitet. Lägg till en **[!UICONTROL End]**-aktivitet efter e-postmeddelandet.

### Översikt över visuellt arbetsflöde

Hela arbetsflödet följer denna logik:

* **Start** → **[!UICONTROL Condition]**: Är det lördag eller söndag?
   * **Ja (lördag):** **[!UICONTROL Wait]** till måndag 9 → **[!UICONTROL Send email]**
   * **Ja (söndag):** **[!UICONTROL Wait]** till måndag 9 → **[!UICONTROL Send email]**
   * **Nej (måndag-fredag):** **[!UICONTROL Send email]** omedelbart

Detta garanterar att alla e-postmeddelanden skickas endast på vardagar, med helgposter automatiskt i kö för måndagsleverans.

### Steg 6: Testa din resa

Innan du publicerar testar du kundens reselogik noggrant i Adobe Journey Optimizer testläge för att bekräfta att allt fungerar som förväntat:

1. Klicka på knappen **[!UICONTROL Test]** längst upp till höger.

1. Aktivera [testläge](testing-the-journey.md).

1. Skapa [testprofiler](../audience/creating-test-profiles.md) med simulerade starttider på olika veckodagar:
   * **Lördagsinträde**: Verifiera att profilen följer lördagssökvägen, väntar och får e-post på måndag den angivna timmen
   * **Sönsterpost**: Verifiera att profilen följer söndagssökvägen, väntar och tar emot e-post på måndag den angivna timmen
   * **Måndag-fredag**: Verifiera att e-postmeddelanden skickas omedelbart utan väntan

1. Granska visualiseringen av resan för att säkerställa att profilerna följer rätt villkorsstyrda sökvägar (lördag, söndag eller veckodag).

1. Kontrollera om det finns [fel eller varningar](troubleshooting.md) under resan.

1. Kontrollera att Wait-formlerna beräknar rätt varaktighet för den önskade måndagsleveranstiden.

>[!IMPORTANT]
>
>Testa alltid kundreslogiken i testläge för att kontrollera att vänteaktiviteterna fungerar som förväntat. Använd testläge för att simulera olika inmatningsscenarier och validera att helgposter är korrekt köade för måndagsleverans. Mer information finns i [testning av resan &#x200B;](testing-the-journey.md).

### Steg 7: Publicera din resa

När testningen är klar:

1. Klicka på **[!UICONTROL Publish]** längst upp till höger.

1. Bekräfta [publikationen](publish-journey.md).

1. Övervaka reseprestanda med hjälp av [reserapportering](report-journey.md) och [liverapporter](../reports/journey-live-report.md).


## Relaterade ämnen

* [Villkorsaktiviteter](condition-activity.md) - Lär dig hur du skapar olika sökvägar i din resa
* [Användningsvillkor i en resa](conditions.md) - Detaljerad guide om resevillkor
* [Vänteaktivitet](wait-activity.md) - Konfigurera väntetider och formler
* [Datumfunktioner](functions/date-functions.md) - Fullständig referens för datum- och tidsfunktioner
* [Uttrycksredigeraren](expression/expressionadvanced.md) - Skapa komplexa uttryck
* [Bästa praxis på resan](journey-gs.md#best-practices) - Rekommenderade strategier för resedesign
