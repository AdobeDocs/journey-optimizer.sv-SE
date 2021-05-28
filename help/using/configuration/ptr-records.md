---
title: PTR-poster
description: Lär dig mer om xxxx
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
source-git-commit: 6988a6ab9412e5d27f1ba9d1145cc11c7c06e7b7
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

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
