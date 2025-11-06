---
solution: Journey Optimizer
product: journey optimizer
title: Kundhanterade nycklar
description: Lär dig hur du konfigurerar och hanterar kundnycklar för Adobe Journey Optimizer.
feature: Privacy, Monitoring
role: Developer, User, Admin, Leader
level: Intermediate
exl-id: f0985d1f-0bcf-452f-bd46-dfeca0424f01
source-git-commit: f9e1ae68fcfb9ecc12e0b80a067ca29186fc01f7
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Konfigurera och hantera kundhanterade nycklar {#cmk}

>[!AVAILABILITY]
>
>Funktionen [!DNL Customer Managed Keys] är för närvarande bara tillgänglig för organisationer som har köpt tilläggserbjudandet [Healthcare Shield eller Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield.html){target="_blank"} .

Med Adobe Journey Optimizer har [kunder inom hälso- och sjukvårdsskölden](https://www.adobe.com/trust/compliance/hipaa-ready.html){target="_blank"} och skölden för sekretess och säkerhet möjlighet att utnyttja Azure Customer Managed Keys (CMK) och tillämpa dem på sina data.

Konfigurationsprocessen för Journey Optimizer består av två delar, som utnyttjar teknik från både Adobe Experience Platform och Customer Journey Analytics (CJA):

* Följ stegen som beskrivs i dokumentationen för [Kundhanterade nycklar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html){target="_blank"}.
* Följ stegen som beskrivs i dokumentationen för [Kundhanterade nycklar i Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/cmk.html){target="_blank"}.

  Du måste slutföra den här installationsprocessen, även om du inte har köpt Customer Journey Analytics (CJA), eftersom vissa komponenter i CJA används i bakgrunden.

Om du vill gå igenom installationsprocessen kan du läsa de stegvisa instruktionerna i [Kundhanterade nycklar i dokumentationen för Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html){target="_blank"}.

Både Adobe Experience Platform och Customer Managed Keys säkerställer datasäkerheten genom att kryptera dem under överföring och i vila. Dina data förblir skyddade, oavsett om du använder kundhanterade nycklar eller inte.

Mer information om datakryptering i Adobe Experience Platform finns i [dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html){target="_blank"} om datakryptering.
