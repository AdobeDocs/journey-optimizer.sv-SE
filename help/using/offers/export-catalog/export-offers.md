---
title: Datauppsättning med personaliserade erbjudanden
description: I det här avsnittet visas alla fält som används i den exporterade datauppsättningen för erbjudanden
badge: label="Äldre" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: c7f691aa-8f89-4f23-b897-53211863eb6d
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '1945'
ht-degree: 0%

---

# Datauppsättning med personaliserade erbjudanden {#offers-dataset}

Varje gång ett erbjudande ändras uppdateras den autogenererade datauppsättningen för personaliserade erbjudanden.

Den senaste lyckade batchen i datauppsättningen visas till höger. Den hierarkiska vyn av schemat för datauppsättningen visas i den vänstra rutan.

![](../assets/dataset-offers.png)

>[!NOTE]
>
>Borttagna personliga erbjudanden markeras som arkiverade i datauppsättningen.

Här är en lista över alla fält som kan användas i datamängden **[!UICONTROL Decision Object Repository - Personalized Offers]**.

<!--Personalized offers form the set of choices for a decision. The objective for decisioning is to take a large inventory of items and apply numerous constraint rules to that inventory to narrow it down and then to rank the qualifying options according to a criteria. The resulting propositions assemble and personalize the experience for specific individuals.-->

+++ Identifierare

**Fält:**_id
**Titel:** Identifierare
**Beskrivning:** En unik identifierare för posten.
**Typ:** sträng

+++

