---
title: "Részlegesen foglalt átmozgatási rendelések kötegelt kiadása"
description: "Ez a témakör leírja, hogyan állíthatja be és alkalmazhatja mobileszközről a részlegesen foglalt átmozgatási rendelések kötegelt kiadását."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ba426692e2e404ab75e5730b8205115fc59e402f
ms.openlocfilehash: 4477749c721cf8c8bd244f551d9eca7ec9449fd1
ms.contentlocale: hu-hu
ms.lasthandoff: 02/08/2018

---

# <a name="batch-release-of-partially-reserved-transfer-orders"></a><span data-ttu-id="b26c8-103">Részlegesen foglalt átmozgatási rendelések kötegelt kiadása</span><span class="sxs-lookup"><span data-stu-id="b26c8-103">Batch release of partially reserved transfer orders</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b26c8-104">A részlegesen foglalt átmozgatási rendelések kötegelt kiadása funkció lehetővé teszi az átmozgatási rendelések részleges kiadását egy raktárba kötegelt feldolgozással.</span><span class="sxs-lookup"><span data-stu-id="b26c8-104">The functionality for batch release of partially reserved transfer orders lets you partially release transfer orders to a warehouse by using a batch job.</span></span>
<span data-ttu-id="b26c8-105">Mivel lehetőség van egy részleges mennyiség kiadására, egy rendelés kiadásához nem kell megvárni, hogy a teljes rendelési mennyiség elérhető legyen a raktárban.</span><span class="sxs-lookup"><span data-stu-id="b26c8-105">Because you have the option to release a partial quantity, you don’t have to wait for the whole order quantity to be available in the warehouse before you release an order.</span></span>

<span data-ttu-id="b26c8-106">A rendelések kiadása egy raktárnak speciális raktárkezelési folyamat.</span><span class="sxs-lookup"><span data-stu-id="b26c8-106">The release of orders to a warehouse is an advanced warehouse management process.</span></span> <span data-ttu-id="b26c8-107">A folyamat olyan tevékenységeket foglal magában, például kitárolás, csomagolás és a szállítás, amelyeket egy raktári dolgozó mobileszköz használatával tud végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="b26c8-107">This process involves activities, such as picking, packing, and shipping, that a warehouse worker can perform by using a mobile device.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="b26c8-108">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="b26c8-108">Where it applies</span></span>

<span data-ttu-id="b26c8-109">Ehhez a funkcióhoz az átmozgatási rendelések kiadása kötegelt feldolgozással történik meg a raktárba.</span><span class="sxs-lookup"><span data-stu-id="b26c8-109">For this functionality, transfer orders are released to a warehouse by using a batch job.</span></span> <span data-ttu-id="b26c8-110">Ez a funkció akkor hasznos, ha nincs elegendő készlet a raktárban, de továbbra is el szeretné vinni a cikkek az egyik raktárból a másikba.</span><span class="sxs-lookup"><span data-stu-id="b26c8-110">This functionality is useful when you don’t have enough inventory in the warehouse, but you still want to transfer items from one warehouse to another.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="b26c8-111">Hogyan van beállítva</span><span class="sxs-lookup"><span data-stu-id="b26c8-111">How it is set up</span></span>

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="b26c8-112">Átmozgatási rendelések és értékesítési rendelések teljesítési feltételeinek megadása</span><span class="sxs-lookup"><span data-stu-id="b26c8-112">Specify fulfillment criteria for transfer orders and sales orders</span></span>

<span data-ttu-id="b26c8-113">Mielőtt egy rendelés részben is kiadható egy raktárnak kötegelve, a teljesítési feltételeknek teljesülniük kell.</span><span class="sxs-lookup"><span data-stu-id="b26c8-113">Before an order can be partially released to a warehouse in a batch, the fulfillment criteria must be met.</span></span> <span data-ttu-id="b26c8-114">A teljesítési feltételeket a teljesítési irányelv határozza meg.</span><span class="sxs-lookup"><span data-stu-id="b26c8-114">These fulfillment criteria are determined by the fulfillment policy.</span></span>

<span data-ttu-id="b26c8-115">Az átmozgatási rendelések és az értékesítési rendelések teljesítési irányelvei a vállalat szintjén vannak megadva.</span><span class="sxs-lookup"><span data-stu-id="b26c8-115">Fulfillment policies for transfer orders and sales orders are specified at the company level.</span></span> <span data-ttu-id="b26c8-116">A teljesítési irányelv beállításától függően a rendelések kötegelt kiadása elfogadásra vagy elutasításra kerül.</span><span class="sxs-lookup"><span data-stu-id="b26c8-116">Depending on the setup of the fulfillment policy, the release of orders in a batch will be accepted or rejected.</span></span> <span data-ttu-id="b26c8-117">A rendelések feldolgozása ennek megfelelően fog megtörténni.</span><span class="sxs-lookup"><span data-stu-id="b26c8-117">The orders will then be processed accordingly.</span></span>

