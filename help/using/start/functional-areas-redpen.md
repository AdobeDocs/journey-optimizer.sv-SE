---
solution: Journey Optimizer
product: journey optimizer
title: Funktionsområden
description: Funktionsområden i AJO
feature: Get Started
role: Admin, Developer, User
level: Beginner
redpen-status: PASS_||_2025-04-28_15-13-07
exl-id: c9b02ae2-e07b-41f4-90cc-b2c0966f1ed1
hide: true
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 0%

---

# Kärnbegrepp

Adobe Journey Optimizer (AJO) innehåller flera viktiga funktionsområden som samverkar smidigt. I den här guiden förklaras varje område och beskrivs hur dessa områden kombineras för att skapa slagkraftiga kundupplevelser. Genom att förstå dessa funktionsområden kan ni utnyttja AJO för att leverera personaliserade upplevelser i flera kanaler på ett effektivt sätt.

## Översikt över funktionsområden

| Funktionsområde | Primär förmån | Analogy |
|-------------------------|--------------------------------------------------|------------------------|
| Datahantering | Ordna rätt kunddata | Grunden |
| Kundhantering | Förstå vilka era kunder är | Lär känna er målgrupp |
| Innehållshantering | Skapa och hantera enhetliga, personaliserade meddelanden | Skapa ditt meddelande |
| Beslutshantering | Välj det bästa meddelandet/erbjudandet i realtid | Hjärnorna |
| Journey Management | Designa och automatisera smidiga kundupplevelser | Orchestra Conducer |
| Anslutningar | Koppla samman datakällor och leverera via kundkanaler | Rör |
| Administration och sekretess | Styr konfiguration, åtkomst och säkerställ att data följs | The Rulebook |

## Detaljerade funktionsområden

### Datahantering: Grunden

**Syfte**: Infoga, strukturera och hantera data som driver personaliseringen. I den här processen ingår att definiera datastrukturer (scheman), skapa lagringsbehållare (datauppsättningar) och importera data från olika system.

Hantera datahantering som grunden för allt kundengagemang. En välstrukturerad grund för data säkerställer att varje beslut, meddelande och resa använder korrekt och ordnad information.

**Nyckelkomponenter**:

- **Skapa och hantera schema**: Definiera strukturen för kunddata.
   - Exempel: Skapa ett schema som visar fält som&quot;Förnamn&quot;,&quot;E-postadress&quot; och&quot;Inköpshistorik&quot;.
- **Datauppsättningskonfiguration**: Ordna data i logiska behållare.
   - Exempel: Gruppera transaktionsdata i en&quot;Sales Transactions&quot;-datamängd för enklare analys.
- **Arbetsflöden för dataöverföring**: Importera data till plattformen effektivt.
   - Exempel: Använd färdiga Source Connectors för att importera kunddata från ett CRM-system (Customer Relationship Management).
- **Verktyg för datakvalitet**: Bibehåll datakvaliteten och fullständigheten.

**Fördelar**: Ser till att kunddata är tillförlitliga, ordnade och tillgängliga och utgör grunden för alla AJO-aktiviteter. Färdiga Source Connectors effektiviserar datainmatningen från vanliga plattformar.



### Kundhantering: Lär känna er målgrupp

**Syfte**: Bygg och underhåll en djupgående förståelse av varje kund. Detta innebär att man använder Adobe Experience Platform (AEP) kundprofil i realtid för att sammanfoga data från alla kontaktytor i en enhetlig vy. Det hanterar också identiteter på olika enheter och i olika kanaler, vilket gör det möjligt att gruppera individer i målgruppsanpassade målgrupper baserat på delade attribut eller beteenden.

Kundhanteringsverktygen kopplar samman olika datapunkter för att ge en sammanhängande bild av varje kund. Tack vare den här förståelsen kan ni leverera relevanta och personaliserade upplevelser.

**Nyckelkomponenter**:

- **Kundprofil i realtid**: Enhetlig vy över varje kund.
   - Exempel: Kombinera webbhistorik, appinteraktioner och offlineköp i en enda profil.
- **Identitetsupplösning**: Länka kunddata mellan enheter och kanaler.
   - Exempel: Matcha en kunds e-postadress med appanvändningsdata med Identity Graph.
- **Skapa och hantera målgrupper**: Definiera grupper baserat på attribut och beteenden.
   - Exempel: Skapa en målgrupp för&quot;lojala kunder&quot; som har gjort fler än fem inköp det senaste året.
- **Segmentering**: Använd regler för dynamiskt målgruppsmedlemskap.
   - Exempel: Ställ in ett segment för&quot;HDR&quot; som uppdateras automatiskt när kunderna spenderar över 500 dollar.

