---
solution: Journey Optimizer
product: journey optimizer
title: Obligatorisk DMARC-uppdatering
description: Läs varför och när du måste ange en DMARC-post i Journey Optimizer
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, domän, e-post, marc, post
hide: true
hidefromtoc: true
source-git-commit: f9d3234a64ad659660c2d2c4ad24ab5c240cb857
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Obligatorisk DMARC-uppdatering {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="Läs mer om obligatorisk DMARC-uppdatering"
>abstract="Som en del av deras branschledande praxis kommer Google och Yahoo att kräva att ni har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem, med början på **1 februari 2024**. <br>Därför måste du se till att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i Journey Optimizer."

Som en del av deras branschledande praxis kommer Google och Yahoo att kräva att ni har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem. Det nya kravet börjar på **1 februari 2024**.

Läs mer om Google och Yahoos krav i [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

>[!CAUTION]
>
>Om detta nya krav från Gmail och Yahoo inte uppfylls förväntas det leda till att e-postmeddelanden landar i skräppostmappen eller blockeras.

Därför rekommenderar Adobe starkt att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i [!DNL Journey Optimizer]. Följ något av de två alternativen nedan:

* Konfigurera DMARC i dina underdomäner eller i den överordnade domänen för dina underdomäner, **i din värdlösning**. Du kan göra det från och med nu.

* Konfigurera DMARC för dina delegerade underdomäner **med den kommande funktionen i [!DNL Journey Optimizer] administrationsgränssnitt** - utan extra arbete med er värdlösning. Den här funktionen kommer att vara tillgänglig den 30 januari 2024.

  >[!CAUTION]
  >
  >Om du har konfigurerat [CNAME-delegering](delegate-subdomain.md#cname-subdomain-delegation) för dina sändande underdomäner, kommer det också att kräva att du deltar i din värdlösning. Se till att du samarbetar med din IT-avdelning så att de kan utföra uppdateringen så fort som [!DNL Journey Optimizer] finns (30 januari 2024). <!--and be ready on February 1st, 2024-->

  Mer information om [!DNL Journey Optimizer] DMARC kommer snart.

<!--
* If you have [fully delegated](delegate-subdomain.md#full-subdomain-delegation) your sending subdomains to Adobe, follow either one of the two options below:

    * Set up DMARC on your subdomains or on the parent domain of your subdomains **in your hosting solution**.

    * Set up DMARC on your delegated subdomains **using the upcoming feature in the [!DNL Journey Optimizer] administration UI** - with no extra work on your hosting solution.

* If you have set up [CNAME delegation](delegate-subdomain.md#cname-subdomain-delegation) for your sending subdomains, follow either one of the two options below:
    * Set up DMARC on your subdomains or on the parent domain of your subdomains **in your hosting solution**.
    * Set up DMARC on your delegated subdomains **using the upcoming feature in the [!DNL Journey Optimizer] administration UI**. However, it will also require entry in your hosting solution. Consequently, make sure you coordinate with your IT department so that they can perform the update as soon as the [!DNL Journey Optimizer] feature is available (on January, 30) - and be ready on February 1st, 2024.
    
-->

>[!NOTE]
>
>Om du har frågor eller behöver support kontaktar du Adobe Deliverability Consultant eller din Adobe-representant.

De senaste tidslinjer som delas av Google och Yahoo är följande:

* Google:

   * **Februari 2024** - Tillfälliga studsar avsedda att varna för bristande efterlevnad börjar. E-postmeddelanden kommer fortfarande att levereras som vanligt efter en kort fördröjning om du ännu inte uppfyller kraven. Om ni uppfyller alla krav kommer det inte att finnas några tillfälliga studsar och ni kommer inte att påverkas.

   * **April 2024** - Blocken börjar för avsändare som inte uppfyller DMARC-kraven. Endast en del av e-postmeddelandet som inte uppfyller kraven blockeras först, och procentandelen blockerad ökar med tiden.

   * **1 juni 2024** - Avsändare som inte uppfyller alla krav blockeras.

* Yahoo har inte angett några exakta datum, men har sagt att &quot;genomförandet börjar i februari 2024. Tvingande åtgärder kommer att successivt sättas ut&quot;.

>[!NOTE]
>
>Läs mer om DMARC i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} för att bättre förstå hur e-postleveransen påverkas.
