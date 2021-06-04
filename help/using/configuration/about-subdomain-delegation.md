---
title: Delegera underdomäner
description: Lär dig hur du delegerar dina underdomäner
internal: n
snippet: y
source-git-commit: e569e992530df5429ffb96f78ba28b53de0ded81
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 26%

---


# Delegering av underdomän i [!DNL Journey Optimizer]

Genom att skapa en underdomän för e-postkampanjer kan varumärken isolera olika typer av trafik (till exempel marknadsföring kontra företag) i specifika IP-pooler och med specifika domäner, vilket snabbar upp IP-uppvärmningsprocessen och förbättrar leveransmöjligheterna generellt. Om du delar en domän och den blockeras eller läggs till i blockeringslista kan det påverka företagets e-postleverans. Men kända problem eller blockeringar på en domän som är specifik för din e-postmarknadsföring kommer att påverka just det e-postflödet. Om du använder huvuddomänen som avsändare eller Från-adress för flera e-postströmmar kan det också bryta e-postautentiseringen, vilket gör att dina meddelanden blockeras eller placeras i skräppostmappen.

En underdomän är en division av din domän som kan användas för att isolera dina varumärken eller olika typer av trafik, till exempel transaktionsmeddelanden och marknadsföringskommunikation.

Låt oss ta exemplet med domänen ”mybrand.com” som används för att skicka både transaktions- och marknadsföringskommunikation. I det här fallet kan du konfigurera två underdomäner:

* underdomänen ”info.mybrand.com” för transaktionskommunikation (inköpsbekräftelser och lösenordsåterställning osv.) och
* underdomänen ”marketing.mybrand.com” för dina e-postmeddelanden till möjliga kunder.

På så sätt kan du bevara domänens och andra underdomäners rykte. Om t.ex. underdomänen ”marketing.mybrand.com” läggs till i blockeringslistan hos internetleverantörer på grund av dålig levererbarhet förhindrar detta att hela domänen ”mybrand.com” och underdomänen ”info.mybrand.com” läggs till i blockeringslistan.

När du implementerar en lösning finns det krav för externt vända komponenter: dessa innehåller bland annat inställningar av länkar och webbsidor som ska spåras, visning av spegelsidor.

Dessa krav hanteras via komponenter som finns både på Adobe och hos kunden, men de innehåller URL:er som kan ses av mottagarna av e-postmeddelandena. För att undvika att ha URL:er som anger den underliggande tekniska lösningen eller värdtjänstleverantören, kan underdomäner konfigureras så att de blir genomskinliga för e-postmeddelandets mottagare.

**Läs mer**

* Lär dig hur du [delegerar dina underdomäner](delegate-subdomain.md) direkt från gränssnittet
* Lär dig hur du [lägger till Google TXT-poster](google-txt.md) i dina underdomäner för att se till att e-postmeddelanden skickas till Gmail-adresser
* Lär dig hur du [får åtkomst till de PTR-poster](ptr-records.md) som genererats för dina underdomäner, så att de kan verifieras genom att skicka e-postservrar
