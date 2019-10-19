---
title: Felvételi útmutató létrehozása és küldése a Dynamics 365 Talent – Onboard használatával
description: Ez a témakör bemutatja, hogyan használhatja a Microsoft Dynamics 365 Talent – Onboard alkalmazást arra, hogy bevezető útmutatót hozzon létre az újonnan felvettek számára. Ez a feladat fontos első lépés a humánerőforrás-kezelési szolgáltatás (HCM) nyugdíjazásig történő felvétel stratégiájában.
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e4dbfcc3b3fd611eea36109a516a7b9361a9f654
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009854"
---
# <a name="create-and-send-an-onboarding-guide"></a><span data-ttu-id="01764-104">Felvételi útmutató létrehozása és küldése</span><span class="sxs-lookup"><span data-stu-id="01764-104">Create and send an onboarding guide</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01764-105">Microsoft Dynamics 365 Talent: Onboard lehetővé teszi, hogy a galériában elérhető vagy az Ön által létrehozott sablonokból felvételi útmutatókat hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="01764-105">Microsoft Dynamics 365 Talent: Onboard lets you create onboarding guides from templates that you created yourself, from templates that are available in a gallery, or from scratch.</span></span>

<span data-ttu-id="01764-106">Miután létrehozta a felvételi útmutatót, elküldheti azt egy újonnan felvett munkatársnak.</span><span class="sxs-lookup"><span data-stu-id="01764-106">After you've created an onboarding guide, you can send it to a new hire.</span></span> <span data-ttu-id="01764-107">Azt is megteheti, hogy több újonnan felvett munkatársnak küldi el, akiket egy Microsoft Excel fájlban határoz meg, amit az Onboard alkalmazásból tölthet le.</span><span class="sxs-lookup"><span data-stu-id="01764-107">Alternatively, you can send it to multiple new hires that you specify in a Microsoft Excel file that you download from the Onboard app.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a><span data-ttu-id="01764-108">Felvételi útmutató létrehozása sablonból és küldés egyetlen újonnan felvett munkatársnak</span><span class="sxs-lookup"><span data-stu-id="01764-108">Create an onboarding guide from a template and send it to a single new hire</span></span>

