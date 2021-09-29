---
title: Utforma din resa
description: Lär dig hur du utformar din resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 1998f6fc-60fd-4038-8669-39cd55bc02d1
source-git-commit: e9da4ec95a82d53e6fcf2cb99fb6215b0c325f08
workflow-type: tm+mt
source-wordcount: '1417'
ht-degree: 1%

---

# Utforma din resa

Med resegränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan. Du kan också dubbelklicka på en aktivitet för att lägga till den på arbetsytan i nästa steg som är tillgängligt. Varje aktivitet har en särskild roll och plats i processen. Aktiviteterna är sekventierade. När en aktivitet är klar fortsätter flödet och bearbetar nästa aktivitet och så vidare.

## Kom igång med resedesign

Paletten **finns till vänster på skärmen.** Alla tillgängliga aktiviteter är sorterade i flera kategorier: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** och **[!UICONTROL Actions]**. Du kan expandera/komprimera de olika kategorierna genom att klicka på deras namn. Om du vill använda en aktivitet på din resa drar och släpper du den från paletten till arbetsytan.

När du påbörjar en ny resa döljs element som inte kan släppas på arbetsytan som det första steget. Detta gäller alla åtgärder, villkorsaktiviteten, väntetiden och reaktionen.

![](../assets/journey38.png)

Med ikonen **[!UICONTROL Filter items]** i det övre vänstra hörnet kan du visa följande filter:

* **Visa endast tillgängliga objekt**: dölja eller visa otillgängliga element på paletten, t.ex. händelser som använder ett annat namnutrymme än de som används under din resa. Som standard är otillgängliga objekt dolda. Om du väljer att visa dem visas de som nedtonade.

* **Visa endast senaste objekt**: Med det här filtret kan du bara visa de fem senast använda händelserna och åtgärderna, förutom de som är färdiga. Detta är specifikt för varje användare. Som standard visas alla objekt.

Du kan också använda fältet **[!UICONTROL Search]**. Endast händelser och åtgärder filtreras.

**arbetsytan** är den centrala zonen i resedesignern. Det är i den här zonen som du kan släppa dina aktiviteter och konfigurera dem. Klicka på en aktivitet på arbetsytan för att konfigurera den. Aktivitetskonfigurationsrutan öppnas till höger.

![](../assets/journey39.png)

Aktivitetskonfigurationsrutan **visas när du klickar på en aktivitet på paletten.** Fyll i de obligatoriska fälten. Klicka på ikonen **[!UICONTROL Delete]** för att ta bort aktiviteten. Klicka på **[!UICONTROL Cancel]** för att avbryta ändringarna eller **[!UICONTROL Ok]** för att bekräfta. Om du vill ta bort aktiviteter kan du även markera en aktivitet (eller flera) och trycka på backstegstangenten. Om du trycker på Esc stängs aktivitetskonfigurationsrutan.

Som standard är skrivskyddade fält dolda. Om du vill visa skrivskyddade fält klickar du på ikonen **Visa skrivskyddade fält** längst upp till vänster i aktivitetskonfigurationsrutan. Denna inställning gäller alla aktiviteter på alla resor.

![](../assets/journey59bis.png)

Beroende på resans status kan du utföra olika åtgärder under resan med hjälp av knapparna i det övre högra hörnet: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. De här knapparna visas när ingen aktivitet är markerad. Vissa knappar visas i sitt sammanhang. Loggknappen för testläget visas när testläget aktiveras.

![](../assets/journey41.png)

## Starta din resa

När du utformar din resa är den första frågan du vill ställa hur profiler kommer in på resan. Det finns två möjligheter:

**Börja med en händelse**: När en resa är inställd på att avlyssna händelser, kommer individer in på resan  **** tillsammans i realtid. Meddelanden som ingår i din resa skickas till den person som för tillfället är på väg in på resan. [Läs mer om evenemang](../event/about-events.md)

**Börja med ett lässegment**: kan ni styra er resa så att ni lyssnar på Adobe Experience Platform segment. I det här fallet kommer alla personer som tillhör det angivna segmentet in på resan. Meddelanden som ingår i resan skickas till personer som tillhör segmentet. [Läs mer om att läsa segment](read-segment.md).

## Definiera nästa steg

Efter din första händelse eller Läs segment kan du kombinera de olika aktiviteterna för att skapa flerstegsscenarier för flera kanaler. Välj de steg du behöver på paletten.

**Händelser**

När du påbörjar din resa med en händelse aktiveras resan när händelsen tas emot. Personen kommer sedan, individuellt, att följa nästa steg som definieras under din resa.

