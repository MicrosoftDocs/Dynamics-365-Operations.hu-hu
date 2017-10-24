---
title: "Beosztás-költségvetéskészítés hibaelhárítása"
description: "Ez a cikk olyan kérdésekre ad választ, amelyek a beosztás-költségvetés elkészítésekor merülhetnek fel. A költségvetési költségösszetevők, kompenzációs csoportok és a kompenzációs rácsok létrehozásával kapcsolatban leggyakrabban feltett kérdéseket tárgyalja."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 421520fcd1b215a19c126ccea51b025977552448
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="position-budgeting-troubleshooting"></a><span data-ttu-id="2630b-104">Beosztás-költségvetéskészítés hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="2630b-104">Position budgeting troubleshooting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2630b-105">Ez a cikk olyan kérdésekre ad választ, amelyek a beosztás-költségvetés elkészítésekor merülhetnek fel.</span><span class="sxs-lookup"><span data-stu-id="2630b-105">This article provides answers to questions that you might have when you configure position budgeting.</span></span> <span data-ttu-id="2630b-106">A költségvetési költségösszetevők, kompenzációs csoportok és a kompenzációs rácsok létrehozásával kapcsolatban leggyakrabban feltett kérdéseket tárgyalja.</span><span class="sxs-lookup"><span data-stu-id="2630b-106">It addresses frequently asked questions about how to create budget cost elements, compensation groups, and compensation grids.</span></span> 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a><span data-ttu-id="2630b-107">Miért nem található az Emberi erőforrásokban az előre jelzett beosztás oldal?</span><span class="sxs-lookup"><span data-stu-id="2630b-107">Why can’t I find the forecast position page in Human resources?</span></span>
---------------------------------------------------------------

<span data-ttu-id="2630b-108">Az előre jelzett beosztások átkerültek a Költségvetés készítésébe.</span><span class="sxs-lookup"><span data-stu-id="2630b-108">Forecast positions have been moved to Budgeting.</span></span>

