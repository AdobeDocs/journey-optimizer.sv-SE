---
solution: Journey Optimizer
product: journey optimizer
title: Justera lodrät justering och utfyllnad i Journey Optimizer
description: Lär dig justera lodrät justering och utfyllnad
feature: Email Design
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: lodrät justering, e-postredigerare, utfyllnad
exl-id: 1e1d90ff-df5d-4432-a63a-a32d0d281d48
source-git-commit: 4817b7426abf202c886b7fd63d59aa0f245e5496
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Justera lodrät justering och utfyllnad {#alignment-and-padding}

I det här exemplet justerar vi utfyllnad och lodrät justering inuti en strukturkomponent som består av tre kolumner.

1. Markera strukturkomponenten direkt i e-postmeddelandet eller använd **[!UICONTROL Navigation tree]** som finns i den vänstra menyn.

1. Klicka på **[!UICONTROL Select a column]** i verktygsfältet och välj den som du vill redigera. Du kan också välja det i strukturträdet.

   De redigerbara parametrarna för den kolumnen visas på fliken **[!UICONTROL Styles]**.

   ![](assets/alignment_2.png)

1. Under **[!UICONTROL Alignment]** väljer du **[!UICONTROL Top]**, **[!UICONTROL Middle]** eller **[!UICONTROL Bottom]**.

   ![](assets/alignment_3.png)

1. Ange utfyllnaden för alla sidor under **[!UICONTROL Padding]**.

   Välj **[!UICONTROL Different padding for each side]** om du vill finjustera utfyllnaden. Klicka på låsikonen för att bryta synkroniseringen.

   ![](assets/alignment_4.png)

1. Gör på samma sätt om du vill justera justeringen och utfyllnaden för de andra kolumnerna.

1. Spara ändringarna.

>[!TIP]
>
>När du utformar e-postinnehåll för Gmail på Android-enheter måste du se till att kolumnutfyllnad används i stället för stora, fasta marginaler för bilder och delare. Gmail på Android återger ofta överdimensionerade bilder och marginaler felaktigt, vilket kan orsaka layoutspill eller reducerade avdelarlinjer. Använd en mindre bildbredd eller använd kolumnbaserad utfyllnad för enhetlig visning.

## Hantera fragmentutfyllnad med vägbeskrivningsnavigering {#fragment-padding-breadcrumb}

När du arbetar med [fragment](../content-management/fragments.md) i e-post-Designer kan du stöta på dold eller kvarvarande utfyllnad som påverkar den mobila återgivningen på ett annat sätt än på skrivbordet. Detta är särskilt vanligt när fragment har låsts upp eller när [arvet har brutits](use-visual-fragments.md#break-inheritance), eftersom överbliven formatering kan finnas kvar i den underliggande kolumnen eller textkomponenterna.

Så här identifierar och redigerar du vänsterutfyllnad i fragment:

1. Använd **[!UICONTROL Navigation tree]** eller klicka direkt på element i redigeraren för att välja varje överordnad struktur eller kolumn i fragmentet. Detta hjälper dig att hitta dold utfyllnad eller marginal som kan vara specifik för mobila enheter.

1. När du har markerat elementet i den synliga sökvägen går du till fliken **[!UICONTROL Styles]** till höger.

1. Granska inställningarna för **[!UICONTROL Padding]** och ta bort eller justera utfyllnaden efter behov för att få rätt mobiljustering.

1. Om justeringsproblemen kvarstår när fragment återanvänds, upprepar du den här processen för andra kolumner eller textkomponenter i fragmentet.

>[!NOTE]
>
>Detta beteende förväntas när fragment infogas och tas bort upprepade gånger, eftersom formateringsregler kan ackumuleras. Verifiera alltid utfyllnadsvärden med hjälp av vägbeskrivningsnavigering, särskilt när du riktar dig till mobila enheter.