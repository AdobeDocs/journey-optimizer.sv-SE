---
title: Datauppsättning med beslut
description: I det här avsnittet visas alla fält som används i den exporterade datauppsättningen för beslut
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 064762b7-9774-42eb-bcef-1d92bc94a988
source-git-commit: 118eddf540d1dfb3a30edb0b877189ca908944b1
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 0%

---

# Datauppsättning med beslut {#decisions-dataset}

Varje gång ett erbjudande ändras uppdateras den autogenererade datauppsättningen för beslut.

![](../assets/dataset-activities.png)

Den senaste lyckade batchen i datauppsättningen visas till höger. Den hierarkiska vyn av schemat för datauppsättningen visas i den vänstra rutan.

>[!NOTE]
>
>Lär dig hur du får åtkomst till exporterade datauppsättningar för varje objekt i ditt Erbjudandebibliotek i [det här avsnittet](../export-catalog/access-dataset.md).

Här är en lista över alla fält som kan användas i **[!UICONTROL Decision Object Repository - Decisions]** datauppsättning (kallades tidigare&quot;Decision Object Repository - Activities&quot;).

<!--A decision (formerly known as offer decision) is used to control the decisioning process. It specifies the filter applied to the total inventory to narrow down offers by topic/category, the placement to narrow down the inventory to those offers that technically fit into the reserved space for the offer and specifies a fallback option should the combined constraints disqualify all available personalization offers.-->

+++ Identifierare

**Fält:** _id
**Titel:** Identifierare
**Beskrivning:** En unik identifierare för posten.
**Typ:** string

+++

+++ upplevelse

**Fält:** upplevelse
**Typ:** object

+++

+++ _experience > decisioning

**Fält:** beslut
**Typ:** object

+++

+++ _experience > decisioning > conditions

**Fält:** kriterier
**Titel:** Kriterier
**Beskrivning:** Definierar en uppsättning beslutskriterier där var och en innehåller en uppsättning begränsningar.
**Typ:** array

+++

+++ _experience > decisioning > conditions > description

**Fält:** description
**Titel:** Beskrivning
**Beskrivning:** Villkorsbeskrivning. Det används för att förmedla mänskliga, läsbara avsikter om hur eller varför detta kriterium konstruerades och hur det påverkar beslutet.
**Typ:** string

+++

++_experience > decisioning > conditions > optionSelection

**Fält:** optionSelection
**Titel:** Alternativ
**Beskrivning:** Alternativvalet definierar giltigheten/tillämpligheten för alternativen i det här sammanhanget.
**Typ:** object

* Beskrivning

   **Fält:** description
   **Titel:** Beskrivning
   **Beskrivning:** Beskrivning av alternativval. Det används för att förmedla mänskliga läsbara avsikter om hur eller varför det här alternativvalet skapades och/eller vilket alternativ som matchar.
   **Typ:** string

* Alternativfilter

   **Fält:** filter
   **Titel:** Alternativfilter
   **Beskrivning:** Referensen till ett samlingskvalificerarbaserat (tidigare kallat taggbaserat filter) som matchar alternativ från ett lager med hjälp av deras kopplade samlingskvalificerare. Värdet är URI (@id) för den beslutsregel som refereras. Se schema https://ns.adobe.com/experience/decisioning/filter.
   **Typ:** string

* Typ av profilbegränsning

   **Fält:** optionSelectionType
   **Titel:** Typ av profilbegränsning
   **Beskrivning:** Avgör om några begränsningar är angivna och hur begränsningarna uttrycks. Det kan vara via en filterfråga eller genom ett eller flera segmentmedlemskap.
   **Typ:** string
   **Möjliga värden:** &quot;none&quot; (default), &quot;directList&quot;, &quot;filter&quot;

* Alternativlista

   **Fält:** alternativ
   **Titel:** Alternativlista
   **Beskrivning:** En lista som direkt anger alternativen utan att utvärdera en filterfråga. Du kan antingen ange en alternativlista eller en alternativfilterregel.
   **Typ:** array

<!--Missing title under Option List? Desc = An identifier of an decision option entity. The value value refers to an `@id` property of a decision option. Type: string-->

+++

++_experience > decisioning > conditions > placements

**Fält:** placeringar
**Titel:** Placeringsbegränsningar
**Beskrivning:** Placeringsbegränsningen anger att det här kriteriet bara gäller för de listade placeringarna. Endast när den riktade placeringen finns i `xdm:placements` list är det alternativ du väljer. Annars hoppas hela beslutskriterierna över. När listan &#39;xdm:placements&#39; utelämnas eller är tom, beaktas kriteriet för alla riktade placeringar. De placeringar som anges här innehåller implicita kriterier för alternativvalet. Ett alternativ som ska beaktas måste ha en representation för den avsedda placeringen.
**Typ:** array

