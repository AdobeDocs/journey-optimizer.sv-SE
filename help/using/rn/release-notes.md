---
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: bc036fc52424adaf129ab379872dedfc5994c3bb
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 8%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target=&quot;_blank&quot;}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till inkorgen varje kvartal.

## Version från augusti 2022 {#aug-2022-release}

### Nya funktioner

<table>
<thead>
<tr>
<th><strong>Skapa och hantera kampanjer i Journey Optimizer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Använd Journey Optimizer kampanjer för att leverera engångsinnehåll till ett visst segment via olika kanaler. När du använder resor är åtgärderna utformade för att utföras i sekvens. Med kampanjer utförs åtgärder samtidigt, antingen omedelbart eller baserat på ett angivet schema. </p>
<img src="assets/do-not-localize/campaigns.gif"/>
<p>Lär dig hur du skapar en kampanj i <a href="../campaigns/get-started-with-campaigns.md">detaljerad dokumentation</a> och <a href="https://video.tv.adobe.com/v/345376">funktionsvideo</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Skicka SMS till användarna (allmän tillgänglighet)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skapa, anpassa och skicka SMS i Journey Optimizer via en integrering med <b>Sinch</b> eller <b>Twilio</b>.</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>Lär dig hur du skapar och skickar ett SMS i det här <a href="../messages/create-sms.md">detaljerad dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>New Dynamic Expression Builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create conditional content blocks across different authoring services to personalize your content.</p>
<p>In addition to the Personalization Expression Library, the Expression Editor provides a new Conditional Rule Builder to help you design and save your content blocks.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->



### Förbättringar

**Rapportering**

* Policytabell och diagram för samtycke finns nu tillgängliga i globala rapporter om resor. Med dessa widgetar kan du spåra de uteslutna profilerna från profilerna i dina anpassade åtgärder. [Läs mer](../reports/journey-global-report.md#journey-global)

   Observera att du måste återställa de olika rapportinstrumentpanelerna för att få tillgång till de senaste widgetarna. Mer information om anpassning av kontrollpanelen finns i [detaljerad dokumentation](../reports/global-report.md).

**Administrering**

* Det går nu att uppdatera det primära telefonnumret som ska användas för SMS-kanalen. [Läs mer](../configuration/primary-email-addresses.md)