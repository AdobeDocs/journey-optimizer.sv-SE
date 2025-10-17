---
solution: Journey Optimizer
product: journey optimizer
title: Översikt över att dela steg i resan
description: Översikt över att dela steg i resan
feature: Journeys, Reporting
topic: Content Management
role: Data Engineer, Data Architect, Admin
level: Experienced
exl-id: 29d6b881-35a3-4c62-9e7d-d0aeb206ea77
source-git-commit: efae7f7d366690af71430bb9eb62523d1881c50e
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 2%

---

# Skapa reserapporter {#design-jo-reports}

Utöver [realtidsrapporter](live-report.md) och inbyggda [rapporteringsfunktioner](report-gs-cja.md) kan [!DNL Journey Optimizer] automatiskt skicka data om reseprestanda till Adobe Experience Platform så att det kan kombineras med andra data i analyssyfte.

>[!NOTE]
>
>Den här funktionen aktiveras som standard för alla instanser för steg i kundresan. Du kan inte ändra eller uppdatera scheman och datauppsättningar som har skapats under etablering för steghändelser. Dessa scheman och datauppsättningar är som standard skrivskyddade.

Du har till exempel konfigurerat en resa som skickar flera e-postmeddelanden. Med den här funktionen kan du kombinera [!DNL Journey Optimizer]-data med händelsedata längre fram i kedjan, som hur många konverteringar som har gjorts, hur mycket engagemang som har gjorts på webbplatsen eller hur många transaktioner som har gjorts i butiken. Reseinformationen kan kombineras med data om Adobe Experience Platform, antingen från andra digitala resurser eller från offlineanläggningar, för att ge en mer heltäckande bild av resultatet.

[!DNL Journey Optimizer] skapar automatiskt nödvändiga scheman och strömmar till datauppsättningar till Adobe Experience Platform för varje steg en individ tar på en resa. En steghändelse motsvarar en person som flyttar från en nod till en annan under en resa. Exempel: i en resa som innehåller en händelse, ett villkor och en åtgärd skickas tre steghändelser till Adobe Experience Platform.

>[!NOTE]
>
>Förutom steg-händelser på profilnivå genererar systemet även interna händelser för **Läs målgrupp**-aktiviteter. Dessa händelser, som kallas `segmentExportJob` händelser, registrerar livscykeln för Läs publik-noden (som att skapa exportjobb, köa, slutföra och fel) och genereras per Läs publik-aktivitet, inte per enskild profil. Därför kanske dessa händelser inte har någon associerad profilidentifierare (UPMID). Dessa interna händelser är användbara för övervakning och felsökning av läs- och målprestanda och kan frågas med hjälp av fälten som beskrivs i avsnittet [serviceEvents](../reports/sharing-field-list.md#servicevents-field). Frågeexempel om hur du arbetar med segmentExportJob-händelser finns i [Frågor som rör läsningen](../reports/query-examples.md#read-segment-queries).

Det finns fall där flera händelser kan skapas för samma nod. Exempel: i fallet med aktiviteten Vänta:

* En händelse genereras när profilen anger väntetiden (attributet travelNodeProcsed är lika med false)
* En händelse genereras när profilen avslutas (attributet travelNodeProcsed är lika med true)

Listan över XDM-fält som skickas är omfattande. Vissa innehåller systemgenererade koder och andra har användarvänliga namn som kan läsas. Exempel är etiketten för reseaktiviteten eller stegstatusen: hur många gånger en åtgärd orsakade fel eller orsakade timeout.

>[!CAUTION]
>
>Det går inte att aktivera datauppsättningar för profiltjänsten i realtid. Kontrollera att växlingsknappen **[!UICONTROL Profile]** är inaktiverad.

[!DNL Journey Optimizer] skickar data i direktuppspelning när de inträffar. Du kan söka efter dessa data med hjälp av frågetjänsten. Du kan ansluta till Customer Journey Analytics eller andra BI-verktyg för att visa data som hör till dessa steg.

Följande scheman skapas:

* Resestegshändelseschema för [!DNL Journey Orchestration] - Resestegshändelse som är knuten till en resemetadata.
* Reseschema med resefält för [!DNL Journey Orchestration] - Resemetadata för att beskriva resor.

![](assets/sharing1.png)

![](assets/sharing2.png)

Följande datauppsättningar har skickats:

* Resestegshändelser
* Resor

![](assets/sharing3.png)

Listorna med XDM-fält som skickas till Adobe Experience Platform finns här:

* [Lista över steghändelsefält](../reports/sharing-field-list.md)
* [Händelsefält för äldre steg](../reports/sharing-legacy-fields.md)

## Integrering med Customer Journey Analytics {#integration-cja}

[!DNL Journey Optimizer] steghändelser kan länkas till andra datauppsättningar i [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=sv-SE){target="_blank"}.

Det allmänna arbetsflödet är:

* [!DNL Customer Journey Analytics] inmatar datamängden &quot;Resestegshändelse&quot;.
* Fältet **profileID** i det associerade schemat för resesegmenthändelse för Journey Orchestration definieras som ett identitetsfält. I [!DNL Customer Journey Analytics] kan du sedan länka den här datauppsättningen till andra datauppsättningar som har samma värde som den personbaserade identifieraren.
* Information om hur du använder den här datauppsättningen i [!DNL Customer Journey Analytics] finns i [Customer Journey Analytics-dokumentationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html?lang=sv-SE){target="_blank"} för analys av flerkanalsresor.

➡️ [Arbeta med Customer Journey Analytics](cja-ajo.md){target="_blank"}
