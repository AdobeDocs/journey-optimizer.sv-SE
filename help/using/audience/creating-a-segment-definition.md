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
source-git-commit: 43e13026b739e855ed82603531802e29af1ada18
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 4%

---

# Skapa segmentdefinitioner {#build-segments}

>[!CONTEXTUALHELP]
>id="ajo_ao_create_rule"
>title="Skapa en regel"
>abstract="Med metoden Skapa regel kan du skapa en ny målgruppsdefinition med Adobe Experience Platform Audience Service."

I det här exemplet kommer vi att bygga en målgrupp för alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980. Alla dessa kunder bör ha öppnat Luma-applikationen inom de senaste 7 dagarna och sedan köpt den inom 2 timmar efter att ansökan öppnats.

➡️ [Lär dig hur du skapar målgrupper i den här videon](#video-segment)

1. Från **[!UICONTROL Audiences]** klickar du på **[!UICONTROL Create audience]** knapp och markera **[!UICONTROL Build rule]**.

   ![](assets/create-segment.png)

   På segmentdefinitionsskärmen kan du konfigurera alla obligatoriska fält för att definiera målgruppen. Lär dig konfigurera målgrupper i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html){target="_blank"}.

   ![](assets/segment-builder.png)

1. I **[!UICONTROL Audience properties]** anger du ett namn och en beskrivning (valfritt) för målgruppen.

   ![](assets/segment-properties.png)

1. Dra och släpp önskade fält från den vänstra rutan till arbetsytan i mitten och konfigurera dem efter behov.

   >[!NOTE]
   >
   >Observera att fälten som är tillgängliga i den vänstra rutan varierar beroende på hur **Individuell XDM-profil** och **XDM ExperienceEvent** scheman har konfigurerats för din organisation.  Läs mer i [XDM-dokumentation (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv){target="_blank"}.

   ![](assets/drag-fields.png)

   I det här exemplet måste vi förlita oss på **Attribut** och **Händelser** fält för att skapa målgruppen:

   * **Attribut**: profiler i Atlanta, San Francisco eller Seattle, född efter 1980

     ![](assets/add-attributes.png)

   * **Händelser**: profiler som har öppnat Luma-programmet inom de senaste 7 dagarna och sedan köpt det inom 2 timmar efter att programmet öppnats.

     ![](assets/add-events.png)

1. När du lägger till och konfigurerar nya fält på arbetsytan visas **[!UICONTROL Audience Properties]** uppdateras automatiskt med information om de uppskattade profilerna som tillhör målgruppen.

   ![](assets/segment-estimate.png)

1. När målgruppen är klar klickar du **[!UICONTROL Save]**. Den visas i listan över Adobe Experience Platform målgrupper. Observera att det finns ett sökfält som du kan använda för att söka efter en viss målgrupp i listan.

Publiken kan nu användas på era resor. Mer information om detta finns i [det här avsnittet](../audience/about-audiences.md).

## Instruktionsvideo{#video-segment}

Lär dig skapa målgrupper.

>[!VIDEO](https://video.tv.adobe.com/v/334281?quality=12)
