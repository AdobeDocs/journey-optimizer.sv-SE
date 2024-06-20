---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
feature: Release Notes
topic: Content Management
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: fec6b15db9f8e6b2a07b55bc9e8fc4d9cb0d73d7
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 6%

---

# Versionsinformation {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="Nyheter?"
>abstract="**Adobe Journey Optimizer** levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen."

[!DNL Adobe Journey Optimizer] levererar kontinuerligt nya funktioner, förbättringar av befintliga funktioner och felkorrigeringar. Alla ändringar konsolideras den sista veckan i varje månad i versionsinformationen.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target="_blank"}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till din inkorg varje kvartal.


## Versionsinformation juni 2024 {#24-6-2024}

**Tidiga versionsinformation nedan kan ändras utan föregående meddelande till dess att releasedatumet blir tillgängligt**.

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


<!--<table>
<thead>
<tr>
<th><strong>Content Fragments customization</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now define specific fields in a fragment that can be edited when the fragment is added to a campaign or journey. This allows for the adjustment of content portions at the time of use, providing flexibility to override default values with context-specific details.</p>
<p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->




<table>
<thead>
<tr>
<th><strong>Rapportering med Customer Journey Analytics (beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer rapportering är nu helt integrerad med Customer Journey Analytics-funktioner, vilket standardiserar rapporteringen på båda plattformarna och förbättrar datakonsekvensen och tillförlitligheten. Denna smidiga integrering mellan Journey Optimizer och Customer Journey Analytics ger en tydligare bild av prestandamätningarna, så att användarna kan fatta mer välgrundade beslut.</p>
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

<!--table>
<thead>
<tr>
<th><strong>Multilingual messages in journeys and campaigns (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now effortlessly create content in multiple languages within a single campaign or journey. With this feature, you can switch between languages when editing your campaign or your journey, streamlining the entire editing process and improving your capability to efficiently manage multilingual content.</p>
<p>Multilingual content is currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
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
<p>Experimentation in journeys is currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
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

### Förbättringar {#june24-improvements}

Den här versionen innehåller de förbättringar som anges nedan.


**Beslutshantering**

* **Stöd för flera regler i beslutshantering** - Du kan nu lägga till upp till 10 regler om begränsning av ett visst erbjudande i Beslutshantering. På så sätt kan ni öka kontrollen över hur erbjudandena skickas. [Läs mer](../offers/offer-library/add-constraints.md#capping)

<!--* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->

**Content Fragments**

>[!AVAILABILITY]
>
>Observera att dessa förbättringar kommer att introduceras gradvis under flera dagar efter den första versionen. Vissa användare har omedelbar åtkomst, men andra kan uppleva en fördröjning innan den blir tillgänglig i deras miljöer.

* Fragment kan nu redigeras och ändringar kan spridas över alla liveresor och -kampanjer där de används.
* Nya statusar för innehållsfragment har införts: **Utkast**, **Live**, **Publicering** och **Arkiverad**.
* Om du vill använda ett fragment i en resa eller kampanj måste det nu finnas i **Live** status. Ett nytt steg har lagts till i processen för att skapa fragment, vilket gör att fragmentet kan publiceras och göras tillgängligt för användning under resor och kampanjer. Observera att fragmentpublicering kräver en ny behörighet.

  **FÖRSIKTIGHET** - sedan **Utkast** och **Live** statusar har introducerats i Journey Optimizer Juniversion, där alla fragment som skapats före den här versionen har **Utkast** status, även om de används i en resa eller kampanj. Lär dig hur du uppdaterar befintliga fragment i det här avsnittet.

Läs mer i [innehållsfragment](../content-management/fragments.md) dokumentation.

**Resor**

* Den globala tidsgränsen för resor har utökats till 91 dagar. [Läs mer](../building-journeys/journey-properties.md#global_timeout)

  Alla nya resor som skapas kommer att få den här nya tidsgränsen angiven. Se det här [Frågor och svar](../building-journeys/journey-properties.md#timeout-faq) om du vill veta mer. Observera att dessa ändringar kommer att införas gradvis under juni månad.


* Adobe Journey Optimizer har nu stöd för förfrågningar om borttagning/åtkomst av sekretess samt livscykelhantering av data. [Läs mer](../privacy/requests.md)
* Du kan nu ändra storlek på kolumnerna i kundresans lager.
  <!--* **Advanced expression editor in Event configuration** is now GA - You can now leverage the advanced expression editor while configuring an event, allowing you to define more complex expressions or use functions in the event id condition. This capability is released in Limited Availability for selected customers. [Read more](../event/about-creating.md)-->
* **Sammanfoga profiler** är nu GA - de sammanslagningsprinciper som används av en resa är nu synliga och konsekventa under hela resan. [Läs mer](../building-journeys/journey-properties.md#merge-policies)



**Kampanjer**

* När du skapar en kampanj i Adobe Journey Optimizer kan du nu välja kampanjtyp (schemalagd eller utlöst) i en ny modal. [Läs mer](../campaigns/create-campaign.md)

<!--**Email channel**

* **List-unsubscribe** - Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. Refer to the following pages: [Email opt-out management](../email/email-opt-out.md#unsubscribe-header) and [Configure email settings](../email/email-settings.md#list-unsubscribe)-->


**SMS-kanal**

* Nu kan du lägga till unika korta koder för varje sandlåda med en enda API-konfiguration, vilket gör processen effektivare och smidigare. [Läs mer](../sms/sms-configuration.md)

* När du har skapat **API-token** fält på **API-autentiseringsuppgifter** sidan är nu maskerad.

<!--* You can now modify existing SMS configurations.-->

**Kanal i appen**

<!--* **Expression fragment** - Expression fragments are now available for the **In-app channel**. [Read more](../personalization/use-expression-fragments.md)-->

* Du kan nu använda Edge Delivery-pluginen för att få den information som behövs för att förstå och felsöka dina inkommande implementeringar. [Läs mer om Edge Delivery View](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}.


**Direktpostkanal**

* Direktreklamkanalen är nu tillgänglig för organisationer som köpt Adobe **Hälsovårdssköld** och **Sköld för skydd av privatlivet och säkerheten** tilläggserbjudanden.
