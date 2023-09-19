---
title: Beslutsobjekt
description: Lär dig hur du arbetar med beslutsobjekt
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
source-git-commit: 69a2ef17b6f5ccd40c08858f7b434029964d544d
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---

# Beslutsobjekt {#items}

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med Experience Decision](gs-experience-decisioning.md)
* Hantera dina beslutsobjekt
   * [Konfigurera objektkatalogen](catalogs.md)
   * **[Skapa beslutsobjekt](items.md)**
   * [Hantera artikelsamlingar](collections.md)
* Konfigurera val av objekt
   * [Skapa beslutsregler](rules.md)
   * [Skapa rangordningsmetoder](ranking.md)
* [Skapa urvalsstrategier](selection-strategies.md)
* [Skapa beslutsprofiler](create-decision.md)

>[!ENDSHADEBOX]

Med Journey Optimizer kan ni skapa marknadsföringserbjudanden, så kallade beslutsobjekt, som ni kan skapa och ordna i en centraliserad katalog och samlingar. De består av standardattribut och anpassade attribut som är anpassade efter just dina behov. Dessutom innehåller de profilbegränsningar som gör att du kan definiera till vilka ett beslutsobjekt kan visas.

Kontrollera att du har skapat en **beslutsregel** om du vill ange villkor för att bestämma vem beslutsobjektet kan visas för. [Lär dig hur du skapar beslutsregler](rules.md).

## Skapa ditt första beslutsobjekt

Så här skapar du ett beslutsobjekt:

1. Navigera till **[!UICONTROL Experience Decisioning]** > **[!UICONTROL Items]**.

1. Definiera beslutsobjektets standardattribut:

   1. Ange ett namn och en beskrivning.
   1. Ange start- och slutdatum. Posten kommer endast att beaktas av beslutsmotorn inom dessa datum.
   1. Ange **[!UICONTROL Priority]** för beslutsobjektet jämfört med andra, om en profil kvalificerar för flera poster. En högre prioritet ger objektet företräde framför andra.

   ![](assets/item-attributes.png)

1. Anpassade attribut är specifika attribut som är anpassade efter dina behov och som du kan tilldela till ett beslutsobjekt. De definieras i beslutsobjektens katalogschema. [Lär dig hur du arbetar med kataloger](catalogs.md)

1. När beslutsobjektets attribut har definierats klickar du på **[!UICONTROL Next]** för att ange profilbegränsningar för objektet.

   Som standard är alla profiler berättigade att ta emot beslutsobjektet, men du kan använda målgrupper eller regler för att begränsa objektet till enbart specifika profiler, båda lösningarna som motsvarar olika användningar. Expandera avsnittet nedan om du vill ha mer information:

   +++Använda målgrupper kontra decimalregler

   En målgrupps utdata är i princip en lista med profiler, medan en beslutsregel är en funktion som körs på begäran mot en enskild profil under beslutsprocessen.

   * **Målgrupper**: Å ena sidan är målgrupperna en grupp Adobe Experience Platform-profiler som matchar en viss logik baserat på profilattribut och upplevelsehändelser. Erbjudandehanteringen innebär dock inte att publiken beräknas om, vilket kanske inte är aktuellt när erbjudandet presenteras.

   * **Beslutsregler**: Å andra sidan baseras en beslutsregel på data som är tillgängliga i Adobe Experience Platform och avgör till vem ett erbjudande kan visas. När regeln har valts i ett erbjudande eller i ett beslut för en viss placering verkställs den varje gång ett beslut fattas, vilket säkerställer att varje profil får det senaste och bästa erbjudandet.

+++

   ![](assets/item-constraints.png)

   * Om du vill begränsa presentationen av beslutsobjektet till medlemmarna i en eller flera av Adobe Experience Platform målgrupper väljer du **[!UICONTROL Visitors who fall into one or multiple audiences]** lägg sedan till en eller flera målgrupper från den vänstra rutan och kombinera dem med **[!UICONTROL And]** / **[!UICONTROL Or]** logiska operatorer. [Läs mer om målgrupper](../audience/about-audiences.md).

   * Om du vill koppla en specifik beslutsregel till beslutsobjektet väljer du **[!UICONTROL By rule]** drar du sedan den önskade regeln från den vänstra rutan till det centrala området. [Läs mer om beslutsregler](rules.md).

   När du väljer målgrupper eller beslutsregler kan du se information om de uppskattade kvalificerade profilerna. Klicka **[!UICONTROL Refresh]** för att uppdatera data.

   >[!NOTE]
   >
   >Profiluppskattningar är inte tillgängliga när regelparametrar innehåller data som inte finns i profilen, till exempel kontextdata. Exempel: en regel som kräver att det aktuella vädret är ≥80 grader.

1. När du har definierat beslutsobjektets begränsningar klickar du på **[!UICONTROL Next]** för att granska och spara objektet.

1. Beslutsobjektet visas nu i listan med **[!UICONTROL Draft]** status. Klicka på ellipsknappen och markera när den är klar att visas för profiler **[!UICONTROL Approve]**.

   ![](assets/item-approve.png)

## Hantera beslutsobjekt

I listan över beslutsobjekt kan du redigera ett beslutsobjekt och ändra dess status (**Utkast**, **Godkänd**, **Arkiverad**), duplicera eller ta bort den.

Om du vill ändra ett beslutsobjekt öppnar du det, gör ändringarna och sparar det.

Om du väljer ett beslutsobjekt eller klickar på ellipsknappen aktiveras de åtgärder som beskrivs nedan.

* **[!UICONTROL Approve]**: Anger beslutsobjektets status till Godkänd.
* **[!UICONTROL Undo approve]**: Anger beslutsobjektets status tillbaka till **[!UICONTROL Draft]**.
* **[!UICONTROL Duplicate]**: Skapar ett beslutsobjekt med identiska attribut och begränsningar. Som standard har det nya objektet **[!UICONTROL Draft]** status.
* **[!UICONTROL Delete]**: Tar bort beslutsobjektet från listan.

  >[!IMPORTANT]
  >
  >När den tagits bort är beslutsobjektet och dess innehåll inte längre tillgängliga. Det går inte att ångra den här åtgärden. Om beslutsobjektet används i en samling eller ett beslut kan det inte tas bort. Du måste ta bort beslutsobjektet från alla objekt först.

* **[!UICONTROL Archive]**: Anger beslutsobjektets status till **[!UICONTROL Archived]**. Beslutsobjektet är fortfarande tillgängligt från listan, men du kan inte återställa dess status till **[!UICONTROL Draft]** eller **[!UICONTROL Approved]**. Du kan bara duplicera eller ta bort den.
