---
solution: Journey Optimizer
product: journey optimizer
title: Starta och övervaka samordnade kampanjer med Adobe Journey Optimizer
description: Lär dig hur du startar och övervakar samordnade kampanjer med Adobe Journey Optimizer.
hide: true
hidefromtoc: true
exl-id: 3c1cad30-3ed7-4df1-a46a-60394a834e79
source-git-commit: 0ae8372c179707a87a6b512a5420753a4aaef754
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%

---

# Skapa återmarknadsföringsfrågor {#retarget}

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md)<br/><br/>[Viktiga steg för att skapa en strukturerad kampanj](gs-campaign-creation.md) | [Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/>[Starta och övervaka kampanjen](start-monitor-campaigns.md)<br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/><b>[Återmarknadsföring](retarget.md)</b> | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](activities/save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

Dokumentation pågår

>[!ENDSHADEBOX]

Med återmarknadsföring kan ni följa upp med mottagare baserat på hur de svarade på en tidigare iscensatt kampanj. Du kan till exempel skicka ett andra e-postmeddelande till profiler som har tagit emot men inte klickat på den första.

Samordnade kampanjer innehåller två huvuddatakällor för detta:

- **Meddelandefeedback**: hämtar leveransrelaterade händelser, t.ex. skickade, öppnade, studsade osv.

- **E-postspårning**: hämtar användaråtgärder, t.ex. klickningar och öppningar.

## Skapa en feedbackbaserad återmarknadsföringsregel

Med feedbackbaserad återmarknadsföringsregel kan du återrikta mottagare baserat på meddelandeleveranshändelser som hämtats i datauppsättningen **Meddelandefeedback**. Dessa händelser innehåller utfall som meddelanden som skickas, öppnas, studsas eller markeras som skräppost.

Med hjälp av dessa data kan du definiera regler för att identifiera mottagare som har tagit emot ett tidigare meddelande, men som inte har interagerat med det, vilket möjliggör uppföljningskommunikation baserat på specifika leveransstatus.

1. Skapa en ny **orkestrerad kampanj**.

2. Lägg till en **Bygg målgrupp**-aktivitet och ange måldimensionen till **Mottagare (katalog)**.

3. Klicka på **Lägg till villkor** i **regelbyggaren** och välj **Meddelandefeedback** i attributväljaren. Klicka på **Bekräfta**.

4. Lägg till ett villkor för **feedbackstatus** och ange värdet till **Meddelande skickat**.

5. Så här riktar du dig till en viss orkestrerad kampanj:

   - Lägg till ytterligare ett villkor, sök efter `entity` och navigera till:\
     `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign`.

   - Välj **Orchestrated Campaign Name** och ange kampanjnamnet.

6. Om du vill rikta ett visst meddelande eller en viss aktivitet inom den samordnade kampanjen:

   - Lägg till ytterligare ett villkor, sök efter `entity` och navigera till:\
     `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign`.

   - Välj **Orchestrated Campaign Action Name** och ange kampanjåtgärdens namn.

     Du hittar åtgärdsnamn genom att klicka på ![informationsikonen](assets/do-not-localize/info-icon.svg) bredvid en aktivitet på arbetsytan.

   >[!TIP]
   >
   >I stället för att använda namn kan du även filtrera efter **Kampanj-ID** (UUID), som finns i dina Campaign-egenskaper.

## Skapa en spårningsbaserad återmarknadsföringsregel

Spårningsbaserad regel för återmarknadsföring riktar sig till mottagare baserat på deras interaktioner med ett meddelande, med data från datauppsättningen **E-postspårning**. Den fångar upp användaråtgärder som e-postöppningar och länkar.

Använd entiteten **E-postspårning** om du vill omdirigera mottagare baserat på meddelandeinteraktioner (t.ex. öppna eller klicka):

1. Skapa en ny **Orchestrated Campaign** och lägg sedan till en **Bygg målgruppsaktivitet** med **Mottagare (CAAS)** som måldimension för att fokusera på tidigare orienterade kampanjmottagare.

1. Lägg till ett nytt villkor för **e-postspårning**. Klicka på **Bekräfta** om du vill skapa ett villkor om att e-postspårning finns, till exempel.

1. Lägg till ett villkor i det villkoret och sök efter attributet **Interaktionstyp**.

1. Använd **Inkluderad i** som operator i de anpassade villkorsalternativen och välj ett eller flera värden beroende på ditt användningssätt. Exempel:
   - **Meddelandet öppnat**
   - **Meddelandelänk klickad**

1. Så här associerar du spårningsdata med en viss kampanj:

   - Lägg till ett villkor i blocket E-postspårning.

   - Navigera till `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign`.

   - Lägg till villkor för både **Orchestrated Campaign Name** och, om det behövs, **Orchestrated Campaign Action Name**.

     Du hittar åtgärdsnamn genom att klicka på ![informationsikonen](assets/do-not-localize/info-icon.svg) bredvid en aktivitet på arbetsytan.

   >[!TIP]
   >
   >I stället för att använda namn kan du även filtrera efter **Kampanj-ID** (UUID), som finns i dina Campaign-egenskaper.
