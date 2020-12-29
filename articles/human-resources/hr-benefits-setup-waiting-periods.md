---
title: Várakozási időszakok konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben a várakozási napokkal hozhatók létre mérföldkövek, amelyek a juttatási konstrukciókhoz használhatók.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e1937ab54eb7898afe0fed6659c3ae676626e8ad
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418862"
---
# <a name="configure-waiting-periods"></a><span data-ttu-id="da9c3-103">Várakozási időszakok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="da9c3-103">Configure waiting periods</span></span>

<span data-ttu-id="da9c3-104">A Microsoft Dynamics 365 Human Resources rendszerben a várakozási napokkal hozhatók létre mérföldkövek, amelyek a juttatási konstrukciókhoz használhatók.</span><span class="sxs-lookup"><span data-stu-id="da9c3-104">In Microsoft Dynamics 365 Human Resources, waiting days establish a milestone to use for benefit plans.</span></span> <span data-ttu-id="da9c3-105">Például három hónap a felvételi dátumtól számítva, a hónap első napja vagy hat hónap.</span><span class="sxs-lookup"><span data-stu-id="da9c3-105">For example, three months from hire date, the first of each month, or six months.</span></span>   

1. <span data-ttu-id="da9c3-106">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Várakozási időszakok** elemet.</span><span class="sxs-lookup"><span data-stu-id="da9c3-106">In the **Benefits management** workspace, under **Setup**, select **Waiting periods**.</span></span>

2. <span data-ttu-id="da9c3-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="da9c3-107">Select **New**.</span></span>

3. <span data-ttu-id="da9c3-108">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="da9c3-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="da9c3-109">Mező</span><span class="sxs-lookup"><span data-stu-id="da9c3-109">Field</span></span> | <span data-ttu-id="da9c3-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="da9c3-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="da9c3-111">**Várakozási kód**</span><span class="sxs-lookup"><span data-stu-id="da9c3-111">**Waiting code**</span></span> | <span data-ttu-id="da9c3-112">A várakozási időszak egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="da9c3-112">A unique identifier for the waiting period.</span></span> |
   | <span data-ttu-id="da9c3-113">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="da9c3-113">**Description**</span></span> | <span data-ttu-id="da9c3-114">A várakozási időszak rövid leírása.</span><span class="sxs-lookup"><span data-stu-id="da9c3-114">A description of the waiting period.</span></span> |
   | <span data-ttu-id="da9c3-115">**Várakozás módja**</span><span class="sxs-lookup"><span data-stu-id="da9c3-115">**Waiting method**</span></span> | <span data-ttu-id="da9c3-116">Válassza ki a megfelelő várakozási módot az értékeket tartalmazó legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="da9c3-116">Select the appropriate waiting method from the drop-down list of values.</span></span> <span data-ttu-id="da9c3-117">A választási lehetőségek a következők: Nettó, Aktuális hónap, Aktuális negyedév, Aktuális év és Aktuális hét.</span><span class="sxs-lookup"><span data-stu-id="da9c3-117">Options are Net, Current month, Current quarter, Current year, and Current week.</span></span> |
   | <span data-ttu-id="da9c3-118">**hónap**</span><span class="sxs-lookup"><span data-stu-id="da9c3-118">**Months**</span></span> | <span data-ttu-id="da9c3-119">Adja meg a várakozási módszerhez hozzáadandó hónapok számát a várakozási dátum kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="da9c3-119">Enter the number of months to add to the waiting method to calculate the waiting date.</span></span> |
   | <span data-ttu-id="da9c3-120">**Nap**</span><span class="sxs-lookup"><span data-stu-id="da9c3-120">**Days**</span></span> | <span data-ttu-id="da9c3-121">Adja meg a várakozási módszerhez hozzáadandó napok számát a várakozási dátum kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="da9c3-121">Enter the number of days to add to the waiting method to calculate the waiting date.</span></span> |
   | <span data-ttu-id="da9c3-122">**Várakozási nap**</span><span class="sxs-lookup"><span data-stu-id="da9c3-122">**Waiting day**</span></span> | <span data-ttu-id="da9c3-123">Válassza ki a várakozási dátum kiszámításához használandó várakozási napot.</span><span class="sxs-lookup"><span data-stu-id="da9c3-123">Select the waiting day to use to calculate the waiting date.</span></span> |

4. <span data-ttu-id="da9c3-124">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="da9c3-124">Select **Save**.</span></span>
