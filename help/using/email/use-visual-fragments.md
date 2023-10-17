---
solution: Journey Optimizer
product: journey optimizer
title: Använd visuella fragment
description: Lär dig använda visuella fragment när du skapar e-postmeddelanden i Journey Optimizer kampanjer och resor
feature: Email Design, Templates
topic: Content Management
role: User
level: Beginner
exl-id: 25a00f74-ed08-479c-9a5d-4185b5f3c684
source-git-commit: 8579acfa881f29ef3947f6597dc11d4c740c3d68
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 2%

---

# Lägg till visuella fragment i e-postmeddelanden {#use-visual-fragments}

Du kan använda ett visuellt fragment i en [e-post](get-started-email-design.md) inom en resa eller kampanj, eller i en [innehållsmall](../content-management/content-templates.md).

>[!NOTE]
>
>Lär dig hur du skapar och hanterar fragment i [det här avsnittet](../content-management/fragments.md).

➡️ [Lär dig hur du hanterar, redigerar och använder fragment i den här videon](../content-management/fragments.md#video-fragments)

## Använda ett fragment {#use-fragment}

1. Öppna e-post- eller mallinnehåll med [E-postdesigner](get-started-email-design.md).

1. Välj **[!UICONTROL Fragments]** ikonen från den vänstra listen.

   ![](assets/fragments-in-designer.png)

1. Listan över alla visuella fragment som skapats i den aktuella sandlådan visas. Du kan:

   * Sök efter ett visst fragment genom att börja skriva dess etikett.
   * Sortera fragment i stigande eller fallande ordning.
   * Ändra hur fragmenten visas (kort eller listvy).

   >[!NOTE]
   >
   >Fragment sorteras efter skapandedatum: nyligen tillagda visuella fragment visas först i listan.

1. Du kan söka i och uppdatera listan.

   >[!NOTE]
   >
   >Om vissa fragment har ändrats eller lagts till medan du redigerar innehållet, uppdateras listan med de senaste ändringarna.

1. Dra och släpp ett fragment från listan till området där du vill infoga det.

   ![](assets/fragment-insert.png)

1. Precis som andra komponenter kan du flytta runt fragmentet i innehållet.

1. Markera fragmentet för att visa motsvarande ruta till höger. Därifrån kan du ta bort fragmentet från innehållet eller duplicera det. Du kan också utföra dessa åtgärder direkt från den snabbmeny som visas ovanpå fragmentet.

   ![](assets/fragment-right-pane.png)

1. Från **[!UICONTROL Settings]** kan du

   * Välj de enheter som du vill att fragmentet ska visas på.
   * Öppna fragmentet på en ny flik om du vill redigera det. [Läs mer](../content-management/fragments.md#edit-fragments)
   * Utforska referenser. [Läs mer](../content-management/fragments.md#explore-references)

1. Du kan anpassa fragmentet ytterligare med **[!UICONTROL Styles]** -fliken.

1. Vid behov kan du bryta arvet med det ursprungliga fragmentet. [Läs mer](#break-inheritance)

1. Lägg till så många fragment du vill och **[!UICONTROL Save]** dina ändringar.

## Bryt arv {#break-inheritance}

När du redigerar ett visuellt fragment synkroniseras ändringarna. De sprids automatiskt till alla **[!UICONTROL Draft]** resor/kampanjer och innehållsmallar som innehåller det fragmentet.

>[!NOTE]
>
>Ändringarna sprids inte till e-postmeddelanden som används i **[!UICONTROL Live]** resor eller kampanjer.

När fragment läggs till i ett e-postmeddelande eller i en innehållsmall synkroniseras de som standard.

Du kan emellertid bryta arvet från det ursprungliga fragmentet. I så fall kopieras fragmentets innehåll till den aktuella designen och ändringarna synkroniseras inte längre.

Följ stegen nedan för att bryta arv:

1. Markera fragmentet.

1. Klicka på upplåsningsikonen i det sammanhangsberoende verktygsfältet.

   ![](assets/fragment-break-inheritance.png)

1. Det fragmentet blir ett fristående element som inte längre är länkat till det ursprungliga fragmentet. Redigera det som vilken annan innehållskomponent som helst i innehållet. [Läs mer](content-components.md)
