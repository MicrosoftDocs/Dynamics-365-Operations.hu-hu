---
title: Projekttámogatások
description: Ez a témakör egy támogatás létrehozásának vagy módosításának lépéseit mutatja be.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282830"
---
# <a name="project-grants"></a><span data-ttu-id="1952d-103">Projekttámogatások</span><span class="sxs-lookup"><span data-stu-id="1952d-103">Project grants</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1952d-104">A támogatás meghatározott célra vagy projektre fordítható pénzadomány.</span><span class="sxs-lookup"><span data-stu-id="1952d-104">A grant is a gift of money for a specific purpose or project.</span></span> <span data-ttu-id="1952d-105">A támogatások felhasználására általában meghatározott korlátozások vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="1952d-105">Usually, there are restrictions on how a grant can be spent.</span></span> <span data-ttu-id="1952d-106">A támogatásokat a Projektvezetés és könyvelés modulban adhatja meg és követheti nyomon, valamint megadhatja azok kapcsolatait a projektekkel és projektszerződésekkel.</span><span class="sxs-lookup"><span data-stu-id="1952d-106">In Project management and accounting, you can enter and track grants, and define their relationships to projects and project contracts.</span></span> <span data-ttu-id="1952d-107">Például a következő műveleteket is elvégezheti:</span><span class="sxs-lookup"><span data-stu-id="1952d-107">For example, you can perform the following tasks:</span></span>

- <span data-ttu-id="1952d-108">Támogatás társítása a projektekhez és a finanszírozási forrásokhoz a **Projekt** és a **Projekt-szerződéses részletei** oldalakra mutató hivatkozásokkal.</span><span class="sxs-lookup"><span data-stu-id="1952d-108">Associate grants with projects and funding sources through links to the **Project** and **Project contract details** pages.</span></span>
- <span data-ttu-id="1952d-109">Megadhatja a támogatásokat, és nyomon követheti az állapotuk változásait.</span><span class="sxs-lookup"><span data-stu-id="1952d-109">Enter and track changes to a grant as it moves from one status to another.</span></span>
- <span data-ttu-id="1952d-110">Megadhatja és nyomon követheti a költségeket, a kért összegeket és a megítélt összegeket.</span><span class="sxs-lookup"><span data-stu-id="1952d-110">Enter and track costs, requested amounts, and awarded amounts.</span></span>
- <span data-ttu-id="1952d-111">Létrehozhat főtámogatásokat, és résztámogatásokat rendelhet hozzájuk.</span><span class="sxs-lookup"><span data-stu-id="1952d-111">Create master grants, and associate subgrants with them.</span></span>

<span data-ttu-id="1952d-112">Támogatást létrehozhat úgy, hogy egy új rekordban adja meg az összes adatot, vagy úgy is, hogy átmásolja és frissíti egy meglévő támogatás adatait.</span><span class="sxs-lookup"><span data-stu-id="1952d-112">You can create a grant by entering all the details in a new record, or you can copy the details from an existing grant and then update them.</span></span>

## <a name="create-a-new-grant"></a><span data-ttu-id="1952d-113">Új támogatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="1952d-113">Create a new grant</span></span>

