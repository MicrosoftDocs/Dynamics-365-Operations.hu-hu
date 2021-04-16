---
title: Szövegcsonkolás elkerülése a pozícióhierarchián és exportálás Visio szolgáltatásba
description: Ez a cikk ismerteti azoknak a problémáknak a megoldását, ahol a magánszemélyek nevei és a beosztások csonkolva jelennek meg, amikor a vevő megtekinti a beosztáshierarchiát a Microsoft Dynamics 365 Human Resources szolgáltatásban. A szöveg csonkolt megjelenítése megnehezítheti a képernyőkép készítését vagy a hierarchia nyomtatását.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f8310def6f33b807f7f749e659432e482245d007
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803873"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="2dfe1-104">Szövegcsonkolás elkerülése a pozícióhierarchiában és exportálás a Visio szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="2dfe1-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2dfe1-105">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="2dfe1-105">**Issue**</span></span>

<span data-ttu-id="2dfe1-106">Amikor a vevő megtekinti a beosztáshierarchiát a Microsoft Dynamics 365 Human Resources szolgáltatásban, a magánszemélyek nevei és a beosztások csonkolva jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Human Resources, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="2dfe1-107">Ez megnehezítheti a képernyőkép készítését, vagy a hierarchia nyomtatását és terjesztését.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Beosztáshierarchia](media/position-h.png)

<span data-ttu-id="2dfe1-109">**Ok**</span><span class="sxs-lookup"><span data-stu-id="2dfe1-109">**Cause**</span></span>

<span data-ttu-id="2dfe1-110">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-110">This behavior is by design.</span></span>

<span data-ttu-id="2dfe1-111">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="2dfe1-111">**Resolution**</span></span>

<span data-ttu-id="2dfe1-112">Azonban a felhasználók nem egyszerűen válthat a szöveg méretét.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="2dfe1-113">Lehetőség van azonban exportálni a beosztáshierarchiát a Human Resources szolgáltatásból, majd importálni a Microsoft Visio alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-113">However, you can export the position hierarchy out of Human Resources and then import it into Microsoft Visio.</span></span> <span data-ttu-id="2dfe1-114">A következő cikk a Microsoft Dynamics AX 2012-re vonatkozóan íródott, de a folyamat a Human Resources szolgáltatásra is érvényes: [Beosztáshierarchia exportálása a Microsoft Visio alkalmazásba](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="2dfe1-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Human Resources: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="2dfe1-115">Kövesse ezeket a lépéseket a Visio alkalmazásba való exportáláshoz.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="2dfe1-116">A Human Resources modulban nyissa meg **Beosztások** lista lapját.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-116">In Human Resources, open the **Positions** list page.</span></span>

    <span data-ttu-id="2dfe1-117">Ha több információt szeretne szerepeltetni a szervezetistruktúra-diagramban, adjon mezőket a **Beosztások** listához, így ezek elérhetőek lesznek, amikor később használja a varázslót az eljárás során.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="2dfe1-118">A Művelet panelen válassza a **Megnyitás Microsoft Office programban** gombot, majd az **Exportálás Excel programba** rész alatt válassza a **Beosztások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="2dfe1-119">Vagy pedig nyomja meg a Ctrl+T billentyűkombinációt.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-119">Alternatively, press Ctrl+T.</span></span>

    ![A Beosztások listaoldal exportálása az Excel programba](media/org-admin.png)

3. <span data-ttu-id="2dfe1-121">Mentse el az exportált Excel-fájlt.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-121">Save the Excel file that is exported.</span></span>

    ![Exportálás Excel-fájlba párbeszédablak](media/export-excel.png)

4. <span data-ttu-id="2dfe1-123">A Visio alkalmazásban válassza a **Visio - Új létrehozása** lehetőséget, majd az **Üzleti** sablonkategóriát.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Új diagram](media/new.png)

5. <span data-ttu-id="2dfe1-125">Válassza a **Szervezeti diagram varázsló** lehetőséget, majd a **Létrehozás** elemet.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Szervezeti diagram varázsló párbeszédablak](media/orgchart-wizard.png)

6. <span data-ttu-id="2dfe1-127">Válassza a **Fájlban vagy adatbázisban már tárolt információ** lehetőséget, majd kattintson a **Következő** gombra.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="2dfe1-129">Válasszon egy **szöveget, Org Plus- (\*.txt) vagy Excel-fájlt**, majd kattintson a **Következő** gombra.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="2dfe1-131">Tallózással keresse meg az exportált Excel-fájl, amely tartalmazza a beosztáshierarchiát, és nyomja meg **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="2dfe1-133">Állítsa a **Név** mezőt **Beosztás** értékre, a **Közvetlen felettes** mezőt **Felettes beosztás** értékre, majd nyomja meg a **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="2dfe1-135">Válassza ki a mezőket, amelyek minden csomóponton jelenjenek meg, és nyomja meg a **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="2dfe1-137">Adja hozzá a **Beosztás** oszlopot az **Adatmezők formázása** listához, majd kattintson a **Következő** gombra.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="2dfe1-139">A képek jelenleg nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-139">Pictures aren't currently available.</span></span> <span data-ttu-id="2dfe1-140">Emiatt a következő oldalon válassza a **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="2dfe1-141">Válassza a **A varázsló automatikusan bontsa a szervezeti diagramot oldalakra** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Szervezeti diagram varázsló 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="2dfe1-143">Válassza a **Befejezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-143">Select **Finish**.</span></span>

    <span data-ttu-id="2dfe1-144">Ha olyan beosztások léteznek, amelyek nem szerepelnek a szerkezetben, a rendszer megkéri, hogy ezeket is szerepeltesse a diagramban.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="2dfe1-145">A Visio alkalmazásban létrehozott diagram minden vezetőt külön munkalapon jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="2dfe1-146">A diagramban való megjelenítésre kiválasztott mezők alapján az egyes csomópontok a megfelelő információt mutatják be, amikor a Visio-fájlt létrehozza.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Hierarchiadiagram](media/hierarchy.png)

<span data-ttu-id="2dfe1-148">**További lehetőség**</span><span class="sxs-lookup"><span data-stu-id="2dfe1-148">**Additional option**</span></span>

<span data-ttu-id="2dfe1-149">A Human Resources modulban a **Személyek** munkaterületen is meg tudja jeleníteni a hierarchiához kapcsolódó információk egy részét.</span><span class="sxs-lookup"><span data-stu-id="2dfe1-149">In Human Resources, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]