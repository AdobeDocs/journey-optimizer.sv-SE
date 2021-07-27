---
solution: Journey Orchestration
title: Om anpassad åtgärdskonfiguration
description: Lär dig hur du konfigurerar en anpassad åtgärd
feature: Instruktioner
topic: Administrering
role: Admin
level: Intermediate
source-git-commit: e6d8d8ee637008a886ca308b5b0d9d53d90b11ce
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 9%

---

# Konfigurera en åtgärd {#configure-an-action}

Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill att resor ska skicka API-anrop till ett tredjepartssystem, är det här du konfigurerar anslutningen till resor. Den anpassade åtgärden som definieras av tekniska användare är sedan tillgänglig på den vänstra paletten på din resa i kategorin **[!UICONTROL Action]** (se [den här sidan](../building-journeys/about-journey-activities.md#action-activities). Här är några exempel på system som du kan ansluta till med anpassade åtgärder: Epsilon, Facebook, Adobe.io, Firebase osv.
Begränsningar visas i [den här sidan](../building-journeys/limitations.md).

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

1. Lägg till **[!UICONTROL URL]** för den externa tjänsten.

   >[!NOTE]
   >
   >Vi rekommenderar starkt att HTTPS används av säkerhetsskäl. Vi tillåter inte användning av Adobe-adresser som inte är offentliga och användning av IP-adresser.

1. Markera samtalet **[!UICONTROL Method]**: det kan vara antingen **[!UICONTROL POST]** eller **[!UICONTROL PUT]**.
1. I avsnittet **[!UICONTROL Headers]** klickar du på **[!UICONTROL Add a header field]** för att definiera ett nytt nyckel/värde-par. De motsvarar HTTP-rubrikerna för den begäran som görs till den externa tjänsten. Om du vill ta bort nyckel/värde-par placerar du markören i rubrikfältet och klickar på ikonen **[!UICONTROL Delete]**.

   **[!UICONTROL Content-Type]** och  **[!UICONTROL Charset]** anges som standard och kan inte tas bort eller åsidosättas.

   >[!NOTE]
   >
   >Sidhuvuden valideras enligt följande [tolkningsregler](https://tools.ietf.org/html/rfc7230#section-3.2.4).

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
* Variabel innebär att parameterns värde varierar. Marknadsföraren som använder den här anpassade åtgärden i en resa kan skicka värdet han vill ha eller ange var värdet för den här parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett som marknadsföraren kommer att se under resan för att namnge den här parametern.

![](../assets/customactionpayloadmessage2.png)
