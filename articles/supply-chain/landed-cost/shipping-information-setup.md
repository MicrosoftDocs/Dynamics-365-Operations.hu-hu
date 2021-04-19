---
title: Szállítási adatok beállítása
description: Ez a témakör azt ismerteti, hogyan lehet szállítási adatokat beállítani a Partraszállítási költség modulhoz.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 74ac7e0eac545369eef1a48f0085c820a4728e75
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833689"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="a7099-103">Szállítási adatok beállítása</span><span class="sxs-lookup"><span data-stu-id="a7099-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7099-104">Ez a témakör azt ismerteti, hogyan lehet szállítási adatokat beállítani a **Partraszállítási költség** modulhoz.</span><span class="sxs-lookup"><span data-stu-id="a7099-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="a7099-105">Áruk leírása</span><span class="sxs-lookup"><span data-stu-id="a7099-105">Description of goods</span></span>

<span data-ttu-id="a7099-106">Az áruk leírása elősegíti a hajóút, a szállítókonténer vagy az árulevelek és a benne lévő áruk azonosítását.</span><span class="sxs-lookup"><span data-stu-id="a7099-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="a7099-107">Az áruk leírása a szállítókonténer fejlécében vagy az árulevél fejlécében választható ki.</span><span class="sxs-lookup"><span data-stu-id="a7099-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="a7099-108">Az áruk leírásával a **Partraszállítási költség \> Szállítási adatok beállítása \> Áruk leírása** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="a7099-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="a7099-109">Itt lehet megtekinteni, megnyitni, létrehozni és törölni az áruk leírásait.</span><span class="sxs-lookup"><span data-stu-id="a7099-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="a7099-110">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="a7099-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="a7099-111">Mező</span><span class="sxs-lookup"><span data-stu-id="a7099-111">Field</span></span> | <span data-ttu-id="a7099-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-112">Description</span></span> |
|---|---|
| <span data-ttu-id="a7099-113">Áruk leírása</span><span class="sxs-lookup"><span data-stu-id="a7099-113">Description of goods</span></span> | <span data-ttu-id="a7099-114">Adjon meg egyedi azonosító nevet / számot a leírást használó árutípushoz.</span><span class="sxs-lookup"><span data-stu-id="a7099-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="a7099-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-115">Description</span></span> | <span data-ttu-id="a7099-116">Adja meg az ebbe a kategóriába tartozó árutípus leírását.</span><span class="sxs-lookup"><span data-stu-id="a7099-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="a7099-117">Hajók</span><span class="sxs-lookup"><span data-stu-id="a7099-117">Vessels</span></span>

<span data-ttu-id="a7099-118">A hajó annak a hajónakaz egyedi neve, amelyet a szállítmányozó vállalat vagy ügynökség használ.</span><span class="sxs-lookup"><span data-stu-id="a7099-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="a7099-119">Hajóút létrehozása során mindig ki kell választani vagy be kell írni egy hajót.</span><span class="sxs-lookup"><span data-stu-id="a7099-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="a7099-120">Ha gyakran ugyanazokat a hajókat használja, gyorsabban és egyszerűbben hozhat létre új hajóútakat, ha mindegyikhez egy hajórekordot hoz létre, ezáltal lehetővé téve a felhasználók számára, hogy a listáról kiválasszák a hajó nevét vagy számát, és ne minden alkalommal manuálisan kell beírják a nevet vagy a számot.</span><span class="sxs-lookup"><span data-stu-id="a7099-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="a7099-121">A hajókkal a **Partraszállítási költség \> Szállítási adatok beállítása \> Hajók** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="a7099-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="a7099-122">Itt lehet megtekinteni, megnyitni, létrehozni és törölni a hajórekordokat.</span><span class="sxs-lookup"><span data-stu-id="a7099-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="a7099-123">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="a7099-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="a7099-124">Mező</span><span class="sxs-lookup"><span data-stu-id="a7099-124">Field</span></span> | <span data-ttu-id="a7099-125">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-125">Description</span></span> |
|---|---|
| <span data-ttu-id="a7099-126">Hajó</span><span class="sxs-lookup"><span data-stu-id="a7099-126">Vessel</span></span> | <span data-ttu-id="a7099-127">Adja meg azon hajó egyedi azonosító nevét/számát, amelyet egy hajóúton áruszállításra használ.</span><span class="sxs-lookup"><span data-stu-id="a7099-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="a7099-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-128">Description</span></span> | <span data-ttu-id="a7099-129">Adja meg a hajó leírását.</span><span class="sxs-lookup"><span data-stu-id="a7099-129">Enter a description of the vessel.</span></span> <span data-ttu-id="a7099-130">Ez a leírás általában azonosítja a hajó nevét és a szállítmányozó vállalat/ügynök nevét.</span><span class="sxs-lookup"><span data-stu-id="a7099-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="a7099-131">Szállítás módja</span><span class="sxs-lookup"><span data-stu-id="a7099-131">Mode of delivery</span></span> | <span data-ttu-id="a7099-132">Válassza ki a hajó által használt szállítási módot (például _Légi_, _Tengeri_ vagy _Vonat_).</span><span class="sxs-lookup"><span data-stu-id="a7099-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="a7099-133">Exportőrök</span><span class="sxs-lookup"><span data-stu-id="a7099-133">Exporters</span></span>

