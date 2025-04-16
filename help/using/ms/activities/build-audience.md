---
solution: Journey Optimizer
product: journey optimizer
title: Använd aktiviteten Skapa målgrupp
description: Lär dig hur du använder aktiviteten Skapa målgrupp i en orkestrerad kampanj
hide: true
hidefromtoc: true
exl-id: 3959b5fa-0c47-42a5-828f-4d7ca9b7e72d
source-git-commit: 3d380d2d02eb7043aebcffd00bb2092e7341b0d5
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---

# Bygg målgrupper {#build-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience"
>title="Bygg målgruppsaktivitet"
>abstract="Med aktiviteten **Skapa målgrupp** kan du definiera målgruppen som ska gå in i den orkestrerade kampanjen. När du skickar meddelanden i samband med en orkestrerad kampanj definieras inte meddelandemålgruppen i kanalaktiviteten, utan i aktiviteten **Bygg målgrupp**."

Aktiviteten **Skapa målgrupp** är en **målgruppsaktivitet**. Med den här aktiviteten kan ni definiera målgruppen som ska delta i den orkestrerade kampanjen. När du skickar meddelanden i samband med en orkestrerad kampanj definieras inte meddelandemålgruppen i kanalaktiviteten, utan i aktiviteten **Bygg målgrupp**.

Om du vill definiera målgruppspopulationen kan du:

* Välj en Adobe Experience Platform-målgrupp.
* Bygg en ny målgrupp med frågemodelleraren genom att definiera och kombinera filtervillkor.

>[!NOTE]
>
>Målgrupper som läses in från en fil kan inte anges som mål med en Build-målgruppsaktivitet. För att göra detta måste du använda en **Läs in fil**-aktivitet följt av en **avstämningsaktivitet** .

<!--
The **Build audience** activity can be placed at the beginning of the workflow or after any other activity. Any activity can be placed after the **Build audience**.
-->

## Konfigurera aktiviteten Skapa målgrupp {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience_audienceselector"
>title="Målgrupp"
>abstract="Välj målgrupp på samma sätt som du använder en målgrupp när du designar en ny leverans."

Följ de här stegen för att konfigurera aktiviteten **Skapa målgrupp**:

![](../assets/workflow-audience.png)

1. Lägg till en **Skapa målgruppsaktivitet**.
1. Definiera en etikett.
1. Definiera målgruppstypen: **Skapa din egen** eller **Läs målgrupp**.
1. Konfigurera målgruppen genom att följa stegen som beskrivs på flikarna nedan.

>[!BEGINTABS]

>[!TAB Skapa en egen (fråga)]

Så här skapar du en egen fråga:

1. Välj **Skapa en egen (fråga)**.
1. Välj **Måldimension**. Med målinriktningsdimensionen kan du definiera målgruppen för operationen: mottagare, mottagare, operatör, prenumeranter osv. Som standard är målet markerat bland mottagarna.
1. Klicka på **Fortsätt**.
1. Använd frågemodelleraren för att definiera frågan, på samma sätt som du skapar en målgrupp när du utformar ett nytt e-postmeddelande.

>[!TAB Läs målgrupp]

Så här väljer du en befintlig målgrupp:

1. Välj **Läs målgrupp**.
1. Klicka på **Fortsätt**.
1. Välj målgrupp på samma sätt som du använder en målgrupp när du designar en ny leverans.

>[!ENDTABS]

## Exempel{#build-audience-examples}

Här är ett exempel på en orkestrerad kampanj med två **Build-målgruppsaktiviteter**. Det första riktar sig till pokerspelarna, följt av ett mejlerbjudande. Det andra riktar sig till VIP kunder, följt av SMS-leverans.

![](../assets/workflow-audience-example.png)
