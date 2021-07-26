---
title: Lägg till ett meddelande i en resa
description: Lägg till ett meddelande i en resa
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 1f0f4f63a31c4546f813dd803f06ae6aad234b71
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---

# Lägg till ett meddelande i en resa

[!DNL Journey Optimizer] meddelandefunktionerna är inbyggda, du behöver bara utforma innehållet och publicera meddelandet. Se [det här avsnittet](../get-started-content.md). Sedan lägger du bara till ett push- eller e-postmeddelande som utformats med Journey Optimizer under resan.

Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer i det här [avsnittet](../action/action.md).

## Lägga till en meddelandeaktivitet

1. Som alltid ska du påbörja resan med en aktivitet eller en **Läs segment**-aktivitet.

   ![](../assets/jo-message0.png)

1. Dra och släpp en **aktivitet av typen Meddelande** på arbetsytan i **avsnittet Åtgärder** på paletten.

   ![](../assets/jo-message1.png)

1. Lägg till en etikett och en beskrivning.

   ![](../assets/jo-message2.png)

1. Klicka i fältet **Meddelande**. En lista över tillgängliga meddelanden som utformats i Journey Optimizer visas. Du kan filtrera listan efter status.

   ![](../assets/jo-message3.png)

1. Välj ett meddelande och klicka på **Välj**. Du kan också skapa ett nytt meddelande direkt från den här skärmen genom att klicka på **Skapa meddelande**.

   ![](../assets/jo-message4-ter.png)

   Om du vill kontrollera meddelandet kan du klicka på ikonen **Öppna meddelandet** i fältet **Meddelande**. Meddelandet öppnas på en ny flik.

   ![](../assets/jo-message4-bis.png)

1. Lägg till nästa steg på din resa.

## E-postparametrar och push-parametrar

Avsnitten **[!UICONTROL Email parameters]** och **[!UICONTROL Push parameters]** visar skrivskyddade fält. Du utför vanligtvis den här konfigurationen när du skapar meddelandet. Se [det här avsnittet](../get-started-content.md).

![](../assets/jo-message4.png)

Om du vill framtvinga ett visst värde kan du använda ikonen **Aktivera parameteråsidosättning** till höger om fältet. Det här alternativet kan vara användbart i testsyfte. Du kan till exempel lägga till din e-postadress för ett e-postmeddelande. När du har publicerat resan skickas e-postmeddelandet till dig.

## Tidsoptimering för sändning{#send-time-optimization}

### Om Tidsoptimering för Skickat{#about-send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_disabled"
>title="Om Tidsoptimering för Skickat"
>abstract="Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe:s AI-tjänster, kan förutsäga den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser."

Adobe Journey Optimizer funktion för optimering av sändningstid, som bygger på Adobe:s AI-tjänster, kan förutsäga den bästa tidpunkten för att skicka e-post eller push-meddelanden för att maximera engagemanget baserat på tidigare öppnings- och klickfrekvenser. Använd vår maskininlärningsmodell för att schemalägga personliga sändningstider för varje användare så att de kan utöka öppnings- och klickfrekvensen för dina meddelanden.

Modellen för optimering av sändningstid (Send-Time Optimization) innehåller information om dina Adobe Journey Optimizer-data och tittar på användarnivå som är öppen (för e-post och push) och klickar (för e-post) för att avgöra när kunderna är mest benägna att interagera med dina meddelanden. För optimering av sändningstid krävs minst en månads meddelandespårningsdata för att kunna ge välgrundade rekommendationer. För varje användare ger modellen följande prediktiva data:

* Den bästa timmen varje dag i veckan för att maximera engagemanget
* Den bästa veckodagen för att maximera engagemanget
* Den bästa timmen på den bästa veckodagen för att maximera engagemanget

Modellen varierar oavsett om du talar om poängsättning eller utbildning. Utbildningen genomförs varje vecka, inledningsvis och därefter varje kvartal. Poängen är en gång i veckan och därefter en gång i månaden.

* Utbildning - utveckling av den algoritm som används för att göra poängen
* Poäng - poängsättning för enskilda profiler baserat på den tränade modellen

Den här informationen lagras med användarens profil och hänvisas till vid körning av resan för att tala om för Adobe Journey Optimizer när meddelandet ska skickas.

## Viktiga anteckningar{#send-time-optimization-notes}

* Den här funktionen är endast tillgänglig för enkanalsmeddelanden via e-post och push-meddelanden med spårning aktiverat.
* Meddelandet måste publiceras.
* Den här funktionen är inte kompatibel med sprängningsläge.

## Aktivera tidsoptimering för Skickat{#activate-send-time-optimization}

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_email"
>title="Aktivera tidsoptimering för Skickat"
>abstract="Välj om du vill optimera e-postöppningen eller skicka e-postklick genom att välja lämplig alternativknapp. Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för Skicka i nästa alternativ."

>[!CONTEXTUALHELP]
>id="jo_bestsendtime_push"
>title="Aktivera tidsoptimering för Skickat"
>abstract="Standardinställningen för push-meddelanden är öppningsalternativet, eftersom klickningar inte gäller för push-meddelanden. Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för Skicka i nästa alternativ."

Aktivera Send-Time Optimization för ett e-postmeddelande eller push-meddelande genom att välja **Send-Time Optimization** från meddelandeaktivitetsparametrarna.

![](../assets/jo-message5.png)

För e-postmeddelanden väljer du om du vill optimera e-postöppningar eller e-postklick genom att välja lämplig alternativknapp. Standardinställningen för push-meddelanden är öppningsalternativet, eftersom klickningar inte gäller för push-meddelanden.

Du kan också välja att klamra de sändningstider som används av systemet genom att ange ett värde för **Skicka inom nästa**-alternativ. Om du anger värdet &quot;sex timmar&quot; kommer Adobe Journey Optimizer att kontrollera varje användarprofil för att se om den optimala sändningstiden infaller inom sex timmar från körningstiden och välja den sändningsoptimeringstid som bestäms. Om den tiden inte är inom de närmaste sex timmarna skickar Adobe Journey Optimizer automatiskt meddelandet vid körning av resan.
