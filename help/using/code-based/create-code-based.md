---
title: Skapa kodbaserade upplevelser
description: Lär dig skapa kodbaserade upplevelser i Journey Optimizer
feature: Code-based Experiences
topic: Content Management
role: User
level: Experienced
exl-id: 25c2c448-9380-47b0-97c5-16d9afb794c5
source-git-commit: 3c9952f2e57c45d5bbd78d70ae7d401bc4555abe
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 1%

---

# Skapa kodbaserade upplevelser {#create-code-based}

Ingår [!DNL Journey Optimizer] kan ni bara skapa kodbaserade upplevelser i **kampanjer**.

Garantier och rekommendationer finns i [den här sidan](code-based-prerequisites.md).

>[!AVAILABILITY]
>
>För närvarande är den kodbaserade upplevelsekanalen inte tillgänglig för organisationer som har köpt Adobe **Hälsovårdssköld** och **Sköld för skydd av privatlivet och säkerheten** tilläggserbjudanden.

## Skapa en kodbaserad kampanj {#create-code-based-campaign}

Följ stegen nedan för att börja skapa en kodbaserad upplevelse genom en kampanj.

1. Skapa en kampanj. [Läs mer](../campaigns/create-campaign.md)

1. Välj **[!UICONTROL Code-based experience]** åtgärd.

