---
title: Az ügyfél-visszatérítések halmozása sikertelen, ha cikkvisszatérítési csoportokat használnak
description: Ha cikk visszatérítési csoportokkal együttes vevői visszatérítési megállapodásokat használ, a program kiszámítja a visszatérítéseket, de az összesítés sikertelen lesz.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026565"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a><span data-ttu-id="2e200-103">Az ügyfél-visszatérítések halmozása sikertelen, ha cikkvisszatérítési csoportokat használnak</span><span class="sxs-lookup"><span data-stu-id="2e200-103">Cumulation of customer rebates fails when item rebate groups are used</span></span>

<span data-ttu-id="2e200-104">Tudásbáziscikk száma: 4611372</span><span class="sxs-lookup"><span data-stu-id="2e200-104">KB number: 4611372</span></span>

## <a name="symptoms"></a><span data-ttu-id="2e200-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="2e200-105">Symptoms</span></span>

<span data-ttu-id="2e200-106">Ha cikk visszatérítési csoportokkal együttes vevői visszatérítési megállapodásokat (*mennyiség* típusú) használ, a program kiszámítja a visszatérítéseket, de az összesítés sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="2e200-106">When you use customer rebate agreements (of the *amount* type) in combination with item rebate groups, rebates are calculated, but cumulation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="2e200-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="2e200-107">Resolution</span></span>

<span data-ttu-id="2e200-108">A rendszer úgy viselkedik, ahogy tervezték.</span><span class="sxs-lookup"><span data-stu-id="2e200-108">The system is behaving as designed.</span></span> <span data-ttu-id="2e200-109">A cikkcsoportok csak olyan cikkeket csoportosítnak, amelyekre azonos küszöbérték-feltétel vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2e200-109">Item groups group only items that have the same threshold condition.</span></span> <span data-ttu-id="2e200-110">A visszatérítési feltétel (küszöbérték) az egyes cikkek összegével szemben van beállítva, nem pedig a cikkcsoporton belül bármelyik cikk összesített összegével szemben.</span><span class="sxs-lookup"><span data-stu-id="2e200-110">The rebate condition (threshold) is set against the amount for each item, not against the cumulated amount for any item in the item group.</span></span>
