---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Kom igång för systemadministratör
description: Som systemadministratör får du lära dig mer om hur du arbetar med Journey Optimizer
feature: Get Started
role: Admin
level: Intermediate
exl-id: 24f85ced-aa45-493f-b2c4-7c7b58351b38
source-git-commit: 2d699fe8a3320400dad2d5d962028d6e2a5425f8
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 1%

---

# Kom igång med systemadministratörer {#get-started-sys-admins}

Som **systemadministratör** konfigurerar du Journey Optimizer-miljön och hanterar åtkomsten så att dina team kan arbeta effektivt och säkert. Du utför viktiga konfigurationssteg så att [datateknikern](data-engineer.md), [utvecklaren](developer.md) och [marknadsföraren](marketer.md) kan börja arbeta med [!DNL Adobe Journey Optimizer].

Ditt primära ansvar är bland annat att konfigurera användargrupper och behörigheter, skapa och hantera sandlådor för partitionering av data och resor för olika användargrupper och konfigurera leveranskanaler och meddelandeförinställningar för att säkerställa enhetlig branding för de olika meddelanden och resurser som levereras via Journey Optimizer. Ni ser till att rätt personer har tillgång till rätt funktioner samtidigt som ni upprätthåller säkerhet och styrning.

Dessa funktioner kan hanteras av **[!UICONTROL Product administrators]** som har åtkomst till produkten Behörigheter. [Läs mer om behörigheter](../../administration/permissions.md){target="_blank"}.

## Konfigurera åtkomst och behörigheter

Följ de här stegen för att konfigurera åtkomsthantering:

