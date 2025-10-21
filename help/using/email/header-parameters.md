---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera e-postrubrikparametrar
description: Lär dig hur du ställer in e-postrubrikparametrar på kanalkonfigurationsnivå
feature: Email, Surface
topic: Administration
role: Admin
level: Experienced
keywords: inställningar, e-post, konfiguration
exl-id: e1556c25-9c79-4362-a5a9-0a46425fa8d9
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Huvudparametrar {#email-header}

När du konfigurerar en ny [e-postkanalskonfiguration](email-settings.md) anger du avsändarnamnen och e-postadresserna som är kopplade till den typ av e-postmeddelanden som skickas med den konfigurationen i avsnittet **[!UICONTROL Header parameters]**.

>[!NOTE]
>
>Om du vill ha större kontroll över e-postinställningarna kan du anpassa rubrikparametrarna. [Läs mer](../email/surface-personalization.md#personalize-header)

* **[!UICONTROL From name]**: Avsändarens namn, till exempel ditt varumärkes namn.
* **[!UICONTROL From email prefix]**: Den e-postadress som du vill använda för din kommunikation.
* **[!UICONTROL Reply to name]**: Namnet som ska användas när mottagaren klickar på knappen **Svara** i sin e-postklientprogramvara.
* **[!UICONTROL Reply to email]**: Den e-postadress som ska användas när mottagaren klickar på knappen **Svara** i sin e-postklientprogramvara. [Läs mer](#reply-to-email)
* **[!UICONTROL Error email prefix]**: Alla fel som genereras av Internet-leverantörer efter några dagar efter att e-post har levererats (asynkrona studsar) tas emot på den här adressen. Meddelanden och svar på frågor tas också emot på den här adressen.

  Om du vill få meddelanden och svar på frågor om frånvaro på en viss e-postadress som inte har delegerats till Adobe måste du konfigurera en [framåtriktad process](#forward-email). I så fall ska du se till att du har en manuell eller automatiserad lösning för att bearbeta e-postmeddelanden som landar i den här inkorgen.

>[!NOTE]
>
>**[!UICONTROL From email prefix]**- och **[!UICONTROL Error email prefix]**-adresserna använder den valda [delegerade underdomänen](../configuration/about-subdomain-delegation.md) för att skicka e-postmeddelandet. Om den delegerade underdomänen till exempel är *marketing.luma.com*:
>
>* Ange *contact* som **[!UICONTROL From email prefix]**. Avsändarens e-postadress är *contact@marketing.luma.com*.
>* Ange *error* som **[!UICONTROL Error email prefix]**. Feladressen är *error@marketing.luma.com*.

![](assets/preset-header.png){width="80%"}

>[!NOTE]
>
>Adresser måste börja med en bokstav (A-Z) och får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt `.` och bindestreck `-`.

## Svara på e-post {#reply-to-email}

När du definierar **[!UICONTROL Reply to email]**-adressen kan du ange vilken e-postadress som helst, förutsatt att det är en giltig adress, i korrekt format och utan att behöva skriva något.

Inkorgen som används för svar kommer att ta emot alla svar, förutom meddelanden som inte är på kontoret och svar på frågor, som tas emot på **Error email** -adressen.

Följ rekommendationerna nedan för att säkerställa korrekt svarshantering:

* Kontrollera att den dedikerade inkorgen har tillräcklig mottagningskapacitet för att kunna ta emot alla svar som skickas med e-postkonfigurationen. Om inkorgen returnerar studsar kanske vissa svar från dina kunder inte tas emot.

* Svar måste behandlas med hänsyn till sekretess och efterlevnadsskyldigheter eftersom de kan innehålla personligt identifierbar information.

* Markera inte meddelanden som skräppost i svarsinkorgen eftersom det påverkar alla andra svar som skickas till den här adressen.

När du definierar adressen **[!UICONTROL Reply to email]** måste du dessutom se till att använda en underdomän som har en giltig MX-postkonfiguration, annars misslyckas e-postkonfigurationsbearbetningen.

Om du får ett felmeddelande när du skickar e-postkonfigurationen betyder det att MX-posten inte är konfigurerad för underdomänen till den angivna adressen. Kontakta administratören för att konfigurera motsvarande MX-post eller använd en annan adress med en giltig MX-postkonfiguration.

>[!NOTE]
>
>Om underdomänen för den adress du angav är en domän som har [delegerats](../configuration/delegate-subdomain.md#full-subdomain-delegation) till Adobe kontaktar du Adobe representant.

## Vidarebefordra e-post {#forward-email}

Om du vill vidarebefordra alla e-postmeddelanden till en viss e-postadress som tagits emot av [!DNL Journey Optimizer] för den delegerade underdomänen kontaktar du Adobe kundtjänst.

>[!NOTE]
>
>Om den underdomän som används för adressen **[!UICONTROL Reply to email]** inte har delegerats till Adobe kan vidarebefordran inte fungera för den här adressen.

Du måste ange:

* Den e-postadress som du väljer. Observera att domänen för e-postadressen för vidarebefordran inte kan matcha någon underdomän som har delegerats till Adobe.
* Namn på din sandlåda.
* Konfigurationsnamnet eller underdomänen som e-postadressen för vidarebefordran ska användas för.
  <!--* The current **[!UICONTROL Reply to (email)]** address or **[!UICONTROL Error email]** address set at the channel configuration level.-->

>[!NOTE]
>
>Det får bara finnas en e-postadress per underdomän. Om flera konfigurationer använder samma underdomän, måste därför samma e-postadress för vidarebefordran användas för alla.

Vidarebefordra e-postadressen har konfigurerats av Adobe. Detta kan ta 3 till 4 dagar.

När du är klar vidarebefordras alla meddelanden som tas emot på **[!UICONTROL Reply to email]**- och **fele-postadresserna** samt alla e-postmeddelanden som skickas till **Från-e-postadressen** till den angivna e-postadressen.

>[!NOTE]
>
>Om vidarebefordran inte är aktiverat ignoreras e-postmeddelanden som skickas direkt till **Från-e-postadressen**.
