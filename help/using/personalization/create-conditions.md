---
solution: Journey Optimizer
product: journey optimizer
title: Skapa villkor
description: Lär dig hur du skapar villkor
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: uttryck, redigerare, villkorsstyrd, regler
exl-id: 246a4a55-059e-462c-ac1e-43b90f4abda4
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Arbeta med villkorliga regler {#conditions}

Villkorliga regler är uppsättningar regler som definierar vilket innehåll som ska visas i dina meddelanden, beroende på olika kriterier som profilattribut, målgruppsmedlemskap eller sammanhangsbaserade händelser.

Villkorliga regler skapas med uttrycksredigeraren och kan lagras om du vill återanvända dem i hela innehållet. [Lär dig hur du sparar en villkorlig regel i biblioteket](#save)

>[!NOTE]
>
>Enskilda behöver [Hantera biblioteksobjekt](../administration/ootb-product-profiles.md) behörighet att spara eller ta bort villkorliga regler. Sparade villkor kan användas av alla användare i en organisation.

## Åtkomst till villkorsregelbyggaren {#access}

Villkorliga regler skapas från **[!UICONTROL Conditions]** -menyn i uttrycksredigeraren, som du kommer åt antingen:

* Från e-postdesignern när du aktiverar dynamiskt innehåll för en komponent i e-postbrödtexten. [Lär dig hur du lägger till dynamiskt innehåll i e-postmeddelanden](dynamic-content.md#emails)

  ![](assets/conditions-access-email.png)

* Inom alla områden där du kan lägga till personalisering med [Uttrycksredigeraren](personalization-build-expressions.md).

  ![](assets/conditions-access-editor.png)

## Skapa en villkorsregel {#create-condition}

>[!CONTEXTUALHELP]
>id="ajo_expression_editor_conditions_create"
>title="Skapa villkor"
>abstract="Kombinera profilattribut, sammanhangsbaserade händelser eller målgrupper för att skapa regler som definierar vilket innehåll som ska visas i dina meddelanden."

>[!CONTEXTUALHELP]
>id="ajo_expression_editor_conditions"
>title="Skapa villkor"
>abstract="Kombinera profilattribut, sammanhangsbaserade händelser eller målgrupper för att skapa regler som definierar vilket innehåll som ska visas i dina meddelanden."

Så här skapar du en villkorlig regel:

1. Öppna **[!UICONTROL Conditions]** från Expression Editor eller Email Designer och klicka sedan på **[!UICONTROL Create new]**.

1. Bygg den villkorliga regeln efter dina behov. Det gör du genom att dra och släppa och ordna de önskade attributen från den vänstra menyn på arbetsytan.

Stegen för att kombinera attribut på arbetsytan liknar de som används för att skapa segment. Mer information om hur du arbetar med arbetsytan i regelbyggaren finns i [den här dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html#rule-builder-canvas).

    ![](assets/conditions-create.png)
    
    Attribut är ordnade i tre flikar:
    
    **[!UICONTROL Profile]**:
    **[!UICONTROL Audiences]** visar alla målgruppsattribut (t.ex. status, version osv.) for [Adobe Experience Platform Segmentation service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html),
    **[!UICONTROL XDM Individual profiles]** listar alla profilattribut som är kopplade till [Experience Data Model (XDM)-schemat](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) som definieras i Adobe Experience Platform.
    **[!UICONTROL Contextual]**: när ditt meddelande används i en resa är fält för sammanhangsbaserad resa tillgängliga via den här fliken.
    **[!UICONTROL Audiences]**: listar alla målgrupper som genereras från segmentdefinitioner som skapas i [Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html).

1. När den villkorliga regeln är klar kan du lägga till den i meddelandet för att skapa dynamiskt innehåll. [Lär dig hur du lägger till dynamiskt innehåll](dynamic-content.md)

   Du kan också spara regeln för att tillåta ytterligare återanvändning. [Lär dig hur du sparar ett villkor](#save)

## Spara en villkorlig regel {#save}

Om det finns villkorsregler som du ofta återanvänder kan du spara dem i villkorsbiblioteket. Alla sparade regler delas och kan användas av personer i organisationen.

>[!NOTE]
>
>Villkorliga regler som utnyttjar resans kontextattribut kan inte sparas i biblioteket.

1. Klicka på **[!UICONTROL Save condition]** -knappen.

1. Ge regeln ett namn och en beskrivning (valfritt) och klicka sedan på **[!UICONTROL Add]**.

   ![](assets/conditions-name-description.png)

1. Den villkorliga regeln sparas i biblioteket. Nu kan du använda den för att skapa dynamiskt innehåll i dina meddelanden. [Lär dig hur du lägger till dynamiskt innehåll](dynamic-content.md)

## Redigera och ta bort sparade villkorsregler {#edit-delete}

Du kan när som helst ta bort en villkorlig regel med hjälp av ellipsknappen.

![](assets/conditions-open.png)

Villkorliga regler som sparats i biblioteket kan inte ändras. Du kan dock fortfarande använda dem för att skapa nya regler. Det gör du genom att öppna villkorsregeln, göra önskade ändringar och sedan spara den i biblioteket. [Lär dig hur du sparar ett villkor i biblioteket](#save)
