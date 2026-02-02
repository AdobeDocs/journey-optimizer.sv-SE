---
title: Använd beslutspolicyer i meddelanden
description: Lär dig hur du använder beslutsprinciper i dina meddelanden.
feature: Decisioning
topic: Integrations
role: User
level: Experienced
mini-toc-levels: 1
version: Journey Orchestration
source-git-commit: 2dfc9c2db5af1b9b74f7405a68e85563f633a54f
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 0%

---

# Använd beslutspolicyer i meddelanden {#create-decision}

När du har lagt till en beslutsprincip i innehållet kan du använda attribut från returnerade beslutsobjekt för personalisering. Om du vill göra det måste du först infoga beslutsprincipkoden i ditt innehåll.

>[!CAUTION]
>
>Beslutsprinciper är tillgängliga för alla kunder för kanalerna **Kodbaserad upplevelse**, **SMS** och **push-meddelanden**.
>
>Beslut om e-postkanalen finns i Begränsad tillgänglighet. Kontakta din Adobe-representant för att få åtkomst. Läs mer om [tillgänglighetsetiketter](../rn/releases.md#availability-labels).

## Infoga koden för beslutspolicy {#insert}

>[!BEGINTABS]

>[!TAB Kodbaserad upplevelse]

1. Redigera din kodbaserade upplevelse och navigera till **[!UICONTROL Decision policy]**.

2. Välj **[!UICONTROL Insert policy]** om du vill lägga till beslutsprincipkoden.

   ![](assets/decision-code-based-add-decision.png)

>[!NOTE]
>
>Om din beslutspolicy innehåller beslutsposter, inklusive fragment, kan du utnyttja dessa fragment i beslutspolicykoden för kodbaserade upplevelser. [Lär dig använda fragment](../experience-decisioning/fragments-decision-policies.md)

>[!TAB E-post]

1. Öppna **Personalization Editor** och gå till **[!UICONTROL Decision policies]**.

2. Välj **[!UICONTROL Insert syntax]** om du vill lägga till koden för din beslutsprincip.

   ![](assets/decision-policy-add.png)

   >[!NOTE]
   >
   >Om infogningsalternativet inte visas kanske en beslutsprincip redan har konfigurerats för den överordnade komponenten.

3. Om ingen placering ännu har tilldelats komponenten väljer du en i listan och klickar på **[!UICONTROL Assign]**.

   ![](assets/decision-policy-placement.png)

>[!TAB SMS]

1. Öppna **Personalization Editor** och gå till **[!UICONTROL Decision policies]**.

2. Välj **[!UICONTROL Insert syntax]** om du vill lägga till koden för din beslutsprincip.

   ![](assets/decision-policy-add-sms-insert-syntax.png)

>[!TAB Tryck]

1. Öppna **Personalization Editor** och gå till **[!UICONTROL Decision policies]**.

2. Välj **[!UICONTROL Insert syntax]** om du vill lägga till koden för din beslutsprincip.

   ![](assets/decision-policy-add-push-insert-syntax.png)

>[!IMPORTANT]
>
>Experience Decision med push-meddelanden kräver en specifik version av Mobile SDK. Innan du implementerar den här funktionen bör du kontrollera [versionsinformationen](https://developer.adobe.com/client-sdks/home/release-notes){target="_blank"} för att identifiera den version som krävs och kontrollera att du har uppgraderat därefter. Du kan även visa alla tillgängliga SDK-versioner för din plattform i [det här avsnittet](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"}.

>[!ENDTABS]

Koden för beslutspolicyn läggs till. Du kan nu använda attribut från de returnerade beslutsobjekten för att anpassa ditt innehåll.

>[!NOTE]
>
>För kodbaserad upplevelse och e-postkanaler upprepar du den här sekvensen en gång per beslutsobjekt som du vill returnera. Om du till exempel väljer att returnera 2 objekt när [du skapar beslutet](create-decision-policy.md), upprepar du sekvensen två gånger. För SMS- och push-kanaler kan bara ett beslutsobjekt returneras.

## Anpassa med attribut för beslutsobjekt {#attributes}

När du har lagt till koden för en beslutspolicy i ditt innehåll blir alla attribut från de returnerade beslutsposterna tillgängliga för personalisering. [Lär dig hur du arbetar med personalisering](../personalization/personalize.md).

Attribut lagras i [katalogschemat](catalogs.md) för erbjudanden. De visas i följande mappar från personaliseringsredigeraren:
* **Anpassade attribut**: `_\<imsOrg\>`-mapp
* **Standardattribut**: `_experience` mapp

Attribut för beslutsobjekt och sammanhangsbaserade attribut stöds inte som standard i [!DNL Journey Optimizer]-fragment. Du kan emellertid använda globala variabler i stället, som beskrivs nedan.

![](assets/decision-code-based-decision-attributes.png)

Om du vill lägga till ett attribut klickar du på ikonen **`+`** bredvid attributet. Du kan lägga till så många attribut som behövs. Du kan även inkludera andra personaliseringsattribut, t.ex. profildata.

* För kanalerna **Email** och **Code-based** kapslar du in attributen i `#each`-slingan med hakparenteser `[ ]` och lägger till ett kommatecken före den avslutande `/each` -taggen.

  +++Se exempel

  ![](assets/decision-code-based-wrap-code.png)

  +++

* För kanalerna **SMS** och **Push** måste du infoga attribut efter syntaxkoden för beslutsprincipen. Den här syntaxen ska alltid hållas på rad 1.

  +++Se exempel

  ![](assets/decision-added-sms.png)

  +++

  >[!NOTE]
  >Om du infogar ett bildresursattribut i SMS- eller push-innehåll (till exempel i titeln eller brödtexten) visas attributvärdet som en URL. Själva bilden återges inte i dessa fält.

* Om du vill aktivera spårning av beslutsobjekt lägger du till attributet `trackingToken`: `trackingToken: {{item._experience.decisioning.decisionitem.trackingToken}}`

## Förhandsgranska och testa ditt innehåll

När du har skapat ditt innehåll kan du förhandsgranska och testa det innan du aktiverar din resa eller kampanj. Beslutsobjekt återges baserat på valda profiler i simuleringsgränssnittet. [Lär dig hur du förhandsgranskar och testar innehåll](../content-management/preview-test.md).

## Nästa steg {#final-steps}

När innehållet är klart kan du granska och publicera kampanjen eller resan:

* [Publicera en resa](../building-journeys/publish-journey.md)
* [Granska och aktivera en kampanj](../campaigns/review-activate-campaign.md)

När utvecklaren gör ett API- eller SDK-anrop för att hämta innehåll för den yta som definieras i kanalkonfigurationen, kommer ändringarna att tillämpas på webbsidan eller appen för kodbaserade upplevelser.

>[!NOTE]
>
>Du kan för närvarande inte simulera beslutsbaserat innehåll för [kodbaserade upplevelser](../code-based/create-code-based.md)-kampanjer eller resor. Det finns en tillfällig lösning [här](../code-based/code-based-decisioning-implementations.md).

## Använda rapportpaneler

För att se hur era beslut fungerar kan ni visa färdiga beslutsvärden i kampanjen eller reserapporten, eller skapa anpassade Customer Journey Analytics-kontrollpaneler för att mäta resultat och få insikter om hur era beslutspolicyer och erbjudanden levereras och engageras med. [Läs mer om beslutsrapportering](cja-reporting.md).

![](../reports/assets/cja-decisioning-item-performance.png)
