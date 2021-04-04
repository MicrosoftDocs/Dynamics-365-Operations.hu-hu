---
title: Mikor kell alaphelyzetbe állítani az adatpiacot?
description: Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók és azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71324d4aa2d20dd6ae4729412a017d130ab0144f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563732"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="9bb2f-103">Mikor kell alaphelyzetbe állítani az adatpiacot?</span><span class="sxs-lookup"><span data-stu-id="9bb2f-103">When to reset a data mart</span></span>

<span data-ttu-id="9bb2f-104">Az adatpiac alaphelyzetbe állítása sok időt vehet igénybe.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="9bb2f-105">A körülményektől függően előfordulhat, hogy ez a művelet nem a szükséges megoldás.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="9bb2f-106">Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók, valamint azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a><span data-ttu-id="9bb2f-107">Mikor kell alaphelyzetbe állítani az adatpiacot?</span><span class="sxs-lookup"><span data-stu-id="9bb2f-107">When do you need to do a data mart reset?</span></span>
<span data-ttu-id="9bb2f-108">Az adatpiac alaphelyzetbe állítása előtt vegye figyelembe a következő kérdéseket.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="9bb2f-109">Ha egy vagy több kérdésre igen a válasz, azt jelezheti, hogy a szervezet számára előnyös lehet az adatpiac alaphelyzetbe állítása.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="9bb2f-110">Az alkalmazás adatbázisát visszaállították, de az adatpiac adatbázis visszaállítására nem került sor.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-110">The application database was restored, but the data mart database was not restored.</span></span>
- <span data-ttu-id="9bb2f-111">Helytelen adatok láthatók egy könyvelési időszaknál, ami nem a jelentéstervvel kapcsolatos probléma eredménye.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-111">You see incorrect data for an accounting period, which isn't the result of an issue with the report design.</span></span>
- <span data-ttu-id="9bb2f-112">Egy könyvelési időszaknál helytelen adatok láthatók, és a rekordok a Jelentéstervező **Integrációs kísérletek** lapján vannak felsorolva (indítsa el a Jelentéstervezőt, és válassza ki az **Eszközök > Integráció állapota** lehetőséget).</span><span class="sxs-lookup"><span data-stu-id="9bb2f-112">You see incorrect data for an accounting period, and records are listed under Integration attempts on the **Integration status** page in Report Designer (start the Report Designer and select **Tools > Integration status**).</span></span>
- <span data-ttu-id="9bb2f-113">Egy támogatási eseményt nyitott meg, és egy ügyfélszolgálati szakértő arra utasítja, hogy állítsa vissza az adatpiacot egy hibaelhárítási lépés részeként.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-113">You've opened a support incident and a support engineer has instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="9bb2f-114">Mikor nem célszerű alaphelyzetbe állítani az adatpiacot?</span><span class="sxs-lookup"><span data-stu-id="9bb2f-114">When it's not appropriate to reset a data mart?</span></span>
<span data-ttu-id="9bb2f-115">Bizonyos körülmények között nem ajánljuk az adatpiac alaphelyzetbe állítását.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-115">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="9bb2f-116">Ezek közé tartoznak a következők.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-116">These include the following.</span></span> 

