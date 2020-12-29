---
title: Rövid kitárolásra jelölt cikkek újbóli felosztásának beállítása
description: Ez a témakör bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e8f5c23f82e96145f411ec993f766a90137b5b8
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429873"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="2d1bb-103">Rövid kitárolásra jelölt cikkek újbóli felosztásának beállítása</span><span class="sxs-lookup"><span data-stu-id="2d1bb-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d1bb-104">Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="2d1bb-105">Az újrafelosztási folyamatot egy **Munkakivétel** vezérli, és a raktári **dolgozó** használja.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="2d1bb-106">Lehetőség van Automatikus, Kézi vagy mindkét újrafelosztási folyamat használatára:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="2d1bb-107">Automatikus újrafelosztás – A rendszer a helyutasítások használatával határozza meg, hogy az áruk egy másik helyen elérhetők-e.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="2d1bb-108">Ha lehetséges, a program frissíti a munkát, és a rendszer átirányítja a raktári felhasználót az alternatív helyre.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="2d1bb-109">Manuális újrafelosztás – Lehetővé teszi a raktári felhasználó számára, hogy válasszon egy vagy több nem lefoglalt mennyiségű áruval rendelkező hely közül.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="2d1bb-110">Automatikus és manuális – Ha a rendszer nem képes automatikus újrafelosztásra, és a nem lefoglalt mennyiséggel rendelkező helyek érhetők el, akkor a program felkéri a felhasználót, hogy válasszon egy helyet.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="2d1bb-111">Munkakivételek beállítása</span><span class="sxs-lookup"><span data-stu-id="2d1bb-111">Set up work exceptions</span></span>
<span data-ttu-id="2d1bb-112">Lehetőség van több munkakivétel meghatározására eltérő cikkfelosztási irányelvekkel, amelyek lehetővé teszik, hogy a raktáros válasszon egyet a feldolgozott szállítmány szükségletei szerint.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="2d1bb-113">Az USMF bemutatócég adatai kerültek felhasználásra a jelen eljárás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="2d1bb-114">A **Navigációs ablaktáblán** ugorjon a **Raktárkezelés > Beállítás > Munka > Munkakivételek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="2d1bb-115">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-115">Click **New**</span></span> 
3. <span data-ttu-id="2d1bb-116">Adjon meg egy értéket a **Munkakivételkód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="2d1bb-117">Ez lesz a kivétel címe.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-117">This will be the title of this exception .</span></span> <span data-ttu-id="2d1bb-118">Például: Rövid kitárolási kézikönyv.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="2d1bb-119">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="2d1bb-120">Ez a kivétel használatának rövid leírása lesz.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="2d1bb-121">Például: Rövid kitárolás – a cikk nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="2d1bb-122">A **Kivétel típus** mezőben válassza ki a **Rövid kitárolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="2d1bb-123">Jelölje be a **Készlethelyesbítés** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="2d1bb-124">Ha ki van választva, automatikusan megtörténik a készlet helyesbítése 0-ra a rövid kitárolás helyén.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="2d1bb-125">Adjon meg vagy válasszon ki egy értéket az **Alapértelmezett helyesbítéstípus-kód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="2d1bb-126">Például az USMF-ben kiválaszthatja a **Remove Res Adj Out** elemet. Minden Helyesbítésitípus-kód négy jellemzőt tartalmaz: név, leírás, készletnapló neve, és a **Foglalások eltávolítása**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="2d1bb-127">Ha a **Foglalások eltávolítása** lehetőséget engedélyezi, a program eltávolítja a rövid kitárolású rendelési sor foglalásait.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="2d1bb-128">A **Cikk újbóli felosztása** mezőben válasszon egy értéket, mint például a Kézi.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="2d1bb-129">Ha bejelöli a manuális, vagy az automatikus és manuális lehetőséget, a raktáros számára engedélyezni kell a manuális újbóli felosztást.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="2d1bb-130">A dolgozó beállítása a manuális cikk-újbólifelosztás használatára</span><span class="sxs-lookup"><span data-stu-id="2d1bb-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="2d1bb-131">Az USMF bemutatócég adatai kerültek felhasználásra a jelen eljárás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="2d1bb-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-132">Close the page.</span></span>
2. <span data-ttu-id="2d1bb-133">A **Navigációs ablaktáblán** ugorjon a **Raktárkezelés > Beállítás > Dolgozó >** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="2d1bb-134">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-134">Click **Edit**.</span></span>
4. <span data-ttu-id="2d1bb-135">A listában válassza a dolgozót.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-135">In the list, select worker.</span></span> <span data-ttu-id="2d1bb-136">Példa: Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="2d1bb-137">Bontsa ki a **Felhasználók** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="2d1bb-138">A listában válasszon ki egy **Felhasználóazonosító** elemet.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="2d1bb-139">Például, 24 elem.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-139">For example, 24.</span></span>
7. <span data-ttu-id="2d1bb-140">Bontsa ki a **Munka** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="2d1bb-141">Válassza ki az **Igen** lehetőséget a **Cikk újbóli manuális felosztásának engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>
