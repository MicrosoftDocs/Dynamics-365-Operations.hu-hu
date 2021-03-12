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
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a><span data-ttu-id="12401-103">Vállalatközi rendelések szűrése a Rendelések és az OrderLines entitások szinkronizálásának elkerülése érdekében</span><span class="sxs-lookup"><span data-stu-id="12401-103">Filter intercompany orders to avoid syncing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12401-104">Szűrheti a vállalatközi rendeléseket, hogy a **Rendelések** és az **OrderLines** táblák ne legyenek szinkronizálva.</span><span class="sxs-lookup"><span data-stu-id="12401-104">You can filter intercompany orders so that the **Orders** and **OrderLines** tables aren't synced.</span></span> <span data-ttu-id="12401-105">Bizonyos esetekben a vállalatközi rendelés részletei nem szükségesek az ügyfélkezelési alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="12401-105">In some scenarios, the intercompany order details aren't required in a customer engagement app.</span></span>

<span data-ttu-id="12401-106">A szabványos Dataverse-táblák mindegyike ki van bővítve az **IntercompanyOrder** oszlopra mutató hivatkozásokkal, és a kettős írású leképezések úgy módosulnak, hogy a szűrők további oszlopaira hivatkozzanak.</span><span class="sxs-lookup"><span data-stu-id="12401-106">Each standard Dataverse table is extended through references to the **IntercompanyOrder** column, and the dual-write maps are modified so that they refer to the additional columns in the filters.</span></span> <span data-ttu-id="12401-107">Emiatt a vállalatközi rendelések már nem szinkronizálódnak.</span><span class="sxs-lookup"><span data-stu-id="12401-107">Therefore, the intercompany orders are no longer synced.</span></span> <span data-ttu-id="12401-108">Ezzel a folyamattal elkerülhetők a szükségtelen adatok az ügyfélkezelési alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="12401-108">This process helps prevent unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="12401-109">Bővítse ki a **CDS értékesítésirendelés-fejlécek** tábláját az **IntercompanyOrder** oszlopra való hivatkozás hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="12401-109">Extend the **CDS Sales Order Headers** table by adding a reference to the **IntercompanyOrder** column.</span></span> <span data-ttu-id="12401-110">Ez az oszlop csak vállalatközi rendeléseken van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="12401-110">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="12401-111">Az **IntercompanyOrder** oszlop a **SalesTable** táblában érhető el.</span><span class="sxs-lookup"><span data-stu-id="12401-111">The **IntercompanyOrder** column is available in the **SalesTable** table.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Leképezés előkészítése az oldal CDS értékesítésirendelés-fejlécek elemre való célzásához":::

2. <span data-ttu-id="12401-113">A **CDS értékesítésirendelés-fejlécek** kiterjesztése után az **IntercompanyOrder** oszlop elérhető a leképezésben.</span><span class="sxs-lookup"><span data-stu-id="12401-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** column is available in the mapping.</span></span> <span data-ttu-id="12401-114">Szűrő alkalmazása az `INTERCOMPANYORDER == ""` elemmel lekérdezési karakterláncként.</span><span class="sxs-lookup"><span data-stu-id="12401-114">Apply a filter that has `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="A CDS értékesítésirendelés-fejlécek lekérdezési párbeszédpanelének szerkesztése":::

3. <span data-ttu-id="12401-116">Bővítse ki a **CDS értékesítésirendelés-sorok** tábláját az **IntercompanyInventTransId** oszlopra való hivatkozás hozzáadásával.</span><span class="sxs-lookup"><span data-stu-id="12401-116">Extend the **CDS Sales Order Lines** table by adding a reference to the **IntercompanyInventTransId** column.</span></span> <span data-ttu-id="12401-117">Ez az oszlop csak vállalatközi rendeléseken van kitöltve.</span><span class="sxs-lookup"><span data-stu-id="12401-117">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="12401-118">Az **IntercompanyInventTransId** oszlop a **SalesLine** táblában érhető el.</span><span class="sxs-lookup"><span data-stu-id="12401-118">The **InterCompanyInventTransId** column is available in the **SalesLine** table.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Leképezés előkészítése az oldal CDS értékesítésirendelés-sorok elemre való célzásához":::