+++ _upplevelse {#experience}

**Fält:**_upplevelse
**Typ:** objekt

+++

+++ _experience > decisioning

**Fält:** beslut
**Typ:** objekt

+++

+++ _experience > decisioning > calendarConstraints 

**Fält:** calendarConstraints
**Titel:** Information om kalenderbegränsningar
**Beskrivning:** Kalenderbegränsningar avgör om ett beslutsalternativ är giltigt utifrån ett datumintervall. Förutom detta datumintervall kan alternativet inte föreslås.
**Typ:** objekt

* **Slutdatum och sluttid**

  **Fält:** endDate
  **Titel:** Slutdatum och sluttid
  **Beskrivning:** Slutdatumet för ett beslutsalternativs giltighet. Alternativ som har passerat slutdatumet kan inte längre föreslås i beslutsprocessen.
  **Typ:** sträng

* **Startdatum och -tid**

  **Fält:** startDate
  **Titel:** Startdatum och -tid
  **Beskrivning:** Startdatumet för ett beslutsalternativs giltighet. Alternativ som inte har nått sitt startdatum kan inte föreslås än i beslutsprocessen.
  **Typ:** sträng

+++

+++ _experience > decisioning > properties

**Fält:** - egenskaper
**Titel:** Beslutsalternativsegenskaper
**Beskrivning:** Ytterligare egenskaper eller attribut som tillhör det här beslutsalternativet. Olika instanser kan ha olika egenskaper (tangenter på kartan). Egenskaperna är namnvärdespar som används för att skilja mellan olika beslutsalternativ. Egenskaper används som värden i innehåll som representerar det här alternativet och som funktioner för att analysera och optimera prestanda för ett alternativ. När alla instanser har samma attribut eller egenskap bör den aspekten modelleras som ett tilläggsschema som härleds från beslutsalternativsinformationen.
**Typ:** objekt

+++

+++ _experience > decisioning > contents

**Fält:** innehåll
**Titel:** Innehållsinformation
**Beskrivning:** Innehållsobjekt som återger beslutsobjektet i olika sammanhang. Ett enda beslutsalternativ kan ha flera innehållsvarianter. Innehåll är information som riktar sig till en målgrupp som konsumeras i en (digital) upplevelse. Innehållet levereras via kanaler till en viss plats.
**Typ:**-matris

+++

+++_experience > decisioning > contents > components

**Fält:** komponenter
**Beskrivning:** Komponenterna i innehållet som representerar beslutsalternativet, inklusive alla deras språkvarianter. Specifika komponenter hittades av dx:format, dc:subject och dc:language eller en kombination av dessa. Dessa metadata används för att hitta eller representera innehållet som är kopplat till ett erbjudande och integrera det enligt placeringskontraktet.
**Typ:**-matris
**Obligatoriskt:** &quot;_type&quot;, &quot;_dc&quot; <!--TBC?-->

* **_experience > decisioning > contents > components > Content Component Type**

  **Fält:**_typ
  **Titel:** Innehållskomponenttyp
  **Beskrivning:** En uppräknad uppsättning URI:er där varje värde mappas till en typ som anges för innehållskomponenten. En del användare av innehållsrepresentationerna förväntar sig att värdet @type ska vara en referens till schemat som beskriver ytterligare egenskaper för innehållskomponenten.
  **Typ:** sträng

* **_experience > Decision > contents > components > _dc**

  **Fält:**_dc
  **Typ:** objekt
  **Obligatoriskt:** &quot;format&quot;

   * **Format**

     **Fält:**-format
     **Titel:** Format
     **Beskrivning:** Resursens fysiska eller digitala manifestation. Vanligtvis ska Format innehålla resursens medietyp. Format kan användas för att fastställa programvara, maskinvara eller annan utrustning som behövs för att visa eller använda resursen. Rekommenderad bästa praxis är att välja ett värde från en kontrollerad vokabulär (till exempel listan med [Internetmedietyper](https://www.iana.org/assignments/media-types/) som definierar datormediaformat).
     **Typ:** sträng
     **Exempel:** &quot;application/vnd.adobe.photoshop&quot;

   * **Språk**
     **Fält:** språk
     **Titel:** Språk
     **Beskrivning:** Resursens språk. \nSpråk anges i språkkoden enligt definitionen i [IETF RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) som är en del av BCP 47, som används någon annanstans i XDM.
     **Typ:**-matris
     **Exempel:** &quot;\n&quot;, &quot;pt-BR&quot;, &quot;es-ES&quot;

* **_experience > Decision > contents > components > _repo**

  **Fält:**_repo
  **Typ:** objekt

   * **id**

     **Fält:** id
     **Beskrivning:** En valfri unik identifierare som refererar till resursen i en innehållsdatabas. När plattforms-API:er används för att hämta representationen kan klienten förvänta sig att ytterligare egenskapen \&quot;repo:resolveUrl\&quot; hämtar resursen.
     **Typ:** sträng
     **Exempel:** &quot;urn:aaid:sc:US:6dc33479-13ca-4b19-b25d-c805eff8a69e&quot;

   * **namn**

     **Fält:** namn
     **Beskrivning:** Tips om var du hittar databasen som lagrar den externa resursen med \&quot;repo:id\&quot;.
     **Typ:** sträng

   * **databaseID**

     **Fält:** databaseID
     **Beskrivning:** En valfri unik identifierare som refererar till resursen i en innehållsdatabas. När plattforms-API:er används för att hämta representationen kan klienten förvänta sig att ytterligare egenskapen \&quot;repo:resolveUrl\&quot; hämtar resursen.
     **Typ:** sträng
     **Exempel:** &quot;C87932A55B06F7070A49412D@AdobeOrg&quot;

   * **resolveURL**

     **Fält:** resolveURL
     **Beskrivning:** En unik resurslokaliserare (valfritt) som kan läsa resursen i en innehållsdatabas. Detta gör det enklare att hämta resursen utan att kunden förstår var resursen hanteras och vilka API:er som ska anropas. Detta liknar en HAL-länk, men semantiken är enklare och mer målinriktad.
     **Typ:** sträng
     **Exempel:** &quot;https://plaftform.adobe.io/resolveByPath?path=&quot;/mycorp/content/projectx/fragment/prod/herobanners/banner14.html3&quot;&quot;

* **_experience > decisioning > contents > components > content**

  **Fält:** innehåll
  **Beskrivning:** Ett valfritt fält som ska innehålla innehåll direkt. I stället för att referera till innehåll i en resursdatabas kan komponenten lagra enkelt innehåll direkt. Det här fältet används inte för sammansatta, komplexa och binära innehållsresurser.
  **Typ:** sträng

* **_experience > Decision > contents > components > deliveryURL**

  **Fält:** deliveryURL
  **Beskrivning:** En unik resurslokaliserare (valfritt) som kan hämta resursen från ett innehållsleveransnätverk eller en tjänstslutpunkt. Den här URL:en används av en användaragent för att få tillgång till resursen offentligt.
  **Typ:** sträng
  **Exempel:** &quot;https://cdn.adobe.io/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

* **_experience > Decision > contents > components > linkURL**

  **Fält:** linkURL
  **Beskrivning:** En unik resurslokaliserare (valfritt) för användarinteraktioner. Den här URL:en används för att referera slutanvändaren till i en användaragent och kan spåras.
  **Typ:** sträng
  **Exempel:** &quot;https://cdn.adobe.io/tracker?code=23432&amp;redirect=/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

+++_experience > decisioning > contents > Placement

**Fält:** placering
**Titel:** Placement
**Beskrivning:** Placering att följa. Värdet är URI (@id) för erbjudandeplaceringen som refereras. Se schema https://ns.adobe.com/experience/decisioning/placement.
**Typ:** sträng

+++

+++ _experience > decisioning > Lifecycle Status

**Fält:** lifecycleStatus
**Titel:** Livscykelstatus
**Beskrivning:** Livscykelstatus tillåter att arbetsflöden utförs med ett objekt. Statusen kan påverka var ett objekt är synligt eller anses relevant. Statusändringar styrs av klienter eller tjänster som använder objekten.
**Typ:** sträng
**Möjliga värden:** &quot;Utkast&quot; (standard), &quot;Godkänd&quot;, &quot;Live&quot;, &quot;Slutförd&quot;, &quot;Arkiverad&quot;

+++

+++ _experience > Decision > Decision Option Name

**Fält:** namn
**Titel:** Beslutsalternativsnamn
**Beskrivning:** Alternativnamn som visas i olika användargränssnitt.
**Typ:** sträng

+++

+++ _experience > decisioning > profileConstraints

**Fält:** profileConstraints
**Titel:** Information om begränsning av profil
**Beskrivning:** Profilbegränsningarna avgör om ett alternativ är kvalificerat för den här profilidentiteten i det här sammanhanget. Om profilbegränsningen inte behöver ta hänsyn till värden för varje alternativ, d.v.s. det är en skillnad mellan alternativen från alternativmarkeringen, avbryts hela alternativmarkeringen av profilbegränsningen som utvärderas till &quot;false&quot;. Å andra sidan utvärderas en profilbegränsningsregel som tar ett alternativ som parameter för varje kvalificeringsalternativ i alternativvalet.
**Typ:** objekt

+++

+++_experience > decisioning > profileConstraints > Description

**Fält:** beskrivning
**Titel:** Beskrivning
**Beskrivning:** Profilbegränsningsbeskrivning. Den används för att förmedla mänskliga läsbara avsikter om hur eller varför den här profilbegränsningen konstruerades och/eller vilket alternativ som kommer att inkluderas eller exkluderas av den.
**Typ:** sträng

+++

+++_experience > decisioning > profileConstraints > eligibility Rule

**Fält:** eligibilityRule
**Titel:** Kvalifikationsregel
**Beskrivning:** En referens till en beslutsregel som utvärderas till true eller false för en given profil och/eller andra angivna kontextuella XDM-objekt. Regeln används för att bestämma om alternativet kvalificerar sig för en viss profil. Värdet är URI (@id) för den beslutsregel som refereras. Se schema https://ns.adobe.com/experience/decisioning/rule.
**Typ:** sträng

+++

+++_experience > decisioning > profileConstraints > Profile Constraint Type

**Fält:** profileConstraintType
**Titel:** Typ av profilbegränsning
**Beskrivning:** Avgör om några begränsningar är angivna och hur begränsningarna uttrycks. Det kan vara via en regel eller genom ett eller flera medlemskap i en målgrupp.
**Typ:** sträng
**Möjliga värden:**

* &quot;none&quot; (standard)
* &quot;eligibilityRule&quot;: &quot;Profilbegränsningen uttrycks som en enskild regel som måste utvärderas till true innan den begränsade åtgärden tillåts.&quot;
* &quot;anySegments&quot;: &quot;Profilbegränsningen uttrycks som en eller flera målgrupper och profilen måste vara medlem av minst en av dem innan den begränsade åtgärden tillåts.&quot;
* &quot;allSegments&quot;:&quot;Profilbegränsningen uttrycks som en eller flera målgrupper och profilen måste vara medlem av alla dem innan den begränsade åtgärden tillåts.&quot;
* &quot;rules&quot;:&quot;Profilbegränsningen uttrycks som ett antal olika regler, t.ex. behörighet, tillämplighet, lämplighet, som alla måste utvärderas till true innan den begränsade åtgärden tillåts.&quot;

+++

+++_experience > decisioning > profileConstraints > Segment Identifiers

**Fält:** segmentIdentities
**Titel:** Segmentidentifierare
**Beskrivning:** Identifierare för målgrupperna
**Typ:** array

* **Identifierare**

  **Fält:**_id
  **Titel:** Identifierare
  **Beskrivning:** Identitet för målgrupperna i det relaterade namnområdet.
  **Typ:** sträng

* **Namnområde**

  **Fält:**-namnområde
  **Titel:** Namnområde
  **Beskrivning:** Det namnutrymme som är associerat med attributet `xid`.
  **Typ:** objekt
  **Obligatoriskt:** &quot;code&quot;

   * **Kod**

     **Fält:** kod
     **Titel:** Kod
     **Beskrivning:** Koden är en läsbar identifierare för namnutrymmet och kan användas för att begära det tekniska namnområdes-ID som används för bearbetning av identitetsdiagram.
     **Typ:** sträng

* **Upplevelseidentifierare**

  **Fält:** xid
  **Titel:** Upplevelseidentifierare
  **Beskrivning:** I förekommande fall representerar det här värdet en identifierare för korsnamnrymd som är unik för alla identifierare med namnrymd i alla namnrymder.
  **Typ:** sträng

+++

+++ _experience > decisioning > ranking

**Fält:** rankning
**Titel:** Information om rankning
**Beskrivning:** Rankning (prioritet). Definierar vad som anses vara den \&quot;bästa åtgärden\&quot; med tanke på beslutskriterierna. Bland alla valda alternativ som uppfyller villkoren för behörighet avgör rangordningsordningen vilket eller vilka översta N-alternativ som föreslås.
**Typ:** objekt

+++

+++_experience > Decision > ranking > Order Evaluation

**Fält:** ordning
**Titel:** Orderutvärdering
**Beskrivning:** Utvärdering av en relativ ordning för ett eller flera beslutsalternativ. Alternativ med högre ordningstal markeras över alternativ med lägre ordningstal. De värden som bestäms med den här metoden kan ordnas, men avståndet mellan dem kan inte mätas och varken summor eller produkter kan beräknas. Medianen och läget är de enda måtten på central tendens som kan användas för ordningstal.
**Typ:** objekt

* **Poängfunktion**

  Funktionen **Fält:**
  **Titel:** Bedömningsfunktion
  **Beskrivning:** En referens till en funktion som beräknar ett numeriskt poängvärde för det här beslutsalternativet. Beslutsalternativen kommer sedan att sorteras (rangordnas) efter den poängen. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/function.
  **Typ:** sträng

* **Typ av orderutvärdering**

  **Fält:** orderEvaluationType
  **Titel:** Orderutvärderingstyp
  **Beskrivning:** Anger vilken ordningsutvärderingsmekanism som används, statisk prioritet för beslutsalternativen, en bedömningsfunktion som beräknar ett numeriskt värde för varje alternativ eller en AI-modell som tar emot en lista för att ordna den.
  **Typ:** sträng
  **Möjliga värden:** &quot;static&quot;, &quot;scoringFunction&quot;, &quot;rankingStrategy&quot;

* **Rankningsstrategi**

  **Fält:** rankingStrategy
  **Titel:** rankningsstrategi
  **Beskrivning:** En referens till en strategi som rangordnar ett beslutsalternativ. Beslutsalternativen returneras i en ordnad lista. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/rankingStrategy.
  **Typ:** sträng

+++

+++_experience > Decision > ranking > Priority

**Fält:** prioritet
**Titel:** Prioritet
**Beskrivning:** Prioriteten för ett enskilt beslutsalternativ i förhållande till alla andra alternativ. Alternativ som ingen orderfunktion har angetts för prioriteras med den här egenskapen. Alternativ med högre prioritetsvärden markeras före alternativ med lägre prioritet. Om två eller flera kvalificerande alternativ har det högsta prioritetsvärdet, väljs ett på ett enhetligt slumpmässigt sätt och används för beslutsförslaget.
**Typ:** heltal
**Minimivärde:** 0
**Standardvärde:** 0

+++

+++ _experience > decisioning > taggar

**Fält:** taggar
**Titel:** Taggar
**Beskrivning:** Uppsättningen med samlingskvalificerare (tidigare känd som taggar) som är associerade med den här entiteten. Samlingskvalificerarna används i filteruttryck för att begränsa det totala lagret till en delmängd (kategori).
**Typ:**-matris

+++

<!--Field without name under tags: Description: An identifier of a collection qualifier object. The value is the @id of the collection qualifier that is referenced. See tag schema: https://ns.adobe.com/experience/decisioning/tag. Type: string-->

+++repo

**Fält:**_repo
**Typ:** objekt

+++ 

+++ _repo > Decision Option ETag

**Fält:**-tagg
**Titel:** Beslutsalternativets ETag
**Beskrivning:** Den revision som beslutsalternativsobjektet var när ögonblicksbilden togs.
**Typ:** sträng

+++
