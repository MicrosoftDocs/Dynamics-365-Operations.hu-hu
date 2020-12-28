---
title: Dynamics 365 Commerce értékelési környezet konfigurálása
description: Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezetet a létesítést követően.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6a1ae960f0f530104af7bdea9a8fcb78b01571f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412755"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="3739d-103">Dynamics 365 Commerce értékelési környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3739d-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3739d-104">Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce értékelési környezetet a létesítést követően.</span><span class="sxs-lookup"><span data-stu-id="3739d-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="3739d-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="3739d-105">Overview</span></span>

<span data-ttu-id="3739d-106">A jelen témakörben ismertetett eljárásokat csak a Commerce értékelési környezet létesítését követően hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="3739d-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="3739d-107">A Commerce értékelési környezetének létesítésével kapcsolatos információkért lásd: [Commerce értékelési környezet kiépítése](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="3739d-107">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="3739d-108">Miután a Commerce értékelési környezet teljes körűen kiépítésre került, további létrehozás utáni konfigurálási lépéseket el kell végezni, mielőtt megkezdheti a környezet értékelését.</span><span class="sxs-lookup"><span data-stu-id="3739d-108">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="3739d-109">Ezen lépések elvégzéséhez a Microsoft Dynamics Lifecycle Services (LCS) és Dynamics 365 Commerce alkalmazásokat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="3739d-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="3739d-110">A program használatának megkezdése előtt</span><span class="sxs-lookup"><span data-stu-id="3739d-110">Before you start</span></span>

