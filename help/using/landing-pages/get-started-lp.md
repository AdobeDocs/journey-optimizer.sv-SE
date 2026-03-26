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
source-git-commit: d0dd382521aeb2c7e18dc547c2ec55fa1472ab8d
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 3%

---

# Kom igång med landningssidor {#get-started-lp}

En landningssida är en fristående webbsida som en användare dirigeras till efter att ha klickat igenom från ett e-postmeddelande, en webbplats, en annons eller någon annan digital plats.

Med [!DNL Journey Optimizer] kan du skapa och utforma landningssidor för att dirigera dina användare till onlineformulär där de kan välja att inte ta emot eller välja att inte ta emot meddelanden eller en viss tjänst som ett nyhetsbrev.

➡️ [Läs mer om hur du konfigurerar prenumerationer och skapar landningssidor i den här videon](#video)

## När landningssidor ska användas {#when-to-use}

Använd landningssidor när du vill:

* Låt kunderna **välja bort eller avanmäla** från marknadsföringskommunikation eller en viss tjänst eller ett visst nyhetsbrev från en länk i ett e-postmeddelande eller en kampanj - inklusive prenumerationslistor för riktade tjänster. [Läs mer](lp-use-cases.md#subscription-to-a-service)
* **Samla in samtycke** innan du skickar kommunikation och skicka ett **bekräftelsemeddelande via e-post** vid anmälan eller avanmälan. [Läs mer](lp-use-cases.md#send-confirmation-email)
* **Hämta eller uppdatera profildata** med formulär på **[!UICONTROL Data Capture]** landningssidor - för progressiv profilering, inställningar, registreringar och liknande scenarier. [Läs mer](#data-capture-lp)
* Omdirigera användare till ett **dedikerat webbformulär** utan att skapa en extern sida utanför [!DNL Journey Optimizer]
* Bygg **responsiva landningssidor** med funktionerna för innehållsdesign i [!DNL Journey Optimizer]

### Datainhämtning med landningssidor {#data-capture-lp}

Med **[!UICONTROL Data Capture]** landningssidor kan du bädda in publicerade formulär så att besökare kan skicka attribut som är skrivna till [!DNL Adobe Experience Platform]-datauppsättningen via den direktuppspelningsanslutning som är konfigurerad i formulärförinställningen. [Lär dig skapa och bädda in formulär på en landningssida](lp-forms.md)

>[!NOTE]
>
>Datainhämtning via landningssidformulär stöds för **kända profiler** (befintliga profiler som identifieras i [!DNL Adobe Experience Platform]). Landningssidan ska öppnas från en **anpassad länk** (till exempel från en e-postkampanj) så att profilens identitet kan matchas när sidan läses in.

Följande är exempel på användningsområden:

1. **Progressiv profilberikning** - Samla in ytterligare attribut från kända kunder, till exempel telefonnummer, födelsedatum eller plats, via en anpassad landningssida för att berika deras befintliga [!DNL Experience Platform] -profil för segmentering och personalisering.

2. **Uppdatering av Inställningscenter** - Tillåt kända prenumeranter att hantera sina kommunikationsinställningar (kanal, ämnesintressen) via en landningssida, där ändringarna vanligtvis återspeglas i deras [!DNL Experience Platform]-profil inom ca 15 minuter.

3. **Registrering av händelse- eller webbinarium** - Hämta händelsespecifika data från kända profiler på en registreringssida, uppdatera profilen med registreringsattribut och utlösa en bekräftelseresa.

4. **Lojalitet eller programregistrering** - Låt befintliga kunder registrera sig för lojalitetsprogram eller medlemsnivåer genom att skicka in ytterligare information via en landningssida, vilket berikar profilen för målinriktning längre fram i kedjan.

5. **Tävlingsbidrag eller tävlingsbidrag** - Låt kända kunder anmäla sig till tävlingar eller lotterier via ett landningsformulär; hämta information om tävlingsbidrag (svar, preferenser eller deklarationer) och skriva dem i profilen för att stödja kvalificering, vinnarurval och uppföljningsresor.

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
<a href="lp-forms.md">
<img alt="Forms-lista för landningssidor i Journey Optimizer" src="../assets/do-not-localize/lp-design.jpg">
</a>
<div>
<a href="lp-forms.md"><strong>Använd formulär på dina landningssidor</strong></a>
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

## Innan du börjar {#prerequisites}

Innan du skapar en landningssida utför du följande steg:

1. **Konfigurera en underdomän** - Konfigurera en underdomän som är dedikerad till att vara värd för dina landningssidor. [Läs mer](lp-subdomains.md)
1. **Skapa en förinställning för landningssida** - En förinställning definierar underdomänen och andra inställningar som tillämpas på dina landningssidor. [Läs mer](lp-presets.md#lp-create-preset)
1. **Skapa en prenumerationslista** (för prenumerationsanvändning) - Krävs om du vill att kunderna ska prenumerera på eller avbryta prenumerationen på en viss tjänst. [Läs mer](subscription-list.md)
1. **Skapa ett formulär** (för datainhämtning) - Krävs när du vill bädda in ett formulär på en **[!UICONTROL Data Capture]** -landningssida och skicka inskickade data till [!DNL Experience Platform]. [Läs mer](lp-forms.md)

## Så fungerar det {#how-it-works}

När du skapar och distribuerar en landningssida följer du den här sekvensen:

1. **Skapa och konfigurera din landningssida** - Välj en förinställning, konfigurera den primära sidan och lägg till eventuella underordnade sidor. [Läs mer](create-lp.md#create-landing-page)
1. **Designa sidan** - Bygg sidinnehållet och formuläret med hjälp av dra-och-släpp-redigeraren i [!DNL Journey Optimizer]. [Läs mer](design-lp.md)
1. **Testa och publicera landningssidan** - Förhandsgranska sidan, testa formulärbeteendet och publicera den så att den blir offentlig. [Läs mer](create-lp.md#test-landing-page)
1. **Länk i ett meddelande eller en resa** - Lägg till landningssidans URL i ett e-postmeddelande, en kampanj eller en reseåtgärd så att kunderna kan nå den. [Läs mer](../email/message-tracking.md#insert-links)

## Instruktionsvideo{#video}

I videon nedan visas hur du skapar en prenumerationslista, ställer in landningssidor för att välja eller avanmäla dig från en tjänst, integrerar alternativet för avanmälan/avanmälan i ett meddelande och konfigurerar relevanta resor.

>[!VIDEO](https://video.tv.adobe.com/v/341280?quality=12&learn=on)
