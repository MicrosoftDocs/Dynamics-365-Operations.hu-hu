---
title: "Költségszámítási verziók"
description: "Ez a cikk a költségszámítási verziókról, azok karbantartásának módjáról, illetve az azokba bevihető adattípusokról nyújt tájékoztatást. A költségszámítási verziók elsődleges célja az, hogy tartalmazzák a cikkek, költségkategóriák és a közvetett költségek számítási képleteinek rekordjait."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 54532
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d22abca3f55ffbe162060bd75191c480992d485
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="costing-versions"></a>Költségszámítási verziók

[!include[banner](../includes/banner.md)]


Ez a cikk a költségszámítási verziókról, azok karbantartásának módjáról, illetve az azokba bevihető adattípusokról nyújt tájékoztatást. A költségszámítási verziók elsődleges célja az, hogy tartalmazzák a cikkek, költségkategóriák és a közvetett költségek számítási képleteinek rekordjait.

A költségszámítási verziók többféle célt szolgálhatnak attól függően, hogy milyen adatokat tartalmaznak. A költségszámítási verziók elsődleges célja az, hogy tartalmazzák a cikkek, költségkategóriák és a közvetett költségek számítási képleteinek rekordjait. A költségszámítási verzió elszámolóár-rekordok vagy olyan tervezett költség rekordok halmazát tartalmazhatja, amelyek a költségszámítási verzióhoz társított költségszámítás-típuson alapulnak.

## <a name="costing-versions-for-standard-or-planned-costs"></a>Költségszámítási verziók elszámolóárakhoz vagy tervezett költségekhez
### <a name="standard-costs"></a>Elszámolóárak

A költségszámítási verziók felhasználhatóak a cikkek elszámolóár szerinti készletmodelljében, ahol a költségszámítási verzió a cikkek és a gyártási folyamatok elszámolóár-rekordjainak halmazát tartalmazza. A gyártási folyamatokra vonatkozó költségadatok az útvonalműveletek költségkategóriáival és a gyártási többletköltségek számítási képleteivel vannak kifejezve.

### <a name="planned-costs"></a>Tervezett költségek

A költségszámítási verziók a cikkek és gyártási folyamatok tervezett költségrekordjait is tartalmazhatják. A tervezett költségeket tartalmazó költségszámítási verziót gyakran használják a költségszámítási szimulációkban, például annak szimulálására, hogy valamilyen beszerzendő anyag vagy gyártási folyamat költségváltozása hogyan hat az előállított cikkek számított költségeire. A tervezett költségek cikköltség-rekordjai a tényleges költség szerinti készletmodellben is felhasználhatók azáltal, hogy megadják a cikköltségek kezdeti értékeit. Ezekbe az értékekbe beletartozik az előállított cikkek tervezett költségeinek számítása.

## <a name="entering-costs"></a>Költségek megadása.
A költségszámítási verzió költségrekord-adatainak karbantartása során rögzíteni kell a beszerzett cikkek és a telephelyek között áthelyezett cikkek költségeit. A gyártó vállalatoknál további adatkarbantartást jelent az útvonalműveletekhez kötődő költségkategóriák költségeinek megadása, a gyártási többletköltséget kifejező közvetett költségek számítási képleteinek megadása, valamint a gyártott cikkek költségeinek számítása. 

A költségszámítási verziókon belül az egyes cikkek költségadatai az adott cikk egy vagy több költségrekordjából állnak össze. A cikk-költségrekordok a legelső bevitelkor **Függőbben** állapottal és egy tervezett érvénybelépési dátummal rendelkeznek. A cikk-költség rekord aktiválásakor az állapot **Aktív** lesz, továbbá az érvénybelépési dátum az aktiválási dátumra módosul. Egy cikk költségrekordjai a telephelyben, az érvénybe lépési dátumban és az állapotban különbözhetnek. A gyártott termékek jövőbeni dátumra vonatkozó költségszámításakor az anyagjegyzék-számításban a megfelelő érvényességi dátumú költségrekordok fognak szerepelni, akár **Függőben**, akár **Aktív** állapotúak. A cikkek aktuális aktív költségrekordja a termelési rendelés költségének becslésében és a készlettranzakció értékének meghatározásában vesz részt az elszámolóár szerinti készletmodellben. A költségkategóriák és a közvetett költség számítási képleteinek költségrekordjai a cikkek költségrekordjaihoz hasonlóan tarthatók karban. 

