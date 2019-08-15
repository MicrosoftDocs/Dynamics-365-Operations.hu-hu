---
title: Az árbevétel-elszámolás áttekintése
description: Ez a témakör a árbevétel-elszámolás funkcióról nyújt tájékoztatást. Ez a funkció rugalmas keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a többelemű rendelések bevételi árának és bevételütemezésének elszámolásához.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: d52a9c7315cccf668a8b9bcf7ba5cad7039e186e
ms.sourcegitcommit: 299e20b59ebefa584ed46a13da3f1a7ff709e43c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863563"
---
# <a name="revenue-recognition-overview"></a>Az árbevétel-elszámolás áttekintése

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> Az „Árbevétel-elszámolás” funkció még nem kapcsolható be a Funkciókezelés helyen. Jelenleg konfigurációs kulcsok használatával kapcsolhatja be.

Olyan iparágak vállalatai esetében, ahol több elem (például termékek, szolgáltatások, előfizetések stb.) értékesítése történik, képesnek kell lennie a több elemből álló rendelések szétbontására, hogy a bevételeket vállalat-és iparág-specifikus irányelvek alapján lehessen elszámolni.

Általánosságban a bevétel-elszámolási folyamat a következő feladatok végrehajtásához használható:

* Bevétel hozzárendelése annak érdekében, hogy garantálható legyen a megfelelő bevételi ár elszámolása a több elemből álló rendelések összetevőinek értéke alapján.
* Bevétel elhalasztása egy bevételütemezés alapján, amely a szerződéses időkeretet és százalékértékeket tartalmazza a bevétel elszámolásához az idők során.

A Bevételelszámolás funkció egy keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a bevételi árak és bevételütemezésének elszámolásához.

A kiadott termékek használatosak a bevételelszámoláshoz az értékesítési rendelési dokumentumokon. A kiadott termékek tartalmazzák azt a beállítást, amely szükséges a bevételi ár és a bevételütemezés meghatározásához. Az értékesítési rendelés idő- és anyagelszámolású projektből származhat.

A vállalatok a bevételütemezés funkciót használhatják a bevételi ár funkcionalitás alkalmazása nélkül is. Ennélfogva az értékesítésirendelés-sorokban szereplő ár bevételként vagy halasztott bevételként is felhasználható. Ha van bevételi ütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár halasztásra kerül. Ha nincs bevételütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár a számlázáskor közzé lesz téve egy bevételi számlán.

A bevételi ár számítása az értékesítési rendelés visszaigazolásakor vagy a számla feladásakor történik. Ha meg szeretné tekinteni az előzetes bevételi árat a számla feladása előtt, akkor meg kell erősítenie az értékesítési rendelést.

Az értékesítési rendelést megerősítésekor, ha bármely értékesítésirendelés-sor bevételi ütemezést tartalmaz, egy várható bevételütemezés is létrejön. Az értékesítési rendelés számlázásakor, a program törli a várható bevételütemezést, és a várható bevételütemezést a tényleges árbevétel-kimutatási ütemezéssel helyettesíti.

A program minden értékesítésirendelés-sorhoz megtartja a bevétel-elszámolás ütemezésének adatait. Ennélfogva a bevétel-elszámolással foglalkozó vezetője megtekintheti a részleteket, és a szerződéses kötelezettség teljesítésekor felszabadíthatja a bevételi sorokat. Az egyes időszakok végén a bevétel-elszámolással foglalkozó vezető bevételi naplót hozhat létre, hogy az általa megadott dátumon vagy azt megelőzően esedékes ütemezési sorokat felszabadítsa. Ez a bevételi napló nem lesz azonnal feladva. Ennélfogva a bevétel-elszámolással foglalkozó vezető ellenőrizheti, hogy a megfelelő összegek lesznek-e felszabadítva a halasztott bevételből a tényleges bevételhez.

Ha egy szerződésmódosítás következtében új értékesítésirendelés-sort kell hozzáadni a meglévő értékesítési rendeléshez vagy új értékesítési rendeléshez, akkor egy újrafelosztási folyamat futtatható a bevételi ár javításához az összes értékesítési rendelés soraiban.
