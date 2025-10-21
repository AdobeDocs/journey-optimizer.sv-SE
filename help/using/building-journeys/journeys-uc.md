---
solution: Journey Optimizer
product: journey optimizer
title: Användningsexempel på resor
description: Användningsexempel på resor
feature: Journeys, Use Cases, Email, Push
topic: Content Management
role: User, Developer
level: Intermediate, Experienced
keywords: användningsfall, flerkanal, meddelanden, resa, kanal, händelser, push
exl-id: a1bbfcee-2235-4820-a391-d5d35f499cb0
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# Skicka flerkanalsmeddelanden {#send-multi-channel-messages}

I det här avsnittet visas ett användningsexempel som kombinerar en Läs publik, en händelse, reaktionshändelser och e-post/push-meddelanden.

![](assets/jo-uc1.png)

## Beskrivning av användningsfallet

I det här fallet är målet att skicka ett första e-postmeddelande till alla kunder som tillhör en viss målgrupp.

Beroende på deras reaktion på det första meddelandet skickas specifika uppföljningsmeddelanden.

Om kunden öppnar e-postmeddelandet väntar systemet på ett köp och skickar ett push-meddelande till kunden som tackar.

Om inget svar kommer skickas ett uppföljningsmejl.

## Förhandskrav

Konfigurera följande för att det här ska fungera:

* En publik för alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980
* En köphändelse

### Skapa målgruppen

Under den här resan utnyttjas en viss målgrupp av kunder. Alla personer som tillhör målgruppen deltar i resan och följer de olika stegen. I det här exemplet riktar sig publiken till alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980.

Mer information om målgrupper finns på [den här sidan](../audience/about-audiences.md).

1. Välj **[!UICONTROL Audiences]** i KUNDENS menyavsnitt.
1. Klicka på knappen **[!UICONTROL Create audience]** längst upp till höger i målgruppslistan.
1. Ange ett namn för målgruppen i rutan **[!UICONTROL Audience properties]**.
1. Dra och släpp önskade fält från den vänstra rutan till arbetsytan i mitten och konfigurera dem efter behov. I det här exemplet använder du attributfälten **City** och **Birth year** .
1. Klicka på **[!UICONTROL Save]**.

   ![](assets/add-attributes.png)

Publiken är nu skapad och redo att användas under resan. Med en **Läs målgrupp**-aktivitet kan alla personer som tillhör målgruppen komma in på resan.

### Konfigurera händelsen

Konfigurera en händelse som skickas till resan när en kund gör ett köp. När resan tar emot händelsen utlöses meddelandet&quot;Tack&quot;.

Använd en [regelbaserad händelse](../event/about-events.md) för detta.

1. I avsnittet ADMINISTRATION-meny väljer du **[!UICONTROL Configurations]** och klickar sedan på **[!UICONTROL Events]**. Klicka på **[!UICONTROL Create event]** för att skapa en ny händelse.

1. Ange namnet på händelsen.

1. Markera **[!UICONTROL Event ID type]** i fältet **[!UICONTROL Rule Based]**.

1. Definiera **[!UICONTROL Schema]** och nyttolasten **[!UICONTROL Fields]**. Använd flera fält, t.ex. den köpta produkten, inköpsdatumet och inköps-ID:t.

1. I fältet **[!UICONTROL Event ID condition]** definierar du villkoret som används av systemet för att identifiera de händelser som utlöser resan. Lägg till ett `purchaseMessage`-fält och definiera följande regel: `purchaseMessage="thank you"`

1. Definiera **[!UICONTROL Namespace]** och **[!UICONTROL Profile Identifier]**.

1. Klicka på **[!UICONTROL Save]**.

   ![](assets/jo-uc2.png)

Händelsen är nu konfigurerad och klar att användas under resan. Med motsvarande händelseaktivitet kan en åtgärd utlösas varje gång en kund gör ett köp.

## Designa resan

1. Starta resan med aktiviteten **Läs målgrupp**. Välj den målgrupp som skapats tidigare. Alla personer som tillhör målgruppen deltar i resan.

   ![](assets/jo-uc4.png)

1. Släpp en **e-postaktivitet** och definiera innehållet i det&quot;första meddelandet&quot;. Det här meddelandet skickas till alla personer på resan. Läs i det här [avsnittet](../email/create-email.md) om du vill veta mer om hur du konfigurerar och utformar ett e-postmeddelande.

   ![](assets/jo-uc5.png)

1. Lägg till en **reaktion**-händelse och välj **E-post öppnad**. Händelsen utlöses när en person som tillhör målgruppen öppnar e-postmeddelandet.

1. Markera rutan **Definiera tidsgräns för händelse**, definiera en varaktighet (1 dag i det här exemplet) och markera **Ange en tidsgräns**. Detta skapar en ny sökväg för personer som inte öppnar det första push- eller e-postmeddelandet.

1. Släpp en **E-post** -åtgärdsaktivitet i timeoutsökvägen och definiera innehållet i &quot;uppföljningsmeddelandet&quot;. Det här meddelandet skickas till de personer som inte öppnar e-postmeddelandet eller skickar det första meddelandet inom nästa dag. [Lär dig hur du konfigurerar och utformar ett e-postmeddelande](../email/create-email.md).

1. Lägg till den inköpshändelse som skapades tidigare i den första sökvägen. Händelsen utlöses när en person gör ett köp.

1. Efter händelsen släpper du en **push**-åtgärd och definierar innehållet i tackmeddelandet. Läs i det här [avsnittet](../push/create-push.md) om du vill veta mer om hur du konfigurerar och utformar en push-funktion.

## Testa och publicera resan

1. Innan du testar resan kontrollerar du att den är giltig och att det inte finns något fel.

1. Använd växlingsknappen **Testa** i det övre högra hörnet för att aktivera testläget. Mer information om hur du använder testläget finns i [avsnittet](testing-the-journey.md).

1. När resan är klar publicerar du den med knappen **Publicera** som finns i det övre högra hörnet.
