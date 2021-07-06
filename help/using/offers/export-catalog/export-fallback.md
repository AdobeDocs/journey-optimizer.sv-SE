---
title: Reserverbjudanden
description: I det här avsnittet visas alla fält som används i den exporterade datauppsättningen för reserverbjudanden.
feature: Erbjudanden
topic: Integreringar
role: User
level: Intermediate
source-git-commit: a25264cb43f77671c29f18522110fd85d0155697
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 0%

---

# Reserverbjudanden {#fallback-dataset}

Varje gång ett erbjudande ändras uppdateras den autogenererade datauppsättningen för reserverbjudanden.

![](../../assets/dataset-fallback.png)

Den senaste lyckade batchen i datauppsättningen visas till höger. Den hierarkiska vyn av schemat för datauppsättningen visas i den vänstra rutan.

>[!NOTE]
>
>Lär dig hur du får åtkomst till exporterade datauppsättningar för varje objekt i ditt Erbjudandebibliotek i [det här avsnittet](../export-catalog/access-dataset.md).

Här är en lista över alla fält som kan användas i **[!UICONTROL Decision Object Repository - Fallback Offers]**-datauppsättningen.

## Identifierare

**Fält:** _id 
**Title:** Identifier 
**Description:** A unique identifier for the record.
**Typ:** sträng

## upplevelse

**fält:** _upplevelsetyp 
**:** objekt

### _experience > decisioning

**fält:** bestämma 
**typ:** objekt

#### _experience > decisioning > properties

**fält:** karakteristiska 
**namn:** Beskrivning av beslutsalternativ:
**** Ytterligare egenskaper eller attribut som hör till det här beslutsalternativet. Olika instanser kan ha olika egenskaper (tangenter på kartan). Egenskaperna är namnvärdespar som används för att skilja mellan olika beslutsalternativ. Egenskaper används som värden i innehåll som representerar det här alternativet och som funktioner för att analysera och optimera prestanda för ett alternativ. När alla instanser har samma attribut eller egenskap bör den aspekten modelleras som ett tilläggsschema som härleds från beslutsalternativsinformationen.
**text:** objekt

<!--Field under Characteristics without title = additionalProperties? Desc = Value of the property. Type: string-->

#### _experience > decisioning > contents

**fält:** innehåll 
**rubrik:** Innehållsinformation 
**beskrivning:** Innehållsobjekt som återger beslutsobjektet i olika sammanhang. Ett enda beslutsalternativ kan ha flera innehållsvarianter. Innehåll är information som riktar sig till en målgrupp som konsumeras i en (digital) upplevelse. Innehållet levereras via kanaler till en viss plats.
**Typ:** array

**_experience > decisioning > contents > components**

**Fält:** Components 
**Description:** Komponenterna i innehållet som representerar beslutsalternativet, inklusive alla deras språkvarianter. Specifika komponenter hittas av &#39;dx:format&#39;, &#39;dc:subject&#39; och &#39;dc:language&#39; eller en kombination av dessa. Dessa metadata används för att hitta eller representera innehållet som är kopplat till ett erbjudande och integrera det enligt placeringskontraktet.
**Typ:** matris 
**krävs:** &quot;_type&quot;, &quot;_dc&quot;  <!--TBC?-->

* **_experience > decisioning > contents > components > Content Component Type**

   **Fält:** _typ
   **titel:** Innehållskomponenttyp
   **Beskrivning:** En uppräknad uppsättning URI:er där varje värde mappas till en typ som anges för innehållskomponenten. En del användare av innehållsrepresentationerna förväntar sig att värdet @type ska vara en referens till schema som beskriver ytterligare egenskaper för innehållskomponenten.
   **Typ:** sträng

