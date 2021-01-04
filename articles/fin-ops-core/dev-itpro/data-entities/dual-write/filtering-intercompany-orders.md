---
title: Vállalatközi rendelések szűrése a Rendelések és a RendelésiSorok szinkronizálásának elkerülése érdekében
description: Ez a témakör a vállalatközi rendelések szűrését mutatja be a Rendelések és a RendelésiSorok szinkronizálásának elkerülése érdekében.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 6c5e1e2467673badd20366d3bd8e1b93b8078b26
ms.sourcegitcommit: 0eb33909a419d526eb84b4e4b64d3595d01731ef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4701033"
---
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a>Vállalatközi rendelések szűrése a Rendelések és a RendelésiSorok szinkronizálásának elkerülése érdekében

[!include [banner](../../includes/banner.md)]

Vállalatközi rendeléseket szűrheti a **Rendelések** és a **RendelésiSorok** szinkronizálásának elkerülése érdekében. Bizonyos esetekben a vállalatközi rendelés részletei nem szükségesek az ügyfélkezelési alkalmazásban.

A szabványos Common Data Service entitások mindegyike ki van bővítve az **IntercompanyOrder** mezőre mutató hivatkozásokkal, és a kettős írású leképezések úgy módosulnak, hogy a szűrők további mezőire hivatkozzanak. Az eredmény az, hogy a vállalatközi rendelések szinkronizálása már nem történik meg. Ezzel a folyamattal elkerülhetők a szükségtelen adatok az ügyfélkezelési alkalmazásban.

1. Hivatkozás hozzáadása a **Vállalatközi rendelés** **CDS értékesítésirendelés-fejlécek** elemhez. Csak vállalatközi rendeléseken van feltöltve. Az **IntercompanyOrder** mező a **SalesTable** táblában érhető el.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz, SalesOrderHeader":::
    
2. A **CDS Sales Order Headers** kiterjesztése után az **IntercompanyOrder** mező elérhető a leképezésben. Szűrő alkalmazása az `INTERCOMPANYORDER == ""` elemmel lekérdezési karakterláncként.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Értékesítési rendelések fejlécei, lekérdezés szerkesztése":::

3. Hivatkozás hozzáadása az **IntercompanyInventTransId** és a **CDS értékesítésirendelés-sorok** elemekhez.  Csak vállalatközi rendeléseken van feltöltve. Az **InterCompanyInventTransID** mező a **SalesLine** táblában érhető el.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz, SalesOrderLine":::

4. A **CDS értékesítésirendelés-sorok** kiterjesztése után az **IntercompanyInventTransId** mező elérhető a leképezésben. Szűrő alkalmazása az `INTERCOMPANYINVENTTRANSID == ""` elemmel lekérdezési karakterláncként.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Értékesítési rendelési sorok, lekérdezés szerkesztése":::

5. Az **Értékesítési számlafejléc V2** és az **Értékesítési számlasorok V2** elemeket bővítse ki, ugyanúgy, ahogy a Common Data Service entitásokat is kiterjesztette az 1. és 2. lépésben. Ezután adja hozzá a szűrőlekérdezéseket. A **V2 értékesítési számlafejléc** szűrőkarakterlánca `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`. A **V2 értékesítési számlasorok** szűrőkarakterlánca `INTERCOMPANYINVENTTRANSID == ""`.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz,Értékesítési számlafejlécek":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Értékesítési számlák fejlécei, lekérdezés szerkesztése":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Értékesítési számlasorok, lekérdezés szerkesztése":::

6. Az **Ajánlatok** entitás nem rendelkezik vállalatközi kapcsolattal. Ha valaki ajánlatot hoz létre az egyik vállalatközi vevőhöz, a **CustGroup** mező segítségével az összes vevőt egy vevőcsoportba helyezheti.  A fejléc és a sorok kiterjeszthetők a **CustGroup** mező hozzáadásához, majd szűrhetők úgy, hogy ne tartalmazza ezt a csoportot.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz,Értékesítési ajánlatfejléc":::

7. Miután kibővítette az **Ajánlatok** entitást, alkalmazzon szűrőt `CUSTGROUP !=  "<company>"` lekérdezési karakterlánccal.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Értékesítési ajánlat fejléce, lekérdezés szerkesztése":::
