---
title: Kom igång med direktreklam
description: Lär dig hur du skapar och skickar direktreklam i Journey Optimizer
feature: Overview
topic: Content Management
role: User
level: Beginner
keywords: direktreklam, meddelande, kampanj
source-git-commit: 40cd058475b37b8fa7d5c0286ad230422e027cf8
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Skapa ett direktutskick {#create-direct}

>[!AVAILABILITY]
>
>För närvarande är Direct mail channel inte tillgängligt för organisationer som har köpt tillägget Adobe Healthcare Shield.

Direktreklam är en offlinekanal som gör att du kan anpassa och generera extraheringsfiler som krävs av direktreklamleverantörer för att skicka e-post till dina kunder.

När du skapar en kampanj för direktreklam genererar Journey Optimizer automatiskt en fil som innehåller alla målprofiler och valda data, till exempel postadresser och profilattribut. Den här filen skickas till den server du väljer så att den blir tillgänglig för den valda leverantören av direktreklam, som kommer att hantera själva utskicksprocessen åt dig.

De viktigaste stegen för att skicka direktutskick är följande:

![](assets/dm-creation-process.png)

Direktutskick kan bara skapas i samband med schemalagda kampanjer. De är inte tillgängliga för användning i API-utlösta kampanjer eller under resor.

>[!IMPORTANT]
>
>Kontrollera att du har konfigurerat innan du skickar ett direktmeddelande:
>
>1. A [konfiguration för filroutning](../direct-mail/direct-mail-configuration.md#file-routing-configuration) som anger den server där extraheringsfilen ska överföras och lagras,
>1. A [meddelandeyta för direktreklam](../direct-mail/direct-mail-configuration.md#direct-mail-surface) som refererar till filroutningskonfigurationen.