* **_experience > decisioning > contents > components > _dc**

   **Fält:** _dc
   **text:** objekt
   **Obligatoriskt:** &quot;format&quot;

   * **Format**

      **fält:** format
      **titel:** format
      **Beskrivning:** Resursens fysiska eller digitala manifestation. Vanligtvis ska Format innehålla resursens medietyp. Format kan användas för att fastställa programvara, maskinvara eller annan utrustning som behövs för att visa eller använda resursen. Rekommenderad bästa praxis är att välja ett värde från ett kontrollerat vokabulär (t.ex. listan [Internetmedietyper](http://www.iana.org/-tilldelningar/medietyper/) som definierar datormediaformat).
      **Typ:** sträng
      **Exempel:** &quot;application/vnd.adobe.photoshop&quot;

   * **Språk**

      **fält:** språk
      **titel:** språk
      **Beskrivning:** Resursens språk. \nSpråk anges i språkkoden enligt definitionen i [IETF RFC 3066](https://www.ietf.org/rfc/rfc3066.txt), som är en del av BCP 47, som används någon annanstans i XDM.
      **Typ:** array
      **Exempel:** &quot;\n&quot;, &quot;pt-BR&quot;, &quot;es-ES&quot;

* **_experience > decisioning > contents > components > _repo**

   **Fält:** _repo
   **text:** objekt

   * **id**

      **fält:** id
      **Beskrivning:** En valfri unik identifierare som refererar till resursen i en innehållsdatabas. När plattforms-API:er används för att hämta representationen kan klienten förvänta sig en ytterligare egenskap \&quot;repo:resolveUrl\&quot; för att hämta resursen.
      **Typ:** sträng
      **Exempel:** &quot;:aaid:urnsc:US:6dc33479-13ca-4b19-b25d-c805eff8a69e&quot;

   * **name**

      **fält:** namn
      **Beskrivning:** Tips om var du hittar databasen där den externa resursen lagras av \&quot;repo:id\&quot;.
      **Typ:** sträng

   * **databaseID**

      **fält:** databasID
      **Beskrivning:** En valfri unik identifierare som refererar till resursen i en innehållsdatabas. När plattforms-API:er används för att hämta representationen kan klienten förvänta sig en ytterligare egenskap \&quot;repo:resolveUrl\&quot; för att hämta resursen.
      **Typ:** sträng
      **Exempel:** &quot;C87932A55B06F7070A49412D@AdobeOrg&quot;

   * **resolveURL**

      **fält:** resolveURL
      **Beskrivning:** En unik resurslokaliserare (tillval) som kan läsa resursen i en innehållsdatabas. Detta gör det enklare att hämta resursen utan att kunden förstår var resursen hanteras och vilka API:er som ska anropas. Detta liknar en HAL-länk, men semantiken är enklare och mer ändamålsenlig.
      **Typ:** sträng
      **Exempel:** &quot;https://plaftform.adobe.io/resolveByPath?path=&quot;/mycorp/content/projectx/fragment/prod/herobanners/banner14.html3&quot;&quot;

* **_experience > decisioning > contents > components > content**

   **fält:** innehåll
   **Beskrivning:** Ett valfritt fält där innehållet ska lagras direkt. I stället för att referera till innehåll i en resursdatabas kan komponenten lagra enkelt innehåll direkt. Det här fältet används inte för sammansatta, komplexa och binära innehållsresurser.
   **Typ:** sträng

* **_experience > decisioning > contents > components > deliveryURL**

   **Fält:** deliveryURL
   **Beskrivning:** En unik resurslokaliserare (tillval) som kan hämta resursen från ett leveransnätverk eller en tjänstslutpunkt. Den här URL:en används av en användaragent för att få tillgång till resursen offentligt.
   **Typ:** sträng
   **Exempel:** &quot;https://cdn.adobe.io/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

* **_experience > decisioning > contents > components > linkURL**

   **Fält:** linkURL
   **Beskrivning:** En unik resurspositionerare (tillval) för användarinteraktioner. Den här URL:en används för att referera slutanvändaren till i en användaragent och kan spåras.
   **Typ:** sträng
   **Exempel:** &quot;https://cdn.adobe.io/tracker?code=23432&amp;redirect=/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

**_experience > decisioning > contents > Placement**

**fält:** placeringsrubrik:
**** Placement 
**Description:** Placement to compliance. Värdet är URI (@id) för erbjudandeplaceringen som refereras. Se schema https://ns.adobe.com/experience/decisioning/placement.
**Typ:** sträng

#### _experience > Decision > Lifecycle Status

**Fält:** lifecycleStatus 
**Title:** Lifecycle Status 
**Description:** Lifecycle status tillåter att arbetsflöden utförs med ett objekt. Statusen kan påverka var ett objekt är synligt eller anses relevant. Statusändringar styrs av klienter eller tjänster som använder objekten.
**Typ:** string 
**Möjliga värden:** &quot;Utkast&quot; (standard), &quot;Godkänd&quot;, &quot;Live&quot;, &quot;Slutförd&quot;, &quot;Arkiverad&quot;

#### _experience > Decision > Decision Option Name

**Fält:** namn 
**Titel:** Namn på beslutsalternativ 
**Beskrivning:** Alternativnamn som visas i olika användargränssnitt.
**Typ:** sträng

#### _experience > decisioning > taggar

**Fält:** taggar 
**Titel:** Taggar 
**Beskrivning:** Den uppsättning taggar som är associerade med den här entiteten. Taggarna används i filteruttryck för att begränsa det totala lagret till en delmängd (kategori).
**Typ:** array

<!--Field without name under tags: Description: An identifier of a tag object. The value is the @id of the tag that is referenced. See tag schema: https://ns.adobe.com/experience/decisioning/tag. Type: string-->

## repo

**fält:** _repo-
**typ:** objekt

### _repo > Decision Option ETag

**Fält:** etag 
**Title:** Decision Option ETag 
**Description:** The revision that the Decision option object was when the snapshot was taken.
**Typ:** sträng
