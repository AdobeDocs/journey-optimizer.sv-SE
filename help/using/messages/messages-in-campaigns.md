---
title: Lägg till meddelanden i kampanjer
description: Lär dig hur du lägger till meddelanden i en kampanj
feature: Overview
topic: Content Management
role: User
level: Beginner
source-git-commit: 87f9a4661b64cf24a8cd62bb9c70d5f1c9fcaddf
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---


# Lägg till meddelanden i kampanjer{#messages-in- campaigns}

I era kampanjer väljer du kanal för att utforma och personalisera det budskap som du vill skicka till er målgrupp. När du lägger till ett e-postmeddelande, ett SMS eller ett push-meddelande till kampanjen kan du skicka det direkt eller schemalägga meddelandet.

>[!NOTE]
>Du kan också skapa resor för att skicka utlösta meddelanden. Läs mer [i det här avsnittet](messages-in-journeys.md).

Lär dig hur du lägger till och konfigurerar meddelanden i en kampanj [i det här avsnittet](../campaigns/create-campaign.md)

Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sida:

* [Skapa ett e-postmeddelande](create-email.md)
* [Skapa push-meddelanden](create-push.md)
* [Skapa ett SMS-meddelande](create-sms.md)

## Aktivera optimering vid sändning{#sto-in-journeys}

För e-post- och push-meddelanden kan du aktivera **[!UICONTROL Send-time optimization]**.

Använd **[!UICONTROL Send-time optimization]** för att schemalägga personliga sändningstider för varje användare så att de kan utöka både öppnings- och klickfrekvensen för dina meddelanden. [Läs mer](../messages/send-time-optimization.md).

## Avancerade parametrar{#adv-settings}

Avancerade parametrar är skrivskyddade och dolda som standard.

Om du vill komma åt avancerade parametrar klickar du på **[!UICONTROL Show read-only fields]** -ikonen högst upp i meddelandefönstret.

![](assets/show-read-only.png)

Avancerade parametrar visas längst ned i meddelandefönstret. Dessa parametrar definieras av [systemadministratör](../start/path/administrator.md) i [kanalyta](../configuration/channel-surfaces.md) (t.ex. meddelandeförinställning) som är kopplad till meddelandet.

För push-meddelanden kan du visa följande parametrar: Token, AppID, AppPlatform.

![](assets/push-adv-parameters.png)

För e-post kan du visa den primära e-postadressen.

Du kan åsidosätta dessa värden i specifika sammanhang om du vill använda dem. Om du vill tvinga fram ett värde klickar du på **Aktivera åsidosättning av parametrar** till höger om fältet. Det här alternativet kan vara användbart till exempel för att:

* Testa ett e-postmeddelande så kan du lägga till din e-postadress. När du har publicerat resan skickas e-postmeddelandet till dig.
* Se e-postadressen till prenumeranterna i en lista. Läs mer i [det här användningsfallet](../building-journeys/message-to-subscribers-uc.md).

Klicka på samma ikon om du vill dölja de avancerade inställningarna.

## Bläddra bland meddelanden{#browse-message}

När flera meddelanden används under en resa kan du växla från ett till ett annat från **Redigera innehåll** skärm.

![](assets/inline-messages-multi-content.png)

Då kan du [kontrollera aviseringar](alerts.md) och [simulera](../design/preview.md) varje innehåll från en och samma vy.

## Duplicera ett meddelande {#duplicate-message}

Du kan kopiera ett befintligt meddelande från arbetsytan för resan.

Gör så här:

1. Markera meddelandet som du vill kopiera.

1. Använd **[!UICONTROL Copy]** från **[!UICONTROL Action]** fönster.

   ![](assets/message-duplicate.png)

1. Retur **Ctrl+V** för att klistra in meddelandet.

   Meddelandet läggs till i kundresan. Alla inställningar och konfigurationer kopieras till det nya meddelandet.

   ![](assets/message-duplicated.png)

1. Byt namn på meddelandet så att det kan skilja det ursprungliga meddelandet från kopian, till exempel när du redigerar meddelanden, enligt nedan:

   ![](assets/multi-message.png)


>[!NOTE]
>
>För e-postmeddelanden kan du även omvandla ett befintligt meddelande till en mall. [Läs mer](../design/email-templates.md).

## Ta bort ett meddelande{#delete-message}

Om du vill ta bort ett meddelande använder du papperskorgsikonen högst upp i åtgärdsrutan för kanaler.

![](assets/delete-message.png)

Använd **[!UICONTROL Confirm]** valideringsknapp.
