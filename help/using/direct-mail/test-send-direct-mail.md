---
title: Testa och skicka ett direktmejl
description: Lär dig hur du testar och skickar direktreklam i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keyword: direct, mail, configuration, direct-mail, provider
exl-id: 69a19190-d2e2-4858-a1df-ffd008226e2b
source-git-commit: c4ab97999d000d969f6f09f4d84be017d1288f94
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 1%

---

# Testa och skicka ett direktmejl {#direct-mail-test-send}

## Förhandsgranska extraheringsfilen {#preview-dm}

När innehållet i extraheringsfilen har definierats kan du använda testprofiler för att förhandsgranska det. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

1. På konfigurationsskärmen för extraheringsfilinnehåll klickar du på **[!UICONTROL Simulate content]**.

   ![](assets/direct-mail-simulate-button.png){width="800" align="center"}

1. Klicka **[!UICONTROL Manage test profiles]** för att lägga till en testprofil.

1. Hitta din testprofil med **[!UICONTROL Identity namespace]** och **[!UICONTROL Identity value]** fält. Klicka sedan på **[!UICONTROL Add profile]**.

   ![](assets/direct-mail-test-profile.png){width="800" align="center"}

1. När du har valt din testprofil kan du stänga **[!UICONTROL Add test profile]** -fönstret.

1. Från **Förhandsgranska och testa** testprofildata läggs till i extraheringsfilens innehåll så att du kan förhandsgranska hur filen kommer att återges.

   ![](assets/direct-mail-simulate.png){width="800" align="center"}

När filinnehållet är klart att skickas stänger du simuleringsskärmen och klickar sedan på **[!UICONTROL Review to activate]** -knappen.

## Validera och aktivera direktreklamkampanjen {#dm-validate}

Kontrollera att kampanjen och extraheringsfilen är korrekt konfigurerade innan du aktiverar kampanjen för direktreklam. Om du vill göra det kontrollerar du varningarna i den övre delen av redigeraren. Vissa av dem är enkla varningar, men andra kan hindra dig från att skicka meddelandet. Två typer av varningar kan inträffa: varningar och fel.

* **Varningar** hänvisa till rekommendationer och bästa praxis. Ett varningsmeddelande visas till exempel om SMS-meddelandet är tomt.

* **Fel** hindra er från att publicera kampanjen, så länge de inte är lösta. Ett felmeddelande varnar dig till exempel när ämnesraden saknas.

![](assets/direct-mail-review.png){width="800" align="center"}

Klicka på knappen **[!UICONTROL Activate]** -knappen. När kampanjen startar genereras extraheringsfilen automatiskt och exporteras till den server som anges i [konfiguration för filroutning](../direct-mail/direct-mail-configuration.md).

När ni har skickat det kan ni mäta effekten av er direktreklamkampanj i Campaign-rapporterna. Mer information om rapportering finns i det här avsnittet.

## Hantera samtycke för direktreklam {#dm-consent-management}

I [!DNL Journey Optimizer], samtycke hanteras av Experience Platform [Samtyckesschema](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html){target="_blank"}. Som standard är värdet för medgivandefältet tomt och behandlas som samtycke för att ta emot dina meddelanden.

Om en profil har valt att inte ta emot direktreklam anger du värdet för `consents.marketing.postalMail.val` kommer att `n` och motsvarande profil kommer inte att ingå i efterföljande leveranser.

Om du vill aktivera profilattributet igen måste du ändra tillbaka det till `consents.marketing.postalMail.val` : `y`.

Om du vill hantera en profils attribut går du till Experience Platform och öppnar profilen genom att markera ett identitetsnamnutrymme och ett motsvarande identitetsvärde. Läs mer i [Experience Platform dokumentation](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target="_blank"}.

Läs mer om hur du hanterar avanmälan i Journey Optimizer i [det här avsnittet](../privacy/opt-out.md).
