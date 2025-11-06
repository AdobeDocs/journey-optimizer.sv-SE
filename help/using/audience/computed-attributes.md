---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med beräknade attribut
description: Lär dig hur du arbetar med beräknade attribut.
feature: Audiences, Profiles
role: User
level: Intermediate
exl-id: 5402a179-263f-46a7-bddf-5b7017cf0f82
source-git-commit: d87f33c80cc85b1d1a87150687f6d7c9a268a016
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Arbeta med beräknade attribut {#computed-attributes}

Beräknade attribut sammanfattar enskilda beteendehändelser i beräknade profilattribut som är tillgängliga på Adobe Experience Platform. Dessa attribut baseras på profilaktiverade Experience Event-datamängder som importerats till Adobe Experience Platform och fungerar som aggregerade datapunkter som lagras i kundprofiler.

Varje beräknat attribut är ett profilattribut som ni kan använda för segmentering, personalisering och aktivering under resor och kampanjer. Den här förenklingen gör det enklare att leverera vältajmade och meningsfulla personaliserade upplevelser till kunderna.


![](../rn/assets/do-not-localize/computed-attributes.gif)


>[!NOTE]
>
>Kontrollera att du har rätt behörighet (**Visa beräknade attribut** och **Hantera beräknade attribut**) för att få åtkomst till beräknade attribut.

## Skapa beräknade attribut {#manage}

Om du vill skapa beräknade attribut går du till fliken **[!UICONTROL Computed attributes]** på menyn **[!UICONTROL Profiles]** som finns till vänster.

Från den här skärmen kan du skapa beräknade attribut genom att skapa regler som kombinerar händelseattribut, sammanställningsfunktioner, tillsammans med en angiven uppslagsperiod. Du kan till exempel beräkna summan av inköp som gjorts de senaste tre månaderna, identifiera den senaste artikeln som visas av en profil som inte har gjort ett köp den senaste veckan eller räkna upp de totala belöningspoängen som ackumulerats av varje profil.

![](assets/computed-attributes.png)

När regeln är klar publicerar du det beräknade attributet så att det blir tillgängligt i andra tjänster längre fram i kedjan, inklusive Journey Optimizer.

Detaljerad information om hur du skapar och hanterar beräknade attribut finns i [dokumentationen om beräknade attribut](https://experienceleague.adobe.com/docs/experience-platform/profile/computed-attributes/overview.html)

## Lägg till beräknade attribut i Adobe Experience Platform-datakällan {#source}

Om du vill använda beräknade attribut i Journey Optimizer lägger du till dem i datakällan för Journey Optimizer **Experience Platform**.

Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan hämtar profildata och Experience Events-data från kundprofiltjänsten i realtid.

Så här lägger du till beräknade attribut i datakällan:

1. Bläddra till den vänstra menyn **[!UICONTROL Configurations]** och klicka sedan på kortet **[!UICONTROL Data sources]**.

1. Välj datakällan **[!UICONTROL Experience Platform]**.

   ![](assets/computed-attributes-add.png)

1. Lägg till fältgruppen **[!UICONTROL SystemComputedAttributes]** som innehåller alla skapade beräknade attribut.

   ![](assets/computed-attributes-fieldgroup.png)

Beräknade attribut kan nu användas i Journey Optimizer. [Lär dig använda beräknade attribut i Journey Optimizer](#use)

Detaljerad information om hur du lägger till fältgrupper i Adobe Experience Platform datakälla finns i [det här avsnittet](../datasource/adobe-experience-platform-data-source.md).

## Använd beräknade attribut i Journey Optimizer {#use}

>[!NOTE]
>
>Innan du börjar ser du till att du har lagt till dina beräknade attribut i Adobe Experience Platform-datakällan. [Läs mer i det här avsnittet](#source).

Beräknade attribut ger mångsidiga funktioner i Journey Optimizer. Använd dem för olika syften, som att personalisera meddelandeinnehåll, skapa nya målgrupper eller dela upp resor baserat på ett specifikt beräknat attribut. Du kan t.ex. dela upp en resa baserat på en profils totala inköp de senaste tre veckorna genom att lägga till ett enda beräknat attribut i en villkorsaktivitet. Du kan också anpassa ett e-postmeddelande genom att visa det senast visade objektet för varje profil.

Eftersom beräknade attribut är profilattributfält som har skapats i ditt profilunionsschema kan du komma åt dem från personaliseringsredigeraren i fältgruppen **SystemComputedAttributes**. Därifrån lägger du till beräknade attribut i dina uttryck och behandlar dem som andra profilattribut för att utföra de önskade åtgärderna.

![](assets/computed-attributes-ajo.png)
