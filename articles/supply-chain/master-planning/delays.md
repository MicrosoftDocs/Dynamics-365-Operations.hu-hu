---
title: Késések
description: Ez a cikk az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.
author: t-benebo
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e7e0150e40193f2f799677ad19cae2ea589afc0
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740630"
---
# <a name="delays"></a>Késések

[!include [banner](../includes/banner.md)]

Ez a cikk az alaptervezésben szereplő késleltetett dátumokról szolgál információval. A késleltetett dátum egy olyan valós határidő, amelyet a tranzakció kap meg, akkor ha az alaptervezés által kiszámított legkorábbi teljesítési dátum későbbre esik, mint a kért dátum.

Az alaptervezés kiszámíthatja egy tranzakció legkorábbi teljesítési dátumát, az átfutási idők, az anyagok rendelkezésre állása, a rendelkezésre álló kapacitás és a különböző tervezési paraméterek alapján. 

Ha az alaptervezés olyan rendelési dátumot számít ki, amely az aktuális dátumnál korábbi, akkor a rendelés időben nem teljesíthető. Emiatt a rendelés késik. Ebben az esetben az alaptervezés az aktuális dátumtól kezdve előretolja a tervet, és figyelembe veszi az átfutási időket is. Ezek az átfutási idők bármely alacsonyabb szintű összetevő elemmel kezdődhetnek. A rendelés ezután egy késleltetett dátumot kap. A késleltetett dátum egy valószerű, a tényleges adatokon alapuló dátum lesz. Az alaptervezés emellett a késés napjait is kiszámítja. 

Bizonyos esetekben előfordulhat, hogy nem kívánja kiszámolni a késést, például amikor a felhasználók tudják, hogy alternatív szállítási módok kiválasztásával megsürgethetik az átfutási időt. 

Beállíthatja, hogyan számítsa ki a rendszer a fedezetcsoport késéseit. Ezt követően csatolhatja a fedezetcsoportot egy cikkhez. 

Az **Alaptervezés paraméterei** lapon beállíthatja a késések számításának kezdő időpontját. Ha egy rendelés ezen időpont után teljesül, akkor egy nap hozzáadódik a rendelés késési dátumához. 

> [!NOTE]
> A korábbi változatokban a késések kiszámítását *határidős üzeneteknek* nevezték, a késleltetett dátum neve *határidős dátum* volt, a késleltetett tranzakcióé pedig *beállított jövőbeli tranzakció*.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>Korlátozott késések a termelési beállításokban több anyagjegyzék-szinttel
Ha több anyagjegyzék-szintet tartalmazó termelési beállításnál késéseket dolgozik, fontos megjegyezni, hogy csak a késést okozó cikk fölött közvetlenül található cikkek (az anyagjegyzék szerkezetben) lesznek frissítve a késéssel az alaptervezés futtatásakor. Az anyagjegyzék-szerkezet többi cikkér nem lesz alkalmazva a késleltetés az első alaptervezés-futtatásig, amikor a felső szintű tervezett rendelés jóvá van hagyva vagy meg van erősítve. 

Ha ezt az ismert korlátozást szeretné megkerülni akkor az anyagjegyzék-szerkezet felső részén található termelési rendelések jóváhagyása (vagy megerősítése) a következő Alaptervezés futtatása előtt elvégezhető. Ily módon a késleltetett jóváhagyott tervezett termelési rendelés késése meg lesz tartva, és a rendszer ennek megfelelően frissíti az összes mögöttes összetevőt.
A műveletüzenetek a későbbi dátumra áthelyezhető tervezett rendelések azonosítására is használhatók, az anyagjegyzék-szerkezet egyéb késései miatt.

## <a name="desired-date"></a>Kívánt dátum

A **Tervezett rendelés** oldalon a **Késések** lapon található a tervezett rendelés **Kívánt dátuma**. Egy tervezett rendelés kívánt dátuma a késések alapdátuma, amely egy számított dátum, a **Kért dátum** értékével egyezik meg, amelyet a **Nettó követelmény** értékéből számítottak. Ha a tervezett rendelés anyagjegyzéksor, termelési sor vagy kanbansor, akkor a kívánt dátum kiszámítása a **Követelmény dátuma** értékén alapul, és a kívánt dátum nem jelenik meg a **Tervezett rendelés** oldalon.

## <a name="additional-resources"></a>További erőforrások

- [Fedezeti beállítások](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]