---
title: Lägg till meddelanden under resor
description: Lär dig hur du lägger till meddelanden under en resa
feature: Overview
topic: Content Management
role: User
level: Beginner
source-git-commit: ed1ae405367a0b0f37e61ceb81fc1f1d1b907ea7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Lägg till meddelanden under resor{#messages-in-journeys}

>[!CONTEXTUALHELP]
>id="ajo_message_category"
>title="Meddelandekategori"
>abstract="Välj Marknadsföring för kommersiella meddelanden eller Transactional för icke-kommersiella meddelanden som orderbekräftelse, meddelanden om lösenordsåterställning eller leveransinformation"

>[!CONTEXTUALHELP]
>id="ajo_message_surface"
>title="Kanalyta"
>abstract="En kanalyta är en instans av den kanalen som har alla inställningar för att kunna leverera en åtgärd via en kampanj eller en resa. Den definieras av en systemadministratör."

Använd kanalåtgärderna på era resor för att utforma och personalisera det budskap ni vill skicka till er målgrupp. När du lägger till ett e-postmeddelande, ett SMS-meddelande eller en push-åtgärd på arbetsytan skapas en utlöst sändning. När kontakterna kommer till den kanalåtgärden skickar Adobe Journey Optimizer automatiskt meddelandet.


>[!NOTE]
>Du kan också skapa kampanjer för att skicka schemalagda meddelanden. Läs mer [i det här avsnittet](../campaigns/get-started-with-campaigns.md).


Om du vill lägga till meddelanden under en resa lägger du till en push-, SMS- eller e-postaktivitet på arbetsytan för resan.

1. Påbörja resan med en [Händelse](../building-journeys/general-events.md) eller en [Läs segment](../building-journeys/read-segment.md) aktivitet.

1. Från **Åtgärder** dra och släpp en **e-post**, en **SMS** eller en **Push** till arbetsytan.

   ![](assets/add-a-message.png)

1. Ange en etikett och en beskrivning.

1. Markera meddelandet **[!UICONTROL Category]**: välj **Marknadsföring** för kommersiella meddelanden, eller **Transactional** för icke-kommersiella meddelanden som orderbekräftelse, meddelanden om lösenordsåterställning eller leveransinformation.

   >[!CAUTION]
   >
   >Om du har definierat [frekvensregler](../configuration/frequency-rules.md) för en viss kanal och kategori tillämpas de automatiskt på meddelandet när den kanalen och kategorin väljs. För närvarande bara **[!UICONTROL Marketing]** finns för frekvensregler.

   ![](assets/inline-message-category.png)

   >[!CAUTION]
   >
   >Marknadsföringsmeddelanden måste innehålla en [länk för avanmälan](../messages/consent.md#opt-out-management). Detta krävs inte för transaktionsmeddelanden eftersom dessa meddelanden kan skickas till profiler som avbeställer marknadskommunikation.

1. Välj kanalen **[!UICONTROL Surface]** (t.ex. meddelandeförinställning) för att skicka meddelandet.

   En yta är en konfiguration som har definierats av en [Systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer](../configuration/channel-surfaces.md).

   >[!CAUTION]
   >
   >Du måste välja en giltig kanalyta för den valda meddelandekategorin och kanalen.

   Du kan när som helst komma åt och ändra meddelandets etikett, beskrivning och yta med hjälp av **[!UICONTROL Properties]** i meddelandegränssnittet.

1. Skapa meddelandeinnehållet.

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

   Meddelandet läggs till på arbetsytan för resan. Alla inställningar och konfigurationer kopieras till det nya meddelandet.

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
