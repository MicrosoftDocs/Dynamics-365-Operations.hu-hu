--- 
title: "Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből"
description: "Ez az eljárás bemutatja, hogyan hozzon létre új termékéletciklus-állapotot, amely kizárja a termékeket az Alaptervezésből és anyagjegyzékszint-számításból."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: 1685e8eb706e29ef5b195e9163bf19345fee78b6
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Termékéletciklus-állapot létrehozása a termékek kizárásához az alaptervezésből

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozzon létre új termékéletciklus-állapotot, amely kizárja a termékeket az Alaptervezésből és anyagjegyzékszint-számításból.


## <a name="create-an-obsolete-state"></a>Elavult állapot létrehozása
1. Válassza a Termékinformációk kezelése > Beállítás > Termékéletciklus állapota lehetőséget.
2. Kattintson az Új lehetőségre.
3. Az Állapot mezőben adjon meg egy értéket.
4. Az Aktív a tervezéshez mezőben várja a Nem lehetőséget.
5. A Leírás mezőben adjon meg egy értéket.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Elavult állapot társítása kiadott termékhez
1. Zárja be a lapot.
2. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
3. Rekordok kereséséhez használja a gyorsszűrőt. Végezzen szűrést a Keresési név mezőben az „M00” értékkel.
4. Kattintson a Szerkesztés lehetőségre.
5. A listában jelölje meg a kiválasztott sort.
6. A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.