A költségszámítási verziók két blokkolási szabálya határozza meg, hogy a függő költségek karbantarthatók-e, illetve azt, hogy a függő költség aktiválható-e. A blokkolási szabályokkal engedélyezheti az adatkarbantartást, majd ugyanezek használatával megakadályozhatja a költségrekordok adatainak karbantartását a költségszámítási verzióban. 

A költségszámítási verziók anyagjegyzék-számítási célból a cikkek eladási és beszerzési árára vonatkozó adatokat is tartalmazhatnak.

## <a name="item-sales-prices-for-bom-calculations"></a>Cikkek eladási árai Anyagjegyzék-számításokhoz
Az eladási árakra vonatkozó adatok megadását főként az indokolja, hogy ebben az esetben rendelkezésre áll a gyártott cikkek számított eladási ára. Ekkor a számított eladási ár elemzésével meghatározható, hogy az összetevők, útvonalműveletek és járulékos elemek hogyan járulnak hozzá az önköltségi, illetve eladási árhoz. 

Az eladási árra vonatkozó adatok megadását másodsorban az is indokolja, hogy ezekkel definiálhatóak az összetevőcikkek eladásiár-rekordjai. Ezeknek a rekordoknak a segítségével azután kiszámítható a gyártott cikkek eladási ára. Elsőként az anyagjegyzék-számítási csoportba ágyazott eladásiár-modellt kell megadnia, és hozzá kell rendelnie az anyagjegyzék-számítási csoportot a beszerzett cikkekhez. Ezután tervezett költségeket felhasználó anyagjegyzék-számítások végrehajtásakor ki kell választania az anyagjegyzék-számítási csoport önköltségiár-modelljét. 

Egyéb esetekben a cikkek eladásiár-rekordjait csak hivatkozási adatként használja a rendszer attól függetlenül, hogy a rekordok manuálisan vannak megadva vagy számítottak. Egy cikk eladásiár-rekordjának aktiválásával frissítheti a cikk eladási alapárát. Azonban az eladási alapár nem helyspecifikus, és manuálisan felülbírálható. A cikk eladási alapárát a rendszer az értékesítési rendeléseken és árajánlatokon alapértelmezett eladási árként használja.

## <a name="item-purchase-prices-for-bom-calculations"></a>Cikkek beszerzési árai Anyagjegyzék-számításokhoz
A beszerzési áradatok engedélyezésének elsődleges célja az összetevőcikkek beszerzésiár-rekordjainak definiálása, amelyek így felhasználhatók a legyártott cikkek költségének számításához. A cikk beszerzésiár-rekordjait saját kezűleg kell rögzíteni. 

A beszerzési árak engedélyezéséhez elsőként definiálnia kell egy olyan anyagjegyzék-számítási csoportot, amely tartalmazza a cikk beszerzési árának önköltségiár-modelljét, és az anyagjegyzék-számítási csoportot hozzá kell rendelnie a beszerzett cikkekhez. Ezt követően az anyagjegyzék-számítási csoport egy önköltségiár-modelljének segítségével, ha tervezett költségeket használó anyagjegyzék-számításokat hajt végre, kiszámíthatja a gyártott cikkel eladási árát. 

A cikkek beszerzésiár-rekordjait hivatkozási adatokként is használja a rendszer. Ha egy cikk beszerzésiár-rekordjának **Függőben** állapotát **Aktív** állapotra módosítja, frissítheti a cikk beszerzési alapárát. Azonban a beszerzési alapár nem helyspecifikus, és manuálisan felülbírálható. A cikk beszerzési alapárát a rendszer a beszerzési rendeléseken alapértelmezett beszerzési árként használja.




