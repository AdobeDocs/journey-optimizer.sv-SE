---
solution: Journey Optimizer
product: journey optimizer
title: Uppfyll nya krav från DMARC
description: Läs varför och när du måste ange DMARC-post i Journey Optimizer
feature: Subdomains, Channel Configuration, Deliverability
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, domän, e-post, marc, post
exl-id: 15b10a61-6ecd-4ffa-b1c2-21e862263f6d
source-git-commit: 8b755351e25ecae9a2058e63919d6512ea0bf153
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Uppfyll nya krav från DMARC {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="Läs mer om obligatorisk DMARC-uppdatering"
>abstract="Som en del av deras branschledande praxis kräver både Google och Yahoo att du har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem, med början den **1 februari 2024**.<br>Du måste därför se till att du har angett en DMARC-post för alla underdomäner som du har delegerat till Adobe i Journey Optimizer."

Domänbaserad meddelandeautentisering, rapportering och överensstämmelse (DMARC) är en e-postautentiseringsmetod som gör att domänägare kan skydda sin domän från obehörig användning. Genom att erbjuda en tydlig profil till e-postleverantörer/Internet-leverantörer hjälper den till att förhindra att oseriösa aktörer skickar e-postmeddelanden som påstår sig vara från din domän. Implementering av DMARC minskar risken för att legitima e-postmeddelanden markeras som skräppost eller avvisas, och förbättrar e-postleveransen.

Google och Yahoo är en del av deras branschledande arbetsmetoder! båda kräver en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem. Det nya kravet gäller från och med den **1 februari 2024**.

>[!CAUTION]
>
>Misslyckas med att uppfylla det nya kravet från Gmail och Yahoo! förväntas resultera i att e-postmeddelanden landar i skräppostmappen eller blockeras.

Därför rekommenderar Adobe att du ser till att du har DMARC-post konfigurerad för alla underdomäner som du har delegerat till Adobe i [!DNL Journey Optimizer]. Följ stegen nedan som gäller ditt ärende:

* Om du har [delegerat](delegate-subdomain.md#full-subdomain-delegation) dina sändande underdomäner till Adobe följer du ett av alternativen nedan:

   * Konfigurera DMARC på den överordnade domänen för dina delegerade underdomäner **i din värdlösning**.
eller
   * Konfigurera DMARC för dina delegerade underdomäner **i användargränssnittet för[!DNL Journey Optimizer]**-konfigurationen, utan något extra arbete med värdlösningen. [Lär dig hur](dmarc-record.md#implement-dmarc)

* Om du har konfigurerat dina sändande underdomäner med [CNAME](delegate-subdomain.md#cname-subdomain-setup) följer du något av alternativen nedan:

   * Konfigurera DMARC på dina underdomäner eller på den överordnade domänen för dina underdomäner **i din värdlösning**.
eller
   * Konfigurera DMARC för dina delegerade underdomäner **i användargränssnittet för[!DNL Journey Optimizer]**-konfigurationen. [Lär dig hur](dmarc-record.md#implement-dmarc)

  CNAME-konfigurationen kräver dock även ytterligare information i värdlösningen. Se därför till att du är koordinerad med din IT-avdelning så att de kan utföra uppdateringen som beskrivs i [det här avsnittet](dmarc-record.md#implement-dmarc).

<!--The most recent timelines shared by Google and Yahoo! are as follows:

* Google:

    * **February 2024** – Temporary bounces designed to provide warning of non-compliance will begin. Emails will still be delivered as normal after a short delay if you are not yet in compliance. If you are fully in compliance there will be no temporary bounces and you will not be affected.

    * **April 2024** – Blocks will begin for senders who are not in compliance with DMARC requirement. Only a portion of non-compliant email will be blocked at first, with the percentage blocked increasing over time.

    * **June 1st, 2024** – Any sender not in full compliance will experience blocking.

* Yahoo! has not provided exact dates, but has said "the rollout of enforcement will begin in February 2024. Enforcement will be gradually rolled out".
-->

>[!NOTE]
>
>Om du har frågor eller behöver support kontaktar du Adobe Deliverability Consultant eller din Adobe-representant.

**Användbara länkar**

* Läs mer om DMARC i [Handboken om bästa praxis för slutprodukter](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"}
* Läs [Google Gmail-meddelandet](https://blog.google/products/gmail/gmail-security-authentication-spam-protection/){target="_blank"}
* Läs upp [Yahoo! meddelande](https://blog.postmaster.yahooinc.com/post/730172167494483968/more-secure-less-spam){target="_blank"}

<!--Find more guidance about these changes in the [Deliverability Best Practice Guide]-->
