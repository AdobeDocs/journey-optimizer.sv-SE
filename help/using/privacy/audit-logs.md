---
solution: Journey Optimizer
product: journey optimizer
title: Granskningsåtgärder för Journey Optimizer-resurser
description: Lär dig hur du spårar åtgärder som har utförts på Journey Optimizer-resurser.
feature: Monitoring
role: User
level: Intermediate
exl-id: 759b014a-c834-4331-bffd-5bc159ec555d
source-git-commit: 78675ca22d8ee9a93d9af128d5708c305523da78
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Granskningsåtgärder för Journey Optimizer-resurser {#track-changes}

## Om granskningsloggar {#audit-logs}

>[!IMPORTANT]
>
>Om du vill visa och exportera granskningsloggen måste du ha **[!DNL View User Activity Log]** tillstånd har beviljats. [Läs mer](../administration/ootb-product-profiles.md)

Med Journey Optimizer kan du identifiera vilka åtgärder som användare i systemet utför på olika tjänster och funktioner som resor, meddelanden, landningssidor osv.

Detta gör att ni kan öka synligheten för aktiviteter som utförs i systemet, felsöka problem och hjälpa ert företag att följa regler och policyer för företagsdatahantering.

Varje åtgärd registreras med metadata i &quot;granskningsloggar&quot; som är tillgängliga i Adobe Experience Platform. Mer information om granskningsloggar, inklusive hur du visar och hanterar dem i användargränssnittet eller API finns i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html).

![](assets/audit-logs.png)

## Händelsetyper som hämtats av granskningsloggar {#events}

Följande tabell visar vilka åtgärder som Journey Optimizer-resurser registreras på i granskningsloggar.

>[!NOTE]
>
>Den fullständiga listan över åtgärder som fångats i granskningsloggarna finns i [Dokumentation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview.html#category).

| Resurs | Åtgärd |
|-----------|------------------|
| AJO-kampanj | Skapa/ta bort/uppdatera/aktivera/stoppa |
| Allmän inställning för AJO-kanal | Skapa/ta bort/uppdatera |
| AJO IP-pool | Skapa/ta bort/uppdatera |
| AJO - startsida | Skapa/ta bort/uppdatera/publicera/avpublicera |
| Mall för AJO-landningssida HTML | Skapa/ta bort/uppdatera |
| Förinställning för AJO-landningssida | Skapa/ta bort/uppdatera |
| AJO - underdomän för landningssida | Skapa/ta bort/uppdatera |
| AJO-meddelande | Skapa/ta bort/uppdatera/publicera |
| AJO-meddelandeförinställning | Skapa/ta bort/uppdatera |
| AJO PTR-post | Skapa/ta bort/uppdatera |
| AJO sparad uttrycksmall | Skapa/ta bort/uppdatera |
| AJO SMS API-autentiseringsuppgifter | Skapa/ta bort/uppdatera |
| AJO-underdomän | Skapa/ta bort/uppdatera |
| AJO-undertryckningslista | Skapa/ta bort/hämta CSV |
| Fältgrupp | Skapa/ta bort/uppdatera |
| Resa | Skapa/ta bort/uppdatera/stoppa/publicera |
| Anpassad reseåtgärd | Skapa/ta bort/uppdatera |
| Resurs, datakälla | Skapa/ta bort/uppdatera |
| Resehändelse | Skapa/ta bort/uppdatera |
| Regel för meddelandefrekvens | Skapa/ta bort/uppdatera |
| Rankningsstrategi | Skapa/ta bort/uppdatera |
