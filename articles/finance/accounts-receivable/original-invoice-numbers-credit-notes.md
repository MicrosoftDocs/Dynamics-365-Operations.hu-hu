---
title: Hivatkozások eredeti számlákra a jóváírásokban
description: Ez a témakör bemutatja az eredeti számlaszámok beállítását és nyomtatását a kapcsolódó jóváírásokban.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 673288f04b33aa2a578f9e2e7913dbe7ac309644
ms.sourcegitcommit: 7cdec5469ff0da145ac4e01caf3287d0627ae2dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2021
ms.locfileid: "5100002"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="eb5eb-103">Hivatkozások eredeti számlákra a jóváírásokban</span><span class="sxs-lookup"><span data-stu-id="eb5eb-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="eb5eb-104">Egyes országokban és régiókban jogi előírás, hogy a nyomtatott jóváírások hivatkozást tartalmazzanak az eredeti számlákra.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="eb5eb-105">Ez a témakör bemutatja az eredeti számlaszámok beállítását és nyomtatását a kapcsolódó jóváírásokban.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb5eb-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="eb5eb-106">Prerequisites</span></span>

- <span data-ttu-id="eb5eb-107">A **Funkciókezelés** munkaterületen kapcsolja be az **Értékesítési és projektszámla-jelentések jóváírás-számlázási elrendezése** funkciót.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="eb5eb-108">További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eb5eb-108">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="eb5eb-109">A szükséges dokumentumok nyomtatható formátumait a Nyomtatáskezelésben kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="eb5eb-110">Az ebben a témakörben leírt funkciók a következő dokumentumokra vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="eb5eb-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="eb5eb-111">**Kinnlevőségek**</span><span class="sxs-lookup"><span data-stu-id="eb5eb-111">**Accounts receivable**</span></span>

- <span data-ttu-id="eb5eb-112">Szabadszövegű jóváírás</span><span class="sxs-lookup"><span data-stu-id="eb5eb-112">Free text credit note</span></span>
- <span data-ttu-id="eb5eb-113">Vevői jóváírás</span><span class="sxs-lookup"><span data-stu-id="eb5eb-113">Customer credit note</span></span>

<span data-ttu-id="eb5eb-114">**Projektvezetés és könyvelés**</span><span class="sxs-lookup"><span data-stu-id="eb5eb-114">**Project management and accounting**</span></span>

- <span data-ttu-id="eb5eb-115">Projekt jóváírása</span><span class="sxs-lookup"><span data-stu-id="eb5eb-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="eb5eb-116">A Kinnlevőségek paraméterei konfigurálása</span><span class="sxs-lookup"><span data-stu-id="eb5eb-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="eb5eb-117">A következő lépések segítségével beállíthatja azt a paramétert, amely meghatározza, hogy az eredeti számlákra vonatkozó hivatkozások ki vannak-e nyomtatva a kapcsolódó jóváírásokban.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="eb5eb-118">Lépjen a **Kinnlevőségek** \> **Beállítások** \> **Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="eb5eb-119">A **Számla** gyorslap **Frissítések** lapján állítsa a **Jóváírás-számlázási elrendezés alkalmazása értékesítési és projektszámla-jelentésekre** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![A Kinnlevőségek paraméterei konfigurálása](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="eb5eb-121">Eredeti számlákra mutató hivatkozások meghatározása</span><span class="sxs-lookup"><span data-stu-id="eb5eb-121">Define references to original invoices</span></span>

<span data-ttu-id="eb5eb-122">A következő eljárásnak megfelelően a dokumentumtípus alapján meghatározhatja az eredeti számlákra történő hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="eb5eb-123">Szabadszövegű jóváírás</span><span class="sxs-lookup"><span data-stu-id="eb5eb-123">Free text credit note</span></span>

1. <span data-ttu-id="eb5eb-124">Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="eb5eb-125">Hozzon létre új jóváírást vagy válasszon ki egy meglévőt.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="eb5eb-126">Nyissa meg a számlát.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-126">Open the invoice.</span></span>
4. <span data-ttu-id="eb5eb-127">A Műveleti ablaktábla **Számla** lapján a **Függvények** csoportban válassza a **Jóváírás számlázása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="eb5eb-128">Írja be az eredeti számlára való hivatkozást, és válassza ki a javítás okát.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Szabadszöveges számla hivatkozásának meghatározása](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="eb5eb-130">Vevői jóváírás</span><span class="sxs-lookup"><span data-stu-id="eb5eb-130">Customer credit note</span></span>

1. <span data-ttu-id="eb5eb-131">Lépjen a **Kinnlevőségek** \> **Rendelések** \> **Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="eb5eb-132">Válassza ki és nyissa meg a javítandó leszámlázott értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="eb5eb-133">A Műveleti ablaktábla **Értékesítés** lapján a **Jóváírás** csoportban válassza a **Jóváírás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="eb5eb-134">Adja meg a javítás okát.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-134">Enter the reason for the correction.</span></span> <span data-ttu-id="eb5eb-135">Az eredeti számlára való hivatkozás automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-135">The reference to the original invoice is automatically established.</span></span>

![Értékesítési rendelés hivatkozásának meghatározása](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="eb5eb-137">Projekt jóváírása</span><span class="sxs-lookup"><span data-stu-id="eb5eb-137">Project credit note</span></span>

1. <span data-ttu-id="eb5eb-138">Lépjen a **Projektvezetés és könyvelés** \> **Projektszámlák** \> **Projektszámlák** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="eb5eb-139">Válassza ki és nyissa meg a javítandó projektszámlát.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="eb5eb-140">A Műveleti ablaktábla **Projektszámla** lapján a **Függvények** csoportban válassza a **Kijelölés jóváíráshoz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="eb5eb-141">Válassza a **Jóváírás számlázása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="eb5eb-142">Adja meg a javítás okát.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-142">Enter the reason for the correction.</span></span> <span data-ttu-id="eb5eb-143">Az eredeti számlára való hivatkozás automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-143">The reference to the original invoice is automatically established.</span></span>

![Projektszámla hivatkozásának meghatározása](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="eb5eb-145">Jóváírások nyomtatása</span><span class="sxs-lookup"><span data-stu-id="eb5eb-145">Printing credit notes</span></span>

<span data-ttu-id="eb5eb-146">Szabadszöveges, vevői és projektjóváírások nyomtatása esetén a jóváírások az eredeti számlára való hivatkozást és a javítás okát is tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Kinyomtatott jóváírás](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="eb5eb-148">Győződjön meg arról, hogy a dokumentumok nyomtatható formátumai helyesen legyenek konfigurálva, feltételezve, hogy az eredeti számlákra mutató hivatkozásokat ki fogják nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="eb5eb-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>
