---
title: Granskningsåtgärder för Journey Optimizer-resurser
description: Lär dig hur du spårar åtgärder som har utförts på Journey Optimizer-resurser.
feature: Monitoring
role: User
level: Intermediate
source-git-commit: 336a2a4d28ce1738cc664861291fdc1f39b3ab29
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Granskningsåtgärder för Journey Optimizer-resurser {#track-changes}

## Om granskningsloggar {#audit-logs}

Med Journey Optimizer kan du identifiera vilka åtgärder som användare i systemet utför på olika tjänster och funktioner som resor, meddelanden, landningssidor osv.

Detta gör att ni kan öka synligheten för aktiviteter som utförs i systemet, felsöka problem och hjälpa ert företag att följa regler och policyer för företagsdatahantering.

Varje åtgärd registreras med metadata i &quot;granskningsloggar&quot; som är tillgängliga i Adobe Experience Platform. Mer information om granskningsloggar, inklusive hur du visar och hanterar dem i användargränssnittet eller API finns i [Dokumentation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html).

![](assets/audit-logs.png)

## Händelsetyper som hämtats av granskningsloggar {#events}

Följande tabell visar vilka åtgärder som Journey Optimizer-resurser registreras på i granskningsloggar.

>[!NOTE]
>
>Den fullständiga listan över åtgärder som fångats i granskningsloggarna finns i [Dokumentation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html#category).

| Resurs | Åtgärd |
|-----------|------------------|
| Fältgrupp | Skapa/ta bort/uppdatera |
| AJO-underdomän | Skapa/ta bort/uppdatera |
| CJM-undertryckningslista | Skapa/ta bort/hämta CSV |
| AJO-meddelandeförinställning | Skapa/ta bort/uppdatera |
| AJO PTR-post | Skapa/ta bort/uppdatera |
| Rankningsstrategi | Skapa/ta bort/uppdatera |
| Anpassad reseåtgärd | Skapa/ta bort/uppdatera |
| Mall för AJO-landningssida HTML | Skapa/ta bort/uppdatera |
| AJO IP-pool | Skapa/ta bort/uppdatera |
| AJO - underdomän för landningssida | Skapa/ta bort/uppdatera |
| AJO SMS API-autentiseringsuppgifter | Skapa/ta bort/uppdatera |
| Förinställning för AJO-landningssida | Skapa/ta bort/uppdatera |
| Resurs, datakälla | Skapa/ta bort/uppdatera |
| Resehändelse | Skapa/ta bort/uppdatera |
| AJO sparad uttrycksmall | Skapa/ta bort/uppdatera |
| Regel för meddelandefrekvens | Skapa/ta bort/uppdatera |
| AJO - startsida | Skapa/ta bort/uppdatera/publicera/avpublicera |
| Resa | Skapa/ta bort/uppdatera/stoppa/publicera |
| AJO-meddelande | Skapa/ta bort/uppdatera/publicera |
| Allmän inställning för AJO-kanal | Skapa/ta bort/uppdatera |