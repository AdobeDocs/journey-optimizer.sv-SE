---
solution: Journey Optimizer
product: journey optimizer
title: Hantera taggar under resor
description: Hantera taggar under resor
feature: Journeys, Tags
topic: Content Management
role: User
level: Intermediate
keywords: resa, taggar
exl-id: 44c255d1-121c-47d4-b407-161626ca3cb4
version: Journey Orchestration
source-git-commit: 302db58525a7b2648bb9c44bc9b42da787ca9c43
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# Hantera taggar under resor {#journey_tags}

Som Journey Optimizer-läkare kan du ordna dina resor med hjälp av taggar. Taggar är ett snabbt och enkelt sätt att klassificera objekt för att förbättra sökningen.

## Taggar jämfört med namnkonventioner {#tags-vs-naming}

Team förlitar sig ofta på komplexa namngivningskonventioner för att lagra metadata direkt i resenamnen, till exempel: *Livscykelmarknadsföring - Utbildning - kundintroduktion V2 - Apputbildning - Q3 2025*. Även om det är välavsiktligt har detta tillvägagångssätt en viktig svaghet: när arbetet skalas över teammedlemmarna tillämpas konventionen sällan konsekvent och reselistorna blir svåra att navigera i.

**Taggkategorier** i Journey Optimizer är ett bättre alternativ. I stället för att koda metadata i namnet lägger du till kategoriserade taggar för varje resa (t.ex. team, mål, fas, kvartal) och använder filter för att hitta dem. Resensnamnen kan sedan fokusera på det som faktiskt betyder något: kundens milstolpe drivs av.

Fördelar med taggkategorier framför namnkonventioner:

* **Konsekvens** - taggar markeras från en kontrollerad lista och skrivs inte fritt.
* **Filterability** - alla kombinationer av taggvärden kan användas för att segmentera reselistan direkt.
* **Klarhet** - namn på resor förblir korta och milstolpe-fokuserade.
* **Skalbarhet** - om du lägger till en ny metadatadimension måste du skapa en ny taggkategori, inte skriva om en namnkonvention.

Ett rekommenderat konfigurationsarbetsflöde finns i [Konfigurera taggkategorier för resehantering](#tags-setup) nedan.

## Lägga till taggar till en resa

I fältet **Taggar** i resans egenskaper kan du definiera taggar för din resa. Du kan antingen markera en befintlig tagg eller skapa en ny. Börja skriva namnet på den önskade taggen och markera den i listan. Om den inte är tillgänglig klickar du på **Skapa** för att skapa en ny och lägga till den på din resa. Du kan definiera så många taggar som behövs.

![Panelen Taggar i resans egenskaper för kategorisering och organisation](assets/tags1.png)

Listan med definierade taggar visas under fältet **Taggar**.

>[!NOTE]
>
> Taggar är skiftlägeskänsliga
> 
> Om du duplicerar eller skapar en ny version av en resa bevaras taggarna.

## Filtrera på taggar

I reselistan visas en dedikerad kolumn så att du enkelt kan se dina taggar.

Ett filter är också tillgängligt för att endast visa resor med vissa taggar.

![Listrutan för taggval med tillgängliga taggar för reseklassificering](assets/tags2.png)

Du kan lägga till eller ta bort taggar från alla typer av resor (live, draft, etc.). Klicka på ikonen **Fler åtgärder** bredvid resan och välj **Redigera taggar**.

![Reselista filtrerad med taggar som visar kategoriserade resor](assets/tags3.png)

## Hantera taggar

Administratörer kan ta bort taggar och ordna dem efter kategorier med hjälp av menyn **Taggar** under **ADMINISTRATION**. Läs den här [dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/overview.html).

>[!NOTE]
>
> Taggar som definieras i resor läggs till i den inbyggda kategorin&quot;Ej kategoriserad&quot;.

## Ställ in taggkategorier för resehantering {#tags-setup}

Följ de här stegen för att ersätta en komplex namnkonvention med en taggbaserad strategi i hela teamet.

**Steg 1 - Skapa taggkategorier (Admin)**

I **[!UICONTROL Administration]** > **[!UICONTROL Tags]** skapar du en kategori för varje metadataattribut som ditt team för närvarande kodar i kundnamnen, till exempel: *Team*, *Marknadsföringsmål*, *Campaign*, *Phase*, *Quarter*.

**Steg 2 - Fyll i varje kategori med taggvärden (Admin)**

I varje kategori skapar du de taggar som representerar alla möjliga värden. Kategorin *Fas* kan t.ex. innehålla: *Medvetenhet*, *Påbörja*, *Behåll*, *Win-back*.

**Steg 3 - Använd taggar när du skapar resor (proffs)**

Varje gång en ny resa skapas väljer du lämplig tagg för varje kategori i reseegenskaperna. En resa har vanligtvis en tagg per kategori.

**Steg 4 - Namnge resor för milstolpen, filtrera efter taggar**

Behåll kundens namn fokuserat på den milstolpe som den kör (t.ex. *Första lojalitetstransaktionen*). Använd taggfilter i reselistan för att hitta resor med valfri kombination av metadata - utan att förlita dig på namnparsning.

>[!TIP]
>
>Mer information om detta tillvägagångssätt och dess fördelar i stor skala finns i [Bästa tillvägagångssätt för avancerade resor i Journey Optimizer](https://experienceleague.adobe.com/en/perspectives/best-practices-for-advanced-journeys-in-journey-optimizer){target="_blank"}.
