---
title: Arbeta med sparade uttryck
description: Lär dig hur du arbetar med sparade uttryck i [!DNL Journey Optimizer] bibliotek.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Arbeta med sparade uttryck {#expression-library}

>[!CONTEXTUALHELP]
>id="ajo_perso_library"
>title="Om uttrycksbiblioteket"
>abstract="[!DNL Journey Optimizer] innehåller ett bibliotek där du kan komma åt sparade personaliseringsuttryck som har konfigurerats av administratörsanvändare. "

[!DNL Journey Optimizer] I finns ett bibliotek där du kan komma åt tidigare sparade anpassningsuttryck som har lagts till av Admin-användare.

1. Om du vill komma åt de sparade uttrycken klickar du på **[!UICONTROL Library]** i den vänstra rutan. I listan visas alla uttryck som har sparats av Admin-användare (se [Spara uttryck i biblioteket](#save-expressions)).

   >[!NOTE]
   >
   >Du kan använda infoknappen för att få mer information om innehållet i ett sparat uttryck. Om du har behörighet att hantera biblioteksobjekt visas informationsknappen på ellipsmenyn.

   ![](assets/library-list.png)

1. Klicka på + för att infoga uttrycket i redigeraren. Sedan kan ni anpassa och validera ert personaliseringsinnehåll som vanligt. [Läs mer](../personalization/personalization-build-expressions.md)

   ![](assets/library-add.png)

## Spara ett uttryck i biblioteket {#save-expressions}

[!DNL Journey Optimizer] gör att administratörsanvändare kan spara personaliseringsuttryck i biblioteket. Dessa uttryck kommer sedan att vara tillgängliga för alla användare för att skapa innehåll för personalisering.

Så här sparar du ett uttryck i biblioteket:

1. Bygg uttrycket i redigeringsgränssnittet och klicka sedan på **[!UICONTROL Add to library]**.

   >[!NOTE]
   >
   >Om knappen inte visas kontrollerar du i Admin Console att du har de behörigheter som krävs (se [Behörighetsnivåer](../administration/high-low-permissions.md)).

   ![](assets/library-save.png)

1. I den högra rutan anger du en rubrik och en beskrivning för uttrycket så att användarna enklare kan hitta det. Klicka sedan på **[!UICONTROL Add]**.

   ![](assets/add-expression.png)

1. Uttrycket läggs till i biblioteket. Användarna kommer nu att kunna använda den för att bygga sitt personaliseringsinnehåll.


>[!NOTE]
>
>* Du sparar upp till 40 uttryck i biblioteket.
>
>* Uttryck får inte överskrida 200 kB.
>
>* Sparade uttryck sorteras efter skapandedatum: nyligen tillagda uttryck visas först i listan.



Om du vill redigera ett befintligt uttryck lägger du till det i redigeraren och ändrar det efter behov. Klicka **[!UICONTROL Add to library]** för att validera syntaxen och spara uttrycket.

Om du vill ta bort ett uttryck klickar du på ellipsknappen och sedan på **[!UICONTROL Delete]**.
