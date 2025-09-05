---
solution: Journey Optimizer
product: journey optimizer
title: Åtkomst och prenumeration på systemvarningar
description: Lär dig hur du får åtkomst till och prenumererar på systemvarningar
feature: Journeys, Alerts
topic: Administration
role: User
level: Intermediate
exl-id: 0855ca5b-c7af-41c4-ad51-bed820ae5ecf
source-git-commit: 13623d28ba7b852f7267b5f800f2c9a3afda4a62
workflow-type: tm+mt
source-wordcount: '1198'
ht-degree: 0%

---

# Åtkomst och prenumeration på systemvarningar {#alerts}

När du skapar resor och kampanjer använder du knappen **Varningar** för att kontrollera och åtgärda fel innan du kör eller publicerar dem:

* Lär dig hur du felsöker dina resor på [den här sidan](../building-journeys/troubleshooting.md).
* Lär dig hur du granskar kampanjer på [den här sidan](../campaigns/review-activate-campaign.md).

På den dedikerade **[!UICONTROL Alerts]**-menyn kan du även prenumerera på [!DNL Adobe Journey Optimizer] systemvarningar enligt informationen på den här sidan.

## Få aviseringar {#access-alerts}

När ett fel inträffar kan du få systemvarningar i Journey Optimizer meddelandecenter (varningar i appen) och/eller få ett e-postmeddelande. Följ stegen nedan för att få åtkomst till dessa aviseringar.

<!--These messages can repeat over a pre-defined time interval until the alert has been resolved.-->

>[!NOTE]
>
>Läs mer om varningar i Adobe Experience Platform i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html){target="_blank"}.

Klicka på **[!UICONTROL Administration]** under **[!UICONTROL Alerts]** på den vänstra menyn. Det finns flera förkonfigurerade varningar för Journey Optimizer.

De listas nedan och varje varning beskrivs nedan.