<span data-ttu-id="a7099-134">Minden exportőrrekord egy szállítót vagy exportőrt azonosít, amely a hajóútért felelős szállítóként definiálható.</span><span class="sxs-lookup"><span data-stu-id="a7099-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="a7099-135">Az exportőr társítható hajóúthoz és jelentéskészítésre használható.</span><span class="sxs-lookup"><span data-stu-id="a7099-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="a7099-136">Az exportőrökkel a **Partraszállítási költség \> Szállítási adatok beállítása \> Exportőrök** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="a7099-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="a7099-137">Itt lehet megtekinteni, megnyitni, létrehozni és törölni az exportőröket.</span><span class="sxs-lookup"><span data-stu-id="a7099-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="a7099-138">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="a7099-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="a7099-139">Mező</span><span class="sxs-lookup"><span data-stu-id="a7099-139">Field</span></span> | <span data-ttu-id="a7099-140">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-140">Description</span></span> |
|---|---|
| <span data-ttu-id="a7099-141">Exportőr</span><span class="sxs-lookup"><span data-stu-id="a7099-141">Exporter</span></span> | <span data-ttu-id="a7099-142">Adja meg azon exportőr egyedi azonosító nevét/számát, amelyet egy hajóúton használ.</span><span class="sxs-lookup"><span data-stu-id="a7099-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="a7099-143">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-143">Description</span></span> | <span data-ttu-id="a7099-144">Adja meg az exportőr leírását.</span><span class="sxs-lookup"><span data-stu-id="a7099-144">Enter a description of the exporter.</span></span> <span data-ttu-id="a7099-145">Ez a leírás általában azonosítja a szállítmányozó vállalat/ügynök teljes nevét.</span><span class="sxs-lookup"><span data-stu-id="a7099-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="a7099-146">Árucikk-kódok</span><span class="sxs-lookup"><span data-stu-id="a7099-146">Commodity codes</span></span>

<span data-ttu-id="a7099-147">Az árucikk-kódok segítséget segítenek a vámügyi azonosításban és a hajóúton érintett áruk vámtételének kiszámításában.</span><span class="sxs-lookup"><span data-stu-id="a7099-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="a7099-148">A **Kiadott termékek** oldalon kiválaszthatja az árucikk-kódokat.</span><span class="sxs-lookup"><span data-stu-id="a7099-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="a7099-149">Az árucikk-kódokkal a **Partraszállítási költség \> Szállítási adatok beállítása \> Árucikk-kódok** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="a7099-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="a7099-150">Itt lehet megtekinteni, megnyitni, létrehozni és törölni az árucikk-kódokat.</span><span class="sxs-lookup"><span data-stu-id="a7099-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="a7099-151">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="a7099-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="a7099-152">Mező</span><span class="sxs-lookup"><span data-stu-id="a7099-152">Field</span></span> | <span data-ttu-id="a7099-153">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-153">Description</span></span> |
|---|---|
| <span data-ttu-id="a7099-154">Árucikk-kód</span><span class="sxs-lookup"><span data-stu-id="a7099-154">Commodity code</span></span> | <span data-ttu-id="a7099-155">Adjon meg egy egyedi kódot az ilyen típusú árucikkhez.</span><span class="sxs-lookup"><span data-stu-id="a7099-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="a7099-156">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-156">Description</span></span> | <span data-ttu-id="a7099-157">Adja meg az árucikktípus leírását.</span><span class="sxs-lookup"><span data-stu-id="a7099-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="a7099-158">Vámügyi leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-158">Customs description</span></span>

<span data-ttu-id="a7099-159">A vámügyi leírások segítik a vámkezelés által érintett áruk azonosítását.</span><span class="sxs-lookup"><span data-stu-id="a7099-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="a7099-160">Vámügyi leírást a **Kiadott termékek** oldalon vagy a beszerzési rendelés sorainál választhat ki.</span><span class="sxs-lookup"><span data-stu-id="a7099-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="a7099-161">A vámügyi leírásokkal a **Partraszállítási költség \> Szállítási adatok beállítása \> Vámügyi leírás** részben dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="a7099-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="a7099-162">Itt lehet megtekinteni, megnyitni, létrehozni és törölni a vámügyi leírásokat.</span><span class="sxs-lookup"><span data-stu-id="a7099-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="a7099-163">Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="a7099-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="a7099-164">Mező</span><span class="sxs-lookup"><span data-stu-id="a7099-164">Field</span></span> | <span data-ttu-id="a7099-165">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-165">Description</span></span> |
|---|---|
| <span data-ttu-id="a7099-166">Vámügyi leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-166">Customs description</span></span> | <span data-ttu-id="a7099-167">Adjon meg egy egyedi kódot az ilyen típusú vámügyi besoroláshoz.</span><span class="sxs-lookup"><span data-stu-id="a7099-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="a7099-168">Ez a kód gyakran a vámhatóság által az áruk leírására és kvalitatív értékére vonatkozó hivatalos leírás lesz.</span><span class="sxs-lookup"><span data-stu-id="a7099-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="a7099-169">Leírás</span><span class="sxs-lookup"><span data-stu-id="a7099-169">Description</span></span> | <span data-ttu-id="a7099-170">Adja meg a vámügyi besorolás leírását.</span><span class="sxs-lookup"><span data-stu-id="a7099-170">Enter a description of the customs classification.</span></span> |
