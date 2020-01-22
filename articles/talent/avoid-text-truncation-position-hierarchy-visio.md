---
title: Szövegcsonkolás elkerülése a pozícióhierarchiában és exportálás a Visio szolgáltatásba
description: Ez a témakör ismerteti azoknak a problémáknak a megoldását, ahol a magánszemélyek nevei és a beosztások csonkolva jelennek meg, amikor a vevő megtekinti a beosztáshierarchiát a Dynamics 365 Talent szolgáltatásban. A szöveg csonkolt megjelenítése megnehezítheti a képernyőkép készítését vagy a hierarchia nyomtatását.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 22e8570ccb53e8a7be2c57d3f14fe8034bdb699b
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898896"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="ae80d-104">Szövegcsonkolás elkerülése a pozícióhierarchiában és exportálás a Visio szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="ae80d-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

<span data-ttu-id="ae80d-105">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="ae80d-105">**Issue**</span></span>

<span data-ttu-id="ae80d-106">Amikor a vevő megtekinti a beosztáshierarchiát a Microsoft Dynamics 365 Talent szolgáltatásban, a magánszemélyek nevei és a beosztások csonkolva jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="ae80d-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Talent, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="ae80d-107">Ez megnehezítheti a képernyőkép készítését, vagy a hierarchia nyomtatását és terjesztését.</span><span class="sxs-lookup"><span data-stu-id="ae80d-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Beosztáshierarchia](media/position-h.png)

<span data-ttu-id="ae80d-109">**Ok**</span><span class="sxs-lookup"><span data-stu-id="ae80d-109">**Cause**</span></span>

<span data-ttu-id="ae80d-110">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="ae80d-110">This behavior is by design.</span></span>

<span data-ttu-id="ae80d-111">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="ae80d-111">**Resolution**</span></span>

<span data-ttu-id="ae80d-112">Azonban a felhasználók nem egyszerűen válthat a szöveg méretét.</span><span class="sxs-lookup"><span data-stu-id="ae80d-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="ae80d-113">Azonban exportálni tudja a beosztáshierarchiát a Talent szolgáltatásból, majd importálhatja a Microsoft Visio szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="ae80d-113">However, you can export the position hierarchy out of Talent and then import it into Microsoft Visio.</span></span> <span data-ttu-id="ae80d-114">Annak ellenére, hogy a következő cikk a Microsoft Dynamics AX 2012-re vonatkozóan íródott, a folyamat a Talent szolgáltatásra is érvényes: [Beosztáshierarchia exportálása a Microsoft Visio alkalmazásba](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="ae80d-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Talent: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="ae80d-115">Kövesse ezeket a lépéseket a Visio alkalmazásba való exportáláshoz.</span><span class="sxs-lookup"><span data-stu-id="ae80d-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="ae80d-116">A Talent alkalmazásban nyissa meg a **Beosztások** listaoldalt.</span><span class="sxs-lookup"><span data-stu-id="ae80d-116">In Talent, open the **Positions** list page.</span></span>

    <span data-ttu-id="ae80d-117">Ha több információt szeretne szerepeltetni a szervezetistruktúra-diagramban, adjon mezőket a **Beosztások** listához, így ezek elérhetőek lesznek, amikor később használja a varázslót az eljárás során.</span><span class="sxs-lookup"><span data-stu-id="ae80d-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="ae80d-118">A Művelet panelen válassza a **Megnyitás Microsoft Office programban** gombot, majd az **Exportálás Excel programba** rész alatt válassza a **Beosztások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae80d-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="ae80d-119">Vagy pedig nyomja meg a Ctrl+T billentyűkombinációt.</span><span class="sxs-lookup"><span data-stu-id="ae80d-119">Alternatively, press Ctrl+T.</span></span>

    ![A Beosztások listaoldal exportálása az Excel programba](media/org-admin.png)

3. <span data-ttu-id="ae80d-121">Mentse el az exportált Excel-fájlt.</span><span class="sxs-lookup"><span data-stu-id="ae80d-121">Save the Excel file that is exported.</span></span>

    ![Exportálás Excel-fájlba párbeszédablak](media/export-excel.png)

4. <span data-ttu-id="ae80d-123">A Visio alkalmazásban válassza a **Visio - Új létrehozása** lehetőséget, majd az **Üzleti** sablonkategóriát.</span><span class="sxs-lookup"><span data-stu-id="ae80d-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Új diagram](media/new.png)

5. <span data-ttu-id="ae80d-125">Válassza a **Szervezeti diagram varázsló** lehetőséget, majd a **Létrehozás** elemet.</span><span class="sxs-lookup"><span data-stu-id="ae80d-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Szervezeti diagram varázsló párbeszédablak](media/orgchart-wizard.png)

6. <span data-ttu-id="ae80d-127">Válassza a **Fájlban vagy adatbázisban már tárolt információ** lehetőséget, majd kattintson a **Következő** gombra.</span><span class="sxs-lookup"><span data-stu-id="ae80d-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="ae80d-129">Válasszon egy **szöveget, Org Plus- (\*.txt) vagy Excel-fájlt**, majd kattintson a **Következő** gombra.</span><span class="sxs-lookup"><span data-stu-id="ae80d-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="ae80d-131">Tallózással keresse meg az exportált Excel-fájl, amely tartalmazza a beosztáshierarchiát, és nyomja meg **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="ae80d-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="ae80d-133">Állítsa a **Név** mezőt **Beosztás** értékre, a **Közvetlen felettes** mezőt **Felettes beosztás** értékre, majd nyomja meg a **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="ae80d-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="ae80d-135">Válassza ki a mezőket, amelyek minden csomóponton jelenjenek meg, és nyomja meg a **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="ae80d-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="ae80d-137">Adja hozzá a **Beosztás** oszlopot az **Adatmezők formázása** listához, majd kattintson a **Következő** gombra.</span><span class="sxs-lookup"><span data-stu-id="ae80d-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Szervezeti diagram varázsló 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="ae80d-139">A képek jelenleg nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="ae80d-139">Pictures aren't currently available.</span></span> <span data-ttu-id="ae80d-140">Emiatt a következő oldalon válassza a **Következő** gombot.</span><span class="sxs-lookup"><span data-stu-id="ae80d-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="ae80d-141">Válassza a **A varázsló automatikusan bontsa a szervezeti diagramot oldalakra** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae80d-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Szervezeti diagram varázsló 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="ae80d-143">Válassza a **Befejezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ae80d-143">Select **Finish**.</span></span>

    <span data-ttu-id="ae80d-144">Ha olyan beosztások léteznek, amelyek nem szerepelnek a szerkezetben, a rendszer megkéri, hogy ezeket is szerepeltesse a diagramban.</span><span class="sxs-lookup"><span data-stu-id="ae80d-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="ae80d-145">A Visio alkalmazásban létrehozott diagram minden vezetőt külön munkalapon jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="ae80d-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="ae80d-146">A diagramban való megjelenítésre kiválasztott mezők alapján az egyes csomópontok a megfelelő információt mutatják be, amikor a Visio-fájlt létrehozza.</span><span class="sxs-lookup"><span data-stu-id="ae80d-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Hierarchiadiagram](media/hierarchy.png)

<span data-ttu-id="ae80d-148">**További lehetőség**</span><span class="sxs-lookup"><span data-stu-id="ae80d-148">**Additional option**</span></span>

<span data-ttu-id="ae80d-149">A Talentben lehet, hogy a **Személyek** munkaterületen is meg tudja jeleníteni a hierarchiához kapcsolódó információk egy részét.</span><span class="sxs-lookup"><span data-stu-id="ae80d-149">In Talent, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>
