---
title: Delegera underdomäner
description: Lär dig hur du delegerar dina underdomäner
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Applikationsinställningar
topic: Administrering
role: Admin
level: Intermediate
source-git-commit: 63de381ea3a87b9a77bc6f1643272597b50ed575
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---


# Åtkomst till delegerade underdomäner

Alla dina delegerade underdomäner visas på menyn **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]**. Det finns filter som hjälper dig att förfina listan (delegeringsdatum, användare eller status).

![](../assets/subdomain-list.png)

Kolumnen **[!UICONTROL Status]** innehåller information om delegeringsprocessen för underdomäner:

* **[!UICONTROL Draft]**: Underdomändelegeringen har sparats som ett utkast. Klicka på underdomänens namn för att återuppta delegeringsprocessen,
* **[!UICONTROL Processing]**: Underdomänen genomgår flera konfigurationskontroller innan den kan användas,
* **[!UICONTROL Success]**: Underdomänen har gått igenom kontrollerna och kan användas för att leverera meddelanden,
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades efter att delegeringen av underdomäner skickades.

Om du vill ha detaljerad information om en underdomän öppnar du den i listan. Ni kan:

* Hämta det underdomännamn (skrivskyddat) som konfigurerats under delegeringsprocessen samt de URL:er som genereras (resurser, spegelsidor, spårnings-URL:er),

* Lägg till en TXT-post för Google Site verification i din underdomän för att se till att den är verifierad (se [Lägg till en Google TXT-post i en underdomän](google-txt.md)).

![](../assets/subdomain-delegated.png)
