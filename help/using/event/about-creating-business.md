---
title: Konfigurera en affärshändelse
description: Lär dig hur du skapar en affärshändelse
feature: Händelser
topic: Administrering
role: Admin
level: Intermediate
source-git-commit: 63de381ea3a87b9a77bc6f1643272597b50ed575
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 14%

---

# Konfigurera en affärshändelse {#configure-a-business-event}

Till skillnad från enhetshändelser är affärshändelser inte länkade till en viss profil. Händelse-ID-typen är alltid regelbaserad. Läs mer om affärshändelser i [det här avsnittet](../event/about-events.md).

Lässegmentbaserade resor kan aktiveras i ett enda steg, av en schemaläggare regelbundet eller av en affärshändelse, när händelsen inträffar.

Affärshändelser kan vara&quot;en produkt är tillbaka i lager&quot;,&quot;ett företags aktiekurs når ett visst värde&quot; osv.

## Viktiga anteckningar

* Händelseschemat måste innehålla en primär identitet.
* Affärsevenemang kan bara tas bort som det första steget i en resa.
* När du släpper en affärshändelse som första steg i en resa blir transportens schemaläggartyp&quot;affärshändelse&quot;.
* Det går bara att ta bort en lässegmentaktivitet efter en affärshändelse. Det läggs automatiskt till som nästa steg.
* Affärshändelser kan inte utlösas oftare än en timme.
* När en affärshändelse har utlösts uppstår en fördröjning om segmentet exporteras från 15 minuter till upp till en timme.
* När du testar en affärshändelse måste du godkänna händelseparametrarna och identifieraren för den testprofil som kommer att gå in i testet. När du testar en affärshändelsebaserad resa kan du dessutom bara utlösa en enskild profilentré. Se [det här avsnittet](../building-journeys/testing-the-journey.md#test-business). I testläge finns inget kodläge tillgängligt.
* Vad händer med individer som för närvarande är på resa om en ny affärshändelse inträffar? Det fungerar på samma sätt som när enskilda personer fortfarande befinner sig på en återkommande resa när ett nytt återkommande händer. Deras väg är slut. Därför måste marknadsförarna vara uppmärksamma på att de inte behöver skapa för långa resor om de förväntar sig återkommande affärshändelser.

## Kom igång med affärsevenemang

Här följer de första stegen för att konfigurera en affärshändelse:

1. Välj **[!UICONTROL Configurations]** under ADMINISTRATION-menyn. Klicka på **[!UICONTROL Manage]** i **[!UICONTROL Events]**-avsnittet. Listan med händelser visas.

   ![](../assets/jo-event1.png)

1. Klicka på **[!UICONTROL Create Event]** för att skapa en ny händelse. Konfigurationsfönstret för händelsen öppnas till höger på skärmen.

   ![](../assets/jo-event2.png)

1. Ange namnet på händelsen. Du kan också lägga till en beskrivning.

   ![](../assets/jo-event3-business.png)

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Välj **Företag** i fältet **[!UICONTROL Type]**.

   ![](../assets/jo-event3bis-business.png)

1. Antalet resor som använder den här händelsen visas i fältet **[!UICONTROL Used in]**. Du kan klicka på ikonen **[!UICONTROL View journeys]** för att visa en lista över resor som använder den här händelsen.

1. Definiera schema- och nyttolastfälten: Här väljer du den händelseinformation (kallas vanligtvis nyttolast) som resor förväntar sig att ta emot. Du kan sedan använda den här informationen i din resa. Se [det här avsnittet](../event/about-creating-business.md#define-the-payload-fields).

   ![](../assets/jo-event5-business.png)

   Endast tidsseriescheman är tillgängliga. Scheman för upplevelsehändelser, beslutshändelser och resesteghändelser är inte tillgängliga. Händelseschemat måste innehålla en primär identitet.

   ![](../assets/test-profiles-4.png)

1. Klicka i fältet **[!UICONTROL Event ID condition]**. Använd den enkla uttrycksredigeraren för att definiera villkoret som ska användas av systemet för att identifiera de händelser som utlöser din resa.
   ![](../assets/jo-event6-business.png)

   I vårt exempel skrev vi ett villkor baserat på produktens id. Det innebär att när systemet tar emot en händelse som matchar det här villkoret, kommer det att skickas till resorna.

1. Klicka på **[!UICONTROL Save]**.

   ![](../assets/journey7-business.png)

   Händelsen är nu konfigurerad och klar att injiceras i en resa. Ytterligare konfigurationssteg krävs för att ta emot händelser. Läs [den här sidan](../event/additional-steps-to-send-events-to-journey-orchestration.md).

## Definiera nyttolastfälten {#define-the-payload-fields}

Nyttolastdefinitionen gör att du kan välja vilken information systemet förväntar sig från händelsen under din resa och nyckeln för att identifiera vilken person som är associerad med händelsen. Nyttolasten baseras på Experience Cloud XDM-fältdefinitionen. Mer information om XDM finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target=&quot;_blank&quot;}.

1. Välj ett XDM-schema i listan och klicka på fältet **[!UICONTROL Fields]** eller på ikonen **[!UICONTROL Edit]**.

   ![](../assets/journey8-business.png)

   Alla fält som definieras i schemat visas. Listan med fält varierar mellan olika scheman. Du kan söka efter ett specifikt fält eller använda filtren för att visa alla noder och fält eller endast de markerade fälten. Enligt schemadefinitionen kan vissa fält vara obligatoriska och förmarkerade. Du kan inte avmarkera dem. Alla fält som är obligatoriska för att händelsen ska kunna tas emot på rätt sätt under resor markeras som standard.

   ![](../assets/journey9-business.png)

1. Markera de fält som du förväntar dig ska tas emot från händelsen. Det här är de områden som affärsanvändaren kommer att utnyttja under resan.

1. När du är klar med att markera de fält som behövs klickar du på **[!UICONTROL Save]** eller trycker på **[!UICONTROL Enter]**.

   Antalet markerade fält visas i fältet **[!UICONTROL Fields]**.

   ![](../assets/journey12-business.png)

## Förhandsgranska nyttolasten {#preview-the-payload}

Med nyttolastförhandsvisningen kan du validera nyttolastdefinitionen.

1. Klicka på ikonen **[!UICONTROL View Payload]** för att förhandsgranska den nyttolast som systemet förväntar sig.

   ![](../assets/journey13-business.png)

   Du kan se att de markerade fälten visas.

   ![](../assets/journey14-business.png)

1. Kontrollera förhandsgranskningen för att validera nyttolastdefinitionen.

1. Sedan kan du dela nyttolastförhandsvisningen med den person som ansvarar för händelsen som skickar. Den här nyttolasten kan hjälpa honom att utforma konfigurationen för en händelse som ska flyttas till [!DNL Journey Optimizer]. Läs [den här sidan](../event/additional-steps-to-send-events-to-journey-orchestration.md).
