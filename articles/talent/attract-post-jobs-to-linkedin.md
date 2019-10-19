---
title: Állások feladása a LinkedIn felületére a Microsoft Dynamics 365 Talent - Attract szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet a Dynamics 365 Talent - Attract alkalmazást használni állások közzétételére a LinkedIn felületén.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
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
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 014202ca49e5bd6204d450b2a43c7372ed84ff33
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008243"
---
# <a name="post-jobs-to-linkedin"></a><span data-ttu-id="89d75-103">Álláshirdetések feladása a LinkedIn felületén</span><span class="sxs-lookup"><span data-stu-id="89d75-103">Post jobs to LinkedIn</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89d75-104">A LinkedIn a legnagyobb online szakmai hálózat, amely hozzáférést biztosít a világ legjobb tehetségéhez.</span><span class="sxs-lookup"><span data-stu-id="89d75-104">LinkedIn is the largest online professional network, giving you access to the world's top talent.</span></span> <span data-ttu-id="89d75-105">A Microsoft Dynamics 365 Talent: Attract segít a tehetségek bevonzásában azáltal, hogy lehetővé teszi, hogy állásait közvetlenül a LinkedIn felületén tegye közzé.</span><span class="sxs-lookup"><span data-stu-id="89d75-105">Microsoft Dynamics 365 Talent: Attract helps you get the talent that you need by letting you post your jobs directly from Attract to LinkedIn.</span></span>

<span data-ttu-id="89d75-106">Az Attract lehetővé teszi Limited Listingek közzétételét a LinkedIn felületén külön költség nélkül.</span><span class="sxs-lookup"><span data-stu-id="89d75-106">Attract lets you post Limited Listings to LinkedIn at no extra cost.</span></span> <span data-ttu-id="89d75-107">Ezek a hirdetések csak a LinkedIn szoftveres partnerein, péládul az Attract alkalmazáson keresztül érhetők el.</span><span class="sxs-lookup"><span data-stu-id="89d75-107">These listings are available only through LinkedIn software partners such as Attract.</span></span> <span data-ttu-id="89d75-108">Nem jelennek meg a vállalat LinkedIn lapján a **Karrier** panelen, mivel csak ott csak a fizetett hirdetések jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="89d75-108">They don't appear in the **Careers** panel on your company's LinkedIn page, because only paid listings appear there.</span></span> <span data-ttu-id="89d75-109">Azonban megjelennek, ha a potenciális jelöltek az összes elérhető állást megtekintik.</span><span class="sxs-lookup"><span data-stu-id="89d75-109">However, they are shown when potential candidates view all available jobs.</span></span> <span data-ttu-id="89d75-110">A Limited Listingek a LinkedIn álláskeresésekben is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="89d75-110">Limited Listings are also shown in LinkedIn job searches.</span></span>

<span data-ttu-id="89d75-111">Miután [létrehozta az állást](./creating-jobs-attract.md) az Attract megoldásban, csak egy gombot kell kiválasztania ahhoz, hogy az állást több ezer potenciális pályázóhoz eljuttassa a LinkedIn oldalán.</span><span class="sxs-lookup"><span data-stu-id="89d75-111">After you [create a job](./creating-jobs-attract.md) in Attract, you just have to select a button to put your job in front of thousands of potential candidates on LinkedIn.</span></span>

<span data-ttu-id="89d75-112">A következő táblázat bemutatja, hogy milyen műveletek hajthatók végre a LinkedIn felületen a felhasználói szerepkörtől függően.</span><span class="sxs-lookup"><span data-stu-id="89d75-112">The following table shows the actions that you can perform on LinkedIn, depending on your user role.</span></span>

