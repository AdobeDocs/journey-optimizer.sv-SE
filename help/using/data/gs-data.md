---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med data i Journey Optimizer
description: Lär dig arbeta med data i Journey Optimizer
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: data, hantering, plattform
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: ef34cb0207d3011eca6d76ad6568f3edc00e13a3
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# Kom igång med datahantering i [!DNL Journey Optimizer] {#about-data}

Riktighet och täckning av slutkundsdata är vad som definierar styrkan och framgången hos alla kundupplevelselösningar, och dessa data är skalbara och av högsta värde för varje enskild kund. Teknikval är nu inbyggt i en strikt utvärdering av datahanteringsfunktioner.

Med [!DNL Adobe Journey Optimizer]kan ni enkelt hantera, behålla och exportera dessa data till plattformar eller system som ingår i er teknologi.

**Mina data, Mina regler** - [!DNL Adobe Journey Optimizer] kontinuerligt (och i realtid) skapar en omfattande uppsättning kundprofildata utöver alla kunddata och erbjuder data som är inbyggda i dess verksamhet. Med smidiga versioner av användardata som hämtas från era databaser kan ni berika och omvandla dem till värdefulla data med täckning och djup. Ni vill att dessa data ska vara säkra, och samtidigt vara universella, så att ni kan utnyttja deras värde i hela IT-ekosystemet.

Den flexibilitet du vill ha från dina data är dessutom:


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="mål" src="assets/do-not-localize/dest.png" /> 
    <br>Finns på andra platser - men [!DNL Adobe Journey Optimizer] skapar synergier och integrerar data för en hyper-personaliserad kundupplevelse och vill ha dessa data i andra system i det övergripande tekniklandskapet, samtidigt som ni letar efter andra sätt att utnyttja dessa data.
    <div>
     <a href="../start/ajo-integrations.md">Läs mer</a></div>
    </div>
    <br>
  </td>
</tr>
</table>

<!--td>
    <div><img alt="retention" src="assets/do-not-localize/retention.png" />  
    <br>Retained for a stipulated duration – Industry or regional regulations (such as GDPR or CCPA) or internal data governance policies stipulate how long or how short a duration, data needs to be maintained or archived in Adobe Experience Platform Data Lake. <a href="../privacy/get-started-privacy.md">Learn more</a></div>
  </td>
</tr>
<tr style="border: 0;"-->
<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="policy" src="assets/do-not-localize/policy.png" /> 
    <br>Borttagen bas - en överenskommen tidslinje eller er policy - Dataradering är en viktig del av dataskyddet och är ett viktigt steg i alla processer för datastyrning. [!DNL Adobe Journey Optimizer] kan producera mer data än vad som krävs. Dessutom vill ni ta största möjliga hand om vad som händer efter att en datamängd har fått den varaktighet som krävs - oavsett om det beror på verktyg eller reglering. Den kontroll du behöver är att ta bort data vid en given tidpunkt. 
    </div>
      <div>
     <a href="../privacy/data-hygiene.md">Läs mer</a></div>
    </div>
  </td>
</tr>
</table>

[!DNL Adobe Experience Platform], som [!DNL Adobe Journey Optimizer] är skapat och ger er högsta möjliga kontroll över data - både under engagemanget och i slutet av engagemanget. Inom [!DNL Journey Optimizer]har du fullständig kontroll över data (som antingen hämtas in eller skapas av, [!DNL Journey Optimizer]), styrningen av dessa data och de destinationer dit dessa data skickas.

Alla data betraktas som kundens egendom och kan bara underhållas, krypteras, distribueras eller förstöras på din begäran. Adobe fungerar som förvaltare, utan några som helst rättigheter till era uppgifter.

Du kan använda [!DNL Journey Optimizer]Med sin flexibilitet att hantera dina specifika krav vad gäller datalagring, arkivering eller radering:

* **Extrahering/export av data**: Du kan initiera extraheringen av källdata när som helst via API:t för dataåtkomst utan straffar eller tidsfördröjningar. The [API för dataåtkomst](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html){target="_blank"} ger användarna ett RESTful-gränssnitt som fokuserar på att upptäcka om inkapslade datauppsättningar är tillgängliga eller inte [!DNL Adobe Experience Platform]. <!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

  Observera att innehåll som används i resor eller kampanjer inte kan extraheras via API- eller målmetoder som nämns ovan.

<!--
* **Profile Service Data Retention**: For Behavioral and Time series data appended to any Profile, you may choose to use Journey Optimizer’s default setting of retaining this data for up to 30 days from the date of its addition to a Profile, or until an alternative time-period selected by the you. The time that Adobe keeps this data varies from contract to contract, and is outlined in an organization’s data retention policy.

  Learn more about Experience Event expirations in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html){target="_blank"}.
-->

* **Rensa och arkivera**: Rensning av data och arkivering kan definieras fritt och automatiseras i [!DNL Adobe Journey Optimizer] att automatisera datalagringspolicyer. Det är möjligt att definiera olika strategier för åldersfördelning för olika datatabeller. Exportmekanismer kan också definieras för att automatiskt exportera åldersfördelningsdata innan de rensas eller arkiveras.

  Med arbetsytan Datahygien kan du skapa och övervaka olika datahygien-uppgifter, som att ta bort konsumentidentiteter och schemalägga förfallodatum för datauppsättningar. Den här arbetsytan är tillgänglig med skölden för skydd och integritet och med hälso- och sjukvårdsskölden. Läs mer i [den här sidan](../privacy/data-hygiene.md).

<!--
* **Data Lake and Deletions**: Customer Data stored in the Data Lake can be retained by Journey Optimizer:
    
    * for 7 days to facilitate the onboarding of Customer Data into the Profile Services, after which it may be permanently deleted, or
    * until chosen to be deleted by you

-->

* **Dataextrahering vid avslutning/avslutning av engagemang**: När kontraktet avslutas tas data bort helt från Adobe lagringsutrymme. Du kan även hämta fullständiga profilextraheringar innan du säger upp ett avtal. Det kostar inget mer. Detta kan göras när som helst och inte bara när det sägs upp.

Ovannämnda metoder är avtalsenligt definierade och detaljerade i det databehandlingsavtal (DPA) som Adobe ömsesidigt instämmer med dig i början av ett ärende. Adobe-program, inklusive [!DNL Journey Optimizer], bygger på principen att varje kunds data behandlas som den kundens egna datatillgångar.