## <a name="why-cant-i-delete-a-budget-cost-element"></a><span data-ttu-id="2630b-109">Miért nem lehet törölni a költségvetési költségösszetevőt?</span><span class="sxs-lookup"><span data-stu-id="2630b-109">Why can’t I delete a budget cost element?</span></span>
<span data-ttu-id="2630b-110">Az olyan költségvetési költségösszetevő nem törölhető, amely egy előre jelzett beosztáshoz van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="2630b-110">You can’t delete a budget cost element that is assigned to a forecast position.</span></span> <span data-ttu-id="2630b-111">Mielőtt törölne egy költségvetési költségösszetevőt, el kell távolítania az összes előre jelzett beosztásból.</span><span class="sxs-lookup"><span data-stu-id="2630b-111">Before you can delete a budget cost element, you must remove it from all forecast positions.</span></span> <span data-ttu-id="2630b-112">**Tipp:** Az összes olyan beosztás eléréshez, amelyhez tartozik költségvetési költségösszetevő válassza ki a költségösszetevőt a **Költségvetési költségösszetevők** oldalon, majd kattintson a **Beosztások frissítése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2630b-112">**Tip:** To find all the positions that a budget cost element is assigned to, select the cost element on the **Budget cost elements** page, and then click **Update positions**.</span></span> <span data-ttu-id="2630b-113">Az adott költségösszetevőt használó beosztások a felső rácson szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="2630b-113">The positions that use the cost element are listed in the upper grid.</span></span>

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a><span data-ttu-id="2630b-114">Hogyan távolíthatom el a költségösszetevőt több előre jelzett beosztásból, anélkül, hogy mindegyiket megnyitnám?</span><span class="sxs-lookup"><span data-stu-id="2630b-114">How can I remove a cost element from multiple forecast positions without opening each one?</span></span>
<span data-ttu-id="2630b-115">A költségösszetevő nem távolítható el.</span><span class="sxs-lookup"><span data-stu-id="2630b-115">You can’t remove a cost element.</span></span> <span data-ttu-id="2630b-116">Azonban ha úgy módosítja a kezdő és záró dátumokat, hogy kívül essenek a költségvetés-tervezési cikluson, akkor a költségösszetevő nem lesz többé hozzárendelve az ezen költségtervezési ciklusban található előre jelzett beosztásokhoz.</span><span class="sxs-lookup"><span data-stu-id="2630b-116">However, if you change the start and end dates so that they are outside the budget planning cycle dates, the cost element will no longer be assigned to the forecast positions in that budget planning cycle.</span></span> <span data-ttu-id="2630b-117">Ezen módosítás végrehajtásához nyissa meg a költségvetési költségösszetevőt, majd a **Költségszámítás** gyorslapon kattintson a **Dátum módosítása** lehetőségre, és változtassa meg az érvénybe lépési dátumot vagy a lejárati dátumot.</span><span class="sxs-lookup"><span data-stu-id="2630b-117">To make this change, open the budget cost element, and then, on the **Cost calculation** FastTab, click **Change dates**, and change the effective date or expiration date.</span></span> <span data-ttu-id="2630b-118">Ezután kattintson az **OK** gombra, hogy automatikusan frissítse az összes előre jelzett beosztást, amelyekhez a költségösszetevő hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="2630b-118">Then click **OK** to automatically update all forecast positions that the cost element is assigned to.</span></span> <span data-ttu-id="2630b-119">**Tipp:** Ha ezt a módszert alkalmazza, ügyeljen arra, hogy ezzel eltávolítja a költségvetési költségösszetevőt **minden** olyan előre jelzett beosztásból, amelyben a kezdő és záró dátumok már nem a megfelelő tartományba esnek.</span><span class="sxs-lookup"><span data-stu-id="2630b-119">**Tip:** If you use this method, be aware that it removes the budget cost element from **all** forecast positions where the start and end dates are no longer within the appropriate range.</span></span> <span data-ttu-id="2630b-120">Ha nem ezt a hatás akarja elérni, akkor meg kell nyitnia minden egyes előre jelzett beosztást, amelyből el kívánja távolítani a költségvetési költségösszetevőt és a módosítást manuálisan kell elvégeznie.</span><span class="sxs-lookup"><span data-stu-id="2630b-120">If this effect isn't what you intend, you must open each forecast position that you want to remove the budget cost element from and manually make the change.</span></span>

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a><span data-ttu-id="2630b-121">Miért nem adható meg a költségvetési költségösszetevő gyorslapján éves összeg?</span><span class="sxs-lookup"><span data-stu-id="2630b-121">Why can’t I enter an annual amount on the Cost calculation FastTab for the budget cost element?</span></span>
<span data-ttu-id="2630b-122">Éves összeg nem adható meg, ha költségvetési költségösszetevők vannak a **Számítás alapja** gyorslapon, mert a rendszer százalékos értéket igényel a számításhoz.</span><span class="sxs-lookup"><span data-stu-id="2630b-122">You can’t enter an annual amount if there are budget cost elements on the **Calculation basis** FastTab, because the system requires a percentage in order to calculate the value.</span></span> <span data-ttu-id="2630b-123">Az érték módosításához távolítson el minden költségvetési költségösszetevőt a **Számítás alapja** gyorslapról.</span><span class="sxs-lookup"><span data-stu-id="2630b-123">To change the value, remove all budget cost elements from the **Calculation basis** FastTab.</span></span>

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a><span data-ttu-id="2630b-124">Miért nem lehet módosítani a kereseti költségvetési költségtípust más költségtípusra?</span><span class="sxs-lookup"><span data-stu-id="2630b-124">Why can’t I change the budget cost type from earning to another budget cost type?</span></span>
<span data-ttu-id="2630b-125">Néhány költségvetési költségösszetevő a kereseti költségösszetevőt használja a számítás alapjául.</span><span class="sxs-lookup"><span data-stu-id="2630b-125">Some budget cost elements use the earning cost element as a calculation basis.</span></span> <span data-ttu-id="2630b-126">Ha módosítani szeretné az **Előirányzott költség típusa** mezőt, akkor távolítsa el a kereseti költségösszetevőt az összes költségvetési költségösszetevő **Számítás alapja** gyorslapjáról.</span><span class="sxs-lookup"><span data-stu-id="2630b-126">To change the **Budget cost type** field, remove the earning cost element from the **Calculation basis** FastTab of all budget cost elements.</span></span>

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a><span data-ttu-id="2630b-127">Miért nem módosítható egy költségvetési költségösszetevő költségösszetevő-sorainak dátuma?</span><span class="sxs-lookup"><span data-stu-id="2630b-127">Why can’t I change the date on budget cost element lines for a budget cost element?</span></span>
<span data-ttu-id="2630b-128">Nem módosíthatja a költségvetési összetevő sorának dátumát, ha a költségvetési költségösszetevőt egy előre jelzett beosztás használja.</span><span class="sxs-lookup"><span data-stu-id="2630b-128">You can’t change the date on the budget cost element line when a budget cost element is used by a forecast position.</span></span> <span data-ttu-id="2630b-129">Ez a korlátozás segít garantálni, hogy az előre jelzett beosztások mindig megfelelnek a költségvetési költségösszetevő irányelveinek.</span><span class="sxs-lookup"><span data-stu-id="2630b-129">This limitation helps guarantee that the forecast positions are always within the guidelines of the budget cost element.</span></span> <span data-ttu-id="2630b-130">A dátum módosításához a **Költségszámítás** gyorslapon kattintson a **Dátum módosítása** lehetőségre, és írja be az új dátumokat.</span><span class="sxs-lookup"><span data-stu-id="2630b-130">To change the date, on the **Cost calculation** FastTab, click **Change dates**, and enter the new dates.</span></span> <span data-ttu-id="2630b-131">Ezután kattintson az **OK** gombra, hogy frissítse az összes előre jelzett beosztást, amelyekhez a költségösszetevő hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="2630b-131">Then click **OK** to update the positions that the cost element is assigned to.</span></span>

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a><span data-ttu-id="2630b-132">Miért nem lehet módosítani a költségvetési költségösszetevő költségeit a Kompenzációs csoport lapon?</span><span class="sxs-lookup"><span data-stu-id="2630b-132">Why can’t I change the costs for a budget cost element on the Compensation group page?</span></span>
<span data-ttu-id="2630b-133">Csak a **Költségvetési költségösszetevők** oldalon hozhat létre és módosíthat költségvetési költségösszetevőket.</span><span class="sxs-lookup"><span data-stu-id="2630b-133">You can create and change budget cost elements only on the **Budget cost elements** page.</span></span>

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a><span data-ttu-id="2630b-134">Miért jelenik meg egy hibaüzenetet egy előre jelzett beosztás esetén a költségösszetevő dátumának módosításakor?</span><span class="sxs-lookup"><span data-stu-id="2630b-134">Why do I receive an error message when I change the dates for a cost element on a forecast position?</span></span>
<span data-ttu-id="2630b-135">Az előre jelzett beosztás költségösszetevő sorának dátuma a következő tartományokba kell hogy essen:</span><span class="sxs-lookup"><span data-stu-id="2630b-135">The dates on the forecast position cost element line must be within the following ranges:</span></span>

-   <span data-ttu-id="2630b-136">A beosztás aktiválási és kivezetési dátuma.</span><span class="sxs-lookup"><span data-stu-id="2630b-136">The activation and retirement dates of the position.</span></span>
-   <span data-ttu-id="2630b-137">A költségvetési költségösszetevő aktiválási és lejárati dátuma.</span><span class="sxs-lookup"><span data-stu-id="2630b-137">The activation and expiration dates of the budget cost element.</span></span>
-   <span data-ttu-id="2630b-138">Azon költségvetési ciklus kezdő és záró dátumai, amely az előre jelzett beosztás költségvetés-tervezési folyamatával van társítva.</span><span class="sxs-lookup"><span data-stu-id="2630b-138">The start and end dates of the budget cycle that is associated with the budget planning process of the forecast position.</span></span>




