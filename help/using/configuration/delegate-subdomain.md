---
title: Delegera underdomäner
description: Lär dig hur du delegerar dina underdomäner
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
feature: Applikationsinställningar
topic: Administrering
role: Admin
level: Intermediate
source-git-commit: 63de381ea3a87b9a77bc6f1643272597b50ed575
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 9%

---


# Delegera en underdomän

Delegering av domännamn är en metod som tillåter ägaren av ett domännamn (tekniskt: en DNS-zon) för att delegera en indelning av den (tekniskt: en DNS-zon under den, som kan kallas en underzon) till en annan entitet. Om en kund hanterar zonen&quot;example.com&quot; kan han delegera underzonen&quot;marketing.example.com&quot; till Adobe.

Genom att delegera en underdomän för användning med [!DNL Journey Optimizer] kan klienterna förlita sig på att Adobe upprätthåller den DNS-infrastruktur som krävs för att uppfylla branschstandardkraven för leverans för avsändardomäner för e-postmarknadsföring, samtidigt som de behåller och kontrollerar DNS för sina interna e-postdomäner.

[!DNL Journey Optimizer] kan du delegera dina underdomäner till Adobe direkt från produktgränssnittet. På så sätt kan Adobe leverera meddelanden som en hanterad tjänst genom att kontrollera och underhålla alla aspekter av DNS som krävs för att leverera, återge och spåra e-postkampanjer.

>[!NOTE]
>
>Som standard kan du med [!DNL Journey Optimizer] licensavtal delegera upp till 10 underdomäner. Kontakta Adobe om du vill öka begränsningen.
>
>Journey Optimizer stöder för närvarande inte användning av CNAME för delegering av underdomäner.

Följ stegen nedan om du vill delegera en ny underdomän:

1. Gå till menyn **[!UICONTROL Channels]** / **[!UICONTROL Subdomains]** och klicka sedan på **[!UICONTROL Delegate subdomain]**.

   ![](../assets/subdomain-delegate.png)

1. Ange namnet på den underdomän som ska delegeras.

   ![](../assets/subdomain-name.png)

   >[!CAUTION]
   >
   >Kontrollera att du har angett en giltig underdomän, till exempel marketing.company.com. Det är inte tillåtet att delegera en ogiltig underdomän till Adobe.

1. Listan med poster som ska placeras på dina DNS-servrar visas. Kopiera de här posterna, antingen en efter en eller genom att hämta en CSV-fil, och navigera sedan till din värdlösning för domänen för att generera matchande DNS-poster.

   Kontrollera att alla DNS-poster har skapats i din domänvärdslösning. Om allt är korrekt konfigurerat markerar du rutan &quot;Jag bekräftar ...&quot; och klickar sedan på **[!UICONTROL Submit]**.

   ![](../assets/subdomain-submit.png)

   >[!NOTE]
   >
   >Du kan skapa posterna och skicka konfigurationen för underdomänen senare med knappen **[!UICONTROL Save as draft]**. Du kan sedan återuppta delegeringen av underdomäner genom att öppna den från listan över underdomäner.

1. När underdomänsdelegeringen har skickats visas underdomänen i listan med statusen **[!UICONTROL Processing]**. Mer information om underdomäners status finns i [det här avsnittet](access-subdomains.md).

   Kontrollerna och åtgärderna nedan utförs tills underdomänen har verifierats och kan användas för att skicka meddelanden.

   Det här steget utförs av Adobe och kan ta upp till 3 timmar.

   1. Kontrollera om underdomänen har delegerats till Adobe DNS (NS-post, SOA-post, zoninställningar, ägarskapspost),
   1. Konfigurera DNS för domänen,
   1. Skapa spårnings- och spegeladresser,
   1. Provisionera CDN Cloud Front,
   1. Skapa, validera och bifoga CDN SSL-certifikat,
   1. Skapa Framåtriktad DNS,
   1. Skapa PTR-post.

   ![](../assets/subdomain-processing.png)

1. När kontrollerna är slutförda får underdomänen **[!UICONTROL Success]**-status. Den är klar att användas för att leverera meddelanden.

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/subdomain-notification.png)


