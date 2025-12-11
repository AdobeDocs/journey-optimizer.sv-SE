---
solution: Journey Optimizer
product: journey optimizer
title: Koda eget e-postinnehåll
description: Lär dig koda ditt eget e-postinnehåll
feature: Email Design
topic: Content Management
role: User
level: Intermediate, Experienced
keywords: kod, HTML, redigerare
exl-id: 5fb79300-08c6-4c06-a77c-d0420aafca31
source-git-commit: 48b3ef3d2e041ea49d1b0c91cc72ea04237a5e33
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Koda eget innehåll {#code-content}

Använd läget **[!UICONTROL Code your own]** för att importera råformaterat HTML och/eller koda ditt e-postinnehåll. Den här metoden kräver HTML kunskaper.

➡️ [Upptäck den här funktionen i en video](#video)

>[!CAUTION]
>
> Det går inte att referera till bilder från [Adobe Experience Manager Assets](../integrations/assets.md) när den här metoden används. De bilder som refereras i din HTML-kod måste lagras på en offentlig plats.

1. Välj **[!UICONTROL Code your own]** på startsidan för e-post till Designer.

   ![](assets/code-your-own.png)

1. Ange eller klistra in HTML-råkod.

1. Använd den vänstra rutan för att utnyttja [!DNL Journey Optimizer]-personaliseringsfunktioner. [Läs mer](../personalization/personalize.md)

   ![](assets/code-editor.png)

   >[!NOTE]
   >
   >Personaliseringsredigeraren i e-postprogrammet Designer har vissa funktionsbegränsningar jämfört med reseuttryck. [Läs mer om begränsningar för datum/tid-funktioner](#date-time-limitations)

1. Om du vill ta bort ditt e-postinnehåll och starta e-postmeddelandet från en ny design väljer du **[!UICONTROL Change your design]** på Alternativ-menyn.

   ![](assets/code-editor-change-design.png)

   >[!NOTE]
   >
   >Den här åtgärden öppnar den markerade mallen i e-post-Designer. Därifrån kan du antingen slutföra designen av ditt e-postmeddelande eller gå tillbaka till kodredigeraren med alternativet **[!UICONTROL Switch to code editor]**.

1. Klicka på knappen **[!UICONTROL Preview]** om du vill kontrollera meddelandets design och anpassning med testprofiler. [Läs mer](../content-management/preview-test.md)

   ![](assets/code-editor-preview.png)

1. När koden är klar klickar du på **[!UICONTROL Save]** och går sedan tillbaka till skärmen för att skapa meddelandet för att slutföra meddelandet.

   ![](assets/code-editor-save.png)

## Funktionsbegränsningar för datum och tid {#date-time-limitations}

När du använder personalisering i kodredigeraren för e-post-Designer är funktionen `now()` inte tillgänglig för dynamiska datumberäkningar.

>[!IMPORTANT]
>
>Funktionen `now()` stöds **inte** i e-postbyggarens uttrycksspråk. Även om `now()` är tillgängligt under resan kan den inte användas i e-postinnehåll eller kodredigeraren.

**Tillgängliga alternativ:**

Använd följande funktioner för att arbeta med aktuellt datum och aktuell tid i e-postpersonalisering:

* **`getCurrentZonedDateTime()`** - Returnerar aktuellt datum och aktuell tid med tidszonsinformation. Detta är det rekommenderade alternativet till `now()`.

  Exempel: `{%= getCurrentZonedDateTime() %}` returnerar `2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]`

* **`currentTimeInMillis()`** - Returnerar aktuell tid i epok i millisekunder.

  Exempel: `{%= currentTimeInMillis() %}`

**Rekommenderade tillfälliga lösningar:**

Om du behöver utföra datumberäkningar i ditt e-postinnehåll:

* **Förberäkna datumfält** - Beräkna obligatoriska datumvärden i din datariod eller profilattribut innan du skickar e-postmeddelandet och referera sedan till dessa förberäknade värden i din personalisering.

  Exempel: `{%= profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate %}`

* **Använd funktioner för datumändring** - Använd [datum-/tidsfunktioner](../personalization/functions/dates.md) som `dayOfYear()` eller `diffInDays()` med datumvärden från profilattribut.

  Exempel: `{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}`

* **Använd beräknade attribut** - Skapa [beräknade attribut](../audience/computed-attributes.md) som utför komplexa datumberäkningar och gör resultaten tillgängliga som profilattribut.

Läs mer om [Funktioner för datum och tid i personalisering](../personalization/functions/dates.md).
