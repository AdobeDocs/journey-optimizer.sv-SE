---
title: Åtkomst till delegerade underdomäner
description: Lär dig hur du får åtkomst till delegerade underdomäner.
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: cb3248c5-f444-47aa-80b2-c1a9fbebfcc0
source-git-commit: dcdbf4a0cd6a93e56cbe97535515c1a6143db81b
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# Åtkomst till delegerade underdomäner {#access-delegated-subdomains}

Alla dina delegerade underdomäner visas i **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]** -menyn. Det finns filter som hjälper dig att förfina listan (delegeringsdatum, användare eller status).

![](../assets/subdomain-list.png)

The **[!UICONTROL Status]** kolumnen innehåller information om delegeringsprocessen för underdomäner:

* **[!UICONTROL Draft]**: Underdomändelegeringen har sparats som ett utkast. Klicka på underdomänens namn för att återuppta delegeringsprocessen,
* **[!UICONTROL Processing]**: Underdomänen genomgår flera konfigurationskontroller innan den kan användas,
* **[!UICONTROL Success]**: Underdomänen har gått igenom kontrollerna och kan användas för att leverera meddelanden,
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades efter att delegeringen av underdomäner skickades.

Om du vill ha detaljerad information om en underdomän öppnar du den i listan. Du kan:

* Hämta det underdomännamn (skrivskyddat) som konfigurerats under delegeringsprocessen samt de URL:er som genereras (resurser, spegelsidor, spårnings-URL:er),

* Lägg till en TXT-post för Google platsverifiering i din underdomän för att kontrollera att den är verifierad (se [Lägga till en Google TXT-post i en underdomän](google-txt.md)).

![](../assets/subdomain-delegated.png)
