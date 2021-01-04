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
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a><span data-ttu-id="55adf-103">Vállalatközi rendelések szűrése a Rendelések és a RendelésiSorok szinkronizálásának elkerülése érdekében</span><span class="sxs-lookup"><span data-stu-id="55adf-103">Filter intercompany orders to avoid synchronizing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="55adf-104">Vállalatközi rendeléseket szűrheti a **Rendelések** és a **RendelésiSorok** szinkronizálásának elkerülése érdekében.</span><span class="sxs-lookup"><span data-stu-id="55adf-104">You can filter intercompany orders to avoid synchronizing the **Orders** and **OrderLines** entities.</span></span> <span data-ttu-id="55adf-105">Bizonyos esetekben a vállalatközi rendelés részletei nem szükségesek az ügyfélkezelési alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="55adf-105">In some scenarios, the intercompany order details are not necessary in customer engagement app.</span></span>

<span data-ttu-id="55adf-106">A szabványos Common Data Service entitások mindegyike ki van bővítve az **IntercompanyOrder** mezőre mutató hivatkozásokkal, és a kettős írású leképezések úgy módosulnak, hogy a szűrők további mezőire hivatkozzanak.</span><span class="sxs-lookup"><span data-stu-id="55adf-106">Each of the standard Common Data Service entities is extended with references to the **IntercompanyOrder** field, and the dual-write maps are modified to refer to the additional fields in the filters.</span></span> <span data-ttu-id="55adf-107">Az eredmény az, hogy a vállalatközi rendelések szinkronizálása már nem történik meg.</span><span class="sxs-lookup"><span data-stu-id="55adf-107">The result is that the intercompany orders are no longer synchronized.</span></span> <span data-ttu-id="55adf-108">Ezzel a folyamattal elkerülhetők a szükségtelen adatok az ügyfélkezelési alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="55adf-108">This process avoids unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="55adf-109">Hivatkozás hozzáadása a **Vállalatközi rendelés** **CDS értékesítésirendelés-fejlécek** elemhez.</span><span class="sxs-lookup"><span data-stu-id="55adf-109">Add a reference to **IntercompanyOrder** to **CDS Sales Order Headers**.</span></span> <span data-ttu-id="55adf-110">Csak vállalatközi rendeléseken van feltöltve.</span><span class="sxs-lookup"><span data-stu-id="55adf-110">It is populated on only intercompany orders.</span></span> <span data-ttu-id="55adf-111">Az **IntercompanyOrder** mező a **SalesTable** táblában érhető el.</span><span class="sxs-lookup"><span data-stu-id="55adf-111">The field **IntercompanyOrder** is available in **SalesTable**.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz, SalesOrderHeader":::
    
2. <span data-ttu-id="55adf-113">A **CDS Sales Order Headers** kiterjesztése után az **IntercompanyOrder** mező elérhető a leképezésben.</span><span class="sxs-lookup"><span data-stu-id="55adf-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** field is available in the mapping.</span></span> <span data-ttu-id="55adf-114">Szűrő alkalmazása az `INTERCOMPANYORDER == ""` elemmel lekérdezési karakterláncként.</span><span class="sxs-lookup"><span data-stu-id="55adf-114">Apply a filter with `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Értékesítési rendelések fejlécei, lekérdezés szerkesztése":::

3. <span data-ttu-id="55adf-116">Hivatkozás hozzáadása az **IntercompanyInventTransId** és a **CDS értékesítésirendelés-sorok** elemekhez.</span><span class="sxs-lookup"><span data-stu-id="55adf-116">Add a reference to **IntercompanyInventTransId** to **CDS Sales Order Lines**.</span></span>  <span data-ttu-id="55adf-117">Csak vállalatközi rendeléseken van feltöltve.</span><span class="sxs-lookup"><span data-stu-id="55adf-117">It is populated on only intercompany orders.</span></span> <span data-ttu-id="55adf-118">Az **InterCompanyInventTransID** mező a **SalesLine** táblában érhető el.</span><span class="sxs-lookup"><span data-stu-id="55adf-118">The field **InterCompanyInventTransID** is available in **SalesLine**.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz, SalesOrderLine":::

