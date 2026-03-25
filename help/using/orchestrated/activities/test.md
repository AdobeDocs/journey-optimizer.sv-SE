---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Test i orkestrerade kampanjer
description: Lär dig använda aktiviteten Testa
exl-id: edd70849-0a21-45f2-91f3-4774a0cad9dd
version: Campaign Orchestration
source-git-commit: b6b74e357029f4924f9699c05af3a0fcd7fcefd6
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 20%

---


# Test {#test}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_test"
>title="Testaktivitet"
>abstract="Aktiviteten **Test** är en **Flödeskontroll**-aktivitet. Det gör att du kan aktivera övergångar baserat på angivna villkor."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_test_conditions"
>title="Villkor"
>abstract="Aktiviteten **Test** kan ha flera utdataövergångar. Under körningen av orkestrerade kampanjer testas varje villkor sekventiellt tills ett av dem uppfylls. Om inget av villkoren uppfylls fortsätter den orkestrerade kampanjen längs sökvägen för **[!UICONTROL Default condition]**. Om inget standardvillkor aktiveras stoppas den orkestrerade kampanjen nu."

Aktiviteten **[!UICONTROL Test]** är en **[!UICONTROL Flow control]**-aktivitet. Använd det för att förgrena kampanjflödet genom att aktivera olika övergångar beroende på vilka villkor du definierar. Varje villkor kan utvärdera data från den inkommande övergången och du kan välja vilken övergång som körs först i den ordning som villkoren utvärderas i.

## Konfigurera aktiviteten Testa {#test-configuration}

Så här konfigurerar du aktiviteten **[!UICONTROL Test]**:

1. Släpp en **[!UICONTROL Test]**-aktivitet på arbetsytan för orkestrerade kampanjer.

1. Som standard ger aktiviteten ett booleskt test: när villkoret &quot;Sant&quot; är uppfyllt aktiveras övergången, annars aktiveras övergången &quot;Falskt&quot; (standard).

   ![](../assets/test-1.png)

1. Definiera villkoret för en övergång genom att fylla i följande fält:

   * **Etikett**: Ett namn för övergången så att du kan identifiera den på arbetsytan.

   * **Villkorstyp**: De data som ska utvärderas som standard, populationsantal.

   * **Operator**: Den jämförelse som ska användas, t.ex. lika med, större än, mindre än. Listan med operatorer beror på villkorstypens datatyp.

   * **Värde**: Värdet som villkorstypen ska jämföras med.

   ![](../assets/test-2.png)

1. Om du vill förgrena fler än två resultat klickar du på **[!UICONTROL Add condition]** och definierar en etikett och ett villkor för varje ytterligare övergång.

1. Vid körning utvärderar kampanjen villkoren i ordning och följer den första som matchar. När inga villkor matchar följer körningen **[!UICONTROL Default condition]** om ett villkor har angetts, annars stannar kampanjen vid aktiviteten **[!UICONTROL Test]**.

## Exempel {#example}

I det här exemplet aktiveras olika övergångar baserat på antalet profiler som en **[!UICONTROL Build audience]**-aktivitet har som mål. Villkoren utvärderas i ordning. Den sista övergången är standardövergång och används när inga tidigare villkor matchar.

* Om fler än 10 000 profiler används skickas ett e-postmeddelande.
* Standard (inga villkor matchade): när antalet är 10 000 eller färre dirigeras populationen till en&quot;inte kontakt&quot;-övergång.

![](../assets/workflow-test-example.png)
