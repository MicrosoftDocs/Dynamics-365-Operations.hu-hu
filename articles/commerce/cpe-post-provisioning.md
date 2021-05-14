---
title: Dynamics 365 Commerce értékelési környezet konfigurálása
description: Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezetet a létesítést követően.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b291a6515c6a3ae7382ea2ad8024ca036489de19
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2021
ms.locfileid: "5937038"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="f71ef-103">Dynamics 365 Commerce értékelési környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f71ef-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f71ef-104">Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezetet a létesítést követően.</span><span class="sxs-lookup"><span data-stu-id="f71ef-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="f71ef-105">A jelen témakörben ismertetett eljárásokat csak a Commerce értékelési környezet létesítését követően hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="f71ef-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="f71ef-106">A Commerce értékelési környezetének létesítésével kapcsolatos információkért lásd: [Commerce értékelési környezet kiépítése](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="f71ef-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="f71ef-107">Miután a Commerce értékelési környezet teljes körűen kiépítésre került, további létrehozás utáni konfigurálási lépéseket el kell végezni, mielőtt megkezdheti a környezet értékelését.</span><span class="sxs-lookup"><span data-stu-id="f71ef-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="f71ef-108">Ezen lépések elvégzéséhez a Microsoft Dynamics Lifecycle Services (LCS) és Dynamics 365 Commerce alkalmazásokat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="f71ef-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f71ef-109">A program használatának megkezdése előtt</span><span class="sxs-lookup"><span data-stu-id="f71ef-109">Before you start</span></span>

