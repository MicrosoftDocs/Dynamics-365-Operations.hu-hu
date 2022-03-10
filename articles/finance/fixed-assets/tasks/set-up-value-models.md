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
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be3b5578bd6509859c36f6a50ea9730e9ef1780e
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7890712"
---
# <a name="set-up-value-models"></a>Értékmodellek beállítása

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Ez az eljárás bemutatja, hogyan hozzon létre új tárgyieszköz-könyvet, és hogyan társítsa azt tárgyieszköz-csoporthoz.

## <a name="create-a-book"></a>Könyv létrehozása
1. Lépjen a **Tárgyi eszközök \> beállítási \> könyvei elemre**.
2. Válassza az **Új** lehetőséget.
3. A **Könyv** mezőbe adjon meg egy értéket.
4. A **Leírás** mezőben adjon meg egy értéket.
5. Állítsa az **Értékcsökkenés kiszámítása beállítást Igen** **értékre.**

    Ha **az Értékcsökkenés kiszámítása** beállítás Igen értékre van állítva, **a kapcsolódó** eszközkönyv az értékcsökkenési javaslatokban lesz feltüntetve. Ha Nem értékre van **állítva**, az eszközkönyv nem lesz automatikusan értékcsökkentve.

6. Az **Értékcsökkenési profil** mezőben adjon meg vagy válasszon ki egy értéket.

    * Az alternatív értékcsökkenési profil az értékcsökkenés alternatív módszereként is ismert. Az értékcsökkenési javaslat akkor vált erre a profilra, ha az alternatív profil az alapértelmezett értékcsökkenési profillal megegyező, vagy annál nagyobb értékcsökkenési összeget eredményez.
    * A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén. Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.
    * Ha az **Értékcsökkenési korrekciók létrehozása alapkorrekciókkal lehetőséget** választja, az értékcsökkenési korrekciók automatikusan létrejönnek az eszköz értékének frissítésekor. Ellenkező esetben a frissített eszközérték csak a jövőbeli értékcsökkenési számításokat érinti.

7. Állítsa az **Értékcsökkenési korrekciók létrehozása alapkorrekcióval** beállítást Igen **értékre**.

    * Alapértelmezés szerint a tárgyieszköz-könyvtranzakciók a főkönyvbe kerülnek. Letilthatja azonban a könyvelést a könyv főkönyvi könyvelésében, ha a **Könyvelés főkönyvbe** beállítást Nem beállításra **állítja.** A főkönyvbe nem feladott könyveket általában adóbevallásra használják. Ez a beállítás nagyobb rugalmasságot biztosít az eszközkönyv előzményügyletek törléséhez, mivel a tranzakciók nincsenek elkötelezve a főkönyvhöz.
    * Alapértelmezés szerint a **Könyvelési réteg** mező az Aktuális rétegre van állítva, **ha a könyvet a** főkönyvbe könyvelik, és **Nincs**, ha a könyvet nem könyvelik a főkönyvbe. Frissítse a Könyvelési réteg mező értékét, **ha** a könyv tranzakcióit egy másik rétegbe kell könyvelni.

8. Számítsa ki a pozitív értékcsökkenést.

    * Alapértelmezés szerint a **Pozitív értékcsökkenés kiszámítása beállítás Nincs** értékre van **állítva.** Ez a beállítás azt jelzi, hogy az értékcsökkenés jóváírja a kiválasztott eszközkönyvet. Ezenkívül a **Beszerzési árnál magasabb nettó könyv szerinti érték engedélyezése** és Negatív nettó könyv szerinti érték engedélyezése beállítás egyaránt Nem **értékre** van állítva, **és a beállítások** egymástól függetlenül módosíthatók. 
    * A pozitív értékcsökkenés kiszámításához állítsa a **Pozitív értékcsökkenés kiszámítása beállítást Igen** **értékre**. Ez a beállítás azt jelzi, hogy az értékcsökkenés megterheli a tárgyieszköz-könyvet. Ha a **Pozitív értékcsökkenés kiszámítása beállítás Igen** értékre van **állítva, a Nettó könyv szerinti érték engedélyezése** magasabb, mint a beszerzési ár **és a Negatív nettó könyv szerinti érték engedélyezése beállítás automatikusan Igen** **értékre** lesz állítva, **és** zárolva lesznek. Ez a zárolás segít biztosítani, hogy a pozitív értékcsökkenés csak a negatív könyv szerinti értékkel (hitel) rendelkező tárgyi eszközökre vonatkozjon. 

10. A **Naptár** mezőben adjon meg vagy jelöljön ki egy értéket.

    A származtatott könyvek tranzakcióinak feladása egyszerre különböző könyvekbe történik. A tranzakció létrehozása az elsődleges könyvvel történik, feladás közben pedig a tranzakció pontos másolata kerül feladásra a származtatott könyvbe. A származtatott könyvbeli tranzakcióknál nincs újraszámítás, így értékcsökkenési tranzakciókhoz ezeket nem szabad használni.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Társítsa a könyvet egy tárgyieszköz-csoporthoz

1. Válassza **a Tárgyieszköz-csoportok** lehetőséget.
2. A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket.
3. Az **Élettartam** mezőbe írjon be egy számot.

    * Az értékcsökkenési időszakok kiszámítása az eszköz élettartamának megadása után történik.
    * Az értékcsökkenési konvenciót az adózási céloknak megfelelően lehet beállítani.
    * A lízingekhez társított tárgyi eszközök esetében az élettartam mező értékét **felülírja** az eszközkönyvben és az eszköz hasznos élettartama alatt a lízingidő kisebb része. Ha a **tulajdonjog átruházása** opció igen értékre van állítva **a** lízingkönyvhöz, az élettartam mező értéke **mindig az eszköz hasznos élettartama** lesz.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
