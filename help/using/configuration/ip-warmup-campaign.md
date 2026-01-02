---
solution: Journey Optimizer
product: journey optimizer
title: Skapa IP-värmningskampanjer
description: Lär dig hur du skapar en IP-värmerskampanj
feature: Campaigns, IP Warmup Plans
topic: Administration
role: Admin
level: Intermediate
keywords: IP, pooler, leveransbarhet
exl-id: a9995ca1-d7eb-4f8d-a9d9-fe56198ac325
source-git-commit: d1fd0b60ae60c2642108a1eb308564c9d04f5f9e
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Skapa IP-värmningskampanjer {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="Aktivera alternativet för IP-värmningsplan"
>abstract="När du väljer det här alternativet kan kampanjen användas i en IP-uppvärmningsplan. Kampanjschemat styrs sedan av IP-värmeringsplanen som det är kopplat till."

Innan du skapar IP-värmeringsplanen i [!DNL Journey Optimizer] måste du först skapa en eller flera kampanjer som är särskilt utformade för att användas i en IP-värmeringsplan<!--through a dedicated option-->.

Följ stegen nedan om du vill skapa en IP-värmare.

1. Skapa en [konfiguration](channel-surfaces.md) för e-postkanalen för domänen och IP-adresserna som du har identifierat för din värdplan.

   Samarbeta med er leveranskonsult för att identifiera vilken domän och vilka IP-adresser som ska användas. Lär dig hur du väljer dem i en e-postkonfiguration i [det här avsnittet](../email/email-settings.md#ip-pools).

   >[!CAUTION]
   >
   >Redigera inte e-postkanalkonfigurationen efter att IP-värmningsplanen har [startat](ip-warmup-execution.md).

1. Skapa en [kampanj](../campaigns/create-campaign.md) för den schemalagda marknadsföringen och välj åtgärden [E-post](../email/create-email.md#create-email).

   <!--Select the Marketing category. The IP warmup plan activation option is only available for  marketing-type campaigns.-->

1. Välj konfigurationen som du skapade för IP-värmare.

   ![](assets/ip-warmup-campaign-surface.png)

   <!--You must use the same configuration as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. Klicka på **[!UICONTROL Create]**.

1. Välj **[!UICONTROL IP warmup plan activation]** i avsnittet **[!UICONTROL Schedule]**.

   ![](assets/ip-warmup-campaign-plan-activation.png)

   Kampanjen [Schedule](../campaigns/campaign-schedule.md) styrs av IP-värmeringsplanen som den är associerad med, vilket innebär att schemat inte längre är definierat i själva kampanjen.

1. Slutför stegen för att skapa en e-postkampanj, som att definiera kampanjegenskaperna, [målgrupp](../audience/about-audiences.md)<!--best practices for IP warmup in terms of audience?--> och [innehåll](../email/get-started-email-design.md#key-steps).

   >[!IMPORTANT]
   >
   >Publiker som tillåts i en IP-uppvärmningskampanj måste vara [segmentbaserade](../audience/creating-a-segment-definition.md) och skapas med [standardsammanslagningsprincipen](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/merge-policies/overview#default-merge-policy){target="_blank"}.
   >
   >Målgrupper för CSV-uppladdning stöds inte för IP-uppvärmningskampanjer och kommer att resultera i ett fel när kampanjen aktiveras.

   Mer information om hur du konfigurerar en kampanj finns på [den här sidan](../campaigns/get-started-with-campaigns.md).

1. [Aktivera](../campaigns/review-activate-campaign.md) kampanjen. Dess status ändras till **[!UICONTROL Live]**.

   >[!NOTE]
   >
   >[Affärsregler](../conflict-prioritization/rule-sets.md#rule-sets) ska inte användas i IP-värmeringsplaner. Om dessa regler tillämpas kan det bli svårt att nå det önskade antalet målgruppsprofiler för kampanjer.

   Knappen **[!UICONTROL Delete]** är tillgänglig tills den är associerad med en IP-värmeringsplan för en aktiv kampanj med en IP-värmeringsplan aktiverad. När kampanjen väl har använts i en plan kan den inte längre tas bort.

1. Kampanjen visas i listan **[!UICONTROL Campaigns]**. Om du enkelt vill hämta alla IP-uppvärmningskampanjer som skapats i den aktuella sandlådan kan du filtrera efter kampanjalternativet **[!UICONTROL IP warmup]**.

   ![](assets/ip-warmup-campaign-filter.png)

När kampanjen är klar att användas i en IP-värmerapport är den klar att användas. [Läs mer](ip-warmup-plan.md)

En IP-värmare kan bara användas i en IP-värmeringsplan. Men samma kampanj kan användas i en eller flera faser i samma IP-värpportplan. [Läs mer](ip-warmup-plan.md#ip-warmup-plan-tab)

>[!NOTE]
>
>När en livekampanj används i en IP-uppvärmningsplan ändras kampanjens [status](ip-warmup-execution.md#mark-as-completed) till [&#x200B; efter att planen är &#x200B;](../campaigns/manage-campaigns.md#statuses)markerad som slutförd **[!UICONTROL Stopped]**.

