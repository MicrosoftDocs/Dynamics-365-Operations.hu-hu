---
title: Karbantartási dolgozók és dolgozói csoportok
description: Ez a témakör a karbantartási dolgozókat és dolgozói csoportokat mutatja be az Eszközkezelésben.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetWorkerGroupCopyFromResourceGroup, EntAssetWorkerGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 553dce8df5e91cce58b64e340d8ff72586d8d46d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838562"
---
# <a name="maintenance-workers-and-worker-groups"></a>Karbantartási dolgozók és dolgozói csoportok

[!include [banner](../../includes/banner.md)]

 

Ez a témakör a karbantartási dolgozókat és dolgozói csoportokat mutatja be az Eszközkezelésben. A Eszközkezelés modulban hozzákapcsolhatja a karbantartási dolgozókat a munkavégzési helyszínekhez. (A munkavégzési helyszínekkel kapcsolatos további tudnivalókat lásd a [Munkavégzési helyszínek létrehozása](../functional-locations/create-functional-locations.md) című témakörben.) Ez a funkció akkor lehet hasznos, ha például egy olyan gépen szeretné ütemezni a karbantartási feladatot, amely a 01. munkavégzési helyszínen található, és a munka végrehajtásához ugyanarról a helyről kívánja hozzárendelni a karbantartási dolgozókat.

Karbantartási munkacsoportokat is létrehozhat, és társíthat hozzájuk karbantartási dolgozókat. Ez a funkció akkor hasznos, ha egyszerű munkarendelés-ütemezést végez, és karbantartási dolgozók egy csoportját szeretné egy munkarendeléshez ütemezni. A karbantartási dolgozók és karbantartási munkacsoportok segítségével beállíthatja az előnyben részesített karbantartási dolgozókat és felelős karbantartási dolgozókat. 


## <a name="create-workers"></a>Munkavállalók létrehozása

1. Válassza ki az **Eszközkezelés**\>**Beállítás**\>**Dolgozók**\>**Dolgozók**  lehetőséget.
2. Válassza ki az **Új** lehetőséget dolgozó listához adásához.
3. A **Dolgozó** mezőben válassza ki a dolgozót.
4. Állítsa az **Aktív** lehetőséget **Igen** értékre a dolgozó munkarendelésekhez való ütemezéséhez.

    Az **Általános** gyorslapon, az **Erőforrás** és **Leírás** mezők automatikusan ki vannak töltve, ha egy erőforrás ki van választva a dolgozóhoz. A **Naptár** mező automatikusan ki van töltve, ha Ön beállította a dolgozót erőforrásként, és hozzárendelt egy naptárat ahhoz az erőforráshoz az **Erőforrások** lapon (**Szervezeti adminisztráció**\> **Erőforrások** \> **Erőforrások**).

5. A **Csoportok** gyorslapon, válassza ki a **Hozzáadás lehetőséget**, majd egy karbantartási dolgozói csoportot a dolgozó számára. A dolgozók több csoporttal is társíthatók.
6. A szokásos beállításban a dolgozó csoporttal való társítása a csoport hozzáadásának dátumától hatályos, és soha nem évül el. Ez a dátum a **Hatályos** mezőben jelenik meg. A **Hatályos** mező megtekintéséhez válassza ki a **Megtekintés** \> **Összes** elemet. Ha a dolgozó csoporttal való viszonyát egy adott időszakra kell korlátozni, akkor a **Hatályos** és a **Lejárat** mezőkkel meghatározhatja az időszakot.
7. A **Munkavégzési helyszínek** gyorslapon, válassza ki a **Hozzáadás** lehetőséget, majd a munkavégzési helyszínt a karbantartási dolgozó számára. Azt is adja meg, hogy melyik hely a dolgozó elsődleges munkavégzési helyszíne.

    > [!NOTE]
    > Amikor munkavégzési helyszíneket ad hozzá egy dolgozóhoz, minden hozzájuk kapcsolódó eszköz megjelenik a különböző menüelemekben, például a **Saját aktív eszközök** és a **Saját aktív munkavégzési helyszínek**. Ezenkívül azokban az eszközkeresésekben is megjelennek, amelyek új eszköz, karbantartási kérés vagy munkarendelés létrehozásakor látszanak.

    A **Részletek** gyorslapon lévő mezők megjelenítik a karbantartási munkacsoportok számát, valamint azokat a munkavégzési helyszíneket, amelyekhez a kiválasztott karbantartási dolgozó kapcsolódik.

## <a name="create-worker-groups"></a>Dolgozói csoportok létrehozása

1. Válassza ki az **Eszközkezelés**\>**Beállítás**\>**Dolgozók**\>**Karbantartási dolgozói csoportok** lehetőséget.
2. Válassza ki az **Új** lehetőséget dolgozói csoport listához adásához.
3. A **Karbantartási dolgozói csoport** mezőbe írja be a csoport azonosítóját.
4. A **Név** mezőben adjon meg egy nevet.
5. A **Dolgozók** gyorslapon, válassza ki a **Hozzáadás** lehetőséget, majd egy karbantartási dolgozót a dolgozói csoport számára. A **Hatályos** és **Lejárat** mezőkről az előző eljárás 6. lépésében talál további információt.
6. Ha egy erőforráscsoportot a kiválasztott karbantartási dolgozói csoporthoz kell kapcsolni, válassza ki a **Másolás erőforráscsoportból** lehetőséget. A **Csoport** mezőben válassza ki azt az erőforráscsoportot, amelyből a naptár beállításait másolni szeretné. Ezután a **Dolgozói csoport** mezőben válassza ki azt a dolgozói csoportot, amelybe az erőforráscsoport naptárbeállításait másolni szeretné. Ez a lépés csak akkor szükséges, ha azt szeretné, hogy a karbantartási dolgozók a munkarendelés ütemezése során a erőforráshoz (műhelyhez) kapcsolódó naptárt használják.

    A **Részletek** gyorslapon lévő mező azoknak a karbantartási dolgozóknak a számát jeleníti meg, akik be lettek állítva a kiválasztott karbantartási dolgozói csoportban.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]