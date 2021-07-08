---
title: Főkönyvi naptár módosítása vagy újbóli hozzárendelése
description: Ez a témakör ismerteti, hogyan módosíthatja a főkönyvhöz aktuálisan hozzárendelt naptárat, és hogyan rendelhet új naptárat a főkönyvhöz.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 052b8944c0a015187d1d7c4ba3db878c52faeeea
ms.sourcegitcommit: 905a8c7a0c1bc06ada2acfba913dfe5f7b44ea16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/14/2021
ms.locfileid: "6039950"
---
# <a name="change-or-reassign-a-ledger-calendar"></a><span data-ttu-id="4fe43-103">Főkönyvi naptár módosítása vagy újbóli hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="4fe43-103">Change or reassign a ledger calendar</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4fe43-104">Ez a témakör ismerteti, hogyan módosíthatja a főkönyvhöz aktuálisan hozzárendelt naptárat, és hogyan rendelhet új naptárat a főkönyvhöz.</span><span class="sxs-lookup"><span data-stu-id="4fe43-104">This topic explains how to change the calendar that is currently assigned to a ledger, and how to assign a new calendar to the ledger.</span></span>

## <a name="issue"></a><span data-ttu-id="4fe43-105">Probléma</span><span class="sxs-lookup"><span data-stu-id="4fe43-105">Issue</span></span>

<span data-ttu-id="4fe43-106">Bizonyos esetekben a vállalatoknak vagy módosítaniuk kell a főkönyvhöz rendelt meglévő naptárat, vagy új naptárat kell hozzárendelniük.</span><span class="sxs-lookup"><span data-stu-id="4fe43-106">Sometime, companies must either change the existing calendar that is assigned to a ledger or assign a new calendar.</span></span>

## <a name="resolution"></a><span data-ttu-id="4fe43-107">Megoldás</span><span class="sxs-lookup"><span data-stu-id="4fe43-107">Resolution</span></span>

<span data-ttu-id="4fe43-108">A főkönyvi naptár módosítására vagy új naptár hozzárendelésére két forgatókönyv létezik.</span><span class="sxs-lookup"><span data-stu-id="4fe43-108">There are two scenarios for changing or reassigning a ledger calendar.</span></span> <span data-ttu-id="4fe43-109">Az első forgatókönyv egy meglévő naptár módosítását fedi le, amely már hozzá van rendelve van a főkönyvhöz.</span><span class="sxs-lookup"><span data-stu-id="4fe43-109">The first scenario involves changing an existing calendar that is already assigned to the ledger.</span></span> <span data-ttu-id="4fe43-110">A második forgatókönyvben egy új naptár létrehozása szerepel, amelyet a főkönyvhöz rendelnek.</span><span class="sxs-lookup"><span data-stu-id="4fe43-110">The second scenario involves creating a new calendar and assigning it to the ledger.</span></span> <span data-ttu-id="4fe43-111">Mindkét módosítás bármikor elvégezhető, még akkor is, ha a tranzakciókat már feladták a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="4fe43-111">Both changes can be done at any time, even after transactions have been posted to the ledger.</span></span>

### <a name="change-an-existing-fiscal-calendar"></a><span data-ttu-id="4fe43-112">Meglévő pénzügyi naptár módosítása</span><span class="sxs-lookup"><span data-stu-id="4fe43-112">Change an existing fiscal calendar</span></span>

<span data-ttu-id="4fe43-113">Ha módosítani szeretné a főkönyvhöz már hozzárendelt naptárat, lépjen a **Főkönyv \> Főkönyv beállítása \> Főkönyv** menüpontba, és válassza ki a pénzügyi naptár hivatkozását a **Főkönyvi naptárak** oldal megnyitáshoz.</span><span class="sxs-lookup"><span data-stu-id="4fe43-113">To change an existing calendar that is assigned to your ledger, go to **General ledger \> Ledger setup \> Ledger**, and select the link for the fiscal calendar to open the **Ledger calendars** page.</span></span>

<span data-ttu-id="4fe43-114">Azonban a naptár lehetséges módosításainak vannak korlátai.</span><span class="sxs-lookup"><span data-stu-id="4fe43-114">There are limits to the changes that can be made to a calendar.</span></span> <span data-ttu-id="4fe43-115">Például módosíthatja az *időszakok* kezdő és záró dátumait egy éven belül, de nem módosíthatja egy *év* kezdő és záró dátumait a naptárban.</span><span class="sxs-lookup"><span data-stu-id="4fe43-115">For example, you can change the start and end dates of the *periods* in a year, but you can't change the start and end dates of a *year* in the calendar.</span></span>

<span data-ttu-id="4fe43-116">Az adott év időszakainak módosításához válassza ki a megfelelő naptárat és évet.</span><span class="sxs-lookup"><span data-stu-id="4fe43-116">To change the periods in a year, select the appropriate calendar and year.</span></span> <span data-ttu-id="4fe43-117">Első lépésként az **Időszak törlése** gombbal törölje ki a meglévő üzemeltetési időszakok némelyikét vagy mindegyikét.</span><span class="sxs-lookup"><span data-stu-id="4fe43-117">First, use the use the **Delete period** button to delete some or all of the existing operating periods.</span></span> <span data-ttu-id="4fe43-118">Az első kivételével az összes üzemeltetési időszak törölhető.</span><span class="sxs-lookup"><span data-stu-id="4fe43-118">All operating periods except the first can be deleted.</span></span> <span data-ttu-id="4fe43-119">Ezután az **Időszak felosztása** gombbal feloszthatja a fennmaradó időszakot vagy időszakokat új időszakokra a következő időszak megfelelő kezdő dátumának megadásával.</span><span class="sxs-lookup"><span data-stu-id="4fe43-119">Then use the **Divide period** button to divide the remaining period or periods into new periods by entering an appropriate start date for the next period.</span></span>

