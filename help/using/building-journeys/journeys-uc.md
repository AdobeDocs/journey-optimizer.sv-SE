---
solution: Journey Optimizer
product: journey optimizer
title: Användningsexempel på resor
description: Användningsexempel på resor
feature: Journeys, Use cases, Email, Push
topic: Content Management
role: User, Data Engineer
level: Intermediate, Experienced
keywords: användningsfall, flerkanal, meddelanden, resa, kanal, händelser, push
exl-id: a1bbfcee-2235-4820-a391-d5d35f499cb0
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 2%

---

# Användningsfall: skicka flerkanalsmeddelanden{#send-multi-channel-messages}

I det här avsnittet visas ett användningsexempel som kombinerar en Läs publik, en händelse, reaktionshändelser och e-post/push-meddelanden.

![](assets/jo-uc1.png)

## Beskrivning av användningsfallet

I det här fallet vill vi skicka ett första meddelande (e-post och push) till alla kunder som tillhör en viss målgrupp.

Baserat på deras reaktion på det första meddelandet vill vi skicka specifika meddelanden.

Efter det första meddelandet väntar vi en dag på att kunderna ska öppna push-meddelandet eller e-postmeddelandet. Om vi inte får någon reaktion skickar vi ett uppföljningsmejl till dem.

Sedan väntar vi på ett köp och skickar ett push-meddelande till kunden för att tacka.

## Förutsättningar

För att detta ska fungera måste du konfigurera följande:

* en målgrupp för alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980.
* en köphändelse

### Skapa målgruppen

Under vår resa vill vi lyfta fram en specifik kundgrupp. Alla personer som tillhör målgruppen deltar i resan och följer de olika stegen. I vårt exempel behöver vi en målgrupp för alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980.

Mer information om målgrupper finns i [page](../audience/about-audiences.md).

1. Välj **[!UICONTROL Audiences]**.

1. Klicka på **[!UICONTROL Create audience]** som finns längst upp till höger i målgruppslistan.

1. I **[!UICONTROL Audience properties]** anger du ett namn för målgruppen.

1. Dra och släpp önskade fält från den vänstra rutan till arbetsytan i mitten och konfigurera dem sedan efter behov. I detta exempel använder vi **Ort** och **Födelseår** attributfält.

1. Klicka på **[!UICONTROL Save]**.

   ![](assets/add-attributes.png)

Publiken är nu skapad och redo att användas på din resa. Använda **Läs målgrupp** kan du göra så att alla personer som tillhör målgruppen kommer in på resan.

### Konfigurera händelsen

Du måste konfigurera ett evenemang som skickas till din resa när en kund gör ett köp. När resan tar emot händelsen utlöses meddelandet&quot;Tack&quot;.

För detta använder vi en regelbaserad händelse. Mer information om händelser finns i [page](../event/about-events.md).

1. I avsnittet ADMINISTRATION-menyn väljer du **[!UICONTROL Configurations]** och sedan klicka **[!UICONTROL Events]**. Klicka på **[!UICONTROL Create event]** för att skapa en ny händelse.

1. Ange namnet på händelsen.

1. Markera **[!UICONTROL Event ID type]** i fältet **[!UICONTROL Rule Based]**.

1. Definiera **[!UICONTROL Schema]** och nyttolast **[!UICONTROL Fields]**. Du kan använda flera fält, till exempel den köpta produkten, inköpsdatumet och inköps-ID:t.

1. I **[!UICONTROL Event ID condition]** definierar du det villkor som används av systemet för att identifiera de händelser som utlöser din resa. Du kan till exempel lägga till en `purchaseMessage` och definiera följande regel: `purchaseMessage="thank you"`

1. Definiera **[!UICONTROL Namespace]** och **[!UICONTROL Profile Identifier]**.

1. Klicka på **[!UICONTROL Save]**.

   ![](assets/jo-uc2.png)

Händelsen är nu konfigurerad och klar att användas under din resa. Genom att använda motsvarande händelseaktivitet kan du aktivera en åtgärd varje gång en kund gör ett köp.

## Designa resan

1. Påbörja resan med en **Läs målgrupp** aktivitet. Välj den målgrupp som skapats tidigare. Alla personer som tillhör målgruppen deltar i resan.

   ![](assets/jo-uc4.png)

1. Släpp **E-post** Åtgärdsaktivitet och definiera innehållet i det&quot;första meddelandet&quot;. Det här meddelandet skickas till alla personer på resan. Se detta [section](../email/create-email.md) om du vill lära dig hur du konfigurerar och utformar ett e-postmeddelande.

   ![](assets/jo-uc5.png)

1. Placera markören på e-postaktiviteten och klicka på plustecknet (+) för att skapa en ny sökväg.

1. Lägg till en **Reaktion** event och select **Push öppnad**. Händelsen utlöses när en person som tillhör målgruppen öppnar den push-versionen av det första meddelandet.

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

1. Klicka på **Testa** för att aktivera testläget, som finns i det övre högra hörnet. Se detta [section](testing-the-journey.md) för att lära dig hur du använder testläget.

1. När resan är klar publicerar du den med **Publicera** i det övre högra hörnet.
