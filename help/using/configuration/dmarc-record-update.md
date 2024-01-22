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
source-git-commit: b67b53b7a3ea6d2daee223a5579696d0e5637c44
workflow-type: tm+mt
source-wordcount: '520'
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

Därför rekommenderar Adobe starkt att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i [!DNL Journey Optimizer]. Följ stegen nedan som gäller ditt ärende:

<!--
* Set up DMARC on your subdomains, or on the parent domain of your subdomains, **in your hosting solution**. You can do it as of now.

* Set up DMARC on your delegated subdomains **using the upcoming feature in the [!DNL Journey Optimizer] administration UI** - with no extra work on your hosting solution. This feature will be available on January 30, 2024.

    >[!CAUTION]
    >
    >If you have set up [CNAME delegation](delegate-subdomain.md#cname-subdomain-delegation) for your sending subdomains, it will also require some entry into your hosting solution. Make sure you coordinate with your IT department so that they can perform the update as soon as the [!DNL Journey Optimizer] feature is available (on January 30, 2024). (and be ready on February 1st, 2024)

    More details on the [!DNL Journey Optimizer] DMARC upcoming feature will come soon.
-->

* Om du har [helt delegerad](delegate-subdomain.md#full-subdomain-delegation) Om du vill skicka underdomäner till Adobe följer du något av följande två alternativ:

   * Konfigurera DMARC på den överordnade domänen för dina delegerade underdomäner **i din värdlösning**.

   * Konfigurera DMARC för dina delegerade underdomäner **med den kommande funktionen i [!DNL Journey Optimizer] administrationsgränssnitt** - utan extra arbete med er värdlösning.

* Om du har konfigurerat [CNAME-delegering](delegate-subdomain.md#cname-subdomain-delegation) för dina sändande underdomäner, följ något av följande två alternativ:
   * Konfigurera DMARC på dina underdomäner eller på den överordnade domänen för dina underdomäner **i din värdlösning**.
   * Konfigurera DMARC för dina delegerade underdomäner **med den kommande funktionen i [!DNL Journey Optimizer] administrationsgränssnitt**. Men det kommer också att kräva att du deltar i din värdlösning. Därför bör du se till att samordna med din IT-avdelning så att de kan utföra uppdateringen så snart som [!DNL Journey Optimizer] finns (den 30 januari). <!--and be ready on February 1st, 2024-->

Mer information om [!DNL Journey Optimizer] DMARC kommer snart.

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
