---
solution: Journey Optimizer
product: journey optimizer
title: Arbetsflöde för snabb start av mobil introduktion
description: Lär dig hur du använder arbetsflödet för snabbstart av mobil introduktion
topic: Mobile
feature: Push
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta" type="Informative"
exl-id: 82477d40-cfea-456b-a7b1-9cfebd76db35
source-git-commit: 62954221f9797fc4ac7b5e066ffea6f99c17ad45
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 4%

---

# Arbetsflöde för snabb start av mobil introduktion {#mobile-wf}

Den nya **snabbstartsarbetsflöde för mobil introduktion** är en ny produktfunktion som snabbt konfigurerar Adobe Experience Platform Mobile SDK, börjar samla in och validera mobilhändelsedata och skickar push-meddelanden med [!DNL Journey Optimizer].

Den här funktionen är tillgänglig via **[!DNL Adobe Experience Platform Data Collection]** startsida till alla kunder som betaversion.

## Kom igång{#gs-mobile-wf}

Det nya arbetsflödet automatiserar konfigurationen av datainsamling genom att minska det totala antalet klick och påskynda mobilkonfigurationen för Journey Optimizer. Det här snabbstartsarbetsflödet tar dig igenom fyra enkla steg för att [konfigurera](##setup-mobile-wf), [implementera](#implement-mobile-wf), [validera](#valid-mobile-wf)och [recension](#review-mobile-wf) din mobilkonfiguration.

Om du vill få tillgång till det nya arbetsflödet för snabbstart av mobilintroduktion går du till **[!DNL Data Collection]** från lösningsväljaren. Välj sedan **[!DNL Start Collecting Mobile Data]** på startsidan.

![](assets/mobile-wf-home.png)

Nedan följer några ytterligare funktioner:

* Smidigt arbetsflöde i fyra steg och användargränssnitt.
* Ger en grundläggande konfiguration för att börja samla in mobilhändelsedata via [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} på några minuter.
* Möjlighet att testa och validera en grundläggande push-händelse för mobila enheter [Adobe Experience Platform Assurance](https://experienceleague.adobe.com/docs/experience-platform/assurance/home.html){target="_blank"}.
* Auto skapar och konfigurerar alla nödvändiga datainsamlingar och Journey Optimizer-resurser.
* I produktvägledning och verktygstips.
* Ger en naturlig övergång för mer avancerad implementering vid behov.

## Konfigurera {#setup-mobile-wf}

I det första steget i det här arbetsflödet skapas och konfigureras automatiskt alla nödvändiga datainsamlingar och Journey Optimizer-resurser, till exempel Mobile Properties (Mobila egenskaper), Mobile Extensions (Mobila tillägg), Journey Optimizer Extension (-tillägg), Rules (Regler), Data Elements (Dataelement) osv.

När du har godkänt betavillkoren anger du namnet på din mobilapp och klickar på **[!DNL Next]**.

![](assets/mobile-wf-setup.png)

Ange information för iOS- och Android-plattformar, inklusive ditt program-ID och autentiseringsnycklar eller nyckelfil.

## Implementera{#implement-mobile-wf}

I nästa steg får du stegvisa anvisningar om hur du installerar koden i din mobilapp.

![](assets/mobile-wf-add-code.png)


## Validera{#valid-mobile-wf}

Granska och kontrollera implementeringen för att validera den. Du kan skicka ett push-testmeddelande.

![](assets/mobile-wf-valid.png)


## Granska {#review-mobile-wf}

Automatiserad installation är klar. Nu kan du gå till taggens mobila egenskap och konfigurera regler eller dataelement och börja skicka push-meddelanden med Adobe Journey Optimizer.

![](assets/mobile-wf-done.png)


**Relaterade ämnen**

* [Kom igång med push-meddelanden](get-started-push.md)
* [Dataflöde och komponenter för push-meddelanden](push-gs.md)
* [Konfigurera push-kanalen](push-configuration.md)
* [Rapport om push-meddelanden](../reports/journey-global-report.md#push-global)
* [Skapa ett push-meddelande](create-push.md)
