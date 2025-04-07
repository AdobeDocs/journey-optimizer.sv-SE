---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med datahantering i Journey Optimizer
description: Lär dig arbeta med data i Journey Optimizer
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: data, hantering, plattform
exl-id: 25519acb-a017-446a-992b-653d3a8a3d96
source-git-commit: 47185cdcfb243d7cb3becd861fec87abcef1f929
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---

# Kom igång med datahantering {#about-data}

Riktighet och täckning av slutkundsdata är vad som definierar styrkan och framgången hos alla kundupplevelselösningar, och dessa data är skalbara och av högsta värde för varje enskild kund. Teknikval är nu inbyggt i en strikt utvärdering av datahanteringsfunktioner.

Med [!DNL Adobe Journey Optimizer] kan du enkelt hantera, behålla och exportera dessa data till plattformar eller system som ingår i din teknikstack.

**Mina data, Mina regler** - [!DNL Adobe Journey Optimizer] skapar kontinuerligt (och i realtid) en omfattande uppsättning kundprofildata, utöver alla kundresedata och erbjuder data som är inbyggda i dess åtgärder. Med smidiga versioner av användardata som hämtas från era databaser kan ni berika och omvandla dem till värdefulla data med täckning och djup. Ni vill att dessa data ska vara säkra, och samtidigt vara universella, så att ni kan utnyttja deras värde i hela IT-ekosystemet.

Den flexibilitet du vill ha från dina data är dessutom:


<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <div><img alt="mål" src="assets/do-not-localize/dest.png" /> 
    <br> Finns för andra ändamål - Även om [!DNL Adobe Journey Optimizer] kan göra data mer tilltalande och integrerade för en hyperpersonaliserad kundupplevelse, vill du ha dessa data i andra system i det övergripande tekniska landskapet, samtidigt som du letar efter andra sätt att utnyttja dessa data.
    <div>
     <a href="../integrations/ajo-integrations.md">Läs mer</a></div>
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
    <br> Borttagen grund, en överenskommen tidslinje eller din policy - Dataradering är en viktig del av dataskyddet och är ett viktigt steg i alla datastyrningsprocesser. [!DNL Adobe Journey Optimizer] kan producera mer data än vad som krävs. Dessutom vill ni ta största möjliga hand om vad som händer efter att en datamängd har fått den varaktighet som krävs - oavsett om det beror på verktyg eller reglering. Den kontroll du behöver är att ta bort data vid en given tidpunkt. 
    </div>
      <div>
     <a href="../privacy/data-hygiene.md">Läs mer</a></div>
    </div>
  </td>
</tr>
</table>

[!DNL Adobe Experience Platform], som [!DNL Adobe Journey Optimizer] byggs på, ger dig störst kontroll över data - både under engagemanget och i slutet av engagemanget. Inom [!DNL Journey Optimizer] har du fullständig kontroll över data (som hämtas till eller skapas av [!DNL Journey Optimizer]), den styrning som överlagras för dessa data och de destinationer dit dessa data skickas.

Alla data betraktas som kundens egendom och kan bara underhållas, krypteras, distribueras eller förstöras på din begäran. Adobe fungerar som förvaltare, utan några som helst rättigheter till era data.

Du kan använda flexibiliteten för data i [!DNL Journey Optimizer] för att uppfylla dina specifika krav för datalagring, arkivering eller borttagning:

* **Dataextrahering/export**: Du kan initiera extraheringen av källdata när som helst via API:t för dataåtkomst utan straffar eller tidsfördröjningar. [API:t för dataåtkomst](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html){target="_blank"} ger användarna ett RESTful-gränssnitt som fokuserar på identifierbarhet och tillgänglighet för kapslade datauppsättningar i [!DNL Adobe Experience Platform]. <!--In the future (on roadmap), you can use file-based destinations to export and migrate log data from Adobe Journey Optimizer. -->

  Observera att innehåll som används i resor eller kampanjer inte kan extraheras via API- eller målmetoder som nämns ovan.

<!--
* **Profile Service Data Retention**: For Behavioral and Time series data appended to any Profile, you may choose to use Journey Optimizer's default setting of retaining this data for up to 91 days from the date of its addition to a Profile, or until an alternative time-period selected by the you. The time that Adobe keeps this data varies from contract to contract, and is outlined in an organization's data retention policy.

  Learn more about Experience Event expirations in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/profile/event-expirations.html){target="_blank"}.
-->

* **Töm- och arkiveringsmekanismer**: Tömning av data och arkivering kan definieras fritt och automatiseras i [!DNL Adobe Journey Optimizer] för att automatisera datalagringsprinciper. Det är möjligt att definiera olika strategier för åldersfördelning för olika datatabeller. Exportmekanismer kan också definieras för att automatiskt exportera åldersfördelningsdata innan de rensas eller arkiveras.

  Med arbetsytan Datalängd kan du skapa och övervaka olika uppgifter under datalängd, till exempel ta bort konsumentidentiteter och schemalägga förfallodatum för datauppsättningar. Den här arbetsytan är tillgänglig med skölden för skydd och integritet och med hälso- och sjukvårdsskölden. Läs mer på [den här sidan](../privacy/data-hygiene.md).

<!--
* **Data Lake and Deletions**: Customer Data stored in the Data Lake can be retained by Journey Optimizer:
    
    * for 7 days to facilitate the onboarding of Customer Data into the Profile Services, after which it may be permanently deleted, or
    * until chosen to be deleted by you

-->

* **Dataextrahering vid avtalsslut/ avslut**: När kontraktet avslutas tas dina data bort helt från Adobe lagringsutrymme. Du kan även hämta fullständiga profilextraheringar innan du säger upp ett avtal. Det kostar inget mer. Detta kan göras när som helst och inte bara när det sägs upp.

Ovannämnda metoder är avtalsenligt definierade och detaljerade i det databehandlingsavtal (DPA) som Adobe kommer överens med er i början av ett ärende. Adobe-program, inklusive [!DNL Journey Optimizer], är uppbyggda kring principen att varje kunds data behandlas som den klientens egna datatillgångar.
