---
title: Feladatok beállítása a Feladatkezelésben
description: Ez a cikk bemutatja a feladatoknak a Microsoft Feladatkezelésben való beállítását Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a38cc2e36c24ddbfe0d8b2886301c108599ab25
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745420"
---
# <a name="set-up-tasks-in-task-management"></a>Feladatok beállítása a Feladatkezelésben

[!INCLUDE [PEAP](../includes/peap-1.md)]

A Microsoft Dynamics 365 Human Resources 10.0.30-as verzió előtti verzióiban a feladatok szerkesztésére csak a feladatot tartalmazó ellenőrzőlistákon lehet egyenként szerkeszteniük a feladatot. Az Emberi erőforrások 10.0.30 verzióban azonban a felhasználók kiválaszthatja a szerkesztett feladatok kezelését. Ha egy szerkesztett feladat egy ellenőrzőlistán van, **·** **·** **akkor** be kell választani a Feladatkezelés frissítése engedélyezése lehetőséget az Emberi erőforrások megosztott paraméterei lap Feladatkezelés lapján, hogy az ellenőrzőlista használni képes legyen a szerkesztett feladat használatára.

[![Feladatkezelés frissítési beállításának engedélyezése az Emberi erőforrások megosztott paraméterei oldalon](./media/task-update.png)](./media/task-update.png)

Ha a feladatok szerkesztését az összes társított ellenőrzőlista-feladatra szeretné alkalmazni, akkor a feladattárban található feladat és az ellenőrzőlistán található feladat között már léteznie kell kapcsolatnak. Lehetőséget adott a tárfeladat és az ellenőrzőlista-feladat közötti kapcsolat létrehozására.

A feladatokat egyenként is létre lehet hozni, majd újra fel lehet használni őket több ellenőrzőlistán. Feladat létrehozásához válassza az Új **lehetőséget** **a** Berakodva beállítási lapon, a Feladatok **lapon.**

## <a name="set-up-tasks"></a>Feladatok beállítása

Ha egy létrehozott feladatot több ellenőrzőlistához szeretne hozzárendelni, válassza ki a feladatot, **majd válassza az Alkalmazva a menü ellenőrzőlistákra** parancsát.

Közvetlenül is hozzá lehet adni feladatokat az ellenőrzőlistához. Feladat **feladatnak** **az ellenőrzőlistához való hozzáadásához hozzon létre egy új ellenőrzőlistát az Ellenőrzőlista** lapon, vagy hozza létre a feladatot egy meglévő ellenőrzőlistához, vagy vegye fel a feladatot egy meglévő ellenőrzőlistához.

Tárfeladat szerkesztéséhez válassza a Feladattár menü **Szerkesztés** parancsát. Ha a feladat bármilyen ellenőrzőlistához hozzá van társítva, ezek az ellenőrzőlisták megjelennek **a Feladat szerkesztése lapon**. Ha azt szeretné, hogy az ellenőrzőlisták bármelyik feladatának frissüljön a szerkesztéssel, jelölje ki ezeket az ellenőrzőlistát az **Alkalmaz az ellenőrzőlistákra szakaszban**.

Ha törölni szeretné a feladatokat a feladattárból, válassza a Törlés **lehetőséget**. Ha a feladat ellenőrzőlistához van társítva, ez a művelet nem törli a feladatot az ellenőrzőlistán. Egy feladatnak az ellenőrzőlistán való eltávolításához külön műveletre van szükség.

### <a name="set-up-checklists"></a>Ellenőrzőlisták beállítása

Az ellenőrzőlista feladatok egy csoportja. Annyi ellenőrzőlistát hozhat létre, amennyit csak szeretne, és ugyanazt a feladatot több ellenőrzőlistához rendelheti hozzá. Ellenőrzőlista létrehozásakor meg kell adnia egy tulajdonost és egy naptárat.

Új feladat ellenőrzőlistán való létrehozásához válassza a feladat menüsor **Új** parancsát. Új feladat létrehozásakor lehetőség van arra, hogy a feladatot hozzáadja a feladattárhoz, hogy több ellenőrzőlista között meg legyen osztva. Ha a feladatot hozzá szeretne adni a feladattárhoz, **a** Feladat alkalmazása tárra beállítást Igen beállításra kell **állítania**. Ha úgy dönt, hogy hozzáadja a feladatot a feladattárhoz, **akkor** a feladatot egyidejűleg más ellenőrzőlistákhoz is hozzáadhatja, ehhez jelölje ki azokat az ellenőrzőlistát az Ellenőrzőlistákra területen. Ha úgy dönt, hogy nem adja hozzá a feladatot a feladattárhoz, akkor a feladat csak a létrehozási hely ellenőrzőlistán fog létezni.

Az ellenőrzőlista egy feladatának szerkesztéséhez válassza **a** Feladat menü Szerkesztés parancsát. Ha a feladat bármilyen ellenőrzőlistához hozzá van társítva, ezek az ellenőrzőlisták megjelennek **a Feladat szerkesztése lapon**. Ha azt szeretné, hogy a többi ellenőrzőlistán található feladatok bármelyike frissüljön a szerkesztéssel, jelölje ki ezeket az ellenőrzőlistát az **Alkalmaz az ellenőrzőlistákhoz szakaszban**.

Ha el szeretne távolítani feladatokat egy ellenőrzőlistán, válassza az Eltávolítás **lehetőséget**. Ez a művelet eltávolítja a feladatokat az ellenőrzőlistán. Nem törli azonban a feladatokat a feladattárból. Ha törölni szeretné a feladatokat a feladattárból, nyissa meg **a** Feladattár lapot, és válassza a Törlés **lehetőséget**.