4. <span data-ttu-id="55adf-120">A **CDS értékesítésirendelés-sorok** kiterjesztése után az **IntercompanyInventTransId** mező elérhető a leképezésben.</span><span class="sxs-lookup"><span data-stu-id="55adf-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** field is available in the mapping.</span></span> <span data-ttu-id="55adf-121">Szűrő alkalmazása az `INTERCOMPANYINVENTTRANSID == ""` elemmel lekérdezési karakterláncként.</span><span class="sxs-lookup"><span data-stu-id="55adf-121">Apply a filter with `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Értékesítési rendelési sorok, lekérdezés szerkesztése":::

5. <span data-ttu-id="55adf-123">Az **Értékesítési számlafejléc V2** és az **Értékesítési számlasorok V2** elemeket bővítse ki, ugyanúgy, ahogy a Common Data Service entitásokat is kiterjesztette az 1. és 2. lépésben.</span><span class="sxs-lookup"><span data-stu-id="55adf-123">Extend **Sales Invoice Header V2** and **Sales Invoice Lines V2** in the same way you extended the Common Data Service entities in steps 1 and 2.</span></span> <span data-ttu-id="55adf-124">Ezután adja hozzá a szűrőlekérdezéseket.</span><span class="sxs-lookup"><span data-stu-id="55adf-124">Then add the filter queries.</span></span> <span data-ttu-id="55adf-125">A **V2 értékesítési számlafejléc** szűrőkarakterlánca `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span><span class="sxs-lookup"><span data-stu-id="55adf-125">The filter string for **Sales Invoice Header V2** is `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span></span> <span data-ttu-id="55adf-126">A **V2 értékesítési számlasorok** szűrőkarakterlánca `INTERCOMPANYINVENTTRANSID == ""`.</span><span class="sxs-lookup"><span data-stu-id="55adf-126">The filter string for **Sales Invoice Lines V2** is `INTERCOMPANYINVENTTRANSID == ""`.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz,Értékesítési számlafejlécek":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Értékesítési számlák fejlécei, lekérdezés szerkesztése":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Értékesítési számlasorok, lekérdezés szerkesztése":::

6. <span data-ttu-id="55adf-130">Az **Ajánlatok** entitás nem rendelkezik vállalatközi kapcsolattal.</span><span class="sxs-lookup"><span data-stu-id="55adf-130">The **Quotations** entity doesn't have an intercompany relationship.</span></span> <span data-ttu-id="55adf-131">Ha valaki ajánlatot hoz létre az egyik vállalatközi vevőhöz, a **CustGroup** mező segítségével az összes vevőt egy vevőcsoportba helyezheti.</span><span class="sxs-lookup"><span data-stu-id="55adf-131">If someone creates a quote for one of your intercompany customers, you can put all of these customers in one customer group by using the **CustGroup** field.</span></span>  <span data-ttu-id="55adf-132">A fejléc és a sorok kiterjeszthetők a **CustGroup** mező hozzáadásához, majd szűrhetők úgy, hogy ne tartalmazza ezt a csoportot.</span><span class="sxs-lookup"><span data-stu-id="55adf-132">Header and lines can be extended to add the **CustGroup** field and then filter to not include this group.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Előkészítés rendszer hozzárendelése a célhoz,Értékesítési ajánlatfejléc":::

7. <span data-ttu-id="55adf-134">Miután kibővítette az **Ajánlatok** entitást, alkalmazzon szűrőt `CUSTGROUP !=  "<company>"` lekérdezési karakterlánccal.</span><span class="sxs-lookup"><span data-stu-id="55adf-134">After you extent the **Quotations** entity, apply a filter with `CUSTGROUP !=  "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Értékesítési ajánlat fejléce, lekérdezés szerkesztése":::
