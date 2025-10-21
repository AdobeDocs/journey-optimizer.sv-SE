---
title: Datauppsättning med beslut
description: I det här avsnittet visas alla fält som används i den exporterade datauppsättningen för beslut
badge: label="Äldre" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: 064762b7-9774-42eb-bcef-1d92bc94a988
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '1526'
ht-degree: 0%

---

# Datauppsättning med beslut {#decisions-dataset}

Varje gång ett erbjudande ändras uppdateras den autogenererade datauppsättningen för beslut.

![](../assets/dataset-activities.png)

Den senaste lyckade batchen i datauppsättningen visas till höger. Den hierarkiska vyn av schemat för datauppsättningen visas i den vänstra rutan.

>[!NOTE]
>
>Lär dig hur du får åtkomst till exporterade datauppsättningar för varje objekt i ditt Erbjudandebibliotek i [det här avsnittet](../export-catalog/access-dataset.md).

Här är en lista över alla fält som kan användas i datamängden **[!UICONTROL Decision Object Repository - Decisions]** (tidigare kallad beslutsobjektdatabas - aktiviteter).

<!--A decision (formerly known as offer decision) is used to control the decisioning process. It specifies the filter applied to the total inventory to narrow down offers by topic/category, the placement to narrow down the inventory to those offers that technically fit into the reserved space for the offer and specifies a fallback option should the combined constraints disqualify all available personalization offers.-->

+++ Identifierare

**Fält:**&#x200B;_id
**Titel:** Identifierare
**Beskrivning:** En unik identifierare för posten.
**Typ:** sträng

+++

+++ upplevelse

**Fält:**&#x200B;_upplevelse
**Typ:** objekt

+++

+++ _experience > decisioning

**Fält:** beslut
**Typ:** objekt

+++

+++ _experience > decisioning > conditions

**Fält:** villkor
**Titel:** Villkor
**Beskrivning:** Definierar en uppsättning beslutskriterier där vart och ett innehåller en uppsättning begränsningar.
**Typ:**-matris

+++

+++ _experience > decisioning > conditions > description

**Fält:** beskrivning
**Titel:** Beskrivning
**Beskrivning:** Villkorsbeskrivning. Det används för att förmedla mänskliga, läsbara avsikter om hur eller varför detta kriterium konstruerades och hur det påverkar beslutet.
**Typ:** sträng

+++

+++_experience > decisioning > conditions > optionSelection

**Fält:** optionSelection
**Titel:** Alternativmarkering
**Beskrivning:** Alternativvalet definierar giltigheten/tillämpligheten för alternativ i det här sammanhanget.
**Typ:** objekt

* Beskrivning

  **Fält:** beskrivning
  **Titel:** Beskrivning
  **Beskrivning:** Beskrivning av alternativval. Det används för att förmedla mänskliga läsbara avsikter om hur eller varför det här alternativvalet skapades och/eller vilket alternativ som matchar.
  **Typ:** sträng

* Alternativfilter

  **Fält:** filter
  **Titel:** Alternativfilter
  **Beskrivning:** Referensen till en samlingskvalificerare (tidigare känd som tagg-baserat filter) som matchar alternativ från ett lager med hjälp av deras kopplade samlingskvalificerare. Värdet är URI (@id) för den beslutsregel som refereras. Se schema https://ns.adobe.com/experience/decisioning/filter.
  **Typ:** sträng

* Typ av profilbegränsning

  **Fält:** optionSelectionType
  **Titel:** Profilbegränsningstyp
  **Beskrivning:** Avgör om några begränsningar har angetts och hur begränsningarna uttrycks. Det kan vara via en filterfråga eller genom ett eller flera målgruppsmedlemskap.
  **Typ:** sträng
  **Möjliga värden:** &quot;none&quot; (default), &quot;directList&quot;, &quot;filter&quot;

* Alternativlista

  **Fält:** alternativ
  **Titel:** Alternativlista
  **Beskrivning:** En lista som direkt anger alternativen utan att utvärdera en filterfråga. Du kan antingen ange en alternativlista eller en alternativfilterregel.
  **Typ:**-matris

<!--Missing title under Option List? Desc = An identifier of an decision option entity. The value value refers to an `@id` property of a decision option. Type: string-->

+++

+++_upplevelse > beslut > villkor > placeringar

