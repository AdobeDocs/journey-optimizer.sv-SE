---
solution: Journey Optimizer
product: journey optimizer
title: Delegering av underdomän i  [!DNL Journey Optimizer]
description: Lär dig delegera dina underdomäner
feature: Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, optimering, delegering
exl-id: 1b5ca4db-44d9-49e2-ab39-a1abba223ec7
source-git-commit: 7854de133ebcd3b29ca59b747aa89fae242f2ea5
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 24%

---

# Delegering av underdomän i [!DNL Journey Optimizer] {#subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_delegated_subdomains"
>title="Dina delegerade underdomäner visas här."
>abstract="Delegera din första underdomän. När delegeringen är klar skapas PTR-poster och e-postkanaler aktiveras."

Genom att skapa en underdomän för e-postkampanjer kan varumärken isolera olika typer av trafik (till exempel marknadsföring kontra företag) i specifika IP-pooler och med specifika domäner, vilket snabbar upp IP-uppvärmningsprocessen och förbättrar leveransmöjligheterna generellt.

Om du delar en domän och den blockeras eller läggs till i blockeringslista kan det påverka företagets e-postleverans. Men kända problem eller blockeringar på en domän som är specifik för din e-postmarknadsföring kommer att påverka just det e-postflödet. Om du använder huvuddomänen som avsändare eller Från-adress för flera e-postströmmar kan det också bryta e-postautentiseringen, vilket gör att dina meddelanden blockeras eller placeras i skräppostmappen.

>[!CAUTION]
>
>Du kan inte använda samma sändande domän för att skicka ut meddelanden från [!DNL Adobe Journey Optimizer] och från en annan produkt, till exempel [!DNL Adobe Campaign] eller [!DNL Adobe Marketo Engage].

## Varför konfigurera underdomäner? {#why-set-up-subdomains}

En underdomän är en division av din domän som kan användas för att isolera dina varumärken eller olika typer av trafik, till exempel transaktionsmeddelanden och marknadsföringskommunikation.

Låt oss ta exemplet med domänen ”mybrand.com” som används för att skicka både transaktions- och marknadsföringskommunikation. I det här fallet kan du konfigurera två underdomäner:

* underdomänen ”info.mybrand.com” för transaktionskommunikation (inköpsbekräftelser och lösenordsåterställning osv.) och
* underdomänen ”marketing.mybrand.com” för dina e-postmeddelanden till möjliga kunder.

På så sätt kan du bevara domänens och andra underdomäners rykte. Om t.ex. underdomänen ”marketing.mybrand.com” läggs till i blockeringslistan hos internetleverantörer på grund av dålig levererbarhet förhindrar detta att hela domänen ”mybrand.com” och underdomänen ”info.mybrand.com” läggs till i blockeringslistan.

När du implementerar en lösning finns det krav på komponenter som riktas mot utsidan: bland annat att ställa in länkar och webbsidor som ska spåras, visa spegelsidor osv.

Dessa krav hanteras via komponenter som finns både hos Adobe och kunden, men de innehåller URL:er som kan ses av mottagarna av e-postmeddelandena. För att undvika att ha URL:er som anger den underliggande tekniska lösningen eller värdtjänstleverantören, kan underdomäner konfigureras så att de blir genomskinliga för e-postmeddelandets mottagare.

**Läs mer**

* Lär dig hur du [delegerar dina underdomäner](delegate-subdomain.md) direkt från gränssnittet
* Lär dig hur du [lägger till Google TXT-poster](google-txt.md) i dina underdomäner för att se till att e-postmeddelanden skickas till Gmail-adresser
* Lär dig hur du [får åtkomst till de PTR-poster](ptr-records.md) som genererats för dina underdomäner, så att de kan verifieras genom att skicka e-postservrar

## Konfigurationsmetoder för underdomäner {#subdomain-delegation-methods}

Med subdomänkonfigurationen kan du konfigurera ett underavsnitt av din domän (tekniskt en &quot;DNS-zon&quot;) för användning med Adobe Campaign.

De tillgängliga konfigurationsmetoderna är följande.

### Delegera en underdomän till Adobe fullständigt (rekommenderas) {#full-subdomain-delegation}

