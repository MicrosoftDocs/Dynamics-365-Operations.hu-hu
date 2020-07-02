---
title: Készlet rendelkezésre állása kettős írásban
description: Ez a témakör a készlet rendelkezésre állásának ellenőrzéséről a kettős írásban tartalmaz tájékoztatást.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
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
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 227a2062a7985a787f8278c196f7df2fb6f31691
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443872"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="5bfce-103">Készlet rendelkezésre állása kettős írásban</span><span class="sxs-lookup"><span data-stu-id="5bfce-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5bfce-104">A készlet elérhetőségét használva ellenőrizheti a készletet, mielőtt terméket ad hozzá az **Ajánlatok**, **Rendelések** vagy **Számlák** oldalakhoz a Microsoft Dynamics 365 Sales alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="5bfce-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="5bfce-105">Például a készlet ellenőrzése és a teljesítés dátuma egy kulcsfeladat a [potenciális vevők készpénzre váltása](dual-write-prospect-to-cash.md) folyamatban.</span><span class="sxs-lookup"><span data-stu-id="5bfce-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="5bfce-106">Ha nincs elég készlete, megbecsülheti a várható szállítási dátumot az előrejelzett készletbevételezés és -kiadás alapján.</span><span class="sxs-lookup"><span data-stu-id="5bfce-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="5bfce-107">Megtekintheti a termék ígérethez rendelkezésre áll információit is, ahol megtalálhatja az ígért mennyiséget az előre meghatározott időkorláton belül.</span><span class="sxs-lookup"><span data-stu-id="5bfce-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="5bfce-108">Aktuális készlet</span><span class="sxs-lookup"><span data-stu-id="5bfce-108">On-hand inventory</span></span>

<span data-ttu-id="5bfce-109">A Dynamics 365 Sales alkalmazásban egy új **Rendelkezésre álló készlet** gomb lett hozzáadva az **Ajánlatok**, **Rendelések** és **Számlák** űrlapjainak fejlécében.</span><span class="sxs-lookup"><span data-stu-id="5bfce-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="5bfce-110">Amikor a gombra kattint, megjelenik egy párbeszédpanel, ahol megadhatja azt a vállalatot és terméket, amelynek az aktuális készletét ellenőrizni szeretné.</span><span class="sxs-lookup"><span data-stu-id="5bfce-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="5bfce-111">Ez a párbeszédpanel ugyanazokat az adatokat jeleníti meg, mint az [Aktuális készlet](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="5bfce-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="5bfce-112">A párbeszédpanel a Dynamics 365 Supply Chain Management készletadatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="5bfce-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5bfce-113">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="5bfce-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="5bfce-114">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-114">On-hand quantity</span></span>
- <span data-ttu-id="5bfce-115">Lefoglalt aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="5bfce-116">Elérhető aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-116">Available on-hand quantity</span></span>
- <span data-ttu-id="5bfce-117">Megrendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-117">Ordered quantity</span></span>
- <span data-ttu-id="5bfce-118">Rendelésben lévő mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-118">On-order quantity</span></span>
- <span data-ttu-id="5bfce-119">Lefoglalt rendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="5bfce-120">Teljes elérhető mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="5bfce-121">Információk az ígérethez rendelkezésre álló készletről</span><span class="sxs-lookup"><span data-stu-id="5bfce-121">ATP information</span></span>

<span data-ttu-id="5bfce-122">A Sales alkalmazásban az **Árajánlatok** , **Rendelések** és **Számlák** oldalain egy új, **ATP-információ** gombbal bővült a cikkek sora.</span><span class="sxs-lookup"><span data-stu-id="5bfce-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="5bfce-123">Amikor ezt a gombot választja, megjelenik egy párbeszédpanel, amelyen megadhatja a vállalatot, terméket, helyet, készletraktárat és rendelési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="5bfce-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="5bfce-124">Ez a párbeszédpanel ugyanolyan beállításokat tartalmaz, mint a [Rendelési ígéret](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="5bfce-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="5bfce-125">A párbeszédpanel a Supply Chain Management „ígérethez rendelkezésre áll” adatait adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5bfce-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="5bfce-126">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="5bfce-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="5bfce-127">Ígérethez rendelkezésre álló mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-127">ATP quantity</span></span>
- <span data-ttu-id="5bfce-128">Bevételezés mennyisége</span><span class="sxs-lookup"><span data-stu-id="5bfce-128">Receipt quantity</span></span>
- <span data-ttu-id="5bfce-129">Kiadás mennyisége</span><span class="sxs-lookup"><span data-stu-id="5bfce-129">Issue quantity</span></span>
- <span data-ttu-id="5bfce-130">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="5bfce-130">On-hand quantity</span></span>
