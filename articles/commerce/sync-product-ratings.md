---
title: 'A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce'
description: Ez a témakör azt mutatja be, hogyan lehet szinkronizálni a termékminősítéseket a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: '---'
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6757a5a13d16c490dced7118c1da8aa0ea6d8994
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029486"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a><span data-ttu-id="cd724-103">A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="cd724-103">Sync product ratings in Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cd724-104">Ez a témakör azt mutatja be, hogyan lehet szinkronizálni a termékminősítéseket a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cd724-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cd724-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cd724-105">Overview</span></span>

<span data-ttu-id="cd724-106">A termék minősítések többcsatornán helyen történő felhasználásához, például a pénztárnál (POS) és a hívásközpontokban a minősítési és az értékelés szolgáltatásból származó minősítéseket importálni kell a Commerce csatornaadatbázisába.</span><span class="sxs-lookup"><span data-stu-id="cd724-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Commerce channel database.</span></span> <span data-ttu-id="cd724-107">Amikor a többcsatornás helyeken elérhetővé teszik a termék minősítését, azzal közvetett módon segítik a vásárlókat, hogy kapcsolatba lépjenek az értékesítőkkel.</span><span class="sxs-lookup"><span data-stu-id="cd724-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="cd724-108">Ez a témakör a következő feladatok leírását tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="cd724-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="cd724-109">A **Termék minősítések szinkronizálása** kötegelt feladatként konfigurálható a **Minősítések és vélemények szolgáltatásból származó** termékminősítések szinkronizálására.</span><span class="sxs-lookup"><span data-stu-id="cd724-109">Configure **Product ratings sync job** as a batch job to synchronize product ratings from the **Ratings and Reviews service**.</span></span>
1. <span data-ttu-id="cd724-110">Annak megerősítése hogy a termékminősítések szinkronizálásának kötegelt feladata sikeres volt.</span><span class="sxs-lookup"><span data-stu-id="cd724-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="cd724-111">A termék minősítések elérhetővé tétele a pénztárban.</span><span class="sxs-lookup"><span data-stu-id="cd724-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a><span data-ttu-id="cd724-112">Kötegelt feladat konfigurálása a termékminősítések szinkronizálásához</span><span class="sxs-lookup"><span data-stu-id="cd724-112">Configure a batch job to synchronize product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd724-113">Mielőtt hozzáfogna, győződjön meg arról, hogy telepítve van a Dynamics 365 Commerce 10.0.6 vagy újabb verziója.</span><span class="sxs-lookup"><span data-stu-id="cd724-113">Before you start, make sure that version 10.0.6 or later of Dynamics 365 Commerce is installed.</span></span>

### <a name="initialize-the-commerce-scheduler"></a><span data-ttu-id="cd724-114">A kereskedelmi tervezés és ütemezés incializálása</span><span class="sxs-lookup"><span data-stu-id="cd724-114">Initialize the commerce scheduler</span></span>

<span data-ttu-id="cd724-115">A kereskedelmi tervezés és ütemezés inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cd724-115">To initialize the commerce scheduler, follow these steps.</span></span>

1. <span data-ttu-id="cd724-116">Ugrás a **Retail és Commerce \> Headquarters beállítás \> Kereskedelmi ütemező  \>Kereskedelmi ütemező inicializálása** elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-116">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Initialize commerce scheduler**.</span></span> <span data-ttu-id="cd724-117">Vagy keressen rá a „Kereskedelmi ütemező inicializálása” elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-117">Alternatively, search for "Initialize commerce scheduler."</span></span>
1. <span data-ttu-id="cd724-118">Győződjön meg arról, hogy a **Kereskedelmi tervezés és ütemezés inicializálása** párbeszédpanelen a **Meglévő konfiguráció törlése** beállítás **Nem** értékre van állítva, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd724-118">In the **Initialize commerce scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="cd724-119">Ellenőrizze a RetailProductRating alfeladatot</span><span class="sxs-lookup"><span data-stu-id="cd724-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="cd724-120">Ha ellenőrizni szeretné, hogy létezik-e a **RetailProductRating** alfeladat, és hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cd724-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="cd724-121">Ugrás a **Retail és Commerce \> Headquarters beállítás \> Kereskedelmi ütemező  \>Ütemezési alfeladatok** elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-121">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="cd724-122">Másik lehetőségként keressen rá az „Ütemezési alfeladatok” elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="cd724-123">Az alfeladatok listájában keressen meg vagy keressen rá a **RetailProductRating** alfeladatra.</span><span class="sxs-lookup"><span data-stu-id="cd724-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="cd724-124">A következő ábra egy példát mutat be az alfeladat részleteire a Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cd724-124">The following illustration shows an example of the subjob details in Commerce.</span></span>

