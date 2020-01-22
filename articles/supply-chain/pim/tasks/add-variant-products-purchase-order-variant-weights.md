---
title: Változattermék hozzáadása beszerzési rendelésekhez változatsúlyokkal
description: Ez az eljárás azt mutatja be, hogy milyen lépések segítségével tudja a változatsúlyokat felhasználni a beszerzési-megrendelés sorok automatikus kitöltéséhez mindegyik termékváltozatra.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adb2300e51f8b5383eee4dea0dffe4129dc8a536
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934817"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a><span data-ttu-id="a0bb7-103">Változattermék hozzáadása beszerzési rendelésekhez változatsúlyokkal</span><span class="sxs-lookup"><span data-stu-id="a0bb7-103">Add variant products to purchase orders using variant weights</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0bb7-104">Ez az eljárás azt mutatja be, hogy milyen lépések segítségével tudja a változatsúlyokat felhasználni a beszerzési-megrendelés sorok automatikus kitöltéséhez mindegyik termékváltozatra.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-104">This procedure walks through the steps for using variant weights to auto populate purchase order lines for each variant of a product.</span></span> <span data-ttu-id="a0bb7-105">A beszerezni kívánt termék mennyiségének kiválasztásakor, a rendszer, a termékváltozatokhoz konfigurált súlyok alapján meghatározott javasolt mennyiségeket tartalmazó beszerzési-rendelés sort hoz létre az összes termékváltozathoz.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-105">When you select the quantity of the product you want to purchase, purchase order lines are created for all the variants of the product with suggested quantities based on the weights configured on the product variants.</span></span> <span data-ttu-id="a0bb7-106">Ez az eljárás nem tárgyalja a súlyok, a termékdimenziók és termékváltozatok kapcsán történő konfigurálásához szükséges lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-106">This procedure doesn’t include steps to configure weight values on product dimensions and product variants.</span></span> <span data-ttu-id="a0bb7-107">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-107">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="a0bb7-108">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="a0bb7-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-109">Click New.</span></span>
3. <span data-ttu-id="a0bb7-110">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-110">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a0bb7-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a0bb7-112">Az Általános szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-112">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="a0bb7-113">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-113">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="a0bb7-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a0bb7-115">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-115">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a0bb7-116">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-116">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a0bb7-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="a0bb7-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-118">Click OK.</span></span>
12. <span data-ttu-id="a0bb7-119">Bontsa ki a Sorok részletei részt.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-119">Toggle the expansion of the Line details section.</span></span>
13. <span data-ttu-id="a0bb7-120">Kattintson a Változatok fülre.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-120">Click the Variants tab.</span></span>
14. <span data-ttu-id="a0bb7-121">Kattintson az Új sor hozzáadására.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-121">Click Add line.</span></span>
15. <span data-ttu-id="a0bb7-122">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="a0bb7-123">A cikkszám mezőbe írja be a „0140” értéket.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-123">In the Item number field, type '0140'.</span></span>
17. <span data-ttu-id="a0bb7-124">Állítsa a mennyiséget 1000 értékre.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-124">Set Quantity to '1000'.</span></span>
18. <span data-ttu-id="a0bb7-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a0bb7-125">Click Save.</span></span>

