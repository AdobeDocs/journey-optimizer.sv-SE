---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med beräknade attribut
description: Lär dig hur du arbetar med beräknade attribut.
feature: Profiles
role: User
level: Beginner
exl-id: 5402a179-263f-46a7-bddf-5b7017cf0f82
source-git-commit: c4ab97999d000d969f6f09f4d84be017d1288f94
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Arbeta med beräknade attribut {#computed-attributes}

Beräknade attribut gör att du kan sammanfatta enskilda beteendehändelser i beräknade profilattribut som är tillgängliga på Adobe Experience Platform. Dessa beräknade attribut baseras på profilaktiverade Experience Event-datamängder som importerats till Adobe Experience Platform och fungerar som aggregerade datapunkter som lagras i kundprofiler.

Varje beräknat attribut är ett profilattribut som ni kan använda för segmentering, personalisering och aktivering under resor och kampanjer. Den här förenklingen gör det enklare att leverera vältajmade och meningsfulla personaliserade upplevelser till kunderna.

>[!NOTE]
>
>För att få åtkomst till beräknade attribut måste du ha rätt behörighet (**Visa beräknade attribut** och **Hantera beräknade attribut**).

## Skapa beräknade attribut {#manage}

Om du vill skapa beräknade attribut går du till **[!UICONTROL Computed attributes]** i **[!UICONTROL Profiles]** menyn till vänster.

Från den här skärmen kan du skapa beräknade attribut genom att skapa regler som kombinerar händelseattribut, sammanställningsfunktioner och en angiven uppslagsperiod. Du kan till exempel beräkna summan av inköp som gjorts de senaste tre månaderna, identifiera den senaste artikeln som visas av en profil som inte har gjort ett köp den senaste veckan eller räkna upp de totala belöningspoängen som ackumulerats av varje profil.

![](assets/computed-attributes.png)

När regeln är klar publicerar du det beräknade attributet så att det blir tillgängligt i andra tjänster längre fram i kedjan, inklusive Journey Optimizer.

Detaljerad information om hur du skapar och hanterar beräknade attribut finns i [Dokumentation för beräknade attribut](https://experienceleague.adobe.com/docs/experience-platform/profile/computed-attributes/overview.html)

## Lägg till beräknade attribut i Adobe Experience Platform-datakällan {#source}

För att kunna utnyttja beräknade attribut i Journey Optimizer måste du först lägga till dem i Journey Optimizer **Experience Platform** datakälla.

Adobe Experience Platform datakälla definierar anslutningen till Adobe kundprofil i realtid. Den här datakällan är utformad för att hämta profildata och Experience Events-data från kundprofiltjänsten i realtid.

Så här lägger du till beräknade attribut i datakällan:

1. Navigera till **[!UICONTROL Configurations]** vänster handmeny och klicka sedan på **[!UICONTROL Data sources]** kort.

1. Välj **[!UICONTROL Experience Platform]** datakälla.

   ![](assets/computed-attributes-add.png)

1. Lägg till **[!UICONTROL SystemComputedAttributes]** fältgrupp som innehåller alla skapade beräknade attribut.

   ![](assets/computed-attributes-fieldgroup.png)

Beräknade attribut kan nu användas i Journey Optimizer. [Lär dig använda beräknade attribut i Journey Optimizer](#use)

Detaljerad information om hur du lägger till fältgrupper i Adobe Experience Platform datakälla finns i [det här avsnittet](../datasource/adobe-experience-platform-data-source.md).

## Använd beräknade attribut i Journey Optimizer {#use}

>[!NOTE]
>
>Innan du börjar bör du kontrollera att du har lagt till dina beräknade attribut i Adobe Experience Platform datakälla. [Läs mer i det här avsnittet](#source).

Beräknade attribut erbjuder en mångsidig uppsättning funktioner i Journey-optimeraren. Du kan använda dem för olika syften, till exempel för att personalisera meddelandeinnehåll, skapa nya målgrupper eller dela upp resor baserat på ett specifikt beräknat attribut. Du kan t.ex. dela upp en resa baserat på en profils totala inköp de senaste tre veckorna genom att lägga till ett enda beräknat attribut i en villkorsaktivitet. Du kan också anpassa ett e-postmeddelande genom att visa det senast visade objektet för varje profil.

Eftersom beräknade attribut är profilattributfält som skapats i ditt profilföreningsschema kan du komma åt dem från uttrycksredigeraren i **SystemComputedAttributes** fältgrupp. Därifrån kan du lägga till ett beräknat attribut i dina uttryck och behandla dem som vilket annat profilattribut som helst för att utföra de önskade åtgärderna.

![](assets/computed-attributes-ajo.png)