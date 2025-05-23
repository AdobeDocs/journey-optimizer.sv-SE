---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Testa i orkestrerade kampanjer
description: Lär dig använda aktiviteten Testa
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: edd70849-0a21-45f2-91f3-4774a0cad9dd
source-git-commit: 3d33d0bdbaf5b56a68d4ea708ce023c6aaae4811
workflow-type: tm+mt
source-wordcount: '362'
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

Aktiviteten **Test** är en **Flödeskontroll**-aktivitet. Det gör att du kan aktivera övergångar baserat på angivna villkor.

## Konfigurera aktiviteten Testa {#test-configuration}

Följ de här stegen för att konfigurera aktiviteten **Test**:

1. Lägg till en **Test**-aktivitet i din samordnade kampanj.

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
