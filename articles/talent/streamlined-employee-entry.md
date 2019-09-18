---
title: Korszerű alkalmazotti belépés és navigálás
description: A Dynamics 365 for Talent dolgozóira vonatkozó adatbevitel révén gyorsan be lehet vinni az adatokat minden egykori, aktív és jövőbeli dolgozó esetében. Frissítettük az egyszerűsített/összesített navigációs modellt, hogy gyorsan meg lehessen találni a keresett információkat, illetve végre lehessen hajtani a szükséges módosításokat.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: be0253ffc4396f36050ef02c51a20d378e44473d
ms.sourcegitcommit: 4176c333ce3f88c5c68e95bd47e5791d32365dd2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2019
ms.locfileid: "1918203"
---
# <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="7f75b-104">Korszerű alkalmazotti belépés és navigálás</span><span class="sxs-lookup"><span data-stu-id="7f75b-104">Streamlined employee entry and navigation</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7f75b-105">A Dynamics 365 for Talent lehetővé teszi az alkalmazotti és foglalkoztatási adatok hatékony bevitelét.</span><span class="sxs-lookup"><span data-stu-id="7f75b-105">Dynamics 365 for Talent allows efficient entry of employee and employment data.</span></span> <span data-ttu-id="7f75b-106">A múltbeli, aktív és jövőbeli alkalmazottak és alvállalkozók esetében gyorsan frissítheti a munkaelőzmények adatait.</span><span class="sxs-lookup"><span data-stu-id="7f75b-106">You can quickly update work history information for past, active, and future employees and contractors.</span></span>

<span data-ttu-id="7f75b-107">Továbbá engedélyezhet egy egyszerűsített navigációs élményt is, hogy gyorsan megtalálhassa a kapcsolódó adatokat, és elvégezhesse a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="7f75b-107">You can also enable a simplified navigation experience to quickly find related information and make any necessary changes.</span></span> <span data-ttu-id="7f75b-108">Ez a funkció jelenleg a sandbox környezetekben érhető el.</span><span class="sxs-lookup"><span data-stu-id="7f75b-108">This functionality is now available in sandbox environments.</span></span> <span data-ttu-id="7f75b-109">A funkció bekapcsolásához navigáljon a **Rendszer-adminisztráció > Hivatkozások > Beállítás > Rendszerparaméterek > előnézeti funkciók** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="7f75b-109">To turn this feature on, navigate to **System administration > Links > Setup > System parameters > Preview features**.</span></span> <span data-ttu-id="7f75b-110">Válassza a **Továbbfejlesztett dolgozói képernyő és navigáció** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7f75b-110">Select **Enhanced worker form and navigation**.</span></span> <span data-ttu-id="7f75b-111">Ez minden felhasználó számára engedélyezi a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="7f75b-111">This will enable these changes for all users.</span></span> <span data-ttu-id="7f75b-112">Ezt a beállítást bármikor ki lehet kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="7f75b-112">You can turn this option off at any time.</span></span>

## <a name="view-options"></a><span data-ttu-id="7f75b-113">Nézet beállításai</span><span class="sxs-lookup"><span data-stu-id="7f75b-113">View options</span></span>

<span data-ttu-id="7f75b-114">A dolgozói képernyő **Nézetbeállításaival** kiválaszthatja az alkalmazottak és alvállalkozók tetszőleges kombinációját egyetlen listából.</span><span class="sxs-lookup"><span data-stu-id="7f75b-114">You can use **View options** on the worker form to select any combination of employees and contractors from a single list.</span></span> <span data-ttu-id="7f75b-115">Ezen beállítások segítségével a jogi személyeknél vagy a jelenleg bejelentkezett jogi személynél nézheti meg a dolgozókat.</span><span class="sxs-lookup"><span data-stu-id="7f75b-115">These options allow you to view workers across legal entities or for the legal entity you're currently signed into.</span></span> <span data-ttu-id="7f75b-116">Ezenkívül megtekintheti az aktív, függő és kilépett dolgozókat, és a dolgozó (alkalmazott vagy vállalkozó) típusától függően korlátozhatja a találatokat.</span><span class="sxs-lookup"><span data-stu-id="7f75b-116">You can also view active, pending, and exited workers, and you can restrict results based on the type of worker (employee or contractor).</span></span> <span data-ttu-id="7f75b-117">Ha a speciális biztonság engedélyezve van, akkor csak azokat az alkalmazottakat és alvállalkozókat fogja látni, akik az Ön számára hozzáférhető jogi személynél találhatók.</span><span class="sxs-lookup"><span data-stu-id="7f75b-117">If advanced security is enabled, you will only see those employees and contractors in the legal entities you have access to.</span></span>

