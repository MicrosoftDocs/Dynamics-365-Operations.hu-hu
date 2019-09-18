---
title: A LinkedIn és a Microsoft Dynamics 365 for Talent - Attract közötti integráció hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet elhárítani a hibákat, amikor megpróbál állást feladni a LinkedIn felületére a Microsoft Dynamics 365 for Talent - Attract megoldásból.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 82ba7c505ba09e47f3c517c74c22e6aef7cd4e65
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739357"
---
# <a name="troubleshoot-integration-with-linkedin"></a><span data-ttu-id="34871-103">A LinkedIn integrációjának hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="34871-103">Troubleshoot integration with LinkedIn</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34871-104">A következő információk segítségével elháríthatja azokat a problémákat, amelyek akkor merülnek fel, amikor a LinkedIn felületére próbál állásokat feltenni a Microsoft Dynamics 365 for Talent Attract megoldásból.</span><span class="sxs-lookup"><span data-stu-id="34871-104">Use the following information to help troubleshoot issues that you might have when you try to post jobs to LinkedIn from Microsoft Dynamics 365 for Talent: Attract.</span></span>

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a><span data-ttu-id="34871-105">Nem lehet bejelentkezni a LinkedIn rendszerbe az Attract megoldásból</span><span class="sxs-lookup"><span data-stu-id="34871-105">You can't sign in to LinkedIn from Attract</span></span>

<span data-ttu-id="34871-106">Ha nem sikerül bejelentkeznie a LinkedIn webhelyre az Attract megoldásból, próbálja meg ezeket a lépéseket:</span><span class="sxs-lookup"><span data-stu-id="34871-106">If you're having trouble signing in to LinkedIn from Attract, try these steps:</span></span>

1. <span data-ttu-id="34871-107">Győződjön meg róla, hogy az Attract megoldásban megadott LinkedIn hitelesítő adatok érvényesek és helyesek.</span><span class="sxs-lookup"><span data-stu-id="34871-107">Verify that the LinkedIn credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="34871-108">Ha a hitelesítő adatok érvényesek és helyesek forduljon a [LinkedIn támogatáshoz](https://www.linkedin.com/help/linkedin).</span><span class="sxs-lookup"><span data-stu-id="34871-108">If the credentials are valid and correct, contact [LinkedIn support](https://www.linkedin.com/help/linkedin).</span></span>
3. <span data-ttu-id="34871-109">Ha a probléma továbbra is fennáll, forduljon [Microsoft támogatáshoz](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="34871-109">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a><span data-ttu-id="34871-110">Az Attract állásai nem jelennek meg a LinkedIn felületén</span><span class="sxs-lookup"><span data-stu-id="34871-110">Job posts from Attract don't appear on LinkedIn</span></span>

<span data-ttu-id="34871-111">Ha az állás 24 órelt eltével nem jelent meg a LinkedIn felületén, próbálja meg ezeket a lépéseket:</span><span class="sxs-lookup"><span data-stu-id="34871-111">If your job hasn't appeared on LinkedIn after 24 hours, try these steps:</span></span>

1. <span data-ttu-id="34871-112">Győződjön meg róla, hogy a LinkedIn vállalat azonosítója a LinkedIn vállalati oldalhoz hozzárendelve, és helyesen van megadva az Attract felügyeleti központjában.</span><span class="sxs-lookup"><span data-stu-id="34871-112">Make sure that your LinkedIn Company ID maps to your LinkedIn company page and is correctly entered in the Attract Admin center.</span></span> <span data-ttu-id="34871-113">A LinkedIn beállításainak az adminisztrációs központban történő módosításáról a következő témakör tartalmaz további tájékoztatást [A LinkedIn integrációjának beállítása](attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="34871-113">For more information about how to change LinkedIn settings in the Admin center, see [Set up integration with LinkedIn](attract-admin-linkedin.md).</span></span> <span data-ttu-id="34871-114">A LinkedIn vállalati azonosíótval kapcsolatos további tudnivalókat lásd [A LinkedIn vállalati azonosítójának társítása a LinkedIn Job Boarddal - Gyakran ismételt kérdések](https://www.linkedin.com/help/linkedin/answer/98972).</span><span class="sxs-lookup"><span data-stu-id="34871-114">For more information about LinkedIn Company IDs, see [Associating your LinkedIn Company ID with the LinkedIn Job Board - Frequently Asked Questions](https://www.linkedin.com/help/linkedin/answer/98972).</span></span>
2. <span data-ttu-id="34871-115">Ellenőrizze az állás adatait a LinkedIn felületén, és győződjön meg arról, hogy a cím teljes.</span><span class="sxs-lookup"><span data-stu-id="34871-115">Check the job details on LinkedIn to make sure that the address is complete.</span></span> <span data-ttu-id="34871-116">Az állások sikeres feladásához a LinkedIn szolgáltatásnak legalább az állás városát és országát vagy régióját meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="34871-116">To post a job successfully, LinkedIn needs at least the city and country or region of the job.</span></span>
3. <span data-ttu-id="34871-117">Győződjön meg róla, hogy az állás nem egy másik állás másolata , amely fel van adva a LinkedIn felületére.</span><span class="sxs-lookup"><span data-stu-id="34871-117">Make sure that the job doesn't duplicate another job that has been posted on LinkedIn.</span></span> <span data-ttu-id="34871-118">A LinkedIn nem fog olyan állásokat feladni, amelyek egy LinkedIn Premium Job Slot vagy Limited Listing másolatai egy másik forrásból.</span><span class="sxs-lookup"><span data-stu-id="34871-118">LinkedIn won't post jobs that are duplicates of either LinkedIn Premium Job Slots or Limited Listings from another source.</span></span> <span data-ttu-id="34871-119">Győződjön meg róla, hogy a vállalat egy másik munkatársa már nem adta fel manuálisan az állást.</span><span class="sxs-lookup"><span data-stu-id="34871-119">Verify that another person at your company didn't already post the job manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="34871-120">Lásd még</span><span class="sxs-lookup"><span data-stu-id="34871-120">See also</span></span>

[<span data-ttu-id="34871-121">LinkedIn GYIK</span><span class="sxs-lookup"><span data-stu-id="34871-121">LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="34871-122">Állások feladása a LinkedIn felületére az Attract szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="34871-122">Post jobs to LinkedIn from Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="34871-123">Jelöltek felkutatása a LinkedIn Recruiter segítségével</span><span class="sxs-lookup"><span data-stu-id="34871-123">Source candidates with LinkedIn Recruiter</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="34871-124">Állások létrehozása</span><span class="sxs-lookup"><span data-stu-id="34871-124">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="34871-125">A LinkedIn integrációjának hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="34871-125">Troubleshoot integration with LinkedIn</span></span>](./attract-troubleshoot-linkedin.md)
