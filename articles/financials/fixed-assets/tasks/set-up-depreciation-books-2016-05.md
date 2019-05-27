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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566915"
---
# <a name="set-up-depreciation-books-may-2016"></a><span data-ttu-id="af59b-103">Értékcsökkenési könyvek beállítása (2016. május)</span><span class="sxs-lookup"><span data-stu-id="af59b-103">Set up depreciation books (May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="af59b-104">Ez a feladat-útmutató új értékcsökkenés könyvet hoz létre, illetve azt egy tárgyieszköz-csoporthoz társítja.</span><span class="sxs-lookup"><span data-stu-id="af59b-104">This task guide will create a new depreciation book and associate it with a fixed asset group.</span></span>  <span data-ttu-id="af59b-105">Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="af59b-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-depreciation-book"></a><span data-ttu-id="af59b-106">Hozzon létre egy értékcsökkenés könyvet.</span><span class="sxs-lookup"><span data-stu-id="af59b-106">Create a depreciation book</span></span>
1. <span data-ttu-id="af59b-107">Ugorjon a Tárgyi eszközök > Beállítás > Értékcsökkenés könyvek pontra.</span><span class="sxs-lookup"><span data-stu-id="af59b-107">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="af59b-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="af59b-108">Click New.</span></span>
3. <span data-ttu-id="af59b-109">Írjon egy értéket az Értékcsökkenés könyv mezőbe.</span><span class="sxs-lookup"><span data-stu-id="af59b-109">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="af59b-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="af59b-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="af59b-111">Az Értékcsökkenés kiszámítása jelölőnégyzet bejelölése vagy a jelölés törlése.</span><span class="sxs-lookup"><span data-stu-id="af59b-111">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="af59b-112">Az Értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="af59b-112">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="af59b-113">Keresse meg majd válassza ki a listából a kívánt értékcsökkenési profilt.</span><span class="sxs-lookup"><span data-stu-id="af59b-113">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="af59b-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="af59b-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="af59b-115">Az Alternatív értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="af59b-115">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="af59b-116">Válassza ki a listából a kívánt értékcsökkenési profilt.</span><span class="sxs-lookup"><span data-stu-id="af59b-116">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="af59b-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="af59b-117">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="af59b-118">A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén.</span><span class="sxs-lookup"><span data-stu-id="af59b-118">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="af59b-119">Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.</span><span class="sxs-lookup"><span data-stu-id="af59b-119">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="af59b-120">Jelölje be az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával jelölőnégyzetet vagy törölje a jelölést.</span><span class="sxs-lookup"><span data-stu-id="af59b-120">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="af59b-121">A Naptár mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="af59b-121">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="af59b-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="af59b-122">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="af59b-123">Társítsa az értékcsökkenés könyvet egy tárgyieszköz-csoporthoz</span><span class="sxs-lookup"><span data-stu-id="af59b-123">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="af59b-124">Kattintson a Tárgyieszköz-csoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="af59b-124">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="af59b-125">A Tárgyieszköz-csoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="af59b-125">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="af59b-126">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="af59b-126">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="af59b-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="af59b-127">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="af59b-128">Válassza ki valamelyik lehetőséget az Értékcsökkenési szabály mezőben.</span><span class="sxs-lookup"><span data-stu-id="af59b-128">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="af59b-129">Adjon meg egy számot az Élettartam mezőben.</span><span class="sxs-lookup"><span data-stu-id="af59b-129">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="af59b-130">Figyelje meg, hogy az Értékcsökkenési időszakok mező értéke az Élettartam beállítását követően kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="af59b-130">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

