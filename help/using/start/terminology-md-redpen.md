---
solution: Journey Optimizer
product: journey optimizer
title: Nyckelterminologi
description: Viktig terminologi i AJO
feature: Get Started
role: Admin, Developer, User
level: Beginner
redpen-status: PASS_||_2025-04-28_15-13-07
exl-id: d4c968d2-5eae-4fff-9b67-427ac9d9d74c
hide: true
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 1%

---

# Terminologi

Välkommen till Adobe Journey Optimizer terminologi guide. Den här resursen ger tydliga och enkla definitioner av nyckeltermer som du stöter på när du använder plattformen. Genom att förstå dessa termer kan ni navigera i Adobe Journey Optimizer på ett säkert sätt, implementera marknadsföringsstrategier effektivt och samarbeta effektivt med teammedlemmar och Adobe support.

## Villkor för kärnplattform

| Villkor | Definition |
|------|------------|
| **Adobe Journey Optimizer (AJO)** | Ett verktyg som gör att du kan skapa och skicka personaliserade meddelanden till kunder i olika kanaler, till exempel e-post, textmeddelanden och mobilappsmeddelanden. Ni kan utforma kundresor som svarar på kundåtgärder i realtid. En e-postbekräftelse utlöses till exempel omedelbart efter att en kund har gjort ett köp på webbplatsen. |
| **Adobe Experience Platform (AEP)** | Grunden till Adobe Journey Optimizer. Här samlas alla kunddata in och organiseras på ett och samma ställe, vilket skapar kompletta kundprofiler som Adobe Journey Optimizer använder för att skicka personaliserade meddelanden. Betrakta AEP som det centrala navet när det gäller att skapa strategier för kundengagemang. |
| **Sandbox** | En separat arbetsyta där du testar och experimenterar utan att påverka kundkommunikationen. En sandlåda fungerar som ett övningsområde eller en testmiljö. Adobe Journey Optimizer tillhandahåller upp till fem sandlådor, så att team kan testa scenarier som introduktionsresor eller kampanjkampanjer. |

## Resevillkor och kampanjvillkor

| Villkor | Definition |
|------|------------|
| **Resa** | En serie sammankopplade steg som vägleder kunderna genom upplevelser med ert varumärke. En välkomstresa innehåller till exempel ett välkomstmeddelande, en påminnelse om appnedladdning och personaliserade produktrekommendationer. Varje steg inträffar efter att det föregående har slutförts, vilket möjliggör sekventiell, personlig interaktion. |
| **Campaign** | En enda kommunikation eller en uppsättning identiska meddelanden som skickas till en viss kundgrupp samtidigt. Till skillnad från resor, som utvecklas över tid, levererar kampanjer meddelanden samtidigt, antingen direkt eller vid en schemalagd tidpunkt. Du kan t.ex. schemalägga en kampanj via e-post för en helgförsäljning. |
| **Kanal** | Den metod som används för att kommunicera med kunder, till exempel e-post, SMS, push-meddelanden (mobilappsaviseringar), meddelanden i appen eller webbplatser. Varje kanal kräver en särskild konfiguration, t.ex. för att verifiera en e-postdomän eller ansluta en SMS-leverantör. |
| **Meddelande** | Det innehåll som skickas till kunderna, inklusive text, bilder och personaliserade element. Du skapar meddelanden för olika format, till exempel e-post, textmeddelanden och push-meddelanden. Ett meddelande kan till exempel vara ett&quot;tack&quot;-e-postmeddelande med dynamiskt infogade kundnamn och orderinformation. |
| **Händelse** | En förekomst som utlöser eller flyttar en resa framåt. Händelserna kan vara kundåtgärder, till exempel att göra ett köp, eller systemhändelser, till exempel att en ny kund registrerar sig. Händelser gör att resor kan reagera på kundaktiviteter i realtid. En kunds födelsedag utlöser till exempel ett särskilt rabattmeddelande. |

## Kund- och målgruppsvillkor

| Villkor | Definition |
|------|------------|
| **Profil** | En komplett bild av varje kund som kombinerar information som kontaktuppgifter, inköpshistorik, inställningar och beteenden. En&quot;engagerande profil&quot; avser en kund som kontaktats med Adobe Journey Optimizer under de senaste 12 månaderna. Profiler är nödvändiga för att skapa personaliserade, datadrivna upplevelser. |
| **Målgrupp** | En grupp kunder som delar gemensamma egenskaper eller beteenden. Exempel:&quot;kunder som köpt de senaste 30 dagarna&quot; eller&quot;kunder som är intresserade av produkter utomhus&quot;. Målgrupper skapas i Adobe Experience Platform och används i Adobe Journey Optimizer för att inrikta sig på specifika segment. |
| **Målgruppskvalifikation** | Den process som inträffar när en kund går med eller lämnar en målgrupp. Adobe Journey Optimizer aktiverar åtgärder automatiskt när någon kommer in i eller lämnar en målgrupp. Det skickar t.ex. ett välkomstmeddelande till nya lojalitetsprogrammedlemmar, som ser till att rätt information skickas i rätt tid. |
| **Adresserbar publik** | Det totala antalet kundprofiler ni kan nå. Med ditt konto får ni en adresserbar publik som är 25 % större än er avtalade engagerande målgrupp, vilket ger flexibilitet i takt med att kundbasen växer. |
| **Engagerbar målgrupp** | Antalet kunder som du aktivt kommunicerar med via Adobe Journey Optimizer baserat på ditt avtal. Detta garanterar att ni håller er inom licensgränserna samtidigt som ni fokuserar på värdefulla interaktioner. |
| **Segmentdefinition** | Reglerna som avgör vilka kunder som tillhör en målgrupp. Dessa regler baseras på attribut, beteenden eller andra kriterier. En segmentdefinition kan till exempel innehålla&quot;kunder som spenderat mer än 500 dollar de senaste sex månaderna&quot;. |

## Villkor för beslutshantering

| Villkor | Definition |
|------|------------|
| **Beslutshantering** | En funktion som automatiskt väljer det bästa innehållet eller det bästa erbjudandet för varje kund. Vi rekommenderar till exempel en kund som ofta överger sin kundvagn att få fri frakt. Detta säkerställer personaliserade och relevanta interaktioner. |
| **Erbjudande** | Ett specifikt marknadsföringsmeddelande eller en viss kampanj som presenteras för kunderna. Exempel: 20 % rabatt, fri frakt eller produktrekommendation. Adobe Journey Optimizer erbjuder upp till 10 erbjudanden per e-post, vilket möjliggör ett brett och skräddarsytt innehåll. |
| **Besluts-API** | En teknisk anslutning som gör det möjligt för andra system att fråga Adobe Journey Optimizer:&quot;Vad är det bästa erbjudandet för den här kunden just nu?&quot; Det valda erbjudandet visas på webbplatser, i appar eller i andra kanaler. Den här integreringen utökar Journey Optimizer möjligheter utöver e-post och SMS. |
| **Erbjudandebibliotek** | En central samling där alla marknadsföringserbjudanden lagras och hanteras. Detta säkerställer enhetlighet i alla kanaler och förenklar uppdateringar av marknadsföringsstrategier. |
| **Kvalifikationsregler** | Villkor som avgör om en kund kan ta emot ett visst erbjudande. Exempel:&quot;Visa endast den här rabatten för kunder som inte har köpt på 60 dagar.&quot; Dessa regler hjälper till att förhindra överbudande eller irrelevanta erbjudanden. |

## Data och tekniska villkor

