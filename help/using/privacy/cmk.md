---
solution: Journey Optimizer
product: journey optimizer
title: Kundhanterade nycklar
description: Lär dig hur du konfigurerar och hanterar kundnycklar för Adobe Journey Optimizer.
feature: Monitoring
role: Developer, User, Admin, Leader
level: Intermediate
exl-id: f0985d1f-0bcf-452f-bd46-dfeca0424f01
source-git-commit: c4ab97999d000d969f6f09f4d84be017d1288f94
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Konfigurera och hantera kundhanterade nycklar för Adobe Journey Optimizer {#cmk}

>[!AVAILABILITY]
>
>[!DNL Customer Managed Keys] för närvarande bara för organisationer som har köpt [Vårdsköld eller sköld för skydd av privatlivet och säkerheten](https://experienceleague.adobe.com/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield.html) tilläggserbjudande.

Med Adobe Journey Optimizer [Hälsovårdssköld](https://www.adobe.com/trust/compliance/hipaa-ready.html) och kunder med skölden för skydd av privatlivet och säkerhet kan utnyttja Azure Customer Managed Keys (CMK) och tillämpa dem på sina data.

Konfigurationsprocessen för Journey Optimizer består av två delar, som utnyttjar teknik från både Adobe Experience Platform och Customer Journey Analytics (CJA):

* Följ stegen som beskrivs i [Kundhanterade nycklar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html) dokumentation.

* Följ stegen som beskrivs i [Kundhanterade nycklar i Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/cmk.html) dokumentation.

  Du måste slutföra den här installationsprocessen, även om du inte har köpt Customer Journey Analytics (CJA), eftersom vissa komponenter i CJA används i bakgrunden.

Om du vill gå igenom installationsprocessen kan du läsa de stegvisa instruktionerna i [Kundhanterade nycklar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html) dokumentation.

Både Adobe Experience Platform och Customer Managed Keys säkerställer datasäkerheten genom att kryptera dem under överföring och i vila. Dina data förblir skyddade, oavsett om du använder kundhanterade nycklar eller inte.

Mer information om datakryptering i Adobe Experience Platform finns i [dokumentation](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html) om datakryptering.
