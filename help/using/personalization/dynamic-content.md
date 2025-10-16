---
solution: Journey Optimizer
product: journey optimizer
title: Skapa dynamiskt innehåll
description: Lär dig hur du lägger till dynamiskt innehåll i meddelanden.
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, dynamiskt innehåll
exl-id: 639ad7df-0d0f-4c9b-95d1-f3101267aae2
source-git-commit: 87245fffb3ad10d51a7500d006dbe69b1905640e
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---

# Skapa dynamiskt innehåll {#dynamic-content}

Med Adobe Journey Optimizer kan du använda villkorliga regler som skapats i biblioteket för att lägga till dynamiskt innehåll i dina meddelanden.

Dynamiskt innehåll kan skapas i alla fält där du kan lägga till personalisering med personaliseringsredigeraren. Detta inkluderar ämnesrad, länkar, push-meddelanden och textrepresentationer. [Läs mer om personalisering](personalize.md)

Dessutom kan du använda villkorliga regler i e-postprogrammet för Designer för att skapa flera varianter av en innehållskomponent.

## Lägg in dynamiskt innehåll i uttryck {#perso-expressions}

Stegen för att lägga till dynamiskt innehåll i uttryck är följande:

1. Navigera till fältet där du vill lägga till dynamiskt innehåll och öppna sedan redigeraren för anpassning.

1. Välj menyn **[!UICONTROL Conditions]** om du vill visa listan med tillgängliga villkorsregler. Klicka på plusknappen bredvid en regel för att lägga till den i det aktuella uttrycket.

   Du kan också skapa en ny regel genom att välja **[!UICONTROL Create new]**. [Lär dig skapa villkor](create-conditions.md)

   ![](assets/conditions-expression.png)

1. Lägg till mellan taggarna `{%if}` och `{%/if}` det innehåll som du vill visa om den villkorliga regeln uppfylls. Du kan lägga till så många regler som behövs för att skapa flera varianter av ett uttryck.

   I exemplet nedan har två varianter skapats för ett SMS-innehåll, beroende på vilket språk mottagaren föredrar.

   ![](assets/conditions-language-sample.png)

1. När innehållet är klart kan du förhandsgranska de olika varianterna med knappen **[!UICONTROL Simulate content]**. [Lär dig hur du testar och förhandsgranskar meddelanden](../content-management/preview-test.md)

   ![](assets/conditions-preview.png)

>[!CAUTION]
>
>Om e-post-Designer inte kan återges korrekt när du har lagt till villkorliga block, kontrollerar du att de nya villkorens syntax är korrekt och att det inte finns några dubbletter eller motstridiga satser. Om problemen kvarstår kan du överväga att återskapa problematiska avsnitt i en ny mall och testa varje villkorsstyrd block stegvis.


## Lägg in dynamiskt innehåll i e-postmeddelanden {#emails}

>[!CONTEXTUALHELP]
>id="ac_conditional_content"
>title="Villkorligt innehåll"
>abstract="Använd villkorsregler för att skapa flera varianter av en innehållskomponent. Om inget av villkoren uppfylls när meddelandet skickas visas innehållet från standardvarianten."

>[!CONTEXTUALHELP]
>id="ac_conditional_content_select"
>title="Villkorligt innehåll"
>abstract="Använd en villkorsstyrd regel som sparats i biblioteket eller skapa en ny."

Stegen för att skapa varianter av en innehållskomponent i e-post-Designer är följande:

1. I [e-posta Designer](../email/content-from-scratch.md) väljer du en innehållskomponent och klickar sedan på **[!UICONTROL Enable conditional content]**.

   ![](assets/conditions-enable-conditional.png)

1. Fönstret **[!UICONTROL Conditional Content]** visas till vänster. I den här rutan kan du skapa flera varianter av den markerade innehållskomponenten med villkor.

   Konfigurera den första varianten genom att välja knappen **[!UICONTROL Select condition]**.

   ![](assets/conditions-apply.png)

1. Villkorsbiblioteket visas. Välj den villkorliga regel som ska associeras med varianten och klicka sedan på **[!UICONTROL Select]**. I det här exemplet vill vi anpassa komponenttexten beroende på vilket språk mottagaren föredrar.

   ![](assets/conditions-select.png)

   Du kan också skapa en ny regel genom att klicka på **[!UICONTROL Create new]**. [Lär dig skapa villkor](create-conditions.md)

1. Den villkorliga regeln är kopplad till varianten. Byt namn på varianten genom att välja åtgärden **[!UICONTROL Rename]** från ikonen Fler åtgärder för att få bättre läsbarhet.

   ![](assets/conditions-rename.png)

1. Konfigurera hur komponenten ska visas om regeln uppfylls när meddelandet skickas. I det här exemplet vill vi visa texten på franska om det är mottagarens favoritspråk.

   ![](assets/conditions-design.png)

1. Lägg till så många varianter som behövs för innehållskomponenten. Du kan när som helst växla mellan de olika varianterna för att kontrollera hur innehållskomponenten visas beroende på villkorsreglerna.

   >[!NOTE]
   >
   >* Om inga av reglerna som definieras i varianterna uppfylls när meddelandet skickas, kommer innehållskomponenten att visa innehållet som definierats i **[!UICONTROL Default variant]**.
   >
   >* Villkorligt innehåll utvärderas mot kopplade regler i den ordning som varianterna visas. Standardvarianten visas alltid om inga andra villkor uppfylls.
   >
   >* När du simulerar eller återger korrektur för e-postmeddelanden som innehåller flera villkorliga varianter kan Journey Optimizer kräva mer bearbetningstid. Om du får timeout eller felmeddelanden kan du minska det totala antalet varianter eller förenkla villkorliga regler. Läs mer om hur du testar ditt innehåll på [den här sidan](../content-management/preview-test.md).


1. Om du vill ta bort en variant klickar du på ikonen Fler åtgärder bredvid den önskade varianten och väljer **[!UICONTROL Delete]**.

   ![](assets/conditions-delete.png)
