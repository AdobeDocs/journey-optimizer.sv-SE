---
title: Använd skräppostrapport
description: Lär dig hur du använder skräppostrapport.
feature: Preview
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: b6872806b3961bb2afbfc03999d984384492cc6d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Använd skräppostrapport {#spam-report}

>[!AVAILABILITY]
>
>Rapportfunktionen för skräppost är för närvarande tillgänglig som betaversion för endast utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

[!DNL Journey Optimizer] Med kan du kontrollera hur ditt innehåll fungerar mot skräppostfiltrering och se till att dina meddelanden hamnar i dina kunders inkorgar - inte i skräppost.

>[!CAUTION]
>
>* Den här funktionen är för närvarande bara tillgänglig för e-postkanalen.
>
>* För närvarande kan skräppostrapportanalysen bara utföras för innehåll på engelska.

När du redigerar eller förhandsgranskar ditt innehåll visas **[!UICONTROL Spam report]** ger poäng och råd för att förbättra poängen för varje enskild post i listan.

Detta gör att du kan avgöra om ett meddelande löper risk att betraktas som skräppost av de antispam-verktyg som används vid mottagande och vidta åtgärder om så inte är fallet.

>[!CAUTION]
>
>Spam-rapporten innehåller endast indikationer och varningar. Observera att du inte hindras från att skicka meddelanden om skräppostrapporten anger att ditt innehåll betraktas som skräppost. Det är ditt val att agera utifrån poängen och föreslå förbättringar.

Använd **[!UICONTROL Spam report]** följer du stegen nedan.

<!--For example spam scoring tool can tell that there are too many Images compared to the text. Retailers tend to do this even though the spam score gets worse because the content is more engaging.-->

<!--Michael, who is a marketer with NIKE works along with Tara from testing team to ensure that the emails being sent as part of the campaign/journey don't get categorised as SPAM.

They need an integration within AJO's marketing system to show how the curated content is doing against different SPAM compliance pillars like for SPAM trigger words, HTML Body content and layout, subject line etc.

They should be able to get scores for each individual items as shown by market standard SPAM filtering tools like Spam Assassin, Symantec etc.

They should also get suggestions on how to improve the score better to be confident that the messages don't get categorised as spam.-->

1. Från **[!UICONTROL Simulate]** klickar du på **[!UICONTROL Spam report]** -knappen.

   ![](assets/spam-report-button.png)

<!--
    You can also open the [Email Designer](../email/content-from-scratch.md), click the **[!UICONTROL More]** button and select **[!UICONTROL Check spam score]** from the menu.

    ![](assets/spam-report-check-score.png)
-->

1. En skräppostkontroll utförs automatiskt och **[!UICONTROL Spam report]** visas resultatet. Det visar hur ditt innehåll fungerar i fråga om brödlayout, struktur, bildstorlek, utlösarord för skräppost, om sådana finns, osv.

   ![](assets/spam-report-high-score.png)

1. Kontrollera poängen och beskrivningarna för varje objekt.

   Om poängen är högre än 5 visas en varning. Det anger att vissa meddelanden kan blockeras eller markeras som skräppost med skräppostverktyg när de tas emot.

1. Om du anser att vissa element kan förbättras baserat på den poängen går du till ditt innehåll med [E-postdesigner](../email/content-from-scratch.md) och gör de uppdateringar som behövs.

1. När du är klar går du tillbaka till **[!UICONTROL Spam report]** för att säkerställa att poängen har förbättrats.

   ![](assets/spam-report-low-score.png)

<!--You can also check the message's alerts for warnings on potential risk of spam detection. Follow the steps below.

1. Click the **[!UICONTROL Alerts]** button on top right of the screen. [Learn more on email alerts](../email/create-email.md#check-email-alerts)

1. If **[!UICONTROL Spam checker alert]** is displayed, you should check your content for a potential risk of spam using the **[!UICONTROL Spam report]** feature as detailed above.

    ![](assets/spam-report-alert.png)
-->



