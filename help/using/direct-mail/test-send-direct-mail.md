---
title: Kontrollera och skicka ett direktutskick
description: Lär dig hur du kontrollerar och skickar direktreklam i Journey Optimizer
feature: Direct Mail, Test Profiles, Preview
topic: Content Management
role: User
level: Beginner
keyword: direct, mail, configuration, direct-mail, provider
exl-id: 69a19190-d2e2-4858-a1df-ffd008226e2b
source-git-commit: 916239c98c982acf9c6f999316e46036d36b2098
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Kontrollera och skicka ett direktutskick {#direct-mail-test-send}

## Förhandsgranska extraheringsfilen {#preview-dm}

När innehållet i extraheringsfilen har definierats kan du använda testprofiler för att förhandsgranska det. Om du har infogat anpassat innehåll kan du kontrollera hur det här innehållet visas i meddelandet med hjälp av testprofildata.

Det gör du genom att klicka på **[!UICONTROL Simulate content]** och sedan lägga till en testprofil för att kontrollera hur extraheringsfilens återgivning använder testprofildata.

![](assets/direct-mail-simulate.png){width="800" align="center"}

Detaljerad information om hur du väljer testprofiler och förhandsgranskar innehåll finns i avsnittet [Innehållshantering](../content-management/preview-test.md).

När filinnehållet är klart att skickas stänger du simuleringsskärmen och klickar sedan på knappen **[!UICONTROL Review to activate]**.

## Validera och aktivera direktreklamkampanjen {#dm-validate}

>[!IMPORTANT]
>
> Om din kampanj omfattas av en policy för godkännande måste du begära godkännande för att kunna skicka din direktreklamkampanj. [Läs mer](../test-approve/gs-approval.md)

Innan du aktiverar kampanjen för direktreklam måste du se till att kampanjen eller resan och extraheringsfilen är korrekt konfigurerade. Om du vill göra det kontrollerar du varningarna i den övre delen av redigeraren. Vissa av dem är enkla varningar, men andra kan hindra dig från att skicka meddelandet. Två typer av varningar kan inträffa: varningar och fel.

* **Varningar** hänvisar till rekommendationer och bästa praxis. Ett varningsmeddelande visas till exempel om SMS-meddelandet är tomt.

* **Fel** hindrar dig från att publicera kampanjen, så länge som de inte har lösts. Ett felmeddelande varnar dig till exempel när ämnesraden saknas.

![](assets/direct-mail-review.png){width="800" align="center"}

När din direktreklamkampanj är klar slutför du konfigurationen av din [resa](../building-journeys/journey-gs.md) eller [kampanj](../campaigns/create-campaign.md) för att skicka den.

>[!NOTE]
>
>Den exporterade filen avslutas som standard med en ny rad. Detta garanterar kompatibilitet med vanliga databehandlingsverktyg.

När du har skickat det kan du mäta effekten av din direktreklamkampanj eller direktreklamresa i rapporterna. Mer information om rapportering av direktreklam finns i följande avsnitt:
* [Rapport om direktreklamkampanj](../reports/campaign-global-report-cja-direct.md)
* [Rapport om direktreklam](../reports/journey-global-report-cja-direct.md)

## Hantera samtycke för direktreklam {#dm-consent-management}

I [!DNL Journey Optimizer] hanteras samtycke av Experience Platform [Consent schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html){target="_blank"}. Som standard är värdet för medgivandefältet tomt och behandlas som samtycke för att ta emot dina meddelanden.

Om en profil har valt att inte ta emot direktreklam, i motsvarande Experience Platform-profilattribut, kommer värdet för `consents.marketing.postalMail.val` att vara `n` och motsvarande profil kommer att uteslutas från efterföljande leveranser.

Om du vill aktivera det igen måste profilattributet ändras tillbaka till `consents.marketing.postalMail.val` : `y`.

Om du vill hantera en profils attribut går du till Experience Platform och öppnar profilen genom att välja ett identitetsnamnutrymme och ett motsvarande identitetsvärde. Läs mer i [Experience Platform-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target="_blank"}.

Läs mer om hur du hanterar avanmälan i Journey Optimizer i [det här avsnittet](../privacy/opt-out.md).
