---
title: "Hibrid vevői rendelések"
description: "A hibrid vevői rendelés lehet egyetlen rendelés, amely az ügyfél által az üzletből kivihető termékeket tartalmaz, illetve tartalmazhat olyan termékeket, amelyek átvételére vagy kiszállítására később kerül sor."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3b330b64c1427517866b17b62ac441a4a8bed2f0
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="hybrid-customer-orders"></a><span data-ttu-id="a9da7-103">Hibrid vevői rendelések</span><span class="sxs-lookup"><span data-stu-id="a9da7-103">Hybrid customer orders</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="a9da7-104">A hibrid vevői rendelés lehet egyetlen rendelés, amely az ügyfél által az üzletből kivihető termékeket tartalmaz, illetve tartalmazhat olyan termékeket, amelyek átvételére vagy kiszállítására később kerül sor.</span><span class="sxs-lookup"><span data-stu-id="a9da7-104">A hybrid customer order is a single order, which contains products that can be carried out of the store by the customer, as well as products that will be picked up or shipped later.</span></span>

<span data-ttu-id="a9da7-105">A Microsoft Dynamics 365 for Retail programban választhatja az összes termék végrehajtását, vagy végrehajthat kijelölt termékeket az adott vevői rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="a9da7-105">In Microsoft Dynamics 365 for Retail, you can select either carry out all products or carry out selected products for a customer order.</span></span> <span data-ttu-id="a9da7-106">A végrehajtandóként megjelölt terméksorok számlázása automatikusan megtörténik a rendelés létrehozása után, és hasonlóképpen azon megrendeléseknél, amelyek átvétele a rendelés létrehozása után történik.</span><span class="sxs-lookup"><span data-stu-id="a9da7-106">The product lines that are marked as carry out are automatically invoiced after the order is created, similarly this is the same for an order that is to be picked-up after the order is created.</span></span> <span data-ttu-id="a9da7-107">A hibrid rendeléseknél esedékes összeg meghatározása a végrehajtandó sorokhoz a letéti százalék hozzáadásával történik a kitárolási és szállítási soroknál.</span><span class="sxs-lookup"><span data-stu-id="a9da7-107">The amount due on hybrid orders is determined by adding the deposit percentage on pick and ship product lines with the full amount of the carry out lines.</span></span> <span data-ttu-id="a9da7-108">A hibrid rendelések esetén a rendszer az alábbiak szerint vált a vevői rendelési mód és a cash and carry mód között:</span><span class="sxs-lookup"><span data-stu-id="a9da7-108">For hybrid orders, the system switches between customer order mode and cash and carry mode as follows:</span></span>

-   <span data-ttu-id="a9da7-109">Ha a bevásárlókosárban található összes termék **Szállítás elvégzése** értékre van állítva, a rendelést a rendszer Cash and Carry tranzakcióként fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="a9da7-109">If all products in the cart are set to **Carry out delivery**, the order will be handled as a Cash and Carry transaction.</span></span>
-   <span data-ttu-id="a9da7-110">Ha a kosár bármely vagy összes sora **Kitárolás** vagy **Kiszállítás** értékre van állítva, a rendelést a rendszert vevői rendelési tranzakcióként fogja kezelni.</span><span class="sxs-lookup"><span data-stu-id="a9da7-110">If any or all lines in the cart are set to either **Pick** or **ship delivery**, the order will be handled as a Customer order transaction.</span></span>

<span data-ttu-id="a9da7-111">Ha a bevásárlókocsi egy soránál kiválasztja a **Kijelölt kitárolása**, **Kijelölt szállítása** vagy **Kiválasztott elvégzése** értéket, ez a szállítási mód csak az adott bevásárlókocsisorra lesz érvényes.</span><span class="sxs-lookup"><span data-stu-id="a9da7-111">If a cart line is selected and **Pick selected**, **Ship selected**, or **Carry out selected** is selected, only the specific cart line is set with that delivery method.</span></span> <span data-ttu-id="a9da7-112">Ebben az esetben a művelet lefelé irányuló folyamata a szokásos módon folytatódik.</span><span class="sxs-lookup"><span data-stu-id="a9da7-112">In that case, the downstream flow of the operation continues as usual.</span></span> <span data-ttu-id="a9da7-113">Azonban ha a **Kijelölt kitárolása**, **Kijelölt szállítása**, vagy **Kiválasztott elvégzése** lehetőséget anélkül választja ki, hogy a bevásárlókocsi egy sora ki lenne jelölve, megnyílik egy új lap, amely az összes bevásárlókocsi-sort felsorolja.</span><span class="sxs-lookup"><span data-stu-id="a9da7-113">However, if **Pick selected**, **Ship selected**, or **Carry out selected** is selected without a cart line being selected, a new page opens that lists all the cart lines.</span></span> <span data-ttu-id="a9da7-114">Ezen a képernyőn több sort kijelölhet egyszerre a kézbesítési mód beállítására.</span><span class="sxs-lookup"><span data-stu-id="a9da7-114">On that screen, you can select multiple lines at once for setting the delivery method.</span></span> <span data-ttu-id="a9da7-115">Ha ezt a módszert használja sorok kijelöléséhez, a rendszer az adott sorhoz rendelt minden korábbi kézbesítési módot felülbírálja.</span><span class="sxs-lookup"><span data-stu-id="a9da7-115">When you use that method for selecting lines, any previous delivery method that has been assigned to the line will be overridden.</span></span>

<a name="see-also"></a><span data-ttu-id="a9da7-116">Lásd még</span><span class="sxs-lookup"><span data-stu-id="a9da7-116">See also</span></span>
--------

[<span data-ttu-id="a9da7-117">Vevői rendelések – áttekintés</span><span class="sxs-lookup"><span data-stu-id="a9da7-117">Customer orders overview</span></span>](customer-orders-overview.md)