* Placement-ID

   **Titel:** Placement-ID
   **Beskrivning:** En referens till en placeringsenhet. Värdet är URI (@id) för placeringen som refereras. Se schema https://ns.adobe.com/experience/decisioning/placement.
   **Typ:** string

+++

++_experience > decisioning > conditions > profileConstraints

**Fält:** profileConstraints
**Titel:** Profilbegränsning
**Beskrivning:** Profilbegränsningen avgör om ett alternativ är tillgängligt för den här profilidentiteten just nu, i det här sammanhanget. Om profilbegränsningen inte behöver ta hänsyn till värdena för varje alternativ, d.v.s. det är en skillnad mellan alternativen från alternativmarkeringen, avbryts hela alternativmarkeringen av profilbegränsningen som utvärderas till &quot;false&quot;. Å andra sidan utvärderas en profilbegränsningsregel som tar ett alternativ som parameter för varje kvalificeringsalternativ i alternativvalet.
**Typ:** object

+++

+++_experience > decisioning > conditions > profileConstraints > Description

**Fält:** description
**Titel:** Beskrivning
**Beskrivning:** Profilbegränsningsbeskrivning. Den används för att förmedla mänskliga läsbara avsikter om hur eller varför den här profilbegränsningen konstruerades och/eller vilket alternativ som kommer att inkluderas eller exkluderas av den.
**Typ:** string

+++

+++ _experience > decisioning > conditions > profileConstraints > eligibility Rule

**Fält:** eligibilityRule
**Titel:** Behörighetsregel
**Beskrivning:** En referens till en beslutsregel som utvärderas till true eller false för en given profil och/eller andra angivna kontextuella XDM-objekt. Regeln används för att bestämma om alternativet kvalificerar sig för en viss profil. Värdet är URI (@id) för den beslutsregel som refereras. Se schema https://ns.adobe.com/experience/decisioning/rule.
**Typ:** string

+++

+++ _experience > decisioning > conditions > profileConstraints > Profile Constraint Type

**Fält:** profileConstraintType
**Titel:** Typ av profilbegränsning
**Beskrivning:** Avgör om några begränsningar är angivna och hur begränsningarna uttrycks. Det kan vara via en regel eller genom ett eller flera segmentmedlemskap.
**Typ:** string
**Möjliga värden:**
* &quot;none&quot; (standard)
* &quot;eligibilityRule&quot;: &quot;Profilbegränsningen uttrycks som en enskild regel som måste utvärderas till true innan den begränsade åtgärden tillåts.&quot;
* &quot;anySegments&quot;: &quot;Profilbegränsningen uttrycks som ett eller flera segment och profilen måste vara medlem i minst ett av dem innan den begränsade åtgärden tillåts.&quot;
* &quot;allSegments&quot;: &quot;Profilbegränsningen uttrycks som ett eller flera segment och profilen måste vara medlem av alla dem innan den begränsade åtgärden tillåts.&quot;
* regler: &quot;Profilbegränsningen uttrycks som ett antal olika regler, t.ex. behörighet, tillämplighet, lämplighet, som alla måste utvärderas till true innan den begränsade åtgärden tillåts.&quot;

+++

+++ _experience > decisioning > conditions > profileConstraints > segmentIdentities

**Fält:** segmentIdentities
**Titel:** Segmentidentifierare
**Beskrivning:** Identifierare för segmenten.
**Typ:** array

* Identifierare

   **Fält:** _id
   **Titel:** Identifierare
   **Beskrivning:** Identitet för segmentet i det relaterade namnutrymmet.
   **Typ:** string

* namespace

   **Fält:** namespace
   **Titel:** Namnutrymme
   **Beskrivning:** Namnutrymmet som är associerat med `xid` -attribut.
   **Typ:** object
   **Obligatoriskt:** &quot;code&quot;

   * Code

      **Fält:** kod
      **Titel:** Code
      **Beskrivning:** Koden är en läsbar identifierare för namnutrymmet och kan användas för att begära det tekniska namnutrymmes-ID som används för bearbetning av identitetsdiagram.
      **Typ:** string

* Upplevelseidentifierare

   **Fält:** xid
   **Titel:** Upplevelseidentifierare
   **Beskrivning:** Om det finns en sådan representerar det här värdet en identifierare för korsnamnutrymme som är unik för alla identifierare som har namnutrymmesomfång i alla namnutrymmen.
   **Typ:** string

