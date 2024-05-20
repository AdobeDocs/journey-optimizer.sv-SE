---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
topic: Content Management
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: bf098c2b8c1eeb48b4c2a2857db9946c32533ffe
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 3%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformation](release-notes.md).

**Tidiga versionsinformation nedan kan ändras utan föregående meddelande till dess att releasedatumet blir tillgängligt**. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation maj 2024 {#e-2024}

**Releasedatum**: 21-22 maj 2024

### Nya funktioner {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.


<table>
<thead>
<tr>
<th><strong>Experience Decision - begränsad tillgänglighet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Experience Decision förenklar personaliseringen genom att erbjuda en centraliserad katalog med marknadsföringserbjudanden som kallas beslutsposter och en sofistikerad beslutsmotor. Den här motorn använder regler och rankningskriterier för att välja ut och presentera de mest relevanta beslutsobjekten för varje enskild person.</p>
<p>Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den nya kodbaserade upplevelsekanalen, som nu är tillgänglig inom Journey Optimizer-kampanjer. Policy för Experience Decision-beslut är endast tillgängliga för kodbaserade upplevelsekampanjer.</p>
<p>Experience Decision är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
<img src="assets/do-not-localize/gif-exd.gif"/>
<p>Mer information finns i den <a href="../experience-decisioning/gs-experience-decisioning.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Arbetsflöde för IP-förstärkning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Om du skickar e-post till en helt ny IP-adress kan du nu enkelt utföra arbetsflöden för IP-värmare direkt från användargränssnittet. Adobe Journey Optimizer erbjuder ett standardiserat och effektivt sätt att värma upp era IP-adresser som följer de bästa metoderna för optimal leverans.</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Business rules - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create granular frequency capping rules, and apply them to different types of marketing communications through rule sets. This new capability lets you control how often your audiences receive a message by setting cross-channel rules, that automatically exclude over-solicited profiles from messages and actions.</p>
<p>Business rules capability is currently available as a beta. To join the beta program, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>Extended personalization data - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now lookup and fetch data values within Adobe Experience Platform datasets, and use these values to build conditions in Adobe Journey Optimizer. You can leverage data from a lookup dataset when a relationship has been defined using an attribute inside of an array of objects. You can specify non-profile enabled datasets for lookup. Once enabled, you can use a profile attribute as a join key to the specified dataset to retrive further data for personalization.</p>
<p>This capability is currently available as a public beta.</p>
</td>
</tr>
</tbody>
</table-->

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Experience Decision** (Begränsad tillgänglighet)

Från betaversion till den här versionen har följande förbättringar lagts till:

* **Experience Decision + Code-based experiences** - Nu kan ni utnyttja beslutsfunktionen i Experience för att använda beslutsobjekt i era kodbaserade kampanjer. Obs! Den kodbaserade upplevelsekanalen och Experience Decision är inte tillgängliga för organisationer som har köpt Adobe Healthcare Shield och tillägg till Privacy and Security Shield. [Läs mer](../code-based/get-started-code-based.md)
* **Kontextdata** - Nu kan du utnyttja kontextdata från Adobe Experience Platform i dina regler för beslutsfattande och rangordningsformler. [Läs mer](../experience-decisioning/context-data.md)
* **Ny behörighet** - Det finns nu en ny behörighet för att hantera Experience Decision Management-resursen. Det gör att ni kan hantera rättigheter för Experience Decision. [Läs mer](../experience-decisioning/gs-experience-decisioning.md)
* **Begränsningsregler** - Du kan nu lägga till flera regler för att sätta stopp för ett visst beslutsobjekt i Experience Decisioning. På så sätt kan ni öka kontrollen över hur erbjudandena skickas. [Läs mer](../experience-decisioning/items.md#capping)
* **Rapportering** - Nu kan du skapa anpassade rapportinstrumentpaneler för Experience Decision-kampanjer med [!DNL Customer Journey Analytics]. [Läs mer](../experience-decisioning/cja-reporting.md)


**Beslutshantering**

* **Stöd för flera regler** - Du kan nu lägga till upp till 10 regler om begränsning av ett visst erbjudande i Beslutshantering. På så sätt kan ni öka kontrollen över hur erbjudandena skickas.
* **Granskningar** - **Ändra logg** så att du kan se alla ändringar som har gjorts i ett erbjudande eller ett beslut har tagits bort. Ändringar som rör erbjudanden och beslut kan nu ses i **Granskningar** -menyn.


**E-postkanal**

* **List-unsubscribe** - Efter de senaste Gmail- och Yahoo-meddelandena om bulkavsändare stöder Journey Optimizer alternativet&quot;post/1-click&quot; List-Unsubscribe.
* **Skräddarsy poäng** (Beta) - Nu kan du kontrollera ditt innehåll som skräppost i en dedikerad skräppostrapport. Med SpamAssassin kan Adobe Journey Optimizer nu testa ditt e-postinnehåll och ge det ett poängvärde som anger om internetleverantörer kommer att betrakta det som skräppost eller inte.
  <!--[Read more](../content-management/spam-report.md)-->

<!--
**Audiences**

* The use of audiences and attributes from audience composition and custom upload (CSV file) is now available for use with Healthcare Shield or Privacy and Security Shield.-->

**Personalisering**

* **Uttrycksfragment** - Uttrycksfragment är nu tillgängliga för **Kanal i appen**.
  <!--[Read more](../personalization/use-expression-fragments.md)-->

**Resor**

<!--* **Merge policies** (Limited Availability)- Merge policies used by a journey are now visible and consistent throughout the journey.-->
* **Stöd för mTLS** - mTLS-autentisering stöds nu i anpassade åtgärder. Det krävs ingen ytterligare konfiguration i den anpassade åtgärden eller resan för att aktivera mTLS. Den sker automatiskt när en mTLS-aktiverad slutpunkt identifieras.
* **Sök tabeller i händelser** - Du kan nu utnyttja data från en uppslagsdatauppsättning när en relation har definierats med ett attribut inuti en objektmatris. Uppslagsvärdena är tillgängliga i resor (villkor, anpassade åtgärder osv.) och personalisering av meddelanden.

**Globalisering**

I vårt pågående arbete med att leverera en enhetlig användarupplevelse harmoniserar vi terminologin som används i Adobe Experience Cloud produkter och appar. Det här påverkar den tyska termen &quot;Titel&quot; som ändras till &quot;Label&quot; när det gäller namnet på ett objekt. Ändringarna införs stegvis i användargränssnittet och dokumentationen.
