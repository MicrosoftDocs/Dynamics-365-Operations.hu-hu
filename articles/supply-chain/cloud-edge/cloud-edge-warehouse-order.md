---
title: Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez
description: Ez a témakör a raktári rendelési funkcióval kapcsolatban tartalmaz tájékoztatást, amely a raktári mérlegegység terhelésének részeként használatos.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: bd3c72f2c008b936ceda53a3fcdde79df1e6b1b7
ms.sourcegitcommit: a21166da59675e37890786ebf7e0f198507f7c9b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/03/2021
ms.locfileid: "7471692"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Nem minden üzleti funkció teljes mértékben támogatott a nyilvános előzetes verzióban, ha a mérlegegység munkaterheléseket használja. Ha a mérlegegységeket használja, ügyeljen arra, hogy csak azokat a folyamatokat használja, amelyeket ez a témakör kifejezetten támogatottként ír le.

## <a name="what-are-warehouse-orders"></a>Mi az a raktári rendelés?

A *Raktári rendelések* olyan rendelési típus, amely a központi és mérlegegységraktárak telepítésének támogatásához használatos. Akkor kaphat és szállíthat készletet, amikor egy skálázási egységen futtat egy raktári terhelést.

A raktári rendelések mind a bejövő, mind a kimenő raktárkezelési feldolgozás részeként használatosak. A *Raktárba kiadás* folyamat részeként jön létre, amely a központon inicializálódik.
A bejövő feldolgozásnál a Warehouse Mobile App a tényleges aktuális készlet regisztrálására használható a bejövő rendelések feldolgozása során, ez elérhető a beszerzési és termelési rendelésekhez, amelyek meghatározzák a raktárkezelési folyamatok használatára engedélyezett skálázásiegység-raktárat és cikkeket.
A kimenő raktári rendelések az átszállítási és értékesítési rendelések szállítmány hullámfeldolgozásának részeként használatosak.

> [!IMPORTANT]
> A raktári rendelések csak olyan telepítésekben érhetők el, amelyek [raktárkezelési terheléseket használnak a felhő- és peremhálózati egységekhez](cloud-edge-workload-warehousing.md).

## <a name="create-an-inbound-warehouse-order"></a>Bejövő raktárrendelés létrehozása

A következő lépéseket követve hozhat létre bejövő raktári rendelést a beszerzési rendelési folyamatához.

1. Jelentkezzen be a központon futó Microsoft Dynamics 365 Supply Chain Management példányára. (Kezdeményeznie kell a *Kiadás raktárba* folyamatot, amíg be van jelentkezve a központba.)
1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. A kapcsolódó raktári rendelési sorok megtekintéséhez nyissa meg a megfelelő beszerzési rendelést, válasszon ki egy sort a **Beszerzési rendelés** sorai szakaszban, majd az eszköztáron válassza a következőt: **Raktár \> Raktári rendelés sorai**. Az összes sor megtekintéséhez menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorokhoz**.

A *Kiadás raktárba* folyamatot kötegelt feladatból is elindíthatja, ha a **Raktárkezelés > Kiadás raktárba > Beszerzési rendelések automatikus kiadása** helyre lép. A kötegelt feladat beállításakor lekérdezés alapján meghatározott beszerzésirendelés-sorokat választhat ki. Jellemző helyzet lehet egy ismétlődő kötegelt feladat, amely kiadja a következő napon várható összes visszaigazolt beszerzésirendelés-sort.

## <a name="cancel-a-warehouse-order"></a>Raktári rendelés visszavonása

A *Raktárba való kiadás* folyamat részeként a beszerzési rendelés készlettranzakciói raktári rendelésekhez kapcsolódnak, és a központ nem frissíti őket. Ha véletlenül ad ki a raktárba, vagy valamilyen más oka van a raktári rendeléssorok létrehozásának sztornírozásának, kérheti a raktári rendeléssorok érvénytelenítését.

Raktári rendelési sorok érvénytelenítéséhez kövesse az alábbi lépéseket.

1. Jelentkezzen be a központon futó Supply Chain Management példányára.
1. Menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorokhoz**.
1. Válassza ki a kívánt sort.
1. A munkaablakban válassza a **Raktári rendelési sorok visszavonása** lehetőséget.

> [!NOTE]
> A sorok érvénytelenítésére vonatkozó kérést a rendszer megtagadja minden olyan sornál, amely már visszavonásra vár, vagy amely jelenleg aktív feldolgozás alatt áll egy olyan raktárban, amely a terhelést egy mérlegegységen futtatja.

## <a name="monitor-a-warehouse-order"></a>Raktári rendelés monitorozása

A **Raktári rendelés sorai** nézetben nyomon követheti a bejövő bevételezés előrehaladását, ha áttekinti a **Bevételezésre megmaradt mennyiség** oszlopban szereplő értékeket. A Raktárkezelés mobilalkalmazás segítségével végzett munkához kapcsolódó részletek megtekintéséhez hajtsa végre az alábbi lépéseket.

- Menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorok** elemhez, és a szűrő segítségével keresse meg a keresett sorokat.
- Ugorjon a **Beszerzés és forrás \> Beszerzési rendelések \> Összes beszerzési rendelés** elemre, és nyissa meg a megfelelő beszerzési rendelést. A **Beszerzési rendelés sorai** szakaszban válasszon ki egy vagy több sort, majd az eszköztáron válassza ki a **Raktár \> Raktári bevételezések bejegyzései** elemet.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
