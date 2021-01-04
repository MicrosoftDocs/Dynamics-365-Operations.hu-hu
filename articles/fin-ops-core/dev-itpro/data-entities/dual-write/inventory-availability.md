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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4453403"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="4f0f1-103">Készlet rendelkezésre állása kettős írásban</span><span class="sxs-lookup"><span data-stu-id="4f0f1-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4f0f1-104">A készlet elérhetőségét használva ellenőrizheti a készletet, mielőtt terméket ad hozzá az **Ajánlatok**, **Rendelések** vagy **Számlák** oldalakhoz a Microsoft Dynamics 365 Sales alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="4f0f1-105">Például a készlet ellenőrzése és a teljesítés dátuma egy kulcsfeladat a [potenciális vevők készpénzre váltása](dual-write-prospect-to-cash.md) folyamatban.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="4f0f1-106">Ha nincs elég készlete, megbecsülheti a várható szállítási dátumot az előrejelzett készletbevételezés és -kiadás alapján.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="4f0f1-107">Megtekintheti a termék ígérethez rendelkezésre áll információit is, ahol megtalálhatja az ígért mennyiséget az előre meghatározott időkorláton belül.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="4f0f1-108">Aktuális készlet</span><span class="sxs-lookup"><span data-stu-id="4f0f1-108">On-hand inventory</span></span>

<span data-ttu-id="4f0f1-109">A Dynamics 365 Sales alkalmazásban egy új **Rendelkezésre álló készlet** gomb lett hozzáadva az **Ajánlatok**, **Rendelések** és **Számlák** űrlapjainak fejlécében.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="4f0f1-110">Amikor a gombra kattint, megjelenik egy párbeszédpanel, ahol megadhatja azt a vállalatot és terméket, amelynek az aktuális készletét ellenőrizni szeretné.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="4f0f1-111">Ez a párbeszédpanel ugyanazokat az adatokat jeleníti meg, mint az [Aktuális készlet](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="4f0f1-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="4f0f1-112">A párbeszédpanel a Dynamics 365 Supply Chain Management készletadatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="4f0f1-113">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="4f0f1-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="4f0f1-114">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-114">On-hand quantity</span></span>
- <span data-ttu-id="4f0f1-115">Lefoglalt aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="4f0f1-116">Elérhető aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-116">Available on-hand quantity</span></span>
- <span data-ttu-id="4f0f1-117">Megrendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-117">Ordered quantity</span></span>
- <span data-ttu-id="4f0f1-118">Rendelésben lévő mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-118">On-order quantity</span></span>
- <span data-ttu-id="4f0f1-119">Lefoglalt rendelt mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="4f0f1-120">Teljes elérhető mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="4f0f1-121">Információk az ígérethez rendelkezésre álló készletről</span><span class="sxs-lookup"><span data-stu-id="4f0f1-121">ATP information</span></span>

<span data-ttu-id="4f0f1-122">A Sales alkalmazásban az **Árajánlatok** , **Rendelések** és **Számlák** oldalain egy új, **ATP-információ** gombbal bővült a cikkek sora.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="4f0f1-123">Amikor ezt a gombot választja, megjelenik egy párbeszédpanel, amelyen megadhatja a vállalatot, terméket, helyet, készletraktárat és rendelési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="4f0f1-124">Ez a párbeszédpanel ugyanolyan beállításokat tartalmaz, mint a [Rendelési ígéret](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="4f0f1-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="4f0f1-125">A párbeszédpanel a Supply Chain Management „ígérethez rendelkezésre áll” adatait adja vissza.</span><span class="sxs-lookup"><span data-stu-id="4f0f1-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="4f0f1-126">Ez az információ az alábbi mennyiségeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="4f0f1-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="4f0f1-127">Ígérethez rendelkezésre álló mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-127">ATP quantity</span></span>
- <span data-ttu-id="4f0f1-128">Bevételezés mennyisége</span><span class="sxs-lookup"><span data-stu-id="4f0f1-128">Receipt quantity</span></span>
- <span data-ttu-id="4f0f1-129">Kiadás mennyisége</span><span class="sxs-lookup"><span data-stu-id="4f0f1-129">Issue quantity</span></span>
- <span data-ttu-id="4f0f1-130">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="4f0f1-130">On-hand quantity</span></span>
