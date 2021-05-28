---
title: A folyamatban található Közvetett költségek jelentés törölt termelési rendeléseket tartalmaz
description: A folyamatban található Közvetett költségek jelentés a részlegesen feldolgozott, majd később törölt termelési rendelések adatait jeleníti meg.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026576"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a><span data-ttu-id="c32a5-103">A folyamatban található Közvetett költségek jelentés törölt termelési rendeléseket tartalmaz</span><span class="sxs-lookup"><span data-stu-id="c32a5-103">The Indirect costs in process report includes deleted production orders</span></span>

<span data-ttu-id="c32a5-104">Tudásbáziscikk száma: 4612748</span><span class="sxs-lookup"><span data-stu-id="c32a5-104">KB number: 4612748</span></span>

## <a name="symptoms"></a><span data-ttu-id="c32a5-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="c32a5-105">Symptoms</span></span>

<span data-ttu-id="c32a5-106">A **Folyamatban lévő közvetett költségek** jelentés a részlegesen feldolgozott, majd később törölt termelési rendelések adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c32a5-106">The **Indirect costs in process** report presents information about production orders that were partially processed and later deleted.</span></span>

## <a name="resolution"></a><span data-ttu-id="c32a5-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="c32a5-107">Resolution</span></span>

<span data-ttu-id="c32a5-108">Termelési rendelés sztornírozása esetén az adott termelési rendelés összes tranzakcióját is sztornírozza.</span><span class="sxs-lookup"><span data-stu-id="c32a5-108">When you reverse a production order, you also reverse all the transactions of that production order.</span></span> <span data-ttu-id="c32a5-109">A termelési rendelés törlésekor az analitikus táblák és a főkönyv a hozzá kapcsolódó tranzakciókat is megtartja.</span><span class="sxs-lookup"><span data-stu-id="c32a5-109">When you delete the production order, the subledger tables and general ledger persist all transactions that are related to it.</span></span> <span data-ttu-id="c32a5-110">A jelentések meg fogják jelenni a tranzakciókat az analitikus táblákban.</span><span class="sxs-lookup"><span data-stu-id="c32a5-110">The reports will show the transactions in the subledger tables.</span></span> <span data-ttu-id="c32a5-111">Az adott termelési rendelés nettó értéke csak 0,00 lehet.</span><span class="sxs-lookup"><span data-stu-id="c32a5-111">For the specific production order, the net value should be 0.00.</span></span>
