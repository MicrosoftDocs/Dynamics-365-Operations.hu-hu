---
title: Beszerzési katalógus létrehozása
description: Ez a témakör a beszerzési katalógus létrehozásának lépéseit mutatja be.
author: Henrikan
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef3747874d43143925bd08dbecc2d60f4e38701a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565423"
---
# <a name="create-a-procurement-catalog"></a>Beszerzési katalógus létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakör a beszerzési katalógus létrehozásának lépéseit mutatja be. Ezt a feladatot tipikusan egy beszerzési szakember végzi el. Azt is megtudhatja, hogy hogyan használhatják az alkalmazottak a katalógust egy igénylést létrehozásakor. Katalógus létrehozása előtt már kell egy beszerzési kategória hierarchiával rendelkeznie a rendszerben. Az új katalógussal örökli a hierarchiát, minden olyan termékkel együtt, ami a hierarchiában benne van. Használhatja ezt a segédletet az USMF bemutató adatok vállalatban, ahol a beszerzési kategóriák hierarchiája rendelkezésre áll, ugyanúgy, mint az eljárásban használt példák.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Győződjön meg arról, hogy létezik a beszerzési kategóriák hierarchiája
1. Menjen a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Beszerzési kategóriák** menübe. Egy beszerzési kategória hierarchia elérhető az USMF bemutató adatok vállalatnál és az **Irodai gépek/Számítógépek** kategóriához termékek lettek hozzáadva. Ha ezt a folyamatot feladat-útmutatóként használja, szüksége lehet az útmutató feloldására a kategóriák kereséséhez. Ha a hierarchia nem volt elérhető, hozzon létre egyet az **Új** gombra kattintva. Ez csak egyszer lehetséges.  
2. Zárja be a lapot.

## <a name="create-a-catalog"></a>Katalógus létrehozása
1. Menjen a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Katalógusok > Beszerzési katalógusok** menübe.
2. Az **Új beszerzési katalógus** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. Írjon be egy értéket a **Név** mezőbe.
4. Válassza ki az **OK** lehetőséget.
5. A fán, nyissa ki a **CORP PROCUREMENT CATEGORIES** pontot.
6. A fán, nyissa ki az **OFFICE MACHINES** pontot.
7. A fán, válassza a **Computers** pontot.

  - A beszerzési kategóriából származó termékek megjelennek a listában. Ha szeretne terméket hozzáadni a kategóriához, akkor ezt a **Beszerzési kategóriák hierarchiája** lapon vagy a **Cikk részletei** lapon teheti meg.  
  - Az **Alapértelmezett** frissítés típus meghatározza, hogy az új termékek amelyek hozzá lettek adva a beszerzési kategóriák hierarchiájához azonnal jelenjenek meg a katalógusban. Ha a frissítés típusa **Dinamikus**, a módosítások azonnal megjelennek. Ha a frissítés típusa **Statikus**, az új termékek csak azoknak az emberek számára fog megjelenni, akik az újra kiadott katalógust használják. A **Közzététel** művelet a Művelet ablakban érhető el az oldal tetején. Ha termékek lettek eltávolítva a beszerzési kategóriák hierarchiájából, a változás azonnal látható, az **Alapértelmezett** frissítés típusától függetlenül.  

8. A műveletpanelen jelölje ki a **Kategórianavigáció** beállítást, és győződjön meg arról, hogy az **Engedélyezés** be van jelölve.
9. Válassza a **Katalógus aktiválása** lehetőséget.
10. Zárja be a lapot.

## <a name="make-the-catalog-visible"></a>Tegye láthatóvá a katalógust
1. Válassza a **Navigációs ablaktábla > Modulok > Beszerzés és forrás> Beállítás > Irányelvek > Beszerzési irányelvek** lehetőséget.
2. Válassza az **USMF Beszerzési Irányelvet**. Ki kell választania a beszerzési irányelvet ahhoz jogi személyhez amihez a dolgozó csatlakozik és aminek a felhasználói profilja termékek rendelésére engedélyezett. A USMF bemutató adatokban, az Admin felhasználó a **Julia Funderburk** nevű dolgozóhoz van csatlakoztatva és ő rendeli meg a termékeket az USMF-ben alapértelmezés szerint.  
3. Válassza ki a most létrehozott katalógust.
4. Válassza ki az **OK** lehetőséget.

## <a name="use-the-catalog"></a>Használja a katalógust
1. Ugorjon a **navigációs panel > Modulok >Beszerzés és forrás > Beszerzési igénylések > Minden beszerzési igénylés** pontra.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Név** mezőbe.
4. Válassza ki az **OK** lehetőséget.
5. Válassza a **Termékek hozzáadása** lehetőséget.
6. Keresse meg és jelölje ki a kívánt rekordot a listán. Használhatja a bal oldalon található kategóriahierarchiát vagy a lista tetején található szűrőt a termékek szűréséhez.  
7. Válassza a **Hozzáadás a sorokhoz** lehetőséget.
8. Válassza ki az **OK** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]