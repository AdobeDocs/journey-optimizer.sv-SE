---
solution: Journey Optimizer
product: journey optimizer
title: Skapa IP-värmningskampanjer
description: Lär dig hur du skapar en IP-värmerskampanj
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
keywords: IP, pooler, leveransbarhet
hide: true
hidefromtoc: true
source-git-commit: b3e5a825b881736516b3bcd1d368843c3a601100
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# Skapa IP-värmningskampanjer {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="Aktivera alternativet för IP-värmningsplan"
>abstract="När du väljer det här alternativet kan kampanjen användas i en IP-uppvärmningsplan. Kampanjschemat styrs sedan av IP-värmeringsplanen som det är kopplat till."

>[!BEGINSHADEBOX]

Vad du hittar i den här handboken:

* [Kom igång med IP-värmare](ip-warmup-gs.md)
* **[Skapa IP-värmningskampanjer](ip-warmup-campaign.md)**
* [Skapa en IP-värmeringsplan](ip-warmup-plan.md)
* [Kör IP-värmerappen](ip-warmup-execution.md)

>[!ENDSHADEBOX]

Innan du skapar en IP-värdskapsplan i [!DNL Journey Optimizer]måste ni först skapa en eller flera kampanjer med det dedikerade alternativet aktiverat, så att de kan användas i en IP-värmare.

Följ stegen nedan om du vill skapa en IP-värmare.

1. Skapa en [e-post](../email/email-settings.md) kanal [yta](channel-surfaces.md) för domänen och IP-adresserna som du har identifierat för din värdplan.

   >[!NOTE]
   >
   >Lär dig hur du väljer vilken domän och vilka IP-adresser som ska användas i en e-postyta i [det här avsnittet](../email/email-settings.md#subdomains-and-ip-pools).
   >
   >Arbeta med din leveranskonsult för att identifiera den domän och de IP-adresser som ska användas för din IP-warmup-plan.<!--TBC-->

1. Skapa en [kampanj](../campaigns/create-campaign.md) och väljer [E-post](../email/create-email.md#create-email-journey-campaign) åtgärd.

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

1. [Aktivera](../campaigns/review-activate-campaign.md) kampanjen.

   >[!NOTE]
   >
   >För en livekampanj med aktiverad IP-uppvärmningsplan **[!UICONTROL Delete]** knappen är tillgänglig tills den är associerad med en IP-värmeringsplan. När kampanjen väl har använts i en plan kan den inte längre tas bort.

1. Kampanjen visas i **[!UICONTROL Campaigns]** lista. Om du enkelt vill hämta alla IP-värmare som skapats i den aktuella sandlådan kan du filtrera på **[!UICONTROL IP warmup]** kampanjalternativ.

   ![](assets/ip-warmup-campaign-filter.png)

När kampanjen är klar att användas i en IP-värmerapport är den klar att användas. [Läs mer](ip-warmup-plan.md)

<!--Any recommendations when defining an audience? i.e do you have to include all your database or a limited number or according to your Excel file?-->
