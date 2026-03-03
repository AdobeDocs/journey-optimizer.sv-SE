---
solution: Journey Optimizer
product: journey optimizer
title: CC (Carbon Copy) i konfiguration av e-postkanal
description: Konfigurera synliga CC-mottagare i Journey Optimizer e-postkanal. Lär dig hur du ställer in CC-fältet, hur det skiljer sig från BCC och begränsningar.
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
hide: true
hidefromtoc: true
keywords: CC, kopia, e-post, kanalkonfiguration, e-posthuvuden, BCC
badge: label="Begränsad tillgänglighet" type="Informative"
source-git-commit: 5b804de873124b8ff53d55c943b3c95649dd9a7c
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---

# Lägg till ett CC-fält i e-postmeddelanden {#cc-email-field}

>[!CONTEXTUALHELP]
>id="ajo_admin_config_cc"
>title="Definiera en e-postadress för CC"
>abstract="Du kan lägga till ett synligt CC-fält (kopia) i e-postmeddelanden som skickas med den här kanalkonfigurationen. Ange en fast e-postadress eller använd personalisering (profilattribut eller kontextvariabel). Tänk på att CC-användningen räknas in i den aktuella meddelandevolymen."

>[!AVAILABILITY]
>
>Den här funktionen är tillgänglig för alla kunder med begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst.

Du kan lägga till ett synligt CC-fält (kopia) i e-postmeddelanden som skickas av [!DNL Journey Optimizer] via dina resor och kampanjer. Den här valfria funktionen är konfigurerad på [kanalkonfigurationsnivå](channel-surfaces.md), tillsammans med e-postrubriksparametrarna och alternativet för BCC-e-post.

>[!CAUTION]
>
>CC-funktionsanvändningen räknas av mot det antal meddelanden som du är licensierad för. Aktivera det bara där du behöver synliga CC-mottagare. Kontrollera om det finns licensierade volymer i ditt avtal.

