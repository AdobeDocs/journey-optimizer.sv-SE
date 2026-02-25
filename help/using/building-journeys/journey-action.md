---
solution: Journey Optimizer
product: journey optimizer
title: Använda aktiviteten Åtgärd
description: Lär dig hur du lägger till en allmän Action-aktivitet för att konfigurera enskilda åtgärder och grupper med inkommande åtgärder för flera åtgärder på arbetsytan för resan, och hur du lägger till inbyggda kanalåtgärder.
feature: Journeys, Activities, Channels Activity
topic: Content Management
role: User
level: Intermediate
keywords: resa, meddelande, push, sms, e-post, in-app, webb, innehållskort, kodbaserad upplevelse
exl-id: 0ed97ffa-8efc-45a2-99ae-7bcb872148d5
version: Journey Orchestration
source-git-commit: 97fa287d94efb7fb95817fc15268e736517cb629
workflow-type: tm+mt
source-wordcount: '1422'
ht-degree: 0%

---

# Använda aktiviteten Åtgärd {#add-a-message-in-a-journey}

>[!CONTEXTUALHELP]
>id="ajo_action_activity"
>title="Åtgärdsaktivitet"
>abstract="Med aktiviteten **Åtgärd** kan du konfigurera en enskild ursprunglig kanalåtgärd och flera inkommande aktiviteter med möjlighet att lägga till optimering till alla inbyggda kanalåtgärder."

[!DNL Journey Optimizer] innehåller en ny allmän **Åtgärd**-aktivitet som gör att du kan konfigurera en enda inbyggd kanalåtgärd och även flera inkommande aktiviteter.

Åtgärdsaktiviteten erbjuder:

* En förenklad inbyggd åtgärdskonfiguration på arbetsytan för resan.
* Kapaciteten för att skapa inkommande åtgärdsgrupper med flera åtgärder.
* Möjlighet att lägga till optimering till alla inbyggda kanalåtgärder.

Använd aktiviteten **Åtgärd** om du vill lägga till en inbyggd kanalåtgärd för din resa. Denna enhetliga aktivitet konsoliderar alla kanalåtgärder (e-post, push, SMS, in-app, webb, kodbaserad upplevelse och innehållskort) till en enda aktivitetstyp som ersätter de tidigare kanalaktiviteterna.

>[!IMPORTANT]
>
>Alla inbyggda kanaler som nu är tillgängliga via aktiviteten Åtgärd kommer äldre inbyggda kanalaktiviteter att bli inaktuella i mars-versionen. Befintliga resor med äldre åtgärder kommer att fortsätta att fungera som de är - ingen migrering krävs.