* Registreringar som är specifika för resor:

   * aviseringen [Fel vid anpassad åtgärd för resan](#alert-custom-actions)
   * aviseringen [Läs målutlösaren misslyckades](#alert-read-audiences)

* Aviseringar som är specifika för kanalkonfigurationen:

   * [DNS-posten för AJO-domänen saknar](#alert-dns-record-missing)-varning
  <!--* the [AJO channel configuration failure](#alert-channel-config-failure) alert
   * the [AJO domain certificates renewal unsuccessful](#alert-certificates-renewal) alert-->

## Prenumerera på aviseringar {#subscribe-alerts}

1. Du kan prenumerera på varje varning individuellt från användargränssnittet genom att välja alternativet **[!UICONTROL Subscribe]**.

   ![](assets/alert-subscribe.png){width=80%}

   >[!NOTE]
   >
   >Prenumerationen gäller bara för en viss sandlåda. Du måste prenumerera på varningar för varje enskild sandlåda.

1. Använd samma metod för **[!UICONTROL Unsubscribe]**.

1. Du kan också prenumerera på aviseringar via [I/O-händelsemeddelanden](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html){target="_blank"}. Varningsregler är ordnade i olika prenumerationspaket. Evenemangsprenumerationer som motsvarar specifika Journey Optimizer-aviseringar visas [nedan](#journey-alerts).

1. Om ett oväntat beteende inträffar och/eller om vissa villkor i åtgärderna har nåtts (t.ex. ett eventuellt problem när systemet överskrider ett tröskelvärde), skickas varningsmeddelanden till alla användare i organisationen som prenumererar på dem.

Beroende på prenumerantens önskemål skickas varningar via e-post och/eller direkt i Journey Optimizer meddelandecenter i det övre högra hörnet av användargränssnittet (meddelanden i appen). Välj hur du vill få dessa aviseringar i [!DNL Adobe Experience Cloud] **[!UICONTROL Preferences]**. [Läs mer](../start/user-interface.md#in-product-alerts)

>[!NOTE]
>
>Som standard är endast varningar i appen aktiverade.

<!--To enable email alerting, refer to [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html#enable-email-alerts){target="_blank"}.-->

När en varning har lösts får prenumeranterna ett meddelande om att den har lösts.

## Hantera aviseringar {#manage-alerts}

Om du vill hantera aviseringar markerar du ett objekt och använder knappen **[!UICONTROL More actions]**.

![](assets/alert-more-actions.png){width=80%}

Som standard är alla aviseringar aktiverade. Om du vill inaktivera en varning väljer du alternativet **[!UICONTROL Disable alert]** på menyn **[!UICONTROL More actions]**. Alla prenumeranter på den här aviseringen får inte längre relaterade meddelanden.

Välj **[!UICONTROL Manage alert subscribers]** om du vill visa listan över användare som prenumererar på aviseringen. Använd det tomma fältet för att lägga till fler prenumeranter.

![](assets/alert-subscribers.png){width=80%}

Möjliga varningsstatusvärden visas nedan:

* **[!UICONTROL Enabled]** - Varningen är aktiverad och övervakar utlösarvillkoret.
* **[!UICONTROL Disabled]** - Varningen är inaktiverad och övervakar för närvarande inte utlösarvillkoret. Du kommer inte att få några meddelanden om den här aviseringen.
* **[!UICONTROL Triggered]** - Varningens utlösarvillkor uppfylls.

## Resevarningar {#journey-alerts}

>[!CAUTION]
>
>Adobe Journey Optimizer-specifika aviseringar gäller endast för **live**-resor. Varningar utlöses inte för resor i testläge.

### Fel i anpassad åtgärd för resa {#alert-custom-actions}

Den här varningen varnar dig om en anpassad åtgärd misslyckas. Vi anser att det finns ett fel där det har förekommit mer än 1 procent av felen i en specifik anpassad åtgärd under de senaste fem minuterna. Detta utvärderas var 30:e sekund.

![](assets/alerts-custom-action.png)

Varningar om anpassade åtgärder löses när, under de senaste fem minuterna:

* det inte har förekommit något fel i den anpassade åtgärden (eller fel under tröskelvärdet 1 %),

* eller så har ingen profil nått den anpassade åtgärden.

Prenumerationsnamnet för en I/O-händelse som motsvarar den anpassade åtgärdsaviseringen är **Fel vid anpassad åtgärd för resan**.

Så här felsöker du **anpassade åtgärdsmeddelanden**:

* Kontrollera din anpassade åtgärd med testläge på en annan resa:

  ![](assets/alert-troubleshooting-2.png)

* Se felen i reserapporten.

  ![](assets/alert-troubleshooting-3.png)

* Kontrollera kundens resaHändelser för att hitta mer information om &quot;errorReason&quot;.

* Kontrollera din konfiguration för anpassad åtgärd och verifiera att autentiseringen fortfarande är OK. Gör till exempel en manuell kontroll med Postman.

### Det gick inte att läsa målutlösaren {#alert-read-audiences}

Den här varningen varnar dig om en **Läs målgrupp**-aktivitet inte har bearbetat någon profil 10 minuter efter den schemalagda körningen. Felet kan bero på tekniska problem eller på att målgruppen är tom. Om det här felet orsakas av tekniska problem ska du vara medveten om att försök fortfarande kan göras, beroende på typ av problem (t.ex. om det inte går att skapa exportjobbet kommer vi att försöka igen var 10:e minut med maximalt 1 timme).

![](assets/alerts1.png)

Varningar för **Läs målgruppsaktiviteter** gäller endast återkommande resor. **Läs målgruppsaktiviteter** i liveresor som har ett schema för att köra **En gång** eller **Så snart som möjligt** ignoreras.

Varningar på **Läs målgrupp** löses när en profil kommer in i noden **Läs målgrupp** .

Prenumerationsnamnet för I/O-händelsen som motsvarar aviseringen **Read Audience Trigger Unsuccess** är **Fördröjningar, fel och fel för läsningspubliken på resan**.

Om du vill felsöka **Läs publikaviseringar** kontrollerar du antalet målgrupper i Experience Platform-gränssnittet.

![](assets/alert-troubleshooting-0.png)

![](assets/alert-troubleshooting-1.png)

## Konfigurationsaviseringar {#configuration-alerts}

### DNS-post för AJO-domän saknas {#alert-dns-record-missing}

Den här varningen meddelar dig när viktiga DNS-poster (NS eller CNAME) som krävs för korrekt leveranskonfiguration saknas eller är felkonfigurerade. Utan dessa register kan e-postleveransen bli komprometterad.

>[!NOTE]
>
>* NS-poster är viktiga för fullständig delegering till underdomäner till Adobe. [Läs mer](../configuration/about-subdomain-delegation.md#full-subdomain-delegation)
>
>* CNAME-poster har stöd för konfiguration av CNAME-underdomäner. [Läs mer](../configuration/about-subdomain-delegation.md#cname-subdomain-setup)

Aviseringen **om att DNS-posten för AJO-domänen saknas** aktiveras när systemet upptäcker att NS- eller CNAME-posterna saknas eller inte matchar konfigurationsstandarderna.

1. Klicka på aviseringen som ska dirigeras till den påverkade [underdomänen](../configuration/delegate-subdomain.md) i gränssnittet [!DNL Journey Optimizer].

   <!--For guidance on editing delegated subdomains, see [this section](../configuration/delegate-subdomain.md).-->

1. Åtgärda DNS-konfigurationen genom att ange posterna korrekt och [skicka underdomänen](../configuration/delegate-subdomain.md#submit-subdomain)-delegeringen igen.

   >[!NOTE]
   >
   >Kontrollera att alla poster har skapats korrekt på din domänvärdslösning innan du fortsätter.

1. Om du är osäker på vilka värden som är korrekta kan du skapa en ny underdomän i [!DNL Journey Optimizer] med samma namn som den påverkade underdomänen. [Lär dig hur du konfigurerar en ny underdomän](../configuration/delegate-subdomain.md#set-up-subdomain)

Om ändringarna inte löser problemet kommer samma varning att utlösas igen nästa dag.

<!--The I/O event subscription name corresponding to this alert is xx. > Do we need to mention this?-->

### Konfigurationsfel för AJO-kanaler {#alert-channel-config-failure}

>[!IMPORTANT]
>
>Den här varningen gäller endast för **e-post**-kanalkonfigurationer som använder delegeringstypen [anpassad underdomän](../configuration/delegate-custom-subdomain.md). <!--Other channel types (such as SMS, push, or in-app) are not covered by this alert.-->

Den här varningen utlöses om systemgranskningen upptäcker e-postkanalens konfigurationsproblem. Dessa problem kan vara felkonfigurerade kanalinställningar, ogiltig DNS-konfiguration, problem med utelämningslista, IP-inkonsekvenser eller andra fel som kan påverka e-postleveransen.

Om du får en sådan varning visas lösningsstegen nedan:

1. Klicka på aviseringen om du vill dirigeras till den påverkade [e-postkanalskonfigurationen](../email/get-started-email-config.md) i [!DNL Journey Optimizer]-gränssnittet.

   Mer information om hur du redigerar kanalkonfigurationer finns i [det här avsnittet](../configuration/channel-surfaces.md#edit-channel-surface).

1. Granska konfigurationsinformationen och felmeddelandena. Vanliga orsaker till misslyckanden är:

   * SPF-valideringen misslyckades
   * DKIM-valideringen misslyckades
   * MX-postvalideringen misslyckades
   * Ogiltiga DNS-poster

   >[!NOTE]
   >
   >Möjliga orsaker till konfigurationsfel visas i [det här avsnittet](../configuration/channel-surfaces.md).

1. Lös problemet:

   * Uppdatera kanalkonfigurationen efter behov.
   * Du kan behöva åtgärda specifika DNS-problem som nämns i aviseringen.

   >[!NOTE]
   >
   >Eftersom en enda domän kan associeras med flera kanalkonfigurationer kan DNS-problem för en kanalkonfiguration automatiskt åtgärda relaterade problem i flera konfigurationer.

Om ändringen inte löser problemet kommer samma varning att utlösas igen nästa dag.

När du åtgärdar e-postkonfigurationsproblem bör du tänka på de bästa metoderna som anges nedan:

* Agera snabbt - Åtgärda konfigurationsfel så snart de upptäcks för att undvika avbrott i e-postleveransen.
* Kontrollera alla konfigurationer - Om varningen indikerar flera påverkade e-postkonfigurationer granskar och åtgärdar du var och en av dem.

<!--### AJO domain certificates renewal unsuccessful {#alert-certificates-renewal}

This alert warns you if a domain certificate (CDN, tracking URL) renewal failed for a specific Journey Optimizer subdomain.-->





