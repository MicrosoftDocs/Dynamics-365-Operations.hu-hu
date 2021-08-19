---
title: Készletzárolás létrehozása és karbantartása
description: Ez az témakör azt mutatja be, hogyan használhat készletzárolást, amellyel megelőzheti a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d602abe4491f6cbbd0fce25a566acf97a25f3bf1e6214e95c80fda2638d14dde
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773274"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Készletzárolás létrehozása és karbantartása

[!include [banner](../../includes/banner.md)]

Ez az témakör azt mutatja be, hogyan használhat készletzárolást, amellyel megelőzheti a fizikai, aktuális készletek lefoglalását más kimenő forrásbizonylatokkal. A témakörben szereplő eljárások megkezdése előtt rendelkeznie kell egy olyan cikkel, amelyhez fizikai, aktuális készlet elérhető.

## <a name="block-inventory"></a>Készletzárolás

A következő lépésekkel lehet készletzárolási rekordot létrehozni a készlet zárolása érdekében.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Készletzárolás** lehetőségre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új zárolási rekord fejlécében állítsa a **Cikkszám** mezőt a blokkolni kívánt cikkre, és adjon meg egy leírást.
1. Az **Általános** gyorslapon a **Mennyiség** mezőben adja meg a zárolni kívánt cikkek számát.
1. A **Készletdimenziók** gyorslapon adja meg azt a telephelyet és raktárt, ahol a blokkolni kívánt cikkek jelenleg találhatók.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Készletzárolás feltételeinek frissítése

A következő lépésekkel frissítheti a készletzárolási rekordokat.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Készletzárolás** lehetőségre.
1. A lista ablaktáblán válassza ki a releváns zárolási rekordot.
1. Szerkessze a rekordot szükség szerint. Például a **Várható dátum** mező értékének módosításával érdemes jelezni, hogy a zárolt készlet a tervek szerint mikor foglalható újra. Ha a **Várt bevételezések** beállítás van kiválasztva, a dátum megjelenik a várható tranzakcióban. (A **Várt bevételezések** beállítását alapértelmezés szerint a zárolási rekord manuális létrehozása esetén választja ki a program.)
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="unblock-inventory"></a>Készletzárolás feloldása

A következő lépésekkel lehet készletzárolási rekordot eltávolítani a készlet zárolásának feloldása érdekében.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Készletzárolás** lehetőségre.
1. A lista ablaktáblán válassza ki a releváns zárolási rekordot.
1. A Műveletpanelen válassza ezután a **Törlés** elemet.
1. A rendszer felszólítja, hogy erősítse meg a műveletet. A folytatáshoz kattintson az **Igen** gombra.
1. Zárja be a lapot.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
