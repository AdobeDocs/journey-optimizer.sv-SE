---
solution: Journey Optimizer
product: journey optimizer
title: Avsluta prenumeration på lista
description: Lär dig hur du tar med en avbruten URL i e-postmeddelandehuvudet med ett klick när du ställer in kanalkonfigurationen
feature: Email, Surface
topic: Administration
role: Admin
level: Experienced
keywords: inställningar, e-post, konfiguration
exl-id: c6c77975-ec9c-44c8-a8d8-50ca6231fea6
source-git-commit: b3655506dff97756a59a63d5b8f0c358dc7c7510
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---

# Avbeställ lista{#list-unsubscribe}

<!--Do not modify - Legal Review Done -->

När du konfigurerar en ny e-postkanalskonfiguration visas alternativet **[!UICONTROL Enable List-Unsubscribe]** när [du väljer en underdomän](email-settings.md#subdomains-and-ip-pools) i listan.

![](assets/preset-list-unsubscribe.png)

## Aktivera avanmälan av lista {#enable-list-unsubscribe}

Det här alternativet är aktiverat som standard för att inkludera en avbruten URL-adress med ett klick i e-posthuvudet, till exempel:

![](assets/preset-list-unsubscribe-header.png)

>[!NOTE]
>
>Om du inaktiverar det här alternativet visas ingen avbruten URL i e-posthuvudet med ett enda klick.

Rubriken för att avbryta prenumerationen på List har två alternativ som är aktiverade som standard om du inte avmarkerar ett av dem eller båda:

![](assets/surface-list-unsubscribe.png){width="80%"}

* En **[!UICONTROL Mailto (unsubscribe)]**-adress, som är den måladress dit begäran om att avbryta prenumerationen dirigeras för automatisk bearbetning.

  I [!DNL Journey Optimizer] är e-postadressen för att avbryta prenumerationen den **[!UICONTROL Mailto (unsubscribe)]** standardadress som visas i kanalkonfigurationen utifrån din [valda underdomän](#subdomains-and-ip-pools). <!--With this method, clicking the Unsubscribe link sends a pre-filled email to the unsubscribe address specified in the email header.-->

* **[!UICONTROL One-click unsubscribe URL]**, som som standard är den enklicksavanmälnings-URL som genereras för att avbryta prenumerationen, baserat på den underdomän som du anger och konfigurerar i kanalkonfigurationsinställningarna. <!--With this method, clicking the Unsubscribe link directly unsubscribes the user, requiring only a single action to unsubscribe.-->

Du kan välja **[!UICONTROL Consent level]** i motsvarande listruta. Den kan vara specifik för kanalen eller för profilens identitet. Baserat på den här inställningen uppdateras medgivandet i [!DNL Adobe Journey Optimizer], antingen på kanalnivå eller på ID-nivå, när en användare avbeställer prenumerationen med hjälp av URL:en för att avbryta prenumerationen i huvudet i ett e-postmeddelande.

Funktionen **[!UICONTROL Mailto (unsubscribe)]** och funktionen **[!UICONTROL One-click unsubscribe URL]** är valfria.

Om du inte vill använda den standardgenererade URL-adressen för ett enda klick kan du avmarkera funktionen. Om du lägger till en [-klicksavanmälningslänk ](../email/email-opt-out.md#one-click-opt-out) i ett meddelande som skapats med den här konfigurationen, kommer rubriken Lista avanmälan att hämta den enklicksavanmälningslänk som du har infogat i e-postmeddelandets brödtext och använda den som ett-klicksvärde för att avbryta prenumerationen i scenariot där alternativet **[!UICONTROL Enable List-Unsubscribe]** är aktiverat och funktionen **[!UICONTROL One-click Unsubscribe URL]** inte är markerad.

![](assets/preset-list-unsubscribe-opt-out-url.png)

>[!NOTE]
>
>Om du inte lägger till en länk för avanmälan med ett enda klick i meddelandeinnehållet och standardinställningen **[!UICONTROL One-click unsubscribe URL]** inte är markerad i kanalkonfigurationsinställningarna, skickas ingen URL till e-posthuvudet som en del av rubriken för att avbryta prenumeration av lista.

Läs mer om hur du hanterar funktioner för att avbryta prenumerationen i dina meddelanden i [det här avsnittet](../email/email-opt-out.md#unsubscribe-header).

## Hantera avbeställningsdata externt {#custom-managed}

>[!CONTEXTUALHELP]
>id="ajo_email_config_unsubscribe_custom"
>title="Definiera hur data för att avbryta prenumerationen hanteras"
>abstract="**Adobe hanterat**: Medgivandedata hanteras av dig i Adobe-systemet.<br>**Kundhanterad**: Medgivandedata hanteras av dig i ett externt system och ingen synkronisering av medgivandedata uppdateras i Adobe-systemet såvida det inte initieras av dig."

Om du hanterar samtycke utanför Adobe väljer du alternativet **[!UICONTROL Customer managed]** för att ange en anpassad e-postadress för att avbryta prenumerationen och en egen adress för att avsluta prenumerationen med ett enda klick.

![](assets/surface-list-unsubscribe-custom.png){width="80%"}

>[!WARNING]
>
>Om du använder alternativet **[!UICONTROL Customer managed]** kommer Adobe inte att lagra några data om att prenumerera eller godkänna. Med alternativet **[!UICONTROL Customer managed]** väljer organisationer att använda ett externt system och ansvarar för att hantera sina medgivandedata i ett sådant externt system. Det finns ingen automatisk synkronisering av medgivandedata mellan det externa systemet och [!DNL Journey Optimizer]. Synkronisering av medgivandedata, som kommer från det externa systemet för att uppdatera användarens medgivandedata i [!DNL Journey Optimizer], måste initieras av organisationen som en dataöverföring för att överföra medgivandedata tillbaka till [!DNL Journey Optimizer].

### Konfigurera dekrypterings-API {#configure-decrypt-api}

Om du har markerat alternativet **[!UICONTROL Customer managed]** och anger anpassade slutpunkter och använder dem i en kampanj eller resa, lägger [!DNL Journey Optimizer] till vissa standardprofilspecifika parametrar i medgivandeuppdateringshändelsen <!--sent to the custom endpoint --> när dina mottagare klickar på länken Avbeställ.

Dessa parametrar skickas till slutpunkten på ett krypterat sätt. Det externa tillståndssystemet måste därför implementera ett specifikt API via [Adobe Developer](https://developer.adobe.com){target="_blank"} för att dekryptera de parametrar som skickas av Adobe.

GET-anropet för att hämta de här parametrarna beror på det alternativ för att avbryta prenumerationen som du använder - **[!UICONTROL One-click unsubscribe URL]** eller **[!UICONTROL Mailto (unsubscribe)]**.

<!--To configure the API to send back the information to [!DNL Adobe Journey Optimizer] when a recipient has unsubscribed using the List unsubscribe option with custom endpoints, follow the steps below.-->

+++ Avbeställ en URL med ett klick

Med alternativet **[!UICONTROL One-click unsubscribe URL]** klickar du på länken Avbeställ direkt för att avsluta prenumerationen på användaren.

GET-samtalet är följande:

Slutpunkt: https://platform.adobe.io/journey/imp/consent/decrypt

Frågeparametrar:

* **parametrar**: innehåller den krypterade nyttolasten
* **pid**: krypterat profil-ID

Dessa två parametrar kommer att inkluderas i den händelse för uppdatering av samtycke som skickas till de anpassade slutpunkterna.

Huvudkrav:

* x-api-key
* x-gw-ims-org-id
* behörighet (användartoken från ditt tekniska konto)

+++

+++ Mailto (avsluta prenumeration)

Med alternativet **[!UICONTROL Mailto (unsubscribe)]** skickas ett förifyllt e-postmeddelande till den angivna avanmälningsadressen när du klickar på länken för att avbryta prenumerationen.

GET-samtalet är som följer.

Slutpunkt: https://platform.adobe.io/journey/imp/consent/decrypt

Frågeparametrar:

* **emailParams**: sträng som innehåller parametrarna **params** (krypterad nyttolast) och **pid** (krypterat profil-ID).

Parametrarna **params** och **pid** inkluderas i den händelse för uppdatering av samtycke som skickas till de anpassade slutpunkterna.

Huvudkrav:

* x-api-key
* x-gw-ims-org-id
* behörighet (användartoken från ditt tekniska konto)

+++
