---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med Live-aktivitet
description: Lär dig hur du skickar Live-aktivitet i Journey Optimizer
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c9766603-df19-4efd-8319-27e9764254b4
source-git-commit: 2fc4b1ee34b44fb6c5bcddb13f1b2b02f7094ff1
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Kom igång med Live-aktivitet {#get-started-mobile-live}

>[!AVAILABILITY]
>
>Live-aktiviteten i Journey Optimizer är bara kompatibel med iOS.

Live-aktiviteten ger uppdateringar i realtid och interaktiva upplevelser i mobilappar, så att användarna kan hålla sig informerade om pågående händelser eller uppgifter direkt på enhetens skärm.

Den här funktionen förbättrar engagemanget genom att leverera live-information, som förloppsspårning, händelseuppdateringar eller interaktivt innehåll, utan att användarna behöver öppna appen.

Live-aktiviteten kan **endast** initieras via **API-utlösta** kampanjer, vilket gör att du kan tillhandahålla anpassade nyttolaster och utföra all personalisering via din egen nyttolast.
Lämplig **API-utlöst**-kampanjtyp måste väljas baserat på användningsfallet för Live-aktivitet:

* Välj **API-utlöst marknadsföring** för målgruppsbaserade kampanjer

  Utformad för målgrupper eller segmentbaserad kommunikation där samma uppdatering skickas till flera användare, t.ex. sportresultat, händelseuppdateringar och delade upplevelser.

* Välj **API-utlöst Transactional** för enskilda kampanjer

  Avsedd enskild användare som identifieras av sin profil, t.ex. orderstatus, leveransspårning.

## Snabbstartsguide

Följ stegen nedan för att konfigurera och implementera Live-aktivitet i ditt program:

1. **[Konfigurera Adobe Journey Optimizer](mobile-live-configuration.md)**

   Konfigurera miljön genom att skapa en mobilkonfiguration.

1. **[Integrera Adobe Experience Platform Mobile SDK](mobile-live-configuration-sdk.md)**

   Integrera med Adobe Experience Platform Mobile SDK för att aktivera dynamiska uppdateringar i realtid på låsskärmen och Dynamic Island.

1. **[Skapa Live-aktivitet i Journey Optimizer](create-mobile-live.md)**

   Använd API-utlösta kampanjer i Journey Optimizer för att starta din Live-aktivitet.

1. **[Spåra kampanjer](../reports/campaign-global-report-cja-activity.md)**

   Börja mäta effekten av Live-aktiviteten med inbyggda rapporter.
