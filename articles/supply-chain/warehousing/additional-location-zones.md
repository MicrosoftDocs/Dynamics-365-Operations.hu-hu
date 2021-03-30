---
title: További helyzónák
description: Ez a témakör áttekintést nyújt a Microsoft rendszerhez hozzáadott új helyzónákról Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4e8d8ddb65ea49f3d5278db0cac6ae891ab40ecf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233223"
---
# <a name="additional-location-zones"></a><span data-ttu-id="64fb6-103">További helyzónák</span><span class="sxs-lookup"><span data-stu-id="64fb6-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64fb6-104">Három új zónamező érhető el a Microsoft Dynamics 365 Supply Chain Management modulban.</span><span class="sxs-lookup"><span data-stu-id="64fb6-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="64fb6-105">A raktárkezelők segítségével további raktári szervezeteket és elrendezéseket lehet definiálni.</span><span class="sxs-lookup"><span data-stu-id="64fb6-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="64fb6-106">Az új zónamezőket manuálisan vagy a **Hely beállítása** varázsló használatával lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="64fb6-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="64fb6-107">Ezek Helyek táblát használó lekérdezésekben vagy szűrésekben használhatók.</span><span class="sxs-lookup"><span data-stu-id="64fb6-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="64fb6-108">Nincs szükség további beállításra a zónamezők használatához.</span><span class="sxs-lookup"><span data-stu-id="64fb6-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="64fb6-109">A További helyzóna funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="64fb6-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="64fb6-110">A *További helyzóna* funkciót használata előtt be kell kapcsolni a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="64fb6-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="64fb6-111">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="64fb6-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="64fb6-112">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="64fb6-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="64fb6-113">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="64fb6-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="64fb6-114">**Funkciónév:** *További helyzóna*</span><span class="sxs-lookup"><span data-stu-id="64fb6-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="64fb6-115">Helyzónák használata</span><span class="sxs-lookup"><span data-stu-id="64fb6-115">Use location zones</span></span>

1. <span data-ttu-id="64fb6-116">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Hely beállítása varázslóra**.</span><span class="sxs-lookup"><span data-stu-id="64fb6-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="64fb6-117">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="64fb6-117">Set the following values:</span></span>

    - <span data-ttu-id="64fb6-118">A **Raktár** mezőben válassza ki az _62_ értéket.</span><span class="sxs-lookup"><span data-stu-id="64fb6-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="64fb6-119">A **Zóna azonosítója** mezőben válassza ki a _EMELET_ elemet.</span><span class="sxs-lookup"><span data-stu-id="64fb6-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="64fb6-120">Az **1. további helyzóna** mezőben válassza ki a _PICKZONE1_ elemet.</span><span class="sxs-lookup"><span data-stu-id="64fb6-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="64fb6-121">Az **2. további helyzóna** mezőben válassza ki a _WEBSHOP1_ elemet.</span><span class="sxs-lookup"><span data-stu-id="64fb6-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="64fb6-122">A **Helyprofil azonosítója** mezőben válassza ki az _EMELET_ elemet.</span><span class="sxs-lookup"><span data-stu-id="64fb6-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="64fb6-123">Válassza ki az **Emelet** sort.</span><span class="sxs-lookup"><span data-stu-id="64fb6-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="64fb6-124">A **Kezdő szám** mezőben adja meg az _1_-es számot.</span><span class="sxs-lookup"><span data-stu-id="64fb6-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="64fb6-125">A **Befejező szám** mezőben adja meg az _3_-es számot.</span><span class="sxs-lookup"><span data-stu-id="64fb6-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="64fb6-126">Válassza ki a **Folyosó** sort.</span><span class="sxs-lookup"><span data-stu-id="64fb6-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="64fb6-127">A **Kezdő szám** mezőben adja meg az _1_-es számot.</span><span class="sxs-lookup"><span data-stu-id="64fb6-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="64fb6-128">A **Befejező szám** mezőben adja meg az _5_-ös számot.</span><span class="sxs-lookup"><span data-stu-id="64fb6-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="64fb6-129">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64fb6-129">Select **Create**.</span></span>
8. <span data-ttu-id="64fb6-130">Olyan üzeneteket kap, amelyek tájékoztatnak az új helyek hozzáadásáról.</span><span class="sxs-lookup"><span data-stu-id="64fb6-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="64fb6-131">Válassza ki az **Üzenetek megjelenítése** gombot az üzenetek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="64fb6-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="64fb6-132">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**.</span><span class="sxs-lookup"><span data-stu-id="64fb6-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="64fb6-133">Az új helyek megjelennek a listán, és az összes zónamező elérhető (azaz a meglévő zónamezőn kívül az új zónamezők is).</span><span class="sxs-lookup"><span data-stu-id="64fb6-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]