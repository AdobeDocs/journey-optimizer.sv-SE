---
title: Lägg till ett meddelande i en resa
description: Lägg till ett meddelande i en resa
feature: Resor
topic: Innehållshantering
role: User
level: Intermediate
source-git-commit: 7937c3b7c9247868a7a506991850537493a76cf1
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Lägg till ett meddelande i en resa

[!DNL Journey Optimizer] meddelandefunktionerna är inbyggda, du behöver bara utforma innehållet och publicera meddelandet. Se [det här avsnittet](../get-started-content.md). Sedan lägger du bara till ett push- eller e-postmeddelande som utformats med Journey Optimizer under resan.

Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. Läs mer i det här [avsnittet](../action/action.md).

## Lägg till en meddelandeaktivitet

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
