---
solution: Journey Optimizer
product: journey optimizer
title: Skapa en kampanj
description: Lär dig skapa kampanjer i Journey Optimizer
feature: Campaigns
topic: Content Management
role: User
level: Beginner
keywords: skapa, optimera, kampanj, yta, meddelanden
exl-id: 617d623c-e038-4b5b-a367-5254116b7815
source-git-commit: f9f2cd339680d0dbff1812e64c5082ca97a34771
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Skapa en kampanj {#create-campaign}

Om du vill skapa en ny kampanj öppnar du menyn **[!UICONTROL Campaigns]** och klickar sedan på **[!UICONTROL Create campaign]**. Du kan också duplicera en befintlig livekampanj och skapa en ny. [Läs mer](modify-stop-campaign.md#duplicate)

>[!NOTE]
>
>Innan du skapar en ny kampanj måste du se till att du har en kanalkonfiguration (dvs. meddelandeyta) och en Adobe Experience Platform-målgrupp klar att använda. Läs mer i följande avsnitt:
>
>* [Skapa kanalkonfigurationer](../configuration/channel-surfaces.md)
>* [Kom igång med målgrupper](../audience/about-audiences.md)

## Välj kampanjtyp {#campaigntype}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_campaign_type"
>title="Kampanjtyp"
>abstract="**Schemalagda kampanjer** körs omedelbart eller på ett angivet datum och är avsedda att skicka meddelanden av marknadsföringstyp. **API-utlösta** kampanjer körs med ett API-anrop. Syftet är att skicka antingen marknadsföringsmeddelanden (reklammeddelanden som kräver användarens samtycke) eller transaktionsmeddelanden (icke-kommersiella meddelanden, som också kan skickas till profiler som inte längre prenumererar i specifika sammanhang)."

1. Välj den typ av kampanj som du vill köra

   * **[!UICONTROL Scheduled - Marketing]**: Kör kampanjen direkt eller på ett angivet datum. Schemalagda kampanjer syftar till att skicka **marknadsföringsmeddelanden**. De konfigureras och körs från användargränssnittet.

   * **[!UICONTROL API-triggered - Marketing/Transactional]**: Kör kampanjen med ett API-anrop. API-utlösta kampanjer syftar till att skicka antingen **marketing** - eller **transactional** -meddelanden, d.v.s. meddelanden som skickas ut efter en åtgärd som utförts av en individ: lösenordsåterställning, kundvagn osv. [Lär dig hur du utlöser en kampanj med API:er](api-triggered-campaigns.md)

   ![](assets/create-campaign-modal.png)

1. Klicka på **[!UICONTROL Create]** för att skapa kampanjen.

## Definiera kampanjegenskaperna {#create}

1. Ange kampanjens namn och en beskrivning i avsnittet **[!UICONTROL Properties]**.

   <!--To test the content of your message, toggle the **[!UICONTROL Content experiment]** option on. This allows you to test multiple variables of a delivery on populations samples, in order to define which treatment has the biggest impact on the targeted population.[Learn more about content experiment](../content-management/content-experiment.md).-->

1. Använd fältet **Taggar** för att tilldela enhetliga Adobe Experience Platform-taggar till kampanjen. På så sätt kan ni enkelt klassificera dem och förbättra sökningen från kampanjlistan. [Lär dig arbeta med taggar](../start/search-filter-categorize.md#tags).

1. Du kan begränsa åtkomsten till den här kampanjen baserat på åtkomstetiketter. Om du vill lägga till en åtkomstbegränsning bläddrar du till knappen **[!UICONTROL Manage access]** högst upp på sidan. Se till att endast markera etiketter som du har behörighet för. [Läs mer om åtkomstkontroll på objektnivå](../administration/object-based-access.md).

## Definiera kampanjmålgruppen {#audience}

En målgrupp är en uppsättning personer som har liknande beteenden och/eller egenskaper. Så här definierar du målgruppen för kampanjen:

1. Klicka på knappen **[!UICONTROL Select audience]** i avsnittet **Målgrupp** för att visa en lista över tillgängliga Adobe Experience Platform-målgrupper. Läs mer om målgrupper i [det här avsnittet](../audience/about-audiences.md).

1. I fältet **[!UICONTROL Identity type]** väljer du vilken typ av nyckel som ska användas för att identifiera personer från den valda målgruppen. Du kan antingen skapa en befintlig identitetstyp eller skapa en ny med hjälp av Adobe Experience Platform identitetstjänst. Standardidentitetsnamnutrymmen visas på [den här sidan](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces#standard){target="_blank"}.

   Endast en identitetstyp tillåts per kampanj. Individer som tillhör ett segment som inte har den valda identitetstypen bland sina olika identiteter kan inte omfattas av kampanjen.

   ![](assets/create-campaign-namespace.png)

   Läs mer om identitetstyper och namnutrymmen i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv){target="_blank"}.

   <!--If you are are creating an API-triggered campaign, the **[!UICONTROL cURL request]** section allows you to retrieve the **[!UICONTROL Campaign ID]** to use in the API call. [Learn more](api-triggered-campaigns.md)-->

>[!IMPORTANT]
>
>* Användning av målgrupper och attribut från [målgruppskomposition](../audience/get-started-audience-orchestration.md) är för närvarande inte tillgängligt för användning med hälso- och sjukvårdsskölden eller skölden för skydd av privatlivet och säkerheten.
>
>* För API-utlösta kampanjer måste målgruppen anges via API-anrop.


## Skapa meddelandet och konfigurera spårning {#content}

1. Markera kanalen i avsnittet **[!UICONTROL Actions]**.

   Listan över tillgängliga kanaler beror på din licensmodell. För API-utlösta transaktionskampanjer är endast e-post-, SMS- och push-meddelandekanaler tillgängliga.

1. Välj kanalkonfiguration.

   En konfiguration definieras av en [systemadministratör](../start/path/administrator.md). Den innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparametrar, underdomän, mobilappar osv. [Läs mer](../configuration/channel-surfaces.md).

   Endast kanalkonfigurationer som är kompatibla med marknadsföringskampanjtypen visas i listrutan.

   ![](assets/create-campaign-action.png)

   >[!NOTE]
   >
   >Om du skapar en kampanj för push-meddelanden kan du aktivera **[!UICONTROL Rapid delivery mode]**, som är ett Journey Optimizer-tillägg som tillåter mycket snabba push-meddelanden som skickas i stora volymer. [Läs mer](../push/create-push.md#rapid-delivery)

1. Klicka på knappen **[!UICONTROL Edit content]** för att skapa och utforma meddelandet. Lär dig detaljerade steg för att skapa meddelandeinnehåll på följande sidor:

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

   När innehållet har definierats kan du använda knappen **[!UICONTROL Simulate content]** för att förhandsgranska och testa innehållet med testprofiler. [Läs mer](../content-management/preview-test.md). Klicka på vänsterpilen om du vill gå tillbaka till skärmen där kampanjen skapades.

   ![](assets/create-campaign-design.png)

1. I avsnittet **[!UICONTROL Content experiment]** kan du använda knappen **[!UICONTROL Create experiment]** för att testa vilket innehåll som fungerar bäst. Funktionerna för innehållsexperimenterande beskrivs i [det här avsnittet](../content-management/content-experiment.md).

1. I avsnittet **[!UICONTROL Actions tracking]** anger du om du vill spåra hur mottagarna svarar på leveransen: du kan spåra klick och/eller öppningar.

   Spåra resultat kan nås från kampanjrapporten när kampanjen har genomförts. [Läs mer om kampanjrapporter](../reports/campaign-global-report-cja.md)

## Schemalägg kampanjen {#schedule}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_schedule"
>title="Kampanjschema"
>abstract="Som standard börjar kampanjer vid manuell aktivering och avslutas omedelbart efter att meddelandet har skickats en gång. Du kan ange ett specifikt datum och en speciell tid för meddelandet som ska skickas. Dessutom kan du ange ett slutdatum för återkommande eller API-utlösta kampanjer. I åtgärdsutlösarna kan du även konfigurera meddelandets sändningsfrekvens så att den passar dina inställningar."

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

Du kan definiera hur ofta kampanjens meddelande ska skickas. Det gör du genom att använda alternativen **[!UICONTROL Action triggers]** på skärmen för att skapa kampanjer för att ange om kampanjen ska köras varje dag, varje vecka eller varje månad.

Om du inte vill köra kampanjen direkt efter aktiveringen kan du ange ett datum och en tidpunkt då meddelandet ska skickas med alternativet **[!UICONTROL Campaign start]**. Med alternativet **[!UICONTROL Campaign end]** kan du ange när en återkommande kampanj ska sluta köras.

![](assets/create-campaign-schedule.png)

När kampanjen är klar kan ni granska och aktivera den. [Läs mer](review-activate-campaign.md)
