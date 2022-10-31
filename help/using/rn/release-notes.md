---
solution: Journey Optimizer
product: journey optimizer
title: Versionsinformation
description: Versionsinformation om Journey Optimizer
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 3a932747de33ced59d68835a96386b7ac560e4fe
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 10%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i [!DNL Journey Optimizer]. Du kan även läsa [senaste dokumentationsuppdateringar](documentation-updates.md) sida för fler ändringar.

[!DNL Adobe Journey Optimizer] är inbyggd i [!DNL Adobe Experience Platform] och ärver av sina senaste innovationer och förbättringar. Läs mer om de här ändringarna i [Versionsinformation för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html){target=&quot;_blank&quot;}.

![Nyhetsbrev](../assets/do-not-localize/nl-icon.png) Registrera dig för [Adobe Journey Optimizer kvartalsvis nyhetsbrev](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;} idag och få de senaste produktuppdateringarna, spännande historier, användningsexempel, tips och mycket annat levererat direkt till inkorgen varje kvartal.


## Oktober 2022-versionen {#oct-2022-release}

<!--

### New capability{#oct-2022-features}

<table>
<thead>
<tr>
<th><strong>Direct Mail Channel (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add direct mail messages in your campaigns and journeys. Direct mail is an offline channel that allows you to personalize and generate the files required by direct mail providers to send mail to your customers.</p>
<p>When you prepare a direct mail delivery, Journey Optimizer generates a file including all the targeted profiles and the chosen contact information (postal address for example). You will then be able to send this file to your direct mail provider who will take care of the actual sending.</p>
</td>
</tr>
</tbody>
</table>

-->

### Förbättringar {#oct-2022-improvements}

**Resor**

* The **Tvinga återinträde vid upprepning** har lagts till i återkommande parametrar för lässegmentschema. Med det här alternativet kan du göra så att alla profiler som fortfarande finns i resan automatiskt avslutar den vid nästa körning. När alternativet är inaktiverat måste profilerna slutföra resan innan de kan återkomma i en annan förekomst. [Läs mer](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**Administrering**

* Ett meddelande lades till i användargränssnittet för att varna för att underdomäner, underdomäner för landningssidor, PTR-poster och IP-poolkonfigurationer är gemensamma för alla sandlådor och därför kommer ändringar i någon av dessa konfigurationer även att påverka produktionssandlådorna.
* Stegen för att överföra undertryckningslistan som en CSV-fil från användargränssnittet har ändrats. [Läs mer](../configuration/manage-suppression-list.md#download-suppression-list)

**Kampanjer**

* Nu kan ni arkivera slutförda och stoppade kampanjer. [Läs mer](../campaigns/modify-stop-campaign.md#archive)
