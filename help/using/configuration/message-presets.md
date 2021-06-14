---
title: Skapa meddelandeförinställningar
description: Lär dig hur du konfigurerar och övervakar meddelandeförinställningar
feature: Applikationsinställningar
topic: Administrering
role: Administrator
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 1%

---


# Skapa meddelandeförinställningar

Med [!DNL Journey Optimizer] kan du konfigurera meddelandeförinställningar som definierar alla tekniska parametrar som krävs för e-post och push-meddelanden: e-posttyp, avsändarens e-postadress och namn, mobilappar med mera.

>[!CAUTION]
>
> Konfigurationen av meddelandeförinställningar är begränsad till Reseadministratörer. [Läs mer](../administration/ootb-product-profiles.md#journey-administrator)



När meddelandeförinställningarna har konfigurerats kan du välja dem när du skapar meddelanden från **[!UICONTROL Presets]**-listan.

## Skapa en meddelandeförinställning {#create-message-preset}

Så här skapar du en meddelandeförinställning:

1. Gå till menyn **[!UICONTROL Channels]** / **[!UICONTROL Message presets]** och klicka sedan på **[!UICONTROL Create Message preset]**.

   ![](../assets/preset-create.png)


1. Ange ett namn och en beskrivning (valfritt) för förinställningen och välj sedan de kanaler som ska konfigureras.

   ![](../assets/preset-general.png)


   >[!NOTE]
   >
   > Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-`.

1. Konfigurera inställningarna för **e-post**.

   ![](../assets/preset-email.png)

   * Välj den typ av meddelande som ska skickas med förinställningen: **Transaktionell** eller **Markering**

      >[!CAUTION]
      >
      > **Transaktionsmeddelanden** kan skickas till profiler som avbeställt marknadskommunikation. Dessa meddelanden kan bara skickas i särskilda sammanhang, t.ex. lösenordsåterställning, orderstatus eller leveransmeddelande.

   * Välj den underdomän som ska användas för att skicka e-postmeddelanden. [Läs mer](about-subdomain-delegation.md)
   * Välj den IP-pool som ska associeras med förinställningen. [Läs mer](ip-pools.md)
   * Ange rubrikparametrarna för e-postmeddelanden som skickas med förinställningen.

      >[!NOTE]
      >
      > * Namn måste börja med en bokstav (A-Z). Det får bara innehålla alfanumeriska tecken. Du kan också använda understreck `_`, punkt`.` och bindestreck `-`.
         > 
         > 
      * Med undantag för **Svara på (vidarebefordrad e-post)** måste e-postadressdomänen använda den valda underdomänen.



1. Konfigurera inställningar för **push-meddelanden**.

   ![](../assets/preset-push.png)

   * Välj minst en plattform: **iOS** och/eller **Android**

   * Välj de mobilprogram som ska användas för varje plattform.

      Mer information om hur du konfigurerar miljön för att skicka push-meddelanden finns i [det här avsnittet](../push-gs.md).

1. När alla parametrar har konfigurerats klickar du på **[!UICONTROL Submit]** för att bekräfta. Du kan också spara meddelandeförinställningen som utkast och återuppta konfigurationen senare.

   ![](../assets/preset-submit.png)

1. När meddelandeförinställningen har skapats visas den i listan med statusen **[!UICONTROL Processing]**.

   Under det här steget kommer flera kontroller att utföras för att verifiera att den har konfigurerats korrekt. Bearbetningstiden är ungefär **48h-72h** och kan ta upp till **7-10 dagar**.

   Dessa kontroller omfattar leveranstester som utförs av Adobe-avdelningen:


   * SPF-validering
   * DKIM-validering
   * MX-postvalidering
   * Kontrollera IP-adresser som blocklist
   * Kontroll av värddator
   * Verifiering av IP-pool
   * A/PTR-post, t/m/res-underdomänverifiering


1. När kontrollerna är slutförda får meddelandeförinställningen statusen **[!UICONTROL Active]**. Den är klar att användas för att leverera meddelanden.

   <!-- later on, users will be notified in Pulse -->

   ![](../assets/preset-active.png)

## Övervaka meddelandeförinställningar

Alla meddelandeförinställningar visas på menyn **[!UICONTROL Channels]** / **[!UICONTROL Message presets]**. Det finns filter som hjälper dig att bläddra igenom listan (kanaltyp, användare, status).

![](../assets/preset-filters.png)

Meddelandeförinställningar kan ha följande status:

* **[!UICONTROL Draft]**: Meddelandeförinställningen har sparats som ett utkast och har inte skickats ännu. Öppna den för att återuppta konfigurationen.
* **[!UICONTROL Processing]**: Meddelandeförinställningen har skickats och genomgår flera verifieringssteg.
* **[!UICONTROL Active]**: Meddelandeförinställningen har verifierats och kan väljas för att skapa meddelanden.
* **[!UICONTROL Failed]**: En eller flera kontroller misslyckades under verifieringen av meddelandeförinställningen.
* **[!UICONTROL De-activated]**: Meddelandeförinställningen inaktiveras. Det kan inte användas för att skapa nya meddelanden.

## Redigera meddelandeförinställningar

Om du vill redigera en meddelandeförinställning måste du först avaktivera den så att den inte är tillgänglig för att skapa nya meddelanden (publicerade meddelanden som använder den här förinställningen påverkas inte och fortsätter att fungera). Du måste sedan duplicera meddelandeförinställningen för att skapa en ny version som du använder för att skapa nya meddelanden:

1. Öppna listan med meddelandeförinställningar och inaktivera sedan den meddelandeförinställning som du vill redigera.

   ![](../assets/preset-deactivate.png)

1. Duplicera den inaktiverade meddelandeförinställningen. En kopia med statusen **[!UICONTROL Draft]** läggs automatiskt till i listan.

   ![](../assets/preset-duplicated.png)

1. Öppna den duplicerade meddelandeförinställningen, ändra den efter dina behov och skicka sedan ändringarna. Meddelandeförinställningen går igenom samma valideringscykel som under [skapandesteget](#create-message-preset).

1. När den har validerats får den statusen **[!UICONTROL Active]** och är klar att användas för att skapa nya meddelanden.

   >[!NOTE]
   >
   >Det går inte att ta bort förinställningar för inaktiverade meddelanden för att undvika problem i resor som uppstår när du använder dessa förinställningar för att skicka meddelanden.

