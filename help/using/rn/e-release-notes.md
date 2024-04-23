---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
topic: Content Management
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
hide: true
hidefromtoc: true
source-git-commit: 63dfe9a27f8a24a1c78968fa60252e16c87abebd
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---

# Tidig versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformation](release-notes.md).

Noteringarna nedan kan ändras utan föregående meddelande fram till releasedatum. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation april 2024 {#e-2024}

**Releasedatum**: 30 april 2024

### Ny funktion {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

<!--table>
<thead>
<tr>
<th><strong>Business rules - Private Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>It is now possible to create and apply rule sets to your marketing communications.  </p>
</td>
</tr>
</tbody>
</table-->

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
<p>Dessa beslutsobjekt integreras smidigt i ett stort antal inkommande ytor via den nya kodbaserade upplevelsekanalen, som nu är tillgänglig inom Journey Optimizer-kampanjer.</p>
<p>Experience Decision är för närvarande bara tillgängligt för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant för att få åtkomst.</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Personalization - Local Lookups - Multi-Entity Support - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>TBD</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Multimedia Message Service (MMS) med Infobip</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med SMS-kanalen kan du nu förbättra kommunikationen genom att skicka MMS-meddelanden (Multimedia Message Service) som gör det möjligt att dela bilder, GIF eller videor med dina kunder. Den här funktionen som tidigare bara fanns med i Sinch är nu även tillgänglig med Infobip.</p>
<img src="assets/do-not-localize/mms.gif"/>
</td>
</tr>
</tbody>
</table>

<!-- table>
<thead>
<tr>
<th><strong>AI Assistant - Experience Variant Generation - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Once you have created and personalized your message, take your content to the next level with the AI assistant. You can now use the AI assistant to optimize your message's impact by experimenting with different main titles, and images. Each variant is managed as a unique Treatment, to measure and compare which title effectively generates more clicks.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>IP Warmup Workflow - LA</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now easily perform IP warmup workflows directly from the Journey Optimizer interface in a standardized and efficient way that follows the best practices for optimal deliverability.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Email Surface Personalization - Private beta </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now define dynamic subdomains and personalized header parameters when creating email channel surfaces, for increased flexibility and control over your email settings.</p>
</td>
</tr>
</tbody>
</table-->

### Förbättringar {#e-improvements}

Den här versionen innehåller de förbättringar som anges nedan.

<!--
* **ExD reporting in AEP**: TBD
-->

**Publiker**

* Ni kan nu använda målgrupper och attribut från målgruppssammansättning med Sköld för hälso- och sjukvård och sköld för skydd och säkerhet.
* Du kan nu använda anpassad överföring (CSV-fil) med hälso- och sjukvårdsskölden och skölden för sekretess och säkerhet.

<!--
* **Experience Decisioning + Code-based experiences (LA)**: You can now leverage the Experience decisioning feature to use decision items in your code-based campaigns. Note: The Code-based experience channel and Experience decisioning are not available for organizations that have purchased the Adobe Healthcare Shield and Privacy and Security Shield add-on offerings.
-->
<!--
* **Expression Fragments supported for Web and In-App**: Expression fragments are now available for the Web and In-app channels. 
-->


<!--
* **DULE for AJO Channel Surface**: It is now possible to apply a label on certain profile attributes to restrict their usage inside a channel surface through marketing actions.
-->


<!--
* **List-Unsubscribe updates**: Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. 
-->

**Beslutsledning**

* The **Ändra logg** så att du kan se alla ändringar som har gjorts i ett erbjudande eller ett beslut har tagits bort. Ändringar som rör erbjudanden och beslut kan nu ses i **Granskningar** -menyn.

**Experience Decision**

Här är förbättringarna från beta till LA:

* Nu kan du utnyttja kontextdata från Adobe Experience Platform i dina beslutsregler med **Kontextdata** -fliken.
* Det finns nu en ny behörighet,&quot;Hantera Experience Decision&quot;, för beslutshanteringsresursen. Det gör att ni kan hantera rättigheter för Experience Decision.
* Nu kan du lägga till flera regler för begränsning av prenumerationer för ett erbjudande. På så sätt kan ni öka kontrollen över hur erbjudandena skickas.
* Nu kan du lägga till flera regler för att sätta stopp för ett visst beslutsobjekt i Experience Decisioning. På så sätt kan ni öka kontrollen över hur erbjudandena skickas.

**Resor**

* **Förbättrad resedesigner**:

   * Det förbättrade gränssnittet på arbetsytan ger en mer intuitiv och effektiv användarupplevelse.
   * Aktiviteterna blir tydligare och ger mer information om arbetsytan med färre klick.

* **Ny Live Reporting**: Rapporteringen av resor är nu tillgänglig via appen Live-rapporter. Det här är ett program som ger många insikter om körningen av resan.

**Konfiguration**

* Nu kan du välja en marknadsföringsåtgärd på kanalnivå. När de används på en yta används alla medgivandepolicyer som är kopplade till den marknadsföringsåtgärden för att ta hänsyn till kundernas önskemål.
* Åtkomstkontrollen på objektnivå är nu tillgänglig för kanalytor.

