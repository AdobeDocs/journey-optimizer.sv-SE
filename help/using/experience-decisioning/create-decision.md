---
title: Kom igång med beslutsprofiler
description: Lär dig hur du arbetar med beslutsstrategier för att leverera erbjudanden.
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 63aa1763-2220-4726-a45d-3a3a8b8a55ec
version: Journey Orchestration
source-git-commit: c2388c84346ed9a0409270fd96f3a1458bf8ad88
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Kom igång med beslutsstrategier {#create-decision}

>[!CONTEXTUALHELP]
>id="ajo_code_based_decision"
>title="Vad är ett beslut?"
>abstract="Beslutspolicyer innehåller all urvalslogik för att beslutsmotorn ska kunna välja det bästa innehållet. Beslutspolicyn är kampanjspecifika. Deras mål är att välja de bästa erbjudandena för varje profil medan kampanjutvecklingen gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Om beslut"

>[!CONTEXTUALHELP]
>id="ajo_journey_decision_policy"
>title="Definiera en beslutspolicy"
>abstract="Med en beslutspolicy kan ni välja ut de bästa elementen från beslutsmotorn och leverera dem till rätt målgrupp."
>additional-url="https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/decisioning/offer-decisioning/get-started-decision/starting-offer-decisioning" text="Om beslut"

>[!CONTEXTUALHELP]
>id="ajo_exd_decision_policy"
>title="Beslutspolitik"
>abstract="Med en beslutspolicy kan ni välja ut de bästa elementen från beslutsmotorn och leverera till varje målgrupp."

>[!CONTEXTUALHELP]
>id="ajo_exd_placements"
>title="Placement"
>abstract="En placering bestämmer var returnerade objekt från beslutsmotorn visas i ett meddelande. Ni kan spåra deras prestanda på olika ställen i rapporteringen."

>[!CONTEXTUALHELP]
>id="ajo_exd_decision_attribute"
>title="Välj beslutsattribut från katalog"
>abstract="Beslutsattribut lagras i katalogschemat. Välj ett attribut som du vill använda här från den valda katalogen."

Beslutspolicyer är behållare för era erbjudanden som utnyttjar beslutsmotorn för att dynamiskt returnera det bästa innehållet för varje målgruppsmedlem. Deras mål är att välja de bästa erbjudandena för varje profil, medan kampanjen/resan gör att du kan ange hur de valda beslutsobjekten ska presenteras, inklusive vilka objektattribut som ska inkluderas i meddelandet.

>[!AVAILABILITY]
>
>För närvarande är beslutsprofiler tillgängliga för alla kunder för den kodbaserade Experience Channel. De är tillgängliga för e-postkanalen som begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

## Viktiga steg {#key}

De viktigaste stegen för att utnyttja beslutsstrategier i meddelanden är följande:

1. [Skapa en beslutspolicy](../experience-decisioning/create-decision-policy.md)

   Ställ in en beslutspolicy i meddelandet genom att välja hur många objekt som ska returneras, konfigurera urvalsstrategier, reservalternativ och utvärderingsordning.

1. [Använd beslutsprincipen i ditt innehåll](../experience-decisioning/use-decision-policy.md)

   Anpassa innehållet med beslutsunderlag och attribut från de beslutsobjekt du vill visa i meddelandet.

1. [Skapa rapportinstrumentpaneler](cja-reporting.md)

   Bygg anpassade Customer Journey Analytics-kontrollpaneler för att mäta prestanda och få insikt i hur era beslutsstrategier och -erbjudanden levereras och engageras.

## Skyddsritningar och begränsningar

* **Spegelsidor för e-post** - För tillfället återges inte beslutsobjekt i e-postspegelsidor.
* **Spårnings- och länktyp** - Om du vill spåra länkar som skapats genom beslut definierar du dem i schemat som&quot;Decisioning Assets&quot;. Attributbaserade länkar går inte att spåra.
* **Beslutsprincipkapsling i e-postmeddelanden** - Det går inte att kapsla flera beslutsprinciper i en överordnad e-postkomponent som redan har en associerad beslutsprincip.
* **Duplicerade resor/kampanjer med beslut** - Om du duplicerar en resa eller kampanj som innehåller en beslutsprincip refererar den duplicerade versionen till det ursprungliga e-postmeddelandet eller den kodbaserade upplevelsen, vilket ger upphov till fel. Konfigurera alltid om beslutsprincipen efter duplicering.
* **Samtyckesprinciper** - Det tar upp till 48 timmar att genomföra uppdateringar av medgivandeprinciper. Om en beslutspolicy refererar till ett attribut som är knutet till en nyligen uppdaterad medgivandepolicy, kommer ändringarna inte att tillämpas omedelbart.

  Om nya profilattribut som omfattas av en samtyckespolicy läggs till i en beslutspolicy kommer de att vara användbara, men den medgivandepolicy som är kopplad till dem kommer inte att tillämpas förrän förseningen har passerat.

  Samtyckesregler är endast tillgängliga för organisationer som har Adobe Healthcare Shield eller tillägg till Privacy and Security Shield.

* **AI-rankning** - För tillfället stöds inte AI-rankning för e-postkanalen i resor med beslut.

## Nästa steg {#next-steps}

Nu när ni förstår hur beslutsfattandet fungerar och hur de hjälper er att leverera personaliserade erbjudanden är ni redo att skapa er första beslutspolicy.

➡️ [Lär dig hur du skapar en beslutsprincip](../experience-decisioning/create-decision-policy.md)

## Instruktionsvideo {#video}

Lär dig hur du använder Decisioning för att anpassa e-postmeddelanden för din målgrupp.

>[!VIDEO](https://video.tv.adobe.com/v/3479214?captions=swe&quality=12)
