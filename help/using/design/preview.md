---
title: Förhandsgranska meddelanden och skicka korrektur
description: Lär dig hur du förhandsgranskar och testar meddelanden
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: f2c2a360-a4b2-4416-bbd0-e27dd014e4ac
source-git-commit: 38addfd8b2f81991616ae93b6268fa1415fe80d2
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 0%

---

# Förhandsgranska och testa dina meddelanden{#preview-and-proof}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du infogade [personaliserat innehåll](../personalization/personalize.md)kan du kontrollera hur det här innehållet visas i meddelandet och dra nytta av testprofildata.

Om du vill identifiera eventuella fel i e-postinnehåll eller personaliseringsinställningar skickar du korrektur för att testa profiler. Ett korrektur ska skickas varje gång en ändring görs för att validera det senaste innehållet.

>[!CAUTION]
>
>Du måste ha testprofiler tillgängliga för att kunna förhandsgranska meddelanden och skicka korrektur.
>
>Lär dig hur du skapar testprofiler i [den här sidan](../segment/creating-test-profiles.md).

Om du vill testa ditt meddelandeinnehåll måste du:

* [välj testprofiler](#select-test-profiles)
* [kontrollera meddelandets förhandsgranskning](#preview-your-messages)

Då kan du [skicka korrektur](#send-proofs) till testprofilerna.

Dessutom kan du **Litmus** konto till [!DNL Journey Optimizer] för att omedelbart förhandsgranska **e-poståtergivning** i vanliga e-postklienter. Sedan kan ni se till att e-postinnehållet ser bra ut och fungerar som det ska i alla inkorgar. Lär dig hur du låser upp förhandsvisningar för Litmus-e-post i [det här avsnittet](#email-rendering)

>[!CAUTION]
>
>När du förhandsgranskar ett meddelande eller skickar korrektur visas endast profilpersonaliseringsdata. Personalisering som bygger på kontextdata, t.ex. händelseinformation, kan bara testas i samband med en resa. Lär dig hur du testar personalisering i [det här användningsfallet](../personalization/personalization-use-case.md).

➡️ [Lär dig hur du förhandsgranskar, korrekturläser och publicerar e-postmeddelanden i den här videon](#video-preview)

## Välj testprofiler{#select-test-profiles}

>[!CONTEXTUALHELP]
>id="ac_preview_testprofiles"
>title="Förhandsgranska och testa dina meddelanden"
>abstract="När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/validate/preview.html?lang=en#email-rendering" text="E-poståtergivning"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/validate/preview.html?lang=en#preview-your-messages" text="Förhandsgranskning"

Använd [Testprofiler](../segment/creating-test-profiles.md) om du vill ange fler mottagare som inte matchar de definierade målinriktningskriterierna som mål.

Så här väljer du testprofiler:

1. I meddelandegränssnittet eller i e-postdesignern klickar du på **[!UICONTROL Show preview]** för att komma åt valet av testprofil.

   ![](assets/email-preview-button.png)

1. Markera namnutrymmet som ska användas för att identifiera testprofiler genom att klicka på **[!UICONTROL Identity namespace]** markeringsikon.

   ![](assets/previewselect-namespace.png)

   Läs mer om Adobe Experience Platform identitetsnamnutrymmen [i det här avsnittet](../segment/get-started-identity.md).

   I exemplet nedan använder vi **E-post** namnutrymme.

1. Använd sökfältet för att hitta namnutrymmet, markera det och klicka på **[!UICONTROL Select]**

   ![](assets/preview-email-namespace.png)

1. Ange värdet för att identifiera testprofilen och klicka på **[!UICONTROL Find test profile]**.

   ![](assets/preview-identity-value.png)

1. Om du har lagt till personalisering i ditt meddelande lägger du till andra profiler så att du kan testa olika varianter av meddelandet beroende på profildata. När du har lagt till profiler visas de under urvalsfälten.

   ![](assets/preview-profile-list.png)

   Baserat på elementen för meddelandeanpassning visar den här listan data för varje testprofil i de relaterade kolumnerna.

## Förhandsgranska meddelanden{#preview-your-messages}

En gång [testprofiler](#select-test-profiles) om du har valt det här alternativet kan du förhandsgranska meddelanden och kontrollera innehåll.

1. Klicka på **[!UICONTROL Preview]** för att testa meddelandet.

1. Välj en testprofil. Du kan kontrollera de värden som är tillgängliga i kolumnerna. Använd höger-/vänsterpilarna för att bläddra bland data.

   ![](assets/preview-tab-select-profile.png)

1. Klicka på **[!UICONTROL Select data]** -ikonen ovanför listan för att lägga till eller ta bort kolumner.

   ![](assets/preview-select-data.png)

   I slutet av listan visas personaliseringsfält som är specifika för det aktuella meddelandet. I det här exemplet är profilens ort, förnamn och efternamn. Markera de fälten och se till att dessa värden är ifyllda i testprofilerna.

1. I meddelandeförhandsgranskningen ersätts anpassade element med de valda testprofildata.

   För det här meddelandet är till exempel både e-postinnehåll och e-postämne personliga:

   ![](assets/preview-test-profile.png)

1. Välj andra testprofiler om du vill förhandsgranska e-poståtergivningen för varje variant av meddelandet.

Om du vill förhandsgranska ett push-meddelande:

1. Växla till **[!UICONTROL Push]** från **[!UICONTROL Channels]** nedrullningsbar lista längst upp till höger i **[!UICONTROL Preview]** skärm.

   ![](assets/preview-select-channel.png)

1. Använd samma steg som beskrivs ovan för att välja en testprofil och välj typ av enhet för att förhandsgranska innehåll: **[!UICONTROL iOS]** eller **[!UICONTROL Android]**.

   ![](assets/preview-iOS.png)

1. I push-förhandsgranskningen används testprofildata i meddelandeinnehållet.

   För det här push-meddelandet är till exempel både rubrik och brödtext personliga:

   ![](assets/preview-android.png)

## Skicka korrektur{#send-proofs}

Ett korrektur är ett specifikt meddelande som gör att du kan testa ett meddelande innan det skickas till huvudmålgruppen. Mottagarna av beviset ansvarar för att godkänna meddelandet: återgivning, innehåll, personaliseringsinställningar, konfiguration.

En gång [testprofiler](#select-test-profiles) om du har valt det här alternativet kan du skicka korrektur.

1. I **[!UICONTROL Preview]** klickar du på **[!UICONTROL Send proof]** -knappen.

   ![](assets/send-proof-button.png)

1. Från **[!UICONTROL Send proof]** fönster, skriv in mottagarens e-postadress och klicka på **[!UICONTROL Add]** för att skicka beviset till dig själv eller medlemmar i din organisation.

   Observera att du kan lägga till upp till tio mottagare för korrekturleveransen.

   ![](assets/send-proof-button_2.png)

1. Välj sedan **Testprofiler** som kommer att användas för att anpassa meddelandeinnehållet.

   Varje mottagare får lika många meddelanden som antalet valda testprofiler. Om du till exempel har lagt till fem e-postmeddelanden till mottagare och valt tio testprofiler, skickar du femtio korrekturmeddelanden och varje mottagare får tio.

1. Du kan vid behov lägga till ett prefix till korrekturens ämnesrad. Endast alfanumeriska tecken och specialtecken, t.ex. . - _ ( ) [ ], tillåts som prefix till ämnesraden.

1. Klicka på **[!UICONTROL Send proof]**.

   ![](assets/send-proof-select.png)

1. Tillbaka i  **[!UICONTROL Preview]** klickar du på  **[!UICONTROL View proofs]** för att kontrollera status.

   ![](assets/send-proof-view.png)

Vi rekommenderar att du skickar korrektur efter varje ändring av meddelandeinnehållet.

>[!NOTE]
>
>I det korrektur som skickas till testprofilerna är länken till spegelsidan inte aktiv. Den aktiveras endast i de slutliga meddelandena.

## E-poståtergivning{#email-rendering}

Du kan använda **Litmus** konto till [!DNL Journey Optimizer] för att omedelbart förhandsgranska **e-poståtergivning** i vanliga e-postklienter.

Om du vill få åtkomst till funktionerna för e-poståtergivning måste du:

* Har ett Litmus-konto
* [Välj testprofiler](#select-test-profiles)

Följ sedan stegen nedan:

1. Klicka på knappen **[!UICONTROL Preview]** och väljer **[!UICONTROL Email rendering]** -fliken.

1. Klicka **Anslut ditt Litmus-konto** i det övre högra avsnittet.

   ![](assets/email-rendering-litmus.png)

1. Ange dina inloggningsuppgifter och logga in.

   ![](assets/email-rendering-credentials.png)

1. Klicka på **Kör test** om du vill generera förhandsgranskningar via e-post.

1. Kontrollera e-postinnehållet i vanliga dator-, mobil- och webbaserade klienter.

   ![](assets/email-rendering-previews.png)

>[!CAUTION]
>
>När du ansluter **Litmus** konto med [!DNL Journey Optimizer]godkänner du att testmeddelanden skickas till Litmus: När de väl har skickats hanteras dessa e-postmeddelanden inte längre av Adobe. Följaktligen gäller Litmus-principen för datalagring i dessa e-postmeddelanden, inklusive personaliseringsdata som kan inkluderas i dessa testmeddelanden.

## Instruktionsvideo{#video-preview}

Lär dig hur du testar e-poståtergivning i olika inkorgar, hur du förhandsgranskar anpassade e-postmeddelanden mot testprofiler, skickar korrektur och publicerar e-postmeddelanden.

>[!VIDEO](https://video.tv.adobe.com/v/334239?quality=12)