Med [!DNL Journey Optimizer] kan du delegera dina underdomäner till Adobe helt och hållet direkt från produktgränssnittet. Genom att göra det kan Adobe leverera meddelanden som en hanterad tjänst genom att kontrollera och underhålla alla aspekter av DNS som krävs för att leverera, återge och spåra e-postkampanjer.

<!--The subdomain is fully delegated to Adobe. Adobe is able to control and maintain all aspects of DNS that are required for delivering, rendering and tracking messages.-->

Du kan förlita dig på att Adobe upprätthåller den DNS-infrastruktur som krävs för att uppfylla branschstandardkraven för leverans för e-postmarknadsföringsavsändardomäner, samtidigt som du fortsätter att underhålla och kontrollera DNS för dina interna e-postdomäner.

>[!IMPORTANT]
>
>Den fullständiga underdomänsdelegeringen är den rekommenderade metoden.

Lär dig hur du delegerar en underdomän till Adobe fullständigt i [det här avsnittet](delegate-subdomain.md#set-up-subdomain).

### Konfigurera en underdomän med CNAME {#cname-subdomain-setup}

Om du har domänspecifika begränsningsprinciper och du vill att Adobe endast ska ha partiell kontroll över DNS, kan du välja att utföra alla DNS-relaterade aktiviteter åt dig.

Med funktionen för konfigurering av CNAME-underdomäner kan du skapa en underdomän och använda CNAME för att peka mot Adobe-specifika poster. Med den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS för att konfigurera miljön för att skicka, återge och spåra e-postmeddelanden.

>[!CAUTION]
>
>CNAME-metoden rekommenderas om organisationens principer begränsar den fullständiga delegeringsmetoden för underdomäner. På det här sättet måste du behålla och hantera DNS-poster på egen hand.
>
>Adobe kan inte hjälpa till med att ändra, underhålla eller hantera DNS för en underdomän som konfigurerats med CNAME-metoden.

Lär dig hur du skapar en underdomän med CNAME:er för att peka på Adobe-specifika poster i [det här avsnittet](delegate-subdomain.md#cname-subdomain-setup).

## Jämföra konfigurationsmetoderna

Tabellen nedan tillhandahåller en sammanfattning av hur dessa metoder fungerar samt den troliga ansträngningsnivån:

| Konfigurationsmetod | Så fungerar det | Ansträngningsnivå |
|---|---|---|
| **Fullständig delegering** | Skapa underdomänen och posten för namnrymden. Adobe konfigurerar sedan alla DNS-poster som krävs för Adobe Campaign.<br/><br/>I den här konfigurationen är Adobe helt ansvarigt för att hantera underdomänen och alla DNS-poster. | Låg |
| **CNAME-metod** | Skapa underdomänen och posten för namnrymden. Adobe tillhandahåller sedan de poster som ska placeras i DNS-servrarna och konfigurerar motsvarande värden i Adobe Campaign DNS-servrar.<br/><br/>I den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS:er. | Hög |

<!--
| Configuration method | How it works | Level of effort |
|---|---|---|
| **Full delegation** | Create the subdomain and namespace record. Adobe will then configure all DNS records required for Adobe Campaign.<br/><br/>In this setup, Adobe is fully responsible for managing the subdomain and all the DNS records. | Low |
| **CNAME method** |  Create the subdomain and namespace record. Adobe will then provide the records to be placed in your DNS servers and will configure the corresponding values in Adobe Campaign DNS servers.<br/><br/>In this setup, both you and Adobe share responsibility for maintaining DNS. | High |
| **Custom delegation method** |  Create the subdomain and namespace record - Adobe will then provide the records to be placed in your DNS servers. Upload the SSL Certificate obtained from the Certificate Authority and complete the Feedback Loop steps by verifying domain ownership and reporting email address.<br/><br/>In this setup, you have full responsibility for maintaining DNS. | Very high |-->

Ytterligare information om domänkonfiguration finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/product-specific-resources/campaign/ac-domain-name-setup.html){target="_blank"}.

Om du har några frågor om konfigureringsmetoder för subdomäner kan du kontakta Adobe eller kontakta kundtjänst för att få rådgivning om slutprodukten.


