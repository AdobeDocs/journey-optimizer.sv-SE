---
solution: Journey Optimizer
product: journey optimizer
title: Följ de nya DMARC-kraven
description: Läs varför och när du måste ange en DMARC-post i Journey Optimizer
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, domän, e-post, marc, post
source-git-commit: a153960d083cbeab8beca30733832a9df8af9cbc
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Följ de nya DMARC-kraven {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="Läs mer om obligatorisk DMARC-uppdatering"
>abstract="Som en del av deras branschledande praxis kommer Google och Yahoo att kräva att ni har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem, med början på **1 februari 2024**.<br>Därför måste du se till att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i Journey Optimizer."

Som en del av deras branschledande praxis kommer Google och Yahoo att kräva att ni har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem. Det nya kravet börjar på **1 februari 2024**.

Läs mer om Google och Yahoos krav i [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

>[!CAUTION]
>
>Om detta nya krav från Gmail och Yahoo inte uppfylls förväntas det leda till att e-postmeddelanden landar i skräppostmappen eller blockeras.

Därför rekommenderar Adobe starkt att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i [!DNL Journey Optimizer]. Följ stegen nedan som gäller ditt ärende:

* Om du har [helt delegerad](delegate-subdomain.md#full-subdomain-delegation) Om du vill skicka underdomäner till Adobe följer du något av följande två alternativ:

   * Konfigurera DMARC på den överordnade domänen för dina delegerade underdomäner **i din värdlösning**.

   * Konfigurera DMARC för dina delegerade underdomäner **i [!DNL Journey Optimizer] administrationsgränssnitt** - utan extra arbete med er värdlösning. [Lär dig mer](dmarc-record.md#implement-dmarc)

* Om du har konfigurerat dina sändande underdomäner med [CNAME](delegate-subdomain.md#cname-subdomain-delegation)följer du något av följande två alternativ:
   * Konfigurera DMARC på dina underdomäner eller på den överordnade domänen för dina underdomäner **i din värdlösning**.
   * Konfigurera DMARC för dina delegerade underdomäner **i [!DNL Journey Optimizer] administrationsgränssnitt**. [Lär dig mer](dmarc-record.md#implement-dmarc)

     Med CNAME-delegering måste du dock även ange detta i din värdlösning. Därför bör du se till att samordna med din IT-avdelning så att de kan utföra uppdateringen så snart som [!DNL Journey Optimizer] finns (den 30 januari). [Läs mer](dmarc-record.md#implement-dmarc)

**Mer information om [!DNL Journey Optimizer] DMARC-funktionen finns tillgänglig i [det här avsnittet](dmarc-record.md).**

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