**Fördelar**: Möjliggör exakt målgruppsanpassning och personalisering genom en dynamisk förståelse av individuella preferenser, historik och segmentmedlemskap.



### Innehållshantering: Skapa ditt meddelande

**Syfte**: Skapa, hantera, personalisera och återanvänd marknadsföringsinnehåll i flera kanaler. Detta innefattar att hantera digitalt material, bygga meddelanden med visuella redigerare eller kod, utnyttja återanvändbara innehållsmallar och fragment, skapa landningssidor och använda artificiell intelligens (AI) för innehållsgenerering.

Med verktygen för innehållshantering kan teamen effektivt skapa och leverera skräddarsydda meddelanden, med bibehållen enhetlighet och relevans vid alla kontaktytor.

**Nyckelkomponenter**:

- **Innehållsredigerare**: Skapa och formatera meddelanden visuellt eller med kod.
   - Exempel: Använd den visuella redigeraren för att utforma en e-postkampanj som främjar semesterförsäljning.
- **Digital resurshantering**: Ordna och använda bilder och andra media.
   - Exempel: Lagra produktbilder i ett centraliserat bibliotek för enkel återanvändning i kampanjer.
- **Mallar och fragment**: Skapa återanvändbara innehållskomponenter.
   - Exempel: Skapa en mall för välkomstmeddelande som dynamiskt infogar kundnamn.
- **Personalization-verktyg**: Anpassa innehåll dynamiskt för enskilda användare.
   - Exempel: Visa anpassade produktrekommendationer baserat på webbhistorik.
- **Landningssidbyggare**: Skapa webbmål för kampanjer.

**Fördelar**: Effektiviserar skapandet av innehåll, säkerställer varumärkets enhetlighet och underlättar effektiv leverans av personaliserade meddelanden.



### Beslutshantering: The Brains of Personalization

**Syfte**: Välj det bästa meddelandet eller erbjudandet för varje kund i rätt ögonblick, baserat på deras realtidsprofil, kontext och fördefinierade affärsregler eller AI-modeller. Beslutshantering innebär att hantera ett centralt bibliotek med erbjudanden, definiera regler för behörighet, tillämpa begränsningar (som frekvensbegränsning) och upprätta rangordningslogik.

Beslutshanteringen säkerställer att personaliseringen fungerar i stor skala genom att ge maximalt värde genom intelligent automatisering.

**Nyckelkomponenter**:

- **Erbjudandebibliotek**: Centralt lagringsutrymme för marknadsföringserbjudanden.
   - Exempel: Lagra erbjudanden som&quot;20 % rabatt&quot; eller&quot;fri frakt&quot; i ett delat bibliotek.
- **Beslutsregler**: Logik för att välja optimalt innehåll.
   - Exempel: Visa endast&quot;Loyalty Discount&quot; för kunder i segmentet&quot;Loyal Customers&quot;.
- **Begränsningar och behörighet**: Kontrollera vem som får vad och när.
   - Exempel: Använd frekvensbegränsning för att hindra en kund från att få samma erbjudande två gånger i veckan.
- **Rankningsstrategier**: Prioritera erbjudanden baserat på affärsmål eller AI.
   - Exempel: Rankning av erbjudanden efter lönsamhet, där högmarginalprodukter visas först.
- **Simuleringsverktyg**: Testa och validera beslutsstrategier.

**Fördel**: Automatiserar och optimerar personaliseringen och ser till att relevanta och slagkraftiga upplevelser levereras vid varje kontaktyta.



### Resehantering: Orkesterkonduktorn

**Syfte**: Designa, samordna och automatisera kundupplevelser i flera steg och i flera kanaler. Resor reagerar på kundbeteenden och händelser i realtid och vägleder individer genom personaliserade vägar. AJO stöder också kampanjer för att leverera schemalagda engångskommentarer till specifika målgrupper.

Resehantering gör att upplevelserna känns anpassningsbara och sömlösa, och guidar individer baserat på deras preferenser och åtgärder.

**Nyckelkomponenter**:

- **Resedesigner**: Visuell arbetsyta för att skapa kundsökvägar.
   - Exempel: Designa en resa som skickar ett välkomstmeddelande när en kund registrerar sig.
- **Reseutlösare**: Händelser som startar eller flyttar framåt.
   - Exempel: Utlös ett uppföljnings-SMS när en kund har övergett sin kundvagn.
- **Villkorssteg**: Använd logikbaserad förgrening.
   - Exempel: Skicka ett annat meddelande beroende på om en kund öppnar ett e-postmeddelande.
