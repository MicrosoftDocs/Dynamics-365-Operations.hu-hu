---
title: Változattermék hozzáadása beszerzési rendelésekhez változatsúlyokkal
description: Ez az eljárás azt mutatja be, hogy milyen lépések segítségével tudja a változatsúlyokat felhasználni a beszerzési-megrendelés sorok automatikus kitöltéséhez mindegyik termékváltozatra.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cd4ca3652c1ce7422e8f80426a7b11545e09861
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242565"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="e57e1-103">Változattermék hozzáadása beszerzési rendelésekhez változatsúlyokkal</span><span class="sxs-lookup"><span data-stu-id="e57e1-103">Add variant products to purchase orders using variant weights</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e57e1-104">Ez az eljárás azt mutatja be, hogy milyen lépések segítségével tudja a változatsúlyokat felhasználni a beszerzési-megrendelés sorok automatikus kitöltéséhez mindegyik termékváltozatra.</span><span class="sxs-lookup"><span data-stu-id="e57e1-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="e57e1-105">A beszerezni kívánt termék mennyiségének kiválasztásakor, a rendszer, a termékváltozatokhoz konfigurált súlyok alapján meghatározott javasolt mennyiségeket tartalmazó beszerzési-rendelés sort hoz létre az összes termékváltozathoz.</span><span class="sxs-lookup"><span data-stu-id="e57e1-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="e57e1-106">Ez az eljárás nem tárgyalja a súlyok, a termékdimenziók és termékváltozatok kapcsán történő konfigurálásához szükséges lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e57e1-106">This procedure doesn't include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="e57e1-107">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="e57e1-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="e57e1-108">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="e57e1-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="e57e1-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e57e1-109">Click New.</span></span>
3. <span data-ttu-id="e57e1-110">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e57e1-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e57e1-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e57e1-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e57e1-112">Az Általános szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="e57e1-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="e57e1-113">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e57e1-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e57e1-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e57e1-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="e57e1-115">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e57e1-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="e57e1-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="e57e1-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="e57e1-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e57e1-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="e57e1-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e57e1-118">Click OK.</span></span>
12. <span data-ttu-id="e57e1-119">Bontsa ki a Sorok részletei részt.</span><span class="sxs-lookup"><span data-stu-id="e57e1-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="e57e1-120">Kattintson a Változatok fülre.</span><span class="sxs-lookup"><span data-stu-id="e57e1-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="e57e1-121">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="e57e1-121">Click Add line.</span></span>
15. <span data-ttu-id="e57e1-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e57e1-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="e57e1-123">A cikkszám mezőbe írja be a „0140” értéket.</span><span class="sxs-lookup"><span data-stu-id="e57e1-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="e57e1-124">Állítsa a mennyiséget 1000 értékre.</span><span class="sxs-lookup"><span data-stu-id="e57e1-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="e57e1-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e57e1-125">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]