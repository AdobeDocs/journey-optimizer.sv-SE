---
title: Delegering till underdomän i [!DNL Journey Optimizer]
description: Lär dig hur du delegerar dina underdomäner
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 1b5ca4db-44d9-49e2-ab39-a1abba223ec7
source-git-commit: d1204d7653a1fe32d068f974f425e10949065bc1
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 32%

---

# Delegering till underdomän i [!DNL Journey Optimizer] {#subdomain-delegation}

Genom att skapa en underdomän för e-postkampanjer kan varumärken isolera olika typer av trafik (till exempel marknadsföring kontra företag) i specifika IP-pooler och med specifika domäner, vilket snabbar upp IP-uppvärmningsprocessen och förbättrar leveransmöjligheterna generellt. Om du delar en domän och den blockeras eller läggs till i blockeringslista kan det påverka företagets e-postleverans. Men kända problem eller blockeringar på en domän som är specifik för din e-postmarknadsföring kommer att påverka just det e-postflödet. Om du använder huvuddomänen som avsändare eller Från-adress för flera e-postströmmar kan det också bryta e-postautentiseringen, vilket gör att dina meddelanden blockeras eller placeras i skräppostmappen.

>[!NOTE]
>
>Du kan inte använda samma sändande domän för att skicka ut meddelanden från [!DNL Adobe Journey Optimizer] och från en annan produkt, som [!DNL Adobe Campaign] eller [!DNL Adobe Marketo Engage].

## Varför konfigurera underdomäner? {#why-setting-up-subdomains}

En underdomän är en division av din domän som kan användas för att isolera dina varumärken eller olika typer av trafik, till exempel transaktionsmeddelanden och marknadsföringskommunikation.

Låt oss ta exemplet med domänen ”mybrand.com” som används för att skicka både transaktions- och marknadsföringskommunikation. I det här fallet kan du konfigurera två underdomäner:

* underdomänen ”info.mybrand.com” för transaktionskommunikation (inköpsbekräftelser och lösenordsåterställning osv.) och
* underdomänen ”marketing.mybrand.com” för dina e-postmeddelanden till möjliga kunder.

På så sätt kan du bevara domänens och andra underdomäners rykte. Om t.ex. underdomänen ”marketing.mybrand.com” läggs till i blockeringslistan hos internetleverantörer på grund av dålig levererbarhet förhindrar detta att hela domänen ”mybrand.com” och underdomänen ”info.mybrand.com” läggs till i blockeringslistan.

När du implementerar en lösning finns det krav för externt vända komponenter: dessa innehåller bland annat inställningar av länkar och webbsidor som ska spåras, visning av spegelsidor.

Dessa krav hanteras via komponenter som finns både på Adobe och hos kunden, men de innehåller URL:er som kan ses av mottagarna av e-postmeddelandena. För att undvika att ha URL:er som anger den underliggande tekniska lösningen eller värdtjänstleverantören, kan underdomäner konfigureras så att de blir genomskinliga för e-postmeddelandets mottagare.

**Läs mer**

* Lär dig hur [delegera dina underdomäner](delegate-subdomain.md) direkt från gränssnittet
* Lär dig hur [lägg till Google TXT-poster](google-txt.md) till dina underdomäner för att säkerställa att e-postmeddelanden skickas till Gmail-adresser
* Lär dig hur [få åtkomst till PTR-posterna](ptr-records.md) som har genererats för dina underdomäner, så att de kan verifieras genom att e-postservrar skickas

## Konfigurationsmetoder för underdomäner {#subdomain-delegation-methods}

Med subdomänkonfigurationen kan du konfigurera ett underavsnitt av din domän (tekniskt en &quot;DNS-zon&quot;) för användning med Adobe Campaign. Tillgängliga installationsmetoder är:

* **Fullständig delegering av underdomäner till Adobe** (rekommenderas): underdomänen delegeras helt till Adobe. Adobe kan styra och underhålla alla aspekter av DNS som krävs för att leverera, återge och spåra meddelanden. [Läs mer om fullständig delegering av underdomäner](delegate-subdomain.md#full-subdomain-delegation)

* **Användning av CNAME**: Skapa en underdomän och använd CNAME:er för att peka på Adobe-specifika poster. Med den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS. [Läs mer om delegering av CNAME-underdomäner](delegate-subdomain.md#cname-subdomain-delegation)

>[!CAUTION]
>
>* Den fullständiga underdomänsdelegeringen är den rekommenderade metoden.
>
>* CNAME-metoden rekommenderas om organisationens principer begränsar den fullständiga delegeringsmetoden för underdomäner. På det här sättet måste du behålla och hantera DNS-poster på egen hand. Adobe kan inte hjälpa till med att ändra, underhålla eller hantera DNS för en underdomän som konfigurerats via CNAME-metoden.


Tabellen nedan tillhandahåller en sammanfattning av hur dessa metoder fungerar samt den troliga ansträngningsnivån:

| Konfigurationsmetod | Så fungerar det | Ansträngningsnivå |
|---|---|---|
| **Fullständig delegering** | Skapa underdomänen och posten för namnrymden. Adobe konfigurerar sedan alla DNS-poster som krävs för Adobe Campaign.<br/><br/>I den här konfigurationen är Adobe helt ansvarigt för att hantera underdomänen och alla DNS-poster. | Låg |
| **CNAME och anpassad metod** | Skapa underdomänen och posten för namnrymden. Adobe tillhandahåller sedan de poster som ska placeras i DNS-servrarna och konfigurerar motsvarande värden i Adobe Campaign DNS-servrar.<br/><br/>I den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS:er. | Hög |

Ytterligare information om domänkonfiguration finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/product-specific-resources/campaign/ac-domain-name-setup.html).

Om du har några frågor om konfigureringsmetoder för subdomäner kan du kontakta Adobe eller så småningom kontakta kundtjänst för att beställa rådgivning om leveransen.
