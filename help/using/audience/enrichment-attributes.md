---
solution: Journey Optimizer
product: journey optimizer
title: Om Adobe Experience Platform målgrupper
description: Lär dig arbeta med Adobe Experience Platform målgrupper
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 3ec496ba-7555-49e2-992c-403c33302a90
source-git-commit: c4f6b7754255ce3bf0229702b10955abf9843548
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 1%

---

# Använd attribut för målgruppsberikning {#enrichment}

När ni riktar in er på en målgrupp som genererats med kompositionsarbetsflöden, en anpassad (CSV-fil) målgrupp eller Federated Audience Composition, kan ni använda anrikningsattribut från dessa målgrupper för att skapa er resa och personalisera era budskap.

>[!NOTE]
>
>Publiker som har skapats via anpassad CSV-filöverföring före 1 oktober 2024 är inte berättigade till personlig anpassning. Om du vill använda attribut från de här målgrupperna och använda den här funktionen fullt ut skapar du om och överför alla externa CSV-målgrupper som importerats före detta datum.
>
>Samtyckesprofiler stöder inte anrikningsattribut. Alla regler för samtyckespolicy bör därför endast baseras på attribut som finns i profilen.

Här är de åtgärder du kan utföra med hjälp av målgruppernas anrikningsattribut:

* **Skapa flera sökvägar i en resa** baserat på regler som utnyttjar målpublikens anrikningsattribut. Det gör du genom att rikta in målgruppen med en [Läs målgrupp](../building-journeys/read-audience.md) -aktivitet och sedan skapa regler i en [Villkor](../building-journeys/condition-activity.md) -aktivitet baserat på målgruppens anrikningsattribut.

  ![](assets/audience-enrichment-attribute-condition.png){width="70%" zoomable="yes"}

* **Anpassa dina meddelanden** på resor eller i kampanjer genom att lägga till anrikningsattribut från målgruppen i personaliseringsredigeraren. [Lär dig arbeta med personaliseringsredigeraren](../personalization/personalization-build-expressions.md)

  ![](assets/audience-enrichment-attribute-perso.png){width="70%" zoomable="yes"}

>[!IMPORTANT]
>
>Om du vill använda anrikningsattribut från målgrupper som skapats med dispositionsarbetsflöden måste du se till att de läggs till i en fältgrupp i Data Source för ExperiencePlatform.
>
>+++ Lär dig hur du lägger till anrikningsattribut i en fältgrupp
>
>1. Navigera till Administration > Konfiguration > Datakällor.
>1. Välj&quot;Experience Platform&quot; och skapa eller redigera en fältgrupp.
>1. Välj lämpligt schema i schemaväljaren. Schemats namn kommer att ha följande format: &#39;Schema for audiensId:&#39; + målgruppens ID. Du kan hitta målgruppens ID på skärmen med målgruppsinformation i målgruppslagret.
>1. Öppna fältväljaren, sök efter de anrikningsattribut som du vill lägga till och markera kryssrutan bredvid dem.
>1. Spara ändringarna.
>1. När anrikningsattributen har lagts till i en fältgrupp kan du använda dem i Journey Optimizer på de platser som listas ovan.
>
>Detaljerad information om datakällor finns i följande avsnitt:
>
>* [Arbeta med Adobe Experience Platform datakälla](../datasource/adobe-experience-platform-data-source.md)
>* [Konfigurera en datakälla](../datasource/configure-data-sources.md)
>
>+++


## Vanliga frågor {#faq-enrichment}

Nedan finns frågor och svar om anrikningsattribut.

Behöver du mer information? Använd alternativen för feedback längst ned på den här sidan för att ställa din fråga eller kontakta [Adobe Journey Optimizer Community](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=en){target="_blank"}.

+++ Vad är anrikningsattribut?

Enrichment-attribut är ytterligare attribut som är sammanhangsberoende och specifika för en viss målgrupp. De är inte associerade med profilen och används vanligtvis för personalisering.

Anrikningsattribut länkas till en målgrupp genom en berikande aktivitet i målgruppssammansättning eller den anpassade överföringsprocessen.

+++

+++ Var kan jag använda anrikningsattribut i Journey Optimizer?

Anrikningsattribut från publikens komposition kan användas inom följande områden. [Lär dig använda attribut för målgruppsberikning](#enrichment)

* Villkorsaktivitet (resor)
* Anpassade åtgärdsattribut (resor)
* Meddelandepersonalisering (resor och kampanjer)

+++

+++ Hur aktiverar jag anrikningsattribut i Journeys?

Om du vill använda anrikningsattribut från målgrupper som skapats med dispositionsarbetsflöden måste du se till att de läggs till i en fältgrupp i Data Source för ExperiencePlatform. Information om hur du lägger till anrikningsattribut i en fältgrupp finns i [det här avsnittet](#enrichment)

+++

+++ Uppdateras värdena för anrikningsattributen efter att en resa påbörjats?

Nej. Även efter vänta- eller händelsnoder är värdena för anrikningsattributen desamma som när resan påbörjades.

+++
