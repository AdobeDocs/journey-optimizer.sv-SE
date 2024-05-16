---
title: Använd skräppostrapport
description: Lär dig hur du använder skräppostrapport.
feature: Preview
role: User
level: Beginner
badge: label="Beta"
hide: true
hidefromtoc: true
exl-id: 9ab43b14-41cf-49f1-bdcf-6fee58db5000
source-git-commit: 8dacf28f4c3217a57e648b3c80e1724d9794c9ea
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Rapport om skräppost {#spam-report}

[!DNL Journey Optimizer] Med kan du kontrollera hur ditt innehåll fungerar mot skräppostfiltrering och se till att dina meddelanden hamnar i dina kunders inkorgar - inte i skräppost.

När du redigerar eller förhandsgranskar ditt e-postinnehåll **[!UICONTROL Spam report]** ger poäng och råd för att förbättra poängen för varje enskild post i listan.

Detta gör att du kan avgöra om ett meddelande löper risk att betraktas som skräppost av de antispam-verktyg som används vid mottagande och vidta åtgärder om så inte är fallet. Många e-postinkorgsleverantörer använder verktyg som en del av sin process för skräppostfiltrering. Att skicka e-postmeddelanden med dåligt resultat kan få stor effekt på leveransförmågan.


>[!CAUTION]
>
>* Den här funktionen är för närvarande endast tillgänglig som en privat betaversion.
>
>* För närvarande kan skräppostrapportanalysen bara utföras för innehåll på engelska.
>
>* >
>Skräppostrapporten är informativ och förhindrar inte att meddelanden med dåligt resultat skickas.

Så här öppnar du **[!UICONTROL Spam report]** följer du stegen nedan.

1. Från **[!UICONTROL Simulate]** klickar du på **[!UICONTROL Spam report]** -knappen.

   ![](assets/spam-report-button.png)

<!--
    You can also open the [Email Designer](../email/content-from-scratch.md), click the **[!UICONTROL More]** button and select **[!UICONTROL Check spam score]** from the menu.

    ![](assets/spam-report-check-score.png)
-->

1. En skräppostkontroll utförs automatiskt och **[!UICONTROL Spam report]** visas resultatet. Det visar hur ditt innehåll fungerar i fråga om brödlayout, struktur, bildstorlek, utlösarord för skräppost, om sådana finns, osv.

   ![](assets/spam-report-high-score.png)

1. Kontrollera poängen och beskrivningarna för varje objekt.

   Ju lägre poäng, desto bättre. Om poängen är högre än 5 visas en varning: den anger att vissa meddelanden kan blockeras eller markeras som skräppost när de tas emot.

1. Om du anser att vissa element kan förbättras utifrån den poängen kan du redigera innehållet i [E-postdesigner](../email/content-from-scratch.md) och gör nödvändiga uppdateringar.

1. När du är klar går du tillbaka till **[!UICONTROL Spam report]** för att säkerställa att poängen har förbättrats.

   ![](assets/spam-report-low-score.png)

<!--You can also check the message's alerts for warnings on potential risk of spam detection. Follow the steps below.

1. Click the **[!UICONTROL Alerts]** button on top right of the screen. [Learn more on email alerts](../email/create-email.md#check-email-alerts)

1. If **[!UICONTROL Spam checker alert]** is displayed, you should check your content for a potential risk of spam using the **[!UICONTROL Spam report]** feature as detailed above.

    ![](assets/spam-report-alert.png)
-->