| <span data-ttu-id="89d75-113">Szerep</span><span class="sxs-lookup"><span data-stu-id="89d75-113">Role</span></span> | <span data-ttu-id="89d75-114">Elvégezhető műveletek</span><span class="sxs-lookup"><span data-stu-id="89d75-114">Actions that you can take</span></span> |
|---|---|
| <span data-ttu-id="89d75-115">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="89d75-115">Admin</span></span> | <span data-ttu-id="89d75-116">Közzététel, ismételt közzététel és közzététel visszavonása</span><span class="sxs-lookup"><span data-stu-id="89d75-116">Post, repost, and unpost</span></span> |
| <span data-ttu-id="89d75-117">Felvételi vezető</span><span class="sxs-lookup"><span data-stu-id="89d75-117">Hiring manager</span></span> | <span data-ttu-id="89d75-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="89d75-118">Read only</span></span> |
| <span data-ttu-id="89d75-119">Toborzó</span><span class="sxs-lookup"><span data-stu-id="89d75-119">Recruiter</span></span> | <span data-ttu-id="89d75-120">Közzététel, ismételt közzététel és közzététel visszavonása</span><span class="sxs-lookup"><span data-stu-id="89d75-120">Post, repost, and unpost</span></span> |
| <span data-ttu-id="89d75-121">Interjúkészítő</span><span class="sxs-lookup"><span data-stu-id="89d75-121">Interviewer</span></span> | <span data-ttu-id="89d75-122">Nincs hozzáférés</span><span class="sxs-lookup"><span data-stu-id="89d75-122">No access</span></span> |
| <span data-ttu-id="89d75-123">Csak olvasható</span><span class="sxs-lookup"><span data-stu-id="89d75-123">Read-only</span></span> | <span data-ttu-id="89d75-124">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="89d75-124">Read only</span></span> |

<span data-ttu-id="89d75-125">Az Attract felhasználói szerepköreivel kapcsolatos további tudnivalókért tekintse át a [Biztonság és szerepkörkezelés az Attract alkalmazásban](./security-attract.md) részt.</span><span class="sxs-lookup"><span data-stu-id="89d75-125">For more information about user roles in Attract, see [Security and role management in Attract](./security-attract.md).</span></span>

