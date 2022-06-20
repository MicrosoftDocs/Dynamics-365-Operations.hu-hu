---
title: Készletzárolás létrehozása és karbantartása
description: Ez a témakör leírja, hogyan lehet készletzárolást használni annak megakadályozására, hogy más kimenő forrásdokumentumok lefoglalják az aktuális készletet.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba95b689bedfc76598dfa81548a074f4fb7c833a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859343"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Készletzárolás létrehozása és karbantartása

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogyan lehet készletzárolást használni annak megakadályozására, hogy más kimenő forrásdokumentumok lefoglalják az aktuális készletet. A cikk eljárásait csak akkor kezdheti el, ha van olyan cikk, amely számára elérhető tényleges aktuális készlet.

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
