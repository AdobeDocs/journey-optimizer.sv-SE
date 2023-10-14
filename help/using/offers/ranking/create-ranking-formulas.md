---
title: Rankningsformler
description: Lär dig hur du skapar formler för att rangordna erbjudanden
feature: Ranking Formulas, Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 8bc808da-4796-4767-9433-71f1f2f0a432
source-git-commit: 3f96cc0037b5bcdb2ce94e2721b02ba13b3cff36
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# Rankningsformler {#create-ranking-formulas}

## Om rankningsformler {#about-ranking-formulas}

**Rankningsformler** gör det möjligt att definiera regler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att ta hänsyn till offertens prioritetspoäng.

Rankningsformler uttrycks i **PQL-syntax** och kan utnyttja profilattribut, kontextdata och erbjuda attribut. Mer information om hur du använder PQL-syntaxen finns i [dedikerad dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html).

När en rankningsformel har skapats kan du tilldela den till en placering i ett beslut. Mer information finns i [Konfigurera urval av erbjudanden i beslut](../offer-activities/configure-offer-selection.md).

## Skapa en rankningsformel {#create-ranking-formula}

Så här skapar du en rankningsformel:

1. Öppna **[!UICONTROL Components]** väljer du **[!UICONTROL Ranking]** -fliken. The **[!UICONTROL Formulas]** -fliken är markerad som standard. Listan med formler som skapats tidigare visas.

   ![](../assets/rankings-list.png)

1. Klicka **[!UICONTROL Create ranking]** för att skapa en ny rankningsformel.

   ![](../assets/ranking-create-formula.png)

1. Ange formelnamn, beskrivning och formel.

   I det här exemplet vill vi prioritera alla erbjudanden med attributet&quot;hot&quot; om vädret är varmt. För att göra detta **contextData.west=hot** har skickats i beslutsanropet.

   ![](../assets/ranking-syntax.png)

1. Klicka på **[!UICONTROL Save]**. Din rankningsformel skapas. Du kan välja den i listan för att få information och redigera eller ta bort den.

   Det är nu klart att användas i ett beslut om att rangordna kvalificerade erbjudanden för en placering (se [Konfigurera urval av erbjudanden i beslut](../offer-activities/configure-offer-selection.md)).

   ![](../assets/ranking-formula-created.png)

## Exempel på rankningsformler {#ranking-formula-examples}

Du kan skapa många olika rankningsformler efter behov. Nedan finns några exempel.

<!--
Boost by offer ID

Boost the priority of an offer with the offer ID *xcore:personalized-offer:13d213cd4cb328ec* by 5.

**Ranking formula:**

```
if( offer._id = "xcore:personalized-offer:13d213cd4cb328ec", offer.rank.priority + 5, offer.rank.priority)
```

Change the offer priority based on a certain profile attribute

Set the offer priority to 30 for offer *xcore:personalized-offer:13d213cd4cb328ec* if the user lives in the city of Bondi.

**Ranking formula:**

```
if( offer._id = "xcore:personalized-offer:13d213cd4cb328ec" and homeAddress.city.equals("Bondi", false), 30, offer.rank.priority)
```

Boost multiple offers by offer ID based on the presence of a profile's audience membership

Boost the priority of offers based on whether the user is a member of a priority audience, which is configured as an attribute in the offer.

**Ranking formula:**

```
if( segmentMembership.get("ups").get(offer.characteristics.get("prioritySegmentId")).status in (["realized","existing"]), offer.rank.priority + 10, offer.rank.priority)
```
-->

### Öka erbjudanden med vissa attribut baserade på profilattribut

Om profilen finns i den stad som motsvarar erbjudandet fördubblas prioriteten för alla erbjudanden i den staden.

**Rankningsformel:**

```
if( offer.characteristics.get("city") = homeAddress.city, offer.rank.priority * 2, offer.rank.priority)
```

### Förbättra erbjudanden där slutdatumet är mindre än 24 timmar från och med nu

**Rankningsformel:**

```
if( offer.selectionConstraint.endDate occurs <= 24 hours after now, offer.rank.priority * 3, offer.rank.priority)
```

### Förbättra erbjudanden med vissa attribut baserade på kontextdata

Öka vissa erbjudanden baserat på de kontextdata som skickas i beslutsanropet. Om `contextData.weather=hot` har skickats in i beslutsanropet, prioriteten för alla erbjudanden med `attribute=hot` måste förstärkas.

**Rankningsformel:**

```
if (@{_xdm.context.additionalParameters;version=1}.weather.isNotNull()
and offer.characteristics.get("weather")=@{_xdm.context.additionalParameters;version=1}.weather, offer.rank.priority + 5, offer.rank.priority)
```

Observera att när du använder API:t för beslutsfattande läggs kontextdata till i elementet profile i begärandebrödtexten, som i exemplet nedan.

**Fragment från begärandetext:**

```
"xdm:profiles": [
{
    "xdm:identityMap": {
        "crmid": [
            {
            "xdm:id": "CRMID1"
            }
        ]
    },
    "xdm:contextData": [
        {
            "@type":"_xdm.context.additionalParameters;version=1",
            "xdm:data":{
                "xdm:weather":"hot"
            }
        }
    ]
 }],
```

### Öka erbjudandena baserat på kundernas benägenhet att köpa den produkt som erbjuds

Ni kan höja poängen för ett erbjudande baserat på kundens benägenhetspoäng.

I det här exemplet är instansen tenant *_salesvelocity* och profilschemat innehåller ett intervall med bakgrundsmusik som lagras i en array:

![](../assets/ranking-example-schema.png)

Med detta i åtanke för en profil som:

```
{"_salesvelocity": {"individualScoring": [
                    {"core": {
                            "category":"insurance",
                            "propensityScore": 96.9
                        }},
                    {"core": {
                            "category":"personalLoan",
                            "propensityScore": 45.3
                        }},
                    {"core": {
                            "category":"creditCard",
                            "propensityScore": 78.1
                        }}
                    ]}
}
```

Erbjudandena skulle innehålla ett attribut för *propensityType* som matchar kategorin från poängen:

![](../assets/ranking-example-propensityType.png)

Din rankningsformel kan sedan ange prioriteten för varje erbjudande som ska vara lika med kunderna *propensityScore* för *propensityType*. Om ingen poäng hittas, använd den statiska prioriteten som angetts i erbjudandet:

```
let score = (select _Individual_Scoring1 from _salesvelocity.individualScoring
             where _Individual_Scoring1.core.category.equals(offer.characteristics.get("propensityType"), false)).head().core.propensityScore
in if(score.isNotNull(), score, offer.rank.priority)
```
