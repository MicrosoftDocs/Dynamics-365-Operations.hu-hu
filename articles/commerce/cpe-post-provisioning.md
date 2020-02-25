---
title: Egy Dynamics 365 Commerce előzetes verziós környezet konfigurálása
description: Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce előzetes környezetet a létesítést követően.
author: psimolin
manager: annbe
ms.date: 12/10/2019
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
ms.openlocfilehash: 12d3a86698e9250f5d1645de51e0749c8d929f75
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024706"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="0c0df-103">Egy Dynamics 365 Commerce előzetes verziós környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0c0df-103">Configure a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0c0df-104">Ez a témakör bemutatja, hogyan lehet konfigurálni egy Microsoft Dynamics 365 Commerce előzetes környezetet a létesítést követően.</span><span class="sxs-lookup"><span data-stu-id="0c0df-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="0c0df-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="0c0df-105">Overview</span></span>

<span data-ttu-id="0c0df-106">A jelen témakörben ismertetett eljárásokat csak a Commerce előnézet környezet létesítését követően hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="0c0df-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="0c0df-107">A Commerce előzetes környezetének létesítésével kapcsolatos információkért lásd: [Commerce előzetes verziós környezet kiépítése](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="0c0df-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="0c0df-108">Miután a Commerce előzetes környezet teljes körűen kiépítésre került, további létrehozás utáni konfigurálási lépéseket el kell végezni, mielőtt megkezdheti a környezet értékelését.</span><span class="sxs-lookup"><span data-stu-id="0c0df-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="0c0df-109">Ezen lépések elvégzéséhez a Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce és Dynamics 365 Retail alkalmazásokat kell használnia.</span><span class="sxs-lookup"><span data-stu-id="0c0df-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce, and Dynamics 365 Retail.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="0c0df-110">A program használatának megkezdése előtt</span><span class="sxs-lookup"><span data-stu-id="0c0df-110">Before you start</span></span>

