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
source-git-commit: 90b7d9bfe40e6d68e22a9f1aa8ef6d302a1035d9
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---

# Kom igång med landningssidor {#get-started-lp}

En landningssida är en fristående webbsida som en användare dirigeras till efter att ha klickat igenom från ett e-postmeddelande, en webbplats, en annons eller någon annan digital plats.

Med [!DNL Journey Optimizer] kan du skapa och utforma landningssidor för att dirigera dina användare till onlineformulär där de kan välja att inte ta emot meddelanden eller prenumerera på en viss tjänst, till exempel ett nyhetsbrev.

➡️ [Läs mer om hur du konfigurerar prenumerationer och skapar landningssidor i den här videon](#video)

## När landningssidor ska användas {#when-to-use}

Använd landningssidor när du vill:

* Låt kunderna **välja att inte ta del av eller avanmäla** för marknadsföringskommunikation från en länk i ett e-postmeddelande eller en kampanj
* Tillåt kunder att **prenumerera eller avbryta prenumeration** på en viss tjänst eller ett nyhetsbrev
* **Samla in samtycke** innan du skickar kommunikation och bekräfta åtgärden med ett automatiskt e-postmeddelande
* Omdirigera användare till ett **dedikerat webbformulär** utan att skapa en extern sida utanför [!DNL Journey Optimizer]

## Innan du börjar {#prerequisites}

Innan du skapar en landningssida utför du följande steg:

1. **Konfigurera en underdomän** - Konfigurera en underdomän som är dedikerad till att vara värd för dina landningssidor. [Konfigurera underdomäner för landningssidor](lp-subdomains.md)
1. **Skapa en förinställning för landningssida** - En förinställning definierar underdomänen och andra inställningar som tillämpas på dina landningssidor. [Skapa en förinställning](lp-presets.md#lp-create-preset)
1. **Skapa en prenumerationslista** (för prenumerationsanvändning) - Krävs om du vill att kunderna ska prenumerera på eller avbryta prenumerationen på en viss tjänst. [Skapa en prenumerationslista](subscription-list.md)

## Så fungerar det {#how-it-works}

När du skapar och distribuerar en landningssida följer du den här sekvensen:

1. **Skapa och konfigurera** din landningssida - Välj en förinställning, konfigurera den primära sidan och lägg till eventuella underordnade sidor. [Skapa en landningssida](create-lp.md)
1. **Designa sidan** - Bygg sidinnehållet och formuläret med hjälp av dra-och-släpp-redigeraren i [!DNL Journey Optimizer]. [Designa en landningssida](design-lp.md)
1. **Testa och publicera** - Förhandsgranska sidan, testa formulärbeteendet och publicera den så att den blir offentlig. [Hantera dina landningssidor](manage-lp.md)
1. **Länk i ett meddelande eller en resa** - Lägg till landningssidans URL i ett e-postmeddelande, en kampanj eller en reseåtgärd så att kunderna kan nå den.

## Viktiga funktioner {#capabilities}

* Utnyttja funktionerna för [!DNL Journey Optimizer]-innehållsdesign för att enkelt bygga **responsiva landningssidor**.
* Konfigurera **anmälnings- och avanmälningsflöden** snabbt och smidigt.
* Skapa prenumerationslistor så att användare kan **prenumerera på en tjänst**. [Läs mer](lp-use-cases.md#subscription-to-a-service)
* Förse dina mottagare med **möjligheten att avbryta prenumerationen** från att ta emot dina meddelanden. [Läs mer](lp-use-cases.md#opt-out)
* Skicka ett **bekräftelsemeddelande** via e-post vid anmälan eller avanmälan. [Läs mer](lp-use-cases.md#send-confirmation-email)

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

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en prenumerationslista, ställer in landningssidor för att erbjuda prenumerationer på eller ta bort prenumerationer från en tjänst, integrerar prenumerationsalternativet (un) i ett meddelande och konfigurerar relevanta resor.

>[!VIDEO](https://video.tv.adobe.com/v/341280?quality=12&learn=on)
