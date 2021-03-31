---
title: Eszközök létrehozása és beszerzése a Követelések modulból
description: A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb7c92fcab622109b01590d4acadce0d707d3d2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227088"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="dde89-103">Eszközök létrehozása és beszerzése a Követelések modulból</span><span class="sxs-lookup"><span data-stu-id="dde89-103">Create and acquire assets from Accounts payable</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dde89-104">A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="dde89-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="dde89-105">A Könyvelő és Kötelezettségek ügyintézőket és a bemutató USMF vállalatot használja.</span><span class="sxs-lookup"><span data-stu-id="dde89-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="dde89-106">Tárgyi eszközök paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="dde89-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="dde89-107">A **navigációs ablaktáblán** ugorjon a **Modulok > Tárgyi eszközök > Beállítás > Tárgyi eszközök paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="dde89-107">In the **Navigation pane**, go to **Modules > Fixed assets > Setup > Fixed assets parameters**.</span></span>
2. <span data-ttu-id="dde89-108">Bontsa ki a **Beszerzési rendelések** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="dde89-108">Expand the **Purchase orders** fastTab.</span></span>
3. <span data-ttu-id="dde89-109">Jelölje be a **Beszerzés modulból való tárgyieszköz-beszerzés engedélyezése** négyzetet.</span><span class="sxs-lookup"><span data-stu-id="dde89-109">Check the **Allow asset acquisition from Purchasing** checkbox.</span></span>
4. <span data-ttu-id="dde89-110">Jelölje be a **Tárgyi eszköz létrehozása termékbevételezés vagy számla feladása közben** négyzetet.</span><span class="sxs-lookup"><span data-stu-id="dde89-110">Check the **Create asset during product receipt or invoice posting** checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="dde89-111">Új szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="dde89-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="dde89-112">Ugorjon a **Navigációs ablaktábla** – **Modulok > Kötelezettségek > Munkaterületek > Szállítói számla bevitele** elemre.</span><span class="sxs-lookup"><span data-stu-id="dde89-112">In the **Navigation pane**, go to **Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="dde89-113">Kattintson az **Új szállítói számla** gombra.</span><span class="sxs-lookup"><span data-stu-id="dde89-113">Click **New vendor invoice**.</span></span>
3. <span data-ttu-id="dde89-114">A **Számlafiók** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="dde89-114">In the **Invoice account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="dde89-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="dde89-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="dde89-116">Adjon meg egy értéket a **Szám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dde89-116">In the **Number** field, type a value.</span></span>
6. <span data-ttu-id="dde89-117">A **Feladási dátum** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="dde89-117">In the **Posting date** field, enter a date.</span></span>
7. <span data-ttu-id="dde89-118">Kattintson az **Új sor hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="dde89-118">Click **Add line**.</span></span>
8. <span data-ttu-id="dde89-119">A **Cikkszám** mezőben kattintson a legördülő gombra a keresés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="dde89-119">In the **Item number** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="dde89-120">Nem raktározott cikkek vagy beszerzési kategóriák használhatók tárgyieszköz-beszerzésekhez is.</span><span class="sxs-lookup"><span data-stu-id="dde89-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="dde89-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="dde89-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="dde89-122">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dde89-122">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="dde89-123">Egy számlasor csak egy tárgyi eszközt hoz létre a mennyiségtől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="dde89-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span> <span data-ttu-id="dde89-124">A számlamennyiség mező értékét átviszi a tárgyi eszköz mennyiségbe.</span><span class="sxs-lookup"><span data-stu-id="dde89-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="dde89-125">Adjon meg egy számot az **Egységár** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dde89-125">In the **Unit price** field, enter a number.</span></span>
12. <span data-ttu-id="dde89-126">Bontsa ki a **Soradatok** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="dde89-126">Expand the **Line details** fastTab.</span></span>
13. <span data-ttu-id="dde89-127">Kattintson a **Tárgyi eszközök** lapra.</span><span class="sxs-lookup"><span data-stu-id="dde89-127">Click the **Fixed assets** tab.</span></span>
14. <span data-ttu-id="dde89-128">Jelölje be az **Új tárgyi eszköz létrehozása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="dde89-128">Check the **Create a new fixed asset** checkbox.</span></span>
15. <span data-ttu-id="dde89-129">A **Tárgyieszköz-csoport** mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="dde89-129">In the **Fixed asset group** field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="dde89-130">A listából válassza ki az új tárgyi eszköz létrehozásakor használni kívánt tárgyieszköz-csoportot.</span><span class="sxs-lookup"><span data-stu-id="dde89-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="dde89-131">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="dde89-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="dde89-132">Kattintson a **Bejegyzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dde89-132">Click **Post**.</span></span> <span data-ttu-id="dde89-133">A tárgyi eszköz létrejön, és átkerül a számla feladásakor.</span><span class="sxs-lookup"><span data-stu-id="dde89-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]