<span data-ttu-id="4fe43-120">Miután módosította a naptárban lévő időszakokat, le kell futtatnia a **Főkönyvi időszakok újraszámítása** folyamatot minden jogi személyben (vállalatban), amelyhez a naptár hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="4fe43-120">After you change the periods in a calendar, you must run the **Recalculate ledger periods** process in every legal entity (company) that the calendar is assigned to.</span></span> <span data-ttu-id="4fe43-121">Bár nem jelenik meg figyelmeztető üzenet, hogy erre a lépésre emlékeztesse, az újraszámítási folyamat elvégzése szükséges az időszak frissítéséhez, amely az egyes feladott tranzakciókhoz van hozzárendelve a Főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="4fe43-121">Although no warning message reminds you to complete this step, the recalculation process is required to update the period that is assigned to each posted transaction in General ledger.</span></span> <span data-ttu-id="4fe43-122">Az újraszámítási folyamat futtatásához válassza a **Főkönyvi időszakok újraszámítása** lehetőséget az egyes vállalatok **Főkönyv beállítása** oldalán.</span><span class="sxs-lookup"><span data-stu-id="4fe43-122">To run the recalculation process, select **Recalculate ledger periods** on the **Ledger setup** page in each company.</span></span>

<span data-ttu-id="4fe43-123">Ha az újraszámítási folyamatot nem futtatják le, előfordulhat, hogy a főkönyvi kivonaton vagy a pénzügyi kimutatásokon szereplő tranzakcióegyenlegek helytelenül szerepelnek az időszakokban.</span><span class="sxs-lookup"><span data-stu-id="4fe43-123">If the recalculation process isn't run, transaction balances on a trial balance or on financial statements might be incorrectly included in periods.</span></span> <span data-ttu-id="4fe43-124">Ebben az esetben az újraszámítási folyamat futtatásával bármikor helyesbítheti az egyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="4fe43-124">In this case, you can correct the balances at any time by running the recalculation process.</span></span>

### <a name="assign-a-new-fiscal-calendar"></a><span data-ttu-id="4fe43-125">Új pénzügyi naptár hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="4fe43-125">Assign a new fiscal calendar</span></span>

<span data-ttu-id="4fe43-126">Új pénzügyi naptár hozzárendeléséhez lépjen a **Főkönyv \> Főkönyv beállítása \> Főkönyv** menüpontra, és válassza a **Szerkesztés** lehetőséget, amellyel a **Főkönyv** oldal szerkesztési módba lép.</span><span class="sxs-lookup"><span data-stu-id="4fe43-126">To assign a new fiscal calendar, go to **General ledger \> Ledger setup \> Ledger**, and select **Edit** to put the **Ledger** page into edit mode.</span></span> <span data-ttu-id="4fe43-127">Ezután a **Pénzügyi naptár** mezőben válasszon új pénzügyi naptárat.</span><span class="sxs-lookup"><span data-stu-id="4fe43-127">Then, in the **Fiscal calendar** field, select a new fiscal calendar.</span></span>

<span data-ttu-id="4fe43-128">Miután módosította a főkönyv pénzügyi naptárát, futtatnia kell a **Főkönyvi időszakok újraszámítása** folyamatot.</span><span class="sxs-lookup"><span data-stu-id="4fe43-128">After you change the fiscal calendar for a ledger, you must run the **Recalculate ledger periods**.</span></span> <span data-ttu-id="4fe43-129">Ha új pénzügyi naptárat rendel a főkönyvhöz, egy üzenet emlékezteti a lépés végrehajtására.</span><span class="sxs-lookup"><span data-stu-id="4fe43-129">When you assign a new fiscal calendar to a ledger, a message reminds you to complete this step.</span></span> <span data-ttu-id="4fe43-130">Bár az üzenetből úgy tűnhet, hogy az újraszámítási folyamat nem kötelező, valójában az.</span><span class="sxs-lookup"><span data-stu-id="4fe43-130">Although the message might seem to indicate that the recalculation process is optional, it isn't.</span></span> <span data-ttu-id="4fe43-131">Kötelező frissítenie azt az időszakot, amelyet hozzárendelt az egyes feladott tranzakciókhoz a Főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="4fe43-131">It's required to update the period that is assigned to each posted transaction in General ledger.</span></span> <span data-ttu-id="4fe43-132">Az újraszámítási folyamat futtatásához válassza a **Főkönyvi időszakok újraszámítása** lehetőséget a **Főkönyv beállítása** oldalon.</span><span class="sxs-lookup"><span data-stu-id="4fe43-132">To run the recalculation process, select **Recalculate ledger periods** on the **Ledger setup** page.</span></span>

<span data-ttu-id="4fe43-133">Ha az újraszámítási folyamatot nem futtatják le, előfordulhat, hogy a főkönyvi kivonaton vagy a pénzügyi kimutatásokon szereplő tranzakcióegyenlegek helytelenül szerepelnek az időszakokban.</span><span class="sxs-lookup"><span data-stu-id="4fe43-133">If the recalculation process isn't run, transaction balances on a trial balance or on financial statements might be incorrectly included in periods.</span></span> <span data-ttu-id="4fe43-134">Ebben az esetben az újraszámítási folyamat futtatásával bármikor helyesbítheti az egyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="4fe43-134">In this case, you can correct the balances at any time by running the recalculation process.</span></span>