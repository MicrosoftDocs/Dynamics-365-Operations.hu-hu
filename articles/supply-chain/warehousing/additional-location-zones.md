---
title: További helyzónák
description: Ez a témakör áttekintést nyújt a Microsoft rendszerhez hozzáadott új helyzónákról Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: AnnBe
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9727187ad555f9e3d09beed3f3447a22c29ed22a
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530167"
---
# <a name="additional-location-zones"></a><span data-ttu-id="f4157-103">További helyzónák</span><span class="sxs-lookup"><span data-stu-id="f4157-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4157-104">Három új zónamező érhető el a Microsoft Dynamics 365 Supply Chain Management modulban.</span><span class="sxs-lookup"><span data-stu-id="f4157-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="f4157-105">A raktárkezelők segítségével további raktári szervezeteket és elrendezéseket lehet definiálni.</span><span class="sxs-lookup"><span data-stu-id="f4157-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="f4157-106">Az új zónamezőket manuálisan vagy a **Hely beállítása** varázsló használatával lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="f4157-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="f4157-107">Ezek Helyek táblát használó lekérdezésekben vagy szűrésekben használhatók.</span><span class="sxs-lookup"><span data-stu-id="f4157-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="f4157-108">Nincs szükség további beállításra a zónamezők használatához.</span><span class="sxs-lookup"><span data-stu-id="f4157-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="f4157-109">A További helyzóna funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="f4157-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="f4157-110">A *További helyzóna* funkciót használata előtt be kell kapcsolni a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f4157-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="f4157-111">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="f4157-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f4157-112">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="f4157-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f4157-113">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="f4157-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f4157-114">**Funkciónév:** *További helyzóna*</span><span class="sxs-lookup"><span data-stu-id="f4157-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="f4157-115">Helyzónák használata</span><span class="sxs-lookup"><span data-stu-id="f4157-115">Use location zones</span></span>

1. <span data-ttu-id="f4157-116">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Hely beállítása varázslóra**.</span><span class="sxs-lookup"><span data-stu-id="f4157-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="f4157-117">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="f4157-117">Set the following values:</span></span>

    - <span data-ttu-id="f4157-118">A **Raktár** mezőben válassza ki az _62_ értéket.</span><span class="sxs-lookup"><span data-stu-id="f4157-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="f4157-119">A **Zóna azonosítója** mezőben válassza ki a _EMELET_ elemet.</span><span class="sxs-lookup"><span data-stu-id="f4157-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="f4157-120">Az **1. további helyzóna** mezőben válassza ki a _PICKZONE1_ elemet.</span><span class="sxs-lookup"><span data-stu-id="f4157-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="f4157-121">Az **2. további helyzóna** mezőben válassza ki a _WEBSHOP1_ elemet.</span><span class="sxs-lookup"><span data-stu-id="f4157-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="f4157-122">A **Helyprofil azonosítója** mezőben válassza ki az _EMELET_ elemet.</span><span class="sxs-lookup"><span data-stu-id="f4157-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="f4157-123">Válassza ki az **Emelet** sort.</span><span class="sxs-lookup"><span data-stu-id="f4157-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="f4157-124">A **Kezdő szám** mezőben adja meg az _1_-es számot.</span><span class="sxs-lookup"><span data-stu-id="f4157-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="f4157-125">A **Befejező szám** mezőben adja meg az _3_-es számot.</span><span class="sxs-lookup"><span data-stu-id="f4157-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="f4157-126">Válassza ki a **Folyosó** sort.</span><span class="sxs-lookup"><span data-stu-id="f4157-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="f4157-127">A **Kezdő szám** mezőben adja meg az _1_-es számot.</span><span class="sxs-lookup"><span data-stu-id="f4157-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="f4157-128">A **Befejező szám** mezőben adja meg az _5_-ös számot.</span><span class="sxs-lookup"><span data-stu-id="f4157-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="f4157-129">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f4157-129">Select **Create**.</span></span>
8. <span data-ttu-id="f4157-130">Olyan üzeneteket kap, amelyek tájékoztatnak az új helyek hozzáadásáról.</span><span class="sxs-lookup"><span data-stu-id="f4157-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="f4157-131">Válassza ki az **Üzenetek megjelenítése** gombot az üzenetek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="f4157-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="f4157-132">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**.</span><span class="sxs-lookup"><span data-stu-id="f4157-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="f4157-133">Az új helyek megjelennek a listán, és az összes zónamező elérhető (azaz a meglévő zónamezőn kívül az új zónamezők is).</span><span class="sxs-lookup"><span data-stu-id="f4157-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
