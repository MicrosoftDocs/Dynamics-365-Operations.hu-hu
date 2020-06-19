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
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426982"
---
# <a name="inventory-availability"></a><span data-ttu-id="97517-103">Készlet elérhetősége</span><span class="sxs-lookup"><span data-stu-id="97517-103">Inventory availability</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="97517-104">A készlet elérhetőségét használva ellenőrizheti a készletet, mielőtt terméket ad hozzá az **Ajánlatok**, **Rendelések** vagy **Számlák** űrlapokhoz a Dynamics 365 modellvezérelt alkalmazásaiban.</span><span class="sxs-lookup"><span data-stu-id="97517-104">Using inventory availability, you can check your inventory before you add a product into the **Quotes**, **Orders**, or **Invoices** forms in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="97517-105">Például a készlet ellenőrzése és a teljesítés dátuma egy kulcsfeladat a [potenciális vevők készpénzre váltása](dual-write-prospect-to-cash.md) folyamatban.</span><span class="sxs-lookup"><span data-stu-id="97517-105">For example, checking inventory and determining a fulfullment date is a key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span> <span data-ttu-id="97517-106">Ha nincs elég készlete, megbecsülheti a várható szállítási dátumot az előrejelzett készletbevételezés és -kiadás alapján.</span><span class="sxs-lookup"><span data-stu-id="97517-106">If you don't have enough inventory, you can estimate a delivery date based on projected inventory receipts and issues.</span></span> <span data-ttu-id="97517-107">Megtekintheti a termék ígérethez rendelkezésre áll információit is, ahol megtalálhatja az ígért mennyiséget az előre meghatározott időkorláton belül.</span><span class="sxs-lookup"><span data-stu-id="97517-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the pre-defined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="97517-108">Aktuális készlet</span><span class="sxs-lookup"><span data-stu-id="97517-108">On-hand Inventory</span></span> 

<span data-ttu-id="97517-109">A Dynamics 365 Sales **Ajánlatok**, **Rendelések** vagy **Számlák** űrlapjainak fejlécében egy új **Aktuális készlet** gomb jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="97517-109">In the header of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **On-hand Inventory** is added.</span></span> <span data-ttu-id="97517-110">Amikor a gombra kattint, megjelenik egy párbeszédpanel, amelyen megadhatja azt a vállalatot és terméket, amelynek az aktuális készletét ellenőrizni szeretné.</span><span class="sxs-lookup"><span data-stu-id="97517-110">When you click the button, a dialog box appears and you can specify the company and the product for which you want to check the on-hand inventory.</span></span> <span data-ttu-id="97517-111">A rendszer a készletadatokat adja vissza a Dynamics 365 Supply Chain Management alkalmazásból, és ugyanazokat az információkat jeleníti meg, mint az [Aktuális készlet](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="97517-111">It returns the inventory information from Dynamics 365 Supply Chain Management, and shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span> <span data-ttu-id="97517-112">Az adatok a következő mennyiségeket tartalmazzák:</span><span class="sxs-lookup"><span data-stu-id="97517-112">The information includes these quantities:</span></span>

- <span data-ttu-id="97517-113">**Aktuális mennyiség**</span><span class="sxs-lookup"><span data-stu-id="97517-113">**On-hand Quantity**</span></span>
- <span data-ttu-id="97517-114">**Lefoglalt aktuális mennyiség**</span><span class="sxs-lookup"><span data-stu-id="97517-114">**Reserved On-hand Quantity**</span></span>
- <span data-ttu-id="97517-115">**Elérhető aktuális mennyiség**</span><span class="sxs-lookup"><span data-stu-id="97517-115">**Available On-hand Quantity**</span></span>
- <span data-ttu-id="97517-116">**Rendelt mennyiség**</span><span class="sxs-lookup"><span data-stu-id="97517-116">**Orderd Quantity**</span></span>
- <span data-ttu-id="97517-117">**Rendelésben lévő mennyiség**</span><span class="sxs-lookup"><span data-stu-id="97517-117">**On-order Quantity**</span></span>
- <span data-ttu-id="97517-118">**Lefoglalt rendelt mennyiség**</span><span class="sxs-lookup"><span data-stu-id="97517-118">**Reserved Ordered Quantity**</span></span>
- <span data-ttu-id="97517-119">**Teljes elérhető mennyiség**</span><span class="sxs-lookup"><span data-stu-id="97517-119">**Total Available Quantity**</span></span>

## <a name="atp-information"></a><span data-ttu-id="97517-120">Információk az ígérethez rendelkezésre álló készletről</span><span class="sxs-lookup"><span data-stu-id="97517-120">ATP information</span></span>

<span data-ttu-id="97517-121">A Dynamics 365 Sales **Ajánlatok**, **Rendelések** vagy **Számlák** űrlapjainak sorelemein egy új **Ígérethez rendelkezésre álló adatok** gomb jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="97517-121">On line items of the **Quotes**, **Orders**, or **Invoices** forms in Dynamics 365 Sales, a new button **ATP Information** is added.</span></span> <span data-ttu-id="97517-122">Amikor a gombra kattint, megjelenik egy párbeszédpanel, amelyen megadhatja a vállalatot, terméket, helyet, készletraktárat és rendelési mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="97517-122">When you click the button, a dialog box appears and you can specify the company, product, inventory Site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="97517-123">Az **Ígérethez rendelkezésre áll adatokat** adja vissza a Supply Chain Management alkalmazásból, és megjeleníti a [Rendelési ígéret](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations) részben leírt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="97517-123">It returns the **ATP Information** from Supply Chain Management and shows the settings descrbed in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span> <span data-ttu-id="97517-124">Az adatok között szerepel az **Ígérethez rendelkezésre álló mennyiség**, **Bevételezett mennyiség**, **Kiadott mennyiség** és az **Aktuális készlet**.</span><span class="sxs-lookup"><span data-stu-id="97517-124">The information includes **ATP quantity**, **Receipt quantity**, **Issue quantity**, and **On-hand quantity**.</span></span>
