---
solution: Journey Optimizer
product: journey optimizer
title: Skicka ett meddelande till prenumeranter
description: Lär dig hur du bygger en resa för att skicka ett meddelande till prenumeranterna på en lista
feature: Journeys, Use Cases, Subscriptions
topic: Content Management
role: User, Developer
level: Intermediate, Experienced
keywords: resa, användningsfall, meddelande, prenumeranter, lista, läsa
exl-id: 2540938f-8ac7-43fa-83ff-fed59f6bc417
version: Journey Orchestration
source-git-commit: 52126b42ff400a355db9c75afde0c86059daf164
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 1%

---

# Skicka ett meddelande till prenumeranterna av en lista {#send-a-message-to-the-subscribers-of-a-list}

Syftet med det här användningsexemplet är att skapa en resa för att skicka ett meddelande till prenumeranterna av en lista.

I det här exemplet används fältgruppen **[!UICONTROL Consent and Preference Details]** från [!DNL Adobe Experience Platform]. Om du vill hitta den här fältgruppen går du till menyn **[!UICONTROL Data Management]** och väljer **[!UICONTROL Schemas]**. På fliken **[!UICONTROL Field groups]** anger du namnet på fältgruppen i sökfältet.

![Den här fältgruppen innehåller prenumerationselementet](assets/consent-and-preference-details-field-group.png)

Så här konfigurerar du den här resan:

1. Skapa en resa som börjar med en **[!UICONTROL Read]**-aktivitet. Läs mer i [Skapa din första resa](journey-gs.md).
1. Lägg till en **[!UICONTROL Email]**-åtgärdsaktivitet på resan. Lär dig hur du [arbetar med kanalåtgärder](journeys-message.md).
1. I avsnittet **[!UICONTROL Email parameters]** i aktivitetsinställningarna för **[!UICONTROL Email]** ersätter du den förvalda e-postadressen (`PersonalEmail.adress`) med e-postadressen till listprenumeranterna:

   1. Klicka på ikonen **[!UICONTROL Enable parameter override]** till höger om fältet **[!UICONTROL Address]** och klicka sedan på ikonen **[!UICONTROL Edit]** .

      ![Resursflöde med Läs målgrupp för prenumerantlista ](assets/message-to-subscribers-uc-1.png)

   1. I uttrycksredigeraren anger du uttrycket för att hämta prenumeranternas e-postadresser. [Läs mer](expression/expressionadvanced.md).

      I det här exemplet visas ett uttryck som innehåller referenser till mappningsfält:

      ```json
      #{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
      ```

      I det här exemplet används följande funktioner:

      | Funktion | Beskrivning | Exempel |
      | --- | --- | --- |
      | `entry` | Avser ett mappningselement enligt det valda namnutrymmet | Se en specifik prenumerationslista |
      | `firstEntryKey` | Hämtar kartans första inmatningsnyckel | Hämta den första e-postadressen till prenumeranter |

      I det här exemplet heter prenumerationslistan `daily-email`. E-postadresser definieras som nycklar i kartan `subscribers` som är länkad till prenumerationslistans karta.

      Läs mer om [referenser till fält](expression/field-references.md) i uttryck.

      ![E-postkonfiguration med anpassat innehåll för prenumeranter](assets/message-to-subscribers-uc-2.png)

   1. Klicka på **[!UICONTROL Add an expression]** i dialogrutan **[!UICONTROL Ok]**.

>[!CAUTION]
>
>Åsidosättning av e-postadresser ska endast användas för särskilda användningsfall. Oftast behöver du inte ändra e-postadressen eftersom det värde som definieras som primär adress i **[!UICONTROL Execution fields]** är den som ska användas. [Läs mer](../configuration/primary-email-addresses.md)