1. <span data-ttu-id="01764-109">A bal oldali menüben válassza a **Sablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-109">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="01764-110">A **Saját sablonok**területen válassza ki azt a sablont, amelyet be szeretne állítani az újonnan felvett munkatársnak a felvételi útmutatóként.</span><span class="sxs-lookup"><span data-stu-id="01764-110">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hire.</span></span>
3. <span data-ttu-id="01764-111">Igény szerint szerkessze a sablont.</span><span class="sxs-lookup"><span data-stu-id="01764-111">Edit the template as you desire.</span></span> <span data-ttu-id="01764-112">Ne felejtse el rendszeresen elmenteni a munkát.</span><span class="sxs-lookup"><span data-stu-id="01764-112">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="01764-113">Ha befejezte a sablon szerkesztését, válassza az **Útmutatólétrehozása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="01764-113">When you've finished editing the template, select **Create guide**.</span></span>

    <span data-ttu-id="01764-114">[![A felvételi útmutató létrehozása egy sablonból](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span><span class="sxs-lookup"><span data-stu-id="01764-114">[![Creating an onboarding guide from a template](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)</span></span>

5. <span data-ttu-id="01764-115">Az **Új sablon létrehozás ablakban** a **Kit vesz fel?** részben adja meg az új munkatárs nevét vagy e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="01764-115">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="01764-116">Ha az újonnan felvett munkatárs még nincs a rendszerben, válassza a **Hozzáadás most** lehetőséget, majd adja meg az alkalmazott adatait.</span><span class="sxs-lookup"><span data-stu-id="01764-116">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="01764-117">Információ megadása a felvételi útmutatóhoz</span><span class="sxs-lookup"><span data-stu-id="01764-117">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. <span data-ttu-id="01764-118">A **Mi a kezdés dátuma?** alatt válassza ki a kezdés dátumát.</span><span class="sxs-lookup"><span data-stu-id="01764-118">Under **When do they start**, select a start date.</span></span>
7. <span data-ttu-id="01764-119">Ha a felvételi útmutatót automatikusan kell kiküldeni az új munkatársnak egy megadott napon, győződjön meg arról, hogy az **Automatikus küldési dátum ütemezése** beállítás be van kapcsolva, majd válassza ki az automatikus küldés dátumát.</span><span class="sxs-lookup"><span data-stu-id="01764-119">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="01764-120">Ha azonnal el szeretné küldeni az útmutatót, kapcsolja ki a **Automatikus küldési dátum ütemezése** beállítást.</span><span class="sxs-lookup"><span data-stu-id="01764-120">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
8. <span data-ttu-id="01764-121">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-121">Select **Done**.</span></span>
9. <span data-ttu-id="01764-122">Ha befejezte a felvételi útmutató szerkesztését, válassza a jobb felső sarokban látható **Küldés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="01764-122">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="01764-123">Majd tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="01764-123">Then follow one of these steps:</span></span>

    - <span data-ttu-id="01764-124">**A hivatkozásmásolása** hivatkozásra kattintva majd a **Másolás** kiválasztásával elküldheti a felvételi útmutató hivatkozását az új munkatársnak.</span><span class="sxs-lookup"><span data-stu-id="01764-124">To send the new hire a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="01764-125">Ha azt szeretné az e-mail-címet testreszabni a felvételi útmutatóban, válassza a **Végezze el az e-mail testreszabását küldés előtt**, majd a **Tovább** lehetőséget, szabja testre az e-mail-címet, majd válassza a **Küldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-125">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="01764-126">Ha azt szeretné, hogy az e-mail küldése a Testreszabás nélkül történjen, válassza a **Tovább**, majd a **Küldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-126">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a><span data-ttu-id="01764-127">Felvételi útmutató létrehozása sablonból és küldés több újonnan felvett munkatársnak</span><span class="sxs-lookup"><span data-stu-id="01764-127">Create an onboarding guide from a template and send it to multiple new hires</span></span>

<span data-ttu-id="01764-128">Az Onboard lehetővé teszi, hogy egyszerre több újonnan felvett munkatársnak küldjön felvételi útmutatót.</span><span class="sxs-lookup"><span data-stu-id="01764-128">Onboard lets you send an onboarding guide to multiple new hires at the same time.</span></span>

1. <span data-ttu-id="01764-129">A bal oldali menüben válassza a **Sablonok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-129">On the left menu, select **Templates**.</span></span>
2. <span data-ttu-id="01764-130">A **Saját sablonok**területen válassza ki azt a sablont, amelyet be szeretne állítani az újonnan felvett munkatársaknak a felvételi útmutatóként.</span><span class="sxs-lookup"><span data-stu-id="01764-130">Under **My templates**, select the template that you want to set up as an onboarding guide for the new hires.</span></span>
3. <span data-ttu-id="01764-131">Igény szerint szerkessze a sablont.</span><span class="sxs-lookup"><span data-stu-id="01764-131">Edit the template as you desire.</span></span> <span data-ttu-id="01764-132">Ne felejtse el rendszeresen elmenteni a munkát.</span><span class="sxs-lookup"><span data-stu-id="01764-132">Be sure to save your work as you go.</span></span>
4. <span data-ttu-id="01764-133">Ha befejezte a sablon szerkesztését, válassza az **Útmutatólétrehozása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="01764-133">When you've finished editing the template, select **Create guide**.</span></span>
5. <span data-ttu-id="01764-134">Az **Útmutató létrehozása** ablakban válassza ki az **Egyszerre több embert kell felvennie?** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-134">In the **Create a guide** window, select **Need to onboard multiple people at once**.</span></span>

    <span data-ttu-id="01764-135">[![A fedélzeti útmutató létrehozása több új munkatársnak](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span><span class="sxs-lookup"><span data-stu-id="01764-135">[![Creating an onboarding guide for multiple new hires](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)</span></span>

6. <span data-ttu-id="01764-136">Válassza az **új felvételi sablon** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-136">Select **new hire template**.</span></span>
7. <span data-ttu-id="01764-137">Az. xlsx fájl letöltését követően válassza a **Megnyitás**parancsot, adja meg az alkalmazottak adatait az Excel-munkafüzetben, majd mentse a munkafüzetet.</span><span class="sxs-lookup"><span data-stu-id="01764-137">After the .xlsx file is downloaded, select **Open**, enter the employees' information in the Excel workbook, and save the workbook.</span></span>

    <span data-ttu-id="01764-138">[![Az Excel-sablon letöltése a fedélzeti útmutató több új munkatársnak történő küldéséhez](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="01764-138">[![Downloading the Excel template for sending the onboarding guide to multiple new hires](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="01764-139">A munkafüzet szerkesztéséhez ki kell választania a **Szerkesztés engedélyezése** lehetőséget az Excelben.</span><span class="sxs-lookup"><span data-stu-id="01764-139">Before you can edit the workbook, you must select **Enable editing** in Excel.</span></span>
    > 
    > <span data-ttu-id="01764-140">[![Szerkesztés engedélyezése](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span><span class="sxs-lookup"><span data-stu-id="01764-140">[![Enabling editing](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)</span></span>

8. <span data-ttu-id="01764-141">Húzza az Excel-munkafüzetet a **Több útmutatólétrehozása** ablak kijelölt területére, vagy kattintson a területen bárhova, és keresse meg a fájlt a számítógépen.</span><span class="sxs-lookup"><span data-stu-id="01764-141">Drag the Excel workbook to the designated area in the **Create multiple guides** window, or click anywhere in that area to browse for the file on your computer.</span></span>

    <span data-ttu-id="01764-142">[![A szerkesztett munkafüzet húzása](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span><span class="sxs-lookup"><span data-stu-id="01764-142">[![Dragging the edited workbook](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)</span></span>

9. <span data-ttu-id="01764-143">Ha befejezte a felvételi útmutató szerkesztését, válassza a jobb felső sarokban látható **Küldés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="01764-143">When you've finished editing the onboarding guide, select **Send** in the upper-right corner.</span></span> <span data-ttu-id="01764-144">Majd tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="01764-144">Then follow one of these steps:</span></span>

    - <span data-ttu-id="01764-145">**A hivatkozás másolása** hivatkozásra kattintva majd a **Másolás** kiválasztásával elküldheti a felvételi útmutató hivatkozását az új munkatársaknak.</span><span class="sxs-lookup"><span data-stu-id="01764-145">To send the new hires a link to the onboarding guide, select **copy a link**, and then select **Copy**.</span></span>
    - <span data-ttu-id="01764-146">Ha azt szeretné az e-mail-címet testreszabni a felvételi útmutatóban, válassza a **Végezze el az e-mail testreszabását küldés előtt**, majd a **Tovább** lehetőséget, szabja testre az e-mail-címet, majd válassza a **Küldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-146">To customize the email for the onboarding guide before you send it, select **Customize the email before sending**, select **Next**, customize the email as you desire, and then select **Send**.</span></span>
    - <span data-ttu-id="01764-147">Ha azt szeretné, hogy az e-mail küldése a Testreszabás nélkül történjen, válassza a **Tovább**, majd a **Küldés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-147">To send the email without customizing it, select **Next**, and then select **Send**.</span></span>

## <a name="create-a-guide-without-using-a-template"></a><span data-ttu-id="01764-148">Útmutató létrehozása sablon használata nélkül</span><span class="sxs-lookup"><span data-stu-id="01764-148">Create a guide without using a template</span></span>

<span data-ttu-id="01764-149">Nem feltétlenül kell sablonból létrehoznia egy útmutatót.</span><span class="sxs-lookup"><span data-stu-id="01764-149">You don't always have to create a guide from a template.</span></span> <span data-ttu-id="01764-150">Ha szeretné, létrehozhat az elejéről is egy útmutatót.</span><span class="sxs-lookup"><span data-stu-id="01764-150">If you prefer, you can create a guide from scratch instead.</span></span>

1. <span data-ttu-id="01764-151">A bal oldali menüben válassza ki az **Útmutatók**, majd válassza a **Hozzáadás** gombot (a pluszjelet \[**+**\]).</span><span class="sxs-lookup"><span data-stu-id="01764-151">On the left menu, select **Guides**, and then select the **Add** button (the plus sign \[**+**\]).</span></span>
2. <span data-ttu-id="01764-152">Az **Új sablon létrehozás ablakban** a **Kit vesz fel?** részben adja meg az új munkatárs nevét vagy e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="01764-152">In the **Create a guide** window, under **Who are you onboarding**, enter the new hire's name or email address.</span></span> <span data-ttu-id="01764-153">Ha az újonnan felvett munkatárs még nincs a rendszerben, válassza a **Hozzáadás most** lehetőséget, majd adja meg az alkalmazott adatait.</span><span class="sxs-lookup"><span data-stu-id="01764-153">If the new hire isn't in the system yet, select **Add now**, and enter the employee's information.</span></span>

    ![[<span data-ttu-id="01764-154">Információ megadása a felvételi útmutatóhoz</span><span class="sxs-lookup"><span data-stu-id="01764-154">Entering information for the onboarding guide</span></span>](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. <span data-ttu-id="01764-155">A **Mi a kezdés dátuma?** alatt válassza ki a kezdés dátumát.</span><span class="sxs-lookup"><span data-stu-id="01764-155">Under **When do they start**, select a start date.</span></span>
4. <span data-ttu-id="01764-156">Ha a felvételi útmutatót automatikusan kell kiküldeni az új munkatársnak egy megadott napon, győződjön meg arról, hogy az **Automatikus küldési dátum ütemezése** beállítás be van kapcsolva, majd válassza ki az automatikus küldés dátumát.</span><span class="sxs-lookup"><span data-stu-id="01764-156">If the onboarding guide should be sent automatically to the new hire on a specific date, make sure that the **Schedule an automatic send date** option is turned on, and then select the automatic send date.</span></span> <span data-ttu-id="01764-157">Ha azonnal el szeretné küldeni az útmutatót, kapcsolja ki a **Automatikus küldési dátum ütemezése** beállítást.</span><span class="sxs-lookup"><span data-stu-id="01764-157">To send the guide immediately, turn off the **Schedule an automatic send date** option.</span></span>
5. <span data-ttu-id="01764-158">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-158">Select **Done**.</span></span>

## <a name="save-a-guide-as-a-template"></a><span data-ttu-id="01764-159">Az útmutató mentése sablonként</span><span class="sxs-lookup"><span data-stu-id="01764-159">Save a guide as a template</span></span>

<span data-ttu-id="01764-160">A felvételi útmutató sablonként is menthető.</span><span class="sxs-lookup"><span data-stu-id="01764-160">You can save an onboarding guide as a template.</span></span> <span data-ttu-id="01764-161">Ily módon időt takaríthat meg, amikor később további felvételi útmutatókat kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="01764-161">In this way, you can save time when you must create more onboarding guides later.</span></span>

1. <span data-ttu-id="01764-162">A bal oldali menüben válassza a **Guides** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01764-162">On the left menu, select **Guides**.</span></span>
2. <span data-ttu-id="01764-163">Válassza ki a **Továbbiak** gombot (három pont \[**…**\]) azon útmutatóhoz, amelyből sablont szeretne létrehozni, majd válassza a **Mentés sablonként** parancsot.</span><span class="sxs-lookup"><span data-stu-id="01764-163">Select the **More** button (the ellipsis \[**...**\]) for the guide that you want to create a template from, and then select **Save as template**.</span></span>

    ![[<span data-ttu-id="01764-164">Egy felvétei útmutató mentése sablonként</span><span class="sxs-lookup"><span data-stu-id="01764-164">Saving an onboarding guide as a template</span></span>](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. <span data-ttu-id="01764-165">Írja be az új sablon nevét a **Mentés új sablonként** ablakba, majd válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="01764-165">In the **Save as a new template** window, enter a name for your new template, and then select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01764-166">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="01764-166">Next steps</span></span>

- [<span data-ttu-id="01764-167">Bevezetési útmutatók és sablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="01764-167">Edit onboarding guides and templates</span></span>](./onboard-edit-guides-templates.md)
- [<span data-ttu-id="01764-168">Osszon meg tartalmakat más közreműködőkkel</span><span class="sxs-lookup"><span data-stu-id="01764-168">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="01764-169">A feladatok és az alkalmazottak és bevezetési állapotának megtekintése</span><span class="sxs-lookup"><span data-stu-id="01764-169">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="01764-170">Toborzócsoportok létrehozása az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="01764-170">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="01764-171">Lásd még</span><span class="sxs-lookup"><span data-stu-id="01764-171">See also</span></span>

- [<span data-ttu-id="01764-172">Próbálja ki vagy vásárolja meg az Onboard alkalmazást</span><span class="sxs-lookup"><span data-stu-id="01764-172">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="01764-173">Újdonságok</span><span class="sxs-lookup"><span data-stu-id="01764-173">What's new</span></span>](./whats-new.md)
- [<span data-ttu-id="01764-174">Programverzióra vonatkozó megjegyzések</span><span class="sxs-lookup"><span data-stu-id="01764-174">Release notes</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="01764-175">Támogatás kérése</span><span class="sxs-lookup"><span data-stu-id="01764-175">Get support</span></span>](./talent-support.md)
