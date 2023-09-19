---
title: Användningsfall vid beslut om upplevelse
description: Lär dig hur du skapar beslut med hjälp av experiment med den kodbaserade kanalen
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 5%

---

# Användningsfall vid beslut om upplevelse {#experience-decisioning-uc}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsobjekt
   * [Konfigurera objektkatalogen](catalogs.md)
   * [Skapa beslutsobjekt](items.md)
   * [Hantera artikelsamlingar](collections.md)
* Konfigurera val av objekt
   * [Skapa beslutsregler](rules.md)
   * [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)
* **[Lär dig med ett användningsexempel](experience-decisioning-uc.md)**

>[!ENDSHADEBOX]

I det här fallet definierar ni två leveransbehandlingar som var och en innehåller olika beslutsprinciper för att mäta vilken som fungerar bäst för målgruppen.

## Skapa artiklar och strategier

Först måste du skapa objekt, gruppera dem i samlingar, ställa in regler och rangordningsmetoder. Med dessa element kan du skapa urvalsstrategier.

1. Navigera till **[!UICONTROL Experience Decisioning]** > **[!UICONTROL Items]** och skapa flera olika erbjudanden. Ange begränsningar med målgrupper eller regler för att begränsa varje objekt till enbart specifika profiler. [Läs mer](items.md)

   <!--
   1. From the items list, click the **[!UICONTROL Edit schema]** button  and edit the custom attributes if needed. [Learn how to work with catalogs](catalogs.md)-->

1. Skapa **samlingar** för att kategorisera och gruppera dina beslutsobjekt efter dina önskemål. [Läs mer](collections.md)

1. Skapa **beslutsregler** för att fastställa till vem ett beslutsobjekt kan visas. [Läs mer](rules.md)

1. Skapa **rangordningsmetoder** och tillämpa dem inom beslutsstrategier för att fastställa prioriteringsordningen för val av beslutsposter. [Läs mer](ranking.md)

1. Bygge **urvalsstrategier** som utnyttjar samlingar, beslutsregler och rangordningsmetoder för att identifiera de beslutsposter som är lämpliga att visa för profiler. [Läs mer](selection-strategies.md)

## Skapa beslutsprofiler

Om du vill presentera det bästa dynamiska erbjudandet och upplevelsen för besökarna på din webbplats eller i din mobilapp lägger du till en beslutspolicy i en kodbaserad kampanj.

Definiera två leveransbehandlingar som var och en innehåller olika beslutspolicyer.

1. Skapa en kampanj och välj **[!UICONTROL Code-base experience (Beta)]** åtgärd. [Läs mer](../code-based/create-code-based.md)

   >[!NOTE]
   >
   >Funktionen för kodbaserad upplevelse är för närvarande endast tillgänglig som betaversion för utvalda användare. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

1. Klicka på i kampanjsammanfattningssidan **[!UICONTROL Create experiment]** för att börja konfigurera ditt innehållsexperiment. [Läs mer](../campaigns/content-experiment.md)

1. Välj **[!UICONTROL Decisions]** ikon, klicka **[!UICONTROL Create a decision]** och fyll i beslutsdetaljerna. [Läs mer](create-decision.md)

   ![](assets/decision-code-based-create.png)

1. Definiera urvalsstrategierna för ditt beslut. Klicka på **[!UICONTROL Add strategy]**.

1. Klicka på **[!UICONTROL Create]**. Det nya beslutet läggs till under **[!UICONTROL Decisions]**.

   ![](assets/decision-code-based-decision-added.png)

1. Klicka på ikonen för fler åtgärder (tre punkter) och välj **[!UICONTROL Add]**. Nu kan du lägga till alla beslutsattribut som du vill ha i det här.

   ![](assets/decision-code-based-add-decision.png)

1. Du kan också lägga till andra attribut som är tillgängliga i uttrycksredigeraren, till exempel profilattribut.

   ![](assets/decision-code-based-decision-profile-attribute.png)

1. Bygg behandlingen B och upprepa stegen ovan för att skapa ett nytt beslut.

1. Spara innehållet.