1. **Skapa sandlådor** för att partitionera dina instanser i separata, isolerade virtuella miljöer. **Sandlådor** skapas i [!DNL Journey Optimizer]. Läs mer i avsnittet [Sandlådor](../../administration/sandboxes.md).

   >[!NOTE]
   >Om du som **systemadministratör** inte kan se menyn **[!UICONTROL Sandboxes]** i [!DNL Journey Optimizer] måste du uppdatera dina behörigheter. Lär dig hur du uppdaterar din roll på [den här sidan](../../administration/permissions.md#edit-product-profile).

1. **Förstå roller**. Roller är en uppsättning enhetsbehörigheter som ger användarna tillgång till vissa funktioner eller objekt i gränssnittet. Läs mer i avsnittet [färdiga roller](../../administration/ootb-product-profiles.md).

1. **Ange behörigheter** för roller, inklusive **Sandlådor**, och ge teammedlemmarna åtkomst genom att tilldela dem till olika roller. Behörigheter är enhetsbehörigheter som gör att du kan definiera de behörigheter som tilldelats **[!UICONTROL Role]**. Varje behörighet samlas in under funktioner, t.ex. Resor eller Erbjudanden, som representerar olika funktioner eller objekt i [!DNL Journey Optimizer]. Läs mer i avsnittet [Behörighetsnivåer](../../administration/high-low-permissions.md).

1. **Använd åtkomstkontroll på objektnivå** (valfritt). Använd etiketter på objekt som resor, kampanjer och kanalkonfigurationer för att styra vilka användare som har tillgång till specifika resurser. Läs mer om [Åtkomstkontroll på objektnivå (OLAC)](../../administration/object-based-access.md).

Dessutom måste du lägga till användare som behöver åtkomst till Assets Essentials i rollerna **Assets Essentials Consumer Users** eller **Assets Essentials Users**. [Läs mer i dokumentationen för Assets Essentials](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html){target="_blank"}.

När du använder [!DNL Journey Optimizer] för första gången tilldelas du en produktionssandlåda och ett visst antal IP-adresser beroende på ditt kontrakt.

## Konfigurera kanaler och meddelanden

Om du vill att [marknadsförare](marketer.md) ska kunna skapa och skicka meddelanden går du till menyn **ADMINISTRATION** . Bläddra i menyn **[!UICONTROL Channels]** om du vill konfigurera kanalinställningar.

>[!NOTE]
>Om du är **systemadministratör** och inte kan se menyn **[!UICONTROL Channels]** i [!DNL Journey Optimizer] måste du uppdatera dina behörigheter i produkten [Permissions](../../administration/permissions.md){target="_blank"} .

Följ de här stegen:

1. **Konfigurera kanalkonfigurationer**. Definiera alla tekniska parametrar som krävs för e-post, SMS, push-meddelanden och andra kanaler:

   * Definiera **inställningar för push-meddelanden** i både [!DNL Adobe Experience Platform] och Adobe Experience Platform Data Collection. [Läs mer](../../push/push-gs.md)

   * Skapa **kanalkonfigurationer** för att konfigurera alla tekniska parametrar som krävs för e-post, SMS, push, in-app, webb och andra kanaler. [Läs mer](../../configuration/channel-surfaces.md)

   * Konfigurera **SMS-kanalen** för att konfigurera alla tekniska parametrar som krävs för SMS. [Läs mer](../../sms/sms-configuration.md)

   * Hantera det antal dagar under vilket **återförsök** utförs innan e-postadresser skickas till listan över utelämnanden. [Läs mer](../../configuration/manage-suppression-list.md)

1. **Delegera underdomäner**: För alla nya underdomäner som ska användas i Journey Optimizer är det första steget att delegera den. [Läs mer](../../configuration/about-subdomain-delegation.md)

   ![](../assets/subdomain.png)

1. **Skapa IP-pooler**: Förbättra e-postleveransen och ditt anseende genom att gruppera IP-adresser som har etablerats med din instans. [Läs mer](../../configuration/ip-pools.md)

   ![](../assets/ip-pool.png)

1. **Hantera inaktiveringen och tillåtelselista**: Förbättra leveransen med inaktivering och tillåtelselista

   * En [inaktiveringslista](../../reports/suppression-list.md) består av e-postadresser som du vill utesluta från leveranser, eftersom det kan skada ditt anseende och din leveransfrekvens om du skickar till dessa kontakter. Du kan övervaka alla e-postadresser som automatiskt har uteslutits från att skickas under en resa, till exempel ogiltiga adresser, adresser som alltid har mjuka studsar, och som kan påverka ditt e-postanseende negativt, samt mottagare som gör något slags skräppostklagomål mot något av dina e-postmeddelanden. Lär dig hur du hanterar [listan över inaktiveringar](../../configuration/manage-suppression-list.md) och [försök](../../configuration/retries.md).

   ![](../assets/suppression-list-filtering-example.png)

   * Med [tillåtelselista](../../configuration/allow-list.md) kan du ange enskilda e-postadresser eller domäner som ska vara de enda mottagarna eller domänerna som har behörighet att ta emot e-postmeddelanden som du skickar från en viss sandlåda. Detta kan förhindra att du av misstag skickar e-post till verkliga kundadresser när du befinner dig i en testmiljö. Lär dig hur du [aktiverar tillåtelselista](../../configuration/allow-list.md).

   Läs mer om Leveranshantering i [!DNL Adobe Journey Optimizer] [på den här sidan](../../reports/deliverability.md).

## Ytterligare funktioner

I takt med att organisationens behov växer bör du tänka på följande avancerade funktioner:

* **Samtyckespolicyer**: Om din organisation har köpt Sköld för hälsovård eller sköld för sekretess och säkerhet, skapar du samtyckespolicyer för att respektera kundpreferenser över olika kanaler. [Läs mer](../../action/consent.md)

* **Datastyrningsprinciper**: Använd etiketter och principer för dataanvändning för att styra hur data används i marknadsföringsåtgärder. [Läs mer](../../action/action-privacy.md)

* **IP-värmeringsplaner**: Öka antalet e-postutskick gradvis för att skapa avsändarens anseende hos e-postleverantörer. [Läs mer](../../configuration/ip-warmup-gs.md)

## Samarbeta mellan roller

Tack vare ert administrativa arbete kan alla team lyckas:

>[!BEGINTABS]

>[!TAB Supporttekniker]

Samarbeta med [datatekniker](data-engineer.md) om datahantering och åtkomst:

* Bevilja behörigheter för datahantering och schemaskapande
* Godkänn sandlådeåtkomst för utveckling och testning
* Koordinera om policyer för datalagring och styrningsregler
* Möjliggör åtkomst till avancerade funktioner som Federated Audience Composition

>[!TAB Aktivera utvecklare]

Samarbeta med [utvecklare](developer.md) om API-åtkomst och -testning:

* Ange API-autentiseringsuppgifter via Adobe Developer Console
* Konfigurera sandlådemiljöer för utveckling och testning
* Godkänn kanalkonfigurationer (push-certifikat, SMS-providers)
* Koordinera testmiljöer och distributionsstrategier

>[!TAB Empower Marketers]

Samarbeta med [marknadsförare](marketer.md) om behörigheter och kanalinställningar:

* Tilldela lämpliga behörigheter för att skapa resor och kampanjer
* Konfigurera de kanaler som de ska använda (e-post, push, SMS etc.)
* Stödja testmiljöer och arbetsflöden för godkännande
* Möjliggör åtkomst till nya funktioner

>[!ENDTABS]

## Nästa steg

När miljön har konfigurerats:

1. **Verifiera installationen**: Bekräfta att alla teammedlemmar har tillgång till de funktioner som krävs
2. **Övervaka användning**: Använd administrationspanelerna för att spåra systemanvändning och identifiera problem
3. **Behåll behörigheter**: Granska och uppdatera behörigheter regelbundet allt eftersom teamroller utvecklas
