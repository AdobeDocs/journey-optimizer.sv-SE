---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Testa i orkestrerade kampanjer
description: Lär dig använda aktiviteten Testa
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: edd70849-0a21-45f2-91f3-4774a0cad9dd
source-git-commit: 6439be00315dfde7ab385d7f848b7031d95060f4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Test {#test}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_test"
>title="Testaktivitet"
>abstract="Aktiviteten **Test** är en **Flödeskontroll**-aktivitet. Det gör att du kan aktivera övergångar baserat på angivna villkor."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_test_conditions"
>title="Villkor"
>abstract="Aktiviteten **Test** kan ha flera utdataövergångar. Under genomförande av samordnade kampanjer testas varje villkor sekventiellt tills ett av dem uppfylls. Om inget av villkoren uppfylls fortsätter den orkestrerade kampanjen längs sökvägen för **[!UICONTROL Default condition]**. Om inget standardvillkor aktiveras stoppas den orkestrerade kampanjen nu."

+++ Innehållsförteckning

| Välkommen till samordnade kampanjer | Starta din första samordnade kampanj | Fråga databasen | Ochestrerade kampanjaktiviteter |
|---|---|---|---|
| [Kom igång med samordnade kampanjer](gs-orchestrated-campaigns.md)<br/><br/>[Konfigurationssteg](configuration-steps.md)<br/><br/>[Få åtkomst till och hantera samordnade kampanjer](access-manage-orchestrated-campaigns.md) | [Viktiga steg för att skapa samordnade kampanjer](gs-campaign-creation.md)<br/><br/>[Skapa och schemalägg kampanjen](create-orchestrated-campaign.md)<br/><br/>[Organisera aktiviteter](orchestrate-activities.md)<br/><br/><b>[Starta och övervaka kampanjen](start-monitor-campaigns.md)</b><br/><br/>[Rapportera](reporting-campaigns.md) | [Arbeta med regelbyggaren](orchestrated-rule-builder.md)<br/><br/>[Bygg din första fråga](build-query.md)<br/><br/>[Redigera uttryck](edit-expressions.md)<br/><br/>[Återmarknadsföring](retarget.md) | [Kom igång med aktiviteter](activities/about-activities.md)<br/><br/>Aktiviteter:<br/>[And-join](activities/and-join.md) - [Bygg målgrupp](activities/build-audience.md) - [Ändra dimension](activities/change-dimension.md) - [Kanalaktiviteter](activities/channels.md) - [Kombinera](activities/combine.md) - [Deduplicering](activities/deduplication.md) - [Enrichment](activities/enrichment.md) - [Fork](activities/fork.md)  - [Avstämning](activities/reconciliation.md) - [Spara målgrupp](save-audience.md) - [Dela](activities/split.md) - [Vänta](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

Aktiviteten **[!UICONTROL Test]** är en **[!UICONTROL Flow control]**-aktivitet. Det gör att du kan aktivera övergångar baserat på angivna villkor.

## Konfigurera aktiviteten Testa {#test-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Test]**:

1. Lägg till en **[!UICONTROL Test]**-aktivitet i din samordnade kampanj.

1. Som standard visar aktiviteten **[!UICONTROL Test]** ett enkelt booleskt test. Om villkoret som definieras i övergången &quot;Sant&quot; är uppfyllt aktiveras den här övergången. Annars aktiveras standardövergången &quot;Falskt&quot;.

1. Klicka på ikonen **[!UICONTROL Open personalization dialog]** om du vill konfigurera villkoret som är kopplat till en övergång. Använd uttrycksredigeraren för att definiera de regler som krävs för att aktivera den här övergången. Du kan också utnyttja händelsevariabler, villkor och datum/tid-funktioner.

   Du kan dessutom ändra fältet **[!UICONTROL Label]** för att anpassa övergångens namn på den orkestrerade kampanjarbetsytan.

   ![](../assets/workflow-test-default.png)

1. Du kan lägga till flera utdataövergångar i en **[!UICONTROL Test]**-aktivitet. Det gör du genom att klicka på knappen **[!UICONTROL Add condition]** och konfigurera etiketten och tillhörande villkor för varje övergång.
v
1. Under genomförande av samordnade kampanjer testas varje villkor sekventiellt tills ett av dem uppfylls. Om inga villkor uppfylls fortsätter de orkestrerade kampanjerna längs sökvägen för **[!UICONTROL Default condition]**. Om inget standardvillkor är aktiverat stoppas arbetsflödena nu.

## Exempel {#example}

I det här exemplet aktiveras olika övergångar baserat på antalet profiler som en **[!UICONTROL Build audience]**-aktivitet har som mål:

* Om fler än 10 000 profiler används skickas ett e-postmeddelande.
* För 1 000 till 10 000 profiler skickas ett SMS.
* Om målprofilerna ligger under 1 000 dirigeras de till en&quot;inte kontakt&quot;-övergång.

![](../assets/workflow-test-example.png)

För att göra detta har händelsevariabeln `vars.recCount` utnyttjats i villkoren för e-post och sms för att räkna antalet målprofiler och aktivera lämplig övergång.

![](../assets/workflow-test-example-config.png)
