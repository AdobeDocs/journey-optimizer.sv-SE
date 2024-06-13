---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Journey Optimizer tidiga versionsinformation
feature: Release Notes
hide: true
hidefromtoc: true
topic: Content Management
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 553743d6d041cd719eb3c8bf7f02288595d8c2a5
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# Tidiga versionsinformation {#e-release-notes}

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras i slutet av varje månad i [versionsinformation](release-notes.md).

**Tidiga versionsinformation nedan kan ändras utan föregående meddelande till dess att releasedatumet blir tillgängligt**. Länkar, skärmar och uppdaterad dokumentation publiceras i [versionsinformation](release-notes.md), på releasedatum.

## Versionsinformation juni 2024 {#e-2024}

**Releasedatum**: 18-19 juni 2024

### Nya funktioner {#e-features}

Den här versionen innehåller de nya funktionerna som beskrivs nedan.

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
<p>Mer information finns i den <a href="../configuration/ip-warmup-gs.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>


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
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
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


<!--table>
<thead>
<tr>
<th><strong>Reporting with Customer Journey Analytics (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer reporting is now fully integrated with Customer Journey Analytics capabilities, standardizing reporting across both platforms and improving data consistency and reliability. This seamless integration between Journey Optimizer and Customer Journey Analytics provides a clearer view of performance metrics, enabling users to make more informed decisions.</p>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>Multilingual messages in journeys and campaigns  (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now effortlessly create content in multiple languages within a single campaign or journey. With this feature, you can switch between languages when editing your campaign or your journey, streamlining the entire editing process and improving your capability to efficiently manage multilingual content.</p>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>Experimentation in journeys (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Already available in campaigns, Adobe Journey Optimizer now supports experiments in journeys. Experiments are randomized trials, which in the context of online testing, means that you expose some randomly selected users to a given variation of a message, and another randomly selected set of users to some other variation or treatment. After exposure, you can then measure the outcome metrics you are interested in, such as opens of emails, subscriptions, or purchases.</p>
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


**Beslutshantering**

* **Stöd för flera regler i beslutshantering** - Du kan nu lägga till upp till 10 regler om begränsning av ett visst erbjudande i Beslutshantering. På så sätt kan ni öka kontrollen över hur erbjudandena skickas. [Läs mer](../offers/offer-library/add-constraints.md#capping)

<!--* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->

**Content Fragments**

* Fragment kan nu redigeras och ändringar kan spridas över alla liveresor och -kampanjer där de används.
* Nya statusar för innehållsfragment har införts: **Utkast**, **Live**, **Publicering** och **Arkiverad**.
* Om du vill använda ett fragment i en resa eller kampanj måste det nu finnas i **Live** status. Ett nytt steg har lagts till i processen för att skapa fragment, vilket gör att fragmentet kan publiceras och göras tillgängligt för användning under resor och kampanjer. Observera att fragmentpublicering kräver en ny behörighet.

  **FÖRSIKTIGHET** - sedan **Utkast** och **Live** statusar har introducerats i Journey Optimizer Juniversion, där alla fragment som skapats före den här versionen har **Utkast** status, även om de används i en resa eller kampanj. Lär dig hur du uppdaterar befintliga fragment i det här avsnittet.

**Resor**

* Den globala tidsgränsen för resan har ökat från 30 till 91 dagar.
* Adobe Journey Optimizer har nu stöd för begäranden om borttagning/åtkomst av sekretess.
* Du kan nu ändra storlek på kolumnerna i kundresans lager.
* **Avancerad uttrycksredigerare i händelsekonfigurationen** är nu GA - Du kan nu använda den avancerade uttrycksredigeraren när du konfigurerar en händelse, så att du kan definiera mer komplexa uttryck eller använda funktioner i händelse-id-villkoret. Den här funktionen lanseras i begränsad tillgänglighet för utvalda kunder. [Läs mer](../event/about-creating.md)
* **Sammanfoga profiler** är nu GA - de sammanslagningsprinciper som används av en resa är nu synliga och konsekventa under hela resan. Den här funktionen lanseras i begränsad tillgänglighet för utvalda kunder. [Läs mer](../building-journeys/journey-gs.md#merge-policies)



**Kampanjer**

* När du skapar en kampanj i Adobe Journey Optimizer kan du nu välja kampanjtyp (schemalagd eller utlöst) i en ny modal.

**E-postkanal**

* **List-unsubscribe** - Efter de senaste Gmail- och Yahoo-meddelandena om bulkavsändare stöder Journey Optimizer alternativet&quot;post/1-click&quot; List-Unsubscribe. <!--Refer to the following pages: [Email opt-out management](../email/email-opt-out.md#unsubscribe-header) and [Configure email settings](../email/email-settings.md#list-unsubscribe)-->


**SMS-kanal**

* Nu kan du lägga till unika korta koder för varje sandlåda med en enda API-konfiguration, vilket gör processen effektivare och smidigare.
  <!--* You can now modify existing SMS configurations.-->

**Kanal i appen**

* **Uttrycksfragment** - Uttrycksfragment är nu tillgängliga för **Kanal i appen**. [Läs mer](../personalization/use-expression-fragments.md)


* Du kan nu använda Edge Delivery-pluginen för att få den information som behövs för att förstå och felsöka dina inkommande implementeringar.


