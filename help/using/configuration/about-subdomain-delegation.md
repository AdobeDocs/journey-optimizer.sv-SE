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
source-git-commit: da995c56b59fb191934788c7aea9048123a2fe6d
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 43%

---


# Kom igång med delegering till underdomäner

## Isolera era varumärken för att skydda ert rykte

En underdomän är en division av din domän som kan användas för att isolera dina varumärken eller olika typer av trafik (transaktionsmeddelanden och marknadsföringsinformation osv.).
Låt oss ta exemplet med domänen ”mybrand.com” som används för att skicka både transaktions- och marknadsföringskommunikation. I det här fallet kan du konfigurera två underdomäner:

* underdomänen ”info.mybrand.com” för transaktionskommunikation (inköpsbekräftelser och lösenordsåterställning osv.) och
* underdomänen ”marketing.mybrand.com” för dina e-postmeddelanden till möjliga kunder.

På så sätt kan du bevara domänens och andra underdomäners rykte. Om t.ex. underdomänen ”marketing.mybrand.com” läggs till i blockeringslistan hos internetleverantörer på grund av dålig levererbarhet förhindrar detta att hela domänen ”mybrand.com” och underdomänen ”info.mybrand.com” läggs till i blockeringslistan.

## Se till att era resurs-URL:er är genomskinliga för kunderna

När du implementerar en lösning finns det krav för externt vända komponenter: dessa innehåller bland annat inställningar av länkar och webbsidor som ska spåras, visning av spegelsidor.

Dessa krav hanteras via komponenter som finns både på Adobe och hos kunden, men de innehåller URL:er som kan ses av mottagarna av e-postmeddelandena. För att undvika att ha URL:er som anger den underliggande tekniska lösningen eller värdtjänstleverantören, kan underdomäner konfigureras så att de blir genomskinliga för e-postmeddelandets mottagare. [Läs mer om domändelegering](https://helpx.adobe.com/se/campaign/kb/domain-name-delegation.html).

## Delegering av underdomän i Journey Optimizer

Journey Optimizer har flera funktioner som hjälper dig att hantera underdomäner:

* [Delegera dina ](delegate-subdomain.md) underdomäner direkt från gränssnittet,
* [Lägg till Google TXT-](google-txt.md) poster i dina underdomäner för att säkerställa att e-postmeddelanden kan levereras till Gmail-adresser,
* [Få åtkomst till PTR-](ptr-records.md) postgenererade för dina underdomäner, så att de kan verifieras genom att skicka e-postservrar.
