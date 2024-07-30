---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: b93c9f7262c5b5530699bb2843f2a8d8dd97a839
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 5%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver från de senaste innovationerna och förbättringarna. Läs mer om de här ändringarna i [Adobe Experience Platform versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsnyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket mer levererade direkt till din inkorg varje kvartal.


## Versionsinformation juli 2024 {#27-4-2024}

**Noteringar om tidig version nedan kan ändras utan föregående meddelande till releasedatum**. Länkar, skärmar och uppdaterad dokumentation publiceras på den här sidan på releasedatum.

**Releasedatum**: 30-31 juli 2024

### Nya funktioner {#27-4-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

<!--table>
<thead>
<tr>
<th><strong>IP Warmup Workflow</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>If you are sending email on a brand new IP address, you can now easily perform IP warmup workflows directly from the user interface. Adobe Journey Optimizer offers a standardized and efficient way to warm up your IP adresses that follows the best practices for optimal deliverability.</p>
<p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>SMS-kanal med valfri leverantör (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du konfigurera ytterligare SMS-leverantörer i Journey Optimizer, utöver standardleverantörerna Sinch, Infobip och Twilio.</p>
<img src="assets/do-not-localize/byo_sms.gif"/>
<p>Mer information finns i den <a href="../sms/sms-configuration-custom.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Federated Audience Composition (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Federated Audience Composition är nu tillgängligt i Adobe Journey Optimizer. Det gör det möjligt för företag att sammanställa data för bättre användning i olika användningsfall. Med detta nya tillvägagångssätt, som Adobe Real-time Customer Data Platform- och/eller Adobe Journey Optimizer-användare, kan ni federera datauppsättningar direkt från ert befintliga datalager för att skapa och berika Adobe Experience Platform målgrupper och attribut i ett och samma system.</p>
<p>Mer information finns i den <a href="https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/home"  target="_blank">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar {#27-4-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

**Resor**

* (Tillgänglighetsdatum: 8 juli) **Avancerad uttrycksredigerare i konfiguration av resthändelser** - Du kan nu utnyttja den avancerade uttrycksredigeraren när du konfigurerar en händelse, så att du kan definiera mer komplexa uttryck eller använda funktioner i händelse-ID-villkoret. [Läs mer](../event/about-creating.md#adv-exp-editor)

<!--**Audiences**

* The use of audiences from custom upload (CSV file) is now available for use with Privacy and Security Shield.-->

## Versionsinformation juni 2024 {#24-6-2024}

**Releasedatum**: 18-19 juni 2024

### Nya funktioner {#june-24-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

<!--table>
<thead>
<tr>
<th><strong>IP Warmup Workflow</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>If you are sending email on a brand new IP address, you can now easily perform IP warmup workflows directly from the user interface. Adobe Journey Optimizer offers a standardized and efficient way to warm up your IP adresses that follows the best practices for optimal deliverability.</p>
<p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->


<table>
<thead>
<tr>
<th><strong>Anpassning av innehållsfragment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du definiera specifika fält i ett fragment som kan redigeras när fragmentet läggs till i en kampanj eller resa. Detta gör det möjligt att justera innehållsdelar vid tiden för användningen, vilket ger flexibilitet att åsidosätta standardvärden med kontextspecifika detaljer.</p>
<img src="../content-management/assets/do-not-localize/gif-fragments.gif"/>
<p>Mer information finns i den <a href="../content-management/customizable-fragments.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Rapportering med Customer Journey Analytics (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer rapportering har en förbättrad interoperabilitet med Customer Journey Analytics, standardiserad rapportering på båda plattformarna och förbättrad datakonsekvens och tillförlitlighet. Denna smidiga integrering mellan Journey Optimizer och Customer Journey Analytics ger en tydligare bild av prestandamätningarna, så att användarna kan fatta mer välgrundade beslut.</p>
<img src="assets/do-not-localize/ajo-cja.gif"/>
<p>Mer information finns i den <a href="../reports/report-gs-cja.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>AI Assistant i Adobe Journey Optimizer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI-assistenten är en funktion i användargränssnittet som du kan använda för att navigera bland och förstå Adobe-koncept och få driftsinsikter för just din miljö. Det finns i flera Adobe Experience Cloud-produkter, inklusive Adobe Journey Optimizer.</p>
<p>Mer information finns i den <a href="../start/ai-assistant.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Flerspråkiga meddelanden under resor och kampanjer (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan ni enkelt skapa innehåll på flera språk i en enda kampanj eller resa. Med den här funktionen kan ni växla mellan olika språk när ni redigerar kampanjer eller hela kundresan, effektivisera hela redigeringsprocessen och förbättra möjligheterna att effektivt hantera flerspråkigt innehåll.</p>
<p>Flerspråkigt innehåll är för närvarande endast tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Experimentera med resor (begränsad tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer finns redan i kampanjer och stöder nu experiment på resor. Experimentella tester är randomiserade, vilket i samband med onlinetestning innebär att du exponerar vissa slumpmässigt utvalda användare för en viss variant av ett meddelande och en annan slumpmässigt utvald uppsättning användare för annan variation eller behandling. Efter exponering kan du mäta de resultatvärden du är intresserad av, som öppningar av e-post, prenumerationer eller inköp.</p>
<p>Experimentation i resor är för närvarande endast tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
</td>
</tr>
</tbody>
</table>

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

### Förbättringar {#june24-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

#### Beslutshantering

* **Stöd för flera regler i beslutshantering** - Du kan nu lägga till upp till 10 appningsregler för ett visst erbjudande i beslutshantering. På så sätt kan ni öka kontrollen över hur erbjudandena skickas. [Läs mer](../offers/offer-library/add-constraints.md#capping)

<!--* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->

#### Innehållsfragment

>[!AVAILABILITY]
>
>Observera att dessa förbättringar kommer att introduceras gradvis under flera dagar efter den första versionen. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i deras miljöer.

* Fragment kan nu redigeras och ändringar kan spridas över alla liveresor och -kampanjer där de används.
* Nya statusar för innehållsfragment har introducerats: **Utkast**, **Live**, **Publicering** och **Arkiverat**.
* Om du vill använda ett fragment i en resa eller kampanj måste det nu ha statusen **Live**. Ett nytt steg har lagts till i processen för att skapa fragment, vilket gör att fragmentet kan publiceras och göras tillgängligt för användning under resor och kampanjer. Observera att fragmentpublicering kräver en ny behörighet.

  **VARNING** - Sedan statusvärdena **Utkast** och **Live** introducerades i Journey Optimizer Juniversion har alla fragment som skapats före den här versionen statusen **Utkast**, även om de används under en resa eller kampanj. Om du ändrar något i dessa fragment måste du [publicera dem](../content-management/create-fragments.md#publish) för att göra dem&quot;Live&quot; och sprida ändringarna till associerade kampanjer och resor. Ni måste också skapa en ny resa/kampanjversion och publicera den.

Läs mer i dokumentationen för [innehållsfragment](../content-management/fragments.md).

#### Resor

* Den globala tidsgränsen för resor har utökats till 91 dagar. [Läs mer](../building-journeys/journey-properties.md#global_timeout)

  Alla nya resor som skapas kommer att få den här nya tidsgränsen angiven. Läs [Frågor och svar](../building-journeys/journey-properties.md#timeout-faq) om du vill veta mer. Observera att dessa ändringar kommer att införas gradvis under juni månad.


* Adobe Journey Optimizer har nu stöd för förfrågningar om borttagning/åtkomst av sekretess samt livscykelhantering av data. [Läs mer](../privacy/requests.md)
* Du kan nu ändra storlek på kolumnerna i kundresans lager.
  <!--* **Advanced expression editor in Event configuration** is now GA - You can now leverage the advanced expression editor while configuring an event, allowing you to define more complex expressions or use functions in the event id condition. This capability is released in Limited Availability for selected customers. [Read more](../event/about-creating.md)-->
* **Sammanslagningsprinciper** är nu GA - Sammanslagningsprinciper som används av en resa är nu synliga och konsekventa under hela resan. [Läs mer](../building-journeys/journey-properties.md#merge-policies)



#### Kampanjer

* När du skapar en kampanj i Adobe Journey Optimizer kan du nu välja kampanjtyp (schemalagd eller utlöst) i en ny modal. [Läs mer](../campaigns/create-campaign.md)

#### E-postkanal

* **List-unsubscribe** - Efter de senaste Gmail- och Yahoo-meddelandena för massavsändare stöder Journey Optimizer alternativet &quot;post/1-click&quot; List-Unsubscribe. Se följande sidor: [Hantera avanmälan via e-post](../email/email-opt-out.md#unsubscribe-header) och [Konfigurera e-postinställningar](../email/email-settings.md#list-unsubscribe).

  **Obs!** - Som standard är alternativet för att avbryta prenumerationen aktiverat för alla nya kanalytor. För befintliga ytor är som standard alternativet för att avbryta prenumeration av URL-adress med ett klick i kanalytans inställningar avmarkerat. Om du använde en avanmälnings-URL med ett klick i e-postmeddelandets brödtext tidigare är den här inställningen fortfarande giltig. Om du markerar alternativet för att avbryta prenumerationen med ett klick i inställningarna för kanalens yta, använder Adobe Journey Optimizer den standardgenererade URL-adressen för att avbryta prenumerationen med ett klick i inställningarna för kanalens yta.

#### SMS-kanal

* Nu kan du lägga till unika korta koder för varje sandlåda med en enda API-konfiguration, vilket gör processen effektivare och smidigare. [Läs mer](../sms/sms-configuration.md)

* Efter skapandet maskeras fältet **API-token** på sidan **API-autentiseringsinformation**.

<!--* You can now modify existing SMS configurations.-->

#### Kanal i appen

<!--* **Expression fragment** - Expression fragments are now available for the **In-app channel**. [Read more](../personalization/use-expression-fragments.md)-->

* Nu kan du använda Edge Delivery plugin för att få information som behövs för att förstå och felsöka dina inkommande implementeringar. [Läs mer om Edge Delivery-vyn](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}.


#### Direktpostkanal

* Direktreklamkanalen är nu tillgänglig för alla kunder. [Läs mer](../direct-mail/get-started-direct-mail.md)

