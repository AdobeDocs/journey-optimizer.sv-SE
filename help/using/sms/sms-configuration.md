---
solution: Journey Optimizer
product: journey optimizer
title: Konfigurera SMS-kanalen
description: Lär dig hur du konfigurerar miljön för att skicka textmeddelanden med Journey Optimizer
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 4dcd22ed-bf7e-4789-ab7b-33544c857db8
source-git-commit: f916d91ffd2c41261612f2127f35c41275c9d013
workflow-type: tm+mt
source-wordcount: '342'
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
>abstract="Innan du skickar textmeddelanden (SMS/MMS) måste du integrera providerinställningarna med Journey Optimizer. När du är klar måste du skapa en SMS/MMS-konfiguration. Dessa steg måste utföras av en Adobe Journey Optimizer-systemadministratör."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="Skapa en SMS-kanalkonfiguration"

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_configuration"
>title="Välj SMS-leverantörskonfiguration"
>abstract="Välj API-autentiseringsuppgifter som konfigurerats för din SMS-leverantör."

Innan du skickar SMS eller MMS måste du konfigurera Adobe Journey Optimizer-miljön. Så här gör du:

1. Integrera leverantörsinställningarna med Journey Optimizer:
   * [Med sinch](sms-configuration-sinch.md)
   * [Med Infobip](sms-configuration-infobip.md)
   * [Med en anpassad provider](sms-configuration-custom.md)
1. [Skapa en SMS-konfiguration](sms-configuration-surface.md)

Dessa steg måste utföras av en Adobe Journey Optimizer [systemadministratör](../start/path/administrator.md).

## Förhandskrav{#sms-prerequisites}

Adobe Journey Optimizer är för närvarande integrerat med tredjepartsleverantörer som erbjuder textmeddelandetjänster oberoende av Adobe Journey Optimizer. Providrar som stöds för textmeddelanden och MMS är: **Sinch**, **Twilio** och **Infobip**.

Innan du konfigurerar SMS-kanalen måste du skapa ett konto hos någon av dessa leverantörer för att få din **API-token** och **tjänst-ID**, som du måste konfigurera anslutningen mellan Adobe Journey Optimizer och den tillämpliga providern.

Din användning av textmeddelanden och MMS-tjänster regleras av ytterligare villkor från tillämplig leverantör. Som tredjepartslösningar är Sinch, Twilio och Infobip tillgängliga för Adobe Journey Optimizer-användare via integrering. Adobe kontrollerar inte och ansvarar inte för tredjepartsprodukter. Kontakta din leverantör om du har problem eller vill ha hjälp med SMS/MMS.

>[!CAUTION]
>
>Om du vill komma åt och redigera SMS-underdomäner måste du ha behörigheten **[!UICONTROL Manage SMS Subdomains]** i produktionssandlådan. Läs mer om behörigheter på [den här sidan](../administration/high-low-permissions.md#administration-permissions).
>

