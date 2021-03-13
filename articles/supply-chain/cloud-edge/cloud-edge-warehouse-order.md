---
title: Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez
description: Ez a témakör a raktári rendelési funkcióval kapcsolatban tartalmaz tájékoztatást, amely a raktári mérlegegység terhelésének részeként használatos.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c04127b9fe621d962be2d7fe06358b3bd1b78916
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2021
ms.locfileid: "5105710"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Raktérkezelés rendelései felhőalapú és peremhálózat-lépték szerinti egységekhez

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Nem minden üzleti funkció teljes mértékben támogatott a nyilvános előzetes verzióban, ha a mérlegegység munkaterheléseket használja. Ha a mérlegegységeket használja, ügyeljen arra, hogy csak azokat a folyamatokat használja, amelyeket ez a témakör kifejezetten támogatottként ír le.

## <a name="what-are-warehouse-orders"></a>Mi az a raktári rendelés?

A *raktári rendelések* olyan rendelési típus, amely a központi és mérlegegységraktárak telepítésének támogatásához jött létre. Akkor kaphat készletet, amikor egy mérlegegységen futtat egy raktári terhelést. Jelenleg csak beszerzési rendelésekkel használatosak.

A raktári rendelések a raktárkezelés feldolgozásában használatosak, például amikor a raktári alkalmazás segítségével regisztrálják a tényleges aktuális készletet a bejövő beszerzési rendelések feldolgozása során. A raktári rendelések létrehozása a *raktárba való kiadás* folyamat részeként történik, amely a raktárkezelési folyamatok használatára engedélyezett mérlegegységraktárat megszabadó beszerzési rendelésekhez áll rendelkezésre.

> [!IMPORTANT]
> A raktári rendelések csak olyan telepítésekben érhetők el, amelyek [raktárkezelési terheléseket használnak a felhő- és peremhálózati egységekhez](cloud-edge-workload-warehousing.md).

## <a name="create-a-warehouse-order"></a>Raktári rendelés létrehozása

Raktári rendelés létrehozásához kövesse az alábbi lépéseket.

1. Jelentkezzen be a központon futó Microsoft Dynamics 365 Supply Chain Management példányára. (Kezdeményeznie kell a *Kiadás raktárba* folyamatot, amíg be van jelentkezve a központba.)
1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. A kapcsolódó raktári rendelési sorok megtekintéséhez nyissa meg a megfelelő beszerzési rendelést, válasszon ki egy sort a **Beszerzési rendelés** sorai szakaszban, majd az eszköztáron válassza a következőt: **Raktár \> Raktári rendelés sorai**. Az összes sor megtekintéséhez menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorokhoz**.

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

A **Raktári rendelés sorai** nézetben nyomon követheti a bejövő bevételezés előrehaladását, ha áttekinti a **Bevételezésre megmaradt mennyiség** oszlopban szereplő értékeket. A raktári alkalmazás segítségével végzett munkához kapcsolódó részletek megtekintéséhez hajtsa végre az alábbi lépéseket.

- Menjen a **Raktárkezelés \> Lekérdezések és jelentések \> Raktári rendelési sorok** elemhez, és a szűrő segítségével keresse meg a keresett sorokat.
- Ugorjon a **Beszerzés és forrás \> Beszerzési rendelések \> Összes beszerzési rendelés** elemre, és nyissa meg a megfelelő beszerzési rendelést. A **Beszerzési rendelés sorai** szakaszban válasszon ki egy vagy több sort, majd az eszköztáron válassza ki a **Raktár \> Raktári bevételezések bejegyzései** elemet.
