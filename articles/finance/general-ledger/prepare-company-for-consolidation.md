---
title: Jogi személy előkészítése a konszolidációs folyamathoz
description: A konszolidációb során több jogi személy számláinak tranzakcióit foglalhatja össze egyetlen jogi személyhez tartozó számlakészletbe. Ez a témakör bemutatja a jogi személyek konszolidációra való előkészítését.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 6f718bef3b1b07d3bb03dbf6acbf1cdf58aa7b8a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815476"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a><span data-ttu-id="335a2-104">Jogi személy előkészítése a konszolidációs folyamathoz</span><span class="sxs-lookup"><span data-stu-id="335a2-104">Prepare a legal entity for the consolidation process</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="335a2-105">A konszolidációb során több jogi személy számláinak tranzakcióit foglalhatja össze egyetlen jogi személyhez tartozó számlakészletbe.</span><span class="sxs-lookup"><span data-stu-id="335a2-105">During a consolidation, you gather transactions from several sets of legal entity accounts into a single set of legal entity accounts.</span></span> <span data-ttu-id="335a2-106">Ez a témakör bemutatja a jogi személyek konszolidációra való előkészítését.</span><span class="sxs-lookup"><span data-stu-id="335a2-106">This topic explains how to prepare a legal entity for a consolidation.</span></span>

> [!NOTE]
> <span data-ttu-id="335a2-107">Javasoljuk, hogy a Management Reporter for Microsoft Dynamics 365 Finance szoftverrel egyesítse több jogi személy pénzügyi eredményeit konszolidált formátumban.</span><span class="sxs-lookup"><span data-stu-id="335a2-107">We recommend that you use Management Reporter for Microsoft Dynamics 365 Finance to combine the financial results for multiple legal entities in a consolidated format.</span></span> <span data-ttu-id="335a2-108">A Management Reporter segítségével konszolidált pénzügyi jelentéseket készíthet több jogi személyre vonatkozóan, az Excel segítségével importálhatja a konszolidációs adatokat más forrásokból, és összegeket fordíthat le bármely jelentési pénznemre anélkül, hogy a konszolidációs folyamatot kellene futtatnia a Dynamics 365 Finance rendszerben.</span><span class="sxs-lookup"><span data-stu-id="335a2-108">Management Reporter lets you create consolidated financial reports across legal entities, use Excel to import consolidation data from other sources, and translate amounts into any number of reporting currencies without having to run the consolidation process in Dynamics 365 Finance.</span></span>

<span data-ttu-id="335a2-109">Ezután lehetősége van a konszolidált jogi személyből jelentéseket, például pénzügyi kimutatásokat kinyomtatni.</span><span class="sxs-lookup"><span data-stu-id="335a2-109">You can print reports, such as financial statements, from the consolidated legal entity.</span></span> <span data-ttu-id="335a2-110">A konszolidált jogi személy azonban nem használható napi tranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="335a2-110">However, you can't use the consolidated legal entity for daily transactions.</span></span>

<span data-ttu-id="335a2-111">Akár olyan jogi személyek adatait is konszolidálhatja, amelyek eltérő adatbázisokat használnak, mint a konszolidált jogi személy.</span><span class="sxs-lookup"><span data-stu-id="335a2-111">You can consolidate data from legal entities that use different databases than the consolidated legal entity.</span></span> <span data-ttu-id="335a2-112">Ezt a konszolidációs folyamatot *import konszolidációnak* nevezik.</span><span class="sxs-lookup"><span data-stu-id="335a2-112">This consolidation process is referred to as an *import consolidation*.</span></span> <span data-ttu-id="335a2-113">Emellett a jogi személyek használhatják ugyanazt az adatbázist is, mint a konszolidált jogi személy.</span><span class="sxs-lookup"><span data-stu-id="335a2-113">Alternatively, the legal entities can use the same database as the consolidated legal entity.</span></span> <span data-ttu-id="335a2-114">Ezt a konszolidációs folyamatot *online konszolidációnak* nevezik.</span><span class="sxs-lookup"><span data-stu-id="335a2-114">This consolidation process is referred to as an *online consolidation*.</span></span>

