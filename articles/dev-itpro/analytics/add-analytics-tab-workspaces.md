---
title: "Analitika hozzáadása munkaterületekhez Power BI Embedded használatával"
description: "Ez a témakör bemutatja, hogy miként ágyazható be egy Power BI jelentés egy munkaterület Elemzés lapjára."
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Operations, Platform
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.intro: Platform update 8
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 677e008279b9f233026f87e469cbabb8c8bcf801
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a><span data-ttu-id="d9d88-103">Analitika hozzáadása munkaterületekhez Power BI Embedded használatával</span><span class="sxs-lookup"><span data-stu-id="d9d88-103">Add analytics to workspaces by using Power BI Embedded</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="d9d88-104">Ez a funkció a Dynamics 365 for Finance and Operationsben támogatott (7.2-es vagy újabb verzió).</span><span class="sxs-lookup"><span data-stu-id="d9d88-104">This feature is supported in Dynamics 365 for Finance and Operations (version 7.2 and later).</span></span>

# <a name="introduction"></a><span data-ttu-id="d9d88-105">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="d9d88-105">Introduction</span></span>
<span data-ttu-id="d9d88-106">Ez a témakör bemutatja, hogy miként ágyazható be egy Microsoft Power BI jelentés egy munkaterület **Elemzés** lapjára.</span><span class="sxs-lookup"><span data-stu-id="d9d88-106">This topic shows how to embed a Microsoft Power BI report on the **Analytics** tab of a workspace.</span></span> <span data-ttu-id="d9d88-107">Például az itt megadott ajánlott kiterjed a **foglalási kezelési** a flottában-kezelés alkalmazást az analitikus munkaterület beágyazása a munkaterület egy **analitika** lapon.</span><span class="sxs-lookup"><span data-stu-id="d9d88-107">For the example that is given here, we will extend the **Reservation management** workspace in the Fleet Management application to embed an analytical workspace on an **Analytics** tab.</span></span>

# <a name="prerequisites"></a><span data-ttu-id="d9d88-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="d9d88-108">Prerequisites</span></span>
+ <span data-ttu-id="d9d88-109">A fejlesztői környezet 8-as vagy újabb Platform frissítés futó való hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="d9d88-109">Access to a developer environment that runs Platform update 8 or later.</span></span>
+ <span data-ttu-id="d9d88-110">Analitikai bizonylat (.pbix fájl), amely Microsoft kiemelt az üzleti Intelligencia asztal használata lett létrehozva, és, amelynek van az entitás üzletadatbázishoz származó adatok modellről.</span><span class="sxs-lookup"><span data-stu-id="d9d88-110">An analytical report (.pbix file) that was created by using Microsoft Power BI Desktop, and that has a data model that is sourced from the Entity store database.</span></span>

# <a name="overview"></a><span data-ttu-id="d9d88-111">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="d9d88-111">Overview</span></span>
<span data-ttu-id="d9d88-112">Alkalmazás meglévő munkaterülethez kiterjesztése, vagy saját új munkaterület bevezetésének, beágyazott elemző nézetek segítségével az üzleti adatokban osztályon és interaktív nézetei szállítani.</span><span class="sxs-lookup"><span data-stu-id="d9d88-112">Whether you extend an existing application workspace or introduce a new workspace of your own, you can use embedded analytical views to deliver insightful and interactive views of your business data.</span></span> <span data-ttu-id="d9d88-113">A folyamat hozzáadása egy analitikai munkaterület lap négy lépés tartozik.</span><span class="sxs-lookup"><span data-stu-id="d9d88-113">The process for adding an analytical workspace tab has four steps.</span></span>

1. <span data-ttu-id="d9d88-114">Dynamics 365 erőforrásként .pbix fájlt hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="d9d88-114">Add a .pbix file as a Dynamics 365 resource.</span></span>
2. <span data-ttu-id="d9d88-115">Határozza meg az analitikus munkaterület lapon.</span><span class="sxs-lookup"><span data-stu-id="d9d88-115">Define an analytical workspace tab.</span></span>
3. <span data-ttu-id="d9d88-116">A munkaterület lap .pbix erőforrás beágyazása.</span><span class="sxs-lookup"><span data-stu-id="d9d88-116">Embed the .pbix resource on the workspace tab.</span></span>
4. <span data-ttu-id="d9d88-117">Választható: A nézet testreszabásához bővítmények.</span><span class="sxs-lookup"><span data-stu-id="d9d88-117">Optional: Add extensions to customize the view.</span></span>

