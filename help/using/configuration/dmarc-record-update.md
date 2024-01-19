---
solution: Journey Optimizer
product: journey optimizer
title: DMARC-post
description: Lär dig hur du ställer in DMARC-post i Journey Optimizer
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, domän, e-post, marc, post
hide: true
hidefromtoc: true
source-git-commit: 5565c98e41e0abc9ae93f85cb12679e372e6d36f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# DMARC-post viktig uppdatering{#dmarc-record}


>[!CAUTION]
>
>Efter de senaste Gmail- och Yahoo-meddelandena om bulkavsändare har Journey Optimizer nu stöd för DMARC-autentiseringstekniken.

Som en del av deras branschledande praxis kommer både Google och Yahoo att kräva att du har en DMARC-post för alla domäner du använder för att skicka e-post till dem. Det nya kravet börjar på **1 februari 2024**.

Läs mer om Google och Yahoos krav på DMARC-registrering i [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

Läs mer om ändringarna på Google och Yahoo på [den här sidan](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

Därefter får du en åtgärd eller nästa steg för ditt avsnitt där det ska stå:

Du måste konfigurera den för alla dina underdomäner
* Om du har delegerat domänen till oss har du två alternativ
   * Konfigurera DMARC på den överordnade domänen för den delegerade domänen i din värdlösning, ELLER
   * Konfigurera DMARC för delegerad domän med hjälp av den kommande funktionen i administratörsgränssnittet utan extra arbete med värdlösningar
* Om du har konfigurerat CNAME för de sändande domänerna har du två alternativ
   * Konfigurera DMARC på underdomänen ELLER den överordnade domänen till underdomänen i din värdlösning, ELLER
   * Konfigurera DMARC med den kommande funktionen i administratörsgränssnittet. Men det kommer inte bara att kräva vårt användargränssnitt, utan också att vi måste vara med i en värdlösning.

Mer information om vår kommande funktion kommer snart.

Dessutom kan du inkludera effekten om den inte ställs in genom att kopiera det avsnitt som är relevant för DMARC från nedanstående avsnitt (kopierat från länken ovan). Antingen drar vi ut bara DMARC-relaterade saker. Eller här kan du informera om att det är DMARC och att det bara finns en klickning under och här är den senaste tidslinjen för båda funktionerna.

Uppdateringar av tidslinjer har gjorts sedan det ursprungliga meddelandet i oktober.

De senaste tidslinjerna ser ut så här:

Gmail:

* Februari 2024 - Tillfälliga studsar avsedda att varna för bristande efterlevnad börjar. E-postmeddelanden kommer fortfarande att levereras som vanligt efter en kort fördröjning om du ännu inte uppfyller kraven. Om ni uppfyller alla krav kommer det inte att finnas några tillfälliga studsar och ni kommer inte att märka någonting.
* April 2024 - Blocken börjar för avsändare som inte uppfyller allt utom List-Unsubscribe 1-Click. Endast en del av e-postmeddelandet som inte uppfyller kraven blockeras först, där procentandelen blockeras med tiden.
* 1 juni 2024 - Alla avsändare som inte uppfyller alla krav, inklusive List-Unsubscribe 1-Click, blockeras.

Yahoo:

Har inte angett några exakta datum, men har sagt att&quot;genomförandet av lagstiftningen kommer att börja i februari 2024. Tvingande åtgärder kommer att successivt sättas ut&quot;.