**Fält:** placeringar
**Titel:** Placeringsbegränsningar
**Beskrivning:** Placeringsbegränsningen anger att det här kriteriet bara gäller för de listade placeringarna. Det är bara när målplaceringen finns i listan `xdm:placements` som alternativet övervägs. Annars hoppas hela beslutskriterierna över. När xdm:placements-listan utelämnas eller är tom, beaktas kriteriet för alla riktade placeringar. De placeringar som anges här innehåller implicita kriterier för alternativvalet. Ett alternativ som ska beaktas måste ha en representation för den avsedda placeringen.
**Typ:**-matris

* Placement-ID

  **Titel:** Placeringsidentifierare
  **Beskrivning:** En referens till en placeringsenhet. Värdet är URI (@id) för placeringen som refereras. Se schema https://ns.adobe.com/experience/decisioning/placement.
  **Typ:** sträng

+++

+++_experience > decisioning > conditions > profileConstraints

**Fält:** profileConstraints
**Titel:** Profilbegränsning
**Beskrivning:** Profilbegränsningen avgör om ett alternativ är tillgängligt för den här profilidentiteten just nu, i det här sammanhanget. Om profilbegränsningen inte behöver ta hänsyn till värden för varje alternativ, d.v.s. det är en skillnad mellan alternativen från alternativmarkeringen, avbryts hela alternativmarkeringen av profilbegränsningen som utvärderas till &quot;false&quot;. Å andra sidan utvärderas en profilbegränsningsregel som tar ett alternativ som parameter för varje kvalificeringsalternativ i alternativvalet.
**Typ:** objekt

+++

+++_experience > decisioning > conditions > profileConstraints > Description

**Fält:** beskrivning
**Titel:** Beskrivning
**Beskrivning:** Profilbegränsningsbeskrivning. Den används för att förmedla mänskliga läsbara avsikter om hur eller varför den här profilbegränsningen konstruerades och/eller vilket alternativ som kommer att inkluderas eller exkluderas av den.
**Typ:** sträng

+++

+++ _experience > decisioning > Criterion > profileConstraints > Eligibility Rule

**Fält:** eligibilityRule
**Titel:** Kvalifikationsregel
**Beskrivning:** En referens till en beslutsregel som utvärderas till true eller false för en given profil och/eller andra angivna kontextuella XDM-objekt. Regeln används för att bestämma om alternativet kvalificerar sig för en viss profil. Värdet är URI (@id) för den beslutsregel som refereras. Se schema https://ns.adobe.com/experience/decisioning/rule.
**Typ:** sträng

+++

+++ _experience > decisioning > conditions > profileConstraints > Profile Constraint Type

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

+++ _experience > decisioning > conditions > profileConstraints > segmentIdentities

**Fält:** segmentIdentities
**Titel:** Segmentidentifierare
**Beskrivning:** Identifierare för målgruppen.
**Typ:**-matris

* Identifierare

  **Fält:**&#x200B;_id
  **Titel:** Identifierare
  **Beskrivning:** Identitet för målgruppen i det relaterade namnområdet.
  **Typ:** sträng

* namespace

  **Fält:**-namnområde
  **Titel:** Namnområde
  **Beskrivning:** Det namnutrymme som är associerat med attributet `xid`.
  **Typ:** objekt
  **Obligatoriskt:** &quot;code&quot;

   * Code

     **Fält:** kod
     **Titel:** Kod
     **Beskrivning:** Koden är en läsbar identifierare för namnutrymmet och kan användas för att begära det tekniska namnområdes-ID som används för bearbetning av identitetsdiagram.
     **Typ:** sträng

* Experience Identifier

  **Fält:** xid
  **Titel:** Upplevelseidentifierare
  **Beskrivning:** I förekommande fall representerar det här värdet en identifierare för korsnamnrymd som är unik för alla identifierare med namnrymd i alla namnrymder.
  **Typ:** sträng

+++

+++_experience > decisioning > regions > rankning

**Fält:** rankning
**Titel:** Information om rankning
**Beskrivning:** Rankning (prioritet). Definierar hur det \&quot;bästa alternativet\&quot; bestäms utifrån beslutskriteriets sammanhang. Bland alla de valda alternativen som uppfyller profilbegränsningarna avgör rankningen vilket eller vilka översta N-alternativ som ska föreslås.
**Typ:** objekt

