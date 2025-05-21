---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera Infobip-provider
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden och MMS med Journey Optimizer med Infobip
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 7b6dc89a-1a81-49c2-b2a7-bf24b9d215e3
source-git-commit: 528e1a54dd64503e5de716e63013c4fc41fd98db
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---

# Konfigurera Infobip-provider {#sms-configuration-infobip}

>[!BEGINSHADEBOX]

Om nyckelord för anmälan eller avanmälan inte anges används standardmeddelanden för godkännande för att respektera användarens integritet. Om du lägger till anpassade nyckelord åsidosätts standardvärdena automatiskt.

**Standardnyckelord:**

* **Opt-In**: SUBSCRIBE, YES, UNSTOP, START, FORTSÄTT, RESUME, BEGIN
* **Opt-Out**: STOP, QUIT, CANCEL, END, UNSUBSCRIBE, NO
* **Hjälp**: HJÄLP

>[!ENDSHADEBOX]

Så här konfigurerar du Infobip med Journey Optimizer:

1. I den vänstra listen bläddrar du till **[!UICONTROL Administration]** `>` **[!UICONTROL Channels]** och väljer menyn **[!UICONTROL API Credentials]** . Klicka på knappen **[!UICONTROL Create new API credentials]**.

1. Konfigurera dina API-autentiseringsuppgifter enligt anvisningarna nedan.

   * **[!UICONTROL SMS vendor]**: Infobip.

   * **[!UICONTROL Name]**: välj ett namn för API-autentiseringsuppgifterna.

   * **[!UICONTROL API base URL]** och **[!UICONTROL API key]**: gå till webbgränssnittets hemsida eller API-nyckelhanteringssidan för att hitta dina autentiseringsuppgifter. Läs mer i [Infobip-dokumentation](https://www.infobip.com/docs/api){target="_blank"}.

   * **[!UICONTROL Opt-In Keywords]**: ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa **[!UICONTROL Opt-In Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-In Message]**: Ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-In Message]**.

   * **[!UICONTROL Opt-Out Keywords]**: Ange standardvärdet eller nyckelorden som automatiskt kommer att utlösa **[!UICONTROL Opt-Out Message]**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Opt-Out Message]**: Ange det anpassade svar som automatiskt skickas som **[!UICONTROL Opt-Out Message]**.

   * **[!UICONTROL Help Keywords]**: ange standardnyckelord eller anpassade nyckelord som automatiskt kommer att utlösa ditt **hjälpmeddelande**. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Help Message]**: ange det anpassade svar som automatiskt skickas som **hjälpmeddelande**.

   * **[!UICONTROL Double Opt-In Keywords]**: ange nyckelorden som utlöser processen för dubbel anmälan. Om en användarprofil inte finns skapas den när den har bekräftats. Använd kommaseparerade värden för flera nyckelord.

   * **[!UICONTROL Double Opt-In Message]**: Ange det anpassade svar som skickas automatiskt som svar på bekräftelsen av dubbel anmälan.

   * **[!UICONTROL Principal Entity ID]**: Ange ditt tilldelade enhets-ID för DLT-huvudnamn.

   * **[!UICONTROL Content Template ID]**: ange ditt registrerade ID för DLT-innehållsmall.

   * **[!UICONTROL Validity Period]**: Ange meddelandets giltighetsperiod i timmar. Om det inte går att leverera meddelanden inom den här tidsramen gör systemet ytterligare försök att skicka dem igen. Standardgiltighetsperioden är inställd på 48 timmar.

   * **[!UICONTROL Callback Data]**: Ange ytterligare klientdata som ska skickas på Notify URL.

   * **[!UICONTROL Inbound Number]**: lägg till ditt unika inkommande nummer. På så sätt kan du använda samma API-autentiseringsuppgifter för olika sandlådor, var och en med ett eget inkommande nummer.

   * **[!UICONTROL Custom Inbound Keywords]**: Definiera unika nyckelord för specifika åtgärder, t.ex. RABATT, ERBJUDANDEN, REGISTRERING. Dessa nyckelord fångas in och lagras som attribut i profilen, vilket gör att du kan aktivera en segmentkvalificering för direktuppspelning under resan och leverera ett anpassat svar eller en anpassad åtgärd.

   * **[!UICONTROL Default Inbound Reply Message]**: Ange det standardsvar som skickas när en slutanvändare skickar ett inkommande SMS som inte matchar något av de definierade nyckelorden.

1. Klicka på **[!UICONTROL Submit]** när du är klar med konfigurationen av dina API-autentiseringsuppgifter.

1. Klicka på bin-ikonen på menyn **[!UICONTROL API Credentials]** för att ta bort dina API-autentiseringsuppgifter.

1. Om du vill ändra befintliga autentiseringsuppgifter letar du reda på de API-autentiseringsuppgifter du vill ha och klickar på alternativet **[!UICONTROL Edit]** för att göra de ändringar som behövs.

När du har skapat och konfigurerat API-autentiseringsuppgifterna måste du nu skapa en kanalkonfiguration för SMS- och MMS-meddelanden. [Läs mer](sms-configuration-surface.md)
