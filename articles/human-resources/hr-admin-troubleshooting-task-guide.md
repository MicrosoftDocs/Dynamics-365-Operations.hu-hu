---
title: Feladat-útmutatók mentése LCS-re, és újbóli lejátszásuk
description: Ez a cikk bemutatja, hogyan lehet menteni feladat-útmutatókat a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásba, majd ezután újra lejátszani őket.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b55937c0867117809471f50f1987f7bf12a4b25d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418857"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="f11a4-103">Feladat-útmutatók mentése LCS-re, és újbóli lejátszásuk</span><span class="sxs-lookup"><span data-stu-id="f11a4-103">Save task guides to LCS and replay them</span></span>

<span data-ttu-id="f11a4-104">**Környezet részletes adatai**</span><span class="sxs-lookup"><span data-stu-id="f11a4-104">**Environment details**</span></span> 

<span data-ttu-id="f11a4-105">A Microsoft Dynamics 365 Human Resources, amelyet a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül telepítettek</span><span class="sxs-lookup"><span data-stu-id="f11a4-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="f11a4-106">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="f11a4-106">**Issue**</span></span>

<span data-ttu-id="f11a4-107">A vevő új feladatrögzítéseket szeretne elmenteni az LCS-projektjéhez, majd újra lejátszani az elmentett feladat-útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="f11a4-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="f11a4-108">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="f11a4-108">**Resolution**</span></span>

<span data-ttu-id="f11a4-109">Kövesse ezeket a lépéseket egy feladatrögzítés LCS-be való elmentéséhez.</span><span class="sxs-lookup"><span data-stu-id="f11a4-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="f11a4-110">Jelentkezzen be az LCS-be, és válassza ki a projektet.</span><span class="sxs-lookup"><span data-stu-id="f11a4-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="f11a4-111">Válassza ki az **Üzletifolyamat-modellező** csempét.</span><span class="sxs-lookup"><span data-stu-id="f11a4-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="f11a4-112">Tekintse meg az oldalt a „Megújult BPM-környezetben”.</span><span class="sxs-lookup"><span data-stu-id="f11a4-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="f11a4-113">Válasszon ki egy könyvtárat, majd válassza a **Másolás** elemet.</span><span class="sxs-lookup"><span data-stu-id="f11a4-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="f11a4-114">Adja meg az üzletifolyamat-modellező (BPM) modell nevét.</span><span class="sxs-lookup"><span data-stu-id="f11a4-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="f11a4-115">Jelentkezzen be a Human Resources rendszerbe az LCS-ből.</span><span class="sxs-lookup"><span data-stu-id="f11a4-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="f11a4-116">A **Keresés** mezőbe írja be a **segítség** szót.</span><span class="sxs-lookup"><span data-stu-id="f11a4-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="f11a4-117">A Lifecycle Services Súgója megnyílik.</span><span class="sxs-lookup"><span data-stu-id="f11a4-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="f11a4-118">Válassza ki a **Frissítés** gombot Lifecycle Services Súgó konfigurációjához.</span><span class="sxs-lookup"><span data-stu-id="f11a4-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="f11a4-119">Az új BPM-könyvtárnak meg kell jelennie, és aktívnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="f11a4-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="f11a4-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f11a4-120">Close the page.</span></span>
10. <span data-ttu-id="f11a4-121">Hozzon létre egy feladatrögzítést.</span><span class="sxs-lookup"><span data-stu-id="f11a4-121">Create a task recording.</span></span>
11. <span data-ttu-id="f11a4-122">Amikor elkészült, válassza ki **Mentés a Lifecycle Services szolgáltatásba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f11a4-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Mentés a Lifecycle Services szolgáltatásba](media/task-guides.png)

12. <span data-ttu-id="f11a4-124">Válassza ki a BPM-könyvtárat és csomópontot, ahova a feladatrögzítést szeretné menteni.</span><span class="sxs-lookup"><span data-stu-id="f11a4-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="f11a4-125">Kövesse az alábbi lépéseket a feladat-útmutató LCS-ből való visszajátszásához.</span><span class="sxs-lookup"><span data-stu-id="f11a4-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="f11a4-126">Indítsa el a Feladatrögzítőt.</span><span class="sxs-lookup"><span data-stu-id="f11a4-126">Start Task recorder.</span></span>
2. <span data-ttu-id="f11a4-127">Válassza a **Megnyitás LCS-ből** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f11a4-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="f11a4-128">Válassza ki a könyvtárat és a BPM-csomópontot, amelyek a mentett feladat-útmutatót tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="f11a4-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="f11a4-129">Nyissa meg a feladat-útmutatót.</span><span class="sxs-lookup"><span data-stu-id="f11a4-129">Open the task guide.</span></span>
