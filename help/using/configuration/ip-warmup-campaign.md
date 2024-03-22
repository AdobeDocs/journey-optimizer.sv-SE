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
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: a9995ca1-d7eb-4f8d-a9d9-fe56198ac325
source-git-commit: 737b7f59819d235b1f637d4a6b996e97cfddb9fe
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 2%

---

# Skapa IP-värmningskampanjer {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="Aktivera alternativet för IP-värmningsplan"
>abstract="När du väljer det här alternativet kan kampanjen användas i en IP-uppvärmningsplan. Kampanjschemat styrs sedan av IP-värmeringsplanen som det är kopplat till."

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med planer för IP-värmare](ip-warmup-gs.md)
* **[Skapa IP-värmningskampanjer](ip-warmup-campaign.md)**
* [Skapa en IP-värmeringsplan](ip-warmup-plan.md)
* [Kör IP-värmerappen](ip-warmup-execution.md)

>[!ENDSHADEBOX]

Innan du skapar en IP-värdskapsplan i [!DNL Journey Optimizer]måste ni först skapa en eller flera kampanjer som är särskilt utformade för att användas i en IP-värmerapport<!--through a dedicated option-->.

Följ stegen nedan om du vill skapa en IP-värmare.

1. Skapa en [e-post](../email/email-settings.md) kanal [yta](channel-surfaces.md) för domänen och IP-adresserna som du har identifierat för din värdplan.

   >[!NOTE]
   >
   >Lär dig hur du väljer vilken domän och vilka IP-adresser som ska användas i en e-postyta i [det här avsnittet](../email/email-settings.md#subdomains-and-ip-pools).
   >
   >Arbeta med din leveranskonsult för att identifiera den domän och de IP-adresser som ska användas för din IP-warmup-plan.<!--TBC-->

1. Skapa en schemalagd marknadsföring [kampanj](../campaigns/create-campaign.md) och väljer [E-post](../email/create-email.md#create-email-journey-campaign) åtgärd.

   <!--Select the Marketing category. The IP warmup plan activation option is only available for  marketing-type campaigns.-->

1. Välj den yta som du skapade för IP-värmare.

   ![](assets/ip-warmup-campaign-surface.png)

   <!--You must use the same surface as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. Klicka på **[!UICONTROL Create]**.

1. Välj **[!UICONTROL IP warmup plan activation]** i avsnittet **[!UICONTROL Schedule]**.

   ![](assets/ip-warmup-campaign-plan-activation.png)

   Kampanjen [schema](../campaigns/create-campaign.md#schedule) styrs av den IP-värmeringsplan som den kommer att kopplas till, vilket innebär att schemat inte längre definieras i själva kampanjen.

1. Slutför stegen för att skapa en e-postkampanj, t.ex. för att definiera kampanjens egenskaper, [publik](../audience/about-audiences.md)<!--best practices for IP warmup in terms of audience?-->och [innehåll](../email/get-started-email-design.md#key-steps).

   >[!NOTE]
   >
   >Mer information om hur du konfigurerar en kampanj finns i [den här sidan](../campaigns/get-started-with-campaigns.md).

1. [Aktivera](../campaigns/review-activate-campaign.md) kampanjen. Dess status ändras till **[!UICONTROL Live]**.

   >[!NOTE]
   >
   >För en livekampanj med aktiverad IP-uppvärmningsplan **[!UICONTROL Delete]** knappen är tillgänglig tills den är associerad med en IP-värmeringsplan. När kampanjen väl har använts i en plan kan den inte längre tas bort.

1. Kampanjen visas i **[!UICONTROL Campaigns]** lista. Om du enkelt vill hämta alla IP-värmare som skapats i den aktuella sandlådan kan du filtrera på **[!UICONTROL IP warmup]** kampanjalternativ.

   ![](assets/ip-warmup-campaign-filter.png)

När kampanjen är klar att användas i en IP-värmerapport är den klar att användas. [Läs mer](ip-warmup-plan.md)

En IP-värmare kan bara användas i en IP-värmeringsplan. Men samma kampanj kan användas i en eller flera faser i samma IP-värpportplan. [Läs mer](ip-warmup-plan.md#define-phases)

>[!NOTE]
>
>När en livekampanj används i en IP-uppvärmningsplan, efter att planen är [markerad som slutförd](ip-warmup-execution.md#mark-as-completed)ändras kampanjens status till **[!UICONTROL Stopped]**.

