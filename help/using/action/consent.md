---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med policyer för samtycke
description: Lär dig hur du arbetar med Adobe Experience Platform medgivandepolicyer
feature: Journeys, Actions, Custom Actions, Privacy, Consent Management
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: politik, styrning, plattform, hälso- och sjukvård, samtycke
exl-id: 01ca4b3e-3778-4537-81e9-97ef92c9aa9e
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 0%

---

# Arbeta med policyer för samtycke {#consent-management}

Dina data kan begränsas av din organisation eller av juridiska bestämmelser. Det är därför viktigt att se till att dataåtgärderna i Journey Optimizer följer [dataanvändningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html){target="_blank"}. These policies are Adobe Experience Platform rules defining which [marketing actions](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html#marketing-actions){target="_blank"} får du utföra på data.

Det finns en typ av principer för dataanvändning **medgivandeprinciper**. De gör det möjligt för er att enkelt anta och tillämpa marknadsföringspolicyer för att respektera kundernas samtycke. [Läs mer om policytillämpning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/enforcement/auto-enforcement.html){target="_blank"}

>[!IMPORTANT]
>
>Samtyckespolicyer är för närvarande bara tillgängliga för organisationer som har köpt Adobe **Hälsovårdssköld** eller **Sköld för skydd av privatlivet och säkerheten** tilläggserbjudanden.

Du kan till exempel [skapa medgivandepolicyer](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#consent-policy){target="_blank"} i Experience Platform för att utesluta kunder som inte har samtyckt till att ta emot e-post, push-meddelanden eller SMS-meddelanden.

* För de interna utgående kanalerna (e-post, push, SMS, direktreklam) är logiken följande:

   * Som standard, om en profil har valt att inte ta emot meddelanden från dig, kommer motsvarande profil att uteslutas från efterföljande leveranser.

   * Om du har Adobe **Hälsovårdssköld** eller **Sköld för skydd av privatlivet och säkerheten** kan du skapa en anpassad medgivandeprincip som åsidosätter standardlogiken. Du kan till exempel definiera en profil som endast skickar e-postmeddelanden till alla personer som har valt att delta. Om det inte finns någon anpassad princip gäller standardprincipen.

  Om du vill tillämpa en anpassad policy måste du definiera en marknadsföringsåtgärd i den policyn och associera den med en kanalyta. [Läs mer](#surface-marketing-actions)

På kundresenivån kan du tillämpa medgivandeprinciper för dina anpassade åtgärder:

* När **konfigurera en anpassad åtgärd** kan ni definiera en kanal- och marknadsföringsåtgärd. [Läs mer](#consent-custom-action)
* När **anpassad åtgärd i en resa** kan ni definiera ytterligare en marknadsföringsåtgärd. [Läs mer](#consent-journey)

## Utnyttja samtyckesregler via kanalytor {#surface-marketing-actions}

I [!DNL Journey Optimizer], samtycke hanteras av Experience Platform [Samtyckesschema](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html){target="_blank"}. By default, the value for the consent field is empty and treated as consent to receive your communications. You can modify this default value while onboarding to one of the possible values listed [here](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html#choice-values){target="_blank"}.

Om du vill ändra värdet på fältet för samtycke kan du skapa en anpassad samtyckespolicy där du definierar en marknadsföringsåtgärd och de villkor som åtgärden utförs under. [Läs mer om marknadsföringsaktiviteter](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html#marketing-actions){target="_blank"}

Om du till exempel vill skapa en samtyckespolicy för att endast rikta sig till profiler som har samtyckt till att ta emot e-postmeddelanden följer du stegen nedan.

1. Se till att din organisation har köpt Adobe **Hälsovårdssköld** eller **Sköld för skydd av privatlivet och säkerheten** tilläggserbjudanden. [Läs mer](https://experienceleague.adobe.com/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield.html){target="_blank"}

1. Skapa en anpassad profil i Adobe Experience Platform (från **[!UICONTROL Privacy]** > **[!UICONTROL Policies]** meny). [Lär dig mer](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#create-policy){target="_blank"}

   <!--![](assets/consent-policy-create.png)-->

1. Välj **[!UICONTROL Consent policy]** skriv och konfigurera ett villkor enligt följande. [Lär dig hur du konfigurerar principer för samtycke](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#consent-policy){target="_blank"}

   1. Under **[!UICONTROL If]** väljer du **[!UICONTROL Email Targeting]** standardmarknadsföringsåtgärd.

      <!--![](assets/consent-policy-marketing-action.png)-->

      >[!NOTE]
      >
      >De viktigaste marknadsföringsåtgärderna från Adobe finns i [det här registret](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#core-actions){target="_blank"}. The steps to create a custom marketing action are listed in [this section](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#create-marketing-action){target="_blank"}.

   1. Välj vad som ska hända när marknadsföringsåtgärden gäller. I detta exempel väljer du **[!UICONTROL Email Marketing Consent]**.

   ![](assets/consent-policy-then.png)

1. Spara och [enable](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#enable){target="_blank"} den här principen.

1. Skapa en e-postyta i Journey Optimizer. [Lär dig mer](../configuration/channel-surfaces.md#create-channel-surface)

1. I informationen om e-postytan väljer du **[!UICONTROL Email Targeting]** marknadsföringsåtgärder.

   ![](assets/surface-marketing-action.png)

Alla policyer för samtycke som är kopplade till den marknadsföringsåtgärden utnyttjas automatiskt för att ta hänsyn till kundernas preferenser.

I det här exemplet är därför alla [e-post](../email/create-email.md) att använda den ytan i en kampanj eller en resa endast skickas till de profiler som har samtyckt till att ta emot e-postmeddelanden från dig. Profiler som inte har samtyckt till att ta emot e-postmeddelanden exkluderas.

## Utnyttja policyer för medgivande genom anpassade åtgärder {#journey-custom-actions}

### Viktiga anteckningar {#important-notes}

I Journey Optimizer kan man också utnyttja medgivande i anpassade åtgärder. Om du vill använda den med inbyggda meddelandefunktioner måste du använda en villkorsaktivitet för att filtrera kunder under kundresan.

Med samtyckeshantering analyseras två olika reseaktiviteter:

* Läsande målgrupp: den hämtade målgruppen beaktas.
* Anpassad åtgärd: samtyckeshantering tar hänsyn till de attribut som används ([åtgärdsparametrar](../action/about-custom-action-configuration.md#define-the-message-parameters)) och de definierade marknadsföringsåtgärderna (nödvändiga marknadsföringsåtgärder och ytterligare marknadsföringsåtgärder).
* Attribut som är en del av en fältgrupp som använder det färdiga unionsschemat stöds inte. De här attributen döljs i gränssnittet. Du måste skapa en annan fältgrupp med ett annat schema.
* Samtyckesprinciper gäller bara när en marknadsföringsåtgärd (obligatorisk eller ytterligare) har ställts in på den anpassade åtgärdsnivån.

Alla andra aktiviteter som används under en resa beaktas inte. Om du påbörjar en resa med en publikkompetens beaktas inte målgruppen.

Om en profil utesluts under en resa genom en samtyckespolicy i en anpassad åtgärd, skickas inte meddelandet till honom, men han fortsätter resan. Profilen går inte till timeout och felsökväg när ett villkor används.

Innan du uppdaterar principer i en anpassad åtgärd som har placerats på en resa måste du se till att resan inte innehåller något fel.

<!--
There are two types of latency regarding the use of consent policies:

* **User latency**: the delay from the time a profile changes a consent settings to the moment it is applied in Experience Platform. This can take up to 48h. 
* **Consent policy latency**: the delay from the time a consent policy is created or updated to the moment it is applied. This can take up to 6 hours
-->

### Konfigurera den anpassade åtgärden {#consent-custom-action}

>[!CONTEXTUALHELP]
>id="ajo_consent_required_marketing_action"
>title="Definiera en obligatorisk marknadsföringsåtgärd"
>abstract="Med den obligatoriska marknadsföringsåtgärden kan ni definiera de marknadsföringsåtgärder som är kopplade till er anpassade åtgärd. Om du till exempel använder den anpassade åtgärden för att skicka e-post kan du välja E-postmarknadsföring. När de används under en resa hämtas och utnyttjas alla medgivandepolicyer som är kopplade till den marknadsföringsåtgärden. Detta kan inte ändras på arbetsytan."

När du konfigurerar en anpassad åtgärd kan två fält användas för samtyckeshantering.

The **Kanal** kan du välja kanal för den här anpassade åtgärden: **E-post**, **SMS**, eller **Push-meddelande**. Den fyller i **Obligatorisk marknadsföringsåtgärd** fält med standardmarknadsföringsåtgärd för den valda kanalen. Om du väljer **övriga**, definieras ingen marknadsföringsåtgärd som standard.

![](assets/consent1.png)

The **Obligatorisk marknadsföringsåtgärd** gör att du kan definiera de marknadsföringsåtgärder som är kopplade till din anpassade åtgärd. Om du till exempel använder den anpassade åtgärden för att skicka e-post kan du välja **Målgruppsanpassning**. När de används under en resa hämtas och utnyttjas alla medgivandepolicyer som är kopplade till den marknadsföringsåtgärden. En standardmarknadsföringsåtgärd har valts, men du kan klicka på nedpilen för att välja alla tillgängliga marknadsföringsåtgärder från listan.

![](assets/consent2.png)

För vissa typer av viktig kommunikation, t.ex. ett transaktionsmeddelande som skickas för att återställa klientens lösenord, kanske du inte vill tillämpa en godkännandeprincip. Sedan väljer du **Ingen** i **Obligatorisk marknadsföringsåtgärd** fält.

De andra stegen för att konfigurera en anpassad åtgärd finns i [det här avsnittet](../action/about-custom-action-configuration.md#consent-management).

### Bygga resan {#consent-journey}

>[!CONTEXTUALHELP]
>id="ajo_consent_required_marketing_action_canvas"
>title="Obligatorisk marknadsföringsåtgärd"
>abstract="En nödvändig marknadsföringsåtgärd definieras när en anpassad åtgärd skapas. Denna nödvändiga marknadsföringsåtgärd kan inte tas bort från åtgärden eller ändras."

>[!CONTEXTUALHELP]
>id="ajo_consent_additional_marketing_action_canvas"
>title="Ytterligare marknadsföringsåtgärder"
>abstract="Lägg till ytterligare en marknadsföringsåtgärd utöver den som krävs. Samtyckesprinciper som är relaterade till båda marknadsföringsåtgärderna kommer att verkställas."

>[!CONTEXTUALHELP]
>id="ajo_consent_refresh_policies_canvas"
>title="Visualisera medgivandeprinciper som ska gälla vid körning"
>abstract="Marknadsföringsåtgärder lägger in medgivandeprinciper som kombinerar åtgärdsparametrar och individuella profiler för att filtrera bort användare. Hämta den senaste definitionen av dessa profiler genom att klicka på knappen för att uppdatera."

När du lägger till den anpassade åtgärden på en resa kan du hantera samtycke med flera alternativ. Klicka på **Visa skrivskyddade fält** för att visa alla parametrar.

The **Kanal** och **Obligatorisk marknadsföringsåtgärd**, som definieras när den anpassade åtgärden konfigureras, visas längst upp på skärmen. Du kan inte ändra dessa fält.

![](assets/consent4.png)

Du kan definiera en **Ytterligare marknadsföringsåtgärder** för att ange typ av anpassad åtgärd. På så sätt kan du definiera syftet med den anpassade åtgärden under den här resan. Utöver den nödvändiga marknadsföringsåtgärden, som vanligtvis är specifik för en kanal, kan ni definiera ytterligare en marknadsföringsåtgärd som är specifik för den anpassade åtgärden under den här resan. Exempel: en träningskommunikation, ett nyhetsbrev, ett friskvårdsmeddelande osv. Både den marknadsföringsåtgärd som krävs och den ytterligare marknadsföringsåtgärden gäller.

![](assets/consent3.png)

Klicka på **Uppdatera profiler** längst ned på skärmen för att uppdatera och kontrollera listan med profiler som har beaktats för den här anpassade åtgärden. Detta är endast avsett som information, när en resa byggs. Med direktresor hämtas och uppdateras godkännandepolicyer automatiskt var sjätte timme.

![](assets/consent5.png)

<!--
The following data is taken into account for consent:

* marketing actions and additional marketing actions defined in the custom action
* action parameters defined in the custom action, see this [section](../action/about-custom-action-configuration.md#define-the-message-parameters) 
* attributes used as criteria in a segment when the journey starts with a Read segment, see this [section](../building-journeys/read-audience.md) 

>[!NOTE]
>
>Please note that there can be a latency when updating the list of policies applied, refer to this [this section](../action/consent.md#important-notes).
-->

De andra stegen för att konfigurera en anpassad åtgärd under en resa beskrivs i [det här avsnittet](../building-journeys/using-custom-actions.md).
