---
title: Értékmodellek beállítása
description: Ez az eljárás bemutatja, hogyan hozzon létre új tárgyieszköz-könyvet, és hogyan társítsa azt tárgyieszköz-csoporthoz.
author: moaamer
ms.date: 08/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46c26e5fad3c5c60d87c2fea2b29043c69b82b5d
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344658"
---
# <a name="set-up-value-models"></a>Értékmodellek beállítása

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]


Ez az eljárás bemutatja, hogyan hozzon létre új tárgyieszköz-könyvet, és hogyan társítsa azt tárgyieszköz-csoporthoz. Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.

## <a name="create-a-book"></a>Könyv létrehozása
1. Nyissa meg a következőt: Tárgyi eszközök > Beállítás > Könyvek.
2. Kattintson az Új lehetőségre.
3. A Könyv mezőben adjon meg egy értéket.
4. A Leírás mezőben adjon meg egy értéket.
    * Az Értékcsökkenés kiszámítása lehetőség kiválasztása esetén a társított eszközkönyv bekerül az értékcsökkenési javaslatokba. Ellenkező esetben az eszközkönyv értékcsökkenése nem lesz automatikus.  
5. Válassza az Igen lehetőséget az Értékcsökkenés számítása mezőben.
6. Az Értékcsökkenés mezőben adjon meg vagy válasszon ki egy értéket.
    * Az alternatív értékcsökkenési profil az értékcsökkenés alternatív módszereként is ismert. Az értékcsökkenési javaslat akkor vált erre a profilra, ha az alternatív profil az alapértelmezett értékcsökkenési profillal megegyező, vagy annál nagyobb értékcsökkenési összeget eredményez.  
    * A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén. Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.  
    * Az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával lehetőség kiválasztása esetén a rendszer automatikusan létrehozza az értékcsökkenés-kiigazítást az eszköz értékének frissítésekor. Ellenkező esetben a tárgyi eszköz frissített értéke csak az ezt követő értékcsökkenés számításokra lesz kihatással.  
7. Az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával mezőben válassza az Igen lehetőséget.
    * Alapértelmezés szerint a tárgyi eszközök tranzakciói a főkönyvbe kerülnek feladásra. A főkönyvbe történő feladás a könyvnél letiltható, ha a Feladás a főkönyvbe mezőt Nem értékre állítja. A nem a főkönyvbe feladott könyveket általában adóbevallási célokra használják. Ez további rugalmasságot biztosít az eszközkönyv előzménytranzakcióinak törléséhez, mivel ezek így nem kerültek rögzítésre a főkönyvbe.  
    * A feladási réteg alapértelmezése az Aktuális réteg, ha a könyv feladásra kerül a főkönyvbe, és Nincs, ha nem kerül feladásra. Frissítse a Feladási réteget, ha a könyvhöz kapcsolódó tranzakciókat eltérő rétegbe szeretné feladni.  
8. A Naptárak mezőben adjon meg vagy válasszon ki egy értéket.
    * A származtatott könyvek tranzakcióinak feladása egyszerre különböző könyvekbe történik. A tranzakció létrehozása az elsődleges könyvvel történik, feladás közben pedig a tranzakció pontos másolata kerül feladásra a származtatott könyvbe. A származtatott könyvbeli tranzakcióknál nincs újraszámítás, így értékcsökkenési tranzakciókhoz ezeket nem szabad használni.  

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Társítsa a könyvet egy tárgyieszköz-csoporthoz
1. Kattintson a Tárgyieszköz-csoportok elemre.
2. A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.
3. Adjon meg egy számot az Élettartam mezőben.

  - Az értékcsökkenési időszakok kiszámítása az eszköz élettartamának megadása után történik.  
  - Az értékcsökkenési konvenciót az adózási céloknak megfelelően lehet beállítani.
  - A lízinghez kapcsolódó befektetett eszközök esetében a **Szolgáltatási élettartam** mezőben szereplő értéket felülírja az eszközkönyvben szereplő lízing futamideje vagy az eszköz hasznos élettartama közül a kisebbik. Ha a **Tulajdonjog átadása** mező a lízingkönyv esetében **Igen**-re van állítva, a **Használati idő** mezőben szereplő érték mindig az eszköz hasznos élettartama lesz.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