1. <span data-ttu-id="1952d-114">Ugorjon a **Projektvezetés és könyvelés** \> **Támogatások** \> **Támogatások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1952d-114">Go to **Project management and accounting** \> **Grants** \> **Grants**.</span></span>
2. <span data-ttu-id="1952d-115">Válassza az **Új** \> **Támogatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1952d-115">Select **New** \> **Grant**.</span></span>
3. <span data-ttu-id="1952d-116">A támogatás részletei lap **Általános** gyorslapján, a **Támogatás azonosítója** mezőben adjon meg egy alfanumerikus azonosítót a támogatáshoz.</span><span class="sxs-lookup"><span data-stu-id="1952d-116">On the grant details page, on the **General** FastTab, in the **Grant ID** field, enter an alphanumeric identifier for the grant.</span></span>
4. <span data-ttu-id="1952d-117">Adja meg a támogatás nevét a **Támogatás neve** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1952d-117">In the **Grant name** field, enter a name for the grant.</span></span>
5. <span data-ttu-id="1952d-118">A **Leírás** mezőben adja meg az új támogatás részleteit.</span><span class="sxs-lookup"><span data-stu-id="1952d-118">In the **Description** field, add details about the new grant.</span></span>

    <span data-ttu-id="1952d-119">Az oldal további mezőinek többségét nem kötelező kitölteni, így lehetősége van arra, hogy csak a minimálisan szükségesnek tartott mennyiségű adatot adja meg.</span><span class="sxs-lookup"><span data-stu-id="1952d-119">Most of the other fields on the page are optional, and you can enter as little or as much information as you want.</span></span>

    <span data-ttu-id="1952d-120">A következő lista bemutatja a támogatási részletek lap egyes gyorslapján megadott adatokat:</span><span class="sxs-lookup"><span data-stu-id="1952d-120">The following list describes the information that is specified on each FastTab of the grant details page:</span></span>

    - <span data-ttu-id="1952d-121">**Általános** – Adja meg a támogatás nevét, állapotát, leírását, célját és összegét.</span><span class="sxs-lookup"><span data-stu-id="1952d-121">**General** – Enter the grant name, status, description, purpose, and amount.</span></span>
    - <span data-ttu-id="1952d-122">**Kapcsolattartási adatok** – Adja meg a támogatást kezelő munkatársakkal és a részleggel kapcsolatos adatokat, valamint annak a vevőnek vagy szervezetnek az adatait, aki vagy amely a támogatás forrása.</span><span class="sxs-lookup"><span data-stu-id="1952d-122">**Contact information** – Enter details about staff members, the department that manages the grant, and the grant customer or organization source of the grant.</span></span> <span data-ttu-id="1952d-123">Azt is jelezheti, hogy a szervezet egy továbbító entitás-e, amely megkapja a támogatást, majd továbbítja azt egy másik címzettnek.</span><span class="sxs-lookup"><span data-stu-id="1952d-123">You can also indicate whether your organization is a pass-through entity that receives the grant and then passes it on to another recipient.</span></span> <span data-ttu-id="1952d-124">Válassza a **Hozzáadás** lehetőséget a támogatást nyújtó szervezet kapcsolattartási adatainak, például a telefonszámának és az e-mail címének megadásához.</span><span class="sxs-lookup"><span data-stu-id="1952d-124">Select **Add** to add contact information such as telephone numbers and email addresses for the organization that provides the grant.</span></span>
    - <span data-ttu-id="1952d-125">**Dátumok és határidők** – Adja meg a támogatáshoz és a támogatási pályázathoz kapcsolódó dátumokat.</span><span class="sxs-lookup"><span data-stu-id="1952d-125">**Dates and deadlines** – Enter dates that are related to the grant and the grant application.</span></span> <span data-ttu-id="1952d-126">Példák erre a pályázat esedékességi dátuma, a benyújtás dátuma, valamint azt a dátumot, amikor a támogatás jóváhagyása vagy elutasítása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="1952d-126">Examples include the application due date, the submission date, and the date when the grant is approved or rejected.</span></span>
    - <span data-ttu-id="1952d-127">**Kapcsolódó projektek és projektszerződések** – Csak akkor adhat meg információt erre a gyorslapra, ha a **Támogatási állapot** mező az **Általános** gyorslapon **Aktív** vagy **Megítélt** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="1952d-127">**Associated projects and project contracts** – You can enter information on this FastTab only if the **Grant status** field on the **General** FastTab is set to **Active** or **Awarded**.</span></span> <span data-ttu-id="1952d-128">A kapcsolódó feladat végrehajtásához a következő lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="1952d-128">Select among the following options to complete the related task:</span></span>

        - <span data-ttu-id="1952d-129">**Finanszírozási forrás hozzáadása** – Új finanszírozási forrás bevonása a támogatásba.</span><span class="sxs-lookup"><span data-stu-id="1952d-129">**Add funding source** – Add a new funding source for the grant.</span></span> <span data-ttu-id="1952d-130">Az adatokat megadhatja azonnal, vagy használhatja az alapértelmezett adatokat, amelyeket később módosíthat.</span><span class="sxs-lookup"><span data-stu-id="1952d-130">You can enter all the details now, or you can use default information and then update it later.</span></span>
        - <span data-ttu-id="1952d-131">**Projektszerződés hozzáadása** – Projektszerződések-adatok hozzáadása vagy módosítása.</span><span class="sxs-lookup"><span data-stu-id="1952d-131">**Add project contract** – Add or update project contract information.</span></span>
        - <span data-ttu-id="1952d-132">**Projekt hozzáadása** – A projekt részletes adatainak hozzáadása vagy módosítása.</span><span class="sxs-lookup"><span data-stu-id="1952d-132">**Add project** – Add or update project details.</span></span>

    - <span data-ttu-id="1952d-133">**Beállítás** – Adja meg a kiegészítő finanszírozások adatait, ha ez az információ szükséges.</span><span class="sxs-lookup"><span data-stu-id="1952d-133">**Setup** – Enter details about matching funds, if this information is required.</span></span> <span data-ttu-id="1952d-134">Számos szervezet, amely támogatásokat nyújt, előírja, hogy a támogatottak a saját pénzükből vagy erőforrásaikból meghatározott összeggel kiegészítsék a támogatás megítélt összegét.</span><span class="sxs-lookup"><span data-stu-id="1952d-134">Many organizations that award grants require that recipients spend a specific amount of their own money or resources, to match the amount that is awarded in the grant.</span></span> <span data-ttu-id="1952d-135">A **Helyi projekt vagy nyomkövetési azonosító** mezőben adjon meg egy azonosítót, amely eltér a projekt azonosítójától.</span><span class="sxs-lookup"><span data-stu-id="1952d-135">In the **Local project or tracking ID** field, you can enter an identifier that differs from the project identifier.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1952d-136">Állítsa az **Altámogató** lehetőséget **Igen** értékre támogatás egy része egy másik szervezetnek lesz odaítélve.</span><span class="sxs-lookup"><span data-stu-id="1952d-136">If part of the grant will be awarded to a different organization, set the **Subgrantor** option to **Yes**.</span></span> <span data-ttu-id="1952d-137">Az Egyesült Államok területén odaítélt támogatások esetében meghatározhatja, hogy a támogatást állami megbízás vagy szövetségi megbízás alapján kell odaítélni.</span><span class="sxs-lookup"><span data-stu-id="1952d-137">For grants that are awarded in the United States, you can specify whether a grant will be awarded under a state mandate or a federal mandate.</span></span>

    - <span data-ttu-id="1952d-138">**Lehívás részletei** – Adja meg vagy módosítsa a támogatási alapok visszavonhatóságának, számlázhatóságának vagy felhasználhatóságának gyakoriságára vonatkozó információt.</span><span class="sxs-lookup"><span data-stu-id="1952d-138">**Drawdown details** – Add or update information about how often grant funds can be withdrawn, billed for, or spent.</span></span>