1. <span data-ttu-id="3739d-111">Jelentkezzen be az [LCS portálra](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3739d-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="3739d-112">Lépjen a projektjére.</span><span class="sxs-lookup"><span data-stu-id="3739d-112">Go to your project.</span></span>
1. <span data-ttu-id="3739d-113">Válassza a felső menü **Felhőalapú környezetek** pontját.</span><span class="sxs-lookup"><span data-stu-id="3739d-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="3739d-114">A listából válassza ki a környezetét.</span><span class="sxs-lookup"><span data-stu-id="3739d-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="3739d-115">Kattintson a jobb oldalon található környezeti információk **Bejelentkezés a környezetbe** elemére.</span><span class="sxs-lookup"><span data-stu-id="3739d-115">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="3739d-116">Megnyílik a Commerce központ modul.</span><span class="sxs-lookup"><span data-stu-id="3739d-116">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="3739d-117">Győződjön meg róla , hogy az **USRT** jogi személy van kiválasztva a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="3739d-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="3739d-118">A Commerce központ alkalmazásban történő létesítés utáni tevékenységek során győződjön meg arról, hogy a **USRT** jogi személy mindig be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="3739d-118">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="3739d-119">A pénztár beállítása</span><span class="sxs-lookup"><span data-stu-id="3739d-119">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="3739d-120">Dolgozó társítása az Ön identitásához</span><span class="sxs-lookup"><span data-stu-id="3739d-120">Associate a worker with your identity</span></span>

<span data-ttu-id="3739d-121">Ha a munkavállalót az identitásához szeretné társítani, kövesse az alábbi lépéseket a Commerce központban.</span><span class="sxs-lookup"><span data-stu-id="3739d-121">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="3739d-122">A bal oldalon található menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Alkalmazottak \> Dolgozók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-122">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="3739d-123">Keresse meg és jelölje ki a következő rekordot a listán: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="3739d-123">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="3739d-124">A Műveleti ablaktáblán válassza ki a **Commerce** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-124">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="3739d-125">Válassza a **Létező identitás társítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-125">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="3739d-126">Írja be az e-mail címét az **E-mail** mezőbe a **Keresés e-mailt használatával** lehetőségtől jobbra.</span><span class="sxs-lookup"><span data-stu-id="3739d-126">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="3739d-127">Válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-127">Select **Search**.</span></span>
1. <span data-ttu-id="3739d-128">Válassza ki a rekordot a saját nevével.</span><span class="sxs-lookup"><span data-stu-id="3739d-128">Select the record that has your name.</span></span>
1. <span data-ttu-id="3739d-129">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-129">Select **OK**.</span></span>
1. <span data-ttu-id="3739d-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-130">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="3739d-131">Felhőalapú pénztár aktiválása</span><span class="sxs-lookup"><span data-stu-id="3739d-131">Activate Cloud POS</span></span>

<span data-ttu-id="3739d-132">A Felhőalapú pénztár aktiválásához hajtsa végre az alábbi lépéseket az LCS-ben.</span><span class="sxs-lookup"><span data-stu-id="3739d-132">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="3739d-133">Válassza a felső menü **Felhőalapú környezetek** pontját.</span><span class="sxs-lookup"><span data-stu-id="3739d-133">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="3739d-134">A listából válassza ki a környezetét.</span><span class="sxs-lookup"><span data-stu-id="3739d-134">Select your environment in the list.</span></span>
1. <span data-ttu-id="3739d-135">Kattintson a jobb oldalon található környezeti információk **Bejelentkezés a felhőalapú pénztárba** elemére.</span><span class="sxs-lookup"><span data-stu-id="3739d-135">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="3739d-136">Kattintson a **Következő** gombra az **Indítás előtt** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3739d-136">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="3739d-137">Hagyja a **Kiszolgáló URL-címe** mező értékét változatlanul.</span><span class="sxs-lookup"><span data-stu-id="3739d-137">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="3739d-138">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-138">Select **Next**.</span></span>
1. <span data-ttu-id="3739d-139">Jelentkezzen be a Microsoft Azure Active Directory (Azure AD) fiókja segítségével.</span><span class="sxs-lookup"><span data-stu-id="3739d-139">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="3739d-140">Az **Üzlet neve** területen válassza a **San Francisco** lehetőséget, majd a **Következő** elemet.</span><span class="sxs-lookup"><span data-stu-id="3739d-140">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="3739d-141">A **Pénztár és eszköz** területen válassza a **SANFRAN-1** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-141">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="3739d-142">Válassza az **Aktiválás** lehetõséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-142">Select **Activate**.</span></span> <span data-ttu-id="3739d-143">Kijelentkezett, és a pénztár bejelentkezési oldalára került.</span><span class="sxs-lookup"><span data-stu-id="3739d-143">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="3739d-144">Most bejelentkezhet a Felhőalapú pénztár élménybe, a **000713** kezelői azonosítóval és az **123** jelszóval.</span><span class="sxs-lookup"><span data-stu-id="3739d-144">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="3739d-145">Webhely beállítása a Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="3739d-145">Set up your site in Commerce</span></span>

<span data-ttu-id="3739d-146">Az értékelési webhely beállításának megkezdéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3739d-146">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="3739d-147">Jelentkezzen be a webhelykészítőbe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="3739d-147">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="3739d-148">A hely beállítási mezőjének megnyitásához kattintson a **Fabrikam** helyre.</span><span class="sxs-lookup"><span data-stu-id="3739d-148">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="3739d-149">Válassza ki azt a tartományt, amelyet az e-kereskedelem inicializálásakor megadott.</span><span class="sxs-lookup"><span data-stu-id="3739d-149">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="3739d-150">Alapértelmezett csatornaként válassza ki a **Fabrikam bővített online áruház** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-150">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="3739d-151">(Győződjön meg arról, hogy a **kiterjesztett** online áruházat választja.)</span><span class="sxs-lookup"><span data-stu-id="3739d-151">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="3739d-152">Alapértelmezett nyelvnek válassza az **en-us** elemet.</span><span class="sxs-lookup"><span data-stu-id="3739d-152">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="3739d-153">Hagyja az **Útvonal** mező értékét változatlanul.</span><span class="sxs-lookup"><span data-stu-id="3739d-153">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="3739d-154">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-154">Select **OK**.</span></span> <span data-ttu-id="3739d-155">Megjelenik a webhelyen lévő oldalak listája.</span><span class="sxs-lookup"><span data-stu-id="3739d-155">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="3739d-156">Munkák engedélyezése</span><span class="sxs-lookup"><span data-stu-id="3739d-156">Enable jobs</span></span>

<span data-ttu-id="3739d-157">A feladatok engedélyezéséhez a Kereskedelemben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3739d-157">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="3739d-158">Jelentkezzen be a környezetbe (HQ).</span><span class="sxs-lookup"><span data-stu-id="3739d-158">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="3739d-159">A bal oldali menü használatával nyissa meg a **Kiskereskedelem és kereskedelem \> Lekérdezések és jelentések \> Kötegelt feladatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-159">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="3739d-160">Az eljárás további lépéseit az alábbi feladatok mindegyikére el kell végezni:</span><span class="sxs-lookup"><span data-stu-id="3739d-160">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="3739d-161">Kiskereskedelmi rendelés e-mail értesítésének feldolgozása</span><span class="sxs-lookup"><span data-stu-id="3739d-161">Process retail order email notification</span></span>
    * <span data-ttu-id="3739d-162">Termék elérhetősége</span><span class="sxs-lookup"><span data-stu-id="3739d-162">Product availability</span></span>
    * <span data-ttu-id="3739d-163">P-0001</span><span class="sxs-lookup"><span data-stu-id="3739d-163">P-0001</span></span>
    * <span data-ttu-id="3739d-164">Rendelésfeladatok szinkronizálása</span><span class="sxs-lookup"><span data-stu-id="3739d-164">Synchronize orders job</span></span>

1. <span data-ttu-id="3739d-165">A Gyorsszűrő használatával kereshet a feladatra név szerint.</span><span class="sxs-lookup"><span data-stu-id="3739d-165">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="3739d-166">Ha a feladat állapota **Végrehajtás**, hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="3739d-166">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="3739d-167">Válassza ki a rekordot.</span><span class="sxs-lookup"><span data-stu-id="3739d-167">Select the record.</span></span>
    1. <span data-ttu-id="3739d-168">A Művelet panel **Kötegelt feladat** lapján válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-168">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="3739d-169">Válassza a **Megszakítás**, majd az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="3739d-169">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="3739d-170">Lehetőség van arra is, hogy a következő feladatokhoz egy (1) percet is be lehessen állítani az ismétlődési intervallumhoz:</span><span class="sxs-lookup"><span data-stu-id="3739d-170">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="3739d-171">Kiskereskedelmi rendelés e-mail értesítésének feldolgozása feladat</span><span class="sxs-lookup"><span data-stu-id="3739d-171">Process retail order email notification job</span></span>
* <span data-ttu-id="3739d-172">P-0001 feladat</span><span class="sxs-lookup"><span data-stu-id="3739d-172">P-0001 job</span></span>
* <span data-ttu-id="3739d-173">Rendelésfeladatok szinkronizálása</span><span class="sxs-lookup"><span data-stu-id="3739d-173">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="3739d-174">Teljes adatszinkronizálás futtatása</span><span class="sxs-lookup"><span data-stu-id="3739d-174">Run full data synchronization</span></span>

<span data-ttu-id="3739d-175">Ha teljes adatszinkronizálást szeretne futtatni a Kereskedelemben, kövesse az alábbi lépéseket a Kereskedelmi központban.</span><span class="sxs-lookup"><span data-stu-id="3739d-175">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="3739d-176">A bal oldali menü használatával nyissa meg a **Modulok \> Kiskereskedelem és kereskedelem \> Központ beállítása \> Kereskedelmi ütemezés \> Csatorna-adatbázis** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-176">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="3739d-177">Válassza ki a másik csatornát, az **scXXXXXXXXX** nevűt.</span><span class="sxs-lookup"><span data-stu-id="3739d-177">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="3739d-178">A műveleti ablakban válassza ki a **Teljes adatszinkronizálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="3739d-178">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="3739d-179">Adja meg **9999** értéket az elosztási ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="3739d-179">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="3739d-180">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-180">Select **OK**.</span></span>
1. <span data-ttu-id="3739d-181">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3739d-181">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="3739d-182">A hitelkártyaadatok tesztelése tesztvásárlások végrehajtásához</span><span class="sxs-lookup"><span data-stu-id="3739d-182">Test credit card information to do test purchases</span></span>

<span data-ttu-id="3739d-183">Teszttranzakciók végrehajtásához a weboldalon használhatja a következő teszt hitelkártyaadatokat:</span><span class="sxs-lookup"><span data-stu-id="3739d-183">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="3739d-184">**Kártyaszám:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="3739d-184">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="3739d-185">**Lejárat dátuma:** 10/20</span><span class="sxs-lookup"><span data-stu-id="3739d-185">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="3739d-186">**Kártyaellenőrző kód (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="3739d-186">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3739d-187">Semmilyen körülmények között ne próbáljon ki tényleges hitelkártya-adatokat a tesztoldalon.</span><span class="sxs-lookup"><span data-stu-id="3739d-187">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3739d-188">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="3739d-188">Next steps</span></span>

<span data-ttu-id="3739d-189">A létesítési és a konfigurálási lépések befejezését követően készen áll arra, hogy elkezdje az értékelési környezet használatát.</span><span class="sxs-lookup"><span data-stu-id="3739d-189">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="3739d-190">Használja a Commerce webhelyépítő eszköz URL-címét a szerzői élményhez lépéshez.</span><span class="sxs-lookup"><span data-stu-id="3739d-190">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="3739d-191">Használja a Commerce webhelykezelő eszköz URL-címét a kiskereskedelmi ügyfél webhely élményhez lépéshez.</span><span class="sxs-lookup"><span data-stu-id="3739d-191">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="3739d-192">A Commerce értékelési környezete nem kötelező funkcióinak konfigurálásához lásd: [Commerce értékelési környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="3739d-192">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3739d-193">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3739d-193">Additional resources</span></span>

[<span data-ttu-id="3739d-194">Dynamics 365 Commerce értékelési környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="3739d-194">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="3739d-195">Dynamics 365 Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="3739d-195">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="3739d-196">Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3739d-196">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="3739d-197">BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben</span><span class="sxs-lookup"><span data-stu-id="3739d-197">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="3739d-198">Dynamics 365 Commerce értékelési környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="3739d-198">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="3739d-199">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="3739d-199">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="3739d-200">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="3739d-200">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="3739d-201">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="3739d-201">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="3739d-202">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="3739d-202">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
