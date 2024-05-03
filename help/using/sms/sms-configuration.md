---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera SMS-kanalen
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: 016b823161b162cb00e0eae27cd45873752425ba
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Kom igång med SMS-konfiguration {#sms-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api_header"
>title="Konfigurera din SMS-leverantör med Journey Optimizer"
>abstract="Adobe Journey Optimizer skickar textmeddelanden via SMS-tjänstleverantörer. Välj leverantör och fyll i dina API-autentiseringsuppgifter."

>[!CONTEXTUALHELP]
>id="ajo_admin_mms_api_header"
>title="Konfigurera MMS-providern med Journey Optimizer"
>abstract="Adobe Journey Optimizer skickar mediematerial via MMS-tjänsteleverantörer. Välj leverantör och fyll i dina API-autentiseringsuppgifter."

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_api"
>title="Konfigurera din SMS/MMS-leverantör med Journey Optimizer"
>abstract="Innan du skickar textmeddelanden (SMS/MMS) måste du integrera providerinställningarna med Journey Optimizer. När du är klar måste du skapa en SMS/MMS-yta. Dessa steg måste utföras av en Adobe Journey Optimizer-systemadministratör."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/sms/configure-sms/sms-configuration-surface" text="Skapa en SMS-kanalyta"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_configuration"
>title="Välj SMS-leverantörskonfiguration"
>abstract="Välj API-autentiseringsuppgifter som konfigurerats för din SMS-leverantör."

Innan du skickar SMS eller MMS måste du konfigurera Adobe Journey Optimizer-miljön. Så här gör du:

1. Integrera leverantörsinställningarna med Journey Optimizer:
   * [Med sinch](sms-configuration-sinch.md)
   * [Med Infobip](sms-configuration-infobip.md)
   * [Med Twilio](sms-configuration-twilio.md)
1. [Skapa en SMS-yta](#message-preset-sms)

Dessa steg måste utföras av en Adobe Journey Optimizer [Systemadministratör](../start/path/administrator.md).

## Förutsättningar{#sms-prerequisites}

Adobe Journey Optimizer är för närvarande integrerat med tredjepartsleverantörer som erbjuder textmeddelandetjänster oberoende av Adobe Journey Optimizer. Leverantörer som stöds för textmeddelanden och MMS är: **Sinch**, **Twilio** och **Infobip**.

Innan du konfigurerar SMS-kanalen måste du skapa ett konto hos någon av dessa leverantörer för att få tillgång till **API-token** och **Tjänst-ID**, som du måste konfigurera anslutningen mellan Adobe Journey Optimizer och den tillämpliga leverantören.

Din användning av textmeddelanden och MMS-tjänster regleras av ytterligare villkor från tillämplig leverantör. Som tredjepartslösningar är Sinch, Twilio och Infobip tillgängliga för Adobe Journey Optimizer-användare via integrering. Adobe kontrollerar inte, och ansvarar inte för, tredjepartsprodukter. Kontakta din leverantör om du har problem eller vill ha hjälp med SMS/MMS.

>[!CAUTION]
>
>Om du vill komma åt och redigera SMS-underdomäner måste du ha **[!UICONTROL Manage SMS Subdomains]** behörighet i produktionssandlådan. Läs mer om behörigheter i [den här sidan](../administration/high-low-permissions.md#administration-permissions).
>

