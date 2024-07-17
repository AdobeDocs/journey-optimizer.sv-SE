---
title: Välj testprofiler
description: Lär dig hur du väljer testprofiler för att förhandsgranska och testa innehåll.
feature: Preview, Proofs
role: User
level: Beginner
exl-id: c51e4089-7f51-437d-a5ed-de10bab46cf8
source-git-commit: feae2cb9d0bed35f12eb117cf2969c9290ebc06f
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Välj testprofiler {#select-test-profiles}

>[!CONTEXTUALHELP]
>id="ajo_preview_test_profiles"
>title="Använd testprofiler för att kontrollera innehållet"
>abstract="Använd testprofiler för att förhandsgranska och testa innehållet. Om du har lagt till anpassade fält kan du kontrollera hur de visas med testprofildata."

Innan du förhandsgranskar eller testar innehållet måste du först välja testprofiler, som är ytterligare mottagare som inte matchar de definierade målinriktningsvillkoren. [Lär dig skapa testprofiler](../audience/creating-test-profiles.md)

Så här väljer du testprofiler:

1. Klicka på knappen **[!UICONTROL Simulate content]** på skärmen Redigera innehåll i ditt meddelande eller i e-post-Designer.

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
