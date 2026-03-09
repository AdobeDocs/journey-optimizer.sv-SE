---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med landningssidor
description: Läs om landningssidor i Journey Optimizer
feature: Landing Pages, Subscriptions
topic: Content Management
role: User
level: Beginner
keywords: landning, landningssida, start, komma igång
exl-id: 0da96e32-52ad-4cc3-bac4-844b1f39ed16
source-git-commit: 170bdaaa13fe78ad4c47a6e091c8090156fde8f6
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# Kom igång med landningssidor {#get-started-lp}

En landningssida är en fristående webbsida som en användare dirigeras till efter att ha klickat igenom från ett e-postmeddelande, en webbplats, en annons eller någon annan digital plats.

Med [!DNL Journey Optimizer] kan du skapa och utforma landningssidor för att dirigera dina användare till onlineformulär där de kan välja att inte ta emot eller välja att inte ta emot meddelanden eller en viss tjänst som ett nyhetsbrev.

➡️ [Läs mer om hur du konfigurerar prenumerationer och skapar landningssidor i den här videon](#video)

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-lp.md">
<img alt="Lead" src="../assets/do-not-localize/lp-subscription.jpeg">
</a>
<div><a href="create-lp.md"><strong>Skapa landningssidor</strong>
</div>
<p>
</td>
<td>
<a href="subscription-list.md">
<img alt="Sällan" src="../assets/do-not-localize/lp-list.jpg">
</a>
<div>
<a href="subscription-list.md"><strong>Skapa prenumerationslistor</strong></a>
</div>
<p></td>
<td>
<a href="design-lp.md">
<img alt="Validering" src="../assets/do-not-localize/lp-design.jpg">
</a>
<div>
<a href="design-lp.md"><strong>Utforma landningssidor</strong></a>
</div>
<p>
</td>
<td>
<a href="../reports/lp-report-live.md">
<img alt="Validering" src="../assets/do-not-localize/lp-reporting.jpg">
</a>
<div>
<a href="../reports/lp-report-live.md"><strong>Rapportering</strong></a>
</div>
<p>
</td>
</tr></table>

## När landningssidor ska användas {#when-to-use}

Använd landningssidor när du vill:

* Låt kunderna **välja bort eller avanmäla** från marknadsföringskommunikation eller en viss tjänst eller ett visst nyhetsbrev från en länk i ett e-postmeddelande eller en kampanj - inklusive prenumerationslistor för riktade tjänster. [Läs mer](lp-use-cases.md#subscription-to-a-service)
* **Samla in samtycke** innan du skickar kommunikation och skicka ett **bekräftelsemeddelande via e-post** vid anmälan eller avanmälan. [Läs mer](lp-use-cases.md#send-confirmation-email)
* Omdirigera användare till ett **dedikerat webbformulär** utan att skapa en extern sida utanför [!DNL Journey Optimizer]
* Bygg **responsiva landningssidor** med funktionerna för innehållsdesign i [!DNL Journey Optimizer]

## Innan du börjar {#prerequisites}

Innan du skapar en landningssida utför du följande steg:

1. [**Konfigurera en underdomän**](lp-subdomains.md) - Konfigurera en underdomän som är dedikerad till att vara värd för dina landningssidor.
1. [**Skapa en förinställning för landningssida**](lp-presets.md#lp-create-preset) - En förinställning definierar underdomänen och andra inställningar som tillämpas på dina landningssidor.
1. [**Skapa en prenumerationslista**](subscription-list.md) (för prenumerationsanvändning) - Krävs om du vill att kunderna ska prenumerera på eller avbryta prenumerationen på en viss tjänst.

## Så fungerar det {#how-it-works}

När du skapar och distribuerar en landningssida följer du den här sekvensen:

1. [**Skapa och konfigurera din landningssida**](create-lp.md) - Välj en förinställning, konfigurera den primära sidan och lägg till eventuella underordnade sidor.
1. [**Designa sidan**](design-lp.md) - Bygg sidinnehållet och formuläret med hjälp av dra-och-släpp-redigeraren i [!DNL Journey Optimizer].
1. [**Testa**](create-lp.md#test-landing-page) och [**publicera**](create-lp.md#publish-landing-page) landningssidan - Förhandsgranska sidan, testa formulärbeteendet och publicera den så att den blir offentlig.
1. [**Länk i ett meddelande eller en resa**](../email/message-tracking.md#insert-links) - Lägg till landningssidans URL i ett e-postmeddelande, en kampanj eller en reseåtgärd så att kunderna kan nå den.

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en prenumerationslista, ställer in landningssidor för att välja eller avanmäla dig från en tjänst, integrerar alternativet för avanmälan/avanmälan i ett meddelande och konfigurerar relevanta resor.

>[!VIDEO](https://video.tv.adobe.com/v/341280?quality=12&learn=on)
