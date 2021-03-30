---
title: Alapértelmezett leírások beállítása az automatikus feladáshoz
description: Beállíthat olyan alapértelmezett szöveget, amelyet a rendszer a  mező kitöltésére használ olyan könyvelési bejegyzések esetén, amelyek feladása automatikusan történik a főkönyvbe. Minden tranzakciótípus esetén beállíthat alapértelmezett leírásszöveget szabad formájú szöveget használva vagy rögzített változókat kijelölve.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5955b796cbc7917eb5500b96c879d1b0819d2edc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204858"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a><span data-ttu-id="1c38c-104">Alapértelmezett leírások beállítása az automatikus feladáshoz</span><span class="sxs-lookup"><span data-stu-id="1c38c-104">Set up default descriptions for automatic posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c38c-105">Beállíthat olyan alapértelmezett szöveget, amelyet a rendszer a  mező kitöltésére használ olyan könyvelési bejegyzések esetén, amelyek feladása automatikusan történik a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="1c38c-105">This topic explains how to set up default text that is used to describe accounting entries that are posted automatically to the general ledger.</span></span> <span data-ttu-id="1c38c-106">Minden tranzakciótípus esetén beállíthat alapértelmezett leírásszöveget szabad formájú szöveget használva vagy rögzített változókat kijelölve.</span><span class="sxs-lookup"><span data-stu-id="1c38c-106">You can set up default description text by using free-form text or by selecting fixed variables.</span></span>

