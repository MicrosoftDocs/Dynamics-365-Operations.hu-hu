---
title: Feladat-útmutatók mentése LCS-re, és újbóli lejátszásuk
description: Ez a cikk bemutatja, hogyan lehet menteni feladat-útmutatókat a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásba, majd ezután újra lejátszani őket.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a18bb14ba8c3c926065c97b0ee26c38ee86ded2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053275"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="25502-103">Feladat-útmutatók mentése LCS-re, és újbóli lejátszásuk</span><span class="sxs-lookup"><span data-stu-id="25502-103">Save task guides to LCS and replay them</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="25502-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="25502-104">**Environment details**</span></span> 

<span data-ttu-id="25502-105">A Microsoft Dynamics 365 Human Resources, amelyet a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül telepítettek</span><span class="sxs-lookup"><span data-stu-id="25502-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="25502-106">**Kiadás**</span><span class="sxs-lookup"><span data-stu-id="25502-106">**Issue**</span></span>

<span data-ttu-id="25502-107">A vevő új feladatrögzítéseket szeretne elmenteni az LCS-projekthez, majd újra lejátszani az elmentett feladat-útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="25502-107">The customer wants to save new task recordings to the LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="25502-108">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="25502-108">**Resolution**</span></span>

<span data-ttu-id="25502-109">Kövesse ezeket a lépéseket egy feladatrögzítés LCS-be való elmentéséhez.</span><span class="sxs-lookup"><span data-stu-id="25502-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="25502-110">Jelentkezzen be az LCS-be, és válassza ki a projektet.</span><span class="sxs-lookup"><span data-stu-id="25502-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="25502-111">Válassza ki az **Üzletifolyamat-modellező** csempét.</span><span class="sxs-lookup"><span data-stu-id="25502-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="25502-112">Tekintse meg az oldalt a „Megújult BPM-környezetben”.</span><span class="sxs-lookup"><span data-stu-id="25502-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="25502-113">Válasszon ki egy könyvtárat, majd válassza a **Másolás** elemet.</span><span class="sxs-lookup"><span data-stu-id="25502-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="25502-114">Adja meg az üzletifolyamat-modellező (BPM) modell nevét.</span><span class="sxs-lookup"><span data-stu-id="25502-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="25502-115">Jelentkezzen be a Human Resources rendszerbe az LCS-ből.</span><span class="sxs-lookup"><span data-stu-id="25502-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="25502-116">A **Keresés** mezőbe írja be a **segítség** szót.</span><span class="sxs-lookup"><span data-stu-id="25502-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="25502-117">A Lifecycle Services Súgója megnyílik.</span><span class="sxs-lookup"><span data-stu-id="25502-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="25502-118">Válassza ki a **Frissítés** gombot Lifecycle Services Súgó konfigurációjához.</span><span class="sxs-lookup"><span data-stu-id="25502-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="25502-119">Az új BPM-könyvtárnak meg kell jelennie, és aktívnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="25502-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="25502-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="25502-120">Close the page.</span></span>
10. <span data-ttu-id="25502-121">Hozzon létre egy feladatrögzítést.</span><span class="sxs-lookup"><span data-stu-id="25502-121">Create a task recording.</span></span>
11. <span data-ttu-id="25502-122">Amikor elkészült, válassza ki **Mentés a Lifecycle Services szolgáltatásba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25502-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Mentés a Lifecycle Services szolgáltatásba](media/task-guides.png)

12. <span data-ttu-id="25502-124">Válassza ki a BPM-könyvtárat és csomópontot, ahova a feladatrögzítést szeretné menteni.</span><span class="sxs-lookup"><span data-stu-id="25502-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="25502-125">Kövesse az alábbi lépéseket a feladat-útmutató LCS-ből való visszajátszásához.</span><span class="sxs-lookup"><span data-stu-id="25502-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="25502-126">Indítsa el a Feladatrögzítőt.</span><span class="sxs-lookup"><span data-stu-id="25502-126">Start Task recorder.</span></span>
2. <span data-ttu-id="25502-127">Válassza a **Megnyitás LCS-ből** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="25502-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="25502-128">Válassza ki a könyvtárat és a BPM-csomópontot, amelyek a mentett feladat-útmutatót tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="25502-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="25502-129">Nyissa meg a feladat-útmutatót.</span><span class="sxs-lookup"><span data-stu-id="25502-129">Open the task guide.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]