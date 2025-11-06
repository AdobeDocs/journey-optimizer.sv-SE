---
solution: Journey Optimizer
product: journey optimizer
title: Kom igång med flerspråkigt innehåll
description: Läs mer om flerspråkigt innehåll i Journey Optimizer
feature: Multilingual Content
topic: Content Management
role: User
level: Beginner
keywords: komma igång, börja, innehåll, experimentera
exl-id: b57683b4-6dcc-4f6c-a8b2-4ba371d78d21
source-git-commit: 0ec43a204f5fcf0bddf38cfd381f0ea496c7de70
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Kom igång med flerspråkigt innehåll {#multilingual-gs}

>[!CONTEXTUALHELP]
>id="ajo_multi_translation_homepage"
>title="Översättningar"
>abstract="Med den flerspråkiga funktionen kan ni enkelt skapa innehåll på flera språk i en enda kampanj eller resa. På sidan Översättningar kan du konfigurera projekt, välja översättningsleverantörer eller hantera språkspecifika ordlistor"

Med den flerspråkiga funktionen kan ni enkelt skapa innehåll på flera språk i en enda kampanj eller resa. Med den här funktionen kan ni växla mellan olika språk när ni redigerar kampanjer, effektivisera hela redigeringsprocessen och förbättra möjligheterna att effektivt hantera flerspråkigt innehåll.

Med Journey Optimizer kan du skapa flerspråkigt innehåll på två olika sätt:

* **Manuell översättning**: Översätt ditt innehåll direkt i e-post-Designer eller importera befintligt flerspråkigt innehåll. [Läs mer](multilingual-manual.md)

* **Automatisk översättning**: Skicka innehåll till den önskade språkleverantören för automatisk översättning. [Läs mer](multilingual-automated.md)

</br>

![](assets/translation_schema.png)

## Förhandskrav {#prerequisites}

>[!CONTEXTUALHELP]
>id="ajo_multi_translation_error"
>title="Översättningsfel"
>abstract="Om du inte kommer åt översättningssidan beror det troligtvis på att översättningsfunktionen inte är aktiverad. För att lösa det här problemet måste du se till att översättningsfunktionen aktiveras av din organisations- och sandlådeadministratör."

Adobe Journey Optimizer är för närvarande integrerat med översättningsleverantörer som erbjuder översättningstjänster från tredje part (maskinöversättning eller mänsklig översättning) oberoende av Adobe Journey Optimizer.

Innan du lägger till den valda översättningsprovidern måste du skapa ett konto hos den aktuella providern.

Användningen av en översättningsleverantörs översättningstjänster regleras av ytterligare villkor från den aktuella leverantören.  Som tredjepartslösningar är översättningstjänster tillgängliga för Adobe Journey Optimizer-användare via integrering.  Adobe kontrollerar inte och ansvarar inte för tredjepartsprodukter.

Om du har frågor eller vill ha hjälp med dina översättningar kontaktar du tillämplig översättningsleverantör.

För det flerspråkiga innehållet måste följande inställningar definieras:

* Om du vill använda översättningsfunktionen i Journey Optimizer måste du tilldela API till motsvarande roll. [Läs mer](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication#assign-api-to-a-role)

* Om du vill börja skapa flerspråkigt innehåll måste användarna ha behörighet **[!UICONTROL Manage Language settings]**. För automatiserat flöde behöver användare även behörigheter som är relaterade till **[!UICONTROL Translation Service]**-funktionerna. [Läs mer om behörigheter](../administration/permissions.md)

  +++ Lär dig hur du tilldelar flerspråkiga behörigheter

   1. Gå till fliken **Roller** i produkten **Behörigheter** och välj önskad **roll**.

   1. Klicka på **Redigera** om du vill ändra behörigheterna.

   1. Lägg till resursen för **översättningstjänsten** och välj sedan lämplig flerspråkig behörighet i listrutan.

      ![](assets/multilingual-permission.png){zoomable="yes"}

   1. Klicka på **Spara** om du vill använda ändringarna.

      Alla användare som redan har tilldelats den här rollen får sina behörigheter automatiskt uppdaterade.

   1. Om du vill tilldela den här rollen till nya användare går du till fliken **Användare** på kontrollpanelen **Roller** och klickar på **Lägg till användare**.

   1. Ange användarens namn, e-postadress eller välj i listan och klicka sedan på **Spara**.

   1. Om användaren inte har skapats tidigare, se [den här dokumentationen](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/users).

  +++

* Om du inte kan komma åt översättningssidan måste du aktivera översättningsfunktionen och beviljas **[!UICONTROL Translation service]**-relaterade behörigheter. [Läs mer](../administration/ootb-permissions.md)

  +++ Lär dig aktivera översättningsfunktionen

   1. Om följande felsida visas indikerar den att funktionen **[!UICONTROL Translation]** inte har aktiverats än. Kontakta din organisations- och sandlådeadministratör för att begära åtkomst.

  ![](assets/multi-troubleshoot.png)

   1. Administratören måste navigera till menyn **[!UICONTROL Translation]** i den vänstra sidofältet.

      Systemet aktiverar översättningsfunktionen automatiskt.

   1. När funktionen har aktiverats kan du komma åt sidan **[!UICONTROL Translation]** tillsammans med flikarna **[!UICONTROL Projects]**, **[!UICONTROL Providers]** och **[!UICONTROL Locale]**.

   1. Om den här proceduren har misslyckats visas fortfarande samma felsida. Om så är fallet, kontakta din Adobe-representant för ytterligare hjälp.

  +++

## Instruktionsvideo {#video}

Lär dig hur du skapar innehåll på flera språk i en enda kampanj eller resa.

>[!VIDEO](https://video.tv.adobe.com/v/3430921/)
