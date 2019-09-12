---
title: Engedélyek létrehozása, amelyek birtokában mások nevében lehet termékeket rendelni
description: Ez a témakör bemutatja, hogyan adhat engedélyt dolgozóknak más dolgozók nevében beszerzési igénylésének elkészítésére.
author: mkirknel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: baf39040bef2ccd0c643ce0d034348807ecdc50c
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914798"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Engedélyek létrehozása, amelyek birtokában mások nevében lehet termékeket rendelni

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a témakör bemutatja, hogyan adhat engedélyt dolgozóknak más dolgozók nevében beszerzési igénylésének elkészítésére. Más szóval a beszerzési igénylés „készítő” létrehozhat igénylést másik „kérelmező”-nek. AZ eljárás azt is megmutatja, hogyan adjon dolgozói engedélyeket cikkek és szolgáltatások megrendelésére különböző jogi személyek vagy üzemi egységek esetén. Általában a beszerzési vezető végzi el ezeket a feladatokat. Ezt a folyamatot az USMF bemutatócégnél vagy a saját adataiban is használhatja.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Adjon engedélyt, hogy bevihessen beszerzési igénylést egy másik dolgozó nevében.
1. A navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás> Beállítás > Irányelvek > Beszerzési igénylési engedélyek** elemre. Győződjön meg arról, hogy az **Aktuális nézet** mező értéke **Készítő által** értékre van állítva. A bal oldali ablakban található lista mutatja azokat a személyeket, akik kaphatnak engedélyt más felhasználók nevében igénylésének elkészítésére.  
2. Válassza ki azt a személyt, akinek az engedélyt adni akarja (a készítő).
3. Válassza a **Hozzáadás** lehetőséget.
4. Keresse meg és válassza ki a személyt, amelyet kérelmezőként kíván hozzáadni.
    - A kérelmező az a személy, aki a készítő nevében igényléseket hozhat létre.  
    - Az  **Engedélyezés** mezőben válassza a **Specifikus** lehetőséget, ha a készítőnek képesnek kell lennie a kijelölt dolgozó nevében beszerzési igénylést készítenie. Válassza a **Jelentés** lehetőséget, ha a készítő számára lehetséges kell legyen, hogy az összes olyan dolgozó nevében készíthessen beszerzési igénylést, akik az adott dolgozónak jelentenek.  
5. Adjon meg egy dátumot az **Érvényesség** mezőben.
6. A **Lejárat ideje** mezőben adjon meg egy dátumot.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Tekintse át azokat a készítőket, akik engedéllyel rendelkeznek az kijelölt dolgozó nevében történő beszerzési igénylések létrehozásához.
1. Az **Aktuális nézet** mezőben, válassza a **Kérelmező által** lehetőséget. Ezt a nézet mutatja azoknak a készítőknek a listáját, akik engedélyt kaptak beszerzési igények létrehozására egy adott dolgozó nevében.  
2. Használja a Gyors Szűrést, hogy megtalálja azt a dolgozót, akit most adott hozzá kérelmezőként.
3. Válassza ki a kérelmezőt. A Készítő lista azokat az embereket mutatja, akik engedéllyel rendelkeznek a bal oldali ablakban kiválasztott kérelmező nevében történő cikk rendeléshez.  További készítőknek itt is hozzáadhat. Ez a nézet lehetővé teszi a kérelmező engedély igénylés kiosztására, hogy igénylést hozhasson létre olyan jogi személyek és üzemi egységek nevében, amelyek nem az illető elsődleges jogi személye vagy üzemi egysége.  

