---
title: A közvetlenül származtatott megerősített rendeléseket egy Felülvizsgálat alatt állapotú munkafolyamat dolgozza fel
description: A közvetlenül származtatott megerősített rendeléseket egy Felülvizsgálat alatt állapottal rendelkező munkafolyamat dolgozza fel.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026583"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a><span data-ttu-id="8fcff-103">A közvetlenül származtatott megerősített rendeléseket egy Felülvizsgálat alatt állapotú munkafolyamat dolgozza fel</span><span class="sxs-lookup"><span data-stu-id="8fcff-103">Directly derived firmed orders are processed by an in-review workflow</span></span>

<span data-ttu-id="8fcff-104">Tudásbáziscikk száma: 4612450</span><span class="sxs-lookup"><span data-stu-id="8fcff-104">KB number: 4612450</span></span>

## <a name="symptoms"></a><span data-ttu-id="8fcff-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="8fcff-105">Symptoms</span></span>

<span data-ttu-id="8fcff-106">A közvetlenül származtatott megerősített rendeléseket egy *Felülvizsgálat alatt* állapottal rendelkező munkafolyamat dolgozza fel.</span><span class="sxs-lookup"><span data-stu-id="8fcff-106">Directly derived firmed orders are processed by a workflow that has a status of *In-review*.</span></span>

## <a name="resolution"></a><span data-ttu-id="8fcff-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="8fcff-107">Resolution</span></span>

<span data-ttu-id="8fcff-108">Ha a nyomon követés engedélyezve van *Ellenőrzés alatt* állapot lesz hozzárendelve a megerősített származtatott rendelésekhez (alvállalkozói beszerzési rendelések).</span><span class="sxs-lookup"><span data-stu-id="8fcff-108">When change tracking is enabled, a status of *In-review* is assigned to firmed derived orders (subcontract purchase orders).</span></span> <span data-ttu-id="8fcff-109">Ezért ha egy beszerzési rendelés származtatott (alvállalkozói beszerzési rendelés), akkor csak egy munkafolyamatba lesz elküldve.</span><span class="sxs-lookup"><span data-stu-id="8fcff-109">Therefore, if a purchase order is derived (a subcontract purchase order), it's only submitted to a workflow.</span></span> <span data-ttu-id="8fcff-110">Ha egy beszerzési rendelés egy jóváhagyott tervezett beszerzési rendelés, a rendszer automatikusan jóváhagyja, hogy a tervezési motor ne hozzon létre új tervezett rendeléseket, amíg a beszerzési rendelés Még *Vázlat* állapotú.</span><span class="sxs-lookup"><span data-stu-id="8fcff-110">If a purchase order is a firmed planned purchase order, it's automatically approved to ensure that the planning engine doesn't create new planned orders while the purchase order is still in *Draft* status.</span></span>