Du kan också konfigurera anpassade åtgärder för att skicka meddelanden i [!DNL Journey Optimizer]. [Läs mer](#recommendation)

## Lägg till en inbyggd kanalåtgärd till en resa  {#add-action}

Följ stegen nedan om du vill lägga till en inbyggd kanalåtgärd för din resa med aktiviteten **[!UICONTROL Action]**.

Mer information om vilka kanaler som är tillgängliga under resor finns i tabellen i det här avsnittet: [Kanaler under resor och kampanjer](../channels/gs-channels.md#channels).

1. Starta din resa med en [Event](general-events.md)- eller [Read Audience](read-audience.md)-aktivitet.

1. Dra och släpp en **[!UICONTROL Actions]**-aktivitet på arbetsytan från delen **[!UICONTROL Action]** på paletten.

1. Välj den inbyggda kanalaktivitet som du vill använda under resan.

   ![Listruta med åtgärdstyp som visar kanalåtgärd och alternativ för anpassade åtgärder](assets/journey-action-type-cbe.png)

1. Lägg till en etikett till åtgärden och välj **[!UICONTROL Configure action]**.

   ![Åtgärdsaktivitetskonfigurationsfönster med etikett- och beskrivningsfält](assets/journey-action-configure.png){width="80%"}

1. Du dirigeras till fliken **[!UICONTROL Actions]** på konfigurationsskärmen för reseåtgärder.

   Välj den konfiguration som ska användas för den valda kanalen.

   ![Fliken Åtgärder på menyn Administration som visar anpassade åtgärder och Adobe-åtgärder](assets/journey-action-actions-tab.png)

1. Om du har valt en inkommande kanal kan du lägga till flera åtgärder. [Läs mer](#multi-action)

1. Konfigurera aktiviteten enligt den valda kanalen. Detaljerade konfigurationsriktlinjer finns på länkarna nedan.

   * Lär dig de detaljerade stegen för att skapa en utgående åtgärd på följande sätt:

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../email/create-email.md">
      <img alt="Lead" src="../assets/do-not-localize/email.jpg">
      </a>
      <div><a href="../email/create-email.md"><strong>Skapa e-post</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../push/create-push.md">
      <img alt="Sällan" src="../assets/do-not-localize/push.jpg">
      </a>
      <div>
      <a href="../push/create-push.md"><strong>Skapa push-meddelanden<strong></a>
      </div>
      <p>
      </td>
      <td>
      <a href="../sms/create-sms.md">
      <img alt="Validering" src="../assets/do-not-localize/sms.jpg">
      </a>
      <div>
      <a href="../sms/create-sms.md"><strong>Skapa textmeddelanden (SMS/MMS)</strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

   * Lär dig de detaljerade stegen för att skapa en inkommande åtgärd på följande sätt:

     <table style="table-layout:fixed">
      <tr style="border: 0;">
      <td>
      <a href="../in-app/create-in-app.md">
      <img alt="Lead" src="../assets/do-not-localize/in-app.jpg">
      </a>
      <div><a href="../in-app/create-in-app.md"><strong>Skapa meddelanden i programmet</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../web/create-web.md">
      <img alt="Lead" src="../assets/do-not-localize/web-create.jpg">
      </a>
      <div><a href="../web/create-web.md"><strong>Skapa webbupplevelser</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../content-card/create-content-card.md">
      <img alt="Lead" src="../assets/do-not-localize/sms-config.jpg">
      </a>
      <div><a href="../content-card/create-content-card.md"><strong>Skapa innehållskort</strong>
      </div>
      <p>
      </td>
      <td>
      <a href="../code-based/create-code-based.md">
      <img alt="Sällan" src="../assets/do-not-localize/web-design.jpg">
      </a>
      <div>
      <a href="../code-based/create-code-based.md"><strong>Skapa kodbaserade upplevelser<strong></a>
      </div>
      <p>
      </td>
      </tr>
      </table>

   >[!NOTE]
   >
   >* Varje inkommande upplevelseåtgärd levereras med en 3-dagars **Wait**-aktivitet. [Läs mer](wait-activity.md#auto-wait-node)
   >
   >* För e-postmeddelanden och push-meddelanden kan du aktivera optimering av sändningstid. [Läs mer](send-time-optimization.md)

1. Beroende på aktiviteten kan du visa avancerade parametrar som är specifika för den valda kanalen och åsidosätta vissa standardvärden, till exempel körningsadressen. [Läs mer](about-journey-activities.md#advanced-parameters)

   >[!NOTE]
   >
   >Om de avancerade parametrarna är dolda klickar du på knappen **[!UICONTROL Show read-only fields]** överst i den högra rutan.

1. Använd avsnittet **[!UICONTROL Optimization]** för att köra innehållsexperiment, utnyttja målinriktningsregler eller använda avancerade kombinationer av både experiment och målinriktning.

   Dessa olika alternativ och de steg som ska följas beskrivs i [det här avsnittet](../content-management/gs-message-optimization.md).

1. Använd avsnittet **[!UICONTROL Languages]** för att skapa innehåll på flera språk i din reseåtgärd. Om du vill göra det klickar du på knappen **[!UICONTROL Add languages]** och väljer önskad **[!UICONTROL Language settings]**.

   Detaljerad information om hur du konfigurerar och använder flerspråkiga funktioner finns i [det här avsnittet](../content-management/multilingual-gs.md).

Ytterligare inställningar är tillgängliga beroende på den valda kommunikationskanalen. Expandera avsnitten nedan om du vill ha mer information.

+++**Använd regler för begränsning** (e-post, push, SMS)

I listrutan **[!UICONTROL Business rules]** väljer du en regeluppsättning för att tillämpa regler för appning på din reseåtgärd.

Genom att utnyttja kanalregeluppsättningar kan ni ange frekvensbegränsning efter kommunikationstyp för att förhindra att kunder med liknande meddelanden överbelastas.

[Lär dig arbeta med regeluppsättningar](../conflict-prioritization/rule-sets.md)

+++

+++**Spåra engagemang** (e-post, SMS).

Använd avsnittet **[!UICONTROL Action tracking]** för att spåra hur dina mottagare svarar på dina e-post- eller SMS-leveranser.

Spåra resultaten kan nås från reserapporten när resan är genomförd.

[Läs mer om reserapporter](../reports/journey-global-report-cja.md)

+++

+++**Aktivera läget Snabb leverans** (push).

Snabb leverans är ett [!DNL Journey Optimizer]-tillägg som tillåter mycket snabba push-meddelanden som skickas i stora volymer via kampanjer.

Snabba leveranser används när fördröjningar i meddelandeleverans är affärskritiska när du vill skicka en snabb push-varning på mobiltelefoner, till exempel nyheter till användare som har installerat din nyhetskanalapp.

Lär dig hur du aktiverar läget Snabb leverans för push-meddelanden [på den här sidan](../push/create-push.md#rapid-delivery).

Mer information om prestanda när du använder läget Snabb leverans finns i [[!DNL Adobe Journey Optimizer] produktbeskrivningen](https://helpx.adobe.com/se/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.

+++

+++**Tilldela prioritetspoäng** (webb, i appen, kodbaserad)

I avsnittet **[!UICONTROL Conflict management]** kan du tilldela en prioritetspoäng till reseåtgärden, så att du kan prioritera en inkommande åtgärd när det finns flera reseåtgärder eller kampanjer som använder samma kanalkonfiguration.

Som standard ärvs prioritetspoängen för åtgärden från den övergripande prioritetspoängen för resan.

[Lär dig hur du tilldelar prioritetspoäng till kanalåtgärder](../conflict-prioritization/priority-scores.md#priority-action)

+++

+++**Ange ytterligare leveransregler** (innehållskort)

För innehållskortresor kan du aktivera ytterligare leveransregler för att välja vilka händelser och villkor som utlöser meddelandet.

[Lär dig hur du skapar innehållskort](../content-card/create-content-card.md)

+++

+++**Definiera utlösare** (i appen)

För meddelanden i programmet kan du använda knappen **[!UICONTROL Edit triggers]** för att välja händelser och villkor som utlöser meddelandet.

[Lär dig hur du skapar ett meddelande i appen](../in-app/create-in-app.md)

+++

## Lägg till flera inkommande åtgärder {#multi-action}

>[!CONTEXTUALHELP]
>id="ajo_multi_action_journey"
>title="Lägg till flera inkommande åtgärder"
>abstract="Du kan välja flera inkommande åtgärder inuti en enskild resa. Med den här funktionen kan ni leverera flera kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbåtgärder till olika platser samtidigt, och varje åtgärd innehåller ett visst innehåll."

För att förenkla kundresan kan ni definiera flera inkommande åtgärder inuti en enskild reseåtgärd.

>[!NOTE]
>
>Den här kapaciteten är endast tillgänglig för inkommande kanaler. För närvarande stöds inte utgående kanaler som e-post.

Med den här kapaciteten kan ni leverera olika kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbåtgärder till olika platser samtidigt, utan att behöva skapa flera olika reseåtgärder. Det gör driftsättningen av kundresan enklare och ger smidigare rapportering där alla data samlas i en enda resa.

Du kan till exempel skicka en kodbaserad upplevelse till flera slutpunkter med något annorlunda innehåll. Det gör du genom att skapa flera kodbaserade åtgärder inom samma reseåtgärd, var och en med olika slutpunktskonfigurationer.

Följ stegen nedan för att definiera flera inkommande åtgärder i en enda åtgärdsnod för resan.

1. Starta din resa med en [Event](general-events.md)- eller [Read Audience](read-audience.md)-aktivitet.

1. Dra och släpp en **[!UICONTROL Actions]**-aktivitet på arbetsytan från delen **[!UICONTROL Action]** på paletten.

1. Välj **[!UICONTROL Multi action]** som åtgärdstyp.

   ![Flerfunktionsaktivitet på resepaletten under Orchestration](assets/journey-multi-action.png)

1. Lägg till en etikett om det behövs och välj **[!UICONTROL Configure action]**.

   ![Fleråtgärdskonfigurationsruta med etikett- och beskrivningsfält](assets/journey-multi-action-configure.png){width="60%"}

1. Du dirigeras till fliken **[!UICONTROL Actions]** på konfigurationsskärmen för reseåtgärder.

   ![Fleråtgärdskonfiguration med en lista över åtgärder som ska utföras](assets/journey-multi-action-configuration.png){width="70%"}

1. Välj en inkommande åtgärd (**Kodbaserad upplevelse**, **Meddelande i appen**, **Innehållskort** eller **webb**) i avsnittet **[!UICONTROL Actions]**.

1. Välj kanalkonfigurationen och definiera ett specifikt innehåll för den åtgärden.

1. Använd knappen **[!UICONTROL Add action]** för att välja en annan inkommande åtgärd från listrutan.

   ![Lägg till åtgärdsknapp om du vill inkludera ytterligare åtgärder i en multiaktionsaktivitet](assets/journey-multi-action-add.png){width="80%"}

1. Fortsätt på samma sätt om du vill lägga till fler åtgärder. Du kan lägga till upp till 10 inkommande åtgärder i en åtgärdsgrupp för resan.

När resan är [live](publish-journey.md) aktiveras alla åtgärder samtidigt.

## Uppdatera ett direktinnehåll {#update-live-content}

Ni kan uppdatera innehållet i en inbyggd kanalåtgärd i en direktresa.

Ändringar som görs i innehållet återspeglas inte i resan förrän du sparar åtgärdens egenskaper. [Läs mer](about-journey-activities.md#advanced-parameters)

Det gör du genom att öppna din direktresa, välja kanalaktiviteten och klicka på **Redigera innehåll**.

![Redigera kanalaktivitetsknappen i direktresan](assets/email-action-edit-content.png)

Du kan dock inte ändra de attribut som används i personaliseringen, vare sig det är profilattribut eller kontextuella data (från händelse- eller reseegenskaper).

* Om du ändrade sammanhangsbaserade data visas följande felmeddelande: `ERR_AUTHORING_JOURNEYVERSION_201`

* Om du ändrade profilattribut visas följande felmeddelande: `ERR_AUTHORING_JOURNEYVERSION_202`

Observera att för aktiviteten i appen kan ändringar göras i innehållet medan resan pågår, men utlösare i appen kan inte ändras.

## Skicka med anpassade åtgärder {#recommendation}

I stället för att använda de inbyggda meddelandefunktionerna kan du använda anpassade åtgärder för att konfigurera anslutningen för ett tredjepartssystem för att skicka meddelanden eller API-anrop.

* Om du använder ett tredjepartssystem för att skicka meddelanden kan du skapa en anpassad åtgärd. [Läs mer](../action/action.md)

* Om du arbetar med Adobe Campaign, se följande avsnitt:

   * [[!DNL Journey Optimizer] och Campaign v7/v8](../action/acc-action.md)
   * [[!DNL Journey Optimizer] och Campaign Standard](../action/acs-action.md)
