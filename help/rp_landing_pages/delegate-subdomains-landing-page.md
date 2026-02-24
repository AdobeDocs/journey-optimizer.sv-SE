---
solution: Journey Optimizer
product: Journey Optimizer
title: Delegera e-postunderdomäner
description: Delegera e-postunderdomäner
redpen-status: CREATED_||_2025-08-11_21-07-51
exl-id: 7df9b8e2-136a-4ffc-9243-53c7be026d81
source-git-commit: bb50d06e86f9399dfd295b8091aa637abcaea4a8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Delegera e-postunderdomäner{#section-overview}

Delegering av e-postunderdomäner är ett huvudsteg i [kanalkonfigurationen](../using/configuration/get-started-configuration.md) - som krävs innan du kan skicka e-postmeddelanden från Journey Optimizer. Med underdomäner kan du isolera trafiktyper (t.ex. marknadsföring jämfört med transaktioner), skydda huvuddomänens rykte och snabba upp [IP-värmen](../using/configuration/ip-warmup-gs.md). De fungerar tillsammans med [e-postkanalskonfiguration](../using/email/get-started-email-config.md) och [leveransövervakning](../using/reports/deliverability.md) för att säkerställa att meddelandena når inkorgar.

Du kan välja mellan flera konfigurationsmetoder: **fullständig delegering** (Adobe hanterar DNS), **CNAME-konfiguration** eller **anpassad delegering** (du äger certifikat och DNS). Om du börjar med CNAME kan du senare [migrera till anpassad delegering](../using/configuration/custom-subdomain-migration.md) för striktare säkerhet. Det här avsnittet omfattar även DMARC- och PTR-poster, Google TXT-poster för Gmail- och IP-pooler. Mer information om leveransvägledning finns i [Kom igång med leveransmöjligheterna](../using/reports/deliverability.md) och [Övervaka e-postadresser](monitor-reputation-landing-page.md).

## Delegera e-postunderdomäner

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg?lang=sv-SE)

Kom igång med underdomänsdelegering

Lär dig fördelarna, konfigurationsmetoderna och överväganden för att delegera underdomäner i Adobe Journey Optimizer.

[Börja delegera underdomäner](../using/configuration/about-subdomain-delegation.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg?lang=sv-SE)

Delegera en underdomän

Stegvis vägledning för delegering av underdomäner till Adobe, inklusive fullständig delegering och konfigurering av CNAME.

[Lär dig delegera](../using/configuration/delegate-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/screwdriver-wrench.svg?lang=sv-SE)

Konfigurera en anpassad underdomän

Utnyttja din fullständiga ägarskap av dina underdomäner med anpassad delegering - ladda upp dina egna SSL-certifikat och behåll full kontroll över domänkonfigurationen.

[Konfigurera en anpassad underdomän](../using/configuration/delegate-custom-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg?lang=sv-SE)

Migrera från CNAME till anpassad delegering

Migrera befintliga CNAME-konfigurerade underdomäner till anpassad delegering för att uppfylla säkerhetsprinciper och få full kontroll över certifikat.

[Migrera din underdomän](../using/configuration/custom-subdomain-migration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg?lang=sv-SE)

Konfigurera DMARC-poster

Konfigurera DMARC-poster för att förbättra e-postsäkerheten och leveransen för delegerade underdomäner.

[Konfigurera DMARC nu](../using/configuration/dmarc-record.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg?lang=sv-SE)

Lägg till en Google TXT-post

Verifiera underdomäner för Gmail-leverans genom att lägga till Google TXT-poster i Adobe Journey Optimizer.

[Lägg till Google TXT-poster](../using/configuration/google-txt.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=sv-SE)

Få åtkomst till och redigera PTR-poster

Hantera PTR-poster för delegerade underdomäner, inklusive redigering och förståelse av uppdateringsstatus.

[Redigera PTR-poster](../using/configuration/ptr-records.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg?lang=sv-SE)

Skapa IP-pooler

Gruppera IP-adresser för förbättrad e-postleverans och hantera underdomänernas anseende effektivt.

[Skapa IP-pooler](../using/configuration/ip-pools.md)
:::

::::

## Ytterligare resurser

- **[Konfigurera underdomäner för landningssidor](../using/landing-pages/lp-subdomains.md)** - Konfigurera underdomäner för landningssidor och prenumerationsformulär.
- **[Konfigurera webbunderdomäner](../using/web/web-delegated-subdomains.md)** - Delegera underdomäner för webbupplevelser och spårning.
- **[Kom igång med kanalkonfiguration](../using/configuration/get-started-configuration.md)** - Översikt över alla kanalkonfigurationssteg, inklusive delegering av underdomäner.
