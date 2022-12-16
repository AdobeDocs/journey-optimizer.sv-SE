---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Analytics-integrering
description: Lär dig utnyttja Adobe Analytics data
feature: Events
topic: Administration
role: Admin
level: Intermediate
exl-id: 9d842722-e5eb-4743-849d-b7ba9448062f
source-git-commit: 53d89f216961daba72e96a728301572b83824655
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 7%

---

# Adobe Analytics-integrering {#analytics-data}

## Utnyttja data från Adobe Analytics eller Web SDK {#leverage-analytics-data}

Ni kan utnyttja alla webbhändelsedata (via Adobe Analytics eller Web SDK) som ni redan samlar in och strömmar till Adobe Experience Platform för att utlösa resor och automatisera kundernas upplevelser.

>[!NOTE]
>
>Det här avsnittet gäller endast för regelbaserade händelser och kunder som behöver använda Adobe Analytics- eller WebSDK-data.

För att detta ska fungera med Adobe Analytics måste du aktivera den rapportsserie som du vill använda i Adobe Experience Platform. Följ stegen nedan för att göra detta:

1. Anslut till Adobe Experience Platform och gå till **[!UICONTROL Sources]**.

1. I Adobe Analytics väljer du **[!UICONTROL Add data]**

   ![](assets/ajo-aa_1.png)

1. I listan över tillgängliga Adobe Analytics-rapportsviter väljer du **[!UICONTROL Report suite]** för att aktivera. Klicka sedan på **[!UICONTROL Next]**.

   ![](assets/ajo-aa_2.png)

1. Välj om du vill använda ett standardschema eller ett anpassat schema.

1. Från **[!UICONTROL Dataflow detail]** väljer du en **[!UICONTROL Dataflow name]**.

1. När konfigurationen är klar klickar du på **[!UICONTROL Finish]**.

   ![](assets/ajo-aa_3.png)

Detta aktiverar Analytics-källkopplingen för den rapportsviten. När informationen kommer in omvandlas den till en Experience-händelse och skickas till Adobe Experience Platform.

![](assets/ajo-aa_4.png)

Läs mer om Adobe Analytics källanslutning i  [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html){target=&quot;_blank&quot;} och [självstudiekurs](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html){target=&quot;_blank&quot;}.

## Skapa en resa med en händelse med hjälp av Adobe Analytics- eller Web SDK-data {#event-analytics}

När du har implementerat integreringen med Adobe Analytics med [Adobe Analytics-källor](#leverage-analytics-data) eller med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)kan du skapa en händelse som senare kan användas i en resa.

I det här exemplet riktar vi oss till användare som har lagt till en produkt i sina kundvagnar:

* Om beställningen är klar får de ett uppföljningsmejl två dagar senare för att be om feedback.
* Om ordern inte är slutförd får de ett mejl som påminner dem om att ordern är slutförd.

1. Från Adobe Journey Optimizer kommer du åt **[!UICONTROL Configuration]** -menyn.

1. Välj sedan **[!UICONTROL Manage]** från **[!UICONTROL Events]** kort.

   ![](assets/ajo-aa_5.png)

1. Klicka på **[!UICONTROL Create event]**. Konfigurationsfönstret för händelsen öppnas till höger på skärmen.

1. Fyll i **[!UICONTROL Event]** parametrar:

   * **[!UICONTROL Name]**: Anpassa namnet på **[!UICONTROL Event]**.
   * **[!UICONTROL Type]**: Välj **[!UICONTROL Unitary]** Typ. [Läs mer](../event/about-events.md)
   * **[!UICONTROL Event ID type]**: Välj **[!UICONTROL Rule based]** Händelse-ID-typ. [Läs mer](../event/about-events.md#event-id-type)
   * **[!UICONTROL Schema]**: Välj det Analytics- eller WebSDK-schema som skapades i avsnittet ovan.
   * **[!UICONTROL Fields]**: Välj nyttolastfälten. [Läs mer](../event/about-creating.md#define-the-payload-fields)
   * **[!UICONTROL Event ID condition]**: Definiera villkoret som ska användas av systemet för att identifiera de händelser som utlöser din resa.

      Här utlöses händelsen när kunderna lägger till en artikel i sina kundvagnar.
   * **[!UICONTROL Profile Identifier]**: Välj ett fält bland dina nyttolastfält eller definiera en formel för att identifiera den person som är associerad med händelsen.

   ![](assets/ajo-aa_6.png)

1. Välj **[!UICONTROL Save]**. Din aktivitet kan nu användas under en resa.

1. Från **[!UICONTROL Journeys]** kan du nu börja skapa din resa. Mer information om detta finns i [det här avsnittet](../building-journeys/journey-gs.md).

1. Lägg till era tidigare konfigurerade Analytics-händelser på er resa.

   ![](assets/ajo-aa_8.png)

1. Lägg till en händelse som utlöses om en beställning slutförs.

1. Från **[!UICONTROL Event menu]** väljer du **[!UICONTROL Define the event timeout]** och **[!UICONTROL Set a timeout path]** alternativ.

   ![](assets/ajo-aa_9.png)

1. Lägg till en **[!UICONTROL Email]** åtgärd. Den här sökvägen kommer att användas för att skicka ett e-postmeddelande till kunder som inte slutfört en order för att påminna dem om att deras kundvagnar fortfarande är tillgängliga.

1. Lägg till en **[!UICONTROL Wait]** efter huvudsökvägen och ange den till önskad längd.

   ![](assets/ajo-aa_10.png)

1. Lägg sedan till en **[!UICONTROL Email action]**. I det här e-postmeddelandet uppmanas kunderna att ge återkoppling om den placerade beställningen.

Nu kan du publicera din resa efter att ha testat dess giltighet. [Läs mer](../building-journeys/publishing-the-journey.md)

![](assets/ajo-aa_7.png)
