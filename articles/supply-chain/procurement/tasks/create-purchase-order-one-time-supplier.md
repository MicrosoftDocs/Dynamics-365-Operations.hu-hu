--- 
title: "Beszerzési rendelés létrehozása egyszeri szállítóhoz"
description: "Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy beszerzési rendelést egy egyszeri szállítóhoz."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 59582e33a3a012d6f9e3f506d1f8303c07fb06a9
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="0c3a3-103">Beszerzési rendelés létrehozása egyszeri szállítóhoz</span><span class="sxs-lookup"><span data-stu-id="0c3a3-103">Create a purchase order for a one-time supplier</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0c3a3-104">Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy beszerzési rendelést egy egyszeri szállítóhoz.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="0c3a3-105">A rendszer automatikusan létrehozza a szállítót a beszerzési rendeléssel együtt, a szállítói számla manuálisan történő létrehozása helyett.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="0c3a3-106">Általában a beszerzési ügynök hozza létre a beszerzési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="0c3a3-107">Az útmutatóban mutatott példa használható az USMF demo adatok cégben.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="0c3a3-108">Ez az előfeltétele annak, hogy a Kötelezettségek paraméterei lapon az egyszeri szállítói számla legyen beállítva.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="0c3a3-109">Beszerzési rendelés létrehozása egyszeri szállítóhoz</span><span class="sxs-lookup"><span data-stu-id="0c3a3-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="0c3a3-110">Ugorjon a Beszerzés és forrás > Beszerzési rendelés > Összes beszerzési rendelés pontra.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="0c3a3-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-111">Click New.</span></span>
3. <span data-ttu-id="0c3a3-112">Válassza ki az Igen lehetőséget az Egyszeri szállító mezőben.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="0c3a3-113">A rendszer automatikusan létrehozza a szállítói számlát és hozzárendeli a beszerzési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="0c3a3-114">A rendszer a szállítói számlát a Kötelezettségek paraméterei oldal Általános lapon megadott sablon alapján hozza létre.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="0c3a3-115">Írja be a szállító nevét a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="0c3a3-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-116">Click OK.</span></span>
    * <span data-ttu-id="0c3a3-117">Lehetséges, hogy már kész van a beszerzési rendelés, és ugyanúgy fel van dolgozva, mint a többi rendelés.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="0c3a3-118">Nincsenek olyan különleges jellemzők, amelyek kapcsolatban állnak azzal, hogy hogyan jött létre.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="0c3a3-119">A számla számot ad az esedékes tranzakcióról azon a szállítói számlán, amelyet a rendeléssel hoztak létre, illetve a kifizetés ezt követően történik meg.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span> <span data-ttu-id="0c3a3-120">Ha ez kész van, akkor törölni lehet a szállítói számlát.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-120">When this is completed, the vendor account can be deleted.</span></span> <span data-ttu-id="0c3a3-121">Ezt általában a kötelezettségkezelő osztály végzi el.</span><span class="sxs-lookup"><span data-stu-id="0c3a3-121">This is typically done by the accounts payable department.</span></span>  


