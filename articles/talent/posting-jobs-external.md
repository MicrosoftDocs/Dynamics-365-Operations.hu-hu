---
title: Álláshirdetések feladása külső karrieroldalak felületére az Attractból
description: Ez a témakör bemutatja, hogyan lehet a Dynamics 365 for Talent - Attract alkalmazást használni állások közzétételére külső toborzóoldalakon
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/15/2019
ms.locfileid: "993668"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="ef6f0-103">Álláshirdetések feladása külső karrieroldalak felületére az Attractból</span><span class="sxs-lookup"><span data-stu-id="ef6f0-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef6f0-104">A nyitott pozíciókat elehető legjobb alkalmas jelölt számára szeretné eljuttatni.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="ef6f0-105">A toborzási oldalak, például a Broadbean segítenek elérni ezt a célt.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="ef6f0-106">A Microsoft Dynamics 365 Talent: Attract lehetővé teszi, hogy állásokat egyen közzé a Broadbean oldalon, és a Microsoft folyamatosan új ajánlatokat biztosít majd ezen a területen.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="ef6f0-107">Állások közzététele a Broadbean-en</span><span class="sxs-lookup"><span data-stu-id="ef6f0-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="ef6f0-108">Mielőtt állást tehetne közzé a Broadbean-en konfigurálnia kell az Broadbean integrációt.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="ef6f0-109">Állások közzétételéhez külső webhelyeken rendelkeznie kell az [Átfogó felvételi bővítménnyel](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="ef6f0-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="ef6f0-110">Ez a funkció jelenleg előnézetben van.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-110">This feature is currently in preview.</span></span> <span data-ttu-id="ef6f0-111">Ha ki szeretné próbálni, akkor [be kell kapcsolnia az Attract rendszergazdai beállításai között](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="ef6f0-111">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="ef6f0-112">Broadbean integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ef6f0-112">Configure Broadbean integration</span></span>

1. <span data-ttu-id="ef6f0-113">Jelentkezzen be Attract alkalmazásba rendszergazdaként</span><span class="sxs-lookup"><span data-stu-id="ef6f0-113">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="ef6f0-114">Válassza ki a **Beállítások** gombot (fogaskerék-szimbólum) a lap jobb felső sarkában, majd válassza a **Felügyeleti központ** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-114">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="ef6f0-115">A **Feladattábla beállításai** lapon a **Broadbean integráció engedélyezése** szakaszban, kapcsolja be az integrációt.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-115">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="ef6f0-116">Forduljon a Broadbean-hoz, és adja meg az adatokat a **Felhasználónév, Ügyfél-azonosító, Titkosítási Token** elemekhez.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-116">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="ef6f0-117">A Broadbean hitelesítő adatai kényes és bizalmas természetűek.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-117">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="ef6f0-118">Ezért átgondoltan ossza meg azokat.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-118">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="ef6f0-119">Mindenki akinek rendszergazdai szerepköre van az Attract megoldásban megtekintheti ezeket a hitelesítő adatokat.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-119">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="ef6f0-120">A Microsoft és Attract vesz nem részt ezen értékek létrehozásában és kezelésében.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-120">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="ef6f0-121">Az Ön felelőssége naprakészen tartani azokat az Attract megoldásban, illetve az, hogy együttműködjön a Broadbeannel, hogy megoldja a hitelesítési adatokkal kapcsolatos esetleges problémákat.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-121">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="ef6f0-122">Állás közzététele a Broadbean-en</span><span class="sxs-lookup"><span data-stu-id="ef6f0-122">Post a job to Broadbean</span></span>

<span data-ttu-id="ef6f0-123">Miután a Broadbean be van kapcsolva,a toborzók és a rendszergazdák állásokat tehetnek közzé rajta.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-123">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="ef6f0-124">Egy jelentkezési URL-cím szükséges az álláshoz.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-124">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="ef6f0-125">Az Attract megoldásban nyissa meg az állást, amelyet fel szeretné adni, a Broadbean-be.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-125">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="ef6f0-126">A **Feladások** részben válassza a **Feladás most** gombot, amely megfele a Broadbean-nek.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-126">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="ef6f0-127">Kövesse a Broadbean ablakának utasításait.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-127">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="ef6f0-128">Az Attract a következő adatokat továbbítja a Broadbean számára:</span><span class="sxs-lookup"><span data-stu-id="ef6f0-128">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="ef6f0-129">Kérésazonosító</span><span class="sxs-lookup"><span data-stu-id="ef6f0-129">Request ID</span></span>
- <span data-ttu-id="ef6f0-130">Beosztás</span><span class="sxs-lookup"><span data-stu-id="ef6f0-130">Job title</span></span>
- <span data-ttu-id="ef6f0-131">Feladat leírása</span><span class="sxs-lookup"><span data-stu-id="ef6f0-131">Job description</span></span>
- <span data-ttu-id="ef6f0-132">Munkavégzés helyszíne</span><span class="sxs-lookup"><span data-stu-id="ef6f0-132">Job location</span></span>
- <span data-ttu-id="ef6f0-133">Jelentkezési URL</span><span class="sxs-lookup"><span data-stu-id="ef6f0-133">Apply URL</span></span>
- <span data-ttu-id="ef6f0-134">Toborzó adatai</span><span class="sxs-lookup"><span data-stu-id="ef6f0-134">Recruiter information</span></span>

<span data-ttu-id="ef6f0-135">A feladás sikeres befejezése után a Broadbean-ben a **Feladások** részében Attract állásnak a Broadbean státusza **Feladva**.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-135">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="ef6f0-136">A Broadbean megköveteli az **Iparág** mezőt.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-136">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="ef6f0-137">Alapértelmezés szerint ez a mező **IT** értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-137">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="ef6f0-138">Az érték módosítható a megfelelő iparágra a Broadbean álláshirdetés ablakában.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-138">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="ef6f0-139">Eltart egy ideig, amíg a Boradbean befejezi az állás közzétételét az összes kiválasztott hirdetőfelületre</span><span class="sxs-lookup"><span data-stu-id="ef6f0-139">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="ef6f0-140">Emiatt előfordulhat, hogy csak egy kis késedelemmel végzi el az Attract az állapotfrissítés t az álláshoz.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-140">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="ef6f0-141">Egy Broadbean álláshirdetés megtekintése</span><span class="sxs-lookup"><span data-stu-id="ef6f0-141">View a Broadbean job posting</span></span>

<span data-ttu-id="ef6f0-142">Miután Broadbean-ben közzétesz egy állást az, Attractból is megtekintheti.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-142">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="ef6f0-143">Az Attract megoldásban nyissa meg az állást, amelyet meg szeretne tekinteni a Broadbean-ben.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-143">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="ef6f0-144">A **feladások** szakaszban,válassz a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Megtekintés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-144">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="ef6f0-145">A Broadbean álláshirdetés egy új ablakban jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-145">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="ef6f0-146">Egy Broadbean álláshirdetés frissítése</span><span class="sxs-lookup"><span data-stu-id="ef6f0-146">Update a Broadbean job posting</span></span>

<span data-ttu-id="ef6f0-147">Kétféle módon frissíthet egy Broadbean álláshirdetést.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-147">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="ef6f0-148">Az Attract megoldásban nyissa meg az állást, amelyet frissíteni szeretne.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-148">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="ef6f0-149">A **Feladások** részben válassza a **Feladás frissítése** gombot, amely megfele a Broadbean-nek.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-149">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="ef6f0-150">Szerkessze a feladást a Broadbean ablakában.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-150">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="ef6f0-151">– vagy –</span><span class="sxs-lookup"><span data-stu-id="ef6f0-151">–or–</span></span>

1. <span data-ttu-id="ef6f0-152">Az Attract megoldásban nyissa meg az állást, amelyet meg szeretne tekinteni a Broadbean-ben.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-152">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="ef6f0-153">A **feladások** szakaszban,válassz a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Megtekintés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-153">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="ef6f0-154">Broadbean ablakában szerkesztheti az állás adatait, és ezután újraküldheti az állást.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-154">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="ef6f0-155">Az állás részletei az Attract megoldásban nem változnak.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-155">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="ef6f0-156">Egy Broadbean álláshirdetés eltávolítása</span><span class="sxs-lookup"><span data-stu-id="ef6f0-156">Remove a Broadbean job posting</span></span>

<span data-ttu-id="ef6f0-157">A Broadbean-ből igény esetén eltávolíthatja az álláshirdetést.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-157">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="ef6f0-158">Az Attract megoldásban nyissa meg az állást, amelyet el szeretne távolítani.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-158">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="ef6f0-159">A **Feladások** szakaszban,válassza a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Közzététel eltávolítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-159">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="ef6f0-160">Miután a Broadbean eltávolítja az állást Broadbean elemhez az Attract megoldásban megjelenik egy **Feladás most** gomb.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-160">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="ef6f0-161">Ez a gomb jelzi, hogy az állás törölve lett, és újra fel lehet adni.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-161">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="ef6f0-162">Broadbean-integráció – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="ef6f0-162">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="ef6f0-163">Ha probléma merül fel a feladással a Broadbean-be, próbálja meg ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-163">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="ef6f0-164">Győződjön meg róla, hogy az Attract megoldásban megadott Broadbean hitelesítő adatok érvényesek és helyesek.</span><span class="sxs-lookup"><span data-stu-id="ef6f0-164">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="ef6f0-165">Ha a hitelesítő adatok érvényesek és helyesek forduljon a [Broadbean támogatáshoz](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="ef6f0-165">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="ef6f0-166">Ha a probléma továbbra is fennáll, forduljon [Microsoft támogatáshoz](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="ef6f0-166">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
