---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Uppdatera data i samordnade kampanjer
description: Lär dig använda aktiviteten Uppdatera data
badge: label="Alpha"
hide: true
hidefromtoc: true
exl-id: 68e7c929-5f07-4d5a-9831-690e071947f8
source-git-commit: bdc584c1aae0c735d81dfc95e11f96f755bea26a
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 12%

---

# Uppdatera data {#update-data}

Aktiviteten **Uppdatera data** är en **datahanteringsaktivitet**. Det gör att du kan utföra en massuppdatering på fält i databasen. Flera alternativ gör att du kan anpassa datauppdateringen.

<!--
The **Operation type** field lets you choose the process to be carried out on the data in the database. Select the first option to add data or update (it if it has already been added). You can also only add data, only update data, or delete data. Select the **Update and merge collections** to select a primary record to link duplicates to, and delete those duplicates safely

Specify how to identify the records in the database: if data relate to an existing targeting dimension, select the **Using the targeting dimension** option and select the targeting dimension and fields to update. Otherwise, specify one or more custom links to identify the data in the database, or direct use of reconciliation keys.

Select the fields to update and reconciliation settings. You can use the **Auto-mapping** option to automatically identify the fields to be updated.

The **Advanced options** section let you specify additional settings to manage data and duplicates.

Toggle the **Generate an outbound transition** option to add an outbound transition that will be activated at the end of the execution of the **Update data** activity. The update generally marks the end of a targeting workflow and therefore the option is not activated by default.

Toggle the **Generate an outbound transition for rejects** option to add an outbound transition containing records that have not been correctly processed after the update (for example if there is a duplicate). The update generally marks the end of a targeting workflow and therefore the option is not activated by default.
-->

## Konfigurera aktiviteten Uppdatera data{#update-data-configuration}

Om du vill konfigurera aktiviteten **Uppdatera data** börjar du med att lägga till aktiviteten till din samordnade kampanj och definierar en etikett.

![](../assets/workflow-update-data.png)

### Åtgärdstyp

I fältet **Åtgärdstyp** kan du välja vilken process som ska utföras på data i databasen:

* **Infoga eller uppdatera**: infoga data eller uppdatera dem om posterna redan finns i databasen.
* **Infoga**: infoga endast data. Posterna som redan finns uppdateras inte. Om avstämningskriterier definieras läggs endast icke avstämda poster till.
* **Uppdatera**: Uppdatera data för de poster som redan finns i databasen.
* **Ta bort**: ta bort data.

I fältet **Batchstorlek** kan du välja antalet inkommande övergångselement som ska uppdateras. Om du till exempel anger 500 uppdateras de första 500 posterna som behandlas.

### Registrerings-ID

I det här avsnittet kan du ange hur posterna i databasen ska identifieras:

* Om dataposter relaterar till en befintlig måldimension väljer du alternativet **Använda måldimensionen** och väljer det i fältet **Måldimension att uppdatera**.
* Du kan också välja **Använda anpassade länkar** och ange en eller flera länkar som gör att data i databasen kan identifieras
* Om den valda åtgärdstypen kräver en uppdatering måste du använda alternativet **Använda avstämningsregler**.

### Fält som ska uppdateras

I avsnittet **Fält som ska uppdateras** lägger du till de fält som uppdateringen ska tillämpas på och, om det behövs, lägger till villkor så att uppdateringen utförs. Om du vill göra det använder du fältet **Ta hänsyn till om**. Villkoren tillämpas i en efter en beroende på listordningen. Använd pilarna till höger för att ändra uppdateringsordningen. Du kan använda samma målfält flera gånger.

Du kan länka fält automatiskt med knappen **Automatisk mappning**. Automatisk länkning identifierar fält med samma namn.

Under en **Infoga- eller uppdateringsåtgärd** kan du välja en åtgärd som ska användas för varje fält separat. Det gör du genom att markera det värde du vill ha i fältet **Åtgärdstyp**.

### Avancerade alternativ

Med de **avancerade alternativen** kan du ange ytterligare alternativ som du kan använda för att uppdatera data och hantera dubbletter.

<!--
* **Disable automatic key management**
* **Disable audit**
* **Empty the destination value if the source value is empty**
* **Update all columns with matching names**
* **Ignore records which concern the same target**: only the first in the list of expressions will be considered
-->

De två sista alternativen gör att du kan utföra specifika åtgärder:

* **Generera en utgående övergång**: skapar en utgående övergång som aktiveras i slutet av körningen. Uppdateringen signalerar vanligtvis slutet på en riktade, iscensatt kampanj och alternativet är därför inte aktiverat som standard.

* **Generera en utgående övergång för projekten**: skapar en utgående övergång som innehåller poster som inte har bearbetats korrekt efter uppdateringen (till exempel om det finns en dubblett). Uppdateringen markerar vanligtvis slutet på en riktade, iscensatt kampanj och därför är alternativet inte aktiverat som standard.