<span data-ttu-id="7f75b-118">A listanézet oszlopai az Ön választásai alapján változnak.</span><span class="sxs-lookup"><span data-stu-id="7f75b-118">Columns in the list view change based on your selections.</span></span> <span data-ttu-id="7f75b-119">A kilépett alkalmazottak megtekintésekor például a megszűnés dátuma és az okkódok a lista további oszlopaiként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="7f75b-119">For example, when viewing exited employees, the termination date and reason codes display as additional columns in the list.</span></span> 

<span data-ttu-id="7f75b-120">[![Nézet beállításai](./media/Worker-view-option.png)](./media/worker-view-option.png)</span><span class="sxs-lookup"><span data-stu-id="7f75b-120">[![View options](./media/Worker-view-option.png)](./media/worker-view-option.png)</span></span>

## <a name="navigation-and-banner"></a><span data-ttu-id="7f75b-121">Navigáció és szalagcím</span><span class="sxs-lookup"><span data-stu-id="7f75b-121">Navigation and banner</span></span>

<span data-ttu-id="7f75b-122">A szalagcímek az egyes dolgozókra vonatkozó alapvető információkat jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="7f75b-122">A banner displays key information for each worker.</span></span> <span data-ttu-id="7f75b-123">Az aktív dolgozók szalagcímei a következő mezőket jelenítik meg:</span><span class="sxs-lookup"><span data-stu-id="7f75b-123">The banner for active workers displays the following fields:</span></span>

- <span data-ttu-id="7f75b-124">**Beosztás**</span><span class="sxs-lookup"><span data-stu-id="7f75b-124">**Title**</span></span>
- <span data-ttu-id="7f75b-125">**Részleg**</span><span class="sxs-lookup"><span data-stu-id="7f75b-125">**Department**</span></span>
- <span data-ttu-id="7f75b-126">**Beosztás típusa**</span><span class="sxs-lookup"><span data-stu-id="7f75b-126">**Position type**</span></span>
- <span data-ttu-id="7f75b-127">**Dolgozó típusa**</span><span class="sxs-lookup"><span data-stu-id="7f75b-127">**Worker type**</span></span>
- <span data-ttu-id="7f75b-128">**Vezető**</span><span class="sxs-lookup"><span data-stu-id="7f75b-128">**Manager**</span></span>
- <span data-ttu-id="7f75b-129">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="7f75b-129">**Legal entity**</span></span>

<span data-ttu-id="7f75b-130">A távozó dolgozók szalagcímei a következő mezőket jelenítik meg:</span><span class="sxs-lookup"><span data-stu-id="7f75b-130">The banner for exited workers displays the following fields:</span></span>

- <span data-ttu-id="7f75b-131">**Kilépés dátuma**</span><span class="sxs-lookup"><span data-stu-id="7f75b-131">**Exited date**</span></span>
- <span data-ttu-id="7f75b-132">**Jogcím**</span><span class="sxs-lookup"><span data-stu-id="7f75b-132">**Reason**</span></span>

<span data-ttu-id="7f75b-133">A függőben lévő dolgozók szalagcímei a következő mezőket jelenítik meg:</span><span class="sxs-lookup"><span data-stu-id="7f75b-133">The banner for pending employees displays the following fields:</span></span>

- <span data-ttu-id="7f75b-134">**Beosztás**</span><span class="sxs-lookup"><span data-stu-id="7f75b-134">**Title**</span></span>
- <span data-ttu-id="7f75b-135">**Részleg**</span><span class="sxs-lookup"><span data-stu-id="7f75b-135">**Department**</span></span>
- <span data-ttu-id="7f75b-136">**Beosztás típusa**</span><span class="sxs-lookup"><span data-stu-id="7f75b-136">**Position type**</span></span>
- <span data-ttu-id="7f75b-137">**Vezető**</span><span class="sxs-lookup"><span data-stu-id="7f75b-137">**Manager**</span></span>
- <span data-ttu-id="7f75b-138">**Kezdő dátum**</span><span class="sxs-lookup"><span data-stu-id="7f75b-138">**Starting date**</span></span>
- <span data-ttu-id="7f75b-139">**Jogi személy**</span><span class="sxs-lookup"><span data-stu-id="7f75b-139">**Legal entity**</span></span>

<span data-ttu-id="7f75b-140">A dolgozói oldal műveleti ablakát átrendeztük, így kevesebb beállítás jelenik meg rajta.</span><span class="sxs-lookup"><span data-stu-id="7f75b-140">The action pane of the worker page has been re-organized to include fewer options.</span></span> <span data-ttu-id="7f75b-141">A rendszer mostantól a következő kategóriákba rendezi az adatokat:</span><span class="sxs-lookup"><span data-stu-id="7f75b-141">Information is now organized in the following categories:</span></span> 

