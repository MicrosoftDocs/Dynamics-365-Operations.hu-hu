---
title: Termeléstervezés
description: Ez a témakör a termelés tervezését írja le, és bemutatja, hogyan lehet módosítani a tervezett termelési rendeléseket a Tervezési optimalizálás segítségével.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: eda22aa6f1e8d665d8ef390f24b247a76d4c2956
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992395"
---
# <a name="production-planning"></a>Termeléstervezés

A tervezési optimalizálások több termelési helyzetet is támogatnak. Ha egy meglévő, beépített alaptervezési motorról tér át, fontos, hogy tisztában legyen a némiképp megváltozott viselkedéssel.

<!-- The following video gives a short introduction to some of the current capabilities. 
KFM: Link to video for production functionality, coming soon... -->

## <a name="planned-production-orders"></a>Terv. term. rendelések

Amikor az alaptervezés tervezett rendeléseket hoz létre a követelmények kielégítése érdekében, a rendelés típusát a **Tervezett rendeléstípus** mező értéke határozza meg. Ha a **Tervezett rendelés típusa** mező beállítása *Termelés*, akkor létrejönnek a tervezett termelési rendelések. Ezek a tervezett termelési rendelések az aktív anyagjegyzékről (BOM) és a kapcsolódó termelési beállításból származó útvonal-azonosítóról tartalmaznak információkat.

## <a name="requirements-from-boms"></a>Követelmények az anyagjegyzékekből

Az anyagjegyzék-adatokat figyelembe veszik az alaptervezés során. A terv kimenete tartalmazza az anyagellátást, amely fedezi a kapcsolódó termelési anyagigényt.

Az alaptervezés során az aktuális, aktív anyagjegyzék használatos a termeléshez szükséges anyagok meghatározására. Ez a lépés az anyagjegyzék-szerkezetnek a szükséges termelési rendeléshez kapcsolódó összes szintjén történik. Az anyagszükséglet kielégítése az elérhető aktuális készletből, a meglévő rendelési készletekből és a jóváhagyott tervezett rendelésekből történik. Ha bárhol további anyag szükséges, egy tervezett rendelés jön létre az igény fedezése érdekében.

## <a name="scheduling-during-firming"></a>Ütemezés megerősítés során

A tervezett termelési rendelések tartalmazzák a termelés ütemezéséhez szükséges útvonal-azonosítót. A tervezett rendelések tervezett futtatása során azonban függőben van az ütemezés támogatása. Az útvonal-azonosító a tervezett termelési rendelések ütemezésére használható a megerősítés során. Ennek megfelelően a tervezett termelési rendelések átfutási ideje eltérhet a kapcsolódó ütemezett, megerősített termelési rendelések átfutási idejétől, a következők szerint:

- **Tervezett termelési rendelés** – Az átfutási idő a kiadott termékből származó statikus átfutási időn alapul.
- **Visszaszorítású termelési rendelés** – Az átfutási idő az útvonal-információkat és a kapcsolódó erőforrásmegszorításokat használó ütemezésen alapul.

A szolgáltatások várható elérhetőségével kapcsolatos további tudnivalókat lásd a [Tervezési optimalizálás igazítási elemzés](planning-optimization-fit-analysis.md)oldalon.

Ha olyan termelési funkcióktól függ, amelyek még nem állnak rendelkezésre tervezési optimalizáláshoz, akkor továbbra is használhatja a beépített alaptervezési motort. Nincs szükség kivételre.

## <a name="delays"></a>Késések

Ha a szükséges anyag átfutási ideje hosszabb a mai dátum és az anyagszükséglet dátuma közötti időszaknál, akkor a szükséges anyag és a kapcsolódó termelési rendelés tervezett rendelése késik. Tervezett rendelések esetén a késleltetés (napokban) számítása a kiadott termék átfutási ideje alapján történik. A késleltetési adatok ezután az anyagjegyzék-szerkezet összes szintjén keresztül továbbterjednek. Így végigkövetheti a késleltetett nyersanyag kihatását a vevői értékesítési rendelésre.

## <a name="modifying-planned-orders"></a>Tervezett rendelések módosítása

Ha módosítja egy tervezett rendelés adatait, a következő üzenet jelenik meg: „Ne feledje, hogy a következő alaptervezés futtatásáig a terv többi részében nem fog tükröződni a manuális módosítások hatása a tervezett rendelésekre.”

Ha módosítani szeretné a tervezett rendelés adatait, és látni szeretné a kapcsolódó anyagkövetelmények hatását, kövesse ezeket a lépéseket.

1. Frissítse a tervezett rendelést.
2. Hagyja jóvá a tervezett rendelést.
3. Futtassa az alaptervezést.

Az alaptervezés futtatásakor nem szabad szűrőket használni, ha szerepel benne tervezett termelési rendelés. További tudnivalókat a [Szűrők](#filters) részben olvashat, a témakör későbbi részében.

> [!NOTE]
> Ha a tervezett rendelés szállítási dátumát későbbi dátumra módosították, akkor előfordulhat, hogy az igény egy új tervezett rendeléshez lesz hozzárendelve. Ez a viselkedés akkor fordul elő, amikor az új ellátási dátum késést okoz a követett igényhez, de az átfutási idő beállításai szerint a késleltetés elkerülhető.

## <a name="explosion-page"></a>Alábontás lap

Az **Alábontás** lap használatával elemezni lehet egy adott termelési rendelés vagy tervezett termelési rendelés igényét, a kapcsolódó fedezetet és az igénykövetési adatokat. Az **Alábontás** lapon az alaptervezés során frissülnek az adatok. Az információk nem frissíthetőek közvetlenül az **Alábontás** lapon.

## <a name="filters"></a><a name="filters"></a>Szűrők

A termelést is magukban foglaló tervezési eseteknél javasoljuk, hogy kerülje el a szűrt alaptervezési futtatásokat. Annak érdekében, hogy a tervezési optimalizálás a helyes eredmény kiszámításához szükséges információkat tartalmazza, minden olyan terméket bele kell foglalnia a tervezett rendelés teljes anyagjegyzék-struktúrájába, amely bármilyen kapcsolatban áll a termékekkel.

Bár a rendszer automatikusan észleli a függő gyermekeket, és bekerül az alaptervezésbe a beépített alaptervezési motor használata esetén, a tervezési optimalizálás nem végzi el ezt a műveletet.

Ha például az A termék anyagjegyzék-szerkezetében egy csavar a B termék előállítására is használatos, akkor a szűrőben szerepelnie kell az A és a B termék anyagjegyzék-szerkezetében található összes terméknek. Mivel nagyon bonyolult lehet annak biztosítása, hogy minden termék a szűrő része legyen, javasoljuk, hogy ne használjon szűrőt alaptervezési futtatásoknál termelési rendelések esetén.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]