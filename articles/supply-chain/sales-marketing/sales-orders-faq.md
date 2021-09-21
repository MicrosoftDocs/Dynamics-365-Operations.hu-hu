---
title: Az értékesítési rendelésekkel kapcsolatos gyakori kérdések
description: Ez az oldal a Dynamics 365 Supply Chain Management értékesítési rendelésekkel kapcsolatos gyakori kérdéseket tartalmazza.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d75022dcc476052040b16c9033cf5ff2a697ae6c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476543"
---
# <a name="sales-order-faqs"></a>Értékesítési rendelés GYIK

Ez az oldal a Dynamics 365 Supply Chain Management értékesítési rendelésekkel kapcsolatos gyakori kérdéseket tartalmazza.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Kapcsolható a beszerzési rendelés egy értékesítési rendeléshez igény teljesítéséhez?

Beszerzési rendelést létrehozhat értékesítési rendelésből. További információ: [Beszerzési rendelés létrehozása értékesítési rendelésből](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order).

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>Tudom-e érvényteleníteni vagy törölni a visszárurendelést vagy az értékesítési rendelést?

Csak a *Létrehozva* állapotú értékesítési rendelések és visszárurendelések vonhatók vissza. További információkkal kapcsolatban lásd: [Visszárurendelések törlése](/dynamics365/supply-chain/service-management/cancel-return-order).

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Visszaállíthatók egy számlázott értékesítési rendelést, amely törölve lett?

Ha a számlázott értékesítési rendelés tévedésből törölve lett, visszaállíthatja, vagy megtekintheti annak adatait.

Lépjen a **Vevői számla \> Tranzakciók \> Eredeti bizonylat \> Részletek megtekintése**. Keresse meg a keresett számlát, és válassza ki, hogy megtekintse az adatait. Ezek a részletek az értékesítési rendelés hivatkozását tartalmazzák. Erről a lapról az értékesítési rendelés részleteit is elérheti.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>Hogyan törölhetem az elárvult értékesítési rendelési rekordokat?

Az elárvult értékesítési rendelések rekordjainak törléséhez futtassa az *Értékesítési rendelés törlése* ismétlődő feladatot a következő helyek valamelyikéről:

- Értékesítés és marketing \> Időszakos feladatok \> Adattisztítás \> Értékesítési rendelések törlése
- Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Adattisztítás \> Értékesítési rendelések törlése

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Van mód jutalékok kiszámítására a már feladott számlákon?

A Supply Chain Management jelenleg nem támogatja a jutalékok számítását a feladott számlákra vonatkozóan.