> [!NOTE]
> <span data-ttu-id="d9d88-118">Elemzési jelentések létrehozásával kapcsolatos további tudnivalókat lásd: [Power az üzleti Intelligencia asztali – első lépések](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="d9d88-118">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span> <span data-ttu-id="d9d88-119">Ez a lap elévült vonatkozó információkat, melyek segítséget nyújtanak arra az elemzési jelentés megoldások létrehozása esetén.</span><span class="sxs-lookup"><span data-stu-id="d9d88-119">This page is a great source for insights that can help you create compelling analytical reporting solutions.</span></span>

# <a name="add-a-pbix-file-as-a-resource"></a><span data-ttu-id="d9d88-120">Erőforrásként .pbix fájlt kell hozzáadni</span><span class="sxs-lookup"><span data-stu-id="d9d88-120">Add a .pbix file as a resource</span></span>
<span data-ttu-id="d9d88-121">Mielőtt elkezdené, létre kell hoznia vagy a kiemelt Üzletiintelligencia-jelentés beágyazza a munkaterület beszerzése.</span><span class="sxs-lookup"><span data-stu-id="d9d88-121">Before you begin, you must create or obtain the Power BI report that you will embed in the workspace.</span></span> <span data-ttu-id="d9d88-122">Elemzési jelentések létrehozásával kapcsolatos további tudnivalókat lásd: [Power az üzleti Intelligencia asztali – első lépések](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="d9d88-122">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span>
 
<span data-ttu-id="d9d88-123">Adja meg a Visual Studio projekt műtermék .pbix fájl lépésekkel.</span><span class="sxs-lookup"><span data-stu-id="d9d88-123">Follow these steps to add a .pbix file as a Visual Studio project artifact.</span></span>

1. <span data-ttu-id="d9d88-124">Hozzon létre egy új projektet a megfelelő modellben.</span><span class="sxs-lookup"><span data-stu-id="d9d88-124">Create a new project in the appropriate model.</span></span>
2. <span data-ttu-id="d9d88-125">A Solution Explorer alkalmazásban válassza ki a projektet, kattintson rá jobb gombbal, majd válassza ki a **Hozzáadás** > **Új elem** pontot.</span><span class="sxs-lookup"><span data-stu-id="d9d88-125">In Solution Explorer, select the project, right-click, and then select **Add** > **New Item**.</span></span>
3. <span data-ttu-id="d9d88-126">Az a **új elem hozzáadása** párbeszédpanel **műveletek műtermékek**, jelölje be a **erőforrás** sablon.</span><span class="sxs-lookup"><span data-stu-id="d9d88-126">In the **Add New Item** dialog box, under **Operations Artifacts**, select the **Resource** template.</span></span>
4. <span data-ttu-id="d9d88-127">Írjon be egy nevet, amely veszi figyelembe a jelentés X ++ metaadatokban hivatkozik, és kattintson a **hozzáadása**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-127">Enter a name that will be used to reference the report in X++ metadata, and then click **Add**.</span></span>

    ![Új elem párbeszédpanelen hozzáadása](media/analytical-workspace-add.png)

5. <span data-ttu-id="d9d88-129">Keresse meg a .pbix fájlt, amely tartalmazza az elemzési jelentés, és kattintson a **nyitott**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-129">Find the .pbix file that contains the definition of the analytical report, and then click **Open**.</span></span>

    ![Válassza ki az erőforrás párbeszédpanel jelenik meg](media/analytical-workspace-select-resource.png)
  
<span data-ttu-id="d9d88-131">Dynamics 365 erőforrásként felvett .pbix fájl, hogy a jelentések beágyazása munkaterületek, és közvetlen kapcsolatokat menüelemek vehet fel.</span><span class="sxs-lookup"><span data-stu-id="d9d88-131">Now that you've added the .pbix file as a Dynamics 365 resource, you can embed the reports in workspaces and add direct links by using menu items.</span></span>

# <a name="add-a-tab-control-to-an-application-workspace"></a><span data-ttu-id="d9d88-132">Az alkalmazás munkaterületének lap vezérlő hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d9d88-132">Add a tab control to an application workspace</span></span>
<span data-ttu-id="d9d88-133">Ebben a példában ajánlott kiterjed a **foglalási kezelése** munkaterület hozzáadásával flottában felügyeleti modellben a **analitika** meghatározásának lap a **FMClerkWorkspace** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="d9d88-133">In this example, we will extend the **Reservation management** workspace in the Fleet Management model by adding the **Analytics** tab to the definition of the **FMClerkWorkspace** form.</span></span>
 
<span data-ttu-id="d9d88-134">A következő ábra azt mutatja, hogy mi a **FMClerkWorkspace** képernyőn dolgozunk a Microsoft Visual Studio-tervezőben.</span><span class="sxs-lookup"><span data-stu-id="d9d88-134">The following illustration shows what the **FMClerkWorkspace** form looks like in the designer in Microsoft Visual Studio.</span></span>

![A képernyőn FMClerkWorkspace változtatások előtt](media/analytical-workspace-definition-before.png)

<span data-ttu-id="d9d88-136">Kövesse az alábbi lépéseket képernyő definíció kiterjeszteni az **foglalási kezelési** munkaterület.</span><span class="sxs-lookup"><span data-stu-id="d9d88-136">Follow these steps to extend the form definition for the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="d9d88-137">Nyissa meg a képernyőtervezőben tervezési definíciójának bővítésére.</span><span class="sxs-lookup"><span data-stu-id="d9d88-137">Open the form designer to extend the design definition.</span></span>
2. <span data-ttu-id="d9d88-138">A tervezési meghatározásában, válassza ki a felső elem címkéje **tervezési | Minta: Munkaterület üzemi**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-138">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
3. <span data-ttu-id="d9d88-139">Kattintson a jobb gombbal, majd a **új** > **lap** nevű új vezérlő hozzáadása **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-139">Right-click, and then select **New** > **Tab** to add a new control that is named **FormTabControl1**.</span></span>
4. <span data-ttu-id="d9d88-140">A képernyőtervezőben válassza: **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-140">In the form designer, select **FormTabControl1**.</span></span>
5. <span data-ttu-id="d9d88-141">Kattintson a jobb gombbal, majd a **új lap** hozzáadása egy új lap.</span><span class="sxs-lookup"><span data-stu-id="d9d88-141">Right-click, and then select **New Tab Page** to add a new tab page.</span></span>
6. <span data-ttu-id="d9d88-142">Nevezze át a lap következhet, mint például **munkaterület**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-142">Rename the tab page to something meaningful, such as **Workspace**.</span></span>
7. <span data-ttu-id="d9d88-143">A képernyőtervezőben válassza: **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-143">In the form designer, select **FormTabControl1**.</span></span>
8. <span data-ttu-id="d9d88-144">Válasszon egy feladatot, kattintson rá a jobb gombbal, majd válassza az **Új lap oldal** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="d9d88-144">Right-click, and then select **New Tab Page**.</span></span>
9. <span data-ttu-id="d9d88-145">Nevezze át a lap következhet, mint például **Elemzés**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-145">Rename the tab page to something meaningful, such as **Analytics**.</span></span>
10. <span data-ttu-id="d9d88-146">Az űrlap-tervezőben, jelölje be a **analitika (lapon)**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-146">In the form designer, select **Analytics (Tab Page)**.</span></span>
11. <span data-ttu-id="d9d88-147">A **Felirat**  tulajdonságot **Elemzés** értékre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="d9d88-147">Set the **Caption** property to **Analytics**.</span></span>
12. <span data-ttu-id="d9d88-148">Kattintson a jobb gombbal a vezérlőelem, és adja meg **új** > **csoport** új űrlapvezérlő csoport hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="d9d88-148">Right-click the control, and then select **New** > **Group** to add a new form group control.</span></span>
13. <span data-ttu-id="d9d88-149">Nevezze át a lap következhet, mint például **powerBIReportGroup**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-149">Rename the form group to something meaningful, such as **powerBIReportGroup**.</span></span>
14. <span data-ttu-id="d9d88-150">Az űrlap-tervezőben, jelölje be a **PanoramaBody (lap)**, és húzza a vezérlő a **munkaterület** lapon.</span><span class="sxs-lookup"><span data-stu-id="d9d88-150">In the form designer, select **PanoramaBody (Tab)**, and then drag the control onto the **Workspace** tab.</span></span>
15. <span data-ttu-id="d9d88-151">A tervezési meghatározásában, válassza ki a felső elem címkéje **tervezési |} Minta: Munkaterület üzemi**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-151">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
16. <span data-ttu-id="d9d88-152">Válasszon egy feladatot, kattintson rá a jobb gombbal, majd válassza a **Minta eltávolítása** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="d9d88-152">Right-click, and then select **Remove pattern**.</span></span>
17. <span data-ttu-id="d9d88-153">Kattintson ismét jobb gombbal, és adja meg **Hozzáadás minta** > **munkaterület többlapos**.</span><span class="sxs-lookup"><span data-stu-id="d9d88-153">Right-click again, and then select **Add pattern** > **Workspace Tabbed**.</span></span>
18. <span data-ttu-id="d9d88-154">A build ellenőrizheti a módosítások végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="d9d88-154">Perform a build to verify your changes.</span></span>
 
<span data-ttu-id="d9d88-155">A következő ábra mutatja, hogy a terv néz módosítások alkalmazása után.</span><span class="sxs-lookup"><span data-stu-id="d9d88-155">The following illustration shows what the design looks like after these changes are applied.</span></span>

![Módosítások után FMClerkWorkspace](media/analytical-workspace-definition-after.png)

<span data-ttu-id="d9d88-157">Most, hogy a munkaterület jelentés beágyazása használt űrlap-vezérlőelemek felvett tulajdonságaként méretét, hogy így alkalmazkodik az elrendezés kell megadni.</span><span class="sxs-lookup"><span data-stu-id="d9d88-157">Now that you've added the form controls that will be used to embed the workspace report, you must define the size of the parent control so that it accommodates the layout.</span></span> <span data-ttu-id="d9d88-158">Alapértelmezés szerint mind **szűrők ablak** lap és a **lap** oldal a jelentésen látható lesz.</span><span class="sxs-lookup"><span data-stu-id="d9d88-158">By default, both the **Filters Pane** page and the **Tab** page will be visible on the report.</span></span> <span data-ttu-id="d9d88-159">Ezeket a vezérlőelemeket a jelentés a cél fogyasztó megfelelő láthatóságát azonban módosítható.</span><span class="sxs-lookup"><span data-stu-id="d9d88-159">However, you can change the visibility of these controls as appropriate for the target consumer of the report.</span></span>
 
> [!NOTE]
> <span data-ttu-id="d9d88-160">Beágyazott munkaterületek esetén javasoljuk, hogy a bővítmények használatával egyaránt rejtse el a **Szűrő ablaktábla** és a **Lap** oldalakat a konzisztencia érdekében.</span><span class="sxs-lookup"><span data-stu-id="d9d88-160">For embedded workspaces, we recommend that you use extensions to hide both the **Filters Pane** and **Tab** pages, for consistency.</span></span>
 
<span data-ttu-id="d9d88-161">Ekkor befejezte a jelentkezési lap definíciójának kiterjesztését.</span><span class="sxs-lookup"><span data-stu-id="d9d88-161">You've now completed the task of extending the application form definition.</span></span> <span data-ttu-id="d9d88-162">Testreszabott bővítmények segítségével a további tudnivalókat lásd:  [Testreszabás: Overlayering és bővítéseinek](../extensibility/customization-overlayering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="d9d88-162">For more information about how to use extensions to do customizations, see  [Customization: Overlayering and extensions](../extensibility/customization-overlayering-extensions.md).</span></span>

# <a name="add-x-business-logic-to-embed-a-viewer-control"></a><span data-ttu-id="d9d88-163">X ++ üzleti logikát a jelentésmegjelenítő vezérlőben beágyazása hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d9d88-163">Add X++ business logic to embed a viewer control</span></span>
<span data-ttu-id="d9d88-164">Kövesse az alábbi lépéseket, amely inicializálja a jelentésmegjelenítő vezérlőben beágyazott üzleti logikát szeretne adni a **foglalási kezelési** munkaterület.</span><span class="sxs-lookup"><span data-stu-id="d9d88-164">Follow these steps to add business logic that initializes the report viewer control that is embedded in the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="d9d88-165">Nyissa meg a **FMClerkWorkspace** képernyőtervezőt tervezési definíciójának bővítésére.</span><span class="sxs-lookup"><span data-stu-id="d9d88-165">Open the **FMClerkWorkspace** form designer to extend the design definition.</span></span>
2. <span data-ttu-id="d9d88-166">Nyomja le az F7 eléréséhez a kód megadása alapjául szolgáló kódot.</span><span class="sxs-lookup"><span data-stu-id="d9d88-166">Press F7 to access the code behind the code definition.</span></span>
3. <span data-ttu-id="d9d88-167">Adja hozzá a következő X++ kódot.</span><span class="sxs-lookup"><span data-stu-id="d9d88-167">Add the following X++ code.</span></span>

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;     
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                FMPBIWorkspaceController controller = new FMPBIWorkspaceController();
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
    }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. <span data-ttu-id="d9d88-168">A build ellenőrizheti a módosítások végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="d9d88-168">Perform a build to verify your changes.</span></span>

