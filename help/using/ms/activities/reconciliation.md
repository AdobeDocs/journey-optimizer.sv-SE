---
solution: Journey Optimizer
product: journey optimizer
title: Använd avstämningsaktiviteten
description: Lär dig använda avstämningsaktiviteten i en orkestrerad kampanj
hide: true
hidefromtoc: true
exl-id: 0d5cfffe-bc6c-40bc-b3e1-5b44368ac76f
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 9%

---

# Avstämning {#reconciliation}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation"
>title="Avstämningsaktivitet"
>abstract="Aktiviteten **Avstämning** är en **målaktivitet** som gör att du kan definiera länken mellan Adobe Journey Optimizer och data i en arbetstabell."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_field"
>title="Avstämningsmarkeringsfält"
>abstract="Avstämningsmarkeringsfält"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_condition"
>title="Avstämning skapa villkor"
>abstract="Avstämning skapa villkor"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_complement"
>title="Avstämning genererar komplementtal"
>abstract="Avstämning genererar komplementtal"

Aktiviteten **Avstämning** är en **målaktivitet** som gör att du kan definiera länken mellan data i Adobe Journey Optimizer och data i en arbetstabell, till exempel data som lästs in från en extern fil.

## Bästa praxis {#reconciliation-best-practices}

Med aktiviteten **Enrichment** kan du definiera ytterligare data som ska bearbetas i din samordnade kampanj (du kan använda en **Enrichment**-aktivitet för att kombinera data från flera uppsättningar eller för att skapa länkar till en tillfällig resurs), men med aktiviteten **Avstämning** kan du länka oidentifierade data till befintliga resurser.

>[!NOTE]
>Avstämningsåtgärden innebär att data för de länkade dimensionerna redan finns i databasen.  Om du till exempel importerar en inköpsfil som visar vilken produkt som köptes vid en viss tidpunkt, av en viss klient och så vidare, så måste produkten och klienten redan finnas i databasen.

## Konfigurera avstämningsaktiviteten {#reconciliation-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_targeting"
>title="Måldimension"
>abstract="Välj den nya måldimensionen. Med en dimension kan du definiera målpopulationen: mottagare, appprenumeranter, operatorer, prenumeranter osv. Som standard är den aktuella måldimensionen markerad."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_rules"
>title="Avstämningsregler"
>abstract="Välj avstämningsregler som ska användas för dedupliceringen. Om du vill använda attribut markerar du alternativet **Enkla attribut** och väljer käll- och målfälten. Om du vill skapa ett eget avstämningsvillkor med frågemodelleraren väljer du alternativet **Avancerade avstämningsvillkor** ."
>additional-url="https://experienceleague.adobe.com/en/docs/campaign-web/v8/query-database/query-modeler-overview" text="Arbeta med frågemodelleraren"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_targeting_selection"
>title="Välj måldimension"
>abstract="Välj måldimension för inkommande data som ska förenas med."
>additional-url="https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/gs-audiences-recipients.html#targeting-dimensions" text="Måldimensioner"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_keep_unreconciled_data"
>title="Behåll ej avstämda data"
>abstract="Som standard behålls ej avstämda data i den utgående övergången och är tillgängliga i arbetstabellen för framtida bruk. Om du vill ta bort ej avstämda data inaktiverar du alternativet **Behåll ej avstämda data**."

>[!CONTEXTUALHELP]
>id="ajo_orchestration_reconciliation_attribute"
>title="Avstämningsattribut"
>abstract="Markera attributet som ska användas för att avstämma data och klicka på Bekräfta."

Så här konfigurerar du aktiviteten **Avstämning**:

1. Lägg till en **avstämningsaktivitet** i din samordnade kampanj.

1. Välj den nya måldimensionen. Med en dimension kan du definiera målpopulationen: mottagare, appprenumeranter, operatorer, prenumeranter osv.

1. Välj de fält som ska användas för avstämningen. Du kan använda ett eller flera avstämningskriterier.

   1. Om du vill använda attribut för att stämma av data markerar du alternativet **Enkla attribut**. I fältet **Source** visas de fält som är tillgängliga i indataövergången och som ska avstämas. Fältet **Mål** motsvarar fälten i den valda måldimensionen. Data avstäms när källan och målet är lika. Markera till exempel fälten **E-post** för att ta bort dubbletter av profiler baserat på deras e-postadress.

      Om du vill lägga till ytterligare avstämningsvillkor klickar du på knappen **Lägg till regel** . Om flera kopplingsvillkor anges måste ALLA verifieras så att data kan länkas ihop.

      ![](../assets/workflow-reconciliation-criteria.png)

   1. Om du vill använda andra attribut för att stämma av data väljer du alternativet **Avancerade avstämningsvillkor** . Du kan sedan skapa ett eget avstämningsvillkor med frågemodelleraren.

1. Du kan filtrera data för avstämning med knappen **Skapa filter** . Detta gör att du kan skapa ett anpassat villkor med hjälp av frågemodelleraren.

Som standard lagras ej avstämda data i den utgående övergången och är tillgängliga i arbetsboken för framtida bruk. Om du vill ta bort ej avstämda data inaktiverar du alternativet **Behåll ej avstämda data**.

## Exempel {#reconciliation-example}

I följande exempel visas en strukturerad kampanj som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter. Den består av följande verksamheter:

Den samordnade kampanjen har följande utformning:

![](../assets/workflow-reconciliation-sample-1.0.png)


Den har följande aktiviteter:

* En [Läs in fil](load-file.md)-aktivitet överför en fil som innehåller profildata som har extraherats från ett externt verktyg.

  Exempel:

  ```
  lastname;firstname;email;birthdate;
  JACKMAN;Megan;megan.jackman@testmail.com;07/08/1975;
  PHILLIPS;Edward;phillips@testmail.com;09/03/1986;
  WEAVER;Justin;justin_w@testmail.com;11/15/1990;
  MARTIN;Babe;babeth_martin@testmail.net;11/25/1964;
  REESE;Richard;rreese@testmail.com;02/08/1987;
  ```

* En **avstämningsaktivitet** som identifierar inkommande data som profiler, genom att använda fälten **email** och **Date of born** som avstämningsvillkor.

  ![](../assets/workflow-reconciliation-sample-1.1.png)

* En [Spara målgruppsaktivitet](save-audience.md) om du vill skapa en ny målgrupp baserat på dessa uppdateringar. Du kan också ersätta aktiviteten **Spara målgrupp** med en **End**-aktivitet om ingen specifik målgrupp behöver skapas eller uppdateras. Mottagarprofiler uppdateras i alla fall när du kör den orkestrerade kampanjen.
