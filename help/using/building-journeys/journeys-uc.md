---
solution: Journey Optimizer
product: journey optimizer
title: Användningsexempel på resor
description: Användningsexempel på resor
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: a1bbfcee-2235-4820-a391-d5d35f499cb0
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 2%

---

# Användningsfall: skicka flerkanalsmeddelanden{#send-multi-channel-messages}

I det här avsnittet presenteras ett användningsexempel som kombinerar ett Läs segment, en händelse, reaktionshändelser och e-post-/push-meddelanden.

![](assets/jo-uc1.png)

## Beskrivning av användningsfallet

I det här fallet vill vi skicka ett första meddelande (e-post och push) till alla kunder som tillhör ett visst segment.

Vi vill skicka specifika meddelanden utifrån deras reaktion på det första meddelandet.

Efter det första meddelandet väntar vi en dag på att kunderna ska öppna push-meddelandet eller e-postmeddelandet. Om vi inte får någon reaktion skickar vi ett uppföljningsmejl till dem.

Sedan väntar vi på ett köp och skickar ett push-meddelande till kunden för att tacka.

## Förutsättningar

För att detta ska fungera måste du konfigurera följande:

* ett segment för alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980.
* en köphändelse

### Skapa segmentet

Under vår resa vill vi utnyttja ett specifikt kundsegment. Alla personer som tillhör segmentet går in på resan och följer de olika stegen. I vårt exempel behöver vi ett segment som riktar sig till alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980.

Mer information om segment finns i [page](../segment/about-segments.md).

1. Välj **[!UICONTROL Segments]**.

1. Klicka på **[!UICONTROL Create segment]** som finns längst upp till höger i segmentlistan.

1. I **[!UICONTROL Segment properties]** anger du ett namn för segmentet.

1. Dra och släpp önskade fält från den vänstra rutan till arbetsytan i mitten och konfigurera dem sedan efter behov. I det här exemplet använder vi **Ort** och **Födelseår** attributfält.

1. Klicka på **[!UICONTROL Save]**.

   ![](assets/add-attributes.png)

Segmentet är nu skapat och klart att användas på din resa. Använda en **Läs segment** kan du göra så att alla personer som tillhör segmentet kommer in på resan.

### Konfigurera händelsen

Du måste konfigurera ett evenemang som skickas till din resa när en kund gör ett köp. När resan tar emot händelsen utlöses meddelandet&quot;Tack&quot;.

För detta använder vi en regelbaserad händelse. Mer information om händelser finns i [page](../event/about-events.md).

1. Välj **[!UICONTROL Configurations]** och sedan klicka **[!UICONTROL Events]**. Klicka på **[!UICONTROL Create event]** för att skapa en ny händelse.

1. Ange namnet på händelsen.

1. Markera **[!UICONTROL Event ID type]** i fältet **[!UICONTROL Rule Based]**.

1. Definiera **[!UICONTROL Schema]** och nyttolast **[!UICONTROL Fields]**. Du kan använda flera fält, till exempel den köpta produkten, inköpsdatumet och inköps-ID:t.

1. I **[!UICONTROL Event ID condition]** definierar du det villkor som används av systemet för att identifiera de händelser som utlöser din resa. Du kan till exempel lägga till en `purchaseMessage` och definiera följande regel: `purchaseMessage="thank you"`

1. Definiera **[!UICONTROL Namespace]** och **[!UICONTROL Profile Identifier]**.

1. Klicka på **[!UICONTROL Save]**.

   ![](assets/jo-uc2.png)

Händelsen är nu konfigurerad och klar att användas under din resa. Genom att använda motsvarande händelseaktivitet kan du aktivera en åtgärd varje gång en kund gör ett köp.

## Designa resan

1. Påbörja resan med en **Läs segment** aktivitet. Markera det segment som skapades tidigare. Alla personer som tillhör segmentet deltar i resan.

   ![](assets/jo-uc4.png)

1. Släpp **E-post** Åtgärdsaktivitet och definiera innehållet i det&quot;första meddelandet&quot;. Det här meddelandet skickas till alla personer på resan. Se detta [section](../email/create-email.md) om du vill lära dig hur du konfigurerar och utformar ett e-postmeddelande.

   ![](assets/jo-uc5.png)

1. Placera markören på e-postaktiviteten och klicka på plustecknet (+) för att skapa en ny sökväg.

1. Lägg till en **Reaktion** event och select **Push öppnad**. Händelsen utlöses när en person som tillhör segmentet öppnar den push-versionen av det första meddelandet.

1. Lägg till en **Reaktion** event och select **E-post öppnad**. Händelsen utlöses när personen öppnar e-postmeddelandet.

1. I någon av reaktionsaktiviteterna ska du kontrollera **Definiera tidsgränsen för händelsen** , definiera en varaktighet (1 dag i exemplet) och markera **Ange en tidsgränssökväg**. Detta skapar en ny sökväg för personer som inte öppnar det första push- eller e-postmeddelandet.

   >[!NOTE]
   >
   >När du konfigurerar en timeout för flera händelser (de två reaktionerna i det här fallet) behöver du bara konfigurera timeout för en av dessa händelser.

1. Släpp en **E-post** Åtgärdsaktivitet och definiera innehållet i&quot;uppföljningsmeddelandet&quot;. Det här meddelandet skickas till de personer som inte öppnar e-postmeddelandet eller skickar det första meddelandet nästa dag. Se detta [section](../email/create-email.md) om du vill lära dig hur du konfigurerar och utformar ett e-postmeddelande.

1. Koppla de tre sökvägarna till inköpshändelsen som skapades tidigare. Händelsen utlöses när en person gör ett köp.

1. Efter händelsen släpper du en **Push** aktiviteten och definiera innehållet i tackmeddelandet. Se detta [section](../push/create-push.md) om du vill lära dig hur du konfigurerar och utformar en push-lösning.

## Testa och publicera resan

1. Innan du testar din resa kontrollerar du att den är giltig och att det inte finns något fel.

1. Klicka på **Testa** för att aktivera testläget, som finns i det övre högra hörnet. Definiera hur du vill att testprofiler ska ange testet: en enda profil, eller upp till 100 samtidigt. Se detta [section](testing-the-journey.md) för att lära dig hur du använder testläget.

1. När resan är klar publicerar du den med **Publicera** i det övre högra hörnet.