<span data-ttu-id="d9d88-169">Üzleti logika inicializálja a jelentésmegjelenítő vezérlőben beágyazott felvételét a feladat már befejeződött.</span><span class="sxs-lookup"><span data-stu-id="d9d88-169">You've now completed the task of adding business logic to initialize the embedded report viewer control.</span></span> <span data-ttu-id="d9d88-170">A következő ábra mutatja, hogy a munkaterület néz módosítások alkalmazása után.</span><span class="sxs-lookup"><span data-stu-id="d9d88-170">The following illustration shows what the workspace looks like after these changes are applied.</span></span>

![A munkaterület ágyazott jelentés](media/analytical-workspace-final.png)

> [!NOTE]
> <span data-ttu-id="d9d88-172">A meglévő működési nézet alatt az oldalcím a munkaterület lapok használatával hozzáfér.</span><span class="sxs-lookup"><span data-stu-id="d9d88-172">You can access the existing operational view by using the workspace tabs below the page title.</span></span>

# <a name="reference"></a><span data-ttu-id="d9d88-173">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="d9d88-173">Reference</span></span>

## <a name="pbireporthelperinitializereportcontrol-method"></a><span data-ttu-id="d9d88-174">PBIReportHelper.initializeReportControl mód</span><span class="sxs-lookup"><span data-stu-id="d9d88-174">PBIReportHelper.initializeReportControl method</span></span>
<span data-ttu-id="d9d88-175">Ez a szakasz a segítő osztály, amelynek használatával az üzleti Intelligencia teljesítmény jelentés (.pbix erőforrás) beágyazása csoport űrlapvezérlő kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="d9d88-175">This section provides information about the helper class that is used to embed a Power BI report (.pbix resource) in a form group control.</span></span>

