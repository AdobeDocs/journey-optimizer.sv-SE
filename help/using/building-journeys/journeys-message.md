---
title: Lägg till ett meddelande i en resa
description: Lägg till ett meddelande i en resa
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 4db07a9e-c3dd-4873-8bd9-ac34c860694c
source-git-commit: dc05d88773dc148dc0e5387953f49c4d03b1888f
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 0%

---

# Lägg till ett meddelande i en resa

[!DNL Journey Optimizer] meddelandefunktionerna är inbyggda, du behöver bara utforma innehållet och publicera meddelandet. Se [det här avsnittet](../get-started-content.md). Sedan lägger du bara till ett push- eller e-postmeddelande som utformats med Journey Optimizer under resan.

Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer om detta [section](../action/action.md).

## Lägg till en meddelandeaktivitet

1. Som alltid, starta din resa med ett evenemang eller en **Läs segment** aktivitet.

   ![](../assets/jo-message0.png)

1. Från **Åtgärder** dra och släpp en **Meddelande** till arbetsytan.

   ![](../assets/jo-message1.png)

1. Lägg till en etikett och en beskrivning.

   ![](../assets/jo-message2.png)

1. Klicka inuti **Meddelande** fält. The list of available messages designed in Journey Optimizer is displayed. Du kan filtrera listan efter status.

   ![](../assets/jo-message3.png)

1. Välj ett meddelande och klicka på **Välj**. Du kan också skapa ett nytt meddelande direkt från den här skärmen genom att klicka på **Skapa meddelande**.

   ![](../assets/jo-message4-ter.png)

   Om du vill kontrollera meddelandet kan du klicka på **Öppna meddelandet** ikonen i **Meddelande** fält. Meddelandet öppnas på en ny flik.

   ![](../assets/jo-message4-bis.png)

1. Lägg till nästa steg på din resa.

## Email parameters and push parameters

The **[!UICONTROL Email parameters]** och **[!UICONTROL Push parameters]** -avsnitt visar skrivskyddade fält. Du utför vanligtvis den här konfigurationen när du skapar meddelandet. Se [det här avsnittet](../get-started-content.md).

![](../assets/jo-message4.png)

To force a specific value, you can use the **Enable parameter override** icon to the right of the field. This option may be useful for various purposes:

* Om du till exempel vill testa ett e-postmeddelande kan du lägga till din e-postadress. När du har publicerat resan skickas e-postmeddelandet till dig.
* Du kan hänvisa till e-postadressen till de som prenumererar på en lista. Se det här [användningsfall](message-to-subscribers-uc.md).

## Sändningsoptimering{#send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_disabled"
>title="About Sent time optimization"
>abstract="Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe:s AI-tjänster, kan förutsäga den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser."

Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe:s AI-tjänster, kan förutsäga den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser. Använd vår maskininlärningsmodell för att schemalägga personliga sändningstider för varje användare så att de kan utöka öppnings- och klickfrekvensen för dina meddelanden.

>[!NOTE]
>
>Den här funktionen är för närvarande i betaversion och endast tillgänglig för betakunder. Om du vill gå med i betaprogrammet kontaktar du Adobe kundtjänst.

The Send-Time Optimization model ingests your Adobe Journey Optimizer data and looks at user-level open (for email and push) and click (for email) rates to determine when your customers are most likely to engage with your messaging. För optimering av sändningstid krävs minst en månads meddelandespårningsdata för att kunna ge välgrundade rekommendationer. För varje användare väljer systemet automatiskt den bästa tiden med följande poäng:

* Den bästa timmen varje dag i veckan för att maximera engagemanget
* The best day of the week to maximize engagement
* Den bästa timmen på den bästa veckodagen för att maximera engagemanget

Modellen varierar oavsett om du talar om poängsättning eller utbildning. Utbildningen genomförs varje vecka, inledningsvis och därefter varje kvartal. Poängen är en gång i veckan och därefter en gång i månaden.

* Utbildning - utveckling av den algoritm som används för att göra poängen
* Scoring - the application of a score to individual profiles based on the trained model

Den här informationen lagras med användarens profil och hänvisas till vid körning av resan för att tala om för Adobe Journey Optimizer när meddelandet ska skickas.

>[!CAUTION]
>
>* Den här funktionen är endast tillgänglig för enkanalsmeddelanden via e-post och push-meddelanden med spårning aktiverat.
>* Meddelandet måste publiceras.
>* Den här funktionen är inte kompatibel med sprängningsläge.


### Aktivera optimering av sändningstid{#activate-send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_email"
>title="Aktivera optimering av sändningstid"
>abstract="Välj om du vill optimera e-postöppningen eller skicka e-postklick genom att välja lämplig alternativknapp. You can also choose to bracket the send times used by the system by entering a value for the Send within the next option."

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_push"
>title="Aktivera optimering av sändningstid"
>abstract="Standardinställningen för push-meddelanden är öppningsalternativet, eftersom klickningar inte gäller för push-meddelanden. Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för Skicka i nästa alternativ."

Aktivera optimering av sändningstid för ett e-postmeddelande eller push-meddelande genom att välja **Sändningsoptimering** växla från meddelandeaktivitetsparametrarna.

![](../assets/jo-message5.png)

For email messages, choose whether to optimize on email opens or email click-throughs by selecting the appropriate radio button. Standardinställningen för push-meddelanden är öppningsalternativet, eftersom klickningar inte gäller för push-meddelanden.

Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för **Skicka inom nästa** alternativ. Om du väljer&quot;sex timmar&quot; som värde, [!DNL Journey Optimizer] kontrollerar varje användarprofil och väljer den optimala sändningstiden inom sex timmar från körningstiden för resan.