> [!NOTE]
> <span data-ttu-id="1c38c-107">Bizonyos tranzakciótípusok esetén belefoglalhat az adott tranzakciótípusokkal kapcsolatos Microsoft Dynamics AX adatbázisban lévő mezőkből származó szöveget is.</span><span class="sxs-lookup"><span data-stu-id="1c38c-107">For some transaction types in some countries or regions, you can also include text from fields in the Microsoft Dynamics AX database that are related to those transaction types.</span></span> <span data-ttu-id="1c38c-108">A tranzakciótípusok és az országok és régiók listája tekintetében lásd: [Választható: Szövegek más alapértelmezett leírások](#optional-add-other-text-to-default-descriptions) szakasz a témakör későbbi részében.</span><span class="sxs-lookup"><span data-stu-id="1c38c-108">For a list of the transaction types, and the countries and regions, see the [Optional: Add other text to default descriptions](#optional-add-other-text-to-default-descriptions) section later in this topic.</span></span>

## <a name="set-up-default-descriptions"></a><span data-ttu-id="1c38c-109">Alapértelmezett leírások beállítása</span><span class="sxs-lookup"><span data-stu-id="1c38c-109">Set up default descriptions</span></span>

1. <span data-ttu-id="1c38c-110">Lépjen a **Szervezetadminisztráció** \> **Beállítás** \> **Alapértelmezett leírások** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="1c38c-110">Go to **Organization administration** \> **Setup** \> **Default descriptions**.</span></span>
2. <span data-ttu-id="1c38c-111">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1c38c-111">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="1c38c-112">A **Leírás** mezőben válassza ki a tranzakciótípust, amelyhez alapértelmezett leírást kíván létrehozni.</span><span class="sxs-lookup"><span data-stu-id="1c38c-112">In the **Description** field, select the type of transaction to create a default description for.</span></span>
4. <span data-ttu-id="1c38c-113">A **Nyelv** mezőben válassza ki azt a nyelvet, amelyre ez a leírás vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="1c38c-113">In the **Language** field, select the language that the description applies to.</span></span>
5. <span data-ttu-id="1c38c-114">A **Szöveg** mezőbe írja be az alapértelmezett leírást.</span><span class="sxs-lookup"><span data-stu-id="1c38c-114">In the **Text** field, enter the default description.</span></span> <span data-ttu-id="1c38c-115">A szöveget beírhatja a mezőbe, vagy használhat egyet vagy többet a következő szabad szöveges változók közül:</span><span class="sxs-lookup"><span data-stu-id="1c38c-115">You can type text in the field, or you can use one or more of the following free-text variables:</span></span>

    - <span data-ttu-id="1c38c-116">**%1** – A tranzakció dátumának hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="1c38c-116">**%1** – Add the transaction date.</span></span>
    - <span data-ttu-id="1c38c-117">**%2** – A főkönyvbe feladásra kerülő dokumentumtípusnak megfelelő azonosító hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="1c38c-117">**%2** – Add an identifier that corresponds to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="1c38c-118">Például számlákhoz kapcsolódó tranzakciótípusok esetén a **%2** változó a számlaszámot adja hozzá.</span><span class="sxs-lookup"><span data-stu-id="1c38c-118">For example, for transaction types that are related to invoices, the **%2** variable adds the invoice number.</span></span>
    - <span data-ttu-id="1c38c-119">**%3** – A főkönyvbe feladásra kerülő dokumentumtípushoz kapcsolódó azonosító hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="1c38c-119">**%3** – Add an identifier that is related to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="1c38c-120">Például számlákhoz kapcsolódó tranzakciótípusok esetén a **%3** változó a vevőkód számát adja hozzá.</span><span class="sxs-lookup"><span data-stu-id="1c38c-120">For example, for transaction types that are related to invoices, the **%3** variable adds the customer account number.</span></span>

## <a name="optional-add-other-text-to-default-descriptions"></a><span data-ttu-id="1c38c-121">Választható: Szöveget más alapértelmezett leírások</span><span class="sxs-lookup"><span data-stu-id="1c38c-121">Optional: Add other text to default descriptions</span></span>

<span data-ttu-id="1c38c-122">Bizonyos tranzakciótípusok esetén belefoglalhat egyes országokban vagy régiókban az alapértelmezett leírások adott tranzakciótípusokkal kapcsolatos adatbázisban lévő mezőkből származó szöveget is.</span><span class="sxs-lookup"><span data-stu-id="1c38c-122">For some transaction types in some countries or regions, default descriptions can include text that comes from fields in your data that are related to those transaction types.</span></span> <span data-ttu-id="1c38c-123">A következő listák megjelenítése a tranzakciótípusok és országok és régiók amelyhez ez a beállítás akkor érhető el.</span><span class="sxs-lookup"><span data-stu-id="1c38c-123">The following lists show the transaction types, and the countries and regions, that this option is available for.</span></span>

<span data-ttu-id="1c38c-124">**Tranzakciótípusok**</span><span class="sxs-lookup"><span data-stu-id="1c38c-124">**Transaction types**</span></span>

<span data-ttu-id="1c38c-125">Más szöveget adhat a tranzakciótípusokat, amelyeket a következő dokumentumtípusokat kapcsolódó alapértelmezett leírása:</span><span class="sxs-lookup"><span data-stu-id="1c38c-125">You can add other text to default descriptions for transaction types that are related to the following document types:</span></span>

- <span data-ttu-id="1c38c-126">Vevői számlák</span><span class="sxs-lookup"><span data-stu-id="1c38c-126">Customer invoices</span></span>
- <span data-ttu-id="1c38c-127">Vevő jóváírások</span><span class="sxs-lookup"><span data-stu-id="1c38c-127">Customer credit notes</span></span>
- <span data-ttu-id="1c38c-128">Vevő készpénzfizetések</span><span class="sxs-lookup"><span data-stu-id="1c38c-128">Customer cash payments</span></span>
- <span data-ttu-id="1c38c-129">Szállítói kifizetések</span><span class="sxs-lookup"><span data-stu-id="1c38c-129">Vendor payments</span></span>
- <span data-ttu-id="1c38c-130">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="1c38c-130">Sales orders</span></span>
- <span data-ttu-id="1c38c-131">Beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="1c38c-131">Purchase orders</span></span>
- <span data-ttu-id="1c38c-132">Készletnaplók</span><span class="sxs-lookup"><span data-stu-id="1c38c-132">Inventory journals</span></span>
- <span data-ttu-id="1c38c-133">Alaptervezés (MRP)</span><span class="sxs-lookup"><span data-stu-id="1c38c-133">Master planning (MRP)</span></span>
- <span data-ttu-id="1c38c-134">Tárgyi eszközök</span><span class="sxs-lookup"><span data-stu-id="1c38c-134">Fixed assets</span></span>

<span data-ttu-id="1c38c-135">**Országok és régiók**</span><span class="sxs-lookup"><span data-stu-id="1c38c-135">**Countries and regions**</span></span>

<span data-ttu-id="1c38c-136">Ez a beállítás a következő országokra és régiókra érhető el:</span><span class="sxs-lookup"><span data-stu-id="1c38c-136">This option is available for the following countries and regions:</span></span>

- <span data-ttu-id="1c38c-137">Brazília</span><span class="sxs-lookup"><span data-stu-id="1c38c-137">Brazil</span></span>
- <span data-ttu-id="1c38c-138">Kína</span><span class="sxs-lookup"><span data-stu-id="1c38c-138">China</span></span>
- <span data-ttu-id="1c38c-139">Cseh Köztársaság</span><span class="sxs-lookup"><span data-stu-id="1c38c-139">Czech Republic</span></span>
- <span data-ttu-id="1c38c-140">Kelet-Európa</span><span class="sxs-lookup"><span data-stu-id="1c38c-140">Eastern Europe</span></span>
- <span data-ttu-id="1c38c-141">Magyarország</span><span class="sxs-lookup"><span data-stu-id="1c38c-141">Hungary</span></span>
- <span data-ttu-id="1c38c-142">Indiai</span><span class="sxs-lookup"><span data-stu-id="1c38c-142">India</span></span>
- <span data-ttu-id="1c38c-143">Japán</span><span class="sxs-lookup"><span data-stu-id="1c38c-143">Japan</span></span>
- <span data-ttu-id="1c38c-144">Litvánia</span><span class="sxs-lookup"><span data-stu-id="1c38c-144">Lithuania</span></span>
- <span data-ttu-id="1c38c-145">Lettország</span><span class="sxs-lookup"><span data-stu-id="1c38c-145">Latvia</span></span>
- <span data-ttu-id="1c38c-146">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="1c38c-146">Poland</span></span>
- <span data-ttu-id="1c38c-147">Oroszország</span><span class="sxs-lookup"><span data-stu-id="1c38c-147">Russia</span></span>

### <a name="add-text-to-default-descriptions"></a><span data-ttu-id="1c38c-148">Választható: Szöveget más alapértelmezett leírások</span><span class="sxs-lookup"><span data-stu-id="1c38c-148">Add text to default descriptions</span></span>

<span data-ttu-id="1c38c-149">A lépések elvégzése után a korábbi [Alapértelmezett leírások beállítása](#set-up-default-descriptions) szakasz lépései végrehajtásával más szöveget adhat az alapértelmezett leírásokhoz.</span><span class="sxs-lookup"><span data-stu-id="1c38c-149">After you complete the steps in the [Set up default descriptions](#set-up-default-descriptions) section earlier in this topic, follow these steps to add other text to the default descriptions.</span></span>

1. <span data-ttu-id="1c38c-150">Válassza a **Paraméterek** gyorslap **Hozzáadás** elemét.</span><span class="sxs-lookup"><span data-stu-id="1c38c-150">On the **Parameters** FastTab, select **Add**.</span></span>
2. <span data-ttu-id="1c38c-151">A **Hivatkozási tábla** mezőben válassza ki azt a táblát, amelyből paraméteradatokat szeretne hozzáadni a leíráshoz.</span><span class="sxs-lookup"><span data-stu-id="1c38c-151">In the **Reference table** field, select the database table from which to add parameter data to the description.</span></span>
3. <span data-ttu-id="1c38c-152">A **Hivatkozási mező** mezőben válassza ki azt mezőt, amelyből paraméteradatokat szeretne hozzáadni a leíráshoz.</span><span class="sxs-lookup"><span data-stu-id="1c38c-152">In the **Reference field** field, select the field from which to add parameter data to the description.</span></span>
4. <span data-ttu-id="1c38c-153">További mezők hozzáadásához ismételje meg a 1–3. lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1c38c-153">Repeat steps 1 through 3 to add more parameters.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]