1. Ange den kodbaserade upplevelseytan. [Läs mer](#surface-definition)

   ![](assets/code-based-campaign-surface.png)

   >[!CAUTION]
   >
   >Kontrollera att den yt-URI som används i din kodbaserade kampanj matchar den som används i din egen implementering. Annars levereras inte ändringarna.

1. Välj **[!UICONTROL Create]**.

1. Slutför stegen för att skapa en kampanj, t.ex. kampanjegenskaperna, [publik](../audience/about-audiences.md)och [schema](../campaigns/create-campaign.md#schedule). Mer information om hur du konfigurerar en kampanj finns i [den här sidan](../campaigns/get-started-with-campaigns.md).

1. Redigera ditt innehåll med uttrycksredigeraren. [Läs mer](#edit-code)

   ![](assets/code-based-campaign-edit-content.png)

## Redigera kodinnehållet {#edit-code}

>[!CONTEXTUALHELP]
>id="ajo_code_based_experience"
>title="Använda uttrycksredigeraren"
>abstract="Infoga och redigera koden som du vill leverera som en del av den här kodbaserade upplevelseåtgärden."
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions.html" text="Kom igång med uttrycksredigeraren"

1. Välj **[!UICONTROL Edit code]**.

   ![](assets/code-based-campaign-edit-code.png)

1. The [Uttrycksredigerare](../personalization/personalization-build-expressions.md) öppnas. Det är ett gränssnitt för att skapa icke-visuella upplevelser som gör att du kan skapa koden.

1. Du kan växla mellan redigeringsläget HTML och JSON, och vice versa.

   ![](assets/code-based-campaign-code-editor.png)

   >[!CAUTION]
   >
   >Om du ändrar redigeringsläget förlorar du all aktuell kod, så se till att växla läge innan du börjar redigera.

1. Ange koden efter behov. Du kan använda [!DNL Journey Optimizer] Uttrycksredigeraren med alla dess funktioner för personalisering och redigering. [Läs mer](../personalization/personalization-build-expressions.md)

1. Du kan lägga till HTML eller JSON-uttrycksfragment om det behövs. [Lär dig mer](../personalization/use-expression-fragments.md)

   Du kan också spara en del av kodinnehållet som fragment. [Lär dig mer](../content-management/fragments.md#save-as-expression-fragment)

<!--
1. In code-based campaigns, you can use the experience decisioning feature. Select the **[!UICONTROL Decisions]** icon from the left bar and click **[!UICONTROL Create decision]**. [Learn more](../experience-decisioning/create-decision.md)

    ![](assets/code-based-campaign-create-decision.png)

    >[!NOTE]
    >
    >The experience decisioning feature is currently available as a beta to select users only.
-->

1. Klicka **[!UICONTROL Save and close]** för att bekräfta dina ändringar.

Så snart utvecklaren gör ett API- eller SDK-anrop för att hämta innehåll för den valda ytan tillämpas ändringarna på din webbsida eller app.

## Testa den kodbaserade kampanjen {#test-code-based-campaign}

>[!CONTEXTUALHELP]
>id="ajo_code_based_preview"
>title="Förgranska din kodbaserade upplevelse"
>abstract="Få en simulering av hur er kodbaserade upplevelse kommer att se ut."

Följ stegen nedan för att visa en förhandsgranskning av din ändrade kodbaserade upplevelse. Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehållet finns i [Förhandsgranska och testa din innehållssida](../content-management/preview-test.md).

>[!CAUTION]
>
>Du måste ha testprofiler tillgängliga för att simulera vilka erbjudanden som ska levereras till dem. Lär dig hur [skapa testprofiler](../audience/creating-test-profiles.md).

1. Välj från antingen uttrycksredigeraren eller redigeringsskärmen för innehåll **[!UICONTROL Simulate content]**.

   ![](assets/code-based-campaign-simulate.png)

1. Klicka **[!UICONTROL Manage test profiles]** om du vill välja en eller flera testprofiler.

1. En förhandsgranskning av den ändrade kodbaserade upplevelsen visas.

<!--
    ![](assets/code-based-designer-preview.png)

    You can also open it in the default browser, or copy the test URI to paste it in any browser. This allows you to share the link with your team and stakeholders who will be able to preview the new web experience in any browser before the campaign goes live.

    When copying the test URI, the content displayed is the one personalized for the test profile used when the content simulation was generated in [!DNL Journey Optimizer].-->

## Aktivera den kodbaserade kampanjen {#activate-code-based-campaign}

När du har definierat din kodbaserade kampanj och redigerat innehållet som du vill med [kodbaserad redigerare](#edit-code)kan du granska och aktivera den. Följ stegen nedan.

>[!NOTE]
>
>Du kan också förhandsgranska kampanjinnehållet innan du aktiverar det. [Läs mer](#test-code-based-campaign)

1. Välj **[!UICONTROL Review to activate]**.

   ![](assets/code-based-campaign-review.png)

1. Kontrollera och redigera vid behov innehåll, egenskaper, yta, målgrupp och schema.

1. Välj **[!UICONTROL Activate]**.

   ![](assets/code-based-campaign-activate.png)

   >[!NOTE]
   >
   >När du klickat **[!UICONTROL Activate]** kan det ta upp till en minut innan kodbaserade kampanjändringar blir tillgängliga live på er plats.

Din kodbaserade kampanj tar **[!UICONTROL Live]** och nu visas för den valda publiken. Alla mottagare av kampanjen kan se dina ändringar.

>[!NOTE]
>
>Om du har definierat ett schema för din kodbaserade kampanj har den **[!UICONTROL Scheduled]** status tills startdatumet och starttiden nås.
>
>Om du aktiverar en kodbaserad kampanj som påverkar samma platser som en annan kampanj som redan är aktiv, tillämpas alla ändringar på dina platser.

Läs mer om att aktivera kampanjer i [det här avsnittet](../campaigns/review-activate-campaign.md).

## Stoppa en kodbaserad kampanj {#stop-code-based-campaign}

När en kodbaserad kampanj är aktiv kan ni stoppa den för att hindra publiken från att se ändringarna. Följ stegen nedan.

1. Välj en livekampanj i listan.

1. I den övre menyn väljer du **[!UICONTROL Stop campaign]**.

   ![](assets/code-based-campaign-stop.png)

1. De ändringar du har lagt till visas inte längre för den målgrupp du har definierat.

>[!NOTE]
>
>När en kodbaserad kampanj har stoppats kan du inte redigera eller aktivera den igen. Du kan bara duplicera den och aktivera den duplicerade kampanjen.

## Kodbaserade kampanjrapporter

Du kan få tillgång till kodbaserade kampanjrapporter från kampanjsammanfattningsskärmen.

Globala rapporter visar händelser som inträffade för minst två timmar sedan och täcker händelser under en vald tidsperiod. Live-rapporter fokuserar på händelser som har inträffat under de senaste 24 timmarna, med ett tidsintervall på minst två minuter från händelseförekomsten.

### Kodbaserad live-rapport {#live-report-code-based}

Från er kampanj **[!UICONTROL Live report]**, **[!UICONTROL Code-based experience]** -fliken innehåller information om huvudinformationen i förhållande till dina program eller webbsidor. [Läs mer i live-rapporten](../reports/campaign-live-report.md)

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för den kodbaserade upplevelserapporten.

The **[!UICONTROL Code-based experience performance]** KPI:er detaljerar den viktigaste informationen i relation till besökarnas engagemang med era kodbaserade upplevelser, som:

* **[!UICONTROL Impressions]**: totalt antal upplevelser som levereras till alla användare.

* **[!UICONTROL Interactions]**: totalt antal ärenden för din app/sida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

The **[!UICONTROL Code-based experience summary]** diagram visar hur upplevelserna har utvecklats (visningar, unika intryck och interaktioner) de senaste 24 timmarna.

<!--The **[!UICONTROL Interactions by element]** table details the main information relative to your visitors' engagement with the various elements on your app/pages.-->
+++

### Kodbaserad global rapport {#global-report-code-based}

Kodbaserad global kampanjrapport kan nås direkt från din kampanj med **[!UICONTROL View report]** -knappen. [Läs mer om global rapport](../reports/campaign-global-report.md)

Från er kampanj **[!UICONTROL Global report]**, **[!UICONTROL Code-based experience]** -fliken innehåller information om huvudinformationen i förhållande till dina program eller webbsidor.

![](assets/code-based-campaign-global-report.png)

<!--image-->

+++Läs mer om de olika mätvärden och widgetar som är tillgängliga för den kodbaserade upplevelserapporten.

The **[!UICONTROL Code-based experience performance]** Nyckeltal anger den viktigaste informationen i relation till besökarnas engagemang i era upplevelser, till exempel:

* **[!UICONTROL Unique impressions]**: antal unika användare som upplevelsen levererades till.

* **[!UICONTROL Impressions]**: totalt antal upplevelser som levereras till alla användare.

* **[!UICONTROL Interactions]**: procent av engagemanget med din app/sida. Detta inkluderar alla åtgärder som användaren utför, t.ex. klickningar eller andra interaktioner.

The **[!UICONTROL Code-based experience summary]** diagram visar hur era upplevelser har utvecklats (unika intryck, visningar och interaktioner) under den aktuella perioden.

<!--The **[!UICONTROL Interactions by element]** table details the main information relative to your visitors' engagement with the various elements on your apps/pages.-->
+++

<!--
## How-to video{#video}

The video below shows how to create a code-based campaign, configure its properties, review, and publish it.

>[!VIDEO]()

-->
