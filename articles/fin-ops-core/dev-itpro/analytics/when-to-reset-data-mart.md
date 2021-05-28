---
title: Mikor kell alaphelyzetbe állítani az adatpiacot?
description: Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók és azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988992"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="12670-103">Mikor kell alaphelyzetbe állítani az adatpiacot?</span><span class="sxs-lookup"><span data-stu-id="12670-103">When to reset a data mart</span></span>

<span data-ttu-id="12670-104">Az adatpiac alaphelyzetbe állítása sok időt vehet igénybe.</span><span class="sxs-lookup"><span data-stu-id="12670-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="12670-105">A körülményektől függően előfordulhat, hogy ez a művelet nem a szükséges megoldás.</span><span class="sxs-lookup"><span data-stu-id="12670-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="12670-106">Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók, valamint azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.</span><span class="sxs-lookup"><span data-stu-id="12670-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a><span data-ttu-id="12670-107">Mikor kell alaphelyzetbe állítanom az adatpiacot?</span><span class="sxs-lookup"><span data-stu-id="12670-107">When do I need to do a data mart reset?</span></span>
<span data-ttu-id="12670-108">Az adatpiac alaphelyzetbe állítása előtt vegye figyelembe a következő kérdéseket.</span><span class="sxs-lookup"><span data-stu-id="12670-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="12670-109">Ha egy vagy több kérdésre igen a válasz, azt jelezheti, hogy a szervezet számára előnyös lehet az adatpiac alaphelyzetbe állítása.</span><span class="sxs-lookup"><span data-stu-id="12670-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="12670-110">Az alkalmazás-adatbázis vissza lett állítva?</span><span class="sxs-lookup"><span data-stu-id="12670-110">Was the application database restored?</span></span>
- <span data-ttu-id="12670-111">Ha egy támogatási eseményt nyitott meg, és egy ügyfélszolgálati szakértő arra utasítja, hogy állítsa vissza az adatpiacot egy hibaelhárítási lépés részeként?</span><span class="sxs-lookup"><span data-stu-id="12670-111">If you've opened a support incident that and a support engineer has instructed you to reset the data mart as part of a troubleshooting step?</span></span>
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="12670-112">Mikor nem célszerű alaphelyzetbe állítani az adatpiacot?</span><span class="sxs-lookup"><span data-stu-id="12670-112">When is it not appropriate to reset a data mart?</span></span>
<span data-ttu-id="12670-113">Bizonyos körülmények között nem ajánljuk az adatpiac alaphelyzetbe állítását.</span><span class="sxs-lookup"><span data-stu-id="12670-113">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="12670-114">Ezek közé tartoznak a következők.</span><span class="sxs-lookup"><span data-stu-id="12670-114">These include the following.</span></span> 

- <span data-ttu-id="12670-115">Adatszinkronizáláshoz kapcsolódó teljesítményproblémákat tapasztal.</span><span class="sxs-lookup"><span data-stu-id="12670-115">You're experiencing performance issues that are associated with a data sync.</span></span> 
- <span data-ttu-id="12670-116">Ha a következő okok valamelyike miatt ismétlődik az alaphelyzetbe állítás:</span><span class="sxs-lookup"><span data-stu-id="12670-116">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="12670-117">**Hiányzó adatok**</span><span class="sxs-lookup"><span data-stu-id="12670-117">**Missing data**</span></span> 
  - <span data-ttu-id="12670-118">**Elakadt integrációs állapot**</span><span class="sxs-lookup"><span data-stu-id="12670-118">**Stuck integration state**</span></span> 
  - <span data-ttu-id="12670-119">**Elavult rekordok** – Az elavult rekordok önmagukban nem feltétlenül igazolják az adatpiac alaphelyzetbe állítását.</span><span class="sxs-lookup"><span data-stu-id="12670-119">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="12670-120">Ha nagy adathalmaz van beállítva, az alaphelyzetbe állítási folyamat futása időt fog igénybe venni, de nem valószínű, hogy ez javulást eredményez.</span><span class="sxs-lookup"><span data-stu-id="12670-120">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="12670-121">Mit jelent az adatpiac alaphelyzetbe állítása?</span><span class="sxs-lookup"><span data-stu-id="12670-121">What is a data mart reset?</span></span>
- <span data-ttu-id="12670-122">A visszaállítás csak akkor indul el, ha a meglévő feladatok befejeződnek.</span><span class="sxs-lookup"><span data-stu-id="12670-122">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="12670-123">Így garantálható, hogy a régi adatok nem lesznek beillesztve.</span><span class="sxs-lookup"><span data-stu-id="12670-123">This ensures that old data is not inserted.</span></span> <span data-ttu-id="12670-124">Ezen a ponton olyan üzenetet láthat, mint például: "Az adatpiac visszaállítását egy aktív feladat miatt nem sikerült feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="12670-124">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="12670-125">Próbálkozzon újra később."</span><span class="sxs-lookup"><span data-stu-id="12670-125">Please try again later.”</span></span>
- <span data-ttu-id="12670-126">A visszaállítás letiltja az integrációs feladatokat, és törli az adatpiac összes adatát.</span><span class="sxs-lookup"><span data-stu-id="12670-126">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="12670-127">Az integráció újra engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="12670-127">The integration is re-enabled.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="12670-128">Ha alaphelyzetbe állítom az adatpiacot, elvesznek a már megtervezett jelentések?</span><span class="sxs-lookup"><span data-stu-id="12670-128">If I reset the data mart, will I lose reports that I've already designed?</span></span> 
<span data-ttu-id="12670-129">Nem, a jelentések SQL-táblákban vannak tárolva, és az adatpiac alaphelyzetbe állítása nem befolyásolja őket.</span><span class="sxs-lookup"><span data-stu-id="12670-129">No, your reports are stored in SQL tables that are not impacted by a reset of the data mart.</span></span> <span data-ttu-id="12670-130">Ha aggódik a megtervezett jelentések elvesztése miatt, készíthet biztonsági jelentést a megőrizni kívánt tervekről.</span><span class="sxs-lookup"><span data-stu-id="12670-130">If you are concerned about losing any reports you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="12670-131">A biztonsági mentéshez nyissa meg a Jelentéstervezőt, és nyissa meg a **Vállalat > Vállalatok > Építőelemek > Exportálás** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="12670-131">To back them up, open Report Designer and go to **Company > Companies > Building Blocks > Export**.</span></span>
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a><span data-ttu-id="12670-132">Szükséges, hogy minden felhasználó kilépjen a rendszerből az adatpiac alaphelyzetbe állításához?</span><span class="sxs-lookup"><span data-stu-id="12670-132">Is it necessary for all users to exit the system to reset the data mart?</span></span>
<span data-ttu-id="12670-133">Nem, a felhasználók továbbra is dolgoznak a rendszerben az adatpiac alaphelyzetbe állítása során.</span><span class="sxs-lookup"><span data-stu-id="12670-133">No, users can continue working in the system during the data mart reset.</span></span> <span data-ttu-id="12670-134">Nem férhetnek azonban hozzá a Pénzügyi jelentés alkalmazással létrehozott jelentésekhez, amíg be nem fejeződik az alaphelyzetbe állítás.</span><span class="sxs-lookup"><span data-stu-id="12670-134">However, they won’t be able to access any reports that were created with Financial Reporter until the reset is finished.</span></span> 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
