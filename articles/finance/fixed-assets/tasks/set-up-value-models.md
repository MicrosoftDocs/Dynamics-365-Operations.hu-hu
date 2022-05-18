---
title: Értékmodellek beállítása
description: Ez az eljárás bemutatja, hogyan hozzon létre új tárgyieszköz-könyvet, és hogyan társítsa azt tárgyieszköz-csoporthoz.
author: moaamer
ms.date: 12/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71d256b600956a4e525cde626c958713f6258f5a
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727061"
---
# <a name="set-up-value-models"></a>Értékmodellek beállítása

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Ez az eljárás bemutatja, hogyan hozzon létre új tárgyieszköz-könyvet, és hogyan társítsa azt tárgyieszköz-csoporthoz.

## <a name="create-a-book"></a>Könyv létrehozása
1. Ugrás a Tárgyi **eszközök – Beállítás \> könyvekhez \>**
2. Válassza az **Új** lehetőséget.
3. A Könyv **mezőbe** írjon be egy értéket.
4. A **Leírás** mezőben adjon meg egy értéket.
5. Állítsa Az Értékcsökkenés **számítása lehetőséget** Igen **beállításra**.

    Ha az **Értékcsökkenés számítása** beállítás **Igen**, az értékcsökkenési javaslatokban szerepelni fog a kapcsolódó eszközkönyv. Ha nemre van **állítva**, akkor az eszközkönyv értékcsökkenése nem lesz automatikus.

6. Az Értékcsökkenési **profil mezőben** adjon meg vagy válasszon ki egy értéket.

    * Az alternatív értékcsökkenési profil az értékcsökkenés alternatív módszereként is ismert. Az értékcsökkenési javaslat akkor vált erre a profilra, ha az alternatív profil az alapértelmezett értékcsökkenési profillal megegyező, vagy annál nagyobb értékcsökkenési összeget eredményez.
    * A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén. Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.
    * Ha az Értékcsökkenés-helyesbítések **létrehozása az alaphelyesbításokkal** lehetőséget választja, az eszköz értékének frissítése esetén automatikusan létrejönnek az értékcsökkenési helyesbítések. Ellenkező esetben a frissített eszközérték csak a jövőbeli értékcsökkenési számításokat érinti.

7. Állítsa Az Értékcsökkenés-helyesbítések **létrehozása az alaphelyesbbséggel** beállítást Igen **beállításra**.

    * Alapértelmezés szerint a tárgyieszközkönyv-tranzakciókat a program feladja a főkönyvbe. A könyv főkönyvbe **való** feladását azonban letilthatja, ha a Feladás a főkönyvbe lehetőséget a Nem beállításra **választja**. A főkönyvbe fel nem adott könyveket általában adóbevallásra használják. Ez a beállítás nagyobb rugalmasságot ad az eszközkönyv előzménytranzakcióinak törléséhez, mivel a tranzakciók még nincsenek véglegesve a főkönyvben.
    * Alapértelmezés szerint a **Feladási** **·** **réteg** mező az Aktuális réteg mezőre van állítva, ha a könyvet fel kell adja a főkönyvbe, és Nincs, ha a könyv nincs feladva a főkönyvbe. A Feladási réteg mező értékének **frissítése**, ha a könyv tranzakcióit más rétegbe kell feladva.

8. Pozitív értékcsökkenés számítása.

    * Alapértelmezés szerint a Pozitív **értékcsökkenés** számítása beállítás Nem beállítás **van megjelölve**. Ez a beállítás azt jelzi, hogy az értékcsökkenés követel lesz a kiválasztott eszközkönyvben. Ezen kívül a **Beszerzési** **·** **árnál** nagyobb nettó könyvérték engedélyezése és a Negatív nettó könyvkönyvi érték engedélyezése beállítás is Nem értékre van állítva, és a beállítások egymástól függetlenül módosíthatók. 
    * A pozitív értékcsökkenés kiszámításához állítsa Igen **beállításra a Pozitív** értékcsökkenés számítása **beállítást**. Ez a beállítás azt jelzi, hogy az értékcsökkenés megterheli a tárgyieszközkönyvet. **Ha a Pozitív értékcsökkenés számítása** **beállítás** Igen értékre van állítva, **·** **a Beszerzési árnál nagyobb nettó könyv szerinti érték engedélyezése és a Negatív nettó könyv szerinti** **érték** engedélyezése beállítás automatikusan Igen értékre lesz állítva, és zárolva lesz. Ez a zárolás gondoskodik arról, hogy csak a negatív könyv szerinti értékkel (követel) beszerzett tárgyi eszközökre legyen alkalmazva pozitív értékcsökkenés. 

10. A Naptár **mezőben** adjon meg vagy válasszon ki egy értéket.

    A származtatott könyvek tranzakcióinak feladása egyszerre különböző könyvekbe történik. A tranzakció létrehozása az elsődleges könyvvel történik, feladás közben pedig a tranzakció pontos másolata kerül feladásra a származtatott könyvbe. A származtatott könyvbeli tranzakcióknál nincs újraszámítás, így értékcsökkenési tranzakciókhoz ezeket nem szabad használni.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Társítsa a könyvet egy tárgyieszköz-csoporthoz

1. Válassza ki **a tárgyieszköz-csoportokat**.
2. A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.
3. Az Élettartam **mezőbe** írjon be egy számot.

    * Az értékcsökkenési időszakok kiszámítása az eszköz élettartamának megadása után történik.
    * Az értékcsökkenési konvenciót az adózási céloknak megfelelően lehet beállítani.
    * **A** bérletekkel kapcsolatos tárgyi eszközök esetén az Élettartam mező értékét felülírja az eszközkönyvben és az eszköz hasznos élettartamában a kisebb bérleti szerződési időtartam. **Ha a tulajdonosátadási** **beállítás** Igen értékre van állítva a bérleti könyvhöz, **az** Élettartam mező értéke mindig az eszköz hasznos élettartamának lesz.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
