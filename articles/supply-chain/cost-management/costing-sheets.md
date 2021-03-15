---
title: Költségszámítási táblázatok
description: A költségszámítási táblázat beállításakor két célt kell szem előtt tartani. Az első cél az áruk költségeinek megjelenítésére használt formátum meghatározása a gyártott cikkekre vagy termelési rendelésre vonatkozóan. A formázott megjelenítés neve költségszámítási táblázat. A második cél a közvetett költségek számításához használt alap meghatározása. A költségszámítási táblázat a költségcsoport funkcióra építve jeleníti meg az adatokat, és a költségcsoportokat a közvetett költség számítási képleteiben is felhasználja. Ebben a cikkben a költségszámítási táblázat beállításának két célkitűzése van leírva.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostSheetDesigner, CostSheetCalculationFactor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53201
ms.assetid: e7d72b43-3892-49ae-8821-9eede3f4d24a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5df761015ed9382f59fa8ba7df9e5856db06287c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987654"
---
# <a name="costing-sheets"></a>Költségszámítási táblázatok

[!include [banner](../includes/banner.md)]

A költségszámítási táblázat beállításakor két célt kell szem előtt tartani. Az első cél az áruk költségeinek megjelenítésére használt formátum meghatározása a gyártott cikkekre vagy termelési rendelésre vonatkozóan. A formázott megjelenítés neve költségszámítási táblázat. A második cél a közvetett költségek számításához használt alap meghatározása. A költségszámítási táblázat a költségcsoport funkcióra építve jeleníti meg az adatokat, és a költségcsoportokat a közvetett költség számítási képleteiben is felhasználja. Ebben a cikkben a költségszámítási táblázat beállításának két célkitűzése van leírva. 

Az első cél az áruk költségeinek megjelenítésére használt formátum meghatározása a gyártott cikkekre vagy termelési rendelésre vonatkozóan. Költségszámítási táblázat beállításakor az adatok formátumának meghatározása, és is a közvetett költségek számításához használt alap meghatározása. A költségszámítási táblázat a költségcsoport funkcióra építve jeleníti meg az adatokat, és a költségcsoportokat a közvetett költség számítási képleteiben is felhasználja. További információt a költségszámítási táblázat beállításának két célja van:
-   **Határozza meg a költségszámítási táblázat formátumát.** A költségszámítási táblázat felhasználó által definiált formátuma meghatározza azon költségek szegmentálását, amelyek egy gyártott cikk bekerülési költségét tartalmazzák. A cikk bekerülési költségadatai például költségcsoport szerint anyag-, munka- és járulékos költségekre oszthatók fel. E költségcsoportok cikkekhez, az útvonalműveleteknél használt költségkategóriákhoz, valamint közvetett költségszámítási képletekhez vannak hozzárendelve. A költségszámítási táblázat formátuma jellemzően részösszegeket is tartalmaz, ha több költségcsoport is meg van határozva, például összegezheti az anyagköltségekhez kapcsolódó költségcsoportokat. Ha például több költségcsoportok kapcsolódó anyag kell összesíteni. A költségszámítási táblázat formátumának meghatározása nem kötelező, közvetett költségek számítása esetén azonban mindenképpen meg kell határozni.
-   **Határozza meg a közvetett költségek számításához használt alapot.** A közvetett költségek a gyártási többletköltségeket tükrözik, amelyek az előállított termék gyártási folyamatával kapcsolatosak. A közvetett költség pótdíj és óradíj formájában is kifejezhető. A pótdíj az érték bizonyos százalékát jelenti, míg az óradíj egy útvonalműveletekre vonatkozó óránkénti összeget jelenít meg. A költségcsoportok meghatározzák a számítási képlet alapját, ami lehet például 100 százalékos pótdíj a munkaköltség csoportjában vagy 50,00 USD/órás óradíj a gépköltség csoportjában. A számítási képlet és az alapul szolgáló költségcsoportok meghatározásához a költségszámítási táblázatban meg kell adni azoknak a költségcsoportoknak az azonosítóját, amelyek megjelenítik a többletköltségeket, és meg kell határozni, hogy pótdíjként vagy óradíjként számítják-e a közvetett költségeket.

Minden számítási képletet költségrekordként kell rögzíteni. A költségrekord egy meghatározott költségszámítási verzióból, egy pótdíj-százalékból vagy egy óradíjösszegből, az alapul szolgáló költségcsoportból, egy állapotból és egy érvényességi dátumból áll. A cikk-költségrekordok a legelső bevitelkor **Függőben** állapottal és egy tervezett érvénybelépési dátummal rendelkeznek. A cikk-költség rekord aktiválásakor az állapot Aktív lesz, továbbá az érvénybelépési dátum az aktiválási dátumra módosul. A költségrekord egész vállalatra kiterjedő vagy telephely-specifikus számítási képletet egyaránt tükrözhet. Azt is megteheti, akkor hagyhatja a **Hely** mező üres, annak jelzésére, hogy a számítási képlet vállalatszintű képlet. A költségrekordban ezenkívül szerepelhet meghatározott cikk vagy cikkcsoport is, ha a számítási képlet egy adott cikkre vonatkozik. 

A közvetett költségszámítási képletek jelenleg aktív költségrekordjai a termelési rendelés költségbecslésében lesznek felhasználva. Az idő és anyag tényleges felhasználásához kapcsolódó tényleges költségszámításban is felhasználásra kerülnek. A függőben lévő költségrekordok a jövőbeni dátumra vonatkozó anyagjegyzék-számításokban vesznek részt. 

A költségszámítási verziók két blokkolási szabálya határozza meg, hogy a függő költségek karbantarthatók-e, illetve azt, hogy a függő költség elindítható-e. A blokkolási szabályokkal engedélyezheti az adatkarbantartást, majd ezután megakadályozhatja a költségadatok karbantartását a költségszámítási verzióban. 

A költségszámítási táblázat formátumának és a közvetett költségek számításának meghatározása után egy külön lépésben kell kezdeményeznie az adatok érvényesítését és mentését. A költségszámítási táblázat olyan formátumot határoz meg, amely vállalatszerte egységesen jeleníti meg a bekerülési költségeket. 

A költségszámítási táblázat részeként jelenik meg a **Tételköltség kiszámítása** oldalon. A gyártott cikkek számított költségrekordjának költségszámítási táblázata az **Cikkár** képernyőn jeleníthető meg, a rendelés-specifikus számítási rekordé pedig az **Anyagjegyzék-számítás eredményei** képernyőn. A **Árszámítás** táblázat látható a termelési rendelés árszámítási lekérdező képernyőjén is.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]