+++ 

+++_experience > decisioning > conditions > ranking > order

**Fält:** ordning
**Titel:** Orderutvärdering
**Beskrivning:** Utvärdering av en relativ ordning för ett eller flera beslutsalternativ. Alternativ med högre ordningstal markeras över alternativ med lägre ordningstal. De värden som bestäms med den här metoden kan ordnas, men avståndet mellan dem kan inte mätas och varken summor eller produkter kan beräknas. Medianen och läget är de enda måtten på central tendens som kan användas för ordningstal.
**Typ:** objekt

* Poängfunktion

  Funktionen **Fält:**
  **Titel:** Bedömningsfunktion
  **Beskrivning:** En referens till en funktion som beräknar ett numeriskt poängvärde för det här beslutsalternativet. Beslutsalternativen kommer sedan att sorteras (rangordnas) efter den poängen. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/function.
  **Typ:** sträng

* Typ av orderutvärdering*

  **Fält:** orderEvaluationType
  **Titel:** Orderutvärderingstyp
  **Beskrivning:** Anger vilken ordningsutvärderingsmekanism som används, statisk prioritet för beslutsalternativen, en bedömningsfunktion som beräknar ett numeriskt värde för varje alternativ eller en AI-modell som tar emot en lista för att ordna den.
  **Typ:** sträng
  **Möjliga värden:** &quot;static&quot;, &quot;scoringFunction&quot;, &quot;rankingStrategy&quot;

* Rankningsstrategi

  **Fält:** rankingStrategy
  **Titel:** rankningsstrategi
  **Beskrivning:** En referens till en strategi som rangordnar ett beslutsalternativ. Beslutsalternativen returneras i en ordnad lista. Värdet för den här egenskapen är URI (@id) för funktionen som ska anropas med alternativet on i taget. Se schema https://ns.adobe.com/experience/decisioning/rankingStrategy.
  **Typ:** sträng

+++

+++ _experience > decisioning > conditions > ranking > Priority

**Fält:** prioritet
**Titel:** Prioritet
**Beskrivning:** Prioriteten för ett enskilt beslutsalternativ i förhållande till alla andra alternativ. Alternativ som ingen orderfunktion har angetts för prioriteras med den här egenskapen. Alternativ med högre prioritetsvärden markeras före alternativ med lägre prioritet. Om två eller flera kvalificerande alternativ har det högsta prioritetsvärdet, väljs ett på ett enhetligt slumpmässigt sätt och används för beslutsförslaget.
**Typ:** heltal
**Minimivärde:** 0
**Standardvärde:** 0

+++

+++ _experience > decisioning > Activity End Date and Time

**Fält:** endTime
**Titel:** Slutdatum och tid för aktiviteten
**Beskrivning:** Slutdatum och sluttid för beslut (tidigare kallat aktivitet). Egenskapen har semantiken för schema.orgs endTime-egenskap definierad på https://schema.org/Action.
**Typ:** sträng

+++

+++ _experience > decisioning > Fallback Option

**Fält:** reserv
**Titel:** Alternativ för reserv
**Beskrivning:** Referensen till ett reservalternativ som används vid beslut i det här beslutet berättigar inte till något av de vanliga alternativen (detta inträffar vanligtvis när hårda begränsningar används). Värdet är URI (@id) för det reservalternativ som refereras.
**Typ:** sträng

+++

+++ _experience > Decision > Activity Name

**Fält:** namn
**Titel:** Aktivitetsnamn
**Beskrivning:** Beslutsnamn (tidigare kallat aktivitet) som visas i olika användargränssnitt.
**Typ:** sträng

+++

+++_experience > decisioning > Activity Start Date and Time

**Fält:** startTime
**Titel:** Startdatum och -tid för aktivitet
**Beskrivning:** Startdatum och sluttid för beslut (tidigare kallat aktivitet). Egenskapen har semantiken för schema.orgs startTime-egenskap definierad på https://schema.org/Action.
**Typ:** sträng

+++

+++ repo

**Fält:**&#x200B;_repo
**Typ:** objekt

+++

+++ _repo > Activity ETag

**Fält:**-tagg
**Titel:** Aktivitets-ETag
**Beskrivning:** Ändringen som beslutsobjektet (tidigare kallat activity) var när ögonblicksbilden togs.
**Typ:** sträng

+++