1. <span data-ttu-id="f71ef-110">Jelentkezzen be az [LCS portálra](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="f71ef-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="f71ef-111">Lépjen a projektjére.</span><span class="sxs-lookup"><span data-stu-id="f71ef-111">Go to your project.</span></span>
1. <span data-ttu-id="f71ef-112">Válassza a felső menü **Felhőalapú környezetek** pontját.</span><span class="sxs-lookup"><span data-stu-id="f71ef-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="f71ef-113">A listából válassza ki a környezetét.</span><span class="sxs-lookup"><span data-stu-id="f71ef-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="f71ef-114">Kattintson a jobb oldalon található környezeti információk **Bejelentkezés a környezetbe** elemére.</span><span class="sxs-lookup"><span data-stu-id="f71ef-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="f71ef-115">Megnyílik a Commerce központ modul.</span><span class="sxs-lookup"><span data-stu-id="f71ef-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="f71ef-116">Győződjön meg róla , hogy az **USRT** jogi személy van kiválasztva a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="f71ef-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="f71ef-117">A Commerce központ alkalmazásban történő létesítés utáni tevékenységek során győződjön meg arról, hogy a **USRT** jogi személy mindig be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="f71ef-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="f71ef-118">A pénztár beállítása</span><span class="sxs-lookup"><span data-stu-id="f71ef-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="f71ef-119">Dolgozó társítása az Ön identitásához</span><span class="sxs-lookup"><span data-stu-id="f71ef-119">Associate a worker with your identity</span></span>

<span data-ttu-id="f71ef-120">Ha a munkavállalót az identitásához szeretné társítani, kövesse az alábbi lépéseket a Commerce központban.</span><span class="sxs-lookup"><span data-stu-id="f71ef-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="f71ef-121">A bal oldalon található menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Alkalmazottak \> Dolgozók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="f71ef-122">Keresse meg és jelölje ki a következő rekordot a listán: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="f71ef-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="f71ef-123">A Műveleti ablaktáblán válassza ki a **Commerce** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="f71ef-124">Válassza a **Létező identitás társítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="f71ef-125">Írja be az e-mail címét az **E-mail** mezőbe a **Keresés e-mailt használatával** lehetőségtől jobbra.</span><span class="sxs-lookup"><span data-stu-id="f71ef-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="f71ef-126">Válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-126">Select **Search**.</span></span>
1. <span data-ttu-id="f71ef-127">Válassza ki a rekordot a saját nevével.</span><span class="sxs-lookup"><span data-stu-id="f71ef-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="f71ef-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-128">Select **OK**.</span></span>
1. <span data-ttu-id="f71ef-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="f71ef-130">Felhőalapú pénztár aktiválása</span><span class="sxs-lookup"><span data-stu-id="f71ef-130">Activate Cloud POS</span></span>

<span data-ttu-id="f71ef-131">A Felhőalapú pénztár aktiválásához hajtsa végre az alábbi lépéseket az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="f71ef-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="f71ef-132">Válassza a felső menü **Felhőalapú környezetek** pontját.</span><span class="sxs-lookup"><span data-stu-id="f71ef-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="f71ef-133">A listából válassza ki a környezetét.</span><span class="sxs-lookup"><span data-stu-id="f71ef-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="f71ef-134">Kattintson a jobb oldalon található környezeti információk **Bejelentkezés a felhőalapú pénztárba** elemére.</span><span class="sxs-lookup"><span data-stu-id="f71ef-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="f71ef-135">Kattintson a **Következő** gombra az **Indítás előtt** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f71ef-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="f71ef-136">Hagyja a **Kiszolgáló URL-címe** mező értékét változatlanul.</span><span class="sxs-lookup"><span data-stu-id="f71ef-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="f71ef-137">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-137">Select **Next**.</span></span>
1. <span data-ttu-id="f71ef-138">Jelentkezzen be a Microsoft Azure Active Directory (Azure AD) fiókja segítségével.</span><span class="sxs-lookup"><span data-stu-id="f71ef-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="f71ef-139">Az **Üzlet neve** területen válassza a **San Francisco** lehetőséget, majd a **Következő** elemet.</span><span class="sxs-lookup"><span data-stu-id="f71ef-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="f71ef-140">A **Pénztár és eszköz** területen válassza a **SANFRAN-1** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="f71ef-141">Válassza az **Aktiválás** lehetõséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-141">Select **Activate**.</span></span> <span data-ttu-id="f71ef-142">Kijelentkezett, és a pénztár bejelentkezési oldalára került.</span><span class="sxs-lookup"><span data-stu-id="f71ef-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="f71ef-143">Most bejelentkezhet a Felhőalapú pénztár élménybe, a **000713** kezelői azonosítóval és az **123** jelszóval.</span><span class="sxs-lookup"><span data-stu-id="f71ef-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="f71ef-144">Webhely beállítása a Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f71ef-144">Set up your site in Commerce</span></span>

<span data-ttu-id="f71ef-145">Az értékelési webhely beállításának megkezdéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f71ef-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f71ef-146">Jelentkezzen be a webhelykészítőbe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="f71ef-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="f71ef-147">A hely beállítási mezőjének megnyitásához kattintson a **Fabrikam** helyre.</span><span class="sxs-lookup"><span data-stu-id="f71ef-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="f71ef-148">Válassza ki azt a tartományt, amelyet az e-kereskedelem inicializálásakor megadott.</span><span class="sxs-lookup"><span data-stu-id="f71ef-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="f71ef-149">Alapértelmezett csatornaként válassza ki a **Fabrikam bővített online áruház** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="f71ef-150">(Győződjön meg arról, hogy a **kiterjesztett** online áruházat választja.)</span><span class="sxs-lookup"><span data-stu-id="f71ef-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="f71ef-151">Alapértelmezett nyelvnek válassza az **en-us** elemet.</span><span class="sxs-lookup"><span data-stu-id="f71ef-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="f71ef-152">Hagyja az **Útvonal** mező értékét változatlanul.</span><span class="sxs-lookup"><span data-stu-id="f71ef-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="f71ef-153">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-153">Select **OK**.</span></span> <span data-ttu-id="f71ef-154">Megjelenik a webhelyen lévő oldalak listája.</span><span class="sxs-lookup"><span data-stu-id="f71ef-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="f71ef-155">Munkák engedélyezése</span><span class="sxs-lookup"><span data-stu-id="f71ef-155">Enable jobs</span></span>

<span data-ttu-id="f71ef-156">A feladatok engedélyezéséhez a Kereskedelemben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f71ef-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f71ef-157">Jelentkezzen be a környezetbe (HQ).</span><span class="sxs-lookup"><span data-stu-id="f71ef-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="f71ef-158">A bal oldali menü használatával nyissa meg a **Kiskereskedelem és kereskedelem \> Lekérdezések és jelentések \> Kötegelt feladatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="f71ef-159">Az eljárás további lépéseit az alábbi feladatok mindegyikére el kell végezni:</span><span class="sxs-lookup"><span data-stu-id="f71ef-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="f71ef-160">Kiskereskedelmi rendelés e-mail értesítésének feldolgozása</span><span class="sxs-lookup"><span data-stu-id="f71ef-160">Process retail order email notification</span></span>
    * <span data-ttu-id="f71ef-161">Termék elérhetősége</span><span class="sxs-lookup"><span data-stu-id="f71ef-161">Product availability</span></span>
    * <span data-ttu-id="f71ef-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="f71ef-162">P-0001</span></span>
    * <span data-ttu-id="f71ef-163">Rendelésfeladatok szinkronizálása</span><span class="sxs-lookup"><span data-stu-id="f71ef-163">Synchronize orders job</span></span>

1. <span data-ttu-id="f71ef-164">A Gyorsszűrő használatával kereshet a feladatra név szerint.</span><span class="sxs-lookup"><span data-stu-id="f71ef-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="f71ef-165">Ha a feladat állapota **Végrehajtás**, hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f71ef-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="f71ef-166">Válassza ki a rekordot.</span><span class="sxs-lookup"><span data-stu-id="f71ef-166">Select the record.</span></span>
    1. <span data-ttu-id="f71ef-167">A Művelet panel **Kötegelt feladat** lapján válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="f71ef-168">Válassza a **Megszakítás**, majd az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="f71ef-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="f71ef-169">Lehetőség van arra is, hogy a következő feladatokhoz egy (1) percet is be lehessen állítani az ismétlődési intervallumhoz:</span><span class="sxs-lookup"><span data-stu-id="f71ef-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="f71ef-170">Kiskereskedelmi rendelés e-mail értesítésének feldolgozása feladat</span><span class="sxs-lookup"><span data-stu-id="f71ef-170">Process retail order email notification job</span></span>
* <span data-ttu-id="f71ef-171">P-0001 feladat</span><span class="sxs-lookup"><span data-stu-id="f71ef-171">P-0001 job</span></span>
* <span data-ttu-id="f71ef-172">Rendelésfeladatok szinkronizálása</span><span class="sxs-lookup"><span data-stu-id="f71ef-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="f71ef-173">Teljes adatszinkronizálás futtatása</span><span class="sxs-lookup"><span data-stu-id="f71ef-173">Run full data synchronization</span></span>

<span data-ttu-id="f71ef-174">Ha teljes adatszinkronizálást szeretne futtatni a Kereskedelemben, kövesse az alábbi lépéseket a Kereskedelmi központban.</span><span class="sxs-lookup"><span data-stu-id="f71ef-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="f71ef-175">A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítása \> Kereskedelmi ütemezés \> Csatorna-adatbázis** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="f71ef-176">Válassza ki a másik csatornát, az **scXXXXXXXXX** nevűt.</span><span class="sxs-lookup"><span data-stu-id="f71ef-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="f71ef-177">A műveleti ablakban válassza ki a **Teljes adatszinkronizálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="f71ef-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="f71ef-178">Adja meg **9999** értéket az elosztási ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="f71ef-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="f71ef-179">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-179">Select **OK**.</span></span>
1. <span data-ttu-id="f71ef-180">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f71ef-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="f71ef-181">A hitelkártyaadatok tesztelése tesztvásárlások végrehajtásához</span><span class="sxs-lookup"><span data-stu-id="f71ef-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="f71ef-182">Teszttranzakciók végrehajtásához a weboldalon használhatja a következő teszt hitelkártyaadatokat:</span><span class="sxs-lookup"><span data-stu-id="f71ef-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="f71ef-183">**Kártyaszám:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="f71ef-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="f71ef-184">**Lejárat dátuma:** 10/20</span><span class="sxs-lookup"><span data-stu-id="f71ef-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="f71ef-185">**Kártyaellenőrző kód (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="f71ef-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f71ef-186">Semmilyen körülmények között ne próbáljon ki tényleges hitelkártya-adatokat a tesztoldalon.</span><span class="sxs-lookup"><span data-stu-id="f71ef-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f71ef-187">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="f71ef-187">Next steps</span></span>

<span data-ttu-id="f71ef-188">A létesítési és a konfigurálási lépések befejezését követően készen áll arra, hogy elkezdje az értékelési környezet használatát.</span><span class="sxs-lookup"><span data-stu-id="f71ef-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="f71ef-189">Használja a Commerce webhelyépítő eszköz URL-címét a szerzői élményhez lépéshez.</span><span class="sxs-lookup"><span data-stu-id="f71ef-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="f71ef-190">Használja a Commerce webhelykezelő eszköz URL-címét a kiskereskedelmi ügyfél webhely élményhez lépéshez.</span><span class="sxs-lookup"><span data-stu-id="f71ef-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="f71ef-191">A Commerce értékelési környezete nem kötelező funkcióinak konfigurálásához lásd: [Commerce értékelési környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="f71ef-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f71ef-192">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f71ef-192">Additional resources</span></span>

[<span data-ttu-id="f71ef-193">Dynamics 365 Commerce értékelési környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="f71ef-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="f71ef-194">Dynamics 365 Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="f71ef-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="f71ef-195">Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="f71ef-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="f71ef-196">BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben</span><span class="sxs-lookup"><span data-stu-id="f71ef-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="f71ef-197">Dynamics 365 Commerce értékelési környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="f71ef-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="f71ef-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="f71ef-198">Microsoft Lifecycle Services (LCS)</span></span>](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="f71ef-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="f71ef-199">Retail Cloud Scale Unit (RCSU)</span></span>](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="f71ef-200">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="f71ef-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="f71ef-201">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="f71ef-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]