---
title: Välj testprofiler
description: Lär dig hur du väljer testprofiler för att förhandsgranska och testa innehåll.
feature: Preview, Proofs
role: User
level: Beginner
exl-id: c51e4089-7f51-437d-a5ed-de10bab46cf8
source-git-commit: 95a6d032808bc735a27a98dcb61efefa93cf5047
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Välj testprofiler {#select-test-profiles}

>[!CONTEXTUALHELP]
>id="ajo_preview_test_profiles"
>title="Använd testprofiler för att kontrollera innehållet"
>abstract="Använd testprofiler för att förhandsgranska och testa innehållet. Om du har lagt till anpassade fält kan du kontrollera hur de visas med testprofildata."

Testprofiler är ytterligare mottagare som inte matchar de definierade målinriktningskriterierna. [Lär dig skapa testprofiler](../audience/creating-test-profiles.md)

Innan du använder testprofiler för att testa innehållet måste du först markera dem. Följ dessa steg för att göra detta:

1. Klicka på knappen **[!UICONTROL Simulate content]** på skärmen Redigera innehåll i ditt meddelande eller i e-post-Designer och välj **[!UICONTROL Simulate content]**.

1. Klicka på knappen **[!UICONTROL Manage test profiles]** och markera sedan det namnutrymme som ska användas för att identifiera testprofiler genom att klicka på markeringsikonen **[!UICONTROL Identity namespace]** . [Läs mer om Adobe Experience Platform identitetsnamnutrymmen](../audience/get-started-identity.md).

   I exemplet nedan använder vi namnutrymmet **Email**.

   ![](../email/assets/previewselect-namespace.png)

1. Använd sökfältet för att hitta namnutrymmet, markera det och klicka på **[!UICONTROL Select]**

   ![](../email/assets/preview-email-namespace.png)

1. I fältet **[!UICONTROL Identity value]** anger du värdet (här e-postadressen) för att identifiera testprofilen och klickar på **[!UICONTROL Add profile]**.

   <!--![](assets/preview-identity-value.png)-->

1. Om du har lagt till personalisering i ditt meddelande lägger du till andra profiler så att du kan testa olika varianter av meddelandet beroende på profildata. När du har lagt till profiler visas de under de valda fälten.

   ![](../email/assets/preview-profile-list.png)

   Baserat på elementen för meddelandeanpassning visar den här listan data för varje testprofil i de relaterade kolumnerna.

>[!NOTE]
>
>Utöver testprofiler kan du i [!DNL Journey optimizer] även testa olika varianter av ditt innehåll genom att förhandsgranska det och skicka korrektur med exempelindata som har överförts från en CSV-/JSON-fil, eller lagts till manuellt. [Lär dig hur du simulerar innehållsvariationer](../test-approve/simulate-sample-input.md)
