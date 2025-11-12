---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med Live-aktiviteter
description: Lär dig hur du skickar live-aktiviteter i Journey Optimizer
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---


# Kom igång med Live-aktivitet {#get-started-mobile-live}

>[!BEGINSHADEBOX]

* **[Kom igång med Live-aktivitet](get-started-mobile-live.md)**
* [Konfiguration av aktiv aktivitet](mobile-live-configuration.md)
* [Live Activity-integrering med Adobe Experience Platform Mobile SDK](mobile-live-configuration-sdk.md)
* [Skapa en Live-aktivitet](create-mobile-live.md)
* [Vanliga frågor och svar](mobile-live-faq.md)
* [Rapport om aktiv aktivitetskampanj](../reports/campaign-global-report-cja-activity.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Live-aktiviteten i Journey Optimizer är bara kompatibel med iOS.

Live-aktiviteter ger uppdateringar i realtid och interaktiva upplevelser i mobilappar, så att användarna kan hålla sig informerade om pågående händelser eller uppgifter direkt på enhetens skärm.

Den här funktionen förbättrar engagemanget genom att leverera live-information, som förloppsspårning, händelseuppdateringar eller interaktivt innehåll, utan att användarna behöver öppna appen.

Live-aktiviteter kan **bara** initieras via **API-utlösta**-kampanjer, vilket gör att du kan tillhandahålla anpassade nyttolaster och utföra all personalisering via din egen nyttolast.
Lämplig **API-utlöst**-kampanjtyp måste väljas baserat på användningsfallet för Live-aktivitet:

* Välj **API-utlöst marknadsföring** för målgruppsbaserade kampanjer

  Utformad för målgrupper eller segmentbaserad kommunikation där samma uppdatering skickas till flera användare, t.ex. sportresultat, händelseuppdateringar och delade upplevelser.

* Välj **API-utlöst Transactional** för enskilda kampanjer

  Avsedd enskild användare som identifieras av sin profil, t.ex. orderstatus, leveransspårning.

## Snabbstartsguide

Följ stegen nedan för att konfigurera och implementera Live-aktiviteter i ditt program:

1. **[Konfigurera Adobe Journey Optimizer](mobile-live-configuration.md)**

   Konfigurera miljön genom att skapa en mobilkonfiguration.

1. **[Integrera Adobe Experience Platform Mobile SDK](mobile-live-configuration-sdk.md)**

   Integrera med Adobe Experience Platform Mobile SDK för att aktivera dynamiska uppdateringar i realtid på låsskärmen och Dynamic Island.

1. **[Skapa Live-aktiviteter i Journey Optimizer](create-mobile-live.md)**

   Använd API-utlösta kampanjer i Journey Optimizer för att starta era Live-aktiviteter.

1. **[Spåra kampanjer](../reports/campaign-global-report-cja-activity.md)**

   Börja mäta effekten av dina Live-aktiviteter med inbyggda rapporter.




