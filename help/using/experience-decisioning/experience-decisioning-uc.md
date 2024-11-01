---
title: Användningsfall vid beslut
description: Lär dig hur du skapar beslut med hjälp av experiment med den kodbaserade kanalen
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate, Experienced
badge: label="Begränsad tillgänglighet"
source-git-commit: ac8ccb52bd16a26c14dea148f989256e28170765
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 6%

---

# Användningsfall vid beslut {#experience-decisioning-uc}

I det här fallet definierar ni två leveransbehandlingar som var och en innehåller olika beslutsprinciper för att mäta vilken som fungerar bäst för målgruppen.

## Skapa artiklar och strategier

Först måste du skapa objekt, gruppera dem i samlingar, ställa in regler och rangordningsmetoder. Med dessa element kan du skapa urvalsstrategier.

1. Navigera till **[!UICONTROL Decisioning]** > **[!UICONTROL  Catalogs]** och skapa flera erbjudandeobjekt. Ange begränsningar med målgrupper eller regler för att begränsa varje objekt till enbart specifika profiler. [Läs mer](items.md)

   <!--
   1. From the items list, click the **[!UICONTROL Edit schema]** button  and edit the custom attributes if needed. [Learn how to work with catalogs](catalogs.md)-->

1. Skapa **samlingar** för att kategorisera och gruppera dina beslutsobjekt enligt dina önskemål. [Läs mer](collections.md)

1. Skapa **beslutsregler** för att avgöra till vilka ett beslutsobjekt kan visas. [Läs mer](rules.md)

1. Skapa **rankningsmetoder** och tillämpa dem inom beslutsstrategier för att fastställa prioritetsordningen för val av beslutsobjekt. [Läs mer](ranking.md)

1. Bygg **urvalsstrategier** som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsobjekt som passar för visning i profiler. [Läs mer](selection-strategies.md)

## Skapa beslutsprofiler

Om du vill presentera det bästa dynamiska erbjudandet och upplevelsen för besökarna på din webbplats eller i din mobilapp lägger du till en beslutspolicy i en kodbaserad kampanj.

Definiera två leveransbehandlingar som var och en innehåller olika beslutspolicyer.

1. Skapa en kampanj och välj åtgärden **[!UICONTROL Code-base experience]**. [Läs mer](../code-based/create-code-based.md)

1. Klicka på **[!UICONTROL Create experiment]** på kampanjsammanfattningssidan för att börja konfigurera ditt innehållsexperiment. [Läs mer](../content-management/content-experiment.md)

1. Välj ikonen **[!UICONTROL Decisions]**, klicka på **[!UICONTROL Create a decision]** och fyll i beslutsinformationen. [Läs mer](create-decision.md)

   ![](assets/decision-code-based-create.png)

1. Definiera urvalsstrategierna för ditt beslut. Klicka på **[!UICONTROL Add strategy]**.

1. Klicka på **[!UICONTROL Create]**. Det nya beslutet läggs till under **[!UICONTROL Decisions]**.

   ![](assets/decision-code-based-decision-added.png)

1. Klicka på ikonen för fler åtgärder (tre punkter) och välj **[!UICONTROL Add]**. Nu kan du lägga till alla beslutsattribut som du vill ha i det här.

   ![](assets/decision-code-based-add-decision.png)

1. Du kan också lägga till andra attribut som är tillgängliga i personaliseringsredigeraren, till exempel profilattribut.

   ![](assets/decision-code-based-decision-profile-attribute.png)

1. Bygg behandlingen B och upprepa stegen ovan för att skapa ett nytt beslut.

1. Spara innehållet.


