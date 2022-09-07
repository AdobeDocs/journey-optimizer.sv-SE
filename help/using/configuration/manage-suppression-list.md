---
title: Hantera listan över inaktiveringar
description: Lär dig hur du får åtkomst till och hanterar Journey Optimizer-listan över inaktiveringar
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 430a2cd4-781d-4d37-a75d-405f5ed82377
source-git-commit: c530905eacbdf6161f6449d7a0b39c8afaf3a321
workflow-type: tm+mt
source-wordcount: '1107'
ht-degree: 1%

---

# Hantera listan över inaktiveringar {#manage-suppression-list}

Med [!DNL Journey Optimizer]kan du övervaka alla e-postadresser som automatiskt utesluts från att skickas under en resa, till exempel:

* Adresser som är ogiltiga (hårda studsar).
* Adresserar som konsekvent studsar utan extra kostnad och kan påverka e-postens anseende negativt om du fortsätter att inkludera dem i dina leveranser.
* Mottagare som skickar skräppost av något slag mot ett av dina e-postmeddelanden.

Sådana e-postadresser samlas automatiskt in i Journey Optimizer **utelämningslista**. Läs mer om begrepp och användning i listan över inaktiveringar i [det här avsnittet](../reports/suppression-list.md).

Du kan också [**manuellt** lägga till en adress eller en domän](#add-addresses-and-domains) till listan över undertryckningar.

>[!NOTE]
>
>Det tar mellan 0 och 60 minuter i [!DNL Journey Optimizer] för att ta hänsyn till de utelämnade adresserna i utgående e-postmeddelanden.

## Åtkomst till listan över inaktiveringar {#access-suppression-list}

Om du vill få tillgång till en detaljerad lista över e-postadresser som inte ingår går du till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** och markera **[!UICONTROL Suppression list]**.

>[!CAUTION]
>
>Behörigheterna att visa, exportera och hantera undertryckningslistan är begränsade till [Reseadministratörer](../administration/ootb-product-profiles.md#journey-administrator). Läs mer om hantering [!DNL Journey Optimizer] användares åtkomsträttigheter i [det här avsnittet](../administration/permissions-overview.md).

![](assets/suppression-list-access.png)

Det finns filter som hjälper dig att bläddra igenom listan.

![](assets/suppression-list-filters.png)

Du kan filtrera på **[!UICONTROL Suppression category]**, **[!UICONTROL Address type]**, eller **[!UICONTROL Reason]**. Välj alternativ för varje kriterium. När du har valt det här alternativet kan du rensa alla filter eller alla filter som visas ovanpå listan.

![](assets/suppression-list-filtering-example.png)

Om du av misstag lägger till en e-postadress eller en domän manuellt, visas **[!UICONTROL Delete]** kan du ta bort inmatningen.

>[!CAUTION]
>
>Använd aldrig **[!UICONTROL Delete]** om du vill ta bort inaktiverade e-postadresser eller domäner.

![](assets/suppression-list-delete.png)

Om du tar bort en e-postadress eller en domän från listan över inaktiveringar kommer du att börja leverera till den här adressen eller domänen igen. Detta kan få allvarliga konsekvenser för din leveransförmåga och IP-anseende, vilket i slutänden kan leda till att din IP-adress eller sändande domän blockeras. Läs mer om hur viktigt det är att undertryckningslistan finns i [det här avsnittet](../reports/suppression-list.md).

>[!NOTE]
>
>Fortsätt med extra omsorg när du funderar på att ta bort en e-postadress eller domän. Om du är osäker kan du kontakta en expert på slutprodukter.

Från **[!UICONTROL Suppression list]** kan du även redigera undertryckningsregler. [Läs mer](retries.md)

Om du vill exportera listan över inaktiveringar som en CSV-fil väljer du **[!UICONTROL Download CSV]** -knappen.

![](assets/suppression-list-download-csv.png)

## Undertryckningskategorier och orsaker {#suppression-categories-and-reasons}

När ett meddelande inte kan levereras till en e-postadress, [!DNL Journey Optimizer] avgör varför leveransen misslyckades och associerar den med en **[!UICONTROL Suppression category]**.

Undertryckningskategorierna är följande:

* **Hård**: E-postadressen skickas omedelbart till listan över inaktiveringar.

   >[!NOTE]
   >
   >När felet beror på ett skräppostklagomål hamnar det också i **Hård** kategori. E-postadressen till mottagaren som skickade klagomålet skickas omedelbart till suppressionslistan.

* **Mjuk**: Mjuka fel skickar en adress till listan när felräknaren når gränsvärdet. [Läs mer om återförsök](retries.md)

* **Manuell**: Du kan också lägga till en e-postadress eller en domän manuellt i listan över inaktiveringar. [Läs mer](#add-addresses-and-domains)

>[!NOTE]
>
>Läs mer om mjuka studsar och hårda studsar i [Leveransfel](../reports/suppression-list.md#delivery-failures) -avsnitt.

För varje e-postadress som visas kan du även kontrollera **[!UICONTROL Type]** (e-post eller domän), **[!UICONTROL Reason]** för att utesluta den, vem som lagt till den och datumet/tiden som den lades till i listan över inaktiveringar.

![](assets/suppression-list.png)

Möjliga orsaker till leveransfel är:

| Orsak | Beskrivning | Undertryckningskategori |
| --- | --- | --- |
| **[!UICONTROL Invalid Recipient]** | Mottagaren är ogiltig eller finns inte. | Hård |
| **[!UICONTROL Soft Bounce]** | Meddelandet studsade på ett annat sätt än de mjuka fel som anges i den här tabellen, till exempel när det skickas över den tillåtna hastighet som rekommenderas av en Internet-leverantör. | Mjuk |
| **[!UICONTROL DNS Failure]** | Meddelandet studsade på grund av ett DNS-fel. | Mjuk |
| **[!UICONTROL Mailbox Full]** | Meddelandet studsade eftersom mottagarens postlåda är full och inte kan ta emot fler meddelanden. | Mjuk |
| **[!UICONTROL Relaying Denied]** | Meddelandet blockerades av mottagaren eftersom återutläggning inte tillåts. | Mjuk |
| **[!UICONTROL Challenge-Response]** | Meddelandet är en frågesvarsundersökning. | Mjuk |
| **[!UICONTROL Spam Complaint]** | Meddelandet blockerades eftersom mottagaren har markerat det som skräppost. | Hård |

>[!NOTE]
>
>Användare som avbeställer prenumerationen får inte e-post från [!DNL Journey Optimizer]Därför kan deras e-postadresser inte skickas till listan över inaktiveringar. Deras val hanteras på Experience Platform-nivå. [Läs mer om att avanmäla dig](../messages/consent.md)

## Lägga till adresser och domäner manuellt {#add-addresses-and-domains}

>[!CONTEXTUALHELP]
>id="ajo_admin_suppression_list"
>title="Lägg till e-postmeddelanden eller domäner i listan över inaktiveringar"
>abstract="Du kan fylla i listan över Journey Optimizer-undertryckningar manuellt om du vill utesluta vissa e-postadresser och/eller domäner från sändningen."

När ett meddelande inte kan levereras till en e-postadress läggs adressen automatiskt till i listan över undertryckningar baserat på den definierade undertryckningsregeln eller avhoppsantalet.

Du kan även fylla i [!DNL Journey Optimizer] utelämningslista om du vill exkludera specifika e-postadresser och/eller domäner från din sändning.

Du kan lägga till e-postadresser eller domäner [en åt gången](#add-one-address-or-domain), eller [i gruppläge](#upload-csv-file) via en CSV-filöverföring.

Om du vill göra det väljer du **[!UICONTROL Add email or domain]** och därefter någon av metoderna nedan.

![](assets/suppression-list-add-email.png)

### Lägg till en adress eller domän {#add-one-address-or-domain}

>[!CONTEXTUALHELP]
>id="ajo_admin_suppression_list_address"
>title="Lägg till ett objekt i listan över inaktiveringar"
>abstract="Du kan fylla i undertryckningslistan genom att lägga till e-postadresser och/eller domäner en i taget."

1. Välj **[!UICONTROL One by one]** alternativ.

   ![](assets/suppression-list-add-email-address.png)

1. Välj adresstyp: **[!UICONTROL Email address]** eller **[!UICONTROL Domain address]**.

1. Ange den e-postadress eller domän som du vill utesluta från sändningen.

   >[!NOTE]
   >
   >Kontrollera att du anger en giltig e-postadress (till exempel abc@company.com) eller domän (till exempel abc.company.com).

1. Ange en orsak om det behövs.

   >[!NOTE]
   >
   >Alla ASCII-tecken mellan 32 och 126 tillåts i **[!UICONTROL Reason]** fält. Den fullständiga listan finns på [den här sidan](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target=&quot;_blank&quot;} till exempel.

1. Klicka på **[!UICONTROL Submit]**.

### Överföra en CSV-fil {#upload-csv-file}

>[!CONTEXTUALHELP]
>id="ajo_admin_suppression_list_csv"
>title="Överför CSV för att lägga till objekt i undertryckningslistan"
>abstract="Du kan fylla i undertryckningslistan genom att överföra en CSV-fil som är ifylld med de e-postadresser/domäner som du vill utesluta."

1. Välj **[!UICONTROL Upload CSV]** alternativ.

   ![](assets/suppression-list-upload-csv.png)

1. Ladda ned CSV-mallen som ska användas, som innehåller kolumnerna och formatet nedan:

   ```
   TYPE,VALUE,COMMENT
   EMAIL,abc@somedomain.com,Comment
   DOMAIN,somedomain.com,Comment
   ```
   >[!NOTE]
   >
   >Alla ASCII-tecken mellan 32 och 126 tillåts i **Kommentar** kolumn. Den fullständiga listan finns på [den här sidan](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target=&quot;_blank&quot;} till exempel.

   Du kan även hämta den här mallen från **[!UICONTROL Suppression list]** huvudvyn.

   >[!CAUTION]
   >
   >Ändra inte namnen på kolumnerna i CSV-mallen.
   >
   >Filstorleken får inte överstiga 1 MB.

1. Fyll i CSV-mallen med de e-postadresser och/eller domäner som du vill lägga till i listan över inaktiveringar.

1. När du är klar drar och släpper du CSV-filen och klickar sedan på **[!UICONTROL Submit]**.

   ![](assets/suppression-list-upload-csv-submit.png)

>[!NOTE]
>
>När överföringen är klar kontrollerar du att den lyckades genom att kontrollera dess status från gränssnittet. [Lär dig mer](#recent-uploads)

### Kontrollera status för senaste överföringar {#recent-uploads}

Du kan kontrollera listan med de senaste CSV-filerna som du har överfört.

Om du vill göra det går du till **[!UICONTROL Suppression list]** visa klickar du på **[!UICONTROL Recent uploads]** -knappen.

![](assets/suppression-list-recent-uploads-button.png)

De senaste överföringarna du skickade och deras motsvarande status visas.

Om en felrapport är kopplad till en fil kan du hämta den för att kontrollera de fel som påträffas.

![](assets/suppression-list-recent-uploads-error.png)

Nedan visas ett exempel på den typ av poster som du kan hitta i felrapporten:

```
type,value,comments,failureReason
Email,examplemail.com,MANUAL,Invalid format for value: examplemail.com
Email,examplemail,MANUAL,Invalid format for value: examplemail
Email,example@mail,MANUAL,Invalid format for value: example@mail
Domain,example,MANUAL,Invalid format for value: example
Domain,example.!com,MANUAL,Invalid format for value: example.!com
Domain,!examplecom,MANUAL,Invalid format for value: !examplecom
```
