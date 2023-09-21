---
solution: Journey Optimizer
product: journey optimizer
title: Skapa IP-värmningskampanjer
description: Lär dig hur du skapar en IP-värmerskampanj
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP, pooler, grupp, underdomäner, leveransbarhet
hide: true
hidefromtoc: true
source-git-commit: ea86d44f7c9309ff69877e01cea6a13e7907a039
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Skapa IP-värmningskampanjer {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="Aktivera alternativet för IP-värmningsplan"
>abstract="Välj aktiveringsalternativet för IP-warmup-plan. När kampanjen är aktiv kan den kopplas till en IP-värmeringsplan."

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med IP-värmare](ip-warmup-gs.md)
* **[Skapa IP-värmningskampanjer](ip-warmup-campaign.md)**
* [Skapa en IP-värmeringsplan](ip-warmup-plan.md)
* [Kör IP-värmningsplanen](ip-warmup-running.md)

>[!ENDSHADEBOX]

Du måste skapa en eller flera kampanjer med ett visst alternativ aktiverat, så att de kan användas i en IP-uppvärmningsplan.

Följ stegen nedan om du vill skapa en IP-värmare.

1. Skapa ett e-postmeddelande [yta](channel-surfaces.md) för domänen och IP-adresserna som du har identifierat för din värdplan.<!--how do you identify these or who does it at the customer level?-->

   >[!NOTE]
   >
   >Lär dig hur du väljer vilken domän och vilka IP-adresser som ska användas i en e-postyta i [det här avsnittet](../email/email-settings.md#subdomains-and-ip-pools).

1. Skapa en [kampanj](../campaigns/create-campaign.md) och väljer [E-post](../email/create-email.md#create-email-journey-campaign) åtgärd.

1. Välj den yta som du skapade för IP-värmare.

   ![](assets/ip-warmup-campaign-surface.png)

   <!--You must use the same surface as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. Klicka på **[!UICONTROL Create]**.

1. Välj **[!UICONTROL IP warmup plan activation]** i avsnittet **[!UICONTROL Schedule]**.

   ![](assets/ip-warmup-campaign-plan-activation.png)

   Kampanjen [schema](../campaigns/create-campaign.md#schedule) styrs av [IP-värmerapport](ip-warmup-plan.md) det kommer att kopplas till, vilket innebär att schemat inte definieras längre i själva kampanjen.

1. [Aktivera](../campaigns/review-activate-campaign.md) kampanjen. När den är klar att användas i en IP-värmerapport är den klar att användas.

>[!NOTE]
>
>För en livekampanj med aktiverad IP-uppvärmningsplan **[!UICONTROL Delete]** knappen är tillgänglig tills den är associerad med en IP-värmeringsplan.

Mer information om hur du konfigurerar en kampanj finns i [den här sidan](../campaigns/get-started-with-campaigns.md).

<!--Any recommendations when defining an audience? i.e do you have to include all your database or a limited number or according to your Excel file?-->

