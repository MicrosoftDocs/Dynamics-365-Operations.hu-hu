---
title: Az adóelőlegelemek kifizetési időszakainak beállítása TDS adótípushoz
description: Ez a témakör elmagyarázza, hogyan lehet beállítani az elszámolási időszakokat a forrásnál levont adó (TDS) elszámolási időszakaihoz.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 9430bc1386f127d02b598d6cad1b53f66e0cf2ba
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023285"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a><span data-ttu-id="203a0-103">Az adóelőlegelemek kifizetési időszakainak beállítása TDS adótípushoz</span><span class="sxs-lookup"><span data-stu-id="203a0-103">Set up withholding tax settlement periods for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="203a0-104">Ez a témakör elmagyarázza, hogyan lehet beállítani az elszámolási időszakokat a forrásnál levont adó (TDS) elszámolási időszakaihoz.</span><span class="sxs-lookup"><span data-stu-id="203a0-104">This topic explains how to set up settlement periods for Tax Deducted at Source (TDS) settlement periods.</span></span>

1. <span data-ttu-id="203a0-105">Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőleg-kiegyenlítési időszakok** elemre.</span><span class="sxs-lookup"><span data-stu-id="203a0-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="203a0-106">[![Adóelőleg-kiegyenlítési időszakok oldala](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span><span class="sxs-lookup"><span data-stu-id="203a0-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)</span></span>

2. <span data-ttu-id="203a0-107">Az **Adótípus** mezőben válassza ki a **TDS** lehetőséget a TDS adótípus adóelőleg kiegyenlítési időszakainak beállításához.</span><span class="sxs-lookup"><span data-stu-id="203a0-107">In the **Tax type** field, select **TDS** to set up withholding tax settlement periods for the TDS tax type.</span></span>
3. <span data-ttu-id="203a0-108">Új sor létrehozásához válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="203a0-108">Select **New** to create a line.</span></span>
4. <span data-ttu-id="203a0-109">A **Kiegyenlítési időszak** mezőbe írja be a TDS kiegyenlítési időszak nevét.</span><span class="sxs-lookup"><span data-stu-id="203a0-109">In the **Settlement period** field, enter a name for the TDS settlement period.</span></span>
5. <span data-ttu-id="203a0-110">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="203a0-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="203a0-111">Az **Adóelőleg hatósága** mezőben válassza ki azt a TDS-hatóságot, amelyhez a TDS elszámolási időszakot határozza meg.</span><span class="sxs-lookup"><span data-stu-id="203a0-111">In the **Withholding tax authority** field, select the TDS authority that you're defining the TDS settlement period for.</span></span>
7. <span data-ttu-id="203a0-112">Az **Általános** gyorslapon az **Időszak intervalluma** mezőben válassza ki a TDS elszámolási időszak időszak-intervallumának típusát.</span><span class="sxs-lookup"><span data-stu-id="203a0-112">On the **General** FastTab, in the **Period interval** field, select the type of period interval for the TDS settlement period.</span></span>
8. <span data-ttu-id="203a0-113">Az **Egységek száma** mezőben adja meg az időszaki intervallumtípus egységeinek számát.</span><span class="sxs-lookup"><span data-stu-id="203a0-113">In the **Number of units** field, specify the number of units for the period interval type.</span></span>
9. <span data-ttu-id="203a0-114">Az **Időszakok** gyorslapon a **Kezdő dátum** mezőben válassza ki a TDS elszámolási időszak kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="203a0-114">On the **Periods** FastTab, in the **From date** field, select the start date for the TDS settlement period.</span></span> <span data-ttu-id="203a0-115">Válassza ki a befejező dátumot a **Befejező dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="203a0-115">In the **To date** field, select the end date.</span></span>
10. <span data-ttu-id="203a0-116">Ha egy meglévő időszakra egy későbbi TDS-elszámolási időszakot szeretne létrehozni az időszakintervallum és az időszakegységek alapján, válassza az **Új időszak** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="203a0-116">To create a subsequent TDS settlement period for an existing period, based on the period interval and period units, select **New period**.</span></span>
11. <span data-ttu-id="203a0-117">Az adott elszámolási időszakra vonatkozó időszakos TDS-elszámolás részleteinek megtekintéséhez válassza az **Adóelőlegfizetés** lehetőséget az **Adóelőlegfizetés** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="203a0-117">To view the details of the periodic TDS settlement that is run for a specific settlement period, select **Withholding tax payments** to open the **Withholding tax payment** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="203a0-118">Az időszakos TDS-elszámolási folyamat futtatásához lépjen a **Főkönyv \> Időszakos \> Adóelőleg \> Adóelőleg-fizetés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="203a0-118">To run the periodic TDS settlement process, go to **General ledger \> Periodic \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="203a0-119">[![Adóelőlegfizetés oldal](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span><span class="sxs-lookup"><span data-stu-id="203a0-119">[![Withholding tax payment page](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)</span></span>

12. <span data-ttu-id="203a0-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="203a0-120">Close the page.</span></span>
