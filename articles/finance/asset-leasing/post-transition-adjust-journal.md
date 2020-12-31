---
title: Átmeneti helyesbítési naplóbejegyzések feladása az Eszközlízingben
description: Ez a témakör azokat a funkciókat ismerteti, amelyek lehetővé teszik a lízingportfólió átváltását az új lízingkönyvelési standardokra, a Könyvelési standardok kodifikációs témakör 842-re (ASC 842) és a Nemzetközi pénzügyi jelentési standard 16-ra (IFRS 16).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4af7b9dc7a03a6d17ff34ffc726eb87e848dd785
ms.sourcegitcommit: f0f5545a8ff99583e0131f435d91c64bb68a1c38
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2020
ms.locfileid: "4444193"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="4b161-103">Átmeneti helyesbítési naplóbejegyzések feladása az Eszközlízingben</span><span class="sxs-lookup"><span data-stu-id="4b161-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b161-104">Ez a témakör azokat a funkciókat ismerteti, amelyek lehetővé teszik a lízingportfólió új lízingkönyvelési standardokra való átváltását: Könyvelési standardok kodifikációs témakör 842 (ASC 842), amely az Egyesült Államok általánosan elfogadott könyvelési elveinek (US GAAP) és a Nemzetközi pénzügyi jelentési standard 16 (IFRS 16) standardja.</span><span class="sxs-lookup"><span data-stu-id="4b161-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="4b161-105">A könyv új standardokra való átváltásához való beállításáról a [Lízingkönyvek beállítása](set-up-lease-books.md) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="4b161-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="4b161-106">Átmeneti helyesbítési naplóbejegyzés létrehozásakor naplóbejegyzés jön létre.</span><span class="sxs-lookup"><span data-stu-id="4b161-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="4b161-107">Ez a bejegyzés a lízingnek az adott napon az új standardok szerinti elszámolásának mérlegre gyakorolt hatását tükrözi.</span><span class="sxs-lookup"><span data-stu-id="4b161-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="4b161-108">A megfelelő eszközszámlát az adott napon megterhelik a könyv szerinti értékkel, és a kötelezettségszámlát jóváírják.</span><span class="sxs-lookup"><span data-stu-id="4b161-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="4b161-109">A különbözetet vagy megterhelik, vagy jóváírják a visszatartott keresetekre.</span><span class="sxs-lookup"><span data-stu-id="4b161-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="4b161-110">Az új könyvelési standardoknak megfelelő átmeneti kiigazítás könyveléséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4b161-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="4b161-111">A **Lízing összegzése** lapon válassza ki a lízinget, majd válassza a **Könyvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b161-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="4b161-112">A könyvben válassza a **Fizetési ütemezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b161-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="4b161-113">A **Fizetési ütemezés** párbeszédpanelen válassza a **Megerősítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b161-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="4b161-114">Majd zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="4b161-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="4b161-115">Válassza az **Átváltás beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b161-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b161-116">Átmeneti kiigazítás csak olyan lízingkönyvekhez hozható létre, amelyek olyan könyvhöz vannak rendelve, ahol az **Átváltási könyv** mező elérhető.</span><span class="sxs-lookup"><span data-stu-id="4b161-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="4b161-117">Ha a **Lízing kezdete** mező értéke későbbi az átmeneti dátumnál, akkor az **Átmeneti kiigazítás** mező értéke nem frissül.</span><span class="sxs-lookup"><span data-stu-id="4b161-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="4b161-118">A naplóbejegyzés megtekintéséhez válassza ki az **Eszköz lízingnaplók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b161-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="4b161-119">Jelölje ki az új naplót, majd válassza a **Feladás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b161-119">Select the new journal, and then select **Post**.</span></span>
