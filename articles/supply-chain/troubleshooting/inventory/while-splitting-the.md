---
title: A tényleges súly mennyiségének felosztásakor a minimális mennyiséget használja a rendszer a névleges mennyiség helyett
description: Amikor a tényleges súly mennyisége kötegekbe van felosztva, a Kitárolási mennyiség mező a cikkhez beállított minimális mennyiséget használja, nem pedig a névleges mennyiséget.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026584"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a><span data-ttu-id="cadf9-103">A tényleges súly mennyiségének felosztásakor a minimális mennyiséget használja a rendszer a névleges mennyiség helyett</span><span class="sxs-lookup"><span data-stu-id="cadf9-103">When a catch-weight quantity is split, minimum quantity is used instead of nominal quantity</span></span>

<span data-ttu-id="cadf9-104">Tudásbáziscikk száma: 4612073</span><span class="sxs-lookup"><span data-stu-id="cadf9-104">KB number: 4612073</span></span>

## <a name="symptoms"></a><span data-ttu-id="cadf9-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="cadf9-105">Symptoms</span></span>

<span data-ttu-id="cadf9-106">Amikor a tényleges súly mennyisége kötegekbe van felosztva, a **Kitárolási mennyiség** mező a cikkhez beállított minimális mennyiséget használja, nem pedig a névleges mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="cadf9-106">When a catch-weight quantity is being split into batches, the **Pick qty** field uses the minimum quantity that is set for the item, not the nominal quantity.</span></span>

## <a name="resolution"></a><span data-ttu-id="cadf9-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="cadf9-107">Resolution</span></span>

<span data-ttu-id="cadf9-108">A rendszer úgy viselkedik, ahogy tervezték.</span><span class="sxs-lookup"><span data-stu-id="cadf9-108">The system is behaving as designed.</span></span> <span data-ttu-id="cadf9-109">A rendszer az egyes cikkek minimális kitárolási mennyiség beállításait használja.</span><span class="sxs-lookup"><span data-stu-id="cadf9-109">The system uses each item's minimum quantity setup for picking.</span></span>
