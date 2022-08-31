---
title: Skapa en kampanj
description: Lär dig hur du skapar kampanjer i [!DNL Journey Optimizer]
feature: Overview
topic: Content Management
role: User
level: Intermediate
exl-id: 7c4afc98-0d79-4e26-90f8-558bac037169
source-git-commit: 28380dbadf485ba05f7ef6788a50253876718441
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 3%

---

# Skapa en kampanj {#create-campaign}

>[!NOTE]
>
>Innan du skapar en ny kampanj måste du se till att du har en ytkanal (dvs. meddelandeförinställning) och ett Adobe Experience Platform-segment som är klart att använda. Läs mer i följande avsnitt:
>
>* [Skapa kanalytor](../configuration/channel-surfaces.md)
>* [Kom igång med segment](../segment/about-segments.md)


## Skapa din första kampanj {#create}

1. Öppna **[!UICONTROL Campaigns]** menyn och klicka sedan på **[!UICONTROL Create campaign]**.

   >[!NOTE]
   >
   >Du kan också duplicera en befintlig livekampanj och skapa en ny. [Läs mer](modify-stop-campaign.md#duplicate)

   ![](assets/create-campaign.png)

<!--1. In the **[!UICONTROL Properties]** section, specify when you want to execute the campaign:

    * **[!UICONTROL Scheduled]**: execute the campaign immediately or on a specified date. Scheduled campaigns are aimed at sending **marketing** type messages.
    * **[!UICONTROL API-triggered]**: execute the campaign using an API call. API-triggered campaigns are aimed at sending **transactional** messages, i.e. messages sent out following an action performed by an individual: password reset, card abandonment etc. [Learn how to trigger a campaign using APIs](api-triggered-campaigns.md)-->

1. I **[!UICONTROL Actions]** väljer du kanal och kanal för att skicka meddelandet och klickar sedan på **[!UICONTROL Create]**.

   En yta är en konfiguration som har definierats av en [Systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer](../configuration/channel-surfaces.md).

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >Endast kanalytor som är kompatibla med marknadsföringskampanjtypen visas i listrutan.

<!--Only channel surfaces compatible with the campaign type (marketing or transactional) are listed in the drop-down list.-->

1. Ange en titel och en beskrivning för kampanjen.

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../campaigns/content-experiment.md).-->

1. I **[!UICONTROL Actions]** konfigurerar du meddelandet som ska skickas med kampanjen:

   1. Klicka på **[!UICONTROL Edit content]** och sedan konfigurera och utforma meddelandeinnehållet. [Läs mer om meddelanden](../messages/get-started-content.md).

      Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sida:

      * [Skapa ett e-postmeddelande](../messages/create-email.md)
      * [Skapa push-meddelanden](../messages/create-push.md)
      * [Skapa ett SMS-meddelande](../messages/create-sms.md)
   1. När innehållet är definierat kan du använda **[!UICONTROL Simulate content]** för att förhandsgranska och testa innehållet med testprofiler. [Läs mer](../design/preview.md).

   1. Klicka på pilen för att gå tillbaka till skärmen för att skapa kampanjer.

      ![](assets/create-campaign-design.png)

   1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra hur mottagarna svarar på leveransen: du kan spåra klick och/eller öppningar.

      Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../reports/campaign-global-report.md)


1. Definiera målgruppen. Om du vill göra det klickar du på **[!UICONTROL Select audience]** om du vill visa en lista över tillgängliga Adobe Experience Platform-segment. [Läs mer om segment](../segment/about-segments.md)

   <!-- NOTE For API-triggered campaigns, the audience needs to be set via API call. [Learn more](api-triggered-campaigns.md)-->

   I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace)

   ![](assets/create-campaign-namespace.png)

   >[!NOTE]
   >
   >Individer som tillhör ett segment som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kommer inte att omfattas av kampanjen.

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

1. Konfigurera **[!UICONTROL Schedule]** -avsnitt. [Lär dig schemalägga kampanjer](#schedule)

När kampanjen är klar kan ni granska och publicera den. [Läs mer](#review-activate)

## Granska och aktivera en kampanj {#review-activate}

När kampanjen har konfigurerats måste du granska dess parameter och innehåll innan du aktiverar den. Följ dessa steg för att göra detta:

1. Klicka på **[!UICONTROL Review to activate]** för att visa en sammanfattning av kampanjen.

   Sammanfattningen gör att du kan ändra kampanjen om det behövs och kontrollera om någon parameter är felaktig eller saknas.

   >[!IMPORTANT]
   >
   >Om fel uppstår kan du inte aktivera kampanjen. Åtgärda felen innan du fortsätter.

   ![](assets/create-campaign-alerts.png)

1. Kontrollera att kampanjen är korrekt konfigurerad och klicka sedan på **[!UICONTROL Activate]**.

   ![](assets/create-campaign-review.png)

1. Kampanjen är nu aktiverad. Dess status är **[!UICONTROL Live]**, eller **[!UICONTROL Scheduled]** om du angav ett startdatum. [Läs mer om kampanjstatus](get-started-with-campaigns.md#statuses).

   Meddelandet som konfigurerats i kampanjen skickas omedelbart eller på det angivna datumet.

   >[!NOTE]
   >
   >The **[!UICONTROL Completed]** status tilldelas automatiskt en kampanj 3 dagar efter att den har aktiverats eller vid kampanjens slutdatum om den har ett återkommande körningsfel.
   >
   >Om inget slutdatum har angetts kommer kampanjen att behålla **[!UICONTROL Live]** status. Om du vill ändra den måste du stoppa kampanjen manuellt. [Lär dig stoppa en kampanj](modify-stop-campaign.md)

1. När en kampanj har aktiverats kan du när som helst kontrollera dess information genom att öppna den. Sammanfattningen gör att du kan få statistik om antalet målprofiler och levererade och misslyckade åtgärder.

   Du kan även få ytterligare statistik i dedikerade rapporter genom att klicka på **[!UICONTROL Reports]** -knappen. [Läs mer](../reports/campaign-global-report.md)

   ![](assets/create-campaign-summary.png)

## Schemalägg en kampanj {#schedule}

Som standard börjar kampanjer när de har aktiverats manuellt och avslutas så snart meddelandet har skickats en gång.

Du kan definiera hur ofta kampanjens meddelande ska skickas. Om du vill göra det använder du **[!UICONTROL Action triggers]** alternativ på skärmen för att skapa kampanjer för att ange om kampanjen ska köras varje dag, varje vecka eller varje månad.

Om du inte vill genomföra kampanjen direkt efter aktiveringen kan du ange ett datum och en tidpunkt då meddelandet ska skickas med **[!UICONTROL Campaign start]** alternativ. The  **[!UICONTROL Campaign end]** kan du ange när en återkommande kampanj ska sluta köras.

![](assets/create-campaign-schedule.png)
