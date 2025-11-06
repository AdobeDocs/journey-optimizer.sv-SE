---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med fragment
description: Lär dig hur du arbetar med innehållsfragment för att återanvända innehåll i Journey Optimizer kampanjer och resor
feature: Fragments
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 7131a953-baca-4e7c-a8df-97c0bd6ac567
source-git-commit: abd5f388a41cc85c710cdb8c8e51c7fe381714ad
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Kom igång med fragment {#fragments}

>[!CONTEXTUALHELP]
>id="ajo_create_fragment"
>title="Definiera egna fragment"
>abstract="Skapa och hantera fristående fragment för att göra innehållet återanvändbart på flera resor och i flera kampanjer."
>additional-url="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/fragments/create-fragments" text="Skapa fragment"

Ett fragment är en återanvändbar komponent som kan refereras i en eller flera e-postmeddelanden över [!DNL Journey Optimizer] kampanjer och resor. Med den här funktionen kan ni skapa flera anpassade innehållsblock som kan användas av marknadsföringsanvändare för att snabbt sammanställa e-postinnehåll i en förbättrad designprocess.

![](../rn/assets/do-not-localize/fragments.gif)

➡️ [Lär dig hur du hanterar, redigerar och använder fragment i dessa videofilmer](#video-fragments)

Så här använder du fragment på bästa sätt:

* **Skapa egna fragment**: Skapa visuella fragment eller uttrycksfragment, antingen från grunden eller genom att spara innehåll som fragment. [Lär dig skapa ett fragment](create-fragments.md). Dessutom kan du använda Journey Optimizer **Content REST API** för att hantera innehållsfragment. Mer information finns i dokumentationen för [Journey Optimizer API:er](https://developer.adobe.com/journey-optimizer-apis/references/content/){target="_blank"}.
* **Återanvänd dina fragment:** Använd dem så många gånger som behövs i ditt innehåll. Se [Lägg till visuella fragment](../email/use-visual-fragments.md) och [Utnyttja uttrycksfragment](../personalization/use-expression-fragments.md)

## Före start {#fragment-prerequisites}

Om du vill skapa, redigera, arkivera och publicera fragment behöver du behörigheterna **[!DNL Manage library items]** och **[Publicera fragment]** i produktprofilen för **[!DNL Content Library Manager]**. [Läs mer](../administration/ootb-product-profiles.md#content-library-manager)

I den här versionen gäller följande begränsningar:

* **Visuella fragment** är endast tillgängliga för e-postkanalen.
* **Uttrycksfragment** är inte tillgängliga för kanalen i appen.

Fler skyddsförslag som gäller för fragment finns i [det här avsnittet](../start/guardrails.md#fragments-guardrails).

## Visual &amp; expression fragments {#visual-expression}

Det finns två typer av fragment:

* **Visuella fragment** är fördefinierade visuella block som du kan återanvända i flera e-postleveranser med [e-post-Designer](../email/get-started-email-design.md) eller i [innehållsmallar](../email/use-email-templates.md).
* **Uttrycksfragment** är fördefinierade uttryck som är tillgängliga från en dedikerad post i [personaliseringsredigeraren](../personalization/personalization-build-expressions.md).

Alla skapade fragment kan nås från den vänstra menyn **[!UICONTROL Content Management]** > **[!UICONTROL Fragments]**. [Lär dig hantera fragment](../content-management/manage-fragments.md)

![](assets/fragment-list.png)

## Instruktionsvideo {#video-fragments}

Lär dig hur du hanterar, redigerar och använder **visuella fragment** i [!DNL Journey Optimizer].

>[!VIDEO](https://video.tv.adobe.com/v/3419932/?quality=12)

Lär dig hantera, redigera och använda **uttrycksfragment** i [!DNL Journey Optimizer].

>[!VIDEO](https://video.tv.adobe.com/v/3424587/?quality=12)
