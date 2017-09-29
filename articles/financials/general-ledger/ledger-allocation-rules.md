---
title: "Főkönyvi felosztási szabályok"
description: "Ez a cikk a főkönyvi felosztási szabályokkal kapcsolatos információkat tartalmaz. Leírja az ezen felosztási szabályok különböző összetevőit, és a hozzájuk használható felosztási módszereket."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 87b98811dabb6a8593cd4a75ad9c5a028f653867
ms.contentlocale: hu-hu
ms.lasthandoff: 06/29/2017


---

# <a name="ledger-allocation-rules"></a><span data-ttu-id="08732-104">Főkönyvi felosztási szabályok</span><span class="sxs-lookup"><span data-stu-id="08732-104">Ledger allocation rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="08732-105">Ez a cikk a főkönyvi felosztási szabályokkal kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="08732-105">This article provides information about ledger allocation rules.</span></span> <span data-ttu-id="08732-106">Leírja az ezen felosztási szabályok különböző összetevőit, és a hozzájuk használható felosztási módszereket.</span><span class="sxs-lookup"><span data-stu-id="08732-106">It describes the various components of these allocation rules and the allocation methods that can be used for them.</span></span>

<span data-ttu-id="08732-107">Főkönyvi felosztási szabályok segítségével automatikusan kiszámítsa és a felosztási naplók és főkönyvi egyenlegek vagy rögzített összegek felosztásának számlabejegyzések létrehozása.</span><span class="sxs-lookup"><span data-stu-id="08732-107">Ledger allocation rules are used to automatically calculate and generate allocation journals and account entries for the allocation of ledger balances or fixed amounts.</span></span> <span data-ttu-id="08732-108">Felosztási módszert is lehet, változó vagy állandó.</span><span class="sxs-lookup"><span data-stu-id="08732-108">Allocation methods can be variable or fixed.</span></span> <span data-ttu-id="08732-109">Az alábbi felosztási módok Főkönyvi felosztási szabályok használható:</span><span class="sxs-lookup"><span data-stu-id="08732-109">The following allocation methods can be used for ledger allocation rules:</span></span>

-   <span data-ttu-id="08732-110">**Alap** – a változó módszert használják, ha a felosztás attól függ, a tényleges főkönyvi egyenleg, a szűrési feltételek alapján.</span><span class="sxs-lookup"><span data-stu-id="08732-110">**Basis** – This variable method is used when the allocation depends on the actual ledger balance, based on filter criteria.</span></span> <span data-ttu-id="08732-111">Például a vállalat hirdetési kiadásait feloszthatja az egyes részlegeknek az összes értékesítéshez képest produkált értékesítésének arányában.</span><span class="sxs-lookup"><span data-stu-id="08732-111">For example, advertising expenses can be allocated based on each department's sales in proportion to the total departmental sales.</span></span>
-   <span data-ttu-id="08732-112">**Rögzített százalék** és **Fix súly** – közvetlenül a szabályhoz meghatározott ezeknek a módszereknek a felosztási százalék vagy súlya.</span><span class="sxs-lookup"><span data-stu-id="08732-112">**Fixed percentage** and **Fixed weight** – For these methods, the allocation percentage or weight is defined directly for the rule.</span></span> <span data-ttu-id="08732-113">Ha például hirdetési költségek lehet felosztani osztály kap a hirdetési kiadások 70 százalékát, és B osztály kap 30 százalékát.</span><span class="sxs-lookup"><span data-stu-id="08732-113">For example, advertising expenses can be allocated so that Department A receives 70 percent of the advertising expense and Department B receives 30 percent.</span></span>
-   <span data-ttu-id="08732-114">**Egyenlő** – Ez a módszer elosztja a összeg egyenlő minden definiált célja.</span><span class="sxs-lookup"><span data-stu-id="08732-114">**Equally** – This method distributes the amount equally to each defined destination.</span></span> <span data-ttu-id="08732-115">Például célok meg vannak adva a szervezeti egység és B osztály, hirdetési kiadások lehet hozzárendelni úgy, osztály, mind a "B" osztály kapja meg a hirdetési kiadások 50%-át.</span><span class="sxs-lookup"><span data-stu-id="08732-115">For example, if destinations are defined for Department A and Department B, advertising expenses can be allocated so that both Department A and Department B receive 50 percent of the advertising expense.</span></span>

<span data-ttu-id="08732-116">Ha egy felosztási szabályhoz az Alap felosztási módszer tartozik, létre kell hoznia egy külön szabályt a főkönyvi felosztás alapjához is.</span><span class="sxs-lookup"><span data-stu-id="08732-116">If Basis is used as the allocation method for an allocation rule, you must also define separate ledger allocation basis rules.</span></span> <span data-ttu-id="08732-117">A „Felosztási kérés feldolgozása” lehetővé teszi, hogy a felhasználók folyamat-a Főkönyvi felosztási szabály feldolgozása, és a létrejövő felosztási napló bejegyzéseinek megtekintése, vagy fel, vagy a számított felosztás törlése előtt.</span><span class="sxs-lookup"><span data-stu-id="08732-117">The "Process allocation request" process lets users process the ledger allocation rule and preview the resulting allocation journal entries before they either post or delete the calculated allocations.</span></span>

