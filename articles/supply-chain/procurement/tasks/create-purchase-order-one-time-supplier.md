---
title: Beszerzési rendelés létrehozása egyszeri szállítóhoz
description: Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy beszerzési rendelést egy egyszeri szállítóhoz.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c4885547cdf2f8496446761e27ce39e67e670f15
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016402"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="f55b0-103">Beszerzési rendelés létrehozása egyszeri szállítóhoz</span><span class="sxs-lookup"><span data-stu-id="f55b0-103">Create a purchase order for a one-time supplier</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f55b0-104">Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy beszerzési rendelést egy egyszeri szállítóhoz.</span><span class="sxs-lookup"><span data-stu-id="f55b0-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="f55b0-105">A rendszer automatikusan létrehozza a szállítót a beszerzési rendeléssel együtt, a szállítói számla manuálisan történő létrehozása helyett.</span><span class="sxs-lookup"><span data-stu-id="f55b0-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="f55b0-106">Általában a beszerzési ügynök hozza létre a beszerzési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="f55b0-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="f55b0-107">Az útmutatóban mutatott példa használható az USMF demo adatok cégben.</span><span class="sxs-lookup"><span data-stu-id="f55b0-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="f55b0-108">Ez az előfeltétele annak, hogy a Kötelezettségek paraméterei lapon az egyszeri szállítói számla legyen beállítva.</span><span class="sxs-lookup"><span data-stu-id="f55b0-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="f55b0-109">Beszerzési rendelés létrehozása egyszeri szállítóhoz</span><span class="sxs-lookup"><span data-stu-id="f55b0-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="f55b0-110">Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.</span><span class="sxs-lookup"><span data-stu-id="f55b0-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="f55b0-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f55b0-111">Click New.</span></span>
3. <span data-ttu-id="f55b0-112">Válassza ki az Igen lehetőséget az Egyszeri szállító mezőben.</span><span class="sxs-lookup"><span data-stu-id="f55b0-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="f55b0-113">A rendszer automatikusan létrehozza a szállítói számlát és hozzárendeli a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="f55b0-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="f55b0-114">A rendszer a szállítói számlát a Kötelezettségek paraméterei oldal Általános lapon megadott sablon alapján hozza létre.</span><span class="sxs-lookup"><span data-stu-id="f55b0-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="f55b0-115">Írja be a szállító nevét a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f55b0-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="f55b0-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f55b0-116">Click OK.</span></span>
    * <span data-ttu-id="f55b0-117">Lehetséges, hogy már kész van a beszerzési rendelés, és ugyanúgy fel van dolgozva, mint a többi rendelés.</span><span class="sxs-lookup"><span data-stu-id="f55b0-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="f55b0-118">Nincsenek olyan különleges jellemzők, amelyek kapcsolatban állnak azzal, hogy hogyan jött létre.</span><span class="sxs-lookup"><span data-stu-id="f55b0-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="f55b0-119">A számla számot ad az esedékes tranzakcióról azon a szállítói számlán, amelyet a rendeléssel hoztak létre, illetve a kifizetés ezt követően történik meg.</span><span class="sxs-lookup"><span data-stu-id="f55b0-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span>

