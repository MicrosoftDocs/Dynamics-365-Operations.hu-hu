---
title: Hivatkozások eredeti számlákra a jóváírásokban
description: Ez a témakör bemutatja az eredeti számlaszámok beállítását és nyomtatását a kapcsolódó jóváírásokban.
author: ilkond
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d7f32c5d3d29be8d1d2742c4017c1719cbd47a8
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897332"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="54c05-103">Hivatkozások eredeti számlákra a jóváírásokban</span><span class="sxs-lookup"><span data-stu-id="54c05-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="54c05-104">Egyes országokban és régiókban jogi előírás, hogy a nyomtatott jóváírások hivatkozást tartalmazzanak az eredeti számlákra.</span><span class="sxs-lookup"><span data-stu-id="54c05-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="54c05-105">Ez a témakör bemutatja az eredeti számlaszámok beállítását és nyomtatását a kapcsolódó jóváírásokban.</span><span class="sxs-lookup"><span data-stu-id="54c05-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54c05-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="54c05-106">Prerequisites</span></span>

- <span data-ttu-id="54c05-107">A **Funkciókezelés** munkaterületen kapcsolja be az **Értékesítési és projektszámla-jelentések jóváírás-számlázási elrendezése** funkciót.</span><span class="sxs-lookup"><span data-stu-id="54c05-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="54c05-108">További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="54c05-108">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="54c05-109">A szükséges dokumentumok nyomtatható formátumait a Nyomtatáskezelésben kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="54c05-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="54c05-110">Az ebben a témakörben leírt funkciók a következő dokumentumokra vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="54c05-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="54c05-111">**Kinnlevőségek**</span><span class="sxs-lookup"><span data-stu-id="54c05-111">**Accounts receivable**</span></span>

- <span data-ttu-id="54c05-112">Szabadszövegű jóváírás</span><span class="sxs-lookup"><span data-stu-id="54c05-112">Free text credit note</span></span>
- <span data-ttu-id="54c05-113">Vevői jóváírás</span><span class="sxs-lookup"><span data-stu-id="54c05-113">Customer credit note</span></span>

<span data-ttu-id="54c05-114">**Projektvezetés és könyvelés**</span><span class="sxs-lookup"><span data-stu-id="54c05-114">**Project management and accounting**</span></span>

- <span data-ttu-id="54c05-115">Projekt jóváírása</span><span class="sxs-lookup"><span data-stu-id="54c05-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="54c05-116">A Kinnlevőségek paraméterei konfigurálása</span><span class="sxs-lookup"><span data-stu-id="54c05-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="54c05-117">A következő lépések segítségével beállíthatja azt a paramétert, amely meghatározza, hogy az eredeti számlákra vonatkozó hivatkozások ki vannak-e nyomtatva a kapcsolódó jóváírásokban.</span><span class="sxs-lookup"><span data-stu-id="54c05-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="54c05-118">Lépjen a **Kinnlevőségek** \> **Beállítások** \> **Kinnlevőségek paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="54c05-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="54c05-119">A **Számla** gyorslap **Frissítések** lapján állítsa a **Jóváírás-számlázási elrendezés alkalmazása értékesítési és projektszámla-jelentésekre** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="54c05-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![A Kinnlevőségek paraméterei konfigurálása](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="54c05-121">Eredeti számlákra mutató hivatkozások meghatározása</span><span class="sxs-lookup"><span data-stu-id="54c05-121">Define references to original invoices</span></span>

<span data-ttu-id="54c05-122">A következő eljárásnak megfelelően a dokumentumtípus alapján meghatározhatja az eredeti számlákra történő hivatkozásokat.</span><span class="sxs-lookup"><span data-stu-id="54c05-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="54c05-123">Szabadszövegű jóváírás</span><span class="sxs-lookup"><span data-stu-id="54c05-123">Free text credit note</span></span>

1. <span data-ttu-id="54c05-124">Válassza a következőt **Kinnlevőségek** \> **Számlák** \> **Kizárólag szabadszöveges számlák**.</span><span class="sxs-lookup"><span data-stu-id="54c05-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="54c05-125">Hozzon létre új jóváírást vagy válasszon ki egy meglévőt.</span><span class="sxs-lookup"><span data-stu-id="54c05-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="54c05-126">Nyissa meg a számlát.</span><span class="sxs-lookup"><span data-stu-id="54c05-126">Open the invoice.</span></span>
4. <span data-ttu-id="54c05-127">A Műveleti ablaktábla **Számla** lapján a **Függvények** csoportban válassza a **Jóváírás számlázása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54c05-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="54c05-128">Írja be az eredeti számlára való hivatkozást, és válassza ki a javítás okát.</span><span class="sxs-lookup"><span data-stu-id="54c05-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Szabadszöveges számla hivatkozásának meghatározása](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="54c05-130">Vevői jóváírás</span><span class="sxs-lookup"><span data-stu-id="54c05-130">Customer credit note</span></span>

1. <span data-ttu-id="54c05-131">Lépjen a **Kinnlevőségek** \> **Rendelések** \> **Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="54c05-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="54c05-132">Válassza ki és nyissa meg a javítandó leszámlázott értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="54c05-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="54c05-133">A Műveleti ablaktábla **Értékesítés** lapján a **Jóváírás** csoportban válassza a **Jóváírás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54c05-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="54c05-134">Adja meg a javítás okát.</span><span class="sxs-lookup"><span data-stu-id="54c05-134">Enter the reason for the correction.</span></span> <span data-ttu-id="54c05-135">Az eredeti számlára való hivatkozás automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="54c05-135">The reference to the original invoice is automatically established.</span></span>

![Értékesítési rendelés hivatkozásának meghatározása](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="54c05-137">Projekt jóváírása</span><span class="sxs-lookup"><span data-stu-id="54c05-137">Project credit note</span></span>

1. <span data-ttu-id="54c05-138">Lépjen a **Projektvezetés és könyvelés** \> **Projektszámlák** \> **Projektszámlák** menüpontba.</span><span class="sxs-lookup"><span data-stu-id="54c05-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="54c05-139">Válassza ki és nyissa meg a javítandó projektszámlát.</span><span class="sxs-lookup"><span data-stu-id="54c05-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="54c05-140">A Műveleti ablaktábla **Projektszámla** lapján a **Függvények** csoportban válassza a **Kijelölés jóváíráshoz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54c05-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="54c05-141">Válassza a **Jóváírás számlázása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54c05-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="54c05-142">Adja meg a javítás okát.</span><span class="sxs-lookup"><span data-stu-id="54c05-142">Enter the reason for the correction.</span></span> <span data-ttu-id="54c05-143">Az eredeti számlára való hivatkozás automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="54c05-143">The reference to the original invoice is automatically established.</span></span>

![Projektszámla hivatkozásának meghatározása](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="54c05-145">Jóváírások nyomtatása</span><span class="sxs-lookup"><span data-stu-id="54c05-145">Printing credit notes</span></span>

<span data-ttu-id="54c05-146">Szabadszöveges, vevői és projektjóváírások nyomtatása esetén a jóváírások az eredeti számlára való hivatkozást és a javítás okát is tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="54c05-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Kinyomtatott jóváírás](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="54c05-148">Győződjön meg arról, hogy a dokumentumok nyomtatható formátumai helyesen legyenek konfigurálva, feltételezve, hogy az eredeti számlákra mutató hivatkozásokat ki fogják nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="54c05-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]