---
title: Datauppsättning med personaliserade erbjudanden
description: I det här avsnittet visas alla fält som används i den exporterade datauppsättningen för erbjudanden
feature: Decision Management, Datasets
topic: Integrations
role: User, Data Engineer
level: Intermediate
exl-id: c7f691aa-8f89-4f23-b897-53211863eb6d
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '2009'
ht-degree: 0%

---

# Datauppsättning med personaliserade erbjudanden {#offers-dataset}

Varje gång ett erbjudande ändras uppdateras den autogenererade datauppsättningen för personaliserade erbjudanden.

![](../assets/dataset-offers.png)

Den senaste lyckade batchen i datauppsättningen visas till höger. Den hierarkiska vyn av schemat för datauppsättningen visas i den vänstra rutan.

>[!NOTE]
>
>Lär dig hur du får åtkomst till exporterade datauppsättningar för varje objekt i ditt Erbjudandebibliotek i [det här avsnittet](../export-catalog/access-dataset.md).

Här är en lista över alla fält som kan användas i **[!UICONTROL Decision Object Repository - Personalized Offers]** datauppsättning.

<!--Personalized offers form the set of choices for a decision. The objective for decisioning is to take a large inventory of items and apply numerous constraint rules to that inventory to narrow it down and then to rank the qualifying options according to a criteria. The resulting propositions assemble and personalize the experience for specific individuals.-->

+++ Identifierare

**Fält:** _id
**Titel:** Identifierare
**Beskrivning:** En unik identifierare för posten.
**Typ:** string

+++

