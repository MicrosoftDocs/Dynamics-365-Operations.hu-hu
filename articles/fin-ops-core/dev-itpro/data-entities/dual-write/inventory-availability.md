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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997892"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="01b5a-103">Készlet rendelkezésre állása kettős írásban</span><span class="sxs-lookup"><span data-stu-id="01b5a-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01b5a-104">A készlet elérhetőségét használva ellenőrizheti a készletet, mielőtt terméket ad hozzá az **Ajánlatok** , **Rendelések** vagy **Számlák** oldalakhoz a Microsoft Dynamics 365 Sales alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="01b5a-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations** , **Orders** , or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="01b5a-105">Például a készlet ellenőrzése és a teljesítés dátuma egy kulcsfeladat a [potenciális vevők készpénzre váltása](dual-write-prospect-to-cash.md) folyamatban.</span><span class="sxs-lookup"><span data-stu-id="01b5a-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="01b5a-106">Ha nincs elég készlete, megbecsülheti a várható szállítási dátumot az előrejelzett készletbevételezés és -kiadás alapján.</span><span class="sxs-lookup"><span data-stu-id="01b5a-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="01b5a-107">Megtekintheti a termék ígérethez rendelkezésre áll információit is, ahol megtalálhatja az ígért mennyiséget az előre meghatározott időkorláton belül.</span><span class="sxs-lookup"><span data-stu-id="01b5a-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="01b5a-108">Aktuális készlet</span><span class="sxs-lookup"><span data-stu-id="01b5a-108">On-hand inventory</span></span>

<span data-ttu-id="01b5a-109">A Dynamics 365 Sales alkalmazásban egy új **Rendelkezésre álló készlet** gomb lett hozzáadva az **Ajánlatok** , **Rendelések** és **Számlák** űrlapjainak fejlécében.</span><span class="sxs-lookup"><span data-stu-id="01b5a-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="01b5a-110">Amikor a gombra kattint, megjelenik egy párbeszédpanel, ahol megadhatja azt a vállalatot és terméket, amelynek az aktuális készletét ellenőrizni szeretné.</span><span class="sxs-lookup"><span data-stu-id="01b5a-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="01b5a-111">Ez a párbeszédpanel ugyanazokat az adatokat jeleníti meg, mint az [Aktuális készlet](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="01b5a-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="01b5a-112">A párbeszédpanel a Dynamics 365 Supply Chain Management készletadatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="01b5a-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="01b5a-113">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="01b5a-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="01b5a-114">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-114">On-hand quantity</span></span>
- <span data-ttu-id="01b5a-115">Lefoglalt aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="01b5a-116">Elérhető aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-116">Available on-hand quantity</span></span>
- <span data-ttu-id="01b5a-117">Megrendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-117">Ordered quantity</span></span>
- <span data-ttu-id="01b5a-118">Rendelésben lévő mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-118">On-order quantity</span></span>
- <span data-ttu-id="01b5a-119">Lefoglalt rendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="01b5a-120">Teljes elérhető mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="01b5a-121">Információk az ígérethez rendelkezésre álló készletről</span><span class="sxs-lookup"><span data-stu-id="01b5a-121">ATP information</span></span>

<span data-ttu-id="01b5a-122">A Sales alkalmazásban az **Árajánlatok** , **Rendelések** és **Számlák** oldalain egy új, **ATP-információ** gombbal bővült a cikkek sora.</span><span class="sxs-lookup"><span data-stu-id="01b5a-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes** , **Orders** , and **Invoices** pages.</span></span> <span data-ttu-id="01b5a-123">Amikor ezt a gombot választja, megjelenik egy párbeszédpanel, amelyen megadhatja a vállalatot, terméket, helyet, készletraktárat és rendelési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="01b5a-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="01b5a-124">Ez a párbeszédpanel ugyanolyan beállításokat tartalmaz, mint a [Rendelési ígéret](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="01b5a-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="01b5a-125">A párbeszédpanel a Supply Chain Management „ígérethez rendelkezésre áll” adatait adja vissza.</span><span class="sxs-lookup"><span data-stu-id="01b5a-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="01b5a-126">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="01b5a-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="01b5a-127">Ígérethez rendelkezésre álló mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-127">ATP quantity</span></span>
- <span data-ttu-id="01b5a-128">Bevételezés mennyisége</span><span class="sxs-lookup"><span data-stu-id="01b5a-128">Receipt quantity</span></span>
- <span data-ttu-id="01b5a-129">Kiadás mennyisége</span><span class="sxs-lookup"><span data-stu-id="01b5a-129">Issue quantity</span></span>
- <span data-ttu-id="01b5a-130">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="01b5a-130">On-hand quantity</span></span>
