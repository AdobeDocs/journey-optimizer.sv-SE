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
source-git-commit: 1349da209bc90dd8ebad0bd309f89039aa6ea3f2
workflow-type: tm+mt
source-wordcount: '2127'
ht-degree: 0%

---

# Åtkomst och prenumeration på systemvarningar {#alerts}

När du skapar resor och kampanjer använder du knappen **Varningar** för att kontrollera och åtgärda fel innan du kör eller publicerar dem.

* Lär dig felsöka dina resor på [den här sidan](../building-journeys/troubleshooting.md)

* Lär dig hur du granskar och aktiverar kampanjer: [Åtgärdskampanjer](../campaigns/review-activate-campaign.md) | [&#x200B; API-utlösta kampanjer &#x200B;](../campaigns/review-activate-api-triggered-campaign.md) | [Samordnade kampanjer](../orchestrated/start-monitor-campaigns.md)


Dessutom kan varningsmeddelanden skickas till alla användare i organisationen som har prenumererat på dem när vissa villkor är uppfyllda. Dessa aviseringar är tillgängliga på den dedikerade **[!UICONTROL Alerts]**-menyn. Adobe Experience Platform innehåller flera fördefinierade varningsregler som du kan aktivera för din organisation. Dessutom kan du prenumerera på [!DNL Adobe Journey Optimizer]-specifika systemaviseringar så som beskrivs på den här sidan.

>[!NOTE]
>
>Läs mer om varningar i Adobe Experience Platform i [Adobe Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html){target="_blank"}.

Klicka på **[!UICONTROL Administration]** under **[!UICONTROL Alerts]** på den vänstra menyn. Flera förkonfigurerade varningar för Journey Optimizer finns tillgängliga på fliken **Bläddra**.

![](assets/updated-alerts-list.png){width=50%}

* Registreringar som är specifika för resor:

   * aviseringen [Läs målutlösaren misslyckades](#alert-read-audiences)
   * aviseringen [Felfrekvens för anpassad åtgärd överskreds](#alert-custom-action-error-rate) (ersätter den tidigare felaviseringen för anpassad åtgärd på resan)
   * varningen [Profilens ignoreringsfrekvens har överskridits](#alert-discard-rate)
   * [Profilens felfrekvens överskreds](#alert-profile-error-rate)-varningen
   * aviseringen [Resa publicerad](#alert-journey-published)
   * aviseringen [Resan slutförd](#alert-journey-finished)
   * aviseringen [Custom Action Capping utlöstes](#alert-custom-action-capping)

* Aviseringar som är specifika för kanalkonfigurationen:

   * [DNS-posten för AJO-domänen saknar](#alert-dns-record-missing)-varning
   * meddelandet [Fel i AJO-kanalkonfiguration](#alert-channel-config-failure)
     <!--* the [AJO domain certificates renewal unsuccessful](#alert-certificates-renewal) alert-->

## Prenumerera på aviseringar {#subscribe-alerts}

Om ett oväntat beteende inträffar och/eller om vissa villkor i åtgärderna har nåtts (t.ex. ett eventuellt problem när systemet överskrider ett tröskelvärde), skickas varningsmeddelanden till alla användare i organisationen som prenumererar på dem.

Du kan prenumerera på varje avisering individuellt från användargränssnittet, antingen globalt på menyn **[!UICONTROL Alerts]** (se [Global prenumeration](#global-subscription)) eller enhetsspecifikt för en viss resa (se [Unitär prenumeration](#unitary-subscription)).

Beroende på prenumerantens önskemål skickas varningar via e-post och/eller direkt i Journey Optimizer meddelandecenter i det övre högra hörnet av användargränssnittet (meddelanden i appen). Välj hur du vill få dessa aviseringar i [!DNL Adobe Experience Cloud] **[!UICONTROL Preferences]**. [Läs mer](../start/user-interface.md#in-product-alerts)

När en varning har lösts får prenumeranterna ett meddelande om att den har lösts. Varningarna löses efter 1 timme för att skydda mot växlande värden.


### Global prenumeration {#global-subscription}

Följ de här stegen för att prenumerera/avbryta prenumerationen på en avisering för alla resor och kampanjer:

1. Bläddra till kontrollpanelen **[!UICONTROL Alerts]** på den vänstra menyn och välj alternativet **[!UICONTROL Subscribe]** för den avisering som du vill prenumerera på.

   ![Prenumererar på en avisering](assets/alert-subscribe.png){width=80%}

   >[!NOTE]
   >
   >Prenumerationen gäller bara för en viss sandlåda. Du måste prenumerera på varningar för varje enskild sandlåda.

1. Använd samma metod för **[!UICONTROL Unsubscribe]**.

Du kan också prenumerera via [I/O-händelsemeddelanden](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html){target="_blank"}. Varningsregler är ordnade i olika prenumerationspaket. Evenemangsprenumerationer som motsvarar specifika Journey Optimizer-aviseringar visas [nedan](#journey-alerts).

### Enhetsspecifik prenumeration {#unitary-subscription}

Följ de här stegen för att prenumerera/avbryta prenumerationen på en viss resa:

1. Bläddra till reseinventeringen och välj alternativet **[!UICONTROL Subscribe to alerts]** för en viss resa.

   ![Prenumerera på en avisering för en viss resa](assets/subscribe-journey-alert.png){width=75%}

1. Välj aviseringar. Följande aviseringar är tillgängliga: [Profilens borttagningsfrekvens har överskridits](#alert-discard-rate), [Anpassad åtgärdsfelfrekvens har överskridits](#alert-custom-action-error-rate), [Profilfelsfrekvens har överskridits](#alert-profile-error-rate), [Resan har publicerats](#alert-journey-published), [Resan har slutförts](#alert-journey-finished) och [Anpassad åtgärd har startats](#alert-custom-action-capping).

1. Om du vill avbryta prenumerationen på en varning avmarkerar du den på samma skärm.

1. Klicka på **[!UICONTROL Save]** för att bekräfta.

<!--To enable email alerting, refer to [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html#enable-email-alerts){target="_blank"}.-->

## Resevarningar {#journey-alerts}


Alla resemeddelanden som är tillgängliga i användargränssnittet listas nedan.

>[!CAUTION]
>
>Adobe Journey Optimizer-specifika aviseringar gäller endast för **live**-resor. Varningar utlöses inte för resor i testläge.

### Det gick inte att läsa målutlösaren {#alert-read-audiences}

Den här varningen varnar dig om en **Läs målgrupp**-aktivitet inte har bearbetat någon profil 10 minuter efter den schemalagda körningen. Felet kan bero på tekniska problem eller på att målgruppen är tom. Om det här felet orsakas av tekniska problem ska du vara medveten om att försök fortfarande kan göras, beroende på typ av problem (t.ex. om det inte går att skapa exportjobbet kommer vi att försöka igen var 10:e minut med maximalt 1 timme).

Varningar för **Läs målgruppsaktiviteter** gäller endast återkommande resor. **Läs målgruppsaktiviteter** i liveresor som har ett schema för att köra **En gång** eller **Så snart som möjligt** ignoreras.

Varningar på **Läs målgrupp** löses när en profil kommer in i noden **Läs målgrupp** eller efter en timme.

Prenumerationsnamnet för I/O-händelsen som motsvarar aviseringen **Read Audience Trigger Unsuccess** är **Fördröjningar, fel och fel för läsningspubliken på resan**.

Om du vill felsöka **Läs publikaviseringar** kontrollerar du antalet målgrupper i Experience Platform-gränssnittet.

### Frekvensen för ignorerade profiler har överskridits {#alert-discard-rate}

Den här varningen varnar dig om förhållandet mellan profilen och de angivna profilerna har överskridits under de senaste 5 minuterna. Standardtröskelvärdet är 20 % men du kan [definiera ett anpassat tröskelvärde](#custom-threshold).

Klicka på namnet på varningen för att kontrollera varningsinformationen och konfigurationen.

![](assets/profile-discard-alert.png)

Det finns flera orsaker till att en profil kan ignoreras, vilket informerar felsökningsmetoden. Några vanliga orsaker är:

* Profilen ignoreras vid inträde eftersom den redan bor i den unitära resan. För att lösa detta måste du se till att profilen har tillräckligt med tid för att avsluta resan innan nästa händelse kommer för den profilen.
* Identitet har inte angetts för profilen, eller så används inte namnutrymmet som används av läsarresan i den profilen. För att lösa detta måste namnutrymmet i resan matcha det identitetsnamnutrymme som används av profilerna.
* Händelsens genomströmningshastighet har överskridits. För att lösa detta måste du se till att händelser som kommer in i systemet inte överskrider dessa gränser.


### Felfrekvens för anpassad åtgärd överskreds {#alert-custom-action-error-rate}

Den här varningen varnar dig om förhållandet mellan anpassade åtgärdsfel och slutförda HTTP-anrop under de senaste 5 minuterna har överskridit tröskelvärdet. Standardtröskelvärdet är 20 % men du kan [definiera ett anpassat tröskelvärde](#custom-threshold).

>[!NOTE]
>
>Den här varningen ersätter den tidigare varningen **Fel vid anpassad åtgärd för resa**.

Klicka på namnet på varningen för att kontrollera varningsinformationen och konfigurationen.

Fel med anpassade åtgärder kan inträffa av flera olika anledningar. Om du vill felsöka felen kan du:

* Kontrollera din anpassade åtgärd med [testläge](../building-journeys/testing-the-journey.md) på en annan resa.
* Kontrollera din [reserapport](../reports/journey-live-report.md) för att se felorsaker till åtgärden.
* Kontrollera kundens resaHändelser för att hitta mer information om &quot;errorReason&quot;.
* Kontrollera att den anpassade åtgärden är korrekt konfigurerad och verifiera att autentiseringen fortfarande är giltig. Gör till exempel en manuell kontroll med Postman.
* Kontrollera att slutpunkten är nåbar och att den anpassade åtgärden kan nå den via den anpassade åtgärdsanslutningskontrollen.
* Verifiera autentiseringsuppgifterna, kontrollera Internetanslutningen osv.

### Profilfelsfrekvensen har överskridits {#alert-profile-error-rate}

Den här varningen varnar dig om förhållandet mellan felprofiler och angivna profiler under de senaste 5 minuterna har överskridit tröskelvärdet. Standardtröskelvärdet är 20 % men du kan [definiera ett anpassat tröskelvärde](#custom-threshold).

Klicka på namnet på varningen för att kontrollera varningsinformationen och konfigurationen.

Om du vill felsöka profilfel kan du fråga data i steghändelser för att förstå var och varför profilen misslyckades under resan.

### Journey Published {#alert-journey-published}

Den här varningen meddelar dig när en resa har publicerats av en person på arbetsytan.

Det här är en informativ varning som hjälper dig att hålla reda på händelser i din organisations livscykel. Det finns inga lösningsvillkor eftersom detta är ett engångsmeddelande.

### Resan avslutad {#alert-journey-finished}

Den här varningen meddelar dig när en resa är klar. Definitionen av&quot;färdig&quot; varierar beroende på resetyp:

| Resetyp | Återkommande? | Har slutdatum? | Definition av&quot;färdigt&quot; |
|--------------|------------|---------------|--------------------------|
| Läs målgrupp | Nej | n/a | 91 dagar efter att körningen har startat |
| Läs målgrupp | Ja | Nej | 91 dagar efter att körningen har startat |
| Läs målgrupp | Ja | Ja | När slutdatumet nås |
| Händelseutlöst resa | n/a | Ja | När slutdatumet nås |
| Händelseutlöst resa | n/a | Nej | När den stängs i användargränssnittet eller via API |

Det här är en informativ varning som hjälper dig att hålla reda på slutförandet av en resa. Det finns inga lösningsvillkor eftersom detta är ett engångsmeddelande.

### Anpassad åtgärd som aktiveras {#alert-custom-action-capping}

Den här varningen varnar dig när capping har utlösts för en anpassad åtgärd. Takning används för att begränsa antalet anrop som skickas till en extern slutpunkt för att förhindra överbelastning av slutpunkten.

Klicka på namnet på varningen för att kontrollera varningsinformationen och konfigurationen.

När capping aktiveras innebär det att det maximala antalet API-anrop har uppnåtts inom den definierade tidsperioden och att ytterligare anrop stryps eller köas. Läs mer om att sätta stopp för anpassade åtgärder på [den här sidan](../action/about-custom-action-configuration.md#custom-action-enhancements-best-practices).

Den här varningen löses när appningen inte längre är aktiv eller när inga profiler når den anpassade åtgärden under utvärderingsperioden.

Så här felsöker du problem med appning:

* Granska takkonfigurationen för din anpassade åtgärd för att se till att gränserna är lämpliga för ditt användningsfall.
* Kontrollera om antalet API-anrop är större än förväntat och överväg att justera inställningarna för kundresan.
* Övervaka den externa slutpunkten för att säkerställa att den kan hantera den förväntade inläsningen.

## Konfigurationsaviseringar {#configuration-alerts}

Varningar för kanalkonfigurationsövervakning som finns i användargränssnittet visas nedan.

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

## Hantera aviseringar {#manage-alerts}

### Redigera en varning

Du kan kontrollera information om en varning genom att klicka på raden. Namn, status och meddelandekanaler visas i den vänstra panelen.
Använd knappen **[!UICONTROL More actions]** för att redigera researney-aviseringar. Du kan sedan definiera en [anpassad tröskel](#custom-threshold) för dessa aviseringar.

![](assets/alert-more-actions.png){width=60%}

### Definiera ett anpassat tröskelvärde {#custom-threshold}

Du kan ange tröskelvärden för [reseaviseringar](#journey-alerts). Tröskelvärdesvarningarna över standardvärdet är 20 %.

Så här ändrar du tröskelvärdet:

1. Bläddra till skärmen **Varningar**
1. Klicka på knappen **[!UICONTROL More actions]** för aviseringen för att uppdatera
1. Ange det nya tröskelvärdet och bekräfta. Det nya tröskelvärdet gäller för **alla** resor


![](assets/alert-threshold.png){width=60%}

>[!CAUTION]
>
>Tröskelvärdena är globala för alla resor och kan inte ändras individuellt per resa.

### Inaktivera en varning

Som standard är alla aviseringar aktiverade. Om du vill inaktivera en avisering väljer du alternativet **[!UICONTROL Disable alert]**: alla prenumeranter på den här aviseringen kommer inte längre att få relaterade meddelanden.


### Varningsstatus

Möjliga varningsstatusvärden visas nedan:

* **[!UICONTROL Enabled]** - Varningen är aktiverad och övervakar utlösarvillkoret.
* **[!UICONTROL Disabled]** - Varningen är inaktiverad och övervakar för närvarande inte utlösarvillkoret. Du kommer inte att få några meddelanden om den här aviseringen.
* **[!UICONTROL Triggered]** - Varningens utlösarvillkor uppfylls.


### Visa och uppdatera prenumeranter {#manage-subscribers}

Välj **[!UICONTROL Manage alert subscribers]** om du vill visa listan över användare som prenumererar på aviseringen.

![](assets/alert-subscribers.png){width=80%}

Om du vill lägga till fler prenumeranter anger du deras e-postadresser avgränsade med kommatecken och väljer **[!UICONTROL Update]**.

Om du vill ta bort prenumeranter tar du bort deras e-postadress från de aktuella prenumeranterna och väljer **[!UICONTROL Update]**.

## Ytterligare resurser {#additional-resources-alerts}

* Lär dig hur du felsöker dina resor på [den här sidan](../building-journeys/troubleshooting.md).
* Lär dig hur du granskar kampanjer på [den här sidan](../campaigns/review-activate-campaign.md).
