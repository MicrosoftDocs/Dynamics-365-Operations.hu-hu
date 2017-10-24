---
title: "Számlaösszegek számlaegyeztetési eltéréseinek feloldása"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3f7e1261838866688c97529b0edfa1354034247b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="2c0da-102">Számlaösszegek számlaegyeztetési eltéréseinek feloldása</span><span class="sxs-lookup"><span data-stu-id="2c0da-102">Resolve discrepancies during invoice totals matching</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="2c0da-103">A számlaegyeztetés ellenőrzésének egyik módja a számlaösszegek egyeztetése.</span><span class="sxs-lookup"><span data-stu-id="2c0da-103">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="2c0da-104">Ha szeretné beállítani, hogy a rendszer elvégezze a számlaösszegek egyeztetését, a **Kötelezettségek paraméterei** oldalon, a **Számla ellenőrzése** fülön állítsa a **Számlaösszegek egyeztetése** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="2c0da-104">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="2c0da-105">A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek.</span><span class="sxs-lookup"><span data-stu-id="2c0da-105">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="2c0da-106">Hat összeget hasonlít össze a rendszer a **Számlaösszegek egyeztetésének részletei** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c0da-106">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="2c0da-107">Ha az összegek bármelyike eltér a várt vonatkozó beszerzési rendelés összegétől, a rendszer egyeztetési eltérést jelez.</span><span class="sxs-lookup"><span data-stu-id="2c0da-107">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="2c0da-108">Az összegek esetében számlaegyeztetési eltérést tartalmazó számla áttekintéséhez kattintson a **Szállítói számla bevitele** munkaterületen a **Függő számlák** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2c0da-108">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="2c0da-109">Ezután a Műveleti panelen az **Ellenőrzés** fülön kattintson az **Egyeztetési részletek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2c0da-109">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="2c0da-110">Ha egyeztetési eltérések észlel, figyelmeztető ikon jelenik meg a számlaösszeg mellett.</span><span class="sxs-lookup"><span data-stu-id="2c0da-110">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="2c0da-111">További részleteket is megtekinthet az összegekről, ha megtekinti a számlaösszegek egyeztetési részleteit.</span><span class="sxs-lookup"><span data-stu-id="2c0da-111">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="2c0da-112">Az eltérés azonosítása után előfordulhat, hogy fel kell vennie a kapcsolatot a szállítóval, amennyiben úgy véli, hogy a számlán helytelen információ szerepel.</span><span class="sxs-lookup"><span data-stu-id="2c0da-112">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="2c0da-113">A szállítóval folytatott egyeztetés eredményétől függően a következő műveletek bármelyikét elvégezheti:</span><span class="sxs-lookup"><span data-stu-id="2c0da-113">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="2c0da-114">Az áreltérés elfogadása és a számla feladása az egyeztetési eltérésekkel.</span><span class="sxs-lookup"><span data-stu-id="2c0da-114">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="2c0da-115">Lehetséges, hogy a rendszerben jóváhagyás szükséges az egyeztetési eltérések feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="2c0da-115">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="2c0da-116">Ebben az esetben jóvá kell hagynia az egyeztetési eltérést, és opcionálisan meg kell adnia egy jóváhagyási megjegyzést.</span><span class="sxs-lookup"><span data-stu-id="2c0da-116">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="2c0da-117">Ezután kiválaszthatja a számla feladását.</span><span class="sxs-lookup"><span data-stu-id="2c0da-117">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="2c0da-118">A számlaösszeg módosítása a várt összegre és a számla feladása.</span><span class="sxs-lookup"><span data-stu-id="2c0da-118">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="2c0da-119">Teljes jóváírás és új, javított számla kérése a szállítótól.</span><span class="sxs-lookup"><span data-stu-id="2c0da-119">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="2c0da-120">További tudnivalókért lásd: [Kivételek kivizsgálása/feloldása](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2c0da-120">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>