<span data-ttu-id="335a2-115">A konszolidált jogi személyben lesznek összsegyűjtve a leányvállalatok eredményei és egyenlegei.</span><span class="sxs-lookup"><span data-stu-id="335a2-115">The consolidated legal entity collects the results and balances of the subsidiaries.</span></span> <span data-ttu-id="335a2-116">A konszolidált jogi személy konszolidációra való előkészítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="335a2-116">To prepare a consolidated legal entity for a consolidation, follow these steps.</span></span>

1. <span data-ttu-id="335a2-117">Nyissa meg a következőt: **Főkönyv \> Beállítás \> Szervezet \> Jogi személyek**.</span><span class="sxs-lookup"><span data-stu-id="335a2-117">Go to **General ledger \> Setup \> Organization \> Legal entities**.</span></span>
2. <span data-ttu-id="335a2-118">Az **Új** gombra kattintva hozza létre a konszolidált jogi személynek szánt új jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="335a2-118">Select **New** to create the legal entity that will be the consolidated legal entity.</span></span>
3. <span data-ttu-id="335a2-119">Jelölje be a **Pénzügyi konszolidálási folyamatokhoz** jelölőnégyzetet, majd adja meg a konszolidált jogi személy adatait.</span><span class="sxs-lookup"><span data-stu-id="335a2-119">Select the **Use for financial consolidation process** check box, and then enter information about the consolidated legal entity.</span></span> <span data-ttu-id="335a2-120">Pontosan úgy adja meg az információkat, ahogyan szerepeltetni szeretné azokat a konszolidált jogi személy pénzügyi kimutatásaiban.</span><span class="sxs-lookup"><span data-stu-id="335a2-120">Be sure to enter this information exactly as you want it to appear on financial statements for the consolidated legal entity.</span></span>
4. <span data-ttu-id="335a2-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="335a2-121">Close the page.</span></span>
5. <span data-ttu-id="335a2-122">Válassza ki a konszolidált jogi személyt az oldal jobb felső sarkában látható mezőben, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="335a2-122">Select the consolidated legal entity in the field in the upper-right corner of the page, and then select **OK**.</span></span>
6. <span data-ttu-id="335a2-123">Ugorjon a **Főkönyv \> Beállítás \> Főkönyv** elemre.</span><span class="sxs-lookup"><span data-stu-id="335a2-123">Go to **General ledger \> Setup \> Ledger**.</span></span>
7. <span data-ttu-id="335a2-124">Válassza ki a konszolidált jogi személy számlatükrét, pénzügyi naptárát, alapértelmezett pénznemét, opcionális jelentési pénznemét, és alapértelmezett árfolyamtípusát.</span><span class="sxs-lookup"><span data-stu-id="335a2-124">Select the chart of accounts, the fiscal calendar, the accounting currency, an optional reporting currency, and the default type of exchange rate for the consolidated legal entity.</span></span> 
8. <span data-ttu-id="335a2-125">Lépjen ide: **Főkönyv \> Beállítás \> Pénznem \> Pénznemek árfolyamtípusai**.</span><span class="sxs-lookup"><span data-stu-id="335a2-125">Go to **General ledger \> Setup \> Currency \> Currency exchange rates**.</span></span>
9. <span data-ttu-id="335a2-126">Adja meg a leányvállalatok pénznemeinek árfolyamait a releváns időszakokban.</span><span class="sxs-lookup"><span data-stu-id="335a2-126">Set up currency exchange rates in relevant periods for the currencies of the subsidiary legal entities.</span></span>
10. <span data-ttu-id="335a2-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="335a2-127">Close the page.</span></span>
11. <span data-ttu-id="335a2-128">Ha a konszolidált jogi személy leányvállalatai külföldi pénznemt használnak, kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="335a2-128">If the consolidated legal entity has subsidiaries that use foreign currencies, follow these steps:</span></span>

    1. <span data-ttu-id="335a2-129">Ugrás ide: **Főkönyv \> Beállítás \> Feladás \> Számlák az automatikus tranzakciókhoz**.</span><span class="sxs-lookup"><span data-stu-id="335a2-129">Go to **General ledger \> Setup \> Posting \> Accounts for automatic transactions**.</span></span>
    2. <span data-ttu-id="335a2-130">A **Feladás típusa** mezőben válasszon ki egy megfelelő számlát:</span><span class="sxs-lookup"><span data-stu-id="335a2-130">In the **Posting type** field, select an appropriate account:</span></span>

        - <span data-ttu-id="335a2-131">Ha a jogi személy olyan külföldi leányvállalatokkal rendelkezik, amelyek pénzügyileg vagy működésileg függetlenek a szülő jogi személytől, válassza ki a **Konszolidációs különbségekhez tartozó eredményszámla** feladási típust.</span><span class="sxs-lookup"><span data-stu-id="335a2-131">If the legal entity has foreign subsidiaries that are financially or operationally interdependent with the parent legal entity, select an appropriate account for the **Profit and loss account for consolidation differences** posting type.</span></span>
        - <span data-ttu-id="335a2-132">Ha olyan leányvállalatot konszolidál, amely pénzügyileg és irányítását tekintve független az anyag jogi személytől, vagy olyan jogi személyt, amely több, pénzügyileg és irányítását tekintve az anya jogi személytől független leányvállalat eredményeit tartalmazza, és amennyiben az adatok konszolidálásához átszámítási módokat használ, akkor válasszon egy megfelelő számlát a **Konszolidációs különbségekhez tartozó mérlegszámla** feladási típushoz.</span><span class="sxs-lookup"><span data-stu-id="335a2-132">If you're consolidating a subsidiary that is financially and operationally independent of the parent legal entity, or a legal entity that contains the results of several subsidiaries that are financially and operationally independent of the parent legal entity, and if you're using translation methods to consolidate the data, select an appropriate account for the **Balance account for consolidation differences** posting type.</span></span>

    3. <span data-ttu-id="335a2-133">A **Fő számla** mezőben válassza ki a devizaértékelés-korrekciókhoz használni kívánt fő számlát.</span><span class="sxs-lookup"><span data-stu-id="335a2-133">In the **Main account** field, select the main accounts that should be used for foreign currency revaluation adjustments.</span></span>
    4. <span data-ttu-id="335a2-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="335a2-134">Close the page.</span></span>

    <span data-ttu-id="335a2-135">Ha a konszolidált jogi személyt egy időszak elején hozza létre, akkor a devizaösszegek átértékelését a konszolidációs időszak során árfolyamváltozásként is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="335a2-135">If you create the consolidated legal entity early in a period, you can revalue foreign currency amounts as exchange rates change during the consolidation period.</span></span>

