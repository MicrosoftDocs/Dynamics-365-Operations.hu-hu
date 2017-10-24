--- 
title: "Termékek áttárolása a fogadó raktárból az üzletekbe"
description: "Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Áttárolást, amellyel termékeket oszthat el egy beszerzési rendelés bevételezési helyéről egy vagy több üzletbe."
author: BibiSp
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: daa42bb83d6b988e8fd18db6ad8386c67fd3e6e5
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="cd18a-103">Termékek áttárolása a fogadó raktárból az üzletekbe</span><span class="sxs-lookup"><span data-stu-id="cd18a-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd18a-104">Ez az eljárás bemutatja, hogy mely lépésekkel hozhat létre és dolgozhat fel egy Áttárolást, amellyel termékeket oszthat el egy beszerzési rendelés bevételezési helyéről egy vagy több üzletbe.</span><span class="sxs-lookup"><span data-stu-id="cd18a-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="cd18a-105">A felhasználó több konfigurációt is definiálhat, majd kérheti a rendszer javaslatát a termékek elosztására, vagy manuálisan megadhatja, hogy a termékek elosztása hová és az egyes üzletekbe milyen mennyiségben történjen.</span><span class="sxs-lookup"><span data-stu-id="cd18a-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="cd18a-106">Az eljárás nem tartalmazza az Áttárolás lehetőségben használható adatok (például: feltöltési szabályok, szervezeti hierarchiák, üzletek súlya) beállítását.</span><span class="sxs-lookup"><span data-stu-id="cd18a-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="cd18a-107">Az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="cd18a-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="cd18a-108">Ugrás az összes beszerzési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="cd18a-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="cd18a-109">Válasszon ki a listából egy beszerzési rendelést, majd a rendelés megnyitásához kattintson a hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="cd18a-110">A Művelet panelen kattintson a Kiskereskedelem elemre.</span><span class="sxs-lookup"><span data-stu-id="cd18a-110">On the Action Pane, click Retail.</span></span>
4. <span data-ttu-id="cd18a-111">Kattintson az Áttárolás gombra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-111">Click Cross docking.</span></span>
5. <span data-ttu-id="cd18a-112">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd18a-112">Click Edit.</span></span>
    * <span data-ttu-id="cd18a-113">A kategória segítségével szűrhetőek a Sorok szakaszban lévő cikkek.</span><span class="sxs-lookup"><span data-stu-id="cd18a-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="cd18a-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="cd18a-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="cd18a-115">Az Áttárolási mennyiség mezőbe írjon be egy értéket, amely megadja, hogy a kiválasztott termékből beszerzett mennyiség mekkora része kerüljön elosztásra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="cd18a-116">A További áttárolási mennyiség mezőbe írjon be egy értéket, amely megadja, hogy az elérhető beszerzett termékekből milyen mennyiség kerüljön elosztásra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="cd18a-117">Az Elosztás mezőbe írja be: „Hely súly”.</span><span class="sxs-lookup"><span data-stu-id="cd18a-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="cd18a-118">Más elosztási szabályok használatához kiválaszthatja a többi típust is.</span><span class="sxs-lookup"><span data-stu-id="cd18a-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="cd18a-119">Válasszon ki egy értéket a Feltöltési hierarchia mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd18a-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="cd18a-120">Válassza az Igen lehetőséget a Szortimentek figyelembevétele mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd18a-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="cd18a-121">Kattintson a Mennyiségek kiszámítása gombra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="cd18a-122">Kattintson a Rendelés létrehozása gombra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-122">Click Create order.</span></span>
14. <span data-ttu-id="cd18a-123">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-123">Click Yes.</span></span>
15. <span data-ttu-id="cd18a-124">A listában keressen meg és jelöljön ki egy raktárat, amely termékeket fogadott.</span><span class="sxs-lookup"><span data-stu-id="cd18a-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="cd18a-125">A kiválasztott raktár létrejött rendeléseinek megtekintéséhez kattintson a Rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="cd18a-125">Click Order to view the orders that got created for the selected warehouse</span></span>

