---
title: Skicka direktutskick med resor
description: Lär dig hur du skapar och skickar direktreklam med resor.
feature: Direct Mail
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
robots: noindex
googlebot: noindex
keywords: direktreklam, meddelande, kampanj
exl-id: 44886355-ee3a-4323-899a-35d967487924
source-git-commit: ca6e2834f92585094d3316e9259e3370cfad22fc
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 0%

---

# Skicka direktutskick med resor {#direct-mail-journeys}

>[!CONTEXTUALHELP]
>id="ajo_journey_direct_mail"
>title="Avsluta aktivitet"
>abstract="Direktreklam är en offlinekanal som gör att du kan anpassa och generera extraheringsfiler som tredjepartsleverantörer av direktreklam behöver för att skicka e-post till dina kunder."

Direktreklam är en offlinekanal som gör att du kan anpassa och generera extraheringsfiler som tredjepartsleverantörer av direktreklam behöver för att skicka e-post till dina kunder.

När du skapar ett direktmeddelandemeddelande genererar [!DNL Journey Optimizer] automatiskt en fil som innehåller alla målprofiler och valda data, till exempel postadresser och profilattribut. Den här filen skickas till valfri server så att den kan nås av den externa direktreklamleverantören, som hanterar den faktiska utskicksprocessen åt dig.

Du måste samarbeta med den valda tredjepartsleverantören av direktreklam för att få kundernas samtycke, om tillämpligt, så att dina kunder kan ta emot e-post från dig. Användningen av posttjänster regleras av ytterligare villkor från den tillämpliga tredjepartsleverantören av direktreklam. Adobe kontrollerar inte och ansvarar inte för din användning av tredjepartsprodukter. Om du har frågor eller vill ha hjälp med att skicka direktreklam kontaktar du en tredjepartsleverantör av direktreklam.

>[!NOTE]
>
>Den här sidan beskriver processen att skapa och skicka direktreklam med resor. Mer information om direktreklamkanalen och hur du skapar direktreklamkampanjer finns i följande avsnitt: [Kom igång med direktreklam](../direct-mail/get-started-direct-mail.md).

## Skapa en filflödeskonfiguration

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_frequency"
>title="Välj AWS"
>abstract="Om din filroutningskonfiguration ska skickas med resor kan du ange hur ofta filen ska skickas till servern."

Innan du skapar ett meddelande för direkt e-post bör du kontrollera att du har konfigurerat en filroutningskonfiguration som anger på vilken server extraheringsfilen ska överföras och lagras. Gör så här:

1. Gå till menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Direct mail settings]** > **[!UICONTROL File routing]** och klicka sedan på **[!UICONTROL Create file routing config]**.

1. Definiera konfigurationsegenskaperna för filroutning, till exempel dess namn, och vilken typ av server som ska användas. Detaljerad information om hur du konfigurerar en filroutningskonfiguration finns i avsnittet [Direktpostkonfiguration](../direct-mail/direct-mail-configuration.md#file-routing-configuration).

   Om din filroutningskonfiguration ska skickas med resor kan du ange hur ofta filen ska skickas till servern.

   ![](assets/file-routing-journey.png)

1. Klicka på **[!UICONTROL Submit]** för att bekräfta skapandet av filroutningskonfigurationen. Konfigurationen skapas med statusen **[!UICONTROL Active]**. Den är nu klar att refereras i en direktadresskonfiguration.

## Skapa en konfiguration för direktreklam {#direct-mail-surface}

En konfiguration för direktreklam innehåller formateringsinställningarna för filen som innehåller målgruppsdata och kommer att användas av e-postleverantören. Du måste också definiera var filen ska exporteras genom att välja filroutningskonfigurationen. Detaljerad information om hur du skapar en konfiguration för direktreklam finns i avsnittet [Konfiguration av direktreklam](../direct-mail/direct-mail-configuration.md#file-routing-configuration).

När konfigurationen för direktreklam är klar kan du lägga till en direktreklamåtgärd på resan.

## Lägg till en Direct mail-åtgärd på din resa

Följ de här stegen för att lägga till en åtgärd för direktreklam i en resa:

1. Öppna resan och dra och släpp en **[!UICONTROL Direct mail]**-aktivitet från **Åtgärder**-delen av paletten.

1. Ange grundläggande information i meddelandet (etikett, beskrivning, kategori) och välj sedan den meddelandekonfiguration som ska användas. Fältet **[!UICONTROL configuration]** är som standard förfyllt med den senaste konfigurationen som används av användaren för den kanalen. Mer information om hur du konfigurerar en resa finns på [den här sidan](../building-journeys/journey-gs.md).

1. Konfigurera extraheringsfilen som ska skickas till din direktmeddelandeleverantör. Klicka på knappen **[!UICONTROL Edit content]** om du vill göra det.

   ![](assets/direct-mail-add-journey.png)

1. Justera extraheringsfilens egenskaper, t.ex. filnamnet eller kolumnerna som ska visas. Mer information om hur du konfigurerar extraheringsfilens egenskaper finns i följande avsnitt: [Skapa ett direktmeddelandemeddelande](../direct-mail/create-direct-mail.md#extraction-file).

   ![](assets/direct-mail-journey-content.png)

1. När innehållet i extraheringsfilen har definierats kan du använda testprofiler för att förhandsgranska det. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

   Om du vill göra det klickar du på **[!UICONTROL Simulate content]** och lägger sedan till en testprofil för att kontrollera hur extraheringsfilens återgivning använder testprofildata. Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehåll finns i avsnittet [Innehållshantering](../content-management/preview-test.md).

   ![](assets/direct-mail-simulate.png){width="800" align="center"}

När extraheringsfilen är klar slutför du konfigurationen av din [resa](../building-journeys/journey-gs.md) för att skicka den.