### <a name="syntax"></a><span data-ttu-id="d9d88-176">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="d9d88-176">Syntax</span></span>
```
public static void initializeReportControl(
     str                 _resourceName,
     FormGroupControl    _formGroupControl,
     str                 _defaultPageName = '',
     boolean             _showFilterPane = false,
     boolean             _showNavPane = false,
     List                _defaultFilters = new List(Types::Class))
```

### <a name="parameters"></a><span data-ttu-id="d9d88-177">Paraméterek</span><span class="sxs-lookup"><span data-stu-id="d9d88-177">Parameters</span></span>

| <span data-ttu-id="d9d88-178">Név</span><span class="sxs-lookup"><span data-stu-id="d9d88-178">Name</span></span> | <span data-ttu-id="d9d88-179">Leírás</span><span class="sxs-lookup"><span data-stu-id="d9d88-179">Description</span></span> |
|---|---|
| <span data-ttu-id="d9d88-180">resourceName</span><span class="sxs-lookup"><span data-stu-id="d9d88-180">resourceName</span></span> | <span data-ttu-id="d9d88-181">A .pbix erőforrás neve</span><span class="sxs-lookup"><span data-stu-id="d9d88-181">The name of the .pbix resource.</span></span> |
| <span data-ttu-id="d9d88-182">formGroupControl</span><span class="sxs-lookup"><span data-stu-id="d9d88-182">formGroupControl</span></span> | <span data-ttu-id="d9d88-183">A képernyőn az üzleti Intelligencia teljesítmény jelentés vezérlőelem alkalmazandó csoportvezérlőnek.</span><span class="sxs-lookup"><span data-stu-id="d9d88-183">The form group control to apply the Power BI report control to.</span></span> |
| <span data-ttu-id="d9d88-184">defaultPageName</span><span class="sxs-lookup"><span data-stu-id="d9d88-184">defaultPageName</span></span> | <span data-ttu-id="d9d88-185">Alapértelmezett oldalnév.</span><span class="sxs-lookup"><span data-stu-id="d9d88-185">The default page name.</span></span> |
| <span data-ttu-id="d9d88-186">showFilterPane</span><span class="sxs-lookup"><span data-stu-id="d9d88-186">showFilterPane</span></span> | <span data-ttu-id="d9d88-187">Logikai érték, amely azt jelzi, hogy megjelenjen (**true**) vagy rejtve maradjon (**false**) a szűrés ablaktáblája.</span><span class="sxs-lookup"><span data-stu-id="d9d88-187">A Boolean value that indicates whether the filter pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="d9d88-188">showNavPane</span><span class="sxs-lookup"><span data-stu-id="d9d88-188">showNavPane</span></span> | <span data-ttu-id="d9d88-189">Logikai érték, amely azt jelzi, hogy megjelenjen (**true**) vagy rejtve maradjon (**false**) a navigációs ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="d9d88-189">A Boolean value that indicates whether the navigation pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="d9d88-190">defaultFilters</span><span class="sxs-lookup"><span data-stu-id="d9d88-190">defaultFilters</span></span> | <span data-ttu-id="d9d88-191">A Power BI jelentés alapértelmezett szűrői.</span><span class="sxs-lookup"><span data-stu-id="d9d88-191">The default filters for the Power BI report.</span></span> |

