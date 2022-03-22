---
title: Bevételelszámolás – áttekintés (videót tartalmaz)
description: Ez a témakör a Bevételelszámolás funkcióról nyújt tájékoztatást. Ez a funkció rugalmas keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a többelemű rendelések bevételi árának és bevételütemezésének elszámolásához.
author: kweekley
ms.date: 11/11/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: a5e7b6407fe72c56ea04920532d4327d2b89f8d1
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982587"
---
# <a name="revenue-recognition-overview"></a>A bevételelszámolás áttekintése

[!include [banner](../includes/banner.md)]

Olyan iparágak vállalatai esetében, ahol több elem (például termékek, szolgáltatások, előfizetések stb.) értékesítése történik, képesnek kell lennie a több elemből álló rendelések szétbontására, hogy a bevételeket vállalat-és iparág-specifikus irányelvek alapján lehessen elszámolni.

> [!NOTE]
> A bevételelszámolási funkció nem kapcsolható be a Funkciókezelés lehetőségen keresztül. Jelenleg konfigurációs kulcsok használatával kapcsolhatja be.

> A bevételelszámolási funkció, beleértve a csomagfunkciót is, nem támogatott a Commerce Channels rendszerben (e-kereskedelem, pénztár, hívásközpont). A bevételelszámolási funkcióval konfigurált tételeket nem lehet hozzáadni a Commerce Channels rendszerben létrehozott rendelésekhez vagy tranzakciókhoz.

Általánosságban a bevételelszámolási folyamat a következő feladatok végrehajtásához használható:

* Bevétel hozzárendelése annak érdekében, hogy biztosítható legyen a megfelelő bevételi ár elszámolása a több elemből álló rendelések összetevőinek értéke alapján.
* Bevétel elhalasztása egy olyan bevételütemezés alapján, amely a szerződéses időkeretet és százalékértékeket tartalmazza a bevétel időbeli elszámolásához.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

A [Bevételelszámolás használata a Dynamics 365 Finance szolgáltatásban](https://youtu.be/v3amIsiqvoo) című videó (fent) szerepel a [Finance and Operations lejátszási listán](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW), amely elérhető a YouTube felületén.

A Bevételelszámolás funkció egy keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a bevételi árak és bevételütemezésének elszámolásához.

A kiadott termékek használatosak a bevételelszámoláshoz az értékesítési rendelési dokumentumokon. A kiadott termékek tartalmazzák azt a beállítást, amely szükséges a bevételi ár és a bevételütemezés meghatározásához. Az értékesítési rendelés idő- és anyagelszámolású projektből származhat.

A vállalatok a bevételütemezési funkciót a bevételi ár funkcionalitás alkalmazása nélkül is használhatják. Ennélfogva az értékesítésirendelés-sorokban szereplő ár bevételként vagy halasztott bevételként is felhasználható. Ha van bevételi ütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár halasztásra kerül. Ha nincs bevételütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár a számlázáskor közzé lesz téve egy bevételi számlán.

A bevételi ár számítása az értékesítési rendelés visszaigazolásakor vagy a számla feladásakor történik. Ha meg szeretné tekinteni az előzetes bevételi árat a számla feladása előtt, akkor meg kell erősítenie az értékesítési rendelést.

Ha az értékesítési rendelés megerősítésekor az egyik értékesítésirendelés-sor bevételi ütemezést tartalmaz, egy várható bevételütemezés is létrejön. Az értékesítési rendelés számlázásakor, a program törli a várható bevételütemezést, és a várható bevételütemezést a tényleges árbevétel-kimutatási ütemezéssel helyettesíti.

A program minden értékesítésirendelés-sorhoz megtartja a bevétel-elszámolás ütemezésének adatait. Ennélfogva a bevétel-elszámolással foglalkozó vezetője megtekintheti a részleteket, és a szerződéses kötelezettség teljesítésekor felszabadíthatja a bevételi sorokat. Az egyes időszakok végén a bevétel-elszámolással foglalkozó vezető bevételi naplót hozhat létre, hogy az általa megadott dátumon vagy azt megelőzően esedékes ütemezési sorokat felszabadítsa. Ez a bevételi napló nem lesz azonnal feladva. Ennélfogva a bevétel-elszámolással foglalkozó vezető ellenőrizheti, hogy a megfelelő összegek lesznek-e felszabadítva a halasztott bevételből a tényleges bevételhez.

Ha egy szerződésmódosítás következtében új értékesítésirendelés-sort kell hozzáadni a meglévő értékesítési rendeléshez vagy új értékesítési rendeléshez, akkor újrafelosztási folyamat futtatható a bevételi ár javításához az összes értékesítési rendelés soraiban.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]