![A RetailProductRating alfeladat részletei](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="cd724-126">Ha nem találja a **RetailProductRating** alfeladatot, előfordulhat, hogy már futtatta a **Termékértékelések szinkronizálása** feladatot és az **1040 CDX** feladatot a Kereskedelmi tervezés és ütemezés inicializálásának megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="cd724-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the Commerce scheduler.</span></span> <span data-ttu-id="cd724-127">Ebben az esetben a **Teljes adatszinkronizálási** feladat futtatásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cd724-127">In this case, follow these steps to run the **Full data sync** job.</span></span>

> 1. <span data-ttu-id="cd724-128">Ugrás a **Retail és Commerce \> Headquarters beállítás \> Kereskedelmi ütemező  \>Csatorna-adatbázis** elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-128">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span> <span data-ttu-id="cd724-129">Vagy keressen rá a „Csatorna-adatbázis” elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="cd724-130">Válassza ki a szinkronizálni kívánt csatorna-adatbázist.</span><span class="sxs-lookup"><span data-stu-id="cd724-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="cd724-131">A műveleti ablakban válassza ki a **Teljes adatszinkronizálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="cd724-131">On the action pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="cd724-132">Válassza ki az **Elosztási ütemezés kiválasztása** legördülő párbeszédpanelan az **1040 – termékek** elemet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cd724-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="cd724-133">Az előző eljárás lépéseinek megismétlésével győződjön meg arról, hogy a **RetailProductRating** alfeladat létrejött.</span><span class="sxs-lookup"><span data-stu-id="cd724-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="cd724-134">Termékminősítések importálása</span><span class="sxs-lookup"><span data-stu-id="cd724-134">Import product ratings</span></span>

<span data-ttu-id="cd724-135">Ha a termékminősítéseket szeretne importálni a Commerce megoldásba a minősítési és az értékelés szolgáltatásból, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cd724-135">To import product ratings into Commerce from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="cd724-136">Nyissa meg a **Retail és Commerce \> Központ beállítása \> Kereskedelmi ütemezés \> Termékminősítés feladatok szinkronizálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd724-136">Go to **Retail and Commerce \> Headquarters setup \> Commerce scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="cd724-137">Vagy keressen rá a „Termékminősítési feladatok importálása” kifejezésre.</span><span class="sxs-lookup"><span data-stu-id="cd724-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="cd724-138">A **Termékminősítések lekérése** párbeszédpanel **Futtatás a háttérben** gyorslapján az **Ismétlődés** elemet.</span><span class="sxs-lookup"><span data-stu-id="cd724-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="cd724-139">Az **Ismétlődés definiálása** párbeszédpanelen állítson be egy ismétlődési mintát.</span><span class="sxs-lookup"><span data-stu-id="cd724-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="cd724-140">(A javasolt érték két óra.) Ne ütemezzen egy óránál rövidebb ismétlődést.</span><span class="sxs-lookup"><span data-stu-id="cd724-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="cd724-141">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd724-141">Select **OK**.</span></span>
1. <span data-ttu-id="cd724-142">Állítsa be a **Kötegelt feldolgozás** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="cd724-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="cd724-143">Ez a beállítás segít biztosítani azt, hogy a naplók ellenőrizhetők legyenek, és ellenőrizhesse a kötegelt feladatok futásának állapotát.</span><span class="sxs-lookup"><span data-stu-id="cd724-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="cd724-144">Válassza az **OK** lehetőséget a kötegelt feladat futtatásához.</span><span class="sxs-lookup"><span data-stu-id="cd724-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="cd724-145">A következő ábra egy példát mutat be a kötegelt feladatok konfigurálására a Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cd724-145">The following illustration shows an example of batch job configuration in Commerce.</span></span>

![A termékminősítések konfigurációja kötegelt feladat konfigurálása](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="cd724-147">Annak megerősítése hogy a termékminősítések szinkronizálásának kötegelt feladata sikeres volt</span><span class="sxs-lookup"><span data-stu-id="cd724-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="cd724-148">Ha ellenőrizni szeretné, hogy a **Termékminősítések szinkronizálása** kötegelt feladat sikeres volt-e, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cd724-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="cd724-149">Nyissa meg a **Retail és Commerce \> Rendszeradminisztrátor \> Lekérdezések \> Kötegelt feladatok** lehetőséget, vagy, ha csak Commerce raktározási egységet (SKU) használ a **Retail és Commerce \> Lekérdezések és jelentések \> Kötegelt feladatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd724-149">Go to **Retail and Commerce \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Commerce-only stock keeping unit (SKU), **Retail and Commerce \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="cd724-150">Vagy keressen rá a „kötegelt feladatok” elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="cd724-151">Ha meg szeretné tekinteni a kötegelt feladat részleteit, a kötegelt feladatok listájában a **Feladattípus** oszlopban keressen egy olyan leírást, amely a „Termékminősítések lekérése” kifejezést tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="cd724-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="cd724-152">Válassza ki a feladat azonosítóját a kötegelt feladat részleteinek, például az ütemezett kezdési dátum/időt és az ismétlődés szövege megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="cd724-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="cd724-153">A következő ábra egy példát mutat be a kötegelt feladat részleteire a Commerce alkalmazásban amikor a kötegelt feladat két órás időközönkénti futtatásra van ütemezve.</span><span class="sxs-lookup"><span data-stu-id="cd724-153">The following illustration shows an example of the batch job details in Commerce when the batch job is scheduled to run at two-hour intervals.</span></span>

![Termékminősítések szinkronizálása kötegelt feladat részletei](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="cd724-155">A termék minősítések elérhetővé tétele a pénztárban</span><span class="sxs-lookup"><span data-stu-id="cd724-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="cd724-156">A minősítések és a értékelések megoldás a Dynamics 365 Commerce alkalmazásban egy többcsatornás megoldás.</span><span class="sxs-lookup"><span data-stu-id="cd724-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="cd724-157">A termék minősítések azonban alapértelmezésben nem jelennek meg a pénztárnál.</span><span class="sxs-lookup"><span data-stu-id="cd724-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="cd724-158">Annak érdekében, hogy az áruházak ügyfelei láthassák a minősítéseket és értékeléseket, amikor segítséget kapnak az értékesítési munkatársaktól, be kell kapcsolni a termék minősítéseit a POS-nál.</span><span class="sxs-lookup"><span data-stu-id="cd724-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="cd724-159">A termékértékelések bekapcsolásához a pénztárban hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cd724-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="cd724-160">Menjen a **Retail és Commerce \> Commerce beállítása \> Paraméterek \> Commerce paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cd724-160">Go to **Retail and Commerce \> Commerce setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="cd724-161">Vagy keressen rá a „Commerce paraméterek” elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-161">Alternatively, search for "Commerce parameters."</span></span>
1. <span data-ttu-id="cd724-162">Válassza a **Konfigurációs paraméterek** lap **Új** elemét.</span><span class="sxs-lookup"><span data-stu-id="cd724-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="cd724-163">Írjon be egy nevet, például **RatingsAndReviews.EnableProductRatingsForRetailStores**, és az értéket állítsa be **igaz**értékre.</span><span class="sxs-lookup"><span data-stu-id="cd724-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="cd724-164">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd724-164">Select **Save**.</span></span>
1. <span data-ttu-id="cd724-165">Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="cd724-165">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span> <span data-ttu-id="cd724-166">Vagy keressen rá az „Elosztási ütemezés” elemre.</span><span class="sxs-lookup"><span data-stu-id="cd724-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="cd724-167">A feladatok listájában válassza az **1110** (**Globális konfiguráció**) elemét, majd válassza a **Futtatás most** parancsot.</span><span class="sxs-lookup"><span data-stu-id="cd724-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="cd724-168">Miután sikeresen futtatta a feladatot, győződjön meg arról, hogy a termékminősítések most megjelennek a pénztárnál.</span><span class="sxs-lookup"><span data-stu-id="cd724-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="cd724-169">A következő ábra egy példát mutat be a Commerce paraméterek konfigurálására, amellyel a termék minősítéseit lehet lehet bekapcsolni a pénztárban.</span><span class="sxs-lookup"><span data-stu-id="cd724-169">The following illustration shows an example of the configuration of the Commerce parameters to turn on product ratings at the POS.</span></span>

![A termék minősítéséhez szükséges Commerce paraméterek konfigurálása a pénztárban](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="cd724-171">A következő ábrán egy példa látható a termékminősítésekre a pénztárban.</span><span class="sxs-lookup"><span data-stu-id="cd724-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Termékminősítések a pénztárban](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="cd724-173">A következő ábrán egy példa látható a termékminősítésekre a hívásközponti csatornákban.</span><span class="sxs-lookup"><span data-stu-id="cd724-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Termékminősítések egy hívásközpont-csatornában](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="cd724-175">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cd724-175">Additional resources</span></span>

[<span data-ttu-id="cd724-176">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="cd724-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="cd724-177">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="cd724-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="cd724-178">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="cd724-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="cd724-179">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="cd724-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