Du kan lägga till **flera händelser** under resan, så länge de använder samma namnutrymme. Händelser konfigureras i förväg. [Läs mer om evenemang](about-journey-activities.md#event-activities)

Du kan också lägga till en **Reaction**-händelse efter ett meddelande för att reagera på spårningsdata som är relaterade till meddelandet. Detta gör att du till exempel kan skicka ett till meddelande om personen öppnade det föregående meddelandet eller klickade i det. Läs mer i det här [avsnittet](reaction-events.md).

Med händelseaktiviteten **Segmentkvalificering** kan du få individer att komma in på eller gå framåt i en resa baserat på Adobe Experience Platform segmentingångar och utgångar. Ni kan få alla nya silverkunder att delta i en resa och skicka personaliserade meddelanden. Läs mer i det här [avsnittet](segment-qualification-events.md).

**Orchestration**

I orkestreringsaktiviteterna hittar du aktiviteten **Läs segment** som gör att du kan ställa in din resa så att den lyssnar på ett Adobe Experience Platform-segment. [Läs mer om Läs segment-aktiviteten](read-segment.md).

Med de andra aktiviteterna kan du lägga till villkor för din resa för att definiera flera olika vägar, ange en väntetid innan nästa aktivitet utförs eller avsluta din resa. Läs mer i det här [avsnittet](about-journey-activities.md#orchestration-activities).

**Instruktioner**

Här finns aktiviteten **Message** som gör att du kan ta med ett meddelande som är utformat i [!DNL Journey Optimizer]. [Läs mer om meddelandeaktiviteten](journeys-message.md)

Du hittar också de anpassade åtgärder som du har konfigurerat för att skicka meddelanden med tredjepartssystem. Läs mer i det här [avsnittet](about-journey-activities.md#action-activities).

## Användning av banor på arbetsytan {#paths}

Flera aktiviteter (**[!UICONTROL Condition]**, **[!UICONTROL Action]** aktiviteter) gör att du kan definiera en reservåtgärd om ett fel eller en timeout inträffar. Markera kryssrutan i aktivitetskonfigurationsrutan: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. En annan sökväg läggs till efter aktiviteten. Tidsgränsen anges i resans egenskaper (se [den här sidan](../building-journeys/journey-gs.md#change-properties) av en administratörsanvändare). Om det t.ex. tar för lång tid att skicka ett e-postmeddelande eller om det är fel, kan du bestämma dig för att skicka ett SMS.

![](../assets/journey42.png)

Med olika aktiviteter (händelse, åtgärd, vänta) kan du lägga till flera sökvägar efter dem. Placera markören på aktiviteten och klicka på plustecknet (+). Endast händelse- och vänteaktiviteter kan anges parallellt. Om flera händelser anges parallellt är den valda sökvägen den första händelsen som inträffar.

När du lyssnar på en händelse rekommenderar vi att du inte väntar på händelsen i oändlighet. Det är inte obligatoriskt, bara en god praxis. Om du bara vill lyssna på en eller flera händelser under en viss tid, placerar du en eller flera händelser och en vänteaktivitet parallellt. Se [det här avsnittet](../building-journeys/general-events.md#events-specific-time).

Om du vill ta bort banan placerar du markören på den och klickar på ikonen **[!UICONTROL Delete path]**.

![](../assets/journey42ter.png)

När två aktiviteter inte är kopplade till arbetsytan visas en varning. Placera markören på varningsikonen för att visa felmeddelandet. Åtgärda problemet genom att flytta den frånkopplade aktiviteten och koppla den till föregående aktivitet.

![](../assets/canvas-disconnected.png)

## Kopierings- och inklistringsaktiviteter {#copy-paste}

Du kan kopiera en eller flera aktiviteter under en resa och klistra in dem antingen under samma resa eller under en annan. På så sätt kan du spara tid om du vill återanvända flera aktiviteter som redan har konfigurerats under en tidigare resa.

**Viktiga anteckningar**

* Du kan kopiera/klistra in mellan olika flikar och webbläsare. Du kan bara kopiera/klistra in aktiviteter i samma instans.
* Du kan inte kopiera/klistra in en händelse om målresan innehåller en händelse som använder ett annat namnutrymme.
* Inklistrade aktiviteter kan referera till data som inte finns i målresan, till exempel om du kopierar/klistrar in mellan olika sandlådor. Sök alltid efter fel och gör nödvändiga justeringar.
* Tänk på att du inte kan ångra en åtgärd. Om du vill ta bort inklistrade aktiviteter måste du markera och ta bort dem. Se därför till att du bara väljer de aktiviteter du behöver innan du kopierar dem.
* Du kan kopiera aktiviteter från vilken resa som helst, även de som är skrivskyddade.
* Du kan välja vilken aktivitet som helst, även en aktivitet som inte är länkad. Länkade aktiviteter förblir länkade när de har klistrats in.

Så här kopierar/klistrar du in aktiviteter:

1. Öppna en resa.
1. Välj de aktiviteter du vill kopiera genom att flytta musen medan du klickar. Du kan också klicka på varje aktivitet samtidigt som du trycker på **Ctrl/Kommando**. Använd **Ctrl/Kommando + A** om du vill markera alla aktiviteter.
   ![](../assets/copy-paste1.png)
1. Tryck på **Ctrl/Kommando + C**.
Om du bara vill kopiera en aktivitet kan du klicka på den och använda ikonen **Kopiera** längst upp till vänster i aktivitetskonfigurationsrutan.
   ![](../assets/copy-paste2.png)
1. Tryck på **Ctrl/Command + V** för att klistra in aktiviteterna utan att länka dem till en befintlig nod under en resa. Inklistrade aktiviteter placeras i samma ordning. När du har klistrat in aktiviteter förblir de markerade så att du enkelt kan flytta dem. Du kan också placera markören på en tom platshållare och trycka på **Ctrl/Kommando + V**. Inklistrade aktiviteter länkas till noden.
   ![](../assets/copy-paste3.png)
