---
title: "Bankkezelési munkaterület"
description: "Ez a témakör a Bankszámla kezelése munkaterületről nyújt tájékoztatást. Ez a munkaterület olyan információkat jelenít meg, amelyek a vállalati bankszámlákhoz kapcsolódnak, és tartalmaz egy Összefoglaló nézetet és egy Elemzés oldalt. Az Összefoglaló nézet összegző csempéket, bankszámlaadatokat, egyenleget és kapcsolódó adatokat tartalmaz. Az Analytics oldal a Microsoft Power BI funkciói révén vizuálisan megjeleni a bankszámlaegyenlegekkel kapcsolatos információkat."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 63bf043124797b328116fd7951913eaeda6ff97b
ms.openlocfilehash: a090d5deef80260858413fa49011b983c6bf4b20
ms.contentlocale: hu-hu
ms.lasthandoff: 01/12/2018

---
# <a name="bank-management-workspace"></a><span data-ttu-id="2a4a3-106">Bankkezelési munkaterület</span><span class="sxs-lookup"><span data-stu-id="2a4a3-106">Bank management workspace</span></span>

<span data-ttu-id="2a4a3-107">A **Bankszámla kezelése** munkaterület olyan információkat jelenít meg, amelyek a vállalati bankszámlákhoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-107">The **Bank management** workspace shows information that is related to company bank accounts.</span></span> <span data-ttu-id="2a4a3-108">Ez a munkaterület egy **Összefoglaló** nézetet és egy **Elemzés** oldalt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-108">This workspace includes a **Summary** view and an **Analytics** page.</span></span> <span data-ttu-id="2a4a3-109">Az **Összefoglaló** nézet összegző csempéket, bankszámlaadatokat, egyenleget és kapcsolódó adatokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-109">The **Summary** view shows summary tiles, bank account information, a balance chart, and related information.</span></span> <span data-ttu-id="2a4a3-110">Az **Analytics** oldal a Microsoft Power BI funkciói révén vizuálisan megjeleni a bankszámlaegyenlegekkel kapcsolatos információkat.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-110">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to bank account balances.</span></span>

## <a name="summary-view"></a><span data-ttu-id="2a4a3-111">Osszegzésé megtekintése</span><span class="sxs-lookup"><span data-stu-id="2a4a3-111">Summary view</span></span>

### <a name="summary"></a><span data-ttu-id="2a4a3-112">Összegzés</span><span class="sxs-lookup"><span data-stu-id="2a4a3-112">Summary</span></span>

<span data-ttu-id="2a4a3-113">Az **Összefoglaló** szakasz csempéi áttekintést nyújtanak a bankszámláiról, és hozzáférést biztosítanak azokról az oldalakról, amelyeket leggyakrabban kell használnia.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-113">The tiles in the **Summary** section give an overview of your bank accounts and provide quick access to the pages that you most often have to use.</span></span> <span data-ttu-id="2a4a3-114">A banki egyeztetés információi a Haladó banki egyeztetés funkciónál jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-114">The bank reconciliation information is specific to the Advanced bank reconciliation functionality.</span></span> <span data-ttu-id="2a4a3-115">Csak azoknál a bankszámláknál jelennek meg az információk, amelyeknél a **Továbbfejlesztett banki egyeztetés** lehetőség beállítása **Igen** a **Bankszámla** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-115">Information is included only for those bank accounts that have the **Advanced bank reconciliation** option set to **Yes** on the **Bank account** page.</span></span> <span data-ttu-id="2a4a3-116">Az **Összefoglalás** szakaszból importálhatja az elektronikus banki fájlokat mindegyik jogi személy bankszámláira vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-116">From the **Summary** section, you can import electronic bank files for bank accounts across all legal entities.</span></span>

### <a name="bank-accounts"></a><span data-ttu-id="2a4a3-117">Bankszámlák</span><span class="sxs-lookup"><span data-stu-id="2a4a3-117">Bank accounts</span></span>

<span data-ttu-id="2a4a3-118">A jogi személy minden egyes bankszámláját egy kártya jelzi a **Bankszámlák** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-118">Each bank account in the legal entity is represented by a card in the **Bank accounts** section.</span></span> <span data-ttu-id="2a4a3-119">Megjelenik az aktuális egyenleg, és Ön leáshat, azokig a tranzakciókig, amikből az összefoglaló számlaegyenleg áll.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-119">The current balance is shown, and you can drill down to the transactions that make up that summary balance amount.</span></span> <span data-ttu-id="2a4a3-120">Az **Áthidalt tranzakciók** összegével Ön leáshat azokig a tranzakciókig, amikből az összefoglaló összeg áll.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-120">The **Bridged transactions** amount also lets you drill down to the transactions that make up that summary amount.</span></span> <span data-ttu-id="2a4a3-121">Az áthidalt tranzakciók olyan függőben lévő tranzakciók, amelyeket az áthidaló funkciók használatával adtak fel, de amelyeket még nem hajtottak végre.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-121">Bridged transactions are any pending transactions that have been posted by using bridging functionality, but that haven't yet been cleared.</span></span> <span data-ttu-id="2a4a3-122">A **Függőben levő egyenleg** összege az aktuális egyenleg, mínusz az áthidalt, illetve függőben lévő tranzakciók.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-122">The **Pending balance** amount is the current balance minus the bridged, or pending, transactions.</span></span>