Precis som [BCC](archiving-support.md#bcc-email) är CC-fältet avsett att skicka en kopia av e-postmeddelandet till en ytterligare adress. Den skiljer sig dock från BCC på följande sätt:

* CC-e-postadressen är synlig för den primära mottagaren så att den primära mottagaren kan se vem som har kopierats och veta vem han/hon ska kontakta för uppföljning.
* Till skillnad från CC stöder e-postfältet i CC personalisering, vilket gör att du kan använda en kanalkonfiguration för många scenarier och skicka kopian till rätt person per mottagare (t.ex. deras relationshanterare). För API-utlösta kampanjer gör detta att du kan CC-adressen som är relevant för en viss händelse eller transaktion.

>[!NOTE]
>
>Om du behöver behålla kopior där adressen inte får vara synlig för mottagaren i arkiverings- eller kompatibilitetssyfte använder du [BCC](archiving-support.md#bcc-email) i stället för CC.

## Aktivera e-post för CC {#enable-cc}

Om du vill aktivera alternativet **[!UICONTROL CC email]** konfigurerar du CC-fältet i [e-postkanalskonfigurationen](../email/email-settings.md).

![](assets/email-config-cc.png)

Du kan ange en extern adress i rätt format, förutom en e-postadress som definierats för en underdomän som delegerats till Adobe. Om du till exempel har delegerat underdomänen *marketing.luma.com* till Adobe tillåts inte adresser som *abc@marketing.luma.com*.

>[!CAUTION]
>
>Du kan bara definiera en e-postadress. Kontrollera att CC-adressen har tillräcklig mottagningskapacitet för att lagra alla e-postmeddelanden som skickas med den aktuella kanalkonfigurationen.
>
>Fler rekommendationer visas i [det här avsnittet](#cc-recommendations-limitations).

Fältet **[!UICONTROL CC email]** accepterar tre typer av värden:

* Ett **hårdkodat värde** som kan vara en fast e-postadress.

* Ett **profilattribut**, t.ex. relationshanterarens e-postadress som är tillgänglig i profilen.

* Ett **kontextuellt attribut** - det här värdet kan **endast användas i API-utlösta kampanjer**. Den hämtas från API-nyttolasten som måste innehålla kontextvariabeln `context.channel.email.ccvalues` med CC-adressvärdet.

  >[!WARNING]
  >
  >När CC anges med en **kontextvariabel** stöds den bara i **API-utlösta kampanjer**. Om du använder den kanalkonfigurationen för en resa eller en åtgärdskampanj skickas e-postmeddelandet endast till den primära mottagaren. Ingen kopia skickas till CC-adressen.

Alla [bilagor](../email/pdf-attachments.md) som ingår i meddelandet skickas till både den primära mottagaren och CC-adressen.

Om CC-värdet är ogiltigt eller saknas vid sändning (t.ex. en tom kontextvariabel) hoppas CC-kopian över. Den primära mottagaren får fortfarande e-postmeddelandet.

Om det finns flera värden för CC-fältet (till exempel om du använder ett profilattribut eller uttryck som matchar flera adresser) används bara det första värdet för att skicka e-postmeddelandet.

## Redigera e-post om CC i befintliga kanalkonfigurationer {#cc-edit}

Om du [redigerar en e-postkonfiguration](channel-surfaces.md#edit-channel-surface) och lägger till eller ändrar CC-fältet kan du bara använda:

* En **hårdkodad** CC-e-postadress, eller
* En **kontextvariabel** (för API-utlöst användning).

>[!CAUTION]
>
>När du redigerar en befintlig e-postkanalskonfiguration kan du inte lägga till nya [profilattribut](../personalization/personalization-build-expressions.md#sources) i fältet **[!UICONTROL CC email]**. Du måste skapa en [ny kanalkonfiguration](channel-surfaces.md#create-channel-surface).

## Rekommendationer och begränsningar {#cc-recommendations-limitations}

* **Tillstånd:** CC-användning räknas in i din berättigade meddelandevolym. Använd bara CC där du behöver synliga CC-mottagare. Kontrollera om det finns licensierade volymer i ditt avtal.

* **Sekretess och efterlevnad:** För att säkerställa din sekretess måste CC-e-post behandlas av ett system som kan lagra säkert personligt identifierbar information (PII) när det är tillämpligt. Eftersom meddelanden kan innehålla känsliga eller privata data, t.ex. PII, måste du se till att CC-adressen är korrekt och skydda åtkomsten till meddelanden.

* **Inkorgshantering:** Inkorgen som används för CC bör hanteras på rätt sätt för utrymme och leverans. Om inkorgen returnerar studsar kanske vissa e-postmeddelanden inte tas emot.

* **Leveranstiming:** Meddelanden kan levereras till e-postadressen för CC före målmottagarna. CC-meddelanden kan också skickas trots att de ursprungliga meddelandena har [studsat](../reports/suppression-list.md#delivery-failures).

* **Rapportering:** Öppnar, klickar och annat engagemang från CC-mottagare ingår i e-postrapporteringsstatistik. Alla öppningar eller klick från CC-mottagare orsakar därför felberäkningar i [rapporter](../reports/report-gs-cja.md).

* **Skräppost:** Markera inte meddelanden som skräppost i CC-inkorgen eftersom det påverkar alla andra e-postmeddelanden som skickas till den här adressen.

* **Leverans:** Använd CC i enlighet med din sändningspraxis och mottagarens förväntningar. Överdriven användning av CC kan påverka leveransen. Följ [Bästa praxis för leveransen](../reports/deliverability.md) och dina avtalsvillkor.

>[!CAUTION]
>
>Klicka inte på länken för att avbryta prenumerationen i de e-postmeddelanden som skickas till CC-adressen eftersom du omedelbart kommer att avbryta prenumerationen på **Till**-mottagaren av e-postmeddelandet.
