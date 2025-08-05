---
solution: Journey Optimizer
product: journey optimizer
title: Skapa samordnade kampanjer med Adobe Journey Optimizer
description: Lär dig skapa samordnade kampanjer med Adobe Journey Optimizer
exl-id: d1d64125-cf00-49c2-a71d-1494ede16f61
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---


# Samordna kampanjaktiviteter {#orchestrate}

När du har [skapat en orchestrated-kampanj](gs-campaign-creation.md) kan du börja organisera de olika uppgifter som ska utföras. För att göra detta finns en visuell arbetsyta som gör att du kan skapa ett orkestrerat kampanjdiagram. I det här diagrammet kan du lägga till olika aktiviteter och koppla dem i en sekventiell ordning.

## Lägg till aktiviteter {#add}

I det här skedet av konfigurationen visas diagrammet med en startikon som representerar början av din samordnade kampanj. Om du vill lägga till din första aktivitet klickar du på knappen **+** som är ansluten till startikonen.

En lista över aktiviteter som kan läggas till i diagrammet visas. Vilka aktiviteter som är tillgängliga beror på din position i det Orchestrerade kampanjdiagrammet. När du till exempel lägger till din första aktivitet kan du starta en orchestrated-kampanj genom att rikta in en målgrupp, dela den orchestrerade kampanjsökvägen eller ange en **Wait**-aktivitet för att fördröja körningen av den orchestrerade-kampanjen. Efter en **Bygg målgrupp** kan du å andra sidan förfina ditt mål med målinriktningsaktiviteter, skicka en leverans till din målgrupp med kanalaktiviteter eller ordna den Orchestrated-kampanjprocessen med flödeskontrollaktiviteter.

![](assets/orchestrated-start.png){zoomable="yes"}

När en aktivitet har lagts till i diagrammet visas en höger ruta där du kan konfigurera den med specifika inställningar. Detaljerad information om hur du konfigurerar varje aktivitet finns i [det här avsnittet](activities/about-activities.md).

![](assets/orchestrated-configure-activities.png){zoomable="yes"}

Upprepa den här processen om du vill lägga till så många aktiviteter som du vill, beroende på vilka uppgifter du vill att den samordnade kampanjen ska utföra. Observera att du även kan infoga en ny aktivitet mellan två aktiviteter. Det gör du genom att klicka på knappen **+** för övergången mellan aktiviteterna, markera önskad aktivitet och konfigurera den i den högra rutan.

Du kan anpassa namnet på övergångarna mellan varje aktivitet. Det gör du genom att markera övergången och ändra dess etikett i den högra rutan.

![](assets/canvas-transition.png)

### Verktygsfältet Arbetsyta {#toolbar}

Verktygsfältet på arbetsytan innehåller alternativ för att enkelt ändra aktiviteterna och navigera på arbetsytan:

![](assets/orchestrated-toolbar.png)