- <span data-ttu-id="7f75b-142">Munka</span><span class="sxs-lookup"><span data-stu-id="7f75b-142">Work</span></span>
- <span data-ttu-id="7f75b-143">Személy</span><span class="sxs-lookup"><span data-stu-id="7f75b-143">Person</span></span>
- <span data-ttu-id="7f75b-144">Kilépés</span><span class="sxs-lookup"><span data-stu-id="7f75b-144">Leave</span></span>
- <span data-ttu-id="7f75b-145">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="7f75b-145">Compensation</span></span>
- <span data-ttu-id="7f75b-146">Előnyök</span><span class="sxs-lookup"><span data-stu-id="7f75b-146">Benefits</span></span>
- <span data-ttu-id="7f75b-147">Megfelelés</span><span class="sxs-lookup"><span data-stu-id="7f75b-147">Compliance</span></span>

<span data-ttu-id="7f75b-148">Ezenkívül a fő dolgozói lap **Hivatkozások** lapján a felhasználók egy központi helyen férhetnek hozzá a kapcsolódó információkhoz egy dolgozóról.</span><span class="sxs-lookup"><span data-stu-id="7f75b-148">In addtion, a new **Links** tab on the main worker page gives users a central location to access all related information for a worker.</span></span>

<span data-ttu-id="7f75b-149">A változtatások miatt előfordulhat, hogy az adatok más helyen jelennnek meg, mint eddig.</span><span class="sxs-lookup"><span data-stu-id="7f75b-149">Due to these changes, information may appear in a different location than you're used to.</span></span> <span data-ttu-id="7f75b-150">Például a dolgozói képernyőn korábban megjelenő bérlista-adatok megjelennek a műveleti ablaktáblában a **Kompenzáció > Bérlista** pontnálmodulban, és a **Személyes adatok** lap mostantól tartalmazza a **További információk** gombot a nem gyakran megnyitott mezők elrejtéséhez.</span><span class="sxs-lookup"><span data-stu-id="7f75b-150">For example, payroll information that previously displayed on the worker form now appears in the action pane under **Compensation > Payroll**, and the **Personal information** tab now has a **More information** button to hide fields that aren't accessed often.</span></span>

<span data-ttu-id="7f75b-151">[![Szalagcím](./media/Banner.png)](./media/Banner.png)</span><span class="sxs-lookup"><span data-stu-id="7f75b-151">[![Banner](./media/Banner.png)](./media/Banner.png)</span></span>

## <a name="work-history"></a><span data-ttu-id="7f75b-152">Munkaelőzmények</span><span class="sxs-lookup"><span data-stu-id="7f75b-152">Work history</span></span>

<span data-ttu-id="7f75b-153">A **Munkaelőzmények** lapon láthatók a munkaelőzmények az összes jogi személyre vonatkozóan, és elérhetők a kilépett, az aktív és a függőben lévő alkalmazottakhoz és alvállalkozókhoz is.</span><span class="sxs-lookup"><span data-stu-id="7f75b-153">The **Work history** tab shows work history accross all legal entities and is available for exited, active, and pending employees and contractors.</span></span> <span data-ttu-id="7f75b-154">Mostantól bármikor megtekintheti az összes munkaelőzményt az Ön számára elérhető jogi személyeknél.</span><span class="sxs-lookup"><span data-stu-id="7f75b-154">You can now view all work history at once for the legal entities you have access to.</span></span> <span data-ttu-id="7f75b-155">Ezenkívül az egyes munkaelőzmények bejegyzéseivel kapcsolatos adatokat az adatkörnyezet módosítása nélkül is szerkesztheti.</span><span class="sxs-lookup"><span data-stu-id="7f75b-155">In addition, you can edit information for each of the work history entries without changing the data context.</span></span> <span data-ttu-id="7f75b-156">Az összes adatot közvetlenül a lapon frissítheti.</span><span class="sxs-lookup"><span data-stu-id="7f75b-156">You can update all information directly on the page.</span></span> 

<span data-ttu-id="7f75b-157">[![Munkaelőzmények](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span><span class="sxs-lookup"><span data-stu-id="7f75b-157">[![Work history](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span></span>

## <a name="position-history"></a><span data-ttu-id="7f75b-158">Beosztások előzményei</span><span class="sxs-lookup"><span data-stu-id="7f75b-158">Position history</span></span>

<span data-ttu-id="7f75b-159">A fő dolgozói lap **Beosztások** lapja teljes áttekintést nyújt a szervezeten belüli beosztásokról, beleértve a múltbeli, a jelenlegi és a jövőbeli hozzárendeléseket is.</span><span class="sxs-lookup"><span data-stu-id="7f75b-159">The **Positions** tab on the main worker page provides a full view of all positions held within the organization, including past, present, and any future assignments.</span></span> <span data-ttu-id="7f75b-160">A műveletablakban továbbra is közvetlenül a dolgozó beosztásának előzményeihez lehet navigálni.</span><span class="sxs-lookup"><span data-stu-id="7f75b-160">You can still navigate directly to the worker's position history in the action pane as well.</span></span>

<span data-ttu-id="7f75b-161">[![Beosztások](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span><span class="sxs-lookup"><span data-stu-id="7f75b-161">[![Positions](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span></span>

