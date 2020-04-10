---
title: Értékcsökkenési könyvek beállítása
description: Ez az eljárás végigvezeti egy új értékcsökkenési könyv létrehozási folyamatán, és annak hozzárendelésén egy tárgyieszköz-csoporthoz.
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
ms.openlocfilehash: 03f915fa91e0eeff2f26ab9a60bbd5118317e853
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154600"
---
# <a name="set-up-depreciation-books"></a><span data-ttu-id="79803-103">Értékcsökkenési könyvek beállítása</span><span class="sxs-lookup"><span data-stu-id="79803-103">Set up depreciation books</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79803-104">Ez az eljárás végigvezeti egy új értékcsökkenési könyv létrehozási folyamatán, és annak hozzárendelésén egy tárgyieszköz-csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="79803-104">This procedure walks through the process of creating a new depreciation book and associate it with a fixed asset group.</span></span> 

## <a name="create-a-depreciation-book"></a><span data-ttu-id="79803-105">Hozzon létre egy értékcsökkenés könyvet.</span><span class="sxs-lookup"><span data-stu-id="79803-105">Create a depreciation book</span></span>
1. <span data-ttu-id="79803-106">Ugorjon a Tárgyi eszközök > Beállítás > Értékcsökkenés könyvek pontra.</span><span class="sxs-lookup"><span data-stu-id="79803-106">Go to Fixed assets > Setup > Depreciation books.</span></span>
2. <span data-ttu-id="79803-107">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="79803-107">Click New.</span></span>
3. <span data-ttu-id="79803-108">Írjon egy értéket az Értékcsökkenés könyv mezőbe.</span><span class="sxs-lookup"><span data-stu-id="79803-108">In the Depreciation book field, type a value.</span></span>
4. <span data-ttu-id="79803-109">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="79803-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="79803-110">Az Értékcsökkenés kiszámítása jelölőnégyzet bejelölése vagy a jelölés törlése.</span><span class="sxs-lookup"><span data-stu-id="79803-110">Check or uncheck the Calculate depreciation checkbox.</span></span>
6. <span data-ttu-id="79803-111">Az Értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79803-111">In the Depreciation profile field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="79803-112">Keresse meg majd válassza ki a listából a kívánt értékcsökkenési profilt.</span><span class="sxs-lookup"><span data-stu-id="79803-112">In the list, find and select the desired depreciation profile.</span></span>
8. <span data-ttu-id="79803-113">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="79803-113">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="79803-114">Az Alternatív értékcsökkenési profil mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79803-114">In the Alternative depreciation profile field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="79803-115">Válassza ki a listából a kívánt értékcsökkenési profilt.</span><span class="sxs-lookup"><span data-stu-id="79803-115">In the list, select the desired depreciation profile.</span></span>
11. <span data-ttu-id="79803-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="79803-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="79803-117">A Rendkívüli értékcsökkenési profil egy adott eszköz további értékcsökkenéséhez használható nem szokványos körülmények esetén.</span><span class="sxs-lookup"><span data-stu-id="79803-117">The Extraordinary depreciation profile is used for additional depreciation of an asset in unusual circumstances.</span></span> <span data-ttu-id="79803-118">Ezt például akkor alkalmazhatja, ha természeti katasztrófa okozta értékcsökkenést kell rögzítenie.</span><span class="sxs-lookup"><span data-stu-id="79803-118">For example, you might use this to record depreciation that results from a natural disaster.</span></span>  
12. <span data-ttu-id="79803-119">Jelölje be az Értékcsökkenés kiigazítása az értékcsökkenési alap kiigazításával jelölőnégyzetet vagy törölje a jelölést.</span><span class="sxs-lookup"><span data-stu-id="79803-119">Check or uncheck the Create depreciation adjustments with basis adjustments checkbox.</span></span>
13. <span data-ttu-id="79803-120">A Naptár mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79803-120">In the Calendar field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="79803-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="79803-121">In the list, click the link in the selected row.</span></span>

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a><span data-ttu-id="79803-122">Társítsa az értékcsökkenés könyvet egy tárgyieszköz-csoporthoz</span><span class="sxs-lookup"><span data-stu-id="79803-122">Associate the depreciation book with a fixed asset group</span></span>
1. <span data-ttu-id="79803-123">Kattintson a Tárgyieszköz-csoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="79803-123">Click Fixed asset groups.</span></span>
2. <span data-ttu-id="79803-124">A Tárgyieszköz-csoport mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="79803-124">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="79803-125">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="79803-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="79803-126">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="79803-126">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="79803-127">Válassza ki valamelyik lehetőséget az Értékcsökkenési szabály mezőben.</span><span class="sxs-lookup"><span data-stu-id="79803-127">In the Depreciation convention field, select an option.</span></span>
6. <span data-ttu-id="79803-128">Adjon meg egy számot az Élettartam mezőben.</span><span class="sxs-lookup"><span data-stu-id="79803-128">In the Service life field, enter a number.</span></span>
    * <span data-ttu-id="79803-129">Figyelje meg, hogy az Értékcsökkenési időszakok mező értéke az Élettartam beállítását követően kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="79803-129">Notice the Depreciation periods field value is calculated after setting the Service life.</span></span>  