<span data-ttu-id="335a2-136">Ezzel beállította a konszolidált jogi személyt a **Konszolidálás** ismétlődő feladathoz.</span><span class="sxs-lookup"><span data-stu-id="335a2-136">The consolidated legal entity is now set up for the **Consolidate** periodic job.</span></span> <span data-ttu-id="335a2-137">Import konszolidációt vagy online konszolidációt végezhet.</span><span class="sxs-lookup"><span data-stu-id="335a2-137">You can do either an import consolidation or an online consolidation.</span></span>

- <span data-ttu-id="335a2-138">Az import konszolidációhoz lépjen ide: **Főkönyv \> Időszakos \> Konszolidálás \> Konszolidálás \[Importálás innen:\]**.</span><span class="sxs-lookup"><span data-stu-id="335a2-138">To do an import consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Import from\]**.</span></span>
- <span data-ttu-id="335a2-139">Az online konszolidációhoz lépjen ide: **Főkönyv \> Időszakos \> Konszolidálás \> Konszolidálás \[Online\]**.</span><span class="sxs-lookup"><span data-stu-id="335a2-139">To do an online consolidation, go to **General ledger \> Periodic \> Consolidate \> Consolidate \[Online\]**.</span></span>

> [!NOTE]
> <span data-ttu-id="335a2-140">A konszolidáció feldolgozása előtt elő kell készítenie a leányvállalati jogi személyeket a konszolidációra.</span><span class="sxs-lookup"><span data-stu-id="335a2-140">Before you can process the consolidation, you must prepare the subsidiary legal entities for consolidation.</span></span> <span data-ttu-id="335a2-141">További információ: [Alárendelt jogi személy beállítása a konszolidációra](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="335a2-141">For more information, see [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]