-   <span data-ttu-id="b26c8-118">Teljesítési irányelvek létrehozásához az átmozgatási rendelésekhez és az értékesítési rendelésekhez kattintson a **Raktárkezelés** \> **Beállítás** \> **Raktárba való kiadás** \> **Teljesítési irányelv**  elemre, és hozzon létre egy teljesítési irányelvet: ehhez írjon be egy nevet és egy leírást.</span><span class="sxs-lookup"><span data-stu-id="b26c8-118">To create fulfillment policies for transfer orders and sales orders, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then create a fulfillment policy by entering a name and a description.</span></span>

-   <span data-ttu-id="b26c8-119">Teljesítési ráta, értéktípus és üzenet beállításához, amely a teljesítési irányelv megszegése esetén jelenik meg, kattintson a **Raktárkezelés** \> **Beállítás** \> **Raktárba való kiadás** \> **Teljesítési irányelv** elemre, majd adja meg a **Teljesítési ráta**, az **Értéktípus** és a **Teljesítési szabálytalanságok üzenetei** mezők tartalmát.</span><span class="sxs-lookup"><span data-stu-id="b26c8-119">To specify a fulfillment rate, a value type, and the message that is shown if the fulfillment policy is violated, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy**, and then set the **Fulfillment rate**, **Value type**, and **Fulfillment violation message** fields.</span></span>

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="b26c8-120">Átmozgatási rendelések és értékesítési rendelések teljesítési irányelveinek megadása</span><span class="sxs-lookup"><span data-stu-id="b26c8-120">Set the fulfillment policies for transfer orders and sales orders</span></span>

-   <span data-ttu-id="b26c8-121">Az átmozgatási rendelések teljesítési irányelveinek beállításához kattintson a **Készletkezelés** \> **Beállítás** \> **Készlet- és raktárkezelési paraméterek** \> **Átmozgatási rendelések** \> **Raktárkezelés** elemre, majd válasszon ki egy átmozgatási rendelési teljesítési irányelvet.</span><span class="sxs-lookup"><span data-stu-id="b26c8-121">To set the fulfillment policies for transfer orders, click **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters** \> **Transfer orders** \> **Warehouse management**, and then select a transfer order fulfillment policy.</span></span>

-   <span data-ttu-id="b26c8-122">Kattintson az értékesítési rendelések teljesítési házirendjeinek beállításához kattintson a **Kinnlevőségek** \> **Beállítás** \> **Kinnlevőségek paraméterei** \> **Raktárkezelés** elemre, és válasszon ki egy értékesítésirendelés-teljesítési irányelvet.</span><span class="sxs-lookup"><span data-stu-id="b26c8-122">To set the fulfillment policies for sales orders, click **Accounts receivable** \> **Setup** \> **Accounts receivable parameters** \> **Warehouse management**, and then select a sales order fulfillment policy.</span></span>

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a><span data-ttu-id="b26c8-123">Engedélyezze a kötegelt kiadást, és adja meg a mennyiséget, amelyet kötegelt kiadással kell kiadni.</span><span class="sxs-lookup"><span data-stu-id="b26c8-123">Allow release in a batch and specify the quantity that should be release in a batch</span></span>

<span data-ttu-id="b26c8-124">A kötegelt feladat rendelések raktárba történő kiadására szolgál, kötegelt módon.</span><span class="sxs-lookup"><span data-stu-id="b26c8-124">A batch job is used to release orders to a warehouse in a batch.</span></span> <span data-ttu-id="b26c8-125">A kötegelt feladatban magában lehet beállítani a paramétereket, amelyek megkülönböztetik a kötegelt rendelésként futtatandó rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="b26c8-125">The parameters that distinguish the orders that should be run in a batch job are set on the batch job itself.</span></span>

<span data-ttu-id="b26c8-126">A **Mennyiség** paraméter határozza meg, hogy a teljes mennyiséget vagy a ténylegesen lefoglalt mennyiséget kell kiadni kötegelve.</span><span class="sxs-lookup"><span data-stu-id="b26c8-126">The **Quantity** parameter specifies whether the whole quantity or the physically reserved quantity should be released in the batch.</span></span> <span data-ttu-id="b26c8-127">A **Részben kiadott rendelések kiadásának engedélyezése** paraméter határozza meg, hogy a kötegelt rendeléseket el kell-e fogadni vagy el kell-e utasítani, ha részben ki lettek adva korábban.</span><span class="sxs-lookup"><span data-stu-id="b26c8-127">The **Allow release of partially released orders** parameter determines whether orders in the batch should be accepted or rejected if they were partially released earlier.</span></span>

-   <span data-ttu-id="b26c8-128">Az átmozgatási rendelések **Mennyiség** és **Részben kiadott rendelések kiadásának engedélyezése** paramétereinek beállításához kattintson a **Raktárkezelés** \> **Raktárba való kiadás** \> **Átmozgatási rendelések automatikus kiadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="b26c8-128">To set the **Quantity** and **Allow release of partially released orders** parameters for transfer orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of transfer orders**.</span></span>

-   <span data-ttu-id="b26c8-129">Az értékesítési rendelések **Mennyiség** és **Részben kiadott rendelések kiadásának engedélyezése** paramétereinek beállításához kattintson a **Raktárkezelés** \> **Raktárba való kiadás** \> **Értékesítési rendelések automatikus kiadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="b26c8-129">To set the **Quantity** and **Allow release of partially released orders** parameters for sales orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of sales orders**.</span></span>