+++

++_experience > decisioning > conditions > ranking

**Fält:** rankning
**Titel:** Rankningsdetaljer
**Beskrivning:** Rankning (prioritet). Definierar hur det \&quot;bästa alternativet\&quot; bestäms utifrån beslutskriteriets sammanhang. Bland alla de valda alternativen som uppfyller profilbegränsningarna avgör rankningen vilket eller vilka översta N-alternativ som ska föreslås.
**Typ:** object

+++

++_experience > decisioning > conditions > ranking > order

**Fält:** order
**Titel:** Orderutvärdering
**Beskrivning:** Utvärdering av en relativ ordning för ett eller flera beslutsalternativ. Alternativ med högre ordningstal markeras över alternativ med lägre ordningstal. De värden som bestäms med den här metoden kan ordnas, men avståndet mellan dem kan inte mätas och varken summor eller produkter kan beräknas. Medianen och läget är de enda måtten på central tendens som kan användas för ordningstal.
**Typ:** object

* Poängfunktion

   **Fält:** function
   **Titel:** Poängfunktion
   **Beskrivning:** En referens till en funktion som beräknar en numerisk poäng för det här beslutsalternativet. Beslutsalternativen kommer sedan att sorteras (rangordnas) efter den poängen. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/function.
   **Typ:** string

* Typ av orderutvärdering*

   **Fält:** orderEvaluationType
   **Titel:** Typ av orderutvärdering
   **Beskrivning:** Anger vilken ordningsutvärderingsmekanism som används, statisk prioritet för beslutsalternativen, en poängsättningsfunktion som beräknar ett numeriskt värde för varje alternativ eller en rangordningsstrategi som tar emot en lista för att ordna den.
   **Typ:** string
   **Möjliga värden:** &quot;static&quot;, &quot;scoringFunction&quot;, &quot;rankingStrategy&quot;

* Rankningsstrategi

   **Fält:** rankingStrategy
   **Titel:** Rankningsstrategi
   **Beskrivning:** En referens till en strategi som rankar en lista över beslutsalternativ. Beslutsalternativen returneras i en ordnad lista. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/rankingStrategy.
   **Typ:** string

+++

+++ _experience > decisioning > conditions > ranking > Priority

**Fält:** prioritet
**Titel:** Prioritet
**Beskrivning:** Prioriteten för ett enda beslutsalternativ i förhållande till alla andra alternativ. Alternativ som ingen orderfunktion har angetts för prioriteras med den här egenskapen. Alternativ med högre prioritetsvärden markeras före alternativ med lägre prioritet. Om två eller flera kvalificerande alternativ har det högsta prioritetsvärdet, väljs ett slumpmässigt och används för beslutsförslaget.
**Typ:** heltal
**Minsta värde:** 0
**Standardvärde:** 0

+++

+++ _experience > decisioning > Activity End Date and Time

**Fält:** endTime
**Titel:** Slutdatum och tid för aktiviteten
**Beskrivning:** Slutdatum och sluttid för beslut (tidigare kallat aktivitet). Egenskapen har semantiken för schema.orgs endTime-egenskap definierad på https://schema.org/Action.
**Typ:** string

+++

+++ _experience > decisioning > Fallback Option

**Fält:** fallback
**Titel:** Reservalternativ
**Beskrivning:** Referensen till ett reservalternativ som används vid beslut inom ramen för detta beslut kvalificerar inte något av de vanliga alternativen (detta inträffar vanligtvis när hårda begränsningar tillämpas). Värdet är URI (@id) för det reservalternativ som refereras.
**Typ:** string

+++

+++ _experience > Decision > Activity Name

**Fält:** name
**Titel:** Aktivitetsnamn
**Beskrivning:** Beslutsnamn (tidigare kallat aktivitet) som visas i olika användargränssnitt.
**Typ:** string

+++

+++_experience > Decision > Activity Start Date and Time

**Fält:** startTime
**Titel:** Startdatum och -tid för aktivitet
**Beskrivning:** Startdatum och sluttid för beslut (tidigare kallat aktivitet). Egenskapen har semantiken för schema.orgs startTime-egenskap definierad på https://schema.org/Action.
**Typ:** string

+++

+++ repo

**Fält:** repo
**Typ:** object

+++

+++ _repo > Activity ETag

**Fält:** etag
**Titel:** Aktivitet - ETag
**Beskrivning:** Ändringen som beslutsobjektet (tidigare kallat activity) var när ögonblicksbilden togs.
**Typ:** string

+++
