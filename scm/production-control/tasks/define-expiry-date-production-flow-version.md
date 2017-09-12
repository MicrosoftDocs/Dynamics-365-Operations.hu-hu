--- 
title: "Lejárati dátum megadása termék folyamatverziójához"
description: "Egy termelésifolyamat-verzió érvényességének és feldolgozásának befejezéséhez egy adott időpontban, vagy egy aktív verzió új verzióra cserélésének tervezéséhez, be kell állítani a verzió lejárati idejét."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6fabeb31720a60bf97d08dabf8ed87ac6af7cbf7
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="2fa6c-103">Lejárati dátum megadása termék folyamatverziójához</span><span class="sxs-lookup"><span data-stu-id="2fa6c-103">Define an expiry date for a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2fa6c-104">Egy termelésifolyamat-verzió érvényességének és feldolgozásának befejezéséhez egy adott időpontban, vagy egy aktív verzió új verzióra cserélésének tervezéséhez, be kell állítani a verzió lejárati idejét.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="2fa6c-105">Nincs szükség a verzió inaktiválására.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="2fa6c-106">Állítson be egy lejárati dátumot a termelésifolyamat-verzió befejezéséhez</span><span class="sxs-lookup"><span data-stu-id="2fa6c-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="2fa6c-107">Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="2fa6c-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2fa6c-109">Válassza ki bármelyik termelési folyamatot, amelyiknek már van definiált verziója.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="2fa6c-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="2fa6c-111">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-111">Click Edit.</span></span>
5. <span data-ttu-id="2fa6c-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="2fa6c-113">Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="2fa6c-114">A lejárati dátumon nem indul el és nem lesz aktiválva új verzió.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="2fa6c-115">Emellett már nem lehet létrehozni vagy elindítani feladatokat a termelési folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="2fa6c-116">Az elindított feladatok a lejárati dátum után is befejezhetők.</span><span class="sxs-lookup"><span data-stu-id="2fa6c-116">You can still complete started jobs after the expiration date.</span></span>  


