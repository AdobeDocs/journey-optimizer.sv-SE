---
title: Förhandsgranska meddelanden och skicka korrektur
description: Lär dig hur du förhandsgranskar och testar meddelanden
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: ff36b68efa639870b68997fca86ee1be24e2cc79
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 0%

---

# Förhandsgranska och testa dina meddelanden{#preview-and-proof}

När meddelandeinnehållet har definierats kan du använda testprofiler för att förhandsgranska och testa det. Om du infogade [anpassat innehåll](personalization/personalize.md) kan du kontrollera hur det här innehållet visas i meddelandet genom att utnyttja testprofildata.

Om du vill identifiera eventuella fel i e-postinnehåll eller personaliseringsinställningar skickar du korrektur för att testa profiler. Ett korrektur ska skickas varje gång en ändring görs för att validera det senaste innehållet.

>[!CAUTION]
>
>Du måste ha testprofiler tillgängliga för att kunna förhandsgranska meddelanden och skicka korrektur.
>
>Lär dig hur du skapar testprofiler i [den här sidan](building-journeys/creating-test-profiles.md).

Om du vill testa ditt meddelandeinnehåll måste du:

* [välj testprofiler](#select-test-profiles)
* [kontrollera meddelandets förhandsgranskning](#preview-your-messages)

Du kan sedan [skicka korrektur](#send-proofs) till dina testprofiler.

Använd dessutom ditt **Litmus**-konto i [!DNL Journey Optimizer] för att omedelbart förhandsgranska din **e-poståtergivning** i vanliga e-postklienter. Sedan kan ni se till att e-postinnehållet ser bra ut och fungerar som det ska i alla inkorgar. Lär dig hur du låser upp förhandsvisningar för Litmus-e-post i [det här avsnittet](#email-rendering)

>[!CAUTION]
>
>När du förhandsgranskar ett meddelande eller skickar korrektur visas endast profilpersonaliseringsdata. Personalisering som bygger på kontextdata, t.ex. händelseinformation, kan bara testas i samband med en resa. Lär dig hur du testar personalisering i [det här användningsexemplet](personalization/personalization-use-case.md).

![](assets/do-not-localize/how-to-video.png) [Lär dig hur du förhandsgranskar, korrekturläser och publicerar e-postmeddelanden i den här videon](#video-preview)

## Välj testprofiler{#select-test-profiles}

Använd [Testa profiler](building-journeys/creating-test-profiles.md) för att ange ytterligare mottagare som inte matchar de definierade målinriktningsvillkoren som mål.

Så här väljer du testprofiler:

1. Klicka på knappen **[!UICONTROL Show preview]** i meddelandegränssnittet eller i e-postdesignern för att komma åt valet av testprofil.

   ![](assets/email-preview-button.png)

1. Markera det namnutrymme som ska användas för att identifiera testprofiler genom att klicka på markeringsikonen **[!UICONTROL Identity namespace]**.

   ![](assets/previewselect-namespace.png)

   Läs mer om Adobe Experience Platform identitetsnamnutrymmen [i det här avsnittet](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=en#getting-started).

   I exemplet nedan använder vi namnutrymmet **Email**.

1. Använd sökfältet för att hitta namnutrymmet, markera det och klicka på **[!UICONTROL Select]**

   ![](assets/preview-email-namespace.png)

1. Ange värdet för att identifiera testprofilen och klicka på **[!UICONTROL Find test profile]**.

   ![](assets/preview-identity-value.png)

1. Om du har lagt till personalisering i ditt meddelande lägger du till andra profiler så att du kan testa olika varianter av meddelandet beroende på profildata. När du har lagt till profiler visas de under urvalsfälten.

   ![](assets/preview-profile-list.png)

   Baserat på elementen för meddelandeanpassning visar den här listan data för varje testprofil i de relaterade kolumnerna.

## Förhandsgranska meddelanden{#preview-your-messages}

När [testprofiler](#select-test-profiles) har valts kan du förhandsgranska dina meddelanden och kontrollera innehållet.

1. Klicka på fliken **[!UICONTROL Preview]** för att testa meddelandet.

1. Välj en testprofil. Du kan kontrollera de värden som är tillgängliga i kolumnerna. Använd höger-/vänsterpilarna för att bläddra bland data.

   ![](assets/preview-tab-select-profile.png)

1. Klicka på ikonen **[!UICONTROL Select data]** ovanför listan för att lägga till eller ta bort kolumner.

   ![](assets/preview-select-data.png)

   I slutet av listan visas personaliseringsfält som är specifika för det aktuella meddelandet. I det här exemplet är profilens ort, förnamn och efternamn. Markera de fälten och se till att dessa värden är ifyllda i testprofilerna.

1. I meddelandeförhandsgranskningen ersätts anpassade element med de valda testprofildata.

   För det här meddelandet är till exempel både e-postinnehåll och e-postämne personliga:

   ![](assets/preview-test-profile.png)

1. Välj andra testprofiler om du vill förhandsgranska e-poståtergivningen för varje variant av meddelandet.

Om du vill förhandsgranska ett push-meddelande:

1. Växla till kanalen **[!UICONTROL Push]** från listrutan **[!UICONTROL Channels]** högst upp till vänster på skärmen **[!UICONTROL Preview]**.

   ![](assets/preview-select-channel.png)

1. Använd samma steg som beskrivs ovan för att välja en testprofil och välj typ av enhet för att förhandsgranska innehåll: **[!UICONTROL iOS]** eller **[!UICONTROL Android]**

   ![](assets/preview-iOS.png)

1. I push-förhandsgranskningen används testprofildata i meddelandeinnehållet.

   För det här push-meddelandet är till exempel både rubrik och brödtext personliga:

   ![](assets/preview-android.png)

## Skicka korrektur{#send-proofs}

Ett korrektur är ett specifikt meddelande som gör att du kan testa ett meddelande innan det skickas till huvudmålgruppen. Mottagarna av beviset ansvarar för att godkänna meddelandet: återgivning, innehåll, personaliseringsinställningar, konfiguration.

När [testprofiler](#select-test-profiles) har valts kan du skicka korrektur.

1. Klicka på knappen **[!UICONTROL Send proof]** på skärmen **[!UICONTROL Preview]**.

   ![](assets/send-proof-button.png)

1. Välj de testprofiler som ska ta emot korrekturet och klicka på **[!UICONTROL Send proof]**. Du kan vid behov lägga till ett prefix till korrekturens ämnesrad.

   ![](assets/send-proof-select.png)

1. Klicka på knappen **[!UICONTROL View proofs]** på skärmen **[!UICONTROL Preview]** för att kontrollera status.

   ![](assets/send-proof-view.png)

Du måste skicka korrektur när du har ändrat meddelandeinnehållet.

>[!NOTE]
>
> I det korrektur som skickas till testprofilerna är länken till spegelsidan inte aktiv. Den aktiveras endast i de slutliga meddelandena.

## E-poståtergivning{#email-rendering}

Du kan använda ditt **Litmus**-konto i [!DNL Journey Optimizer] för att omedelbart förhandsgranska din **e-poståtergivning** i vanliga e-postklienter.

Om du vill få åtkomst till funktionerna för e-poståtergivning måste du:

* Har ett Litmus-konto
* [Välj testprofiler](#select-test-profiles)

Följ sedan stegen nedan:

1. Klicka på knappen **[!UICONTROL Preview]** i e-postdesignern och välj fliken **[!UICONTROL Email rendering]**.

1. Klicka på **Anslut ditt Litmus-konto** i det övre högra avsnittet.

   ![](assets/email-rendering-litmus.png)

1. Ange dina inloggningsuppgifter och logga in.

   ![](assets/email-rendering-credentials.png)

1. Klicka på knappen **Kör test** om du vill generera förhandsgranskningar via e-post.

1. Kontrollera e-postinnehållet i vanliga dator-, mobil- och webbaserade klienter.

   ![](assets/email-rendering-previews.png)

>[!CAUTION]
>
>När du ansluter ditt **Litmus**-konto med [!DNL Journey Optimizer] godkänner du att testmeddelanden skickas till Litmus: När de väl har skickats hanteras dessa e-postmeddelanden inte längre av Adobe. Följaktligen gäller Litmus-principen för datalagring i dessa e-postmeddelanden, inklusive personaliseringsdata som kan inkluderas i dessa testmeddelanden.

## Instruktionsvideo{#video-preview}

Lär dig hur du testar e-poståtergivning i olika inkorgar, hur du förhandsgranskar anpassade e-postmeddelanden mot testprofiler, skickar korrektur och publicerar e-postmeddelanden.

>[!VIDEO](https://video.tv.adobe.com/v/334239?quality=12)
