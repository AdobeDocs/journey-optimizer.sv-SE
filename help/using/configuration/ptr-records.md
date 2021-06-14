---
title: PTR-poster
description: '"Lär dig hantera ptr-records"'
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
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 1%

---


# PTR-poster

## Om PTR-poster

En pekarpost (PTR) är en typ av DNS-post (Domain Name System) som tillhandahåller det domännamn som är länkat till en IP-adress.

Med PTR-poster kan e-postservrar som tar emot e-post kontrollera e-postservrarnas äkthet genom att identifiera om deras IP-adresser motsvarar de namn som servrarna ansluter till.

## Få åtkomst till dina underdomäners PTR-poster

När en underdomän har delegerats i kundresehantering skapas en PTR-post automatiskt och kopplas till den här underdomänen. Du kommer åt den från menyn **[!UICONTROL Channels]** / **[!UICONTROL PTR records]**.

![](../assets/ptr-records.png)

I listan visas de PTR-poster som genererats för varje delegerad underdomän med syntaxen nedan:

* &quot;r&quot; för register,
* &quot;xx&quot; för de två sista siffrorna i IP-adressen,
* underdomännamn.

Du kan öppna en PTR-post från listan för att visa det associerade underdomännamnet och IP-adressen.

>[!NOTE]
>
>Observera att PTR-posterna är skrivskyddade och att du inte kan ändra den underdomän som är kopplad till en IP-adress.
