---
title: Értékcsökkenési könyvek beállítása (2016. május)
description: Ez a feladat-útmutató új értékcsökkenés könyvet hoz létre, illetve azt egy tárgyieszköz-csoporthoz társítja.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6840e211847494598a81cd3228dbd3796447e18c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186900"
---
# <a name="set-up-depreciation-books-may-2016"></a><span data-ttu-id="1e6d0-103">Értékcsökkenési könyvek beállítása (2016. május)</span><span class="sxs-lookup"><span data-stu-id="1e6d0-103">Set up depreciation books (May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1e6d0-104">Ez a feladat-útmutató új értékcsökkenés könyvet hoz létre, illetve azt egy tárgyieszköz-csoporthoz társítja.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="1e6d0-105">Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="1e6d0-106">Hozzon létre egy értékcsökkenés könyvet.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-106">Create a depreciation book</span></span>
1. <span data-ttu-id="1e6d0-107">Ugorjon a Tárgyi eszközök > Beállítás > Értékcsökkenés könyvek pontra.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="1e6d0-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-108">Click New.</span></span>
3. <span data-ttu-id="1e6d0-109">Írjon egy értéket az Értékcsökkenés könyv mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="1e6d0-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1e6d0-111">Az Értékcsökkenés kiszámítása jelölőnégyzet bejelölése vagy a jelölés törlése.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="1e6d0-112">Az Értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="1e6d0-113">Keresse meg majd válassza ki a listából a kívánt értékcsökkenési profilt.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="1e6d0-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="1e6d0-115">Az Alternatív értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="1e6d0-116">Válassza ki a listából a kívánt értékcsökkenési profilt.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="1e6d0-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1e6d0-118">A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="1e6d0-119">Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="1e6d0-120">Jelölje be az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával jelölőnégyzetet vagy törölje a jelölést.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="1e6d0-121">A Naptár mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="1e6d0-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="1e6d0-123">Társítsa az értékcsökkenés könyvet egy tárgyieszköz-csoporthoz</span><span class="sxs-lookup"><span data-stu-id="1e6d0-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="1e6d0-124">Kattintson a Tárgyieszköz-csoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="1e6d0-125">A Tárgyieszköz-csoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="1e6d0-126">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="1e6d0-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1e6d0-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="1e6d0-128">Válassza ki valamelyik lehetőséget az Értékcsökkenési szabály mezőben.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="1e6d0-129">Adjon meg egy számot az Élettartam mezőben.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="1e6d0-130">Figyelje meg, hogy az Értékcsökkenési időszakok mező értéke az Élettartam beállítását követően kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="1e6d0-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

