---
title: Välj testprofiler
description: Lär dig hur du väljer testprofiler för att förhandsgranska och testa innehåll.
feature: Preview, Proofs
role: User
level: Beginner
source-git-commit: 6da7f4c8caa5a0a6cfda1e90d0c6cd4787c6afca
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

1. I fönstret Redigera innehåll i meddelandet eller i e-postdesignern klickar du på **[!UICONTROL Simulate content]** -knappen.

1. Klicka på **[!UICONTROL Manage test profiles]** och sedan markera det namnutrymme som ska användas för att identifiera testprofiler genom att klicka på **[!UICONTROL Identity namespace]** markeringsikon. [Läs mer om Adobe Experience Platform identitetsnamnutrymmen](../audience/get-started-identity.md).

   I exemplet nedan använder vi **E-post** namnutrymme.

   ![](../email/assets/previewselect-namespace.png)

1. Använd sökfältet för att hitta namnutrymmet, markera det och klicka på **[!UICONTROL Select]**

   ![](../email/assets/preview-email-namespace.png)

1. I **[!UICONTROL Identity value]** anger du värdet (här är e-postadressen) för att identifiera testprofilen och klickar på **[!UICONTROL Add profile]**.

   <!--![](assets/preview-identity-value.png)-->

1. Om du har lagt till personalisering i ditt meddelande lägger du till andra profiler så att du kan testa olika varianter av meddelandet beroende på profildata. När du har lagt till profiler visas de under de valda fälten.

   ![](../email/assets/preview-profile-list.png)

   Baserat på elementen för meddelandeanpassning visar den här listan data för varje testprofil i de relaterade kolumnerna.
