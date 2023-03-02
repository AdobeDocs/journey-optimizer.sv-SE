---
solution: Journey Optimizer
product: journey optimizer
title: Arbeta med AEM mallar
description: Lär dig hur du skapar mallar i AEM och exporterar dem till Journey Optimizer
hide: true
hidefromtoc: true
feature: Overview
topic: Content Management
role: User
level: Beginner
badge: label="Beta" type="Informative"
source-git-commit: a162f70dceb3bef635085840fc304e0da2c33eed
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---

# Arbeta med Adobe Experience Manager-mallar {#aem-templates}

>[!AVAILABILITY]
>
>Integrering med Adobe Experience Manager är för närvarande endast tillgängligt som betaversion för utvalda användare.
> Använd [det här formuläret](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4Wf0cbVTQ3tCpW_unE-w8-JUN1FaNlAzNkhPSUdaSkJXVFRCNTRJNVRFSy4u){target="_blank"} för att ge feedback.

Med Adobe Journey Optimizer kan du skapa skräddarsydda meddelanden via Adobe Experience Manager webbplatser. Börja med att designa mallarna med Adobe Experience Manager innehållskällor och skicka dem sedan till Adobe Journey Optimizer. När mallarna har delats kan de användas i Adobe Journey Optimizer e-postdesigner, vilket förenklar arbetet med att skapa och skicka meddelanden till rätt målgrupp.

## Förutsättningar {#prerequisites}

Innan du börjar använda den här funktionen bör du kontrollera att du uppfyller följande krav:

* **Inställningar för Experience Manager**

   Den här funktionen är tillgänglig från och med Adobe Experience Manager 6.5.14. Du måste ansluta till Adobe Experience Manager Sites i din Managed Services Author-miljö.

   Som en del av betaprogrammet utfördes Cloud Servicen av Adobe i Adobe Experience Manager för att ansluta till Adobe Journey Optimizer.

* **Behörigheter**

   Om du vill skapa, redigera och ta bort innehållsmallar i Adobe Journey Optimizer måste du ha **[!DNL Manage Library Items]** behörighet som ingår i **[!DNL Content Library Manager]** produktprofil. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)


## Skyddsritningar och begränsningar{#aem-templates-limitations}

Om du vill optimera din användning av Adobe Experience Manager med Adobe Journey Optimizer ännu mer är det viktigt att du är medveten om följande extra skyddsförslag och begränsningar:

* Mallen Experience Manager får inte innehålla personalisering. Personalisering bör endast utföras i Journey Optimizer.

* Export av gruppmallar stöds inte för närvarande, mallar måste exporteras individuellt.

* Det går för närvarande inte att synkronisera mellan Experience Manager och Journey Optimizer. Om en Experience Manager-mall ändras efter att den har skickats till Journey Optimizer måste användaren exportera om mallen och skicka den till Journey Optimizer igen.

## Skicka en mall till Journey Optimizer{#aem-templates-send}

Om du vill exportera en Adobe Experience Manager-mall till Adobe Journey Optimizer följer du stegen nedan:

1. På Adobe Experience Manager hemsida väljer du **[!UICONTROL Outbound Marketing]**.

   ![](assets/aem-outbound-menu.png)

1. Gå till ditt innehållsbibliotek och välj den mall som du vill exportera till Journey Optimizer.

   Du kan också skapa en ny sida från grunden. [Läs mer](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/authoring/managing-pages.html?lang=en#creating-a-new-page)

   ![](assets/aem-send-template.png)

1. När du har valt mallen väljer du **[!UICONTROL Send to]** på den avancerade menyn.

   ![](assets/aem-advanced-menu.png)

1. Ange **[!UICONTROL Name]** i innehållsmallen och välj mål **[!UICONTROL Sandbox]**.

   ![](assets/aem-send-template-settings.png)

1. När du har klickat på **[!UICONTROL Send]** kommer exportprocessen att börja. När exporten är klar visas följande meddelande i användargränssnittet: &quot;Mallen &quot;XX&quot; har skickats till AJO&quot;.

Mallen läggs till i Adobe Journey Optimizer-innehållsmallar för den valda sandlådan.

## Använda och anpassa en Adobe Experience Manager-mall{#aem-templates-perso}

När mallen Experience Manager är tillgänglig i Journey Optimizer som innehållsmall kan du identifiera och infoga det innehåll som behövs för e-postmeddelandet, inklusive personalisering.

1. I Journey Optimizer från **[!UICONTROL Content template]** öppnar du den importerade mallen.

   ![](assets/aem_ajo_1.png)

1. Genom att klicka på **[!UICONTROL Alert]** kan du snabbt kontrollera om några viktiga inställningar saknas. Detta hjälper till att säkerställa att dina meddelanden är korrekt konfigurerade och förhindrar eventuella fel eller problem.

   ![](assets/aem_ajo_2.png)

1. I **[!UICONTROL Template properties]** klickar du på **[!UICONTROL Manage access]** om du vill tilldela egna eller grundläggande dataanvändningsetiketter till mallen. [Läs mer om OLAC (Object Level Access Control)](../administration/object-based-access.md)

1. Om du vill anpassa din AEM ytterligare och lägga till anpassad anpassning till ditt innehåll klickar du på **[!UICONTROL Edit content]**. På så sätt kan du enkelt göra ändringar och anpassa mallen efter dina specifika behov. [Läs mer](get-started-email-design.md)

   >[!NOTE]
   >
   > Om du vill redigera och anpassa mallen kan du bara använda kompatibilitetsläget.

1. När innehållsmallen är klar [testa och validera den](content-templates.md#test-template).

1. När innehållet har definierats kan du använda det när du skapar ny e-post genom att bläddra i **[!UICONTROL Saved templates]** samling. Välj sedan **[!UICONTROL Use this template]**.

   Lär dig redigera och anpassa e-postinnehåll i [det här avsnittet](content-from-scratch.md).

   ![](assets/aem_ajo_3.png)

När din e-post är klar slutför du konfigurationen av [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md)och aktivera det för att skicka meddelandet.
