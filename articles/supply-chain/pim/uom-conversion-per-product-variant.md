---
title: Mértékegység-átváltás termékváltozatonként
description: Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a termékváltozatokon. Egy példát is tartalmaz a beállításra.
author: johanhoffmann
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 71d35d47a703f0931ba3b4ab5df21c7199c7ea5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429806"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Mértékegység-átváltás termékváltozatonként

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet mértékegység-átváltásokat beállítani a különféle termékváltozatokon.

A karbantartani kívánt több egyéni termék létrehozása helyett használhatja a termékváltozatokat egyetlen termék változatainak létrehozásához. Egy termékváltozat lehet például egy adott méretű és színű póló.

Korábban a mértékegységek átváltásait csak az alaptermékben lehetett beállítani. Ezért minden termékváltozat ugyanazzal az egységátváltási szabályokkal rendelkezett. Ha azonban a *Mértékegység-átváltások termékváltozatok esetén* funkció be van kapcsolva, ha a pólókat dobozban értékesítik, és a csomagolható pólók száma a pólók méretétől függ, akkor most beállíthatja a különböző pólóméretek és a csomagoláshoz használt dobozok között mértékegység-átváltásokat.

## <a name="turn-on-the-feature-in-your-system"></a>A funkció bekapcsolása a rendszerben

Ha nem látja ezt a funkciót a rendszerben, nyissa meg a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) részt, és kapcsolja be a *Mértékegység-átváltások termékváltozatok esetén* funkciót.

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>A termék beállítása egységátváltáshoz változat szerint

Termékváltozatokat csak olyan termékekhez lehet létrehozni, amelyek alaptermékek. További információ: [Alaptermék létrehozása](tasks/create-product-master.md). A *Mértékegység-átváltások termékváltozatok esetén* funkció nem érhető el a tényleges súlyú folyamatokhoz beállított termékek esetében.

A következő lépésekkel konfigurálhat egy alapterméket, amely támogatja a változatonkénti mértékegység-átalakítást.

1. Ugorjon a **Termékinformációk kezelése \> Termékek \> Alaptermékek** lehetőségre.
1. Hozzon létre vagy nyisson meg egy alapterméket, hogy a **Termék részletei** oldalra jusson.
1. Állítsa a **Mértékegység-átváltások engedélyezése** beállítást *Igen* értékre.
1. A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Mértékegység-átváltások** lehetőséget.
1. Megnyílik a **Mértékegység-átváltások** oldal. A következő lapok közül választhat:

    - **Osztályon belüli átváltások** – Akkor válassza ezt a lapot, ha az ugyanahhoz az osztályhoz tartozó mértékegységek között szeretné végrehajtani az átalakítást.
    - **Osztályok közötti átváltások** – Akkor válassza ezt a lapot, ha a különböző osztályokhoz tartozó mértékegységek között szeretné végrehajtani az átalakítást.

1. Új mértékegység-átváltás hozzáadásához kattintson az **Új** parancsra.
1. Állítsa a **Átváltás létrehozása a következőhöz:** mezőt a következő értékek egyikére:

    - **Termék** – Ha ezt az értéket választja, akkor beállíthatja a mértékegység-átváltást az alaptermékhez. Ez a mértékegység-átváltás tartalékként fog szerepelni az összes olyan termékváltozathoz, amelynél nincs beállítva mértékegység-átváltás.
    - **Termékváltozat** – Ha ezt az értéket választja, akkor beállíthatja a mértékegység-átváltást egy adott termékváltozathoz. Válassza ki a változatot a **Termékváltozat** mező segítségével.

    ![![Új mértékegység-átváltás hozzáadása](media/uom-new-conversion.png "Új mértékegység-átváltás hozzáadása")](media/uom-new-conversion.png "Adding a new unit conversion")

1. A mértékegység-átváltás beállításához használja az egyéb megadott mezőket.
1. Az új mértékegység-átalakítás mentéséhez kattintson az **OK** gombra.

> [!TIP]
> A termék vagy a termékváltozat **Mértékegység-átalakítás** oldalát a következő oldalak bármelyikéről megnyithatja:
> 
> - Termék részletei
> - Megjelent termékek részletei
> - Kiadott termékváltozatok

## <a name="example-scenario"></a>Példaforgatókönyv

Ebben a forgatókönyvben egy vállalat pólókat értékesít kicsi, közepes, nagy és extra nagy méretben. A pólót termékként határozzuk meg, a különböző méreteket pedig a termék változataiként definiáljuk. A pólók csomagolása dobozokban történik. A kis, közepes és nagy méreteknél a dobozban öt póló lehet. Az extra nagy méretnél azonban csak négy póló számára van hely a dobozban.

A vállalat nyomon szeretné követni a pólók különböző változatait *Darab* mértékegyégben, de a pólókat *Doboz* mértékegységben forgalmazza. Kis, közepes és nagy méretek esetében a készletegység és az értékesítési egység közötti átváltási arány 1 doboz = 5 darab. Az extra nagy méretnél az átváltási arány 1 doboz = 4 darab.

1. Először nyissa meg a **Mértékegység-átváltás** lapot a **Póló** termék **Termékkiadás részletei** lapjáról.
1. A **Mértékegység-átváltás** lapon állítsa be a következő mértékegység-átváltást az **Extra nagy** kiadási termékváltozatnál.

    | Mező                 | Beállítás                 |
    |-----------------------|-------------------------|
    | Átváltás létrehozása a következőhöz: | Termékváltozat         |
    | Termékváltozat       | Póló : : Extra nagy : : |
    | Kezdő egység             | Dobozok                   |
    | Szorzó                | 4                       |
    | Záró egység               | darab                  |

1. Mivel a **Kicsi**, **Közepes** és **Nagy** termékváltozatok esetében azonos a mértékegység-átváltás a *Doboz* és a *Darab* egységek között, az alapterméken meg lehet adni a mértékegység-átváltást ezekhez a termékváltozatokhoz.

    | Mező                 | Beállítás |
    |-----------------------|---------|
    | Átváltás létrehozása a következőhöz: | Termék |
    | Termék               | Póló |
    | Kezdő egység             | Dobozok   |
    | Szorzó                | 5       |
    | Záró egység               | darab  |

## <a name="using-excel-to-update-the-unit-conversions"></a>A mértékegység-átváltások frissítése az Excel programmal

Ha egy terméknek számos olyan változata van, amelyek eltérő mértékegység-átváltással rendelkeznek, akkor célszerű exportálni egy Microsoft Excel munkafüzetbe az egység konverzióit, frissíteni őket, majd újra közzéteheti őket a Dynamics 365 Supply Chain Management alkalmazásban.

Az egységek átváltásának Excel programba történő exportálásához válassza a **Mértékegység-átváltások** oldal Művelet paneljén a **Megnyitás Microsoft Office alkalmazásban** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Mértékegység kezelése](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]