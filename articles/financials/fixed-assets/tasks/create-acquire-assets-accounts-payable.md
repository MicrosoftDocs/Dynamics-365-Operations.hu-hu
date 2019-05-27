---
title: Eszközök létrehozása és beszerzése a Követelések modulból
description: A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e6c36338cc67855c79ec97d88bb8b633417b85c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562461"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="13413-103">Eszközök létrehozása és beszerzése a Követelések modulból</span><span class="sxs-lookup"><span data-stu-id="13413-103">Create and acquire assets from Accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13413-104">A feladat-útmutató végigvezeti a tárgyi eszköz létrehozásán és a beszerzésén a beszerzési folyamaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="13413-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="13413-105">A Könyvelő és Kötelezettségek ügyintézőket és a bemutató USMF vállalatot használja.</span><span class="sxs-lookup"><span data-stu-id="13413-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="13413-106">Tárgyi eszközök paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="13413-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="13413-107">Ugorjon a Tárgyi eszközök > Beállítás > Tárgyi eszköz paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="13413-107">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="13413-108">Bontsa ki vagy csukja össze a Beszerzési rendelések szakaszt.</span><span class="sxs-lookup"><span data-stu-id="13413-108">Expand or collapse the Purchase orders section.</span></span>
3. <span data-ttu-id="13413-109">Jelölje be a Beszerzés modulból való tárgyieszköz-beszerzés engedélyezése négyzetet.</span><span class="sxs-lookup"><span data-stu-id="13413-109">Check the Allow asset acquisition from Purchasing checkbox.</span></span>
4. <span data-ttu-id="13413-110">Jelölje be a Tárgyi eszköz létrehozása termékbevételezés vagy számla feladása közben négyzetet.</span><span class="sxs-lookup"><span data-stu-id="13413-110">Check the Create asset during product receipt or invoice posting checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="13413-111">Új szállítói számla létrehozása</span><span class="sxs-lookup"><span data-stu-id="13413-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="13413-112">Ugorjon a Kötelezettségek > Munkaterületek > Szállítói számla bevitele elemre.</span><span class="sxs-lookup"><span data-stu-id="13413-112">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="13413-113">Kattintson az Új szállítói számla gombra.</span><span class="sxs-lookup"><span data-stu-id="13413-113">Click New vendor invoice.</span></span>
3. <span data-ttu-id="13413-114">A Számlafiók mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13413-114">In the Invoice account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="13413-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13413-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="13413-116">Érték beírása a Szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="13413-116">In the Number field, type a value.</span></span>
6. <span data-ttu-id="13413-117">A Feladási dátum mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="13413-117">In the Posting date field, enter a date.</span></span>
7. <span data-ttu-id="13413-118">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13413-118">Click Add line.</span></span>
8. <span data-ttu-id="13413-119">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13413-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="13413-120">Nem raktározott cikkek vagy beszerzési kategóriák használhatók tárgyieszköz-beszerzésekhez is.</span><span class="sxs-lookup"><span data-stu-id="13413-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="13413-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13413-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="13413-122">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="13413-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="13413-123">Egy számlasor csak egy tárgyi eszközt hoz létre a mennyiségtől függetlenül.</span><span class="sxs-lookup"><span data-stu-id="13413-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span>  <span data-ttu-id="13413-124">A számlamennyiség mező értékét átviszi a tárgyi eszköz mennyiségbe.</span><span class="sxs-lookup"><span data-stu-id="13413-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="13413-125">Adjon meg egy számot az Egységár mezőben.</span><span class="sxs-lookup"><span data-stu-id="13413-125">In the Unit price field, enter a number.</span></span>
12. <span data-ttu-id="13413-126">Bontsa ki vagy csukja össze a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="13413-126">Expand or collapse the Line details section.</span></span>
13. <span data-ttu-id="13413-127">Kattintson a Tárgyi eszközök lapra.</span><span class="sxs-lookup"><span data-stu-id="13413-127">Click the Fixed assets tab.</span></span>
14. <span data-ttu-id="13413-128">Jelölje be az Új tárgyi eszköz létrehozása jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="13413-128">Check the Create a new fixed asset checkbox.</span></span>
15. <span data-ttu-id="13413-129">A Tárgyieszköz-csoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="13413-129">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="13413-130">A listából válassza ki az új tárgyi eszköz létrehozásakor használni kívánt tárgyieszköz-csoportot.</span><span class="sxs-lookup"><span data-stu-id="13413-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="13413-131">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="13413-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="13413-132">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="13413-132">Click Post.</span></span>
    * <span data-ttu-id="13413-133">A tárgyi eszköz létrejön, és átkerül a számla feladásakor.</span><span class="sxs-lookup"><span data-stu-id="13413-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  