| Villkor | Definition |
|------|------------|
| **Datalandningszon** | Ett tillfälligt lagringsområde där du placerar datafiler innan du flyttar dem till Adobe Experience Platform. Tänk dig att det är ett mellanlagringsområde för dina data. Du kan till exempel överföra en CSV-fil med kundtransaktioner här innan du integrerar den i systemet. |
| **Frågetjänst** | Ett verktyg som gör att du kan köra databasliknande frågor för att validera data efter att de har importerats till Adobe Journey Optimizer. Du kan till exempel fråga&quot;Hur många kunder har registrerat sig under den senaste veckan?&quot; för att säkerställa en korrekt målgruppssegmentering. |
| **Beräknat attribut** | En egenskap hos kunden som beräknas utifrån deras beteende. Exempel: &quot;genomsnittligt inköpsvärde&quot; eller &quot;totalt antal webbplatsbesök den här månaden.&quot; Dessa attribut hjälper er att personalisera meddelanden baserat på kundmönster, som att rikta in er på värdefulla kunder med exklusiva erbjudanden. |
| **Anpassningsfält** | Platshållare i meddelanden som ersätts med kundspecifik information, till exempel förnamn, nyligen gjorda köp eller medlemsnivå. Adobe Journey Optimizer har stöd för upp till fem personaliseringsfält per meddelande. Till exempel&quot;Hej [Förnamn]! Ditt senaste köp av [Produktnamn] är på väg!&quot; |
| **Schema** | En plan som definierar hur kunddata är ordnade. Den mappar de informationstyper som lagras och deras relationer. Ett tydligt schema säkerställer smidig integrering och korrekt dataanvändning i alla arbetsflöden. |
| **Datauppsättning** | En samling relaterade data som är ordnad enligt ett schema. Du kan till exempel ha separata datauppsättningar för inköpshistorik, webbplatsaktivitet och kundtjänstinteraktioner. Med dessa datauppsättningar kan ni analysera och agera utifrån olika aspekter av kundbeteende. |

## Innehåll och tillgångsvillkor

| Villkor | Definition |
|------|------------|
| **AI-assistenten** | En inbyggd funktion som använder artificiell intelligens för att skapa innehåll. Det genererar text, utformar e-postmeddelanden eller skapar meddelandevarianter för olika kanaler. Du kan till exempel be den att skapa ett reklamutskick baserat på målgruppens önskemål. |
| **Grundläggande om resurser** | Ett bibliotek som medföljer Adobe Journey Optimizer för att lagra och hantera digitala filer som bilder, logotyper och dokument. Den innehåller lagring för marknadsföringsresurser och stöder upp till fem användare med fullständig behörighet och 100 användare med visningsåtkomst. Detta förenklar samarbetet och säkerställer ett enhetligt varumärke. |
| **Innehållsfragment** | Återanvändbart innehåll som används i flera meddelanden. Till exempel en standardsidfot med kontaktinformation som visas i alla e-postmeddelanden. Detta ger enhetlighet och minskar tidsåtgången för att återskapa delade element. |
| **Mall** | En fördesignad meddelandelayout anpassad efter specifikt innehåll. Mallar hjälper till att bibehålla en enhetlig stil och känsla i kommunikationen, som varumärkesprofilerad e-postdesign eller SMS-format. |

## Rapporterings- och analysvillkor

| Villkor | Definition |
|------|------------|
| **Global rapport** | En omfattande översikt som visar hur alla resor och kampanjer fungerar. Det hjälper er att förstå trender i engagemanget över alla kanaler och utvärdera den övergripande marknadsföringseffektiviteten. |
| **Live-rapport** | Realtidsdata om pågående resor och kampanjer. Detta möjliggör omedelbara justeringar vid behov. Du kan till exempel pausa en kampanj med lågt engagemang och ändra dess budskap. |
| **Reserapport** | Detaljerade resultatinsikter om en viss resa. Det visar hur kunderna rör sig genom varje steg och var de kan lämna jobbet. Detta hjälper till att optimera kundupplevelserna. |
| **Meddelanderapport** | Statistik om ett visst meddelande, till exempel hur många som har levererats, öppnats och klickats. Den här informationen hjälper till att förbättra framtida kommunikation genom att visa hur väl kunderna svarar på ert innehåll. |

## Relaterad dokumentation

* [Kom igång med Adobe Journey Optimizer](get-started.md)
* [Arkitektur och begrepp](architecture-concepts-redpen.md)
* [Guide för funktionsområden](functional-areas-redpen.md)