<span data-ttu-id="89d75-126">Ha Ön adminisztrátor, és a LinkedIn integrációjának konfigurálásával kapcsolatban további tájékoztatást szeretne kapni lásd a [A LinkedIn integrációjának beállítása](./attract-admin-linkedin.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="89d75-126">If you're an admin and need more information about how to configure LinkedIn integration with Attract, see [Set up integration with LinkedIn](./attract-admin-linkedin.md).</span></span>

<span data-ttu-id="89d75-127">A LinkedIn oldalra közzátett állássok az élő LinkedIn webhelyen jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="89d75-127">Jobs that are posted to LinkedIn appear on the live LinkedIn site.</span></span> <span data-ttu-id="89d75-128">Nincs LinkedIn nem rendelkezik tesztelési környezettel állások közzétételéhez.</span><span class="sxs-lookup"><span data-stu-id="89d75-128">LinkedIn doesn't have a test environment for posting jobs.</span></span> <span data-ttu-id="89d75-129">Ezért ügyeljen arra, hogy ne tegyen közzé tesztállásokat.</span><span class="sxs-lookup"><span data-stu-id="89d75-129">Therefore, make sure that you don't accidentally post any test jobs.</span></span>

## <a name="post-jobs-to-linkedin"></a><span data-ttu-id="89d75-130">Álláshirdetések feladása a LinkedIn felületén</span><span class="sxs-lookup"><span data-stu-id="89d75-130">Post jobs to LinkedIn</span></span>

1. <span data-ttu-id="89d75-131">Az Attract megoldásban nyissa meg az állást, amelyet fel szeretné adni, a LinkedIn-en.</span><span class="sxs-lookup"><span data-stu-id="89d75-131">In Attract, open the job that you want to post to LinkedIn.</span></span>
2. <span data-ttu-id="89d75-132">A **Feladások** részben válassza a **Feladás most** gombot, amely megfelel a LinkedIn-nek.</span><span class="sxs-lookup"><span data-stu-id="89d75-132">On the **Postings** tab, select the **Post Now** button that corresponds to LinkedIn.</span></span>

    <span data-ttu-id="89d75-133">[![Állások feladása a LinkedIn felületére az Attract szolgáltatásból](./media/attract-post-job-to-linkedin.png)](./media/attract-post-job-to-linkedin.png)</span><span class="sxs-lookup"><span data-stu-id="89d75-133">[![Attract post job to LinkedIn](./media/attract-post-job-to-linkedin.png)](./media/attract-post-job-to-linkedin.png)</span></span>

3. <span data-ttu-id="89d75-134">A **„Jelentkezés most” webcím létrehozása** párbeszédpanelen válasszon egy beállítást a **A jelöltek a következő módon jelentkezhetnek** alatt.</span><span class="sxs-lookup"><span data-stu-id="89d75-134">In the **Create an "Apply now" web address** dialog box, select an option under **Candidates can apply using a**.</span></span> <span data-ttu-id="89d75-135">Javasoljuk, hogy a **Hivatkozás Attract alkalmazásban** lehetőséget válassza.</span><span class="sxs-lookup"><span data-stu-id="89d75-135">We recommend that you select **Link in Attract**.</span></span>
4. <span data-ttu-id="89d75-136">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89d75-136">Select **Done**.</span></span>
5. <span data-ttu-id="89d75-137">Az **Elküldés feladás után** üzenetmezőben válassza a **Jóváhagyás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89d75-137">In the **Submit for posting** message box, select **Confirm**.</span></span>

<span data-ttu-id="89d75-138">A feladás sikeres befejezése után a LinkedIn felületén a **Feladások** részében Attract állásnak a LinkedIn státusza **Feladva**.</span><span class="sxs-lookup"><span data-stu-id="89d75-138">After LinkedIn successfully completes the posting, the **Postings** section of the job in Attract shows the LinkedIn status as **Posted**.</span></span> <span data-ttu-id="89d75-139">Akár 48 óráig is eltarthat, hogy az állás megjelenjen a LinkedIn felületén.</span><span class="sxs-lookup"><span data-stu-id="89d75-139">It can take up to 48 hours for your job to appear in LinkedIn.</span></span>

<span data-ttu-id="89d75-140">Amikor az érdeklődő jelöltek a hirdetés mellett a nézet mellett a **Megtekintés** lehetőséget választják akkor az összes állásadatot látják, valamint a jelentkezésre vonatkozó információkat.</span><span class="sxs-lookup"><span data-stu-id="89d75-140">When interested candidates select **View** next to your listing, they will see the full job details, together with your information about how to apply.</span></span>

<span data-ttu-id="89d75-141">Az Attract megoldáson keresztül feladott állások Limited Listingek.</span><span class="sxs-lookup"><span data-stu-id="89d75-141">All job postings that are done through Attract are Limited Listings.</span></span> <span data-ttu-id="89d75-142">A LinkedIn szolgáltatás Limited Listing hirdetéseivel kapcsolatos további tudnivalókat lásd [Limited Listingek és Premium Job Slotok összehasonlítása Job Wrapping esetén](https://www.linkedin.com/help/recruiter/answer/79049).</span><span class="sxs-lookup"><span data-stu-id="89d75-142">For more information about Limited Listings on LinkedIn, see [Limited Listings vs Premium Job Slots for Job Wrapping](https://www.linkedin.com/help/recruiter/answer/79049).</span></span>

<span data-ttu-id="89d75-143">Ha nem sikerül bejelentkeznie a LinkedIn rendszerbe, vagy állást közzétennie az Attract megoldásból a LinkedIn felületére, lásd [A LinkedIn álláshirdetések hibaelhárítása](./attract-troubleshoot-linkedin.md)</span><span class="sxs-lookup"><span data-stu-id="89d75-143">If you're having trouble posting jobs to LinkedIn, see [Troubleshoot posting jobs to LinkedIn](./attract-troubleshoot-linkedin.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89d75-144">Lásd még</span><span class="sxs-lookup"><span data-stu-id="89d75-144">See also</span></span>

[<span data-ttu-id="89d75-145">LinkedIn GYIK</span><span class="sxs-lookup"><span data-stu-id="89d75-145">LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="89d75-146">A LinkedIn integrációjának beállítása</span><span class="sxs-lookup"><span data-stu-id="89d75-146">Set up integration with LinkedIn</span></span>](./attract-admin-linkedin.md)

[<span data-ttu-id="89d75-147">Állások létrehozása</span><span class="sxs-lookup"><span data-stu-id="89d75-147">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="89d75-148">Jelöltek felkutatása a LinkedIn Recruiter segítségével</span><span class="sxs-lookup"><span data-stu-id="89d75-148">Source candidates with LinkedIn Recruiter</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="89d75-149">A LinkedIn integrációjának hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="89d75-149">Troubleshoot integration with LinkedIn</span></span>](./attract-troubleshoot-linkedin.md)
