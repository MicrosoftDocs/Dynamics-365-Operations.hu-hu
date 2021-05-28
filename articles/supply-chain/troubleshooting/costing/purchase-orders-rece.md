---
title: A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a készletzárási jelentésben
description: A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a Nyitott mennyiségek ellenőrzése készletzárási jelentésben.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026575"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a><span data-ttu-id="819e0-103">A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a készletzárási jelentésben</span><span class="sxs-lookup"><span data-stu-id="819e0-103">Physically received purchase orders don't appear on the inventory closing report</span></span>

<span data-ttu-id="819e0-104">Tudásbáziscikk száma: 4612595</span><span class="sxs-lookup"><span data-stu-id="819e0-104">KB number: 4612595</span></span>

## <a name="symptoms"></a><span data-ttu-id="819e0-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="819e0-105">Symptoms</span></span>

<span data-ttu-id="819e0-106">A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a **Nyitott mennyiségek ellenőrzése** készletzárási jelentésben.</span><span class="sxs-lookup"><span data-stu-id="819e0-106">Physically received purchase orders don't appear on the **Check open quantities** inventory closing report.</span></span>

## <a name="resolution"></a><span data-ttu-id="819e0-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="819e0-107">Resolution</span></span>

<span data-ttu-id="819e0-108">A **Nyitott mennyiségek ellenőrzése** jelentés olyan kiadási tranzakciókat mutat, amelyek a pénzügyileg frissített készletbevételezésekkel szemben nem egyenlíthetők ki a kiválasztott zárási dátummal.</span><span class="sxs-lookup"><span data-stu-id="819e0-108">The **Check open quantities** report shows issue transactions that can't be settled against financially updated inventory receipts as of the selected closing date.</span></span> <span data-ttu-id="819e0-109">A tényleges bevételezéseket is bele lehet foglalni a jelentésbe.</span><span class="sxs-lookup"><span data-stu-id="819e0-109">You can choose to include physical receipts on the report.</span></span> <span data-ttu-id="819e0-110">Ebben az esetben a tényleges bevételezések megjelennek, ha fedezik a ki nem egyenlíthető kiadási tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="819e0-110">In that case, physical receipts will be shown if they can cover the issue transactions that can't be settled.</span></span> <span data-ttu-id="819e0-111">További információ: [A készletzárás futtatásának előkészítése](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span><span class="sxs-lookup"><span data-stu-id="819e0-111">For more information, see [Preparing to run inventory close](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).</span></span>
