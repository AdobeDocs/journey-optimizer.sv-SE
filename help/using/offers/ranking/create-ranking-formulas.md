---
title: Rankningsformler
description: Lär dig hur du skapar formler för att rangordna erbjudanden
badge: label="Äldre" type="Informative"
feature: Ranking, Decision Management
topic: Integrations
role: User
level: Intermediate
mini-toc-levels: 1
exl-id: 8bc808da-4796-4767-9433-71f1f2f0a432
source-git-commit: 87f3da0a1d73f9aa26c7420d260778286bacdf0c
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 0%

---

# Rankningsformler {#create-ranking-formulas}

## Om rankningsformler {#about-ranking-formulas}

**Rankningsformler** gör att du kan definiera regler som avgör vilket erbjudande som ska presenteras först för en viss placering, i stället för att ta hänsyn till offertens prioritetspoäng.

Rankningsformler uttrycks i **PQL-syntax** och kan utnyttja profilattribut, kontextdata och attribut. Mer information om hur du använder PQL-syntaxen finns i [dedikerad dokumentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=sv-SE).

När en rankningsformel har skapats kan du tilldela den till en placering i ett beslut. Mer information finns i [Konfigurera erbjudandeval i beslut](../offer-activities/configure-offer-selection.md).

## Skapa en rankningsformel {#create-ranking-formula}

Så här skapar du en rankningsformel:

1. Gå till menyn **[!UICONTROL Components]** och välj fliken **[!UICONTROL Ranking]**. Fliken **[!UICONTROL Formulas]** är markerad som standard. Listan med formler som skapats tidigare visas.

   ![](../assets/rankings-list.png)

1. Klicka på **[!UICONTROL Create ranking]** om du vill skapa en ny rankningsformel.

   ![](../assets/ranking-create-formula.png)

1. Ange formelnamn, beskrivning och formel.

   I det här exemplet vill vi prioritera alla erbjudanden med attributet&quot;hot&quot; om vädret är varmt. För att göra detta skickades **contextData.wall=hot** i beslutsanropet. [Lär dig arbeta med kontextdata](../context-data.md)

   ![](../assets/ranking-syntax.png)

   >[!IMPORTANT]
   >
   >När du skapar en rankningsformel stöds inte möjligheten att gå tillbaka till en tidigare tidsperiod. Om du till exempel anger en upplevelsehändelse som inträffade under den sista månaden som en komponent i formeln. Alla försök att inkludera en uppslagsperiod när formeln skapas kommer att utlösa ett fel när den sparas.

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

### Öka erbjudandena baserat på kundernas benägenhet att köpa den produkt som erbjuds

Ni kan höja poängen för ett erbjudande baserat på kundens benägenhetspoäng.

I det här exemplet är instanstenanten *_salesvelocity* och profilschemat innehåller ett intervall med poäng lagrade i en array:

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

### Öka erbjudanden baserat på kontextdata {#context-data}

Med [!DNL Journey Optimizer] kan du öka vissa erbjudanden baserat på de kontextdata som skickas i anropet. Om till exempel `contextData.weather=hot` skickas måste prioriteten för alla erbjudanden med `attribute=hot` öka. Detaljerad information om hur du skickar kontextdata med API:erna **Edge Decisioning** och **Decisioning** finns i [det här avsnittet](../context-data.md)

Observera att när du använder API:t **Decisioning** läggs kontextdata till i profilelementet i begärandetexten, som i exemplet nedan.

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

Här är exempel som illustrerar hur man använder kontextdata i rankningsformler för att höja offertens prioritet. Expandera varje avsnitt för att få information om rangordningens syntax.

>[!NOTE]
>
>Ersätt `<OrgID>` med ditt organisationskontor-ID i exemplen för Edge Decihering API.

+++Öka prioriteten med 10 om kanalen från kontextdata matchar kundens önskade kanal

>[!BEGINTABS]

>[!TAB Besluts-API]

`if (@{_xdm.context.additionalParameters;version=1}.channel.isNotNull() and @{_xdm.context.additionalParameters;version=1}.channel.equals(_abcMobile.preferredChannel), offer.rank.priority + 10, offer.rank.priority)`

>[!TAB Edge Decisioning API]

`if (xEvent.<OrgID>.channel.isNotNull() and xEvent.<OrgID>.channel.equals(_abcMobile.preferredChannel), offer.rank.priority + 10, offer.rank.priority)`

>[!ENDTABS]

+++

+++Prioritera alla erbjudanden med&quot;attribute=hot&quot; om&quot;contextData.wall=hot&quot; skickas i anropet.

>[!BEGINTABS]

>[!TAB Besluts-API]

`if (@{_xdm.context.additionalParameters;version=1}.weather.isNotNull() and offer.characteristics.get("weather")=@{_xdm.context.additionalParameters;version=1}.weather, offer.rank.priority + 5, offer.rank.priority)`

>[!TAB Edge Decisioning API]

`if (xEvent.<OrgID>.weather.isNotNull() and offer.characteristics.get("weather")=xEvent.<OrgID>.weather, offer.rank.priority + 5, offer.rank.priority)`

>[!ENDTABS]

+++

+++Ökning av innehållets ursprung

>[!BEGINTABS]

>[!TAB Besluts-API]

`if (@{_xdm.context.additionalParameters;version=1}.contentorigin.isNotNull() and offer.characteristics.contentorigin=@{_xdm.context.additionalParameters;version=1}.contentorigin, offer.rank.priority * 100, offer.rank.priority)`

>[!TAB Edge Decisioning API]

`if (xEvent.<OrgID>.contentorigin.isNotNull() and offer.characteristics.contentorigin=xEvent.<OrgID>.contentorigin, offer.rank.priority * 100, offer.rank.priority)`

>[!ENDTABS]

+++

+++Väderförbättring

>[!BEGINTABS]

>[!TAB Besluts-API]

`if (@{_xdm.context.additionalParameters;version=1}.weather.isNotNull() and offer.characteristics.weather=@{_xdm.context.additionalParameters;version=1}.weather, offer.rank.priority * offer.characteristics.scoringBoost, offer.rank.priority)`

>[!TAB Edge Decisioning API]

`if (xEvent.<OrgID>.weather.isNotNull() and offer.characteristics.weather=xEvent.<OrgID>.weather, offer.rank.priority * offer.characteristics.scoringBoost, offer.rank.priority)`

>[!ENDTABS]

+++
