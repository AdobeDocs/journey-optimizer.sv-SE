---
solution: Journey Optimizer
product: journey optimizer
title: Skapa ett SMS/MMS-meddelande
description: Lär dig skapa ett SMS/MMS-meddelande i Journey Optimizer
feature: SMS
topic: Content Management
role: User
level: Beginner
exl-id: 1f88626a-b491-4b36-8e3f-57f2b7567dd0
source-git-commit: 8a1ec5acef067e3e1d971deaa4b10cffa6294d75
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Skapa ett textmeddelande (SMS/MMS) {#create-sms}

>[!CONTEXTUALHELP]
>id="ajo_message_sms"
>title="Skapa ett textmeddelande"
>abstract="Om du vill skapa ett textmeddelande (SMS/MMS) lägger du till en SMS-åtgärd i en resa eller kampanj och börjar personalisera den med personaliseringsredigeraren."

Du kan utforma och skicka SMS- och MMS-meddelanden med Adobe Journey Optimizer. Du måste först lägga till en SMS-åtgärd på en resa eller i en kampanj och sedan definiera innehållet i textmeddelandet, enligt beskrivningen nedan. Adobe Journey Optimizer har också funktioner för att testa textmeddelanden innan de skickas, så att du kan kontrollera återgivning, anpassningsattribut och alla andra inställningar.

>[!NOTE]
>
>I enlighet med branschens standarder och bestämmelser måste alla SMS/MMS-marknadsföringsmeddelanden innehålla ett sätt för mottagarna att enkelt avbryta prenumerationen. För att göra detta kan SMS-mottagare svara med nyckelord för deltagande och avanmälan. [Lär dig hur du hanterar avanmälan](../privacy/opt-out.md#sms-opt-out-management-sms-opt-out-management)


## Lägga till ett textmeddelande {#create-sms-journey-campaign}

Bläddra bland flikarna nedan för att lära dig hur du lägger till ett textmeddelande (SMS/MMS) i en kampanj eller en resa.

>[!BEGINTABS]

>[!TAB Lägga till ett textmeddelande på en resa]

1. Öppna resan och dra och släpp en SMS-aktivitet från **Åtgärder** på paletten.

   ![](assets/sms_create_1.png)

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandeyta som ska användas.

   ![](assets/sms_create_2.png)

   Mer information om hur du konfigurerar en resa finns i [den här sidan](../building-journeys/journey-gs.md)

   The **[!UICONTROL Surface]** som standard är fältet förifyllt med den sista yta som användaren använder för den kanalen.

Nu kan du börja designa ditt SMS-meddelande via **[!UICONTROL Edit content]** som beskrivs nedan.

>[!TAB Lägga till ett textmeddelande i en kampanj]

1. Skapa en ny schemalagd eller API-utlöst kampanj, välj **[!UICONTROL SMS]** som din åtgärd och väljer **[!UICONTROL App surface]** att använda. Läs mer om SMS-konfiguration i [den här sidan](sms-configuration.md).

   ![](assets/sms_create_3.png)

1. Klicka **[!UICONTROL Create]**.

1. Från **[!UICONTROL Properties]** redigerar du Campaigns **[!UICONTROL Title]** och **[!UICONTROL Description]**.

   ![](assets/sms_create_4.png)

1. Klicka på **[!UICONTROL Select audience]** för att definiera målgruppen i listan över tillgängliga Adobe Experience Platform-målgrupper. [Läs mer](../audience/about-audiences.md).

1. I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera personer från den valda målgruppen. [Läs mer](../event/about-creating.md#select-the-namespace).

   ![](assets/sms_create_5.png)

1. Klicka **[!UICONTROL Create experiment]** för att börja konfigurera ert innehållsexperiment och skapa behandlingar för att mäta deras prestanda och identifiera det bästa alternativet för er målgrupp. [Läs mer](../campaigns/content-experiment.md)

1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra klickningar på länkar i SMS-meddelandet.

1. Kampanjer är utformade för att köras ett visst datum eller med en återkommande frekvens. Lär dig hur du konfigurerar **[!UICONTROL Schedule]** av kampanjen i [det här avsnittet](../campaigns/create-campaign.md#schedule).

1. Från **[!UICONTROL Action triggers]** väljer du **[!UICONTROL Frequency]** av SMS-meddelandet:

   * En gång
   * Dagligen
   * Vecka
   * Månad

Nu kan du börja designa textmeddelandets innehåll från **[!UICONTROL Edit content]** som beskrivs nedan.

>[!ENDTABS]

## Definiera ditt SMS-innehåll{#sms-content}

>[!CONTEXTUALHELP]
>id="ajo_message_sms_content"
>title="Definiera ditt SMS-innehåll"
>abstract="Anpassa och anpassa dina textmeddelanden (SMS/MMS) genom att använda personaliseringsredigeraren för att definiera innehållet och införliva dynamiska element."

Följ stegen nedan för att konfigurera ditt SMS-innehåll. Inställningarna för MMS finns i [det här avsnittet](#mms-content).

1. Klicka på **[!UICONTROL Edit content]** för att konfigurera textmeddelandets innehåll.

1. Klicka på **[!UICONTROL Message]** för att öppna personaliseringsredigeraren.

   ![](assets/sms-content.png)

1. Använd personaliseringsredigeraren för att definiera innehåll, lägga till personalisering och dynamiskt innehåll. Du kan använda alla attribut, till exempel profilnamnet eller stad. Du kan också definiera villkorliga regler. Bläddra till följande sidor om du vill veta mer om [personalisering](../personalization/personalize.md) och [dynamiskt innehåll](../personalization/get-started-dynamic-content.md) i personaliseringsredigeraren.

1. När du har definierat innehållet kan du lägga till spårade URL:er i meddelandet. Om du vill göra det går du till **[!UICONTROL Helper functions]** meny och välj **[!UICONTROL Helpers]**.

   Observera att för att kunna använda funktionen för förkortning av URL-adresser måste du först konfigurera en underdomän som sedan länkas till din yta. [Läs mer](sms-subdomains.md)

   >[!CAUTION]
   >
   > Om du vill komma åt och redigera SMS-underdomäner måste du ha **[!UICONTROL Manage SMS Subdomains]** behörighet i produktionssandlådan. Läs mer om behörigheter i [det här avsnittet](../administration/high-low-permissions.md).

   ![](assets/sms_tracking_1.png)

1. I **[!UICONTROL Helper functions]** meny, klicka **[!UICONTROL URL function]** och sedan **[!UICONTROL Add URL]**.

   ![](assets/sms_tracking_2.png)

1. I `originalUrl` klistra in den URL som du vill förkorta och klicka på **[!UICONTROL Save]**.

1. Klicka **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen. Nu kan du testa och kontrollera meddelandeinnehållet enligt [det här avsnittet](#sms-mms-test).

## Definiera ditt MMS-innehåll{#mms-content}

Du kan förbättra kommunikationen genom att skicka MMS-meddelanden (Multimedia Message Service), vilket möjliggör delning av media som videor, bilder, ljudklipp och GIF med mera. Dessutom kan MMS innehålla upp till 1 600 tecken i meddelandet.

>[!NOTE]
>
>* MMS-kanalen har några begränsningar som anges i [den här sidan](../start/guardrails.md#sms-guardrails).

Så här skapar du MMS-innehåll:

1. Skapa ett SMS enligt anvisningarna i [det här avsnittet](#create-sms-journey-campaign).

1. Redigera ditt SMS-innehåll enligt informationen i [det här avsnittet](#sms-content).

1. Aktivera alternativet MMS för att lägga till media i SMS-innehåll.

   ![](assets/sms_create_6.png)

1. Lägg till en **[!UICONTROL Title]** till era medier.

1. Ange URL-adressen till dina media i dialogrutan **[!UICONTROL Media]** fält.

   ![](assets/sms_create_7.png)

1. Klicka **[!UICONTROL Save]** och kontrollera meddelandet i förhandsgranskningen. Du kan nu testa och kontrollera meddelandeinnehållet enligt beskrivningen nedan.

## Testa och skicka meddelanden {#sms-mms-test}

Använd **[!UICONTROL Simulate content]** för att förhandsgranska textmeddelandeinnehåll, förkortade URL:er och anpassat innehåll.

![](assets/sms-content-preview.png)

När du har utfört testerna och validerat innehållet kan du skicka textmeddelandet till mottagarna. Dessa steg beskrivs i [den här sidan](send-sms.md)

När ni har skickat det kan ni mäta effekten av ert SMS i kampanjrapporten eller reserapporten. Mer information om rapportering finns i [det här avsnittet](../reports/campaign-global-report.md#sms-tab).

**Relaterade ämnen**

* [Förhandsgranska, testa och skicka ditt textmeddelande](send-sms.md)
* [Konfigurera SMS-kanal](sms-configuration.md)
* [SMS-/MMS-rapporter](../reports/journey-global-report.md#sms-global)
* [Lägg till ett meddelande i en resa](../building-journeys/journeys-message.md)
* [Lägg till ett meddelande i en kampanj](../campaigns/create-campaign.md)
