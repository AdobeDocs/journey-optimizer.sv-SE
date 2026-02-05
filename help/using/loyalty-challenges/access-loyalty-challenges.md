---
solution: Journey Optimizer
product: journey optimizer
title: Få tillgång till och hantera utmaningar och uppgifter
description: Lär dig hur du får tillgång till, hanterar och organiserar lojalitetsutmaningar och uppgifter i Adobe Journey Optimizer.
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Privat beta" type="Informative"
mini-toc-levels: 2
source-git-commit: 43d3593264ea6d33794914e1b1f9ea45c295c79e
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# Få tillgång till och hantera utmaningar och uppgifter {#access-loyalty-challenges}

>[!AVAILABILITY]
>
>Den här funktionen är för närvarande i **privat beta** och är kanske inte tillgänglig i din miljö. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

>[!BEGINSHADEBOX]

**Dokumentation om lojalitetsproblem:**

* [Kom igång med lojalitetsutmaningar](get-started.md) - Översikt, arbetsflöde, förutsättningar
* **Få åtkomst till och hantera utmaningar och uppgifter** {2 }︎ ◀Du är här **- Inventering, utmaning och uppgiftshantering**
* [Skapa utmaningar](create-challenges.md) - Bygg och konfigurera utmaningar
* [Skapa aktiviteter](create-tasks.md) - Definiera utmaningsuppgifter

>[!ENDSHADEBOX]

## Få tillgång till och hantera utmaningar och uppgifter

Om du vill få åtkomst till lojalitetsutmaningar går du till Journey Optimizer och väljer **[!UICONTROL Loyalty Challenge (Beta)]** under avsnittet **[!UICONTROL Journey management]**. Gränssnittet Lojalitetsutmaningar är en central plats där du kan visa, hantera och organisera alla utmaningar och uppgifter.

Gränssnittet ger tillgång till två huvudsakliga inventeringar:

* **Utmaningar**: Visa och hantera alla lojalitetsproblem, övervaka deras status och utföra snabba åtgärder som att visa, redigera, duplicera eller ta bort utmaningar
* **Uppgifter**: Bläddra bland återanvändbara uppgifter som kan användas i flera utmaningar och hantera uppgiftsdefinitioner oberoende av varandra


## Utmaningslager {#challenges-tab}

Fliken **[!UICONTROL Challenges]** visar alla utmaningar sorterade efter senaste ändringsdatum, där de senast ändrade utmaningarna visas först.

![](assets/challenges-inventory.png)

Visad nyckelinformation:

* **[!UICONTROL State]**: Utfrågans aktuella tillstånd (utkast eller publicerat)
* **[!UICONTROL Tasks]**: Antal konfigurerade uppgifter i utmaningen
* **[!UICONTROL Journey]**: Länk till den automatiskt genererade resan som är associerad med utmaningen
* **[!UICONTROL Status]**: Aktuell status för den associerade resan (utkast, Live, stoppad osv.)
* **[!UICONTROL Start/End Date (UTC)]**: När utmaningen blir aktiv och upphör att gälla

På fliken Utmaningar kan du utföra åtgärder på utmaningar:

* **Visa utmaning**: Välj utmaningsnamnet för att öppna informationssidan
* **Duplicera en utmaning**: Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) och välj **[!UICONTROL Duplicate]**. En kopia skapas med alla uppgifter, allt innehåll och alla meddelanden intakta.
* **Ta bort en utmaning**: Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) och välj **[!UICONTROL Delete]**
* **Redigera en utmaning**: Välj utmaningsnamnet för att öppna dess informationssida och redigera den.

  När du öppnar en publicerad utmaning för redigering måste du först återställa den till statusen Utkast. Eventuella anpassningar som gjorts direkt i den automatiskt genererade resan går förlorade. När du har gjort ändringarna sparar och publicerar du utmaningen igen och publicerar den tillhörande resan igen.

  >[!IMPORTANT]
  >
  >Det går inte att ångra en publicerad utmaning till ett utkast. Fundera på vilken effekt din aktiva resa har innan du fortsätter.

## Aktivitetslager {#tasks-tab}

Fliken **[!UICONTROL Tasks]** visar alla återanvändbara uppgifter som kan användas för flera utmaningar. Uppgifter som skapas här blir tillgängliga för markering när du skapar eller redigerar utmaningar.

![](assets/tasks-inventory.png)

Visad nyckelinformation:

* **[!UICONTROL Description]**: En kort beskrivning av vad aktiviteten kräver
* **[!UICONTROL Task Activity]**: Typ av aktivitet (Inköp, Utgift)
* **[!UICONTROL SKU]**: Godtagbara och/eller undantagna objekt
* **[!UICONTROL Used in challenges]**: Antal utmaningar som för närvarande använder den här aktiviteten

På fliken Åtgärder kan du utföra åtgärder för uppgifter:

* **Visa/redigera en uppgift**: Markera aktivitetsnamnet om du vill visa den fullständiga konfigurationen och redigera uppgiften
* **Duplicera en uppgift**: Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) och välj **[!UICONTROL Duplicate]**
* **Ta bort en uppgift**: Markera ikonen ![](assets/do-not-localize/Smock_More_18_N.svg) och välj **[!UICONTROL Delete]**