<span data-ttu-id="2a4a3-123">A kártya azt is megjeleníti, hogy mikor egyeztették utoljára a bankszámlát.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-123">The card also shows when the bank account was last reconciled.</span></span> <span data-ttu-id="2a4a3-124">Ez az információ csak akkor jelenik meg, ha a Haladó banki egyeztetés engedélyezett a bankszámlánál.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-124">This information is shown only if Advanced bank reconciliation is enabled for the bank account.</span></span>

### <a name="balance"></a><span data-ttu-id="2a4a3-125">Egyenleg</span><span class="sxs-lookup"><span data-stu-id="2a4a3-125">Balance</span></span>

<span data-ttu-id="2a4a3-126">Az **Egyenleg** diagram vagy a **Bankszámlák** szakaszban kijelölt bankszámla korábbi egyenlegére vonatkozó információkat jeleníti meg, vagy egy összegzést a korábbi egyenlegadatokról a jogi személy minden bankszámlájára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-126">The **Balance** chart shows either historic balance information for the bank account that is selected in the **Bank accounts** section or a summary of historic balance information for all bank accounts in the legal entity.</span></span> <span data-ttu-id="2a4a3-127">Ez az információ különböző időszakokra vonatkozóan állnak rendelkezésre: az aktuális hét, az aktuális hónap, az aktuális év, az elmúlt öt év, illetve minden időszak (a bankszámla minden előzménye).</span><span class="sxs-lookup"><span data-stu-id="2a4a3-127">This information is available for various periods: the current week, the current month, the current year, the last five years, and all periods (the full history of the bank account).</span></span> 

<span data-ttu-id="2a4a3-128">Ha egyetlen bankszámlára vonatkozóan nézi meg az **Egyenleg** diagramot, a korábbi egyenlegek a bankszámla pénznemében jelennek meg</span><span class="sxs-lookup"><span data-stu-id="2a4a3-128">If you're viewing the **Balance** chart for a single bank account, the historic balances are shown in the bank account currency.</span></span> <span data-ttu-id="2a4a3-129">Ha a jogi személy összes bankszámlájára vonatkozóan nézi meg a diagramot, a korábbi egyenlegek a könyvelés pénznemében jelennek meg</span><span class="sxs-lookup"><span data-stu-id="2a4a3-129">If you're viewing the chart for all bank accounts in the legal entity, the historic balances are shown in the accounting currency.</span></span>

<span data-ttu-id="2a4a3-130">Az utolsó frissítés idejéről szóló információ a diagram tetején jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-130">Information about when the data was last updated appears at the top of the chart.</span></span> <span data-ttu-id="2a4a3-131">Szükség esetén módosítani lehet az adatokat.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-131">You can update the data as you require.</span></span>

### <a name="related-information"></a><span data-ttu-id="2a4a3-132">Kapcsolódó információ</span><span class="sxs-lookup"><span data-stu-id="2a4a3-132">Related information</span></span>

<span data-ttu-id="2a4a3-133">A **Kapcsolódó információ** szakaszban megnyithatja az **Általános napló** oldalt, és végrehajthatja a banki átutalásokat.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-133">From the **Related information** section, you can open the **General journal** page to complete bank transfers.</span></span> <span data-ttu-id="2a4a3-134">Emellett gyorsan megnyithatja a **Banki tranzakciók** és az **Áthidalt tranzakciók** oldalakat.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-134">You can also quickly open the **Bank transactions** and **Bridged transactions** pages.</span></span>

## <a name="analytics-view"></a><span data-ttu-id="2a4a3-135">Elemzés nézet</span><span class="sxs-lookup"><span data-stu-id="2a4a3-135">Analytics view</span></span>

<span data-ttu-id="2a4a3-136">Az **Elemzés** oldalon fontos mérőszámok tekinthetők meg a jelenlegi vállalat bankszámláiról.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-136">The **Analytics** page provides important metrics about the bank accounts in the current company.</span></span> <span data-ttu-id="2a4a3-137">Az alábbi megjelenítési lehetőségek állnak rendelkezésre az oldalon:</span><span class="sxs-lookup"><span data-stu-id="2a4a3-137">The following visualizations are available on the page:</span></span>

-   <span data-ttu-id="2a4a3-138">Összesített egyenleg a rendszer pénznemében</span><span class="sxs-lookup"><span data-stu-id="2a4a3-138">Total bank balance in system currency</span></span>
-   <span data-ttu-id="2a4a3-139">Egyenleg jogi személy szerint</span><span class="sxs-lookup"><span data-stu-id="2a4a3-139">Balance by legal entity</span></span>
-   <span data-ttu-id="2a4a3-140">Aznapi tényleges és előrejelzett egyenleg a bankszámla pénznemében</span><span class="sxs-lookup"><span data-stu-id="2a4a3-140">Today’s actual vs forecasted balance in bank account currency</span></span>
-   <span data-ttu-id="2a4a3-141">Egyenleg bankszámla szerint</span><span class="sxs-lookup"><span data-stu-id="2a4a3-141">Balance by bank account</span></span>
-   <span data-ttu-id="2a4a3-142">Egyenleg pénznemenként</span><span class="sxs-lookup"><span data-stu-id="2a4a3-142">Balance by currency</span></span>

<span data-ttu-id="2a4a3-143">Megtekintheti a banki elemzéseket az összes vállalatra vonatkozóan a **Készpénzáttekintés – minden vállalat** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="2a4a3-143">You can view bank analytics across all companies from the **Cash overview – all companies** workspace.</span></span>

