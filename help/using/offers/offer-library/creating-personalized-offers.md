---
title: Skapa personaliserade erbjudanden
description: Lär dig hur du skapar personaliserade erbjudanden i Adobe Experience Platform.
feature: Erbjudanden
topic: Integreringar
role: User
level: Intermediate
source-git-commit: 8ffafb76b15ea7dfabd52c278833fc607f3338a5
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 1%

---

# Skapa personaliserade erbjudanden {#creating-personalized-offers}

Innan du skapar ett erbjudande måste du kontrollera att du har skapat:

* En **placering** där erbjudandet ska visas. Se [Skapa placeringar](../offer-library/creating-placements.md)
* En **beslutsregel** som definierar det villkor som erbjudandet ska presenteras under. Se [Skapa beslutsregler](../offer-library/creating-decision-rules.md).
* En eller flera **taggar** som du vill associera med erbjudandet. Se [Skapa taggar](../offer-library/creating-tags.md).

![](../../assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

Listan med personaliserade erbjudanden finns på **[!UICONTROL Offers]**-menyn.

![](../../assets/offers_list.png)

## Skapa erbjudandet {#create-offer}

Så här skapar du ett **erbjudande**:

1. Klicka på **[!UICONTROL Create offer]** och välj sedan **[!UICONTROL Personalized offer]**.

   ![](../../assets/create_offer.png)

1. Ange erbjudandets namn samt start- och slutdatum och sluttid. Du kan också koppla en eller flera befintliga taggar till erbjudandet, så att du enklare kan söka efter och ordna erbjudandebiblioteket.

   ![](../../assets/offer_details.png)

   >[!NOTE]
   >
   >I **[!UICONTROL Offer attributes]**-avsnittet kan du koppla nyckelvärdepar till erbjudandet i rapporterings- och analyssyfte.

## Konfigurera offertens representationer {#representations}

1. Lägg till en eller flera representationer för ditt erbjudande med knappen **[!UICONTROL Add representation]**.

   >[!NOTE]
   >
   >Ett erbjudande kan visas på olika platser i ett meddelande: i en övre banderoll med en bild, som text i ett stycke, som ett html-block osv. Ju fler representationer ett erbjudande har, desto fler möjligheter finns det att använda erbjudandet i olika placeringssammanhang.

1. För varje representation anger du **[!UICONTROL Channel]** och **[!UICONTROL Placement]** där erbjudandet ska visas.

   ![](../../assets/channel-placement.png)

   Med knappen **[!UICONTROL Browse]** kan du filtrera tillgängliga placeringar och filtrera dem efter kanal- och/eller innehållstyp.

   ![](../../assets/browse-placements.png)

1. Lägg till innehåll i varje representation som kommer från Adobe Experience Cloud Assets-biblioteket eller från en extern offentlig plats.

   * Om du vill lägga till innehåll från Adobe Experience Cloud Resurser-biblioteket drar och släpper du det från den vänstra rutan i visningsområdet och anger sedan den URL som ska associeras med innehållet i **[!UICONTROL Destination link]**-fältet.

      >[!NOTE]
      >
      >Innehåll kan bara dras och släppas från resursväljaren i den vänstra panelen. Endast innehåll som motsvarar placeringens innehållstyp är tillgängligt för användning.

      ![](../../assets/offer_drag_content.png)

   * Om du vill lägga till innehåll från en extern offentlig plats klickar du på knappen **[!UICONTROL Add content]** och anger sedan namnet, URL:en och destinationslänken för innehållet som ska läggas till.

      Kontrollera att innehållet som du lägger till motsvarar den valda placeringens innehållstyp.

      ![](../../assets/offer_add_content.png)

   * Du kan också infoga text. Om du vill göra det klickar du på knappen **[!UICONTROL Add content]** och väljer sedan alternativet **[!UICONTROL Custom text]**. I fältet **[!UICONTROL Text]** skriver du den text som ska visas i erbjudandet.

      >[!NOTE]
      >
      >Det här alternativet är inte tillgängligt för bildtypsplaceringar.

      ![](../../assets/offer_text_content.png)

## Lägg till regler och begränsningar för berättigande {#eligibility}

Behörighetsregler och -begränsningar gör att du kan definiera villkoren för hur ett erbjudande ska visas.

1. Konfigurera **[!UICONTROL Offer eligibility]**. Som standard är alternativet **[!UICONTROL All visitors]** för beslutsregel valt, vilket innebär att alla profiler kan presenteras erbjudandet.

   Du kan begränsa erbjudandets presentation till medlemmarna i ett eller flera Adobe Experience Platform-segment. Aktivera alternativet **[!UICONTROL Visitors who fall into one or multiple segments]** och lägg sedan till ett eller flera segment från den vänstra rutan och kombinera dem med de logiska operatorerna **[!UICONTROL And]** / **[!UICONTROL Or]**.

   Mer information om hur du arbetar med segment finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).

   ![](../../assets/offer-eligibility-segment.png)

   Om du vill koppla en viss beslutsregel till erbjudandet väljer du **[!UICONTROL By defined decision rule]** och drar sedan den önskade regeln från den vänstra rutan till **[!UICONTROL Decision rule]**-området. Mer information om hur du skapar en beslutsregel finns i [det här avsnittet](../offer-library/creating-decision-rules.md).

   ![](../../assets/offer_rule.png)

