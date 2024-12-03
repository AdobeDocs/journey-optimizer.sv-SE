---
title: Användningsfall vid beslut
description: Lär dig hur du skapar beslut med hjälp av experiment med den kodbaserade kanalen
feature: Decisioning
topic: Integrations
role: User
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 09770df2-c514-4217-a71b-e31c248df543
source-git-commit: 196caffc918ef4f8fd97c2eb2c790ae4583aa311
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 4%

---

# Användningsfall vid beslut {#experience-decisioning-uc}

Du är osäker på om en viss rankningsformel kommer att fungera bättre än de förtilldelade prioriteterna.

I det här fallet skapar ni en kampanj där ni definierar två leveransbehandlingar - som vart och ett innehåller en egen beslutspolicy för att mäta vilken som fungerar bäst för er målgrupp.

Gör så att experimentet

* Den första behandlingen innehåller en urvalsstrategi med prioritet som rangordningsmetod.
* Den andra behandlingen innehåller en annan urvalsstrategi där en formel är rangordningsmetoden.


## Skapa beslutsposter och urvalsstrategier

Först måste du skapa objekt, gruppera dem i samlingar, ställa in regler och rangordningsmetoder. Med dessa element kan du skapa urvalsstrategier.

1. Navigera till **[!UICONTROL Decisioning]** > **[!UICONTROL Catalogs]** och skapa flera beslutsobjekt. Ange begränsningar med målgrupper eller regler för att begränsa varje objekt till enbart specifika profiler. [Läs mer](items.md)

   <!--
   1. From the items list, click the **[!UICONTROL Edit schema]** button  and edit the custom attributes if needed. [Learn how to work with catalogs](catalogs.md)-->

1. Skapa **samlingar** för att kategorisera och gruppera dina beslutsobjekt enligt dina önskemål. [Läs mer](collections.md)

1. Skapa **beslutsregler** för att avgöra till vilka ett beslutsobjekt kan visas. [Läs mer](rules.md)

1. Skapa **rankningsmetoder** och tillämpa dem inom beslutsstrategier för att fastställa prioritetsordningen för val av beslutsobjekt. [Läs mer](ranking.md)

1. Bygg **urvalsstrategier** som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsobjekt som passar för visning i profiler. [Läs mer](selection-strategies.md)

## Skapa beslutsprofiler

Om du vill presentera det bästa dynamiska erbjudandet och upplevelsen för besökarna på din webbplats eller i din mobilapp lägger du till en beslutspolicy i en kodbaserad kampanj.

<!--Define two delivery treatments each containing a different decision policy.-->

1. Skapa en kampanj och välj åtgärden **[!UICONTROL Code-base experience]**. [Läs mer](../code-based/create-code-based.md)

1. Börja personalisera behandling A från fönstret **[!UICONTROL Edit content]**.

1. Välj ikonen **[!UICONTROL Decisions]**, klicka på **[!UICONTROL Create a decision]** och fyll i beslutsinformationen. [Läs mer](create-decision.md)

   ![](assets/decision-code-based-create.png)

1. Definiera urvalsstrategierna för ditt beslut. Klicka på **[!UICONTROL Add strategy]**.

1. Klicka på **[!UICONTROL Create]**. Det nya beslutet läggs till under **[!UICONTROL Decisions]**.

   ![](assets/decision-code-based-decision-added.png)

1. Klicka på ikonen för fler åtgärder (tre punkter) och välj **[!UICONTROL Add]**. Nu kan du lägga till alla beslutsattribut som du vill ha i det här.

   ![](assets/decision-code-based-add-decision.png)

1. Du kan också lägga till andra attribut som är tillgängliga i personaliseringsredigeraren, till exempel profilattribut.

   ![](assets/decision-code-based-decision-profile-attribute.png)

1. Klicka på **[!UICONTROL Create experiment]** på kampanjsammanfattningssidan för att börja konfigurera ditt innehållsexperiment. [Läs mer](../content-management/content-experiment.md)

1. I fönstret **[!UICONTROL Edit content]** väljer du din behandling B för att ändra innehållet och upprepar stegen ovan för att skapa ett annat beslut.

1. Spara innehållet.