## <a name="create-a-new-grant-from-a-copy"></a><span data-ttu-id="1952d-139">Új támogatás létrehozása másolatból</span><span class="sxs-lookup"><span data-stu-id="1952d-139">Create a new grant from a copy</span></span>

1. <span data-ttu-id="1952d-140">Ugorjon a **Projektvezetés és könyvelés** \> **Támogatások** \> **Támogatások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1952d-140">Go to **Project management and accounting** \> **Grants** \> **Grants**.</span></span>
2. <span data-ttu-id="1952d-141">Válassza az **Új** \> **Másolat kiválasztása a támogatásból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1952d-141">Select **New** \> **Copy from grant**.</span></span>
3. <span data-ttu-id="1952d-142">Adjon meg egy alfanumerikus azonosítót és egy nevet az új támogatásnak, és válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1952d-142">Enter an alphanumeric identifier and a name for the new grant, and then select **OK**.</span></span>
4. <span data-ttu-id="1952d-143">A támogatás részletei lapon tekintse át a másolt támogatás adatait, és végezze el a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="1952d-143">On the grant details page, review the details of the copied grant, and make any changes that are required.</span></span> <span data-ttu-id="1952d-144">Az oldal legtöbb mezője nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="1952d-144">Most of the fields on the page are optional.</span></span>

## <a name="view-or-modify-grant-details"></a><span data-ttu-id="1952d-145">A támogatás részleteinek megtekintése vagy módosítása</span><span class="sxs-lookup"><span data-stu-id="1952d-145">View or modify grant details</span></span>

1. <span data-ttu-id="1952d-146">Ugorjon a **Projektvezetés és könyvelés** \> **Támogatások** \> **Támogatások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1952d-146">Go to **Project management and accounting** \> **Grants** \> **Grants**.</span></span>
2. <span data-ttu-id="1952d-147">Válassza ki a módosítani kívánt támogatást.</span><span class="sxs-lookup"><span data-stu-id="1952d-147">Select the grant to modify.</span></span>
3. <span data-ttu-id="1952d-148">A Műveleti ablaktáblán a **Támogatás** lapján a **Karbantartás** csoportban válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1952d-148">On the Action Pane, on the **Grant** tab, in the **Maintain** group, select **Edit**.</span></span>
4. <span data-ttu-id="1952d-149">Tekintse át a támogatás adatait, és végezze el a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="1952d-149">Review the grant details, and make any changes that are required.</span></span>
