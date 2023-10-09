---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en kampanj
description: Lär dig skapa kampanjer i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Intermediate
keywords: skapa, optimera, kampanj, yta, meddelanden
exl-id: 617d623c-e038-4b5b-a367-5254116b7815
source-git-commit: 78744537149a18b2e5c8b54689de97c350939a00
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 2%

---

# Skapa en kampanj {#create-campaign}

>[!NOTE]
>
>Innan du skapar en ny kampanj måste du se till att du har en ytkanal (t.ex. en meddelandeförinställning) och en Adobe Experience Platform-målgrupp klar att använda. Läs mer i följande avsnitt:
>
>* [Skapa kanalytor](../configuration/channel-surfaces.md)
>* [Kom igång med målgrupper](../audience/about-audiences.md)

Om du vill skapa en ny kampanj öppnar du **[!UICONTROL Campaigns]** menyn och klicka sedan på **[!UICONTROL Create campaign]**. Du kan också duplicera en befintlig livekampanj och skapa en ny. [Läs mer](modify-stop-campaign.md#duplicate)

## Välj kampanjtyp och kanal {#campaigntype}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="Kampanjtyp"
>abstract="**Schemalagda kampanjer** körs omedelbart eller vid ett angivet datum och är avsedda att skicka meddelanden av marknadsföringstyp. **API-utlöst** kampanjer körs med ett API-anrop. Syftet är att skicka antingen marknadsföringsmeddelanden (reklammeddelanden som kräver användarens samtycke) eller transaktionsmeddelanden (icke-kommersiella meddelanden, som också kan skickas till profiler som inte längre prenumererar i specifika sammanhang)."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_category"
>title="Kampanjkategori"
>abstract="Om du skapar en schemalagd kampanj visas **marknadsföring** text väljs automatiskt. Välj om du vill skicka en **marknadsföring** meddelande (kampanjmeddelande som kräver användarens samtycke) eller **transaktionsbaserad** meddelande (icke-kommersiellt meddelande, som också kan skickas till profiler som inte längre prenumererar i specifika sammanhang)."

1. I **[!UICONTROL Properties]** anger du hur kampanjen ska köras. Det finns två typer av kampanjer:

   * **[!UICONTROL Scheduled]**: kör kampanjen direkt eller på ett angivet datum. Schemalagda kampanjer syftar till att skicka **marknadsföring** meddelanden. De konfigureras och körs från användargränssnittet.

   * **[!UICONTROL API-triggered]**: kör kampanjen med ett API-anrop. API-utlösta kampanjer syftar till att skicka antingen **marknadsföring**, eller **transaktionsbaserad** meddelanden, t.ex. meddelanden som skickas ut efter en åtgärd som har utförts av en person: lösenordsåterställning, kundvagn osv. [Lär dig hur du utlöser en kampanj med API:er](api-triggered-campaigns.md)

1. Om du skapar en schemalagd kampanj visas **marknadsföring** text väljs automatiskt. Välj om du vill skicka en **marknadsföring** eller **transaktionsbaserad** meddelande.&quot;

1. I **[!UICONTROL Actions]** väljer du kanal och kanal för att skicka meddelandet.

   En yta är en konfiguration som har definierats av en [Systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer](../configuration/channel-surfaces.md).

   Endast kanalytor som är kompatibla med marknadsföringskampanjtypen visas i listrutan.

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >Om du skapar en kampanj för push-meddelanden kan du aktivera **[!UICONTROL Rapid delivery mode]**, som är ett Journey Optimizer-tillägg som gör att det går att skicka mycket snabba push-meddelanden i stora volymer. [Läs mer](../push/create-push.md#rapid-delivery)

1. Klicka **[!UICONTROL Create]** för att skapa kampanjen.

## Definiera kampanjegenskaperna {#create}

1. I **[!UICONTROL Properties]** anger du ett namn och en beskrivning för kampanjen.

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../campaigns/content-experiment.md).-->

1. The **Taggar** I kan du tilldela enhetliga Adobe Experience Platform-taggar till kampanjen. På så sätt kan ni enkelt klassificera dem och förbättra sökningen från kampanjlistan. [Lär dig hur du arbetar med taggar](../start/search-filter-categorize.md#tags)

1. Klicka på knappen **[!UICONTROL Manage access]** -knappen. [Läs mer om OLA (Object Level Access Control)](../administration/object-based-access.md)

## Skapa meddelandet och konfigurera spårning {#content}

I **[!UICONTROL Actions]** skapar du meddelandet som ska skickas med kampanjen.

1. Klicka på **[!UICONTROL Edit content]** och sedan skapa och utforma meddelandeinnehållet.

   Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sidor:

   <table style="table-layout:fixed">
    <tr style="border: 0;">
    <td>
    <a href="../email/create-email.md">
    <img alt="Lead" src="../assets/do-not-localize/email.jpg">
    </a>
    <div><a href="../email/create-email.md"><strong>Skapa e-postmeddelanden</strong>
    </div>
    <p>
    </td>
    <td>
    <a href="../push/create-push.md">
      <img alt="Sällan" src="../assets/do-not-localize/push.jpg">
    </a>
    <div>
    <a href="../push/create-push.md"><strong>Skapa push-meddelanden</strong></a>
    </div>
    <p>
    </td>
    <td>
    <a href="../sms/create-sms.md">
      <img alt="Validering" src="../assets/do-not-localize/sms.jpg">
    </a>
    <div>
    <a href="../sms/create-sms.md"><strong>Skapa SMS-meddelanden</strong></a>
    </div>
    <p>
    </td>
    </tr>
    </table>

1. När innehållet är definierat kan du använda **[!UICONTROL Simulate content]** för att förhandsgranska och testa innehållet med testprofiler. [Läs mer](../email/preview.md).

1. Klicka på pilen för att gå tillbaka till skärmen för att skapa kampanjer.

   ![](assets/create-campaign-design.png)

1. I **[!UICONTROL Actions tracking]** anger du om du vill spåra hur mottagarna svarar på leveransen: du kan spåra klick och/eller öppningar.

   Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../reports/campaign-global-report.md)

## Definiera målgruppen {#audience}

Klicka på **[!UICONTROL Select audience]** om du vill visa en lista över tillgängliga Adobe Experience Platform-segment. [Läs mer om segment](../audience/about-audiences.md)

>[!NOTE]
>
>För API-utlösta kampanjer måste målgruppen anges via API-anrop. [Läs mer](api-triggered-campaigns.md)

I **[!UICONTROL Identity namespace]** väljer du det namnutrymme som ska användas för att identifiera individerna från det valda segmentet. [Läs mer om namnutrymmen](../event/about-creating.md#select-the-namespace)

![](assets/create-campaign-namespace.png)

>[!NOTE]
>
>Individer som tillhör ett segment som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kommer inte att omfattas av kampanjen.

<!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

## Schemalägg kampanjen {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="Kampanjschema"
>abstract="Som standard börjar kampanjer vid manuell aktivering och avslutas omedelbart efter att meddelandet har skickats en gång. Du kan dock ange ett specifikt datum och en viss tid för när meddelandet ska skickas. Dessutom kan du ange ett slutdatum för återkommande eller API-utlösta kampanjer. I åtgärdsutlösarna kan du även konfigurera meddelandets sändningsfrekvens så att den passar dina inställningar."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_start"
>title="Kampanjstart"
>abstract="Ange ett datum och en tidpunkt då meddelandet ska skickas."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_end"
>title="Kampanjslut"
>abstract="Ange när en återkommande kampanj ska sluta köras."

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule_triggers"
>title="Kampanjåtgärdsutlösare"
>abstract="Definiera en frekvens som kampanjens meddelande ska skickas med."

Som standard börjar kampanjer när de har aktiverats manuellt och avslutas så snart meddelandet har skickats en gång.

Du kan definiera hur ofta kampanjens meddelande ska skickas. Använd **[!UICONTROL Action triggers]** alternativ på skärmen för att skapa kampanjer för att ange om kampanjen ska köras varje dag, varje vecka eller varje månad.

Om du inte vill genomföra kampanjen direkt efter aktiveringen kan du ange ett datum och en tidpunkt då meddelandet ska skickas med **[!UICONTROL Campaign start]** alternativ. The **[!UICONTROL Campaign end]** kan du ange när en återkommande kampanj ska sluta köras.

![](assets/create-campaign-schedule.png)

När kampanjen är klar kan ni granska och publicera den. [Läs mer](review-activate-campaign.md)
