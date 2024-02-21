---
solution: Journey Optimizer
product: journey optimizer
title: Följ de nya DMARC-kraven
description: Läs varför och när du måste ange en DMARC-post i Journey Optimizer
feature: Subdomains, Channel Configuration, Deliverability
topic: Administration
role: Admin
level: Experienced
keywords: underdomän, domän, e-post, marc, post
source-git-commit: f59f6a60aabb793aec0cb813ddd9cee10c0fc097
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# Följ de nya DMARC-kraven {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="Läs mer om obligatorisk DMARC-uppdatering"
>abstract="Google och Yahoo kräver att ni har en **DMARC-post** för alla domäner som du använder för att skicka e-post till dem, med början på **1 februari 2024**.<br>Därför måste du se till att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i Journey Optimizer."

Domänbaserad Message Authentication, Reporting och Conformance (DMARC) är en autentiseringsmetod som gör att domänägare kan skydda sin domän från obehörig användning. Genom att erbjuda en tydlig profil till e-postleverantörer/Internet-leverantörer hjälper den till att förhindra att oseriösa aktörer skickar e-postmeddelanden som påstår sig vara från din domän. Implementering av DMARC minskar risken för att legitima e-postmeddelanden markeras som skräppost eller avvisas, och förbättrar e-postleveransen.

Google och Yahoo är en del av deras branschledande arbetsmetoder! kräver båda **DMARC-post** för alla domäner som du använder för att skicka e-post till dem. Detta nya krav börjar gälla **1 februari 2024**. [Läs mer](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html#dmarc){target="_blank"}

>[!CAUTION]
>
>Misslyckas med att uppfylla det nya kravet från Gmail och Yahoo! förväntas resultera i att e-postmeddelanden landar i skräppostmappen eller blockeras.

Därför rekommenderar Adobe starkt att du har DMARC-posten inställd för alla underdomäner som du har delegerat till Adobe i [!DNL Journey Optimizer]. Följ stegen nedan som gäller ditt ärende:

* Om du har [helt delegerad](delegate-subdomain.md#full-subdomain-delegation) Om du vill skicka underdomäner till Adobe följer du något av följande alternativ:

   * Konfigurera DMARC på den överordnade domänen för dina delegerade underdomäner **i din värdlösning**.
eller
   * Konfigurera DMARC för dina delegerade underdomäner **i[!DNL Journey Optimizer]** användargränssnitt för konfiguration - utan extra arbete med värdlösningen. [Lär dig mer](dmarc-record.md#implement-dmarc)

* Om du har konfigurerat dina sändande underdomäner med [CNAME](delegate-subdomain.md#cname-subdomain-delegation)följer du något av alternativen nedan:

   * Konfigurera DMARC på dina underdomäner eller på den överordnade domänen för dina underdomäner **i din värdlösning**.
eller
   * Konfigurera DMARC för dina delegerade underdomäner **i[!DNL Journey Optimizer]** användargränssnitt för konfiguration. [Lär dig mer](dmarc-record.md#implement-dmarc)

  >[!IMPORTANT]
  >
  >CNAME-konfigurationen kräver dock även ytterligare information i värdlösningen. Se därför till att du samarbetar med din IT-avdelning så att de kan utföra de uppdateringar som beskrivs i [det här avsnittet](dmarc-record.md#implement-dmarc).

De senaste tidslinjer som delas av Google och Yahoo! är följande:

* Google:

   * **Februari 2024** - Tillfälliga studsar avsedda att varna för bristande efterlevnad börjar. E-postmeddelanden kommer fortfarande att levereras som vanligt efter en kort fördröjning om du ännu inte uppfyller kraven. Om ni uppfyller alla krav kommer det inte att finnas några tillfälliga studsar och ni kommer inte att påverkas.

   * **April 2024** - Blocken börjar för avsändare som inte uppfyller DMARC-kraven. Endast en del av e-postmeddelandet som inte uppfyller kraven blockeras först, och procentandelen blockerad ökar med tiden.

   * **1 juni 2024** - Avsändare som inte uppfyller alla krav blockeras.

* Yahoo! har inte angett några exakta datum, men har sagt att&quot;genomförandet av lagstiftningen kommer att börja i februari 2024. Tvingande åtgärder kommer att successivt sättas ut&quot;.

>[!NOTE]
>
>Om du har frågor eller behöver support kontaktar du Adobe Deliverability Consultant eller din Adobe-representant.

**Användbara länkar**

* Läs mer om DMARC i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"}
* Mer information om de här ändringarna finns i [Handbok om bästa praxis för leverans](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html){target="_blank"}
* Läs mer om [Google Gmail-meddelande](https://blog.google/products/gmail/gmail-security-authentication-spam-protection/){target="_blank"}
* Läs mer om [Yahoo! meddelande](https://blog.postmaster.yahooinc.com/post/730172167494483968/more-secure-less-spam){target="_blank"}
