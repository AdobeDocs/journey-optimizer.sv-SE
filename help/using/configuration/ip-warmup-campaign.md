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
source-git-commit: 1ec2c406e777e08de97c3ad53cee5986afeb3c44
workflow-type: tm+mt
source-wordcount: '334'
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

Innan du skapar en IP-värdskapsplan i [!DNL Journey Optimizer]måste ni först skapa en eller flera kampanjer med det dedikerade alternativet aktiverat, så att de kan användas i en IP-värmare.

Följ stegen nedan om du vill skapa en IP-värmare.

1. Skapa en [e-post](../email/email-settings.md) kanal [yta](channel-surfaces.md) för domänen och IP-adresserna som du har identifierat för din värdplan.

   >[!NOTE]
   >
   >Lär dig hur du väljer vilken domän och vilka IP-adresser som ska användas i en e-postyta i [det här avsnittet](../email/email-settings.md#subdomains-and-ip-pools).
   >
   >Om det behövs kan du samarbeta med din leveranskonsult för att identifiera den domän och IP-adress som ska användas för din IP-värmeringsplan.<!--TBC-->

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
   >För en livekampanj med aktiverad IP-uppvärmningsplan **[!UICONTROL Delete]** knappen är tillgänglig tills den är associerad med en IP-värmeringsplan. När kampanjen väl har använts i en IP-värmare kan den inte längre tas bort.

1. Kampanjen visas i **[!UICONTROL Campaigns]** lista. Om du enkelt vill hämta alla IP-värmare som skapats i den aktuella sandlådan kan du filtrera efter kampanjalternativet **[!UICONTROL IP warmup]**.

   ![](assets/ip-warmup-campaign-filter.png)

När kampanjen är klar att användas i en IP-värmerapport är den klar att användas. [Läs mer](ip-warmup-plan.md)

<!--Any recommendations when defining an audience? i.e do you have to include all your database or a limited number or according to your Excel file?-->

