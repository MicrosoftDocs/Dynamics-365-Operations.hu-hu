---
title: Számlaösszegek számlaegyeztetési eltéréseinek feloldása – áttekintés
description: A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0cf5a48a0f6beafad3c9a657c44079b290a7ebd5
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772214"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a><span data-ttu-id="36914-103">Számlaösszegek számlaegyeztetési eltéréseinek feloldása – áttekintés</span><span class="sxs-lookup"><span data-stu-id="36914-103">Resolve discrepancies during invoice totals matching overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36914-104">A számlaegyeztetés ellenőrzésének egyik módja a számlaösszegek egyeztetése.</span><span class="sxs-lookup"><span data-stu-id="36914-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="36914-105">Ha szeretné beállítani, hogy a rendszer elvégezze a számlaösszegek egyeztetését, a **Kötelezettségek paraméterei** oldalon, a **Számla ellenőrzése** fülön állítsa a **Számlaösszegek egyeztetése** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="36914-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="36914-106">A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek.</span><span class="sxs-lookup"><span data-stu-id="36914-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="36914-107">Hat összeget hasonlít össze a rendszer a **Számlaösszegek egyeztetésének részletei** oldalon.</span><span class="sxs-lookup"><span data-stu-id="36914-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="36914-108">Ha az összegek bármelyike eltér a várt vonatkozó beszerzési rendelés összegétől, a rendszer egyeztetési eltérést jelez.</span><span class="sxs-lookup"><span data-stu-id="36914-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="36914-109">Az összegek esetében számlaegyeztetési eltérést tartalmazó számla áttekintéséhez kattintson a **Szállítói számla bevitele** munkaterületen a **Függő számlák** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="36914-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="36914-110">Ezután a Műveleti panelen az **Ellenőrzés** fülön kattintson az **Egyeztetési részletek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="36914-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="36914-111">Ha egyeztetési eltérések észlel, figyelmeztető ikon jelenik meg a számlaösszeg mellett.</span><span class="sxs-lookup"><span data-stu-id="36914-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="36914-112">További részleteket is megtekinthet az összegekről, ha megtekinti a számlaösszegek egyeztetési részleteit.</span><span class="sxs-lookup"><span data-stu-id="36914-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="36914-113">Az eltérés azonosítása után előfordulhat, hogy fel kell vennie a kapcsolatot a szállítóval, amennyiben úgy véli, hogy a számlán helytelen információ szerepel.</span><span class="sxs-lookup"><span data-stu-id="36914-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="36914-114">A szállítóval folytatott egyeztetés eredményétől függően a következő műveletek bármelyikét elvégezheti:</span><span class="sxs-lookup"><span data-stu-id="36914-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="36914-115">Az áreltérés elfogadása és a számla feladása az egyeztetési eltérésekkel.</span><span class="sxs-lookup"><span data-stu-id="36914-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="36914-116">Lehetséges, hogy a rendszerben jóváhagyás szükséges az egyeztetési eltérések feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="36914-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="36914-117">Ebben az esetben jóvá kell hagynia az egyeztetési eltérést, és opcionálisan meg kell adnia egy jóváhagyási megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="36914-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="36914-118">Ezután kiválaszthatja a számla feladását.</span><span class="sxs-lookup"><span data-stu-id="36914-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="36914-119">A számlaösszeg módosítása a várt összegre és a számla feladása.</span><span class="sxs-lookup"><span data-stu-id="36914-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="36914-120">Teljes jóváírás és új, javított számla kérése a szállítótól.</span><span class="sxs-lookup"><span data-stu-id="36914-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="36914-121">További tudnivalókért lásd: [Kivételek kivizsgálása/feloldása](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="36914-121">For more information, see [Research/Resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>