## <a name="components-of-ledger-allocation-rules"></a><span data-ttu-id="08732-118">Felosztási szabályok összetevői</span><span class="sxs-lookup"><span data-stu-id="08732-118">Components of ledger allocation rules</span></span>
<span data-ttu-id="08732-119">Minden felosztási szabály négy elsődleges összetevőből áll: általános, forrás, cél, és az ellenszámla.</span><span class="sxs-lookup"><span data-stu-id="08732-119">Each allocation rule has four components: general, source, destination, and offset.</span></span> <span data-ttu-id="08732-120">További alkatrészek, a Főkönyvi felosztási szabályok adatbázisok szükség, ha az Alap az elosztási módszert használja.</span><span class="sxs-lookup"><span data-stu-id="08732-120">An additional component, ledger allocation bases rules, is required if Basis is used as the allocation method.</span></span> <span data-ttu-id="08732-121">Minden egyes összetevő egy kritikus fontosságú eleme szeretné feldolgozni a felosztásokat szükséges információt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="08732-121">Each component provides a critical piece of the information that is required in order to process allocations.</span></span>

-   <span data-ttu-id="08732-122">**Általános** – Az általános összetevő a felhasználó által megadott beállításokat jelenti, többek között a felosztási módszert, a vállalatközi szabálybeállításokat, illetve a szabály aktív vagy nem aktív állapotát.</span><span class="sxs-lookup"><span data-stu-id="08732-122">**General** – This component is where the user specifies options such as the allocation method, intercompany rule settings, and whether the rule is active.</span></span>
-   <span data-ttu-id="08732-123">**Forrás** – ezt az összetevőt, akkor a felhasználó megadhatja a felosztás forrásadatait.</span><span class="sxs-lookup"><span data-stu-id="08732-123">**Source** – This component is where the user specifies the source data for the allocation.</span></span> <span data-ttu-id="08732-124">A felosztás alapulhat főkönyvi egyenlegeken (**Adatforrás** = **Főkönyv**) vagy rögzített összegeken (**Adatforrás** = **Rögzített érték**).</span><span class="sxs-lookup"><span data-stu-id="08732-124">Allocation can be based on ledger balances (**Data source** = **Ledger**) or fixed amounts (**Data source** = **Fixed value**).</span></span> <span data-ttu-id="08732-125">Ha **Adatforrás** értéke **Főkönyvi**, forrás szűrési feltételeket meg kell adni a Főkönyvi felosztási szabály (például a hirdetési költségek).</span><span class="sxs-lookup"><span data-stu-id="08732-125">When **Data source** is set to **Ledger**, source filter criteria must be defined for the ledger allocation rule (for example, for the advertising expenses).</span></span>
-   <span data-ttu-id="08732-126">**Cél** – A cél határozza meg, hogy a felosztási számítás eredményét hogyan kell elosztani a cél felosztási sorai között.</span><span class="sxs-lookup"><span data-stu-id="08732-126">**Destination** – This component defines how the result of the allocation calculation should be distributed and accounted for.</span></span> <span data-ttu-id="08732-127">Például lehet az egyes részlegekhez tartozó cél soronként.</span><span class="sxs-lookup"><span data-stu-id="08732-127">For example, there can be one destination line for each department.</span></span>
-   <span data-ttu-id="08732-128">**Ellenoldal** – ezt az összetevőt határozza meg, hogyan fő számlák és dimenziók érdekében meg kell határozni az ellenoldali bejegyzéseket, amelyek kiegyenlítik a cél bejegyzései.</span><span class="sxs-lookup"><span data-stu-id="08732-128">**Offset** – This component defines how main accounts and dimensions should be determined for the offset entries that balance the destination entries.</span></span> <span data-ttu-id="08732-129">Ezek a bejegyzések általában a forrás oldalán megadott számlák/dimenziók helyében állnak.</span><span class="sxs-lookup"><span data-stu-id="08732-129">User-defined options are typically used instead of accounts and dimensions that are based on the source.</span></span> <span data-ttu-id="08732-130">Ha **Adatforrás** értéke **Rögzített érték**, a **Forrás** lehetőség nem használható.</span><span class="sxs-lookup"><span data-stu-id="08732-130">When **Data source** is set to **Fixed value**, **Source** can't be used as an option.</span></span>
-   <span data-ttu-id="08732-131">**Főkönyvi felosztási alap szabályok** – ezek szabályok saját forrás szűrési feltételek meghatározása, hogy mely főkönyvi egyenlegek használandó felosztási (például a bevétel szerinti beosztásokról) használja.</span><span class="sxs-lookup"><span data-stu-id="08732-131">**Ledger allocation basis rules** – These rules use their own source filter criteria to determine which ledger balances should be used for allocation (for example, the revenue per department).</span></span> <span data-ttu-id="08732-132">Egy felosztási alapszabály több felosztási szabállyal együtt is használható.</span><span class="sxs-lookup"><span data-stu-id="08732-132">Each allocation basis rule can be used with multiple allocation rules.</span></span>





