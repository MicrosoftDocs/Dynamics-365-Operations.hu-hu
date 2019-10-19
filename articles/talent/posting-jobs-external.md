---
title: Állások feladása külső karrierwebhelyekre az Attract szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet a Dynamics 365 Talent – Attract alkalmazást használni állások közzétételére külső toborzóoldalakon
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: 919cec773d5e57e8f5429e31872db7ed658e969b
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008082"
---
# <a name="post-jobs-to-broadbean"></a><span data-ttu-id="d1342-103">Állások közzététele a Broadbean felületén</span><span class="sxs-lookup"><span data-stu-id="d1342-103">Post jobs to Broadbean</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1342-104">A Microsoft Dynamics 365 Talent: Attract segít a tehetségek bevonzásában azáltal, hogy lehetővé teszi, hogy állásait közvetlenül a Boadbean felületén tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="d1342-104">Microsoft Dynamics 365 Talent: Attract helps you get the talent you need by letting you post your jobs directly from Attract to Broadbean.</span></span> <span data-ttu-id="d1342-105">Miután [létrehozta az állást](./creating-jobs-attract.md) az Attract megoldásban, csupán egy gombot kell kiválasztania ahhoz, hogy az állást az összes potenciális pályázóhoz eljuttassa a Broadbean oldalán.</span><span class="sxs-lookup"><span data-stu-id="d1342-105">After you [create a job](./creating-jobs-attract.md), all you have to do is click a button to put your job in front of all the potential job candidates on Broadbean.</span></span>

