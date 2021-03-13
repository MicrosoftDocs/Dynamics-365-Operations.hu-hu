---
title: Globális adóelőleg
description: Ez a témakör a globális adóelőleg funkcióval és a funkció beállításával kapcsolatban tartalmaz tájékoztatást. A globális adóelőleg funkció továbbfejlesztett szállítói és vevői tranzakcióknál használható, így az adóelőleg számítása a cikk szintjén történik.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 17ed1dcae97f6cd28175c483be5ca3ce96d59e05
ms.sourcegitcommit: 053f4cda6862fbcd9e3aa6e9cb009e7de833beac
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/28/2021
ms.locfileid: "5075738"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="218b8-104">Globális adóelőleg</span><span class="sxs-lookup"><span data-stu-id="218b8-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="218b8-105">Ez a témakör a globális adóelőleg funkcióval és a funkció beállításával kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="218b8-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="218b8-106">Az új funkció a 10.0.17-es és későbbi verziókban áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="218b8-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="218b8-107">A globális adóelőleg funkció továbbfejlesztett szállítói és vevői tranzakcióknál használható, így az adóelőleg számítása a cikk szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="218b8-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="218b8-108">A beszerzési tranzakciók adóelőleg-számlájának egyenlege az adóelőleg-kiegyenlítési feladatnak az adóelőleg-elszámolási számlára vonatkozó futtatásával egyenlíthető ki.</span><span class="sxs-lookup"><span data-stu-id="218b8-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="218b8-109">A globális adóelőleg nem támogatja a **Költségek karbantartása** funkciót a beszerzési rendelés, a szállítói számla és az értékesítési rendelés oldalakon.</span><span class="sxs-lookup"><span data-stu-id="218b8-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="218b8-110">Globális adóelőleg bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="218b8-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="218b8-111">A **Funkció kezelése** munkaterületen válassza ki a **Globális adóelőleg** lehetőséget, majd válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="218b8-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="218b8-112">Lépjen az **Adó \> Beállítás \> Paraméterek \> Főkönyvi paraméterek** pontra, majd az **Adóelőleg** lapon állítsa a **Globális adóelőleg engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="218b8-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="218b8-113">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="218b8-113">Select **Save**.</span></span>
4. <span data-ttu-id="218b8-114">Frissítse az oldalt a webböngészőben.</span><span class="sxs-lookup"><span data-stu-id="218b8-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="218b8-115">A globális adóelőleg funkció nem kapcsolható be olyan országokban/régiókban, ahol már léteznek honosított adóelőleg-megoldások.</span><span class="sxs-lookup"><span data-stu-id="218b8-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="218b8-116">Ezek a területek többek között Indiára, Brazíliára, Thaiföldre, Szaúd-Arábiára, Írországra, Nagy-Britanniára és az Egyesült Államokra korlátozódnak.</span><span class="sxs-lookup"><span data-stu-id="218b8-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>