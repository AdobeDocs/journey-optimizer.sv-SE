---
solution: Journey Optimizer
product: journey optimizer
title: Lägga till kontextuella attribut i publicerade fragment
description: Lär dig hur du lägger till kontextuella attribut i publicerade fragment (begränsad tillgänglighet)
feature: Fragments
topic: Content Management
role: User
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: 4162403bedc1632ed28db122e2ec16e3c00a2630
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---

# Lägga till kontextuella attribut i publicerade fragment {#adding-contextual-attributes}

>[!AVAILABILITY]
>
>Den här funktionen är bara tillgänglig för utvalda kunder och innebär betydande risker. Kontrollera med din Adobe-representant att den här funktionen är aktiverad för din organisation.

Som standard stöds inte tillägg av nya [anpassningsattribut](../personalization/personalization-build-expressions.md) till ett publicerat fragment. När ett fragment har publicerats låses profiluppsättningen eller kontextuella attribut för alla kampanjer och resor.

Men för utvalda kunder går det bara att lägga till **kontextattribut** i publicerade fragment.

>[!WARNING]
>
>När du lägger till personaliseringsattribut i ett publicerat fragment är valideringsprocessen mindre strikt och fel kanske inte identifieras. Detta kan orsaka oavsiktliga genombrott på resorna och i kampanjer som använder det fragmentet i stor skala.

## Skyddsritningar och begränsningar {#limitations}

* Se till att alla resor och kampanjer som för närvarande använder fragmentet kan hantera de nya kontextuella attributen.
* Det går inte att lägga till profilattribut i publicerade fragment. Endast kontextuella attribut stöds.
* Sammanhangsberoende attribut måste anges manuellt i kodredigeraren. De kan inte väljas i redigeringsgränssnittet för anpassning.
* När du lägger till anpassade attribut till live-fragment avspäns valideringarna, vilket innebär att fel kanske inte kan identifieras och att det kan orsaka oönskade skador i stor skala.
* När de publicerats kommer eventuella fel omedelbart att påverka all kommunikation som använder det fragmentet.

## Lägg till kontextuella attribut {#add-contextual-attributes}

Följ stegen nedan om du vill lägga till sammanhangsberoende attribut i ett publicerat fragment.

>[!IMPORTANT]
>
>Fortsätt bara om ni är fullt medvetna om påverkan på resor och kampanjer som refererar till fragmentet. [Läs mer](#limitations)

1. Navigera till **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]**.

1. Markera det publicerade fragmentet och klicka på **[!UICONTROL Modify]** för att skapa ett utkast.

   ![](assets/fragment-live-modify.png){width="70%" align="left"}

1. Klicka på **[!UICONTROL Edit]** för att öppna fragmentinnehållsredigeraren.

1. Växla till **[!UICONTROL Code editor]** eller **[!UICONTROL Advanced mode]** i personaliseringsredigeraren.

1. Skriv eller kopiera och klistra in sammanhangsberoende attribut manuellt med syntaxen:

   ```
   {{context.attribute_name}}
   ```

   Exempel på ett `promotionCode`-attribut:

   ```
   {{context.promotionCode}}
   ```

   >[!CAUTION]
   >
   >Dubbelkontrollera om attributsökvägen är korrekt. Fel upptäcks kanske inte och kan störa kommunikationen i stor omfattning.

1. Spara ändringarna.

1. När du har bekräftat klickar du på **[!UICONTROL Publish]** för att aktivera ändringarna.

>[!NOTE]
>Om du vill undvika oavsiktliga avbrott mellan resor och kampanjer kan du testa kontextuella attributsökvägar i en icke-produktionsmiljö.

## Relaterade ämnen {#related-topics}

* [Hantera fragment](manage-fragments.md)
* [Använd visuella fragment i e-postmeddelanden](../email/use-visual-fragments.md)
* [Använd uttrycksfragment](../personalization/use-expression-fragments.md)
* [API-utlösta kampanjer](../campaigns/api-triggered-campaigns.md)
* [Personalization syntax](../personalization/personalization-syntax.md)

