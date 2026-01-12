---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera kampanjåtgärden
description: Lär dig hur du konfigurerar kampanjåtgärden.
feature: Campaigns
topic: Content Management
role: User
level: Beginner
mini-toc-levels: 1
keywords: skapa, optimera, kampanj, yta, meddelanden
exl-id: fed96e48-2e54-4bd4-ae17-77434d1b90eb
source-git-commit: 27de3d2171e6f6575eb66ada20f951f6cb3abc98
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---

# Konfigurera kampanjåtgärden {#action-campaign-action}

Använd fliken **[!UICONTROL Actions]** för att välja en kanalkonfiguration för meddelandet och konfigurera ytterligare inställningar som spårning, innehållsexperiment eller flerspråkigt innehåll.

1. **Välj kanal**

   Navigera till fliken **[!UICONTROL Actions]**, klicka på knappen **[!UICONTROL Add action]** och markera kommunikationskanalen.

   ![](assets/create-campaign-add-action.png)

   >[!NOTE]
   >
   >Mer information om vilka kanaler som stöds finns i tabellen i det här avsnittet: [Kanaler i resor och kampanjer](../channels/gs-channels.md#channels).
   >
   >Vilka kanaler som är tillgängliga varierar beroende på licensmodell och tillägg.

   Om du väljer en inkommande kanal (kodbaserad upplevelse, meddelande i appen, innehållskort eller webbåtgärd) kan du lägga till fler inkommande åtgärder - för totalt upp till 10 åtgärder i en enda kampanj. [Lär dig hur](#multi-action)

1. **Välj en kanalkonfiguration**

   En konfiguration definieras av en [systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Lär dig hur du konfigurerar kanalkonfigurationer](../configuration/channel-surfaces.md)

   ![](assets/create-campaign-action.png)

1. **Utnyttjandeoptimering**

   Använd avsnittet **[!UICONTROL Optimization]** för att köra innehållsexperiment, utnyttja målinriktningsregler eller använda avancerade kombinationer av både experiment och målinriktning. Dessa olika alternativ och de steg som ska följas beskrivs i [det här avsnittet](../content-management/gs-message-optimization.md).
<!--
1. **Create a content experiment**

    Use the **[!UICONTROL Content experiment]** section to define multiple delivery treatments in order to measure which one performs best for your target audience. Click the **[!UICONTROL Create experiment]** button then follow the steps detailed in this section: [Create a content experiment](../content-management/content-experiment.md).-->

1. **Lägg till flerspråkigt innehåll**

   Använd avsnittet **[!UICONTROL Languages]** för att skapa innehåll på flera språk i kampanjen. Om du vill göra det klickar du på knappen **[!UICONTROL Add languages]** och väljer önskad **[!UICONTROL Language settings]**. Detaljerad information om hur du konfigurerar och använder flerspråkiga funktioner finns i [det här avsnittet](../content-management/multilingual-gs.md).

Ytterligare inställningar är tillgängliga beroende på den valda kommunikationskanalen. Expandera avsnitten nedan om du vill ha mer information.

+++**Använd regler för begränsning** (e-post, direktreklam, push, SMS)

I listrutan **[!UICONTROL Business rules]** väljer du en regeluppsättning för att tillämpa regler för appning på kampanjen. Genom att utnyttja kanalregeluppsättningar kan ni ange frekvensbegränsning efter kommunikationstyp för att förhindra att kunder med liknande meddelanden överbelastas. [Lär dig arbeta med regeluppsättningar](../conflict-prioritization/rule-sets.md)

+++

+++**Spåra engagemang** (e-post, SMS).

Använd avsnittet **[!UICONTROL Action tracking]** för att spåra hur dina mottagare svarar på dina e-post- eller SMS-leveranser. Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../reports/campaign-global-report-cja.md)

+++

+++**Aktivera läget Snabb leverans** (push).

Snabb leverans är ett [!DNL Journey Optimizer]-tillägg som tillåter mycket snabba push-meddelanden som skickas i stora volymer via kampanjer. Snabba leveranser används när fördröjningar i meddelandeleverans är affärskritiska när du vill skicka en snabb push-varning på mobiltelefoner, till exempel nyheter till användare som har installerat din nyhetskanalapp. Lär dig hur du aktiverar läget Snabb leverans för push-meddelanden [på den här sidan](../push/create-push.md#rapid-delivery).

Mer information om prestanda när du använder läget Snabb leverans finns i [Adobe Journey Optimizer produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}.

+++

+++**Tilldela prioritetspoäng** (webb, i appen, kodbaserad)

Om ni tilldelar kampanjens prioritetspoäng kan ni prioritera en inkommande kampanj när det finns en begränsning, till exempel ett frekvenstak. Ange ett numeriskt värde (från 0-100). Observera att ju högre tal desto högre prioritet. [Lär dig hur du tilldelar prioritetspoäng till resor och kampanjer](../conflict-prioritization/priority-scores.md)

+++

+++**Ange ytterligare leveransregler** (innehållskort)

För innehållskortkampanjer kan du aktivera ytterligare leveransregler för att välja vilka händelser och villkor som utlöser meddelandet. [Lär dig skapa innehållskort](../content-card/create-content-card.md)

+++

+++**Definiera utlösare** (i appen)

För meddelanden i programmet kan du använda knappen **[!UICONTROL Edit triggers]** för att välja händelser och villkor som utlöser meddelandet. [Lär dig skapa ett meddelande i appen](../in-app/create-in-app.md)

+++

## Lägg till flera inkommande åtgärder {#multi-action}

>[!CONTEXTUALHELP]
>id="ajo_multi_action"
>title="Lägg till flera inkommande åtgärder"
>abstract="Du kan välja flera inkommande åtgärder inuti en enda kampanj. Med den här funktionen kan ni leverera flera kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbåtgärder till olika platser samtidigt, och varje åtgärd innehåller ett visst innehåll."

För att förenkla er kampanjsamordning kan ni definiera flera inkommande åtgärder i en enda kampanj, där varje åtgärd innehåller ett visst innehåll.

>[!NOTE]
>
>Den här funktionen är bara tillgänglig för inkommande kanaler. För närvarande stöds inte utgående kanaler som e-post.

Med den här funktionen kan ni leverera olika kodbaserade upplevelser, meddelanden i appen, innehållskort eller webbåtgärder till olika platser samtidigt, utan att behöva skapa flera kampanjer. Det gör driftsättningen av er kampanj enklare och ger smidigare rapportering, med alla data samlade i en enda kampanj.

Du kan till exempel skicka en kodbaserad upplevelse till flera slutpunkter med något annorlunda innehåll. Det gör du genom att skapa flera kodbaserade åtgärder inom samma kampanj, där var och en har olika slutpunktskonfigurationer.

Följ stegen nedan för att definiera flera inkommande åtgärder i en kampanj.

1. Välj en inkommande åtgärd (**Kodbaserad upplevelse**, **Meddelande i appen**, **Innehållskort** eller **webb**) i avsnittet **[!UICONTROL Actions]**.

1. Välj kanalkonfigurationen och definiera ett specifikt innehåll för den åtgärden.

1. Använd knappen **[!UICONTROL Add action]** för att välja en annan inkommande åtgärd från listrutan.

   ![](assets/create-campaign-multi-action.png){width="80%"}

1. Fortsätt på samma sätt om du vill lägga till fler åtgärder. Du kan lägga till upp till 10 inkommande åtgärder i en kampanj.

När kampanjen är [live](review-activate-campaign.md) aktiveras alla åtgärder samtidigt.

## Nästa steg {#next}

När kampanjåtgärden är klar kan ni utforma innehållet i den. [Läs mer](campaign-content.md)
