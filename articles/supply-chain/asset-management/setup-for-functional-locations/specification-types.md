---
title: Karbantartási attribútumtípusok
description: Ez a témakör bemutatja, hogyan lehet attribútumtípusokat létrehozni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b221e9168fc60b5927bb92de80bd6b9614ad591c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019804"
---
# <a name="maintenance-attribute-types"></a><span data-ttu-id="25589-103">Karbantartási attribútumtípusok</span><span class="sxs-lookup"><span data-stu-id="25589-103">Maintenance attribute types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="25589-104">Ez a témakör bemutatja, hogyan lehet attribútumtípusokat létrehozni az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="25589-104">This topic explains how to create attribute types in Asset Management.</span></span> <span data-ttu-id="25589-105">Az attribútumok a különböző elemek tulajdonságainak leírására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="25589-105">Attributes are used to describe the properties of various elements.</span></span> <span data-ttu-id="25589-106">A következő elemeknél lehet beállítani attribútumokat:</span><span class="sxs-lookup"><span data-stu-id="25589-106">You can set up attributes on the following elements:</span></span>

- [<span data-ttu-id="25589-107">Munkavégzési helyszínek típusai</span><span class="sxs-lookup"><span data-stu-id="25589-107">Functional location types</span></span>](../setup-for-functional-locations/functional-location-types.md)
- [<span data-ttu-id="25589-108">Munkavégzési helyszínek létrehozása</span><span class="sxs-lookup"><span data-stu-id="25589-108">Create functional locations</span></span>](../functional-locations/create-functional-locations.md)
- [<span data-ttu-id="25589-109">Eszköztípusok</span><span class="sxs-lookup"><span data-stu-id="25589-109">Asset types</span></span>](../setup-for-objects/object-types.md)
- <span data-ttu-id="25589-110">Eszközök</span><span class="sxs-lookup"><span data-stu-id="25589-110">Assets</span></span>

<span data-ttu-id="25589-111">A beállítható attribútumok az elemtől függően változhatnak.</span><span class="sxs-lookup"><span data-stu-id="25589-111">The attributes that you can set up vary, depending on the element.</span></span> <span data-ttu-id="25589-112">Egy munkavégzési helyszín esetében például a hely konfigurációjához és fizikai méretéhez állíthat be attribútumokat.</span><span class="sxs-lookup"><span data-stu-id="25589-112">For example, for a functional location, you can set up attributes for the configuration and physical size of the location.</span></span> <span data-ttu-id="25589-113">Egy eszköztípus vagy eszköz esetében a motor térfogatához, energiafogyasztásához és maximális terheléséhez különböző feltételek mellett is beállíthat attribútumokat.</span><span class="sxs-lookup"><span data-stu-id="25589-113">For an asset type or an asset, you can set up attributes for engine volume, power consumption, and maximum load capacity under different conditions.</span></span>

## <a name="create-attribute-types"></a><span data-ttu-id="25589-114">Attribútumtípusok létrehozása</span><span class="sxs-lookup"><span data-stu-id="25589-114">Create attribute types</span></span>

<span data-ttu-id="25589-115">Létrehozhatja saját attribútumtípusait.</span><span class="sxs-lookup"><span data-stu-id="25589-115">You can create your own attribute types.</span></span> <span data-ttu-id="25589-116">Ezenkívül a termékdimenziókat áthelyezheti az **Attribútumtípusok** oldalra.</span><span class="sxs-lookup"><span data-stu-id="25589-116">Additionally, you can transfer product dimensions to the **Attribute types** page.</span></span>

1. <span data-ttu-id="25589-117">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Attribútumtípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25589-117">Select **Asset management** \> **Setup** \> **Attribute types**.</span></span>
2. <span data-ttu-id="25589-118">Ha első alkalommal hoz létre attribútumtípusokat, válassza ki a **Termékdimenziók létrehozása** elemet a szabványos termékdimenziók automatikus áthelyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="25589-118">The first time that you set up attribute types, select **Create product dimensions** to automatically transfer standard product dimensions.</span></span>
3. <span data-ttu-id="25589-119">Válassza ki az **Új** lehetőséget egy új attribútumtípus létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="25589-119">Select **New** to create a new attribute type.</span></span>
4. <span data-ttu-id="25589-120">Az **Attribútumtípus** mezőben adja meg az attribútumtípus nevét.</span><span class="sxs-lookup"><span data-stu-id="25589-120">In the **Attribute type** field, enter a name for the attribute type.</span></span>
5. <span data-ttu-id="25589-121">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="25589-121">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="25589-122">Az **Egység** mezőben szükség szerint válassza ki a megfelelő attribútumegységet.</span><span class="sxs-lookup"><span data-stu-id="25589-122">In the **Unit** field, select the relevant attribute unit, as required.</span></span>
7. <span data-ttu-id="25589-123">Az **Adattípus** mezőben válasszon ki egy adattípust az egységhez.</span><span class="sxs-lookup"><span data-stu-id="25589-123">In the **Data type** field, select a data type for the unit.</span></span>
8. <span data-ttu-id="25589-124">Ha a **Karakterláncot** választotta adattípusként, kövesse az alábbi lépéseket az attribútumtípus értékeinek létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="25589-124">If you selected **String** as the data type, follow these steps to create values for the attribute type:</span></span>

    1. <span data-ttu-id="25589-125">Válassza ki az attribútumtípust, majd az **Értékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25589-125">Select the attribute type, and then select **Values**.</span></span>
    2. <span data-ttu-id="25589-126">Az **Attribútumértékek** mezőben válassza ki az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25589-126">In the **Attribute values** field, select **New**.</span></span>
    3. <span data-ttu-id="25589-127">Az **Attribútumtípus** mezőben válasszon ki egy attribútumtípust (dimenziót).</span><span class="sxs-lookup"><span data-stu-id="25589-127">In the **Attribute type** field, select an attribute type (dimension).</span></span>
    4. <span data-ttu-id="25589-128">Az **Érték** mezőben adja meg a kapcsolódó értéket.</span><span class="sxs-lookup"><span data-stu-id="25589-128">In the **Value** field, enter a related value.</span></span>
    5. <span data-ttu-id="25589-129">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="25589-129">In the **Description** field, enter a description.</span></span>
    6. <span data-ttu-id="25589-130">Mentse a rekordot.</span><span class="sxs-lookup"><span data-stu-id="25589-130">Save the record.</span></span>
    7. <span data-ttu-id="25589-131">Térjen vissza az **Attribútumtípusok** oldalra.</span><span class="sxs-lookup"><span data-stu-id="25589-131">Return to the **Attribute types** page.</span></span>

9. <span data-ttu-id="25589-132">Mentse a rekordot.</span><span class="sxs-lookup"><span data-stu-id="25589-132">Save the record.</span></span>

    <span data-ttu-id="25589-133">A **Munkavégzési helyszín típusai** mezőben az attribútumtípust használó munkavégzési helyszínek száma látható.</span><span class="sxs-lookup"><span data-stu-id="25589-133">The **Functional location types** field shows the number of functional locations that are using the attribute type.</span></span> <span data-ttu-id="25589-134">Az **Eszköztípusok** mezőben az azt használó eszköztípusok száma látható.</span><span class="sxs-lookup"><span data-stu-id="25589-134">The **Asset types** field shows the number of asset types that are using it.</span></span>