- <span data-ttu-id="9bb2f-117">Bármikor, amikor az ok nem szerepel ebben a témakörben.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-117">Anytime the reason isn’t listed in this topic.</span></span>
- <span data-ttu-id="9bb2f-118">Adatszinkronizálással összefüggő teljesítményproblémákat tapasztal. Ebben a helyzetben az adatpiac alaphelyzetbe állítása valószínűleg nem segít.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-118">You're experiencing performance issues that are associated with a data sync. In this circumstance, resetting the data mart probably won't help.</span></span>
- <span data-ttu-id="9bb2f-119">Ha a következő okok valamelyike miatt ismétlődik az alaphelyzetbe állítás:</span><span class="sxs-lookup"><span data-stu-id="9bb2f-119">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="9bb2f-120">**Hiányzó adatok** – Először küszöbölje ki a jelentésterv-problémákat és az adatszinkronizálási időmérési problémákat, például figyelje meg, hogy a hiányzó adatok feladása óta nem futott a ténytérkép.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-120">**Missing data** - First, eliminate report design issues and data sync timing issues, for example, you observe that the fact map hasn’t run since missing data was posted.</span></span>
  - <span data-ttu-id="9bb2f-121">**Elakadt integrációs állapot** – Ha az integráció lassú vagy úgy tűnik, hogy elakadt, akkor nem valószínű, hogy az adatpiac alaphelyzetbe állítása oldja meg a problémát.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-121">**Stuck integration state** - If the integration is slow or seems stuck, resetting the data mart is unlikely to resolve the issue.</span></span>
  - <span data-ttu-id="9bb2f-122">**Az alaphelyzetbe állítási kísérletek sikertelenek voltak** – Ha az adatok visszaállítását több ízben is megpróbálta, és azok a hiányzó adatok miatt sikertelenek voltak, akkor javasoljuk, hogy nyissa meg a támogatási eseményt, és egy ügyfélszolgálati szakemberrel együtt elemezze az adott helyzetet, és csak ezt követően próbálja meg újból alaphelyzetbe állítani az adatpiacot.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-122">**Attempts to reset have been unsuccessful** - If a number of attempts to complete a reset have been made, and have been unsuccessful because of missing data, we recommend opening a support incident and working with a support engineer to analyze your situation before attempting to reset the data mart again.</span></span>
  - <span data-ttu-id="9bb2f-123">**Elavult rekordok** – Az elavult rekordok önmagukban nem feltétlenül igazolják az adatpiac alaphelyzetbe állítását.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-123">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="9bb2f-124">Ha nagy adathalmaz van beállítva, az alaphelyzetbe állítási folyamat futása időt fog igénybe venni, de nem valószínű, hogy ez javulást eredményez.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-124">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-a-data-mart-reset-does-not-do"></a><span data-ttu-id="9bb2f-125">Amire az adatpiac alaphelyzetbe állítása nem alkalmas</span><span class="sxs-lookup"><span data-stu-id="9bb2f-125">What a data mart reset does not do</span></span>  
- <span data-ttu-id="9bb2f-126">A visszaállítás csak akkor indul el, ha a meglévő feladatok befejeződnek.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-126">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="9bb2f-127">Így garantálható, hogy a régi adatok nem lesznek beillesztve.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-127">This ensures that old data is not inserted.</span></span> <span data-ttu-id="9bb2f-128">Ezen a ponton olyan üzenetet láthat, mint például: "Az adatpiac visszaállítását egy aktív feladat miatt nem sikerült feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-128">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="9bb2f-129">Próbálkozzon újra később."</span><span class="sxs-lookup"><span data-stu-id="9bb2f-129">Please try again later.”</span></span>
- <span data-ttu-id="9bb2f-130">A visszaállítás letiltja az integrációs feladatokat, és törli az adatpiac összes adatát.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-130">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="9bb2f-131">Az integráció újra engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-131">The integration is re-enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="9bb2f-132">A következő pontok két olyan dolgot határoznak meg, amelyek *nem* érhetők el az adatpiac alaphelyzetbe állításával.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-132">The following points specify two things that resetting a data mart will *not* do.</span></span> <br>
> - <span data-ttu-id="9bb2f-133">A alaphelyzetbe állítások nem törlik a jelentésterveket.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-133">Resets do not clear report designs.</span></span> <br>
> - <span data-ttu-id="9bb2f-134">Az alaphelyzetbe állítás csak akkor törli a vállalati vagy a felhasználói adatokat, ha be vannak jelölve.</span><span class="sxs-lookup"><span data-stu-id="9bb2f-134">Resets do not clear company data or user data unless selected.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]