<span data-ttu-id="d1342-106">Az állásoknak a Broadbeanen történő feladásához megfelelő Broadbean-licenc szükséges.</span><span class="sxs-lookup"><span data-stu-id="d1342-106">Posting jobs to Broadbean requires an appropriate Broadbean license.</span></span> <span data-ttu-id="d1342-107">A Broadbean különböző termékeket és csomagokat kínál.</span><span class="sxs-lookup"><span data-stu-id="d1342-107">Broadbean offers various products and plans.</span></span> <span data-ttu-id="d1342-108">Ha további tájékoztatást szeretne a Broadbean licenceléséről és árképzéséről, [vegye fel a kapcsolatot a Broadbeannel](https://www.broadbean.com/contact-us/).</span><span class="sxs-lookup"><span data-stu-id="d1342-108">For more information about Broadbean licensing and pricing, [contact Broadbean](https://www.broadbean.com/contact-us/).</span></span>

<span data-ttu-id="d1342-109">Ha Ön egy olyan adminisztrátor, akinek több információra van szüksége a Broadbean-integrációnak az Attract szolgáltatással történő konfigurálásával kapcsolatban, lásd: [Külső álláshirdetések beállításainak megadása](./attract-admin-job-board-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d1342-109">If you're an admin who needs more information about how to configure Broadbean integration with Attract, see [Enter settings for external job boards](./attract-admin-job-board-settings.md).</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="d1342-110">Állások közzététele a Broadbean felületén</span><span class="sxs-lookup"><span data-stu-id="d1342-110">Post jobs to Broadbean</span></span>

<span data-ttu-id="d1342-111">Miután a Broadbean be van kapcsolva,a toborzók és a rendszergazdák állásokat tehetnek közzé rajta.</span><span class="sxs-lookup"><span data-stu-id="d1342-111">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="d1342-112">Egy jelentkezési URL-cím szükséges az álláshoz.</span><span class="sxs-lookup"><span data-stu-id="d1342-112">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="d1342-113">Az Attract megoldásban nyissa meg az állást, amelyet fel szeretné adni, a Broadbean-be.</span><span class="sxs-lookup"><span data-stu-id="d1342-113">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="d1342-114">A **Feladások** részben válassza a **Feladás most** gombot, amely megfele a Broadbean-nek.</span><span class="sxs-lookup"><span data-stu-id="d1342-114">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="d1342-115">Kövesse a Broadbean ablakának utasításait.</span><span class="sxs-lookup"><span data-stu-id="d1342-115">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="d1342-116">Az Attract a következő adatokat továbbítja a Broadbean számára:</span><span class="sxs-lookup"><span data-stu-id="d1342-116">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="d1342-117">Kérésazonosító</span><span class="sxs-lookup"><span data-stu-id="d1342-117">Request ID</span></span>
- <span data-ttu-id="d1342-118">Beosztás</span><span class="sxs-lookup"><span data-stu-id="d1342-118">Job title</span></span>
- <span data-ttu-id="d1342-119">Feladat leírása</span><span class="sxs-lookup"><span data-stu-id="d1342-119">Job description</span></span>
- <span data-ttu-id="d1342-120">Munkavégzés helyszíne</span><span class="sxs-lookup"><span data-stu-id="d1342-120">Job location</span></span>
- <span data-ttu-id="d1342-121">Jelentkezési URL</span><span class="sxs-lookup"><span data-stu-id="d1342-121">Apply URL</span></span>
- <span data-ttu-id="d1342-122">Toborzó adatai</span><span class="sxs-lookup"><span data-stu-id="d1342-122">Recruiter information</span></span>

<span data-ttu-id="d1342-123">A feladás sikeres befejezése után a Broadbean-ben a **Feladások** részében Attract állásnak a Broadbean státusza **Feladva**.</span><span class="sxs-lookup"><span data-stu-id="d1342-123">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="d1342-124">A Broadbean megköveteli az **Iparág** mezőt.</span><span class="sxs-lookup"><span data-stu-id="d1342-124">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="d1342-125">Alapértelmezés szerint ez a mező **IT** értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="d1342-125">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="d1342-126">Az érték módosítható a megfelelő iparágra a Broadbean álláshirdetés ablakában.</span><span class="sxs-lookup"><span data-stu-id="d1342-126">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="d1342-127">Eltart egy ideig, amíg a Boradbean befejezi az állás közzétételét az összes kiválasztott hirdetőfelületre</span><span class="sxs-lookup"><span data-stu-id="d1342-127">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="d1342-128">Emiatt előfordulhat, hogy csak egy kis késedelemmel végzi el az Attract az állapotfrissítés t az álláshoz.</span><span class="sxs-lookup"><span data-stu-id="d1342-128">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="d1342-129">Egy Broadbean álláshirdetés megtekintése</span><span class="sxs-lookup"><span data-stu-id="d1342-129">View a Broadbean job posting</span></span>

<span data-ttu-id="d1342-130">Miután Broadbean-ben közzétesz egy állást az, Attractból is megtekintheti.</span><span class="sxs-lookup"><span data-stu-id="d1342-130">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="d1342-131">Az Attract megoldásban nyissa meg az állást, amelyet meg szeretne tekinteni a Broadbean-ben.</span><span class="sxs-lookup"><span data-stu-id="d1342-131">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="d1342-132">A **Feladások** szakaszban válassza a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Megtekintés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d1342-132">On the **Postings** tab, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="d1342-133">A Broadbean álláshirdetés egy új ablakban jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d1342-133">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="d1342-134">Egy Broadbean álláshirdetés frissítése</span><span class="sxs-lookup"><span data-stu-id="d1342-134">Update a Broadbean job posting</span></span>

<span data-ttu-id="d1342-135">Kétféle módon frissíthet egy Broadbean álláshirdetést.</span><span class="sxs-lookup"><span data-stu-id="d1342-135">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="d1342-136">Az Attract megoldásban nyissa meg az állást, amelyet frissíteni szeretne.</span><span class="sxs-lookup"><span data-stu-id="d1342-136">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="d1342-137">A **Feladások** részben válassza a **Feladás frissítése** gombot, amely megfele a Broadbean-nek.</span><span class="sxs-lookup"><span data-stu-id="d1342-137">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="d1342-138">Szerkessze a feladást a Broadbean ablakában.</span><span class="sxs-lookup"><span data-stu-id="d1342-138">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="d1342-139">– vagy –</span><span class="sxs-lookup"><span data-stu-id="d1342-139">–or–</span></span>

1. <span data-ttu-id="d1342-140">Az Attract megoldásban nyissa meg az állást, amelyet meg szeretne tekinteni a Broadbean-ben.</span><span class="sxs-lookup"><span data-stu-id="d1342-140">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="d1342-141">A **feladások** szakaszban,válassz a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Megtekintés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d1342-141">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="d1342-142">Broadbean ablakában szerkesztheti az állás adatait, és ezután újraküldheti az állást.</span><span class="sxs-lookup"><span data-stu-id="d1342-142">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="d1342-143">Az állás részletei az Attract megoldásban nem változnak.</span><span class="sxs-lookup"><span data-stu-id="d1342-143">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="d1342-144">Egy Broadbean álláshirdetés eltávolítása</span><span class="sxs-lookup"><span data-stu-id="d1342-144">Remove a Broadbean job posting</span></span>

<span data-ttu-id="d1342-145">A Broadbean-ből igény esetén eltávolíthatja az álláshirdetést.</span><span class="sxs-lookup"><span data-stu-id="d1342-145">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="d1342-146">Az Attract megoldásban nyissa meg az állást, amelyet el szeretne távolítani.</span><span class="sxs-lookup"><span data-stu-id="d1342-146">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="d1342-147">A **Feladások** szakaszban,válassza a három pont (**...**) gombot, amely megfelel a Broadbean-nek, és válassza **Közzététel eltávolítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d1342-147">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="d1342-148">Miután a Broadbean eltávolítja az állást Broadbean elemhez az Attract megoldásban megjelenik egy **Feladás most** gomb.</span><span class="sxs-lookup"><span data-stu-id="d1342-148">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="d1342-149">Ez a gomb jelzi, hogy az állás törölve lett, és újra fel lehet adni.</span><span class="sxs-lookup"><span data-stu-id="d1342-149">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-job-posting-to-broadbean"></a><span data-ttu-id="d1342-150">A Broadbean álláshirdetéseinek hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="d1342-150">Troubleshoot job posting to Broadbean</span></span>

<span data-ttu-id="d1342-151">Ha probléma merül fel a feladással a Broadbean-be, próbálja meg ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d1342-151">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="d1342-152">Győződjön meg róla, hogy az Attract megoldásban megadott Broadbean hitelesítő adatok érvényesek és helyesek.</span><span class="sxs-lookup"><span data-stu-id="d1342-152">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="d1342-153">Ha a hitelesítő adatok érvényesek és helyesek forduljon a [Broadbean támogatáshoz](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="d1342-153">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="d1342-154">Ha a probléma továbbra is fennáll, forduljon [Microsoft támogatáshoz](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="d1342-154">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1342-155">Lásd még</span><span class="sxs-lookup"><span data-stu-id="d1342-155">See also</span></span>

[<span data-ttu-id="d1342-156">Állások létrehozása</span><span class="sxs-lookup"><span data-stu-id="d1342-156">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="d1342-157">Külső álláshirdetések beállításainak megadása</span><span class="sxs-lookup"><span data-stu-id="d1342-157">Enter settings for external job boards</span></span>](./attract-admin-job-board-settings.md)
