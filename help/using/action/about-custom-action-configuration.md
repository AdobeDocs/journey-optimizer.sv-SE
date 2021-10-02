---
solution: Journey Orchestration
title: Om anpassad åtgärdskonfiguration
description: Lär dig hur du konfigurerar en anpassad åtgärd
feature: Actions
topic: Administration
role: Admin
level: Intermediate
exl-id: 4df2fc7c-85cb-410a-a31f-1bc1ece237bb
source-git-commit: a174944bb8efcb67d758d4fe215674c1b8bbee13
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 6%

---

# Konfigurera en åtgärd {#configure-an-action}

Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett tredjepartssystem, är det här du konfigurerar anslutningen till resor. Den anpassade åtgärden som definieras av tekniska användare är sedan tillgänglig på den vänstra paletten på din resa i kategorin **[!UICONTROL Action]** (se [den här sidan](../building-journeys/about-journey-activities.md#action-activities). Här är några exempel på system som du kan ansluta till med anpassade åtgärder: Epsilon, Facebook, Adobe.io, Firebase osv.

Begränsningar visas i [den här sidan](../limitations.md).

Du kan skicka samlingar dynamiskt med anpassade åtgärder. Se det här [användningsexemplet](../limitations.md).

Här följer de huvudsteg som krävs för att konfigurera en anpassad åtgärd:

1. Välj **[!UICONTROL Configurations]** under ADMINISTRATION-menyn. Klicka på **[!UICONTROL Manage]** i **[!UICONTROL Actions]**-avsnittet. Klicka på **[!UICONTROL Create Action]** för att skapa en ny åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/custom2.png)

1. Ange ett namn för åtgärden.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Lägg till en beskrivning av åtgärden. Det här steget är valfritt.
1. Antalet resor som använder den här åtgärden visas i fältet **[!UICONTROL Used in]**. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa listan över resor med den här åtgärden.
1. Definiera de olika **[!UICONTROL URL Configuration]**-parametrarna. Läs [den här sidan](../action/about-custom-action-configuration.md#url-configuration).
1. Konfigurera avsnittet **[!UICONTROL Authentication]**. Den här konfigurationen är densamma som för datakällor.  Se [det här avsnittet](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definiera **[!UICONTROL Action parameters]**. Läs [den här sidan](../action/about-custom-action-configuration.md#define-the-message-parameters).
1. Klicka på **[!UICONTROL Save]**.

   Den anpassade åtgärden är nu konfigurerad och klar att användas på dina resor. Läs [den här sidan](../building-journeys/about-journey-activities.md#action-activities).

   >[!NOTE]
   >
   >När en anpassad åtgärd används i en resa är de flesta parametrar skrivskyddade. Du kan bara ändra fälten **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** och **[!UICONTROL Authentication]**.

## URL-konfiguration {#url-configuration}

När du konfigurerar en anpassad åtgärd måste du definiera följande **[!UICONTROL URL Configuration]**-parametrar:

![](../assets/journeyurlconfiguration.png)

1. Ange URL-adressen för den externa tjänsten i fältet **[!UICONTROL URL]**:

   * Om URL:en är statisk anger du URL:en i det här fältet.

   * Om URL:en innehåller en dynamisk sökväg anger du bara den statiska delen av URL:en, det vill säga schemat, värden, porten och, eventuellt, en statisk del av sökvägen.

      Exempel: `https://xxx.yyy.com/somethingstatic/`

      Du anger den dynamiska sökvägen för URL:en när du lägger till den anpassade åtgärden på en resa. [Läs mer](../building-journeys/using-custom-actions.md).
   >[!NOTE]
   >
   >Av säkerhetsskäl rekommenderar vi starkt att du använder HTTPS-schemat för URL:en. Vi tillåter inte användning av Adobe-adresser som inte är offentliga och användning av IP-adresser.
   >
   >Endast standardportar tillåts när en anpassad åtgärd definieras: 80 för http och 443 för https.

1. Markera samtalet **[!UICONTROL Method]**: det kan vara antingen **[!UICONTROL POST]** eller **[!UICONTROL PUT]**.
1. I avsnittet **[!UICONTROL Headers]** anger du HTTP-rubrikerna för det begärandemeddelande som ska skickas till den externa tjänsten:
   1. Om du vill lägga till ett rubrikfält klickar du på **[!UICONTROL Add a header field]**.
   1. Ange huvudfältets nyckel.
   1. Om du vill ange ett dynamiskt värde för nyckelvärdepar väljer du **[!UICONTROL Variable]**. Annars väljer du **[!UICONTROL Constant]**.

      Du kan till exempel ange ett dynamiskt värde för en tidsstämpel.

   1. Om du har valt **[!UICONTROL Constant]** anger du konstantvärdet.

      Om du har valt **[!UICONTROL Variable]** anger du den här variabeln när du lägger till den anpassade åtgärden på en resa. [Läs mer](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Om du vill ta bort ett rubrikfält pekar du på rubrikfältet och klickar på ikonen **[!UICONTROL Delete]**.
   Rubrikfälten **[!UICONTROL Content-Type]** och **[!UICONTROL Charset]** är inställda som standard. Du kan inte ändra eller ta bort dessa fält.

   När du har lagt till den anpassade åtgärden för en resa kan du fortfarande lägga till rubrikfält i den om resan är i utkaststatus. Om du inte vill att resan ska påverkas av konfigurationsändringar duplicerar du den anpassade åtgärden och lägger till rubrikfälten i den nya anpassade åtgärden.

   >[!NOTE]
   >
   >Huvuden valideras enligt fälttolkningsregler. [Läs mer](https://tools.ietf.org/html/rfc7230#section-3.2.4).

## Definiera åtgärdsparametrarna {#define-the-message-parameters}

![](../assets/messageparameterssection.png)

I avsnittet **[!UICONTROL Action parameters]** klistrar du in ett exempel på JSON-nyttolasten som ska skickas till den externa tjänsten.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Fältnamn i nyttolasten får inte innehålla &quot;.&quot; tecken. De kan inte börja med tecknet &quot;$&quot;.

Du kan definiera parametertypen (t.ex.: sträng, heltal osv.).

Du kan också välja mellan att ange om en parameter är en konstant eller en variabel:

* Konstant innebär att parametervärdet definieras av en teknisk person i åtgärdskonfigurationsfönstret. Värdet är alltid detsamma oavsett resa. Det kommer inte att variera och marknadsföraren kommer inte att se det när han eller hon använder den anpassade åtgärden under resan. Det kan till exempel vara ett ID som tredjepartssystemet förväntar sig. I så fall är fältet till höger om växlingskonstanten/variabeln det värde som skickas.
* Variabel innebär att parameterns värde varierar. Marknadsförare som använder den här anpassade åtgärden under en resa kan skicka det värde de vill ha eller ange var värdet för den här parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett marknadsförarna kommer att se under resan för att namnge den här parametern.

![](../assets/customactionpayloadmessage2.png)

