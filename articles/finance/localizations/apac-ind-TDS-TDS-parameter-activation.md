---
title: 'A TDS-paraméterek beállítása:'
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani a paramétereket a forrásnál levont adó (TDS) funkció aktiválásához a megadott tranzakciókban. Ez a lépés szükséges Forrásnál levont adó funkció használatához.
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
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023296"
---
# <a name="set-the-tds-parameters"></a><span data-ttu-id="4c0d1-104">A TDS-paraméterek beállítása:</span><span class="sxs-lookup"><span data-stu-id="4c0d1-104">Set the TDS parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c0d1-105">Ez a témakör bemutatja, hogy hogyan lehet beállítani a paramétereket a forrásnál levont adó (TDS) funkció aktiválásához a megadott tranzakciókban.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-105">This topic explains how to set parameters to activate Tax Deducted at Source (TDS) functionality in specified transactions.</span></span> <span data-ttu-id="4c0d1-106">Ez a lépés szükséges Forrásnál levont adó funkció használatához.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-106">This is a necessary step to use the Tax Deducted at Source TDS feature.</span></span>

1. <span data-ttu-id="4c0d1-107">Menjen a **Főkönyv \> Főkönyv beállítás \> Főkönyv paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-107">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="4c0d1-108">A **Közvetlen adók** lapon a **Forrásnál levont adó** szakaszban állítsa a **TDS aktiválása** lehetőséget **Igen** beállításra a TDS funkció, valamint az ahhoz használt lapok és mezők aktiválásához.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-108">On the **Direct taxes** tab, in the **Tax Deducted at Source** section, set the **Activate TDS** option to **Yes** to activate the TDS functionality, and the pages and fields that are used for it.</span></span>
3. <span data-ttu-id="4c0d1-109">Állítsa a **Számla** lehetőséget **Igen** értékre, hogy aktiválja a számla szintjén az adószámításhoz és -levonáshoz használt mezőket.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-109">Set the **Invoice** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the invoice level.</span></span>
4. <span data-ttu-id="4c0d1-110">Állítsa a **Fizetés** lehetőséget **Igen** értékre, hogy aktiválja a fizetés szintjén az adószámításhoz és -levonáshoz használt mezőket.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-110">Set the **Payment** option to **Yes** to activate the fields that are used to calculate and deduct TDS at the payment level.</span></span>

    <span data-ttu-id="4c0d1-111">[![Közvetlen adók lap](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span><span class="sxs-lookup"><span data-stu-id="4c0d1-111">[![Direct taxes tab](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)</span></span>

5. <span data-ttu-id="4c0d1-112">A **Számsorozatok** lapon keresse meg azt a sort, amelyben a **Hivatkozás** mezőben **Adóelőleg-fizetés** van beállítva.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-112">On the **Number sequences** tab, find the row where the **Reference** field is set to **Withholding tax payment**.</span></span> <span data-ttu-id="4c0d1-113">A **Számsorozat kódja** mezőben a sorhoz válasszon ki egy számsorozat-kódot.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-113">In the **Number sequence code** field for the row, select the number sequence code.</span></span> <span data-ttu-id="4c0d1-114">A számsorozatkód segítségével bizonylatszámokat lehet létrehozni az időszakos TDS kiegyenlítési folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-114">The number sequence code is used to generate voucher numbers for the periodic TDS settlement process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c0d1-115">Az időszakos TDS-elszámolási folyamat futtatásához lépjen az **Adó \> Nyilatkozatok \> Adóelőleg \> Adóelőleg-fizetés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-115">To run the periodic TDS settlement process, go to **Tax \> Declarations \> Withholding tax \> Withholding tax payment**.</span></span>

    <span data-ttu-id="4c0d1-116">[![Számsorozatok lap](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span><span class="sxs-lookup"><span data-stu-id="4c0d1-116">[![Number sequences tab](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)</span></span>

6. <span data-ttu-id="4c0d1-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4c0d1-117">Close the page.</span></span>