+++ upplevelse {#experience}

**Fält:** upplevelse
**Typ:** object

+++

+++ _experience > decisioning

**Fält:** beslut
**Typ:** object

+++

+++ _experience > decisioning > calendarConstraints

**Fält:** calendarConstraints
**Titel:** Begränsningsinformation för kalender
**Beskrivning:** Kalenderbegränsningar avgör om ett beslutsalternativ är giltigt utifrån ett datumintervall. Förutom detta datumintervall kan alternativet inte föreslås.
**Typ:** object

* **Slutdatum och -tid**

  **Fält:** endDate
  **Titel:** Slutdatum och -tid
  **Beskrivning:** Slutdatumet för en beslutsalternativs giltighet. Alternativ som har passerat slutdatumet kan inte längre föreslås i beslutsprocessen.
  **Typ:** string

* **Startdatum och -tid**

  **Fält:** startDate
  **Titel:** Startdatum och -tid
  **Beskrivning:** Startdatumet för ett beslutsalternativs giltighet. Alternativ som inte har nått sitt startdatum kan inte föreslås än i beslutsprocessen.
  **Typ:** string

+++

+++ _experience > decisioning > properties

**Fält:** egenskaper
**Titel:** Beslutsalternativsegenskaper
**Beskrivning:** Ytterligare egenskaper eller attribut som hör till det här särskilda beslutsalternativet. Olika instanser kan ha olika egenskaper (tangenter på kartan). Egenskaperna är namnvärdespar som används för att skilja mellan olika beslutsalternativ. Egenskaper används som värden i innehåll som representerar det här alternativet och som funktioner för att analysera och optimera prestanda för ett alternativ. När alla instanser har samma attribut eller egenskap bör den aspekten modelleras som ett tilläggsschema som härleds från beslutsalternativsinformationen.
**Typ:** object

+++

+++ _experience > decisioning > contents

**Fält:** innehåll
**Titel:** Innehållsinformation
**Beskrivning:** Innehållsobjekt som återger beslutsobjektet i olika sammanhang. Ett enda beslutsalternativ kan ha flera innehållsvarianter. Innehåll är information som riktar sig till en målgrupp som konsumeras i en (digital) upplevelse. Innehållet levereras via kanaler till en viss plats.
**Typ:** array

+++

++_experience > decisioning > contents > components

**Fält:** komponenter
**Beskrivning:** Komponenterna i det innehåll som representerar beslutsalternativet, inklusive alla deras språkvarianter. Specifika komponenter hittas av &#39;dx:format&#39;, &#39;dc:subject&#39; och &#39;dc:language&#39; eller en kombination av dessa. Dessa metadata används för att hitta eller representera innehållet som är kopplat till ett erbjudande och integrera det enligt placeringskontraktet.
**Typ:** array
**Obligatoriskt:** &quot;_type&quot;, &quot;_dc&quot; <!--TBC?-->

* **_experience > decisioning > contents > components > Content Component Type**

  **Fält:** _type
  **Titel:** Innehållskomponenttyp
  **Beskrivning:** En uppräknad uppsättning URI:er där varje värde mappas till en typ som ges till innehållskomponenten. En del användare av innehållsrepresentationerna förväntar sig att värdet @type ska vara en referens till schemat som beskriver ytterligare egenskaper för innehållskomponenten.
  **Typ:** string

* **_experience > decisioning > contents > components > _dc**

  **Fält:** _dc
  **Typ:** object
  **Obligatoriskt:** &quot;format&quot;

   * **Format**

     **Fält:** format
     **Titel:** Format
     **Beskrivning:** Resursens fysiska eller digitala manifestation. Vanligtvis ska Format innehålla resursens medietyp. Format kan användas för att fastställa programvara, maskinvara eller annan utrustning som behövs för att visa eller använda resursen. Rekommenderad bästa metod är att välja ett värde från ett kontrollerat vokabulär (t.ex. listan med [Internetmedietyper](https://www.iana.org/assignments/media-types/) definiera datormedieformat).
     **Typ:** string
     **Exempel:** &quot;application/vnd.adobe.photoshop&quot;

   * **Språk**
     **Fält:** språk
     **Titel:** Språk
     **Beskrivning:** Resursens språk. \nSpråk anges i språkkoden enligt definitionen i [IETF RFC 3066](https://www.ietf.org/rfc/rfc3066.txt), som ingår i BCP 47, som används någon annanstans i XDM.
     **Typ:** array
     **Exempel:** &quot;\n&quot;, &quot;pt-BR&quot;, &quot;es-ES&quot;

* **_experience > decisioning > contents > components > _repo**

  **Fält:** repo
  **Typ:** object

   * **id**

     **Fält:** id
     **Beskrivning:** En valfri unik identifierare som refererar till resursen i en innehållsdatabas. När plattforms-API:er används för att hämta representationen kan klienten förvänta sig en ytterligare egenskap \&quot;repo:resolveUrl\&quot; för att hämta resursen.
     **Typ:** string
     **Exempel:** &quot;urn:aaid:sc:US:6dc33479-13ca-4b19-b25d-c805eff8a69e&quot;

   * **name**

     **Fält:** name
     **Beskrivning:** Tips om var du hittar databasen där den externa resursen lagras av \&quot;repo:id\&quot;.
     **Typ:** string

   * **databaseID**

     **Fält:** databaseID
     **Beskrivning:** En valfri unik identifierare som refererar till resursen i en innehållsdatabas. När plattforms-API:er används för att hämta representationen kan klienten förvänta sig en ytterligare egenskap \&quot;repo:resolveUrl\&quot; för att hämta resursen.
     **Typ:** string
     **Exempel:** &quot;C87932A55B06F7070A49412D@AdobeOrg&quot;

   * **resolveURL**

     **Fält:** resolveURL
     **Beskrivning:** En unik resurslokaliserare (tillval) som kan läsa resursen i en innehållsdatabas. Detta gör det enklare att hämta resursen utan att kunden förstår var resursen hanteras och vilka API:er som ska anropas. Detta liknar en HAL-länk, men semantiken är enklare och mer målinriktad.
     **Typ:** string
     **Exempel:** &quot;https://plaftform.adobe.io/resolveByPath?path=&quot;/mycorp/content/projectx/fragment/prod/herobanners/banner14.html3&quot;&quot;

* **_experience > decisioning > contents > components > content**

  **Fält:** innehåll
  **Beskrivning:** Ett valfritt fält som innehåller innehåll direkt. I stället för att referera till innehåll i en resursdatabas kan komponenten lagra enkelt innehåll direkt. Det här fältet används inte för sammansatta, komplexa och binära innehållsresurser.
  **Typ:** string

* **_experience > decisioning > contents > components > deliveryURL**

  **Fält:** deliveryURL
  **Beskrivning:** En unik resurslokaliserare (tillval) som kan hämta resursen från ett leveransnätverk eller en tjänstslutpunkt. Den här URL:en används av en användaragent för att få tillgång till resursen offentligt.
  **Typ:** string
  **Exempel:** &quot;https://cdn.adobe.io/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

* **_experience > decisioning > contents > components > linkURL**

  **Fält:** linkURL
  **Beskrivning:** En unik resurslokaliserare (tillval) för användarinteraktioner. Den här URL:en används för att referera slutanvändaren till i en användaragent och kan spåras.
  **Typ:** string
  **Exempel:** &quot;https://cdn.adobe.io/tracker?code=23432&amp;redirect=/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

++_experience > decisioning > contents > Placement

**Fält:** placering
**Titel:** Placement
**Beskrivning:** Placering att följa. Värdet är URI (@id) för erbjudandeplaceringen som refereras. Se schema https://ns.adobe.com/experience/decisioning/placement.
**Typ:** string

+++

+++ _experience > decisioning > Lifecycle Status

**Fält:** lifecycleStatus
**Titel:** Livscykelstatus
**Beskrivning:** Livscykelstatus gör att arbetsflöden kan utföras med ett objekt. Statusen kan påverka var ett objekt är synligt eller anses relevant. Statusändringar styrs av klienter eller tjänster som använder objekten.
**Typ:** string
**Möjliga värden:** &quot;Utkast&quot; (standard), &quot;Godkänd&quot;, &quot;Live&quot;, &quot;Slutförd&quot;, &quot;Arkiverad&quot;

+++

+++ _experience > Decision > Decision Option Name

**Fält:** name
**Titel:** Namn på beslutsalternativ
**Beskrivning:** Alternativ som visas i olika användargränssnitt.
**Typ:** string

+++

+++ _experience > decisioning > profileConstraints

**Fält:** profileConstraints
**Titel:** Profilbegränsningsdetaljer
**Beskrivning:** Profilbegränsningarna avgör om ett alternativ är kvalificerat för den här profilidentiteten i det här sammanhanget. Om profilbegränsningen inte behöver ta hänsyn till värden för varje alternativ, d.v.s. det är en skillnad mellan alternativen från alternativmarkeringen, avbryts hela alternativmarkeringen av profilbegränsningen som utvärderas till &quot;false&quot;. Å andra sidan utvärderas en profilbegränsningsregel som tar ett alternativ som parameter för varje kvalificeringsalternativ i alternativvalet.
**Typ:** object

+++

+++_experience > decisioning > profileConstraints > Description

**Fält:** description
**Titel:** Beskrivning
**Beskrivning:** Profilbegränsningsbeskrivning. Den används för att förmedla mänskliga läsbara avsikter om hur eller varför den här profilbegränsningen konstruerades och/eller vilket alternativ som kommer att inkluderas eller exkluderas av den.
**Typ:** string

+++

++_experience > decisioning > profileConstraints > eligibility Rule

**Fält:** eligibilityRule
**Titel:** Behörighetsregel
**Beskrivning:** En referens till en beslutsregel som utvärderas till true eller false för en given profil och/eller andra angivna kontextuella XDM-objekt. Regeln används för att bestämma om alternativet kvalificerar sig för en viss profil. Värdet är URI (@id) för den beslutsregel som refereras. Se schema https://ns.adobe.com/experience/decisioning/rule.
**Typ:** string

+++

++_experience > decisioning > profileConstraints > Profile Constraint Type

**Fält:** profileConstraintType
**Titel:** Typ av profilbegränsning
**Beskrivning:** Avgör om några begränsningar är angivna och hur begränsningarna uttrycks. Det kan vara via en regel eller genom ett eller flera medlemskap i en målgrupp.
**Typ:** string
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

  **Fält:** _id
  **Titel:** Identifierare
  **Beskrivning:** Identitet för målgrupperna i det relaterade namnutrymmet.
  **Typ:** string

* **Namnutrymme**

  **Fält:** namespace
  **Titel:** Namnutrymme
  **Beskrivning:** Namnutrymmet som är associerat med `xid` -attribut.
  **Typ:** object
  **Obligatoriskt:** &quot;code&quot;

   * **Code**

     **Fält:** kod
     **Titel:** Code
     **Beskrivning:** Koden är en läsbar identifierare för namnutrymmet och kan användas för att begära det tekniska namnutrymmes-ID som används för bearbetning av identitetsdiagram.
     **Typ:** string

* **Experience Identifier**

  **Fält:** xid
  **Titel:** Experience Identifier
  **Beskrivning:** Om det finns en sådan representerar det här värdet en identifierare för korsnamnutrymme som är unik för alla identifierare som har namnutrymmesomfång i alla namnutrymmen.
  **Typ:** string

+++

+++ _experience > decisioning > ranking

**Fält:** rankning
**Titel:** Rankningsdetaljer
**Beskrivning:** Rankning (prioritet). Definierar vad som anses vara den \&quot;bästa åtgärden\&quot; med tanke på beslutskriterierna. Bland alla valda alternativ som uppfyller villkoren för behörighet avgör rangordningsordningen vilket eller vilka översta N-alternativ som föreslås.
**Typ:** object

+++

++_experience > decisioning > ranking > Order Evaluation

**Fält:** beställa
**Titel:** Utvärdering av order
**Beskrivning:** Utvärdering av en relativ ordning för ett eller flera beslutsalternativ. Alternativ med högre ordningstal markeras över alternativ med lägre ordningstal. De värden som bestäms med den här metoden kan ordnas, men avståndet mellan dem kan inte mätas och varken summor eller produkter kan beräknas. Medianen och läget är de enda måtten på central tendens som kan användas för ordningstal.
**Typ:** object

* **Poängfunktion**

  **Fält:** function
  **Titel:** Poängfunktion
  **Beskrivning:** En referens till en funktion som beräknar en numerisk poäng för det här beslutsalternativet. Beslutsalternativen kommer sedan att sorteras (rangordnas) efter den poängen. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/function.
  **Typ:** string

* **Typ av orderutvärdering**

  **Fält:** orderEvaluationType
  **Titel:** Typ av orderutvärdering
  **Beskrivning:** Anger vilken ordningsutvärderingsmekanism som används, statisk prioritet för beslutsalternativen, en poängsättningsfunktion som beräknar ett numeriskt värde för varje alternativ eller en AI-modell som tar emot en lista för att ordna den.
  **Typ:** string
  **Möjliga värden:** &quot;static&quot;, &quot;scoringFunction&quot;, &quot;rankingStrategy&quot;

* **Rankningsstrategi**

  **Fält:** rankingStrategy
  **Titel:** Rankningsstrategi
  **Beskrivning:** En referens till en strategi som rankar en lista över beslutsalternativ. Beslutsalternativen returneras i en ordnad lista. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/rankingStrategy.
  **Typ:** string

+++

+++_experience > Decision > ranking > Priority

**Fält:** prioritet
**Titel:** Prioritet
**Beskrivning:** Prioriteten för ett enda beslutsalternativ i förhållande till alla andra alternativ. Alternativ som ingen orderfunktion har angetts för prioriteras med den här egenskapen. Alternativ med högre prioritetsvärden markeras före alternativ med lägre prioritet. Om två eller flera kvalificerande alternativ har det högsta prioritetsvärdet, väljs ett på ett enhetligt slumpmässigt sätt och används för beslutsförslaget.
**Typ:** heltal
**Minsta värde:** 0
**Standardvärde:** 0

+++

+++ _experience > decisioning > taggar

**Fält:** taggar
**Titel:** Taggar
**Beskrivning:** Uppsättningen med samlingskvalificerare (kallas tidigare taggar) som är associerade med den här entiteten. Samlingskvalificerarna används i filteruttryck för att begränsa det totala lagret till en delmängd (kategori).
**Typ:** array

+++

<!--Field without name under tags: Description: An identifier of a collection qualifier object. The value is the @id of the collection qualifier that is referenced. See tag schema: https://ns.adobe.com/experience/decisioning/tag. Type: string-->

+++_repo

**Fält:** repo
**Typ:** object

+++

+++ _repo > Decision Option ETag

**Fält:** etag
**Titel:** Beslutsalternativ ETag
**Beskrivning:** Revisionen som beslutsalternativsobjektet användes när ögonblicksbilden togs.
**Typ:** string

+++
