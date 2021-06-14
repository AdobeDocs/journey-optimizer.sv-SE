---
title: Användningsexempel på resor
description: Användningsexempel på resor
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 2%

---

# Användningsexempel på resa

![](../assets/do-not-localize/badge.png)

I det här avsnittet visas ett användningsexempel som kombinerar ett Lässegment, en händelse, reaktionshändelser och e-post/push-meddelanden.

![](../assets/jo-uc1.png)

## Beskrivning av användningsfallet

I det här fallet vill vi skicka ett första meddelande (e-post och push) till alla kunder som tillhör ett visst segment.

Vi vill skicka specifika meddelanden utifrån deras reaktion på det första meddelandet.

Efter det första meddelandet väntar vi en dag på att kunderna ska öppna push-meddelandet eller e-postmeddelandet. Om vi inte får någon reaktion skickar vi ett uppföljningsmejl till dem.

Sedan väntar vi på ett köp och skickar ett push-meddelande till kunden för att tacka.

## Förutsättningar

För att detta ska fungera måste du konfigurera följande:

* ett segment för alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980.
* en köphändelse
* tre meddelanden

### Skapa segmentet

Under vår resa vill vi utnyttja ett specifikt kundsegment. Alla personer som tillhör segmentet går in på resan och följer de olika stegen. I vårt exempel behöver vi ett segment som riktar sig till alla kunder som bor i Atlanta, San Francisco eller Seattle och som är födda efter 1980.

Mer information om segment finns på den här [sidan](../segment/about-segments.md).

1. Klicka på **[!UICONTROL Create segment]** på menyn **[!UICONTROL Segments]**.

1. I rutan **[!UICONTROL Segment properties]** anger du ett namn för segmentet.

1. Dra och släpp önskade fält från den vänstra rutan till arbetsytan i mitten och konfigurera dem sedan efter behov. I det här exemplet använder vi attributfälten **Ort** och **Födelseår**.

1. Klicka på **[!UICONTROL Save]**.

   ![](../assets/add-attributes.png)

Segmentet är nu skapat och klart att användas på din resa. Om du använder en **Läs-aktivitet** kan du få alla personer som tillhör segmentet att komma in på resan.

### Konfigurera händelsen

Du måste konfigurera ett evenemang som skickas till din resa när en kund gör ett köp. När resan tar emot händelsen utlöses meddelandet&quot;Tack&quot;.

För detta använder vi en regelbaserad händelse. Mer information om händelser finns på den här [sidan](../event/about-events.md).

1. I avsnittet Administration går du till **[!UICONTROL Configurations]** och klickar sedan på **[!UICONTROL Events]**. Klicka på **[!UICONTROL Add]** för att skapa en ny händelse.

1. Ange namnet på händelsen.

1. Markera **[!UICONTROL Event ID type]** i fältet **[!UICONTROL Rule Based]**.

1. Definiera **[!UICONTROL Schema]** och nyttolasten **[!UICONTROL Fields]**. Du kan använda flera fält, till exempel den köpta produkten, inköpsdatumet och inköps-ID:t.

1. I fältet **[!UICONTROL Event ID condition]** definierar du villkoret som används av systemet för att identifiera de händelser som utlöser din resa. Du kan till exempel lägga till ett `purchaseMessage`-fält och definiera följande regel: `purchaseMessage="thank you"`

1. Definiera **[!UICONTROL Namespace]** och **[!UICONTROL Key]**.

1. Klicka på **[!UICONTROL Save]**.

   ![](../assets/jo-uc2.png)

Händelsen är nu konfigurerad och klar att användas under din resa. Genom att använda motsvarande händelseaktivitet kan du aktivera en åtgärd varje gång en kund gör ett köp.

### Skapa meddelanden

I det här fallet måste vi skapa tre meddelanden:

* ett push- och e-postmeddelande
* ett push-tackmeddelande
* ett uppföljningsmeddelande via e-post

![](../assets/jo-uc3.png)

Läs det här [avsnittet](../segment/about-segments.md) om du vill veta mer om hur du utformar och publicerar dessa meddelanden.

## Designa resan

1. Starta resan med en **Läs segment**-aktivitet. Markera det segment som skapades tidigare. Alla personer som tillhör segmentet deltar i resan.

   ![](../assets/jo-uc4.png)

1. Släpp en **Message**-aktivitet och välj push- och email first message. Det här meddelandet skickas till alla personer på resan.

   ![](../assets/jo-uc5.png)

1. Placera markören på meddelandeaktiviteten och klicka på plustecknet (+) för att skapa en ny sökväg.

1. Lägg till en **Reaction**-händelse i den första sökvägen och välj **Push opened**. Händelsen utlöses när en person som tillhör segmentet öppnar den push-versionen av det första meddelandet.

1. Lägg till en **reaktion**-händelse i den andra sökvägen och välj **E-post öppnad**. Händelsen utlöses när personen öppnar e-postmeddelandet.

1. I någon av reaktionsaktiviteterna markerar du rutan **Definiera tidsgräns för händelse**, definierar en varaktighet (1 dag i vårt exempel) och markerar **Ange en tidsgräns**. Detta skapar en ny sökväg för personer som inte öppnar det första push- eller e-postmeddelandet.

   >[!NOTE]
   >
   >När du konfigurerar en timeout för flera händelser (de två reaktionerna i det här fallet) behöver du bara konfigurera timeout för en av dessa händelser.

1. Släpp en **Message**-aktivitet i timeoutsökvägen och välj e-postens uppföljningsmeddelande. Det här meddelandet skickas till de personer som inte öppnar e-postmeddelandet eller skickar det första meddelandet nästa dag.

1. Koppla de tre sökvägarna till inköpshändelsen som skapades tidigare. Händelsen utlöses när en person gör ett köp.

1. Efter händelsen släpper du en **Meddelande**-aktivitet och väljer e-postmeddelandet&quot;Tack&quot;.

1. Lägg till en **End**-aktivitet.

## Testa och publicera resan

1. Innan du testar din resa kontrollerar du att den är giltig och att det inte finns något fel.

1. Klicka på växlingsknappen **Testa** längst upp till höger för att aktivera testläget. Definiera hur du vill att testprofiler ska ange testet: en enda profil, eller upp till 100 samtidigt. Läs det här [avsnittet](testing-the-journey.md) om du vill veta hur du använder testläget.

1. När resan är klar publicerar du den med knappen **Publicera**, som finns i det övre högra hörnet.