![Ikon för flervalsläge](assets/do-not-localize/canvas-multiple.svg) Markera flera aktiviteter om du vill ta bort alla samtidigt eller kopiera och klistra in dem. [Lär dig hur du kopierar och klistrar in aktiviteter](#copy)

![Roteringsikon](assets/do-not-localize/canvas-rotate.svg) Växla arbetsytan lodrätt.

![Anpassa till skärmikon](assets/do-not-localize/canvas-fit.svg) Anpassa arbetsytans zoomnivå till skärmen.

![Ikonen Zooma ut](assets/do-not-localize/canvas-zoomout.svg) ![Ikonen Zooma in](assets/do-not-localize/canvas-zoomin.svg) Zooma ut eller på arbetsytan.

![Ikon för kampanjinställningar](assets/do-not-localize/canvas-map.svg) Öppnar en ögonblicksbild av arbetsytan som visar att du finns.

### Hantera aktiviteter {#manage}

När du lägger till aktiviteter är åtgärdsknappar tillgängliga i egenskapsrutan, vilket gör att du kan utföra flera åtgärder.

![](assets/activity-action.png)

![Ta bort ikon](assets/do-not-localize/activity-delete.svg) Ta bort aktiviteten från arbetsytan.

![Inaktivera ikon](assets/do-not-localize/activity-disable.svg) ![Aktivera ikon](assets/do-not-localize/activity-enable.svg) Inaktivera/aktivera aktiviteten. När den orchestrerade kampanjen körs, körs inte inaktiverade aktiviteter och följande aktiviteter på samma sökväg och den orchestrerade kampanjen stoppas.

![Ikonen Paus](assets/do-not-localize/activity-pause.svg) ![Ikonen Återuppta](assets/do-not-localize/activity-resume.svg) Pausa/Återuppta aktiviteten. När den Orchestrated-kampanjen körs pausas den vid den pausade aktiviteten. Motsvarande uppgift och alla som följer den i samma sökväg körs inte.

Du kan använda valfri aktivitet på arbetsytan som brytpunkt för att pausa kampanjkörningen. Det innebär att kampanjen endast körs tills den här aktiviteten har pausats. När du pausar körningen håller segmenteringsmotorn temporära data tillgängliga för förhandsgranskning. Du kan välja den inkommande övergången precis före den pausade aktiviteten för att visa de överförda data. Läs mer i det här avsnittet: [Visuell flödesövervakning](../orchestrated/start-monitor-campaigns.md#flow)

![Kopiera ikon](assets/do-not-localize/activity-copy.svg) Kopiera aktiviteten. [Lär dig hur du kopierar och klistrar in aktiviteter](#copy)

![Loggar och uppgifter-ikon](assets/do-not-localize/activity-logs.svg) Åtkomst till aktivitetens loggar och uppgifter.

Flera **målaktiviteter**, till exempel **Kombinera** eller **Ta bort dubbletter**, gör att du kan bearbeta den återstående populationen och inkludera den i en ytterligare utgående övergång. Om du till exempel använder en **delad** -aktivitet består komplementet av den population som inte matchade någon av de tidigare definierade delmängderna. Aktivera alternativet **[!UICONTROL Generate complement]** om du vill använda den här funktionen.

### Kopiera och klistra in aktiviteter {#copy}

Du kan kopiera aktiviteter och klistra in dem på valfri Orchestrated-kampanjarbetsyta. Målkampanjen kan finnas på en annan webbläsarflik.

* Om du vill kopiera en aktivitet klickar du på knappen ![Kopiera ikon](assets/do-not-localize/activity-copy.svg) i aktivitetsegenskapsfönstret.
* Om du vill kopiera flera aktiviteter klickar du på ikonen ![Flera markeringslägen](assets/do-not-localize/canvas-multiple.svg) i verktygsfältet på arbetsytan.

| Kopiera en aktivitet | Kopiera flera aktiviteter |
|  ---  |  ---  |
| ![](assets/orchestrated-copy-1.png){width="200" align="center" zoomable="yes"} | ![](assets/orchestrated-copy-2.png){width="200" align="center" zoomable="yes"} |

Klistra in aktiviteterna genom att klicka på knappen **+** för en övergång och välja Klistra in x-aktivitet.

![](assets/orchestrated-copy-3.png){zoomable="yes"}{width="50%"}

## Diagramexempel {#example}

Här är ett exempel på en Orchestrated-kampanj som utformats för att skicka ett e-postmeddelande till alla kunder som har köpt minst 100$, med undantag för alla kunder som har färre än 50 förmånspoäng.

![](assets/canvas-example-diagram.png){zoomable="yes"}

För att uppnå detta har följande aktiviteter lagts till:

* En **[!UICONTROL Fork]**-aktivitet delar upp den orkestrerade kampanjen i tre sökvägar.
* **[!UICONTROL Build audience]** aktiviteter riktar sig till de tre uppsättningarna kunder:

   * Kunder med e-post
   * Kunder som har köpt minst 100$,
   * Kunder som har mindre än 50 poäng för lojalitet.

* En **[!UICONTROL Combine]**-aktivitet grupperar kunder med ett e-postmeddelande och de som har köpt minst 100$,
* En **[!UICONTROL Combine]**-aktivitet exkluderar kunder med mindre än 50 förmånspoäng,
* En **[!UICONTROL Email delivery]**-aktivitet skickar ett e-postmeddelande till de resulterande kunderna.

## Nästa steg {#next}

När du har utformat det orchestrerade kampanjdiagrammet kan du köra den orkestrerade kampanjen och spåra förloppet för dess olika uppgifter. [Lär dig hur du startar en Orchestrated-kampanj och övervakar dess körning](start-monitor-campaigns.md)
