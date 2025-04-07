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
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 23%

---

# Delegering av underdomän i [!DNL Journey Optimizer] {#subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_delegated_subdomains"
>title="Dina delegerade underdomäner visas här."
>abstract="Delegera din första underdomän. När delegeringen är klar skapas PTR-poster och e-postkanaler aktiveras."

Genom att skapa en underdomän för e-postkampanjer kan varumärken isolera olika typer av trafik (till exempel marknadsföring kontra företag) i specifika IP-pooler och med specifika domäner, vilket snabbar upp IP-uppvärmningsprocessen och förbättrar leveransmöjligheterna generellt.

Om du delar en domän och den blockeras eller läggs till i blockeringslista kan det påverka företagets e-postleverans. Men kända problem eller blockeringar på en domän som är specifik för din e-postmarknadsföring kommer att påverka just det e-postflödet. Om du använder huvuddomänen som avsändare eller Från-adress för flera e-postströmmar kan det också bryta e-postautentiseringen, vilket gör att dina meddelanden blockeras eller placeras i skräppostmappen.

>[!NOTE]
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

Med subdomänkonfigurationen kan du konfigurera ett underavsnitt av din domän (tekniskt en &quot;DNS-zon&quot;) för användning med Adobe Campaign. Tillgängliga installationsmetoder är:

* **Fullständig underdomändelegering till Adobe** (rekommenderas): Underdomänen har delegerats till Adobe. Adobe kan styra och underhålla alla aspekter av DNS som krävs för att leverera, återge och spåra meddelanden. [Läs mer om fullständig delegering av underdomäner](delegate-subdomain.md#full-subdomain-delegation)

* **Använda CNAME**: Skapa en underdomän och använd CNAME för att peka på Adobe-specifika poster. Med den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS. [Läs mer om delegering av CNAME-underdomäner](delegate-subdomain.md#cname-subdomain-delegation)

>[!CAUTION]
>
>* Den fullständiga underdomänsdelegeringen är den rekommenderade metoden.
>
>* CNAME-metoden rekommenderas om organisationens principer begränsar den fullständiga delegeringsmetoden för underdomäner. På det här sättet måste du behålla och hantera DNS-poster på egen hand. Adobe kan inte hjälpa till med att ändra, underhålla eller hantera DNS för en underdomän som konfigurerats med CNAME-metoden.

Tabellen nedan tillhandahåller en sammanfattning av hur dessa metoder fungerar samt den troliga ansträngningsnivån:

| Konfigurationsmetod | Så fungerar det | Ansträngningsnivå |
|---|---|---|
| **Fullständig delegering** | Skapa underdomänen och posten för namnrymden. Adobe konfigurerar sedan alla DNS-poster som krävs för Adobe Campaign.<br/><br/>I den här konfigurationen är Adobe helt ansvarigt för att hantera underdomänen och alla DNS-poster. | Låg |
| **CNAME och anpassad metod** | Skapa underdomänen och posten för namnrymden. Adobe tillhandahåller sedan de poster som ska placeras i DNS-servrarna och konfigurerar motsvarande värden i Adobe Campaign DNS-servrar.<br/><br/>I den här konfigurationen delar både du och Adobe ansvaret för att underhålla DNS:er. | Hög |

Ytterligare information om domänkonfiguration finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/product-specific-resources/campaign/ac-domain-name-setup.html).

Om du har några frågor om konfigureringsmetoder för subdomäner kan du kontakta Adobe eller så småningom kontakta kundtjänst för att få rådgivning om slutprodukten.

## Åtkomst till delegerade underdomäner {#access-delegated-subdomains}

Alla dina delegerade underdomäner visas på menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Subdomains]**. Det finns filter som hjälper dig att förfina listan (delegeringsdatum, användare eller status).

![](assets/subdomain-list.png)

Kolumnen **[!UICONTROL Status]** innehåller information om delegeringsprocessen för underdomäner:

* **[!UICONTROL Draft]**: Underdomänsdelegeringen har sparats som ett utkast. Klicka på underdomänens namn för att återuppta delegeringsprocessen,
* **[!UICONTROL Processing]**: Underdomänen genomgår flera konfigurationskontroller innan den kan användas,
* **[!UICONTROL Success]**: Underdomänen har gått igenom kontrollerna och kan användas för att leverera meddelanden,
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades efter att delegeringen av underdomäner skickades.

Om du vill få tillgång till detaljerad information om en underdomän med statusen **[!UICONTROL Success]** öppnar du den i listan.

![](assets/subdomain-delegated.png)

Du kan:

* Hämta det underdomännamn (skrivskyddat) som konfigurerats under delegeringsprocessen samt de URL:er som genereras (resurser, spegelsidor, spårnings-URL:er),

* Lägg till en TXT-post för webbplatsverifiering från Google i din underdomän för att kontrollera att den är verifierad (se [Lägg till en TXT-post från Google i en underdomän](google-txt.md)).


>[!CAUTION]
>
>Underdomänskonfigurationen är gemensam för alla miljöer. Därför kommer alla ändringar av en underdomän också att påverka produktionssandlådorna.
