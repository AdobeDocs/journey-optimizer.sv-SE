---
solution: Journey Optimizer
product: journey optimizer
title: Skapa segmentdefinitioner
description: Lär dig skapa målgrupper med hjälp av segmentdefinitioner
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 289aac5d-6cdb-411f-985e-3acef58050a8
source-git-commit: b9d70bf2b3e16638a03b59fd4036771ad959a631
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 2%

---

# Skapa segmentdefinitioner {#build-segments}

>[!CONTEXTUALHELP]
>id="ajo_ao_create_rule"
>title="Skapa en regel"
>abstract="Med metoden Skapa regel kan du skapa en ny målgruppsdefinition med Adobe Experience Platform Segmentation Service."

I det här exemplet kommer vi att bygga en målgrupp för alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980. Alla dessa kunder bör ha öppnat Luma-applikationen inom de senaste 7 dagarna och sedan köpt den inom 2 timmar efter att ansökan öppnats.

➡️ [Lär dig skapa målgrupper i den här videon](#video-segment)

1. Klicka på knappen **[!UICONTROL Create audience]** på menyn **[!UICONTROL Audiences]** och välj **[!UICONTROL Build rule]**.

   ![](assets/create-segment.png)

   På segmentdefinitionsskärmen kan du konfigurera alla obligatoriska fält för att definiera målgruppen. Lär dig hur du konfigurerar målgrupper i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html){target="_blank"}.

   ![](assets/segment-builder.png)

1. Ange ett namn och en beskrivning (valfritt) för målgruppen i rutan **[!UICONTROL Audience properties]**.

   ![](assets/segment-properties.png)

1. Dra och släpp önskade fält från den vänstra rutan till arbetsytan i mitten och konfigurera dem efter behov.

   >[!NOTE]
   >
   >Observera att fälten som är tillgängliga i den vänstra rutan varierar beroende på hur scheman **XDM Individual Profile** och **XDM ExperienceEvent** har konfigurerats för din organisation.  Läs mer i [XDM-dokumentationen (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

   ![](assets/drag-fields.png)

   I det här exemplet måste vi förlita oss på fälten **Attribut** och **Händelser** för att skapa målgruppen:

   * **Attribut**: profiler som bor i Atlanta, San Francisco eller Seattle, födda efter 1980

     ![](assets/add-attributes.png)

   * **Händelser**: profiler som öppnat Luma-programmet inom de senaste 7 dagarna och sedan gjort ett köp inom två timmar efter att programmet öppnats.

     ![](assets/add-events.png)

     >[!NOTE]
     >
     >Adobe rekommenderar att du inte använder öppna och skicka händelser med direktuppspelningssegmentering. Använd istället riktiga användaraktivitetssignaler som klickningar, köp eller beacon-data. Använd affärsregler i stället för att skicka händelser för frekvens- eller undertryckningslogik. [Läs mer](about-audiences.md#open-and-send-event-guardrails)

1. När du lägger till och konfigurerar nya fält på arbetsytan uppdateras rutan **[!UICONTROL Audience Properties]** automatiskt med information om de uppskattade profilerna som tillhör målgruppen.

   ![](assets/segment-estimate.png)

1. När målgruppen är klar klickar du på **[!UICONTROL Save]**. Den visas i listan över Adobe Experience Platform målgrupper. Observera att det finns ett sökfält som du kan använda för att söka efter en viss målgrupp i listan.

Publiken kan nu användas på era resor. Mer information om detta finns i [det här avsnittet](../audience/about-audiences.md).

## Instruktionsvideo{#video-segment}

Förstå hur Journey Optimizer använder regler för att generera målgrupper och lär sig hur man använder attribut, händelser och befintliga målgrupper för att skapa en målgrupp.

>[!VIDEO](https://video.tv.adobe.com/v/3425020?quality=12)