1. Definiera **[!UICONTROL Priority]** för erbjudandet jämfört med andra om användaren kvalificerar för mer än ett erbjudande. Ju högre prioritet ett erbjudande har, desto högre blir prioriteringen jämfört med andra erbjudanden.

1. Ange erbjudandets **[!UICONTROL Capping]**, vilket innebär hur många gånger erbjudandet kommer att visas totalt för alla användare. Om erbjudandet har levererats till alla användare det antal gånger som du har angett i det här fältet, upphör leveransen.

   >[!NOTE]
   >
   >Det antal gånger ett erbjudande föreslås beräknas vid e-postförberedelsen. Om du t.ex. förbereder ett e-postmeddelande med ett antal erbjudanden räknas dessa siffror mot det högsta antalet oavsett om e-postmeddelandet skickas eller inte.
   >
   >Om en e-postleverans tas bort eller om förberedelserna görs på nytt innan den skickas, uppdateras erbjudandets begränsningsvärde automatiskt.

   ![](../../assets/offer_capping.png)

   I exemplet ovan:

   * Prioriteten för erbjudandet är 50, vilket innebär att erbjudandet presenteras före erbjudanden med en prioritet mellan 1 och 49, och efter erbjudanden med en prioritet på minst 51.
   * Erbjudandet gäller endast användare som matchar&quot;Gold Loyalty Customers&quot;-beslutsregeln.
   * Erbjudandet gäller endast en gång per användare.

## Se erbjudandet {#review}

När regler och begränsningar för behörighet har definierats visas en sammanfattning av egenskaperna för erbjudandet. Om allt är korrekt konfigurerat och erbjudandet är klart att visas för användarna klickar du på **[!UICONTROL Finish]** och väljer sedan **[!UICONTROL Save and approve]**.

Du kan också spara erbjudandet som ett utkast för att redigera det och godkänna det senare.

![](../../assets/offer_review.png)

Erbjudandet visas i listan med statusen **[!UICONTROL Live]** eller **[!UICONTROL Draft]**, beroende på om du godkände det eller inte i det föregående steget.

Den är nu klar att levereras till användarna. Du kan markera den för att visa dess egenskaper och redigera eller inaktivera den.

![](../../assets/offer_created.png)

När du har skapat ett erbjudande kan du klicka på dess namn i listan för att få tillgång till detaljerad information, samt övervaka alla ändringar som har gjorts på den via fliken **[!UICONTROL Change log]** (se [Övervaka ändringar i erbjudanden och beslut](../get-started/user-interface.md#monitoring-changes)).

## Videokurs {#video}

>[!NOTE]
>
>Den här videon gäller för Offera decisioningens programtjänst som är byggd på Adobe Experience Platform. Det ger dock allmän vägledning om hur man använder Erbjudandet inom ramen för Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329375?quality=12)