1. <span data-ttu-id="0c0df-111">Jelentkezzen be az [LCS portálra](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="0c0df-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="0c0df-112">Lépjen a projektjére.</span><span class="sxs-lookup"><span data-stu-id="0c0df-112">Go to your project.</span></span>
1. <span data-ttu-id="0c0df-113">Válassza a felső menü **Felhőalapú környezetek**pontját.</span><span class="sxs-lookup"><span data-stu-id="0c0df-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="0c0df-114">A listából válassza ki a környezetét.</span><span class="sxs-lookup"><span data-stu-id="0c0df-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="0c0df-115">Kattintson a jobb oldalon található környezeti információk **Minden részlet** elemére.</span><span class="sxs-lookup"><span data-stu-id="0c0df-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="0c0df-116">Válassza a **Bejelentkezés** lehetőséget a menü megnyitásához , majd válassza a **Bejelentkezés a környezetbe** parancsot.</span><span class="sxs-lookup"><span data-stu-id="0c0df-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="0c0df-117">Győződjön meg róla , hogy az **USRT** jogi személy van kiválasztva a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="0c0df-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="0c0df-118">A pénztár beállítása az LCS-ben</span><span class="sxs-lookup"><span data-stu-id="0c0df-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="0c0df-119">Dolgozó társítása az Ön identitásához</span><span class="sxs-lookup"><span data-stu-id="0c0df-119">Associate a worker with your identity</span></span>

<span data-ttu-id="0c0df-120">Ha a munkavállalót az LCS-ben lévő identitásához szeretné társítani, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c0df-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="0c0df-121">A bal oldalon található menü használatával nyissa meg a **Modulok \> Kiskereskedelem \> Alkalmazottak \> Dolgozók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-121">Use the menu on the left to go to **Modules \> Retail \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="0c0df-122">Keresse meg és jelölje ki a következő rekordot a listán: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="0c0df-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="0c0df-123">A Műveleti ablaktáblán kattintson a **Kiskereskedelem** elemre.</span><span class="sxs-lookup"><span data-stu-id="0c0df-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="0c0df-124">Válassza a **Létező identitás társítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="0c0df-125">Írja be az e-mail címét az **E-mail** mezőbe a **Keresés e-mailt használatával** lehetőségtől jobbra.</span><span class="sxs-lookup"><span data-stu-id="0c0df-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="0c0df-126">Válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-126">Select **Search**.</span></span>
1. <span data-ttu-id="0c0df-127">Válassza ki a rekordot a saját nevével.</span><span class="sxs-lookup"><span data-stu-id="0c0df-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="0c0df-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-128">Select **OK**.</span></span>
1. <span data-ttu-id="0c0df-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="0c0df-130">Felhőalapú pénztár aktiválása</span><span class="sxs-lookup"><span data-stu-id="0c0df-130">Activate Cloud POS</span></span>

<span data-ttu-id="0c0df-131">Az LCS-ben található Felhőalapú pénztár aktiválásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c0df-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="0c0df-132">Válassza a felső menü **Felhőalapú környezetek**pontját.</span><span class="sxs-lookup"><span data-stu-id="0c0df-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="0c0df-133">A listából válassza ki a környezetét.</span><span class="sxs-lookup"><span data-stu-id="0c0df-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="0c0df-134">Kattintson a jobb oldalon található környezeti információk **Minden részlet** elemére.</span><span class="sxs-lookup"><span data-stu-id="0c0df-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="0c0df-135">Válassza a **Bejelentkezés** lehetőséget a menü megnyitásához, majd válassza a **Bejelentkezés a pénztári felhőbe** lehetőséget a pénztár (POS) megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0c0df-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="0c0df-136">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-136">Select **Next**.</span></span>
1. <span data-ttu-id="0c0df-137">Jelentkezzen be a Microsoft Azure Active Directory (Azure AD) fiókja segítségével.</span><span class="sxs-lookup"><span data-stu-id="0c0df-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="0c0df-138">Az **Üzlet neve** területen válassza a **SanFrancisco** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="0c0df-139">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-139">Select **Next**.</span></span>
1. <span data-ttu-id="0c0df-140">A **Pénztár és eszköz** területen válassza a **SANFRAN-1** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="0c0df-141">Válassza az **Aktiválás** lehetõséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-141">Select **Activate**.</span></span> <span data-ttu-id="0c0df-142">Kijelentkezett, és a pénztár bejelentkezési oldalára került.</span><span class="sxs-lookup"><span data-stu-id="0c0df-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="0c0df-143">Most bejelentkezhet a Felhőalapú pénztár élménybe, a **000713** kezelői azonosítóval és az **123** jelszóval.</span><span class="sxs-lookup"><span data-stu-id="0c0df-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="0c0df-144">Webhely beállítása a Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="0c0df-144">Set up your site in Commerce</span></span>

<span data-ttu-id="0c0df-145">Az előzetes webhely beállításának megkezdéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c0df-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="0c0df-146">Jelentkezzen be a webhelykezelő eszközbe azzal az URL-címmel, amelyet az e-kereskedelem inicializálásakor a létesítés során megadott (lásd: [E-kereskedelem inicializálása](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="0c0df-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="0c0df-147">A hely beállítási mezőjének megnyitásához kattintson a **Fabrikam** helyre.</span><span class="sxs-lookup"><span data-stu-id="0c0df-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="0c0df-148">Válassza ki azt a tartományt, amelyet az e-kereskedelem inicializálásakor megadott.</span><span class="sxs-lookup"><span data-stu-id="0c0df-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="0c0df-149">Alapértelmezett csatornaként válassza ki a **Fabrikam bővített online áruház** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="0c0df-150">(Győződjön meg arról, hogy a **kiterjesztett** online áruházat választja.)</span><span class="sxs-lookup"><span data-stu-id="0c0df-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="0c0df-151">Alapértelmezett nyelvnek válassza az **en-us** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c0df-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="0c0df-152">Hagyja az **Útvonal** mező értékét változatlanul.</span><span class="sxs-lookup"><span data-stu-id="0c0df-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="0c0df-153">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-153">Select **OK**.</span></span> <span data-ttu-id="0c0df-154">Megjelenik a webhelyen lévő oldalak listája.</span><span class="sxs-lookup"><span data-stu-id="0c0df-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs-in-retail"></a><span data-ttu-id="0c0df-155">Feladatok engedélyezése a Kiskereskedelemben</span><span class="sxs-lookup"><span data-stu-id="0c0df-155">Enable jobs in Retail</span></span>

<span data-ttu-id="0c0df-156">A feladatok engedélyezéséhez a Kiskereskedelemben kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c0df-156">To enable jobs in Retail, follow these steps.</span></span>

1. <span data-ttu-id="0c0df-157">Jelentkezzen be a környezetbe (HQ).</span><span class="sxs-lookup"><span data-stu-id="0c0df-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="0c0df-158">A bal oldali menü használatával nyissa meg a **Kiskereskedelem \> Lekérdezések és jelentések \> Kötegelt feladatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-158">Use the menu on the left to go to **Retail \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="0c0df-159">Az eljárás további lépéseit az alábbi feladatok mindegyikére el kell végezni:</span><span class="sxs-lookup"><span data-stu-id="0c0df-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="0c0df-160">Kiskereskedelmi rendelés e-mail értesítésének feldolgozása</span><span class="sxs-lookup"><span data-stu-id="0c0df-160">Process retail order email notification</span></span>
    * <span data-ttu-id="0c0df-161">Termék elérhetősége</span><span class="sxs-lookup"><span data-stu-id="0c0df-161">Product availability</span></span>
    * <span data-ttu-id="0c0df-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="0c0df-162">P-0001</span></span>
    * <span data-ttu-id="0c0df-163">Rendelésfeladatok szinkronizálása</span><span class="sxs-lookup"><span data-stu-id="0c0df-163">Synchronize orders job</span></span>

1. <span data-ttu-id="0c0df-164">A Gyorsszűrő használatával kereshet a feladatra név szerint.</span><span class="sxs-lookup"><span data-stu-id="0c0df-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="0c0df-165">Ha a feladat állapota **Visszatartás**, hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0c0df-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="0c0df-166">Válassza ki a rekordot.</span><span class="sxs-lookup"><span data-stu-id="0c0df-166">Select the record.</span></span>
    1. <span data-ttu-id="0c0df-167">A Művelet panel **Kötegelt feladat** lapján válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="0c0df-168">Válassza a **Várakozás** parancsot, majd válassza az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c0df-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization-in-retail"></a><span data-ttu-id="0c0df-169">Teljes adatszinkronizálás futtatása a Kiskereskedelemben</span><span class="sxs-lookup"><span data-stu-id="0c0df-169">Run full data synchronization in Retail</span></span>

<span data-ttu-id="0c0df-170">Ha teljes adatszinkronizálást szeretne futtatni a Kiskereskedelemben, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0c0df-170">To run full data synchronization in Retail, follow these steps.</span></span>

1. <span data-ttu-id="0c0df-171">A bal oldali menü használatával nyissa meg a **Modulok \> Kereskedelem \> Központ beállítása \> Kiskereskedelmi ütemezés \> Csatornaadatbázis** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-171">Use the menu on the left to go to **Modules \> Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="0c0df-172">A bal oldali listában az **Alapértelmezett** csatorna van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="0c0df-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="0c0df-173">Válassza ki a másik elérhető csatornát.</span><span class="sxs-lookup"><span data-stu-id="0c0df-173">Select the other available channel.</span></span> <span data-ttu-id="0c0df-174">A csatorna neve **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="0c0df-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="0c0df-175">A műveleti ablakban válassza ki a **Teljes adatszinkronizálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="0c0df-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="0c0df-176">Adja meg **9999** értéket az elosztási ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="0c0df-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="0c0df-177">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-177">Select **OK**.</span></span>
1. <span data-ttu-id="0c0df-178">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0c0df-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="0c0df-179">A hitelkártyaadatok tesztelése tesztvásárlások végrehajtásához</span><span class="sxs-lookup"><span data-stu-id="0c0df-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="0c0df-180">Teszttranzakciók végrehajtásához a weboldalon használhatja a következő teszt hitelkártyaadatokat:</span><span class="sxs-lookup"><span data-stu-id="0c0df-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="0c0df-181">**Kártyaszám:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="0c0df-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="0c0df-182">**Lejárat dátuma:** 10/20</span><span class="sxs-lookup"><span data-stu-id="0c0df-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="0c0df-183">**Kártyaellenőrző kód (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="0c0df-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c0df-184">Semmilyen körülmények között ne próbáljon ki tényleges hitelkártya-adatokat a tesztoldalon.</span><span class="sxs-lookup"><span data-stu-id="0c0df-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c0df-185">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="0c0df-185">Next steps</span></span>

<span data-ttu-id="0c0df-186">A létesítési és a konfigurálási lépések befejezését követően készen áll arra, hogy értékelje az előnézeti környezetet.</span><span class="sxs-lookup"><span data-stu-id="0c0df-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="0c0df-187">Használja a Commerce webhelykezelő eszköz URL-címét a szerzői élményhez lépéshez.</span><span class="sxs-lookup"><span data-stu-id="0c0df-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="0c0df-188">Használja a Commerce webhelykezelő eszköz URL-címét a kiskereskedelmi ügyfél webhely élményhez lépéshez.</span><span class="sxs-lookup"><span data-stu-id="0c0df-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="0c0df-189">A Commerce előzetes környezete nem kötelező funkcióinak konfigurálásához lásd: [Commerce előzetes környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="0c0df-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c0df-190">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0c0df-190">Additional resources</span></span>

[<span data-ttu-id="0c0df-191">Dynamics 365 Commerce előzetes verziós környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="0c0df-191">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="0c0df-192">Egy Dynamics 365 Commerce előnézeti környezet létesítése</span><span class="sxs-lookup"><span data-stu-id="0c0df-192">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="0c0df-193">A Dynamics 365 Commerce előzetes verziós környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="0c0df-193">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="0c0df-194">Dynamics 365 Commerce előzetes verziós környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="0c0df-194">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="0c0df-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="0c0df-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="0c0df-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="0c0df-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="0c0df-197">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="0c0df-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="0c0df-198">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="0c0df-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