4. <span data-ttu-id="12401-120">A **CDS értékesítésirendelés-sorok** kiterjesztése után az **IntercompanyInventTransId** oszlop elérhető a leképezésben.</span><span class="sxs-lookup"><span data-stu-id="12401-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** column is available in the mapping.</span></span> <span data-ttu-id="12401-121">Szűrő alkalmazása az `INTERCOMPANYINVENTTRANSID == ""` elemmel lekérdezési karakterláncként.</span><span class="sxs-lookup"><span data-stu-id="12401-121">Apply a filter that has `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="A CDS értékesítésirendelés-sorok lekérdezési párbeszédpanelének szerkesztése":::

5. <span data-ttu-id="12401-123">Ismételje meg az 1–2. lépést az **V2 értékesítési számlafejléc** tábla kiterjesztéséhez és szűrőlekérdezés hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="12401-123">Repeat steps 1 and 2 to extend the **Sales Invoice Header V2** table and add a filter query.</span></span> <span data-ttu-id="12401-124">Ebben az esetben használja az `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` a szűrő lekérdezési karakterláncaként.</span><span class="sxs-lookup"><span data-stu-id="12401-124">In this case, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Leképezés előkészítése az oldal V2 értékesítési számlafejléc elemre való célzásához":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="A V2 értékesítési számlafejléc lekérdezési párbeszédpanelének szerkesztése":::

6. <span data-ttu-id="12401-127">Ismételje meg az 3–4. lépést az **V2 értékesítési számlasor** tábla kiterjesztéséhez és szűrőlekérdezés hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="12401-127">Repeat steps 3 and 4 to extend the **Sales Invoice Lines V2** table and add a filter query.</span></span> <span data-ttu-id="12401-128">Ebben az esetben használja az `INTERCOMPANYINVENTTRANSID == ""` a szűrő lekérdezési karakterláncaként.</span><span class="sxs-lookup"><span data-stu-id="12401-128">In this case, use `INTERCOMPANYINVENTTRANSID == ""` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="A V2 értékesítési számlasor lekérdezési párbeszédpanelének szerkesztése":::

7. <span data-ttu-id="12401-130">Az **Ajánlatok** tábla nem rendelkezik vállalatközi kapcsolattal.</span><span class="sxs-lookup"><span data-stu-id="12401-130">The **Quotations** table doesn't have an intercompany relationship.</span></span> <span data-ttu-id="12401-131">Ha valaki ajánlatot hoz létre az egyik vállalatközi vevőhöz, a **CustGroup** oszlop segítségével az összes vevőt egy vevőcsoportba helyezheti.</span><span class="sxs-lookup"><span data-stu-id="12401-131">If someone creates a quotation for one of your intercompany customers, you can use the **CustGroup** column to put all those customers into one customer group.</span></span> <span data-ttu-id="12401-132">A fejlécet és sorokat a **CustGroup** oszlop hozzáadásával bővítheti, majd úgy szűrheti, hogy a csoportot ne tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="12401-132">You can extend the header and lines by adding the **CustGroup** column, and then filter so that the group isn't included.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Leképezés előkészítése az oldal CDS értékesítési ajánlatfejléc elemre való célzásához":::

8. <span data-ttu-id="12401-134">Miután kibővítette az **Ajánlatok** entitást, alkalmazzon szűrőt `CUSTGROUP != "<company>"` lekérdezési karakterlánccal.</span><span class="sxs-lookup"><span data-stu-id="12401-134">After **Quotations** is extended, apply a filter that has `CUSTGROUP != "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="A CDS értékesítési ajánlatfejléc lekérdezési párbeszédpanelének szerkesztése":::
