---
title: Bevételelszámolás – áttekintés (videót tartalmaz)
description: Ez a cikk a Bevételek kimutatása funkcióval kapcsolatban tartalmaz tájékoztatást. Ez a funkció rugalmas keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a többelemű rendelések bevételi árának és bevételütemezésének elszámolásához.
author: bking
ms.date: 03/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 5bf07356b5613f438034f8dabac7db197e69a6c8
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644030"
---
# <a name="revenue-recognition-overview"></a>A bevételelszámolás áttekintése

[!include [banner](../includes/banner.md)]

>[!NOTE]
>Ez a funkció 2023. októberében lesz elavult, ezért az új felhasználóknak előfizetési számlázást kell használniuk.

Olyan iparágak vállalatai esetében, ahol több elem (például termékek, szolgáltatások, előfizetések stb.) értékesítése történik, képesnek kell lennie a több elemből álló rendelések szétbontására, hogy a bevételeket vállalat-és iparág-specifikus irányelvek alapján lehessen elszámolni.

A bevételelszámolási funkció, beleértve a csomagfunkciót is, nem támogatott a Commerce Channels rendszerben (e-kereskedelem, pénztár, hívásközpont). A bevételelszámolási funkcióval konfigurált tételeket nem lehet hozzáadni a Commerce Channels rendszerben létrehozott rendelésekhez vagy tranzakciókhoz.

Általánosságban a bevételelszámolási folyamat a következő feladatok végrehajtásához használható:

* Bevétel hozzárendelése annak érdekében, hogy biztosítható legyen a megfelelő bevételi ár elszámolása a több elemből álló rendelések összetevőinek értéke alapján.
* Bevétel elhalasztása egy olyan bevételütemezés alapján, amely a szerződéses időkeretet és százalékértékeket tartalmazza a bevétel időbeli elszámolásához.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

A [Bevétel-felismerés használata a Dynamics 365 Pénzügyben](https://youtu.be/v3amIsiqvoo) (fent látható) [a pénzügyi és műveleti elérhetővé](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) című témakörben található YouTube.

A Bevételelszámolás funkció egy keretet biztosít, amely lehetővé teszi, hogy vállalatspecifikus szabályokat határozzon meg a bevételi árak és bevételütemezésének elszámolásához.

A kiadott termékek használatosak a bevételelszámoláshoz az értékesítési rendelési dokumentumokon. A kiadott termékek tartalmazzák azt a beállítást, amely szükséges a bevételi ár és a bevételütemezés meghatározásához. Az értékesítési rendelés idő- és anyagelszámolású projektből származhat.

A vállalatok a bevételütemezési funkciót a bevételi ár funkcionalitás alkalmazása nélkül is használhatják. Ennélfogva az értékesítésirendelés-sorokban szereplő ár bevételként vagy halasztott bevételként is felhasználható. Ha van bevételi ütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár halasztásra kerül. Ha nincs bevételütemezés az értékesítésirendelés-sorban, akkor az értékesítésirendelés-sorban szereplő ár a számlázáskor közzé lesz téve egy bevételi számlán.

A bevételi ár számítása az értékesítési rendelés visszaigazolásakor vagy a számla feladásakor történik. Ha meg szeretné tekinteni az előzetes bevételi árat a számla feladása előtt, akkor meg kell erősítenie az értékesítési rendelést.

Ha az értékesítési rendelés megerősítésekor az egyik értékesítésirendelés-sor bevételi ütemezést tartalmaz, egy várható bevételütemezés is létrejön. Az értékesítési rendelés számlázásakor, a program törli a várható bevételütemezést, és a várható bevételütemezést a tényleges árbevétel-kimutatási ütemezéssel helyettesíti.

A program minden értékesítésirendelés-sorhoz megtartja a bevétel-elszámolás ütemezésének adatait. Ennélfogva a bevétel-elszámolással foglalkozó vezetője megtekintheti a részleteket, és a szerződéses kötelezettség teljesítésekor felszabadíthatja a bevételi sorokat. Az egyes időszakok végén a bevétel-elszámolással foglalkozó vezető bevételi naplót hozhat létre, hogy az általa megadott dátumon vagy azt megelőzően esedékes ütemezési sorokat felszabadítsa. Ez a bevételi napló nem lesz azonnal feladva. Ennélfogva a bevétel-elszámolással foglalkozó vezető ellenőrizheti, hogy a megfelelő összegek lesznek-e felszabadítva a halasztott bevételből a tényleges bevételhez.

Ha egy szerződésmódosítás következtében új értékesítésirendelés-sort kell hozzáadni a meglévő értékesítési rendeléshez vagy új értékesítési rendeléshez, akkor újrafelosztási folyamat futtatható a bevételi ár javításához az összes értékesítési rendelés soraiban.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

