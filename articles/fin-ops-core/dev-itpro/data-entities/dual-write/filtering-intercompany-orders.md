---
title: Vállalatközi rendelések szűrése a Rendelések és az OrderLines entitások szinkronizálásának elkerülése érdekében
description: Ez a témakör leírja, hogyan lehet szűrni a vállalatközi rendeléseket, hogy a Rendelések és az OrderLines entitások ne legyenek szinkronizálva.
author: negudava
manager: tfehr
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 342db8c1b4337145bfd61f5698ff6de25434a400
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796606"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Vállalatközi rendelések szűrése a Rendelések és az OrderLines entitások szinkronizálásának elkerülése érdekében

[!include [banner](../../includes/banner.md)]

Szűrheti a vállalatközi rendeléseket, hogy a **Rendelések** és az **OrderLines** táblák ne legyenek szinkronizálva. Bizonyos esetekben a vállalatközi rendelés részletei nem szükségesek az ügyfélkezelési alkalmazásban.

A szabványos Dataverse-táblák mindegyike ki van bővítve az **IntercompanyOrder** oszlopra mutató hivatkozásokkal, és a kettős írású leképezések úgy módosulnak, hogy a szűrők további oszlopaira hivatkozzanak. Emiatt a vállalatközi rendelések már nem szinkronizálódnak. Ezzel a folyamattal elkerülhetők a szükségtelen adatok az ügyfélkezelési alkalmazásban.

1. Bővítse ki a **CDS értékesítésirendelés-fejlécek** tábláját az **IntercompanyOrder** oszlopra való hivatkozás hozzáadásával. Ez az oszlop csak vállalatközi rendeléseken van kitöltve. Az **IntercompanyOrder** oszlop a **SalesTable** táblában érhető el.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Leképezés előkészítése az oldal CDS értékesítésirendelés-fejlécek elemre való célzásához":::

2. A **CDS értékesítésirendelés-fejlécek** kiterjesztése után az **IntercompanyOrder** oszlop elérhető a leképezésben. Szűrő alkalmazása az `INTERCOMPANYORDER == ""` elemmel lekérdezési karakterláncként.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="A CDS értékesítésirendelés-fejlécek lekérdezési párbeszédpanelének szerkesztése":::

3. Bővítse ki a **CDS értékesítésirendelés-sorok** tábláját az **IntercompanyInventTransId** oszlopra való hivatkozás hozzáadásával. Ez az oszlop csak vállalatközi rendeléseken van kitöltve. Az **IntercompanyInventTransId** oszlop a **SalesLine** táblában érhető el.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Leképezés előkészítése az oldal CDS értékesítésirendelés-sorok elemre való célzásához":::

4. A **CDS értékesítésirendelés-sorok** kiterjesztése után az **IntercompanyInventTransId** oszlop elérhető a leképezésben. Szűrő alkalmazása az `INTERCOMPANYINVENTTRANSID == ""` elemmel lekérdezési karakterláncként.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="A CDS értékesítésirendelés-sorok lekérdezési párbeszédpanelének szerkesztése":::

5. Ismételje meg az 1–2. lépést az **V2 értékesítési számlafejléc** tábla kiterjesztéséhez és szűrőlekérdezés hozzáadásához. Ebben az esetben használja az `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` a szűrő lekérdezési karakterláncaként.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Leképezés előkészítése az oldal V2 értékesítési számlafejléc elemre való célzásához":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="A V2 értékesítési számlafejléc lekérdezési párbeszédpanelének szerkesztése":::

6. Ismételje meg az 3–4. lépést az **V2 értékesítési számlasor** tábla kiterjesztéséhez és szűrőlekérdezés hozzáadásához. Ebben az esetben használja az `INTERCOMPANYINVENTTRANSID == ""` a szűrő lekérdezési karakterláncaként.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="A V2 értékesítési számlasor lekérdezési párbeszédpanelének szerkesztése":::

7. Az **Ajánlatok** tábla nem rendelkezik vállalatközi kapcsolattal. Ha valaki ajánlatot hoz létre az egyik vállalatközi vevőhöz, a **CustGroup** oszlop segítségével az összes vevőt egy vevőcsoportba helyezheti. A fejlécet és sorokat a **CustGroup** oszlop hozzáadásával bővítheti, majd úgy szűrheti, hogy a csoportot ne tartalmazza.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Leképezés előkészítése az oldal CDS értékesítési ajánlatfejléc elemre való célzásához":::

8. Miután kibővítette az **Ajánlatok** entitást, alkalmazzon szűrőt `CUSTGROUP != "<company>"` lekérdezési karakterlánccal.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="A CDS értékesítési ajánlatfejléc lekérdezési párbeszédpanelének szerkesztése":::
