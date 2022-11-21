---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med data i [!DNL Journey Optimizer]
description: Lär dig arbeta med data i [!DNL Journey Optimizer]
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: 2dcfcc8d7006c92e046152db5ac1288bdde8b063
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 0%

---

# Kom igång med datahantering i [!DNL Journey Optimizer] {#about-data}

Omfattningen av slutkundsdata och hur omfattande de är definierar styrkan och framgången för alla kundupplevelselösningar. och dessa data är skalbara och av högsta värde för en viss kund. Teknikval är nu inbyggt i en strikt utvärdering av datahanteringsfunktioner.

Med Adobe Journey Optimizer kan ni enkelt hantera, behålla och exportera dessa data till plattformar eller system som ingår i er teknologi.

**Mina data, Mina regler** - Journey Optimizer skapar kontinuerligt (och i realtid) en omfattande uppsättning kundprofildata, utöver alla kunddata och erbjuder data som är inbyggda i dess verksamhet. Med smidiga versioner av användardata som hämtas från era databaser kan ni berika och omvandla dem till värdefulla data med täckning och djup. Ni vill att dessa data ska vara säkra, och samtidigt vara universella, så att ni kan utnyttja deras värde i hela IT-ekosystemet.

Den flexibilitet du vill ha från dina data är dessutom tre gånger så stor:


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="mål" src="assets/do-not-localize/dest.png" /> 
    <br>Finns för andra destinationer - Journey Optimizer ger möjlighet till samverkan och integrering av data för en hyperpersonaliserad kundupplevelse, men ni vill ha dessa data i andra system i er övergripande teknikmiljö, samtidigt som ni letar efter andra sätt att utnyttja dessa data.
    <div>
     <a href="../start/ajo-integrations.md">Läs mer</a></div>
    </div>
    <br>
  </td>
</tr>
  <td>
    <div><img alt="kvarhållande" src="assets/do-not-localize/retention.png" />  
    <br>Bevaras under en viss tid - Branschregler eller regionala regler (t.ex. GDPR eller CCPA) eller interna regler för datastyrning anger hur lång eller kort tid som data måste underhållas eller arkiveras i Adobe Experience Platform Data Lake. <a href="../privacy/get-started-privacy.md">Läs mer</a></div>
  </td>
</tr>
<tr style="border: 0;">
  <td>
    <div><img alt="policy" src="assets/do-not-localize/policy.png" /> 
    <br>Borttagen bas - en överenskommen tidslinje eller er policy - Dataradering är en viktig del av dataskyddet och är ett viktigt steg i alla processer för datastyrning. Journey Optimizer kan producera mer data än vad som krävs. Dessutom vill ni ta största möjliga hand om vad som händer efter att en datamängd har fått den varaktighet som krävs - oavsett om det beror på verktyg eller reglering. Den kontroll du behöver är att ta bort data vid en given tidpunkt. <a href="https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html">Läs mer om datahygien i Adobe Experience Platform-dokumentationen</a></div>
  </td>
</tr>
</table>

Adobe Experience Platform, som Journey Optimizer är byggt på, ger dig störst kontroll över data - både under engagemanget och i slutet av engagemanget. Inom Journey Optimizer har ni fullständig kontroll över data (som hämtas in eller skapas av Journey Optimizer), den styrning som gäller för dessa data och de destinationer dit dessa data skickas.

Alla data betraktas som kundens egendom och kan bara underhållas, krypteras, distribueras eller förstöras på din begäran. Adobe fungerar som förvaltare, utan några som helst rättigheter till era uppgifter.

Du kan använda Journey Optimizer flexibilitet för att uppfylla dina specifika krav när det gäller datalagring, arkivering eller radering:

* **Extrahering/export av data**: Du kan initiera extraheringen av källdata när som helst via API:t för dataåtkomst utan straffavgifter eller tidsfördröjningar. The [API för dataåtkomst](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html){target=&quot;_blank&quot;} förser användarna med ett RESTful-gränssnitt som fokuserar på identifierbarhet och tillgänglighet för kapslade datauppsättningar i Experience Platform. <!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

   Observera att innehåll som används i resor eller kampanjer inte kan extraheras via API- eller målmetoder som nämns ovan.

* **Profiltjänstens datalagring**: För data från Beteende- och Tidsserier som bifogas till en profil kan du välja att använda Journey Optimizer standardinställning för att behålla dessa data i upp till 30 dagar från det datum då de lades till i en profil, eller tills du väljer en annan tidsperiod. Den tid som Adobe lagrar dessa data varierar från kontrakt till kontrakt och beskrivs i en organisations policy för datalagring.

   Läs mer om förfallodatum för Experience Event i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html){target=&quot;_blank&quot;}.

* **Rensa och arkivera**: Rensning av data och arkivering kan definieras fritt och automatiseras i Journey Optimizer för att automatisera datalagringspolicyer. Det är möjligt att definiera olika strategier för åldersfördelning för olika datatabeller. Exportmekanismer kan också definieras för att automatiskt exportera åldersfördelningsdata innan de rensas eller arkiveras.

   Med arbetsytan Datahygien i Adobe Experience Platform-gränssnittet kan du skapa och övervaka olika datahygien, bland annat ta bort konsumentidentiteter och schemalägga förfallodatum för datauppsättningar. Den här arbetsytan är tillgänglig med skölden för skydd och integritet och med hälso- och sjukvårdsskölden. Läs mer i [Adobe Experience Platform-dokumentation](https://experienceleague.adobe.com/docs/experience-platform/hygiene/ui/overview.html){target=&quot;_blank&quot;}.

* **Data Lake och Deletions**: Kunddata som lagras i Data Lake kan lagras av Journey Optimizer:

   * under 7 dagar för att underlätta införandet av kunddata i profiltjänsterna, varefter dessa kan raderas permanent, eller
   * tills du valt att ta bort


* **Dataextrahering vid avslutning/avslutning av engagemang**: När kontraktet har avslutats tas alla data bort från Adobe lagringsutrymme. Du kan även hämta fullständiga profilextraheringar innan du säger upp ett avtal. Det kostar inget mer. Detta kan göras när som helst och inte bara när det sägs upp.

Ovannämnda metoder är avtalsenligt definierade och detaljerade i det databehandlingsavtal (DPA) som Adobe ömsesidigt instämmer med dig i början av ett ärende. Adobe-applikationer, inklusive Journey Optimizer, bygger på principen att varje kunds data behandlas som kundens egna datatillgångar.
