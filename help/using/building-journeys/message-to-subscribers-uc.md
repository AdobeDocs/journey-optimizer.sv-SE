---
title: Skicka ett meddelande till prenumeranter
description: Lär dig hur du bygger en resa för att skicka ett meddelande till prenumeranterna på en lista
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 2540938f-8ac7-43fa-83ff-fed59f6bc417
source-git-commit: dee8dbac067dac851af02d87a3dece1ba2b29376
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 3%

---

# Användningsfall: skicka ett meddelande till prenumeranterna i en lista{#send-a-message-to-the-subscribers-of-a-list}

Syftet med det här användningsexemplet är att skapa en resa för att skicka ett meddelande till prenumeranterna av en lista.

I det här exemplet **[!UICONTROL Consent and Preference Details]** fältgrupp från [!DNL Adobe Experience Platform] används. Om du vill hitta den här fältgruppen går du till **[!UICONTROL Data Management]** meny, välja **[!UICONTROL Schemas]**. På **[!UICONTROL Field groups]** anger du namnet på fältgruppen i sökfältet.

![Den här fältgruppen innehåller prenumerationselementet](assets/consent-and-preference-details-field-group.png)

Så här konfigurerar du den här resan:

1. Skapa en resa som börjar med en **[!UICONTROL Read]** aktivitet. [Läs mer](journey-gs.md).
1. Lägg till en **[!UICONTROL Message]** aktivitet, med e-post, på resan. [Läs mer](journeys-message.md).
1. I **[!UICONTROL Email parameters]** i **[!UICONTROL Message]** aktivitetsinställningar, ersätt standardadress för e-post (`PersonalEmail.adress`) med e-postadressen till listprenumeranterna:

   1. Klicka på **[!UICONTROL Enable parameter override]** ikonen till höger om **[!UICONTROL Address]** och klicka sedan på **[!UICONTROL Edit]** ikon.

      ![](assets/message-to-subscribers-uc-1.png)

      Om du vill kunna ändra e-postadressen måste du ha publicerat meddelandet tidigare.

   1. I uttrycksredigeraren anger du uttrycket för att hämta prenumeranternas e-postadresser. [Läs mer](expression/expressionadvanced.md).

      I det här exemplet visas ett uttryck som innehåller referenser till mappningsfält:

      ```json
      #{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
      ```

      I det här exemplet används följande funktioner:

      |  -funktion | Beskrivning | Exempel |
      | --- | --- | --- |
      | `entry` | Se ett mappningselement enligt det valda namnutrymmet | Se en specifik prenumerationslista |
      | `firstEntryKey` | Hämta den första startnyckeln för en karta | Hämta den första e-postadressen till prenumeranter |

      I det här exemplet heter prenumerationslistan `daily-email`. E-postadresser definieras som nycklar i `subscribers` karta, som är länkad till prenumerationslistan.

      Läs mer om [referenser till fält](expression/field-references.md) i uttryck.

      ![](assets/message-to-subscribers-uc-2.png)

   1. I **[!UICONTROL Add an expression]** klickar du på **[!UICONTROL Ok]**.

   ![](assets/message-to-subscribers-uc-3.png)

1. Avsluta resan med en **[!UICONTROL End]** aktivitet.