- **Vänteaktiviteter**: Kontrollera förloppet med tidsfördröjningar.
   - Exempel: Vänta i tre dagar innan du skickar ett påminnelsemejl.
- **Kampanjhantering**: Verktyg för schemalagda engångsmeddelanden.

**Fördelar**: Skapar sömlösa, sammankopplade upplevelser som anpassar sig till enskilda interaktioner, vårdar relationer och ger önskat resultat.



### Anslutningar: Rör

**Syfte**: Hantera dataflöde till AJO (källor) och meddelande- eller dataleverans från AJO (kanaler och mål). Källor för in data i Adobe Experience Platform (AEP). Kanaler levererar meddelanden (via e-post, SMS, push, webben osv.). Destinationer gör att målgrupps- eller datauppsättningsinformation kan flödas till externa plattformar.

Anslutningarna säkerställer att data kommer in i AJO effektivt och når kunderna på ett tillförlitligt sätt via rätt kontaktyta.

**Nyckelkomponenter**:

- **Source-anslutningar**: Importera data till plattformen.
   - Exempel: Använd en koppling för att hämta inköpsdata från en e-handelsplattform.
- **Kanalkonfiguration**: Konfigurera och hantera leveransmekanismer.
   - Exempel: Konfigurera SMS-leverans för kampanjmeddelanden.
- **Målkonfiguration**: Anslut till externa aktiveringssystem.
   - Exempel: Dela målgruppsdata med en annonseringsplattform för sociala medier.
- **Dataflödeshantering**: Kontrollera informationsförflyttning.

**Fördelar**: Säkerställer effektiv datainmatning och tillförlitlig meddelandeleverans över alla kanaler samtidigt som aktivering aktiveras i externa system.



### Administration och sekretess: Regelboken

**Syfte**: Konfigurera systeminställningar, hantera användaråtkomst och behörigheter, konfigurera kommunikationskanaler, definiera parametrar för resan och säkerställa efterlevnad av datasekretess- och styrningsprinciper. Detta innefattar att hantera samtycke, tillämpa regler för dataanvändning och hantera förfrågningar om dataåtkomst eller -borttagning.

Administrations- och sekretessverktygen säkerställer att dataintegriteten skyddas och att alla juridiska och organisatoriska policyer följs.

**Nyckelkomponenter**:

- **Hantering av användare och åtkomst**: Kontrollera åtkomst och behörigheter.
   - Exempel: Tilldela specifika behörigheter till marknadsförings- och IT-team.
- **Sandlådekonfiguration**: Separata miljöer för utveckling och testning.
   - Exempel: Använd en sandlåda för att testa nya resedesigner innan du distribuerar dem live.
- **Kanalkonfiguration**: Konfigurera tekniska inställningar för leverans.
   - Exempel: Konfigurera e-postserverinformation för kampanjmeddelanden.
- **Sekretessverktyg**: Hantera inställningar för samtycke och sekretess.
   - Exempel: Hantera effektivt förfrågningar från GDPR (General Data Protection Regulation) om databorttagning.
- **Styrningskontroller**: Använd dataanvändningsprinciper.

**Fördelar**: Säkerställer säker plattformsåtgärd, efterlevnad av regler och anpassning till organisationsprofiler.



## Koppla samman punkter: Hur fungerar allt tillsammans

Dessa funktionsområden har en kontinuerlig cykel för att leverera och optimera personaliserade kundupplevelser:

1. **Datainmatning**: Dataflöden in i AEP, strukturerade med datahantering.
2. **Kundförståelse**: Kundprofiler i realtid förenar dessa data, medan kundhantering förfinar insikterna via profiler och målgrupper.
3. **Innehålls- och erbjudandestrategi**: Innehållshantering skapar meddelanden och resurser. Beslutshantering definierar erbjudanden och logik för att välja den bästa.
4. **Orchestration**: Resehantering mappar ut interaktioner över flera kanaler och utnyttjar kundförståelse, innehåll och beslut.
5. **Leverans**: Anslutningar underlättar meddelandeleverans via valda kanaler eller delar data med externa system.
6. **Mått och optimering**: Prestandadata och kundinteraktioner ger insikter tillbaka till systemet för att förfina målgrupper, innehåll, beslut och resor.
7. **Styrning**: Administrations- och sekretesskontroller säkerställer efterlevnad och korrekt systemkonfiguration.

Denna iterativa process gör det möjligt för organisationer att kontinuerligt lära sig och förbättra sina strategier för kundengagemang.
