---
title: Mozgóátlag tartalék költségsorrend
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management tartalék költségsorrendjéről tartalmaz tájékoztatást a mozgóátlagok számításához.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 541b7ecca5c1c36999f573d6d0f2dc0c9e901631
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967583"
---
# <a name="moving-average-fallback-cost-sequence"></a><span data-ttu-id="279e5-103">Mozgóátlag tartalék költségsorrend</span><span class="sxs-lookup"><span data-stu-id="279e5-103">Moving average fallback cost sequence</span></span>

<span data-ttu-id="279e5-104">A készlet költségének kiszámítására használt egyik módszer a _mozgóátlag_.</span><span class="sxs-lookup"><span data-stu-id="279e5-104">One way that you can calculate the cost of your inventory is by using a _moving average_.</span></span> <span data-ttu-id="279e5-105">Az egyes készletcikkekhez legfeljebb három költségérték tartozhat:</span><span class="sxs-lookup"><span data-stu-id="279e5-105">Up to three cost values can be associated with each inventory item:</span></span>

- <span data-ttu-id="279e5-106">**Utolsó kiadás** – Az utolsó kiadási költség, ami hozzá lett rendelve, mielőtt a készlet negatívba ment át</span><span class="sxs-lookup"><span data-stu-id="279e5-106">**Last issue** – The last issue cost that was assigned before inventory went negative</span></span>
- <span data-ttu-id="279e5-107">**Aktív költség** – Egy költségszámítási verzióban aktivált legutóbbi költség</span><span class="sxs-lookup"><span data-stu-id="279e5-107">**Active cost** – The latest cost that was activated in a costing version</span></span>
- <span data-ttu-id="279e5-108">**Cikk ára** – A kiadott termékhez megadott költség</span><span class="sxs-lookup"><span data-stu-id="279e5-108">**Item price** – The cost that is specified for the released product</span></span>

<span data-ttu-id="279e5-109">Annak eldöntéséhez, hogy a mozgóátlag-számításokhoz melyik költségadat legyen használva, a rendszer egy _tartalék költségsorrendet_ használ az értékek rangsorának meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="279e5-109">To determine which of these cost values should be used in moving average calculations, the system uses a _fallback cost sequence_ to establish the order of preference for the values.</span></span> <span data-ttu-id="279e5-110">Ha a preferált költségérték nem érhető el, akkor a rendszer a következő preferált értéket használja, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="279e5-110">If the preferred cost value isn't available, the system uses the next-preferred value, and so on.</span></span>

<span data-ttu-id="279e5-111">A Microsoft Dynamics 365 Supply Chain Management korábbi verzióiban a rendszer rögzített tartalék költségsorozatot használt (_Utolsó kiadás – Aktív költség – Cikkár_).</span><span class="sxs-lookup"><span data-stu-id="279e5-111">In previous versions of Microsoft Dynamics 365 Supply Chain Management, the system used a fixed fallback cost sequence (_Last issue – Active cost – Item price_).</span></span> <span data-ttu-id="279e5-112">A 10.0.11 verzióban ez a sorozat továbbra is az alapértelmezett sorrend.</span><span class="sxs-lookup"><span data-stu-id="279e5-112">In version 10.0.11, this sequence is still the default sequence.</span></span> <span data-ttu-id="279e5-113">Ugyanakkor lehetőség van olyan funkció bekapcsolására is, amely lehetővé teszi, hogy a három rendelkezésre álló költségsorozat közül válasszon.</span><span class="sxs-lookup"><span data-stu-id="279e5-113">However, you can also turn on a feature that lets you select among three available fallback cost sequences.</span></span> <span data-ttu-id="279e5-114">Ez a funkció különösen akkor hasznos lehet olyan szervezeteknél, amelyek gyakran használnak negatív készletértékeket.</span><span class="sxs-lookup"><span data-stu-id="279e5-114">This feature can be especially useful for organizations that regularly use negative inventory values.</span></span>

<span data-ttu-id="279e5-115">Ha azt szeretné, hogy a költségsorozat kiválasztó modulja elérhető legyen, akkor Ön (vagy egy rendszergazda) a [Szolgáltatások kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) használatával kapcsolja be a _Mozgóátlag tartalék költségsorrend_ nevű funkciót.</span><span class="sxs-lookup"><span data-stu-id="279e5-115">To make the selector for the fallback cost sequence available, you (or an admin) must use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named _Moving average fallback cost sequence_.</span></span>

<span data-ttu-id="279e5-116">Az mozgóátlag-számítások költségsorozatának kiválasztásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="279e5-116">To select the fallback cost sequence for moving average calculations, follow these steps.</span></span>

1. <span data-ttu-id="279e5-117">Nyissa meg a **Paraméterek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="279e5-117">Open the **Parameters** page.</span></span>
2. <span data-ttu-id="279e5-118">A **Készletkönyvelés** lap **Mozgóátlag** szakaszában a következő értékek egyikére állítsa be a **Mozgóátlag tartalék költségsorrend** mezőt:</span><span class="sxs-lookup"><span data-stu-id="279e5-118">On the **Inventory accounting** tab, in the **Moving average** section, set the **Fallback cost sequence** field to one of the following values:</span></span>

    - <span data-ttu-id="279e5-119">**Utolsó kiadás – aktív költség – cikkár** – Ez a sorozat az alapértelmezett sorozat.</span><span class="sxs-lookup"><span data-stu-id="279e5-119">**Last issue – Active cost – Item price** – This sequence is the default sequence.</span></span> <span data-ttu-id="279e5-120">Ez ugyanaz a sorrend, ami akkor van használva, ha a _Mozgóátlag tartalék költségsorrend_ funkció nincsen bekapcsolva.</span><span class="sxs-lookup"><span data-stu-id="279e5-120">It's the same sequence that is used if the _Moving average fallback cost sequence_ feature isn't turned on.</span></span>
    - <span data-ttu-id="279e5-121">**Aktív költség – Utolsó kiadás**</span><span class="sxs-lookup"><span data-stu-id="279e5-121">**Active cost – Last issue**</span></span>
    - <span data-ttu-id="279e5-122">**Aktív költség – Cikkár** – A vállalatok teljesítménnyel kapcsolatos problémákat tapasztalhatnak, ha olyan üzleti folyamatokat alkalmaznak, amelyeknél a készlet rendszeres időközönként negatívba megy át, és ezzel egyidejűleg a tranzakciók mennyisége is magas.</span><span class="sxs-lookup"><span data-stu-id="279e5-122">**Active cost – Item price** – Organizations might experience performance issues if they use business processes where inventory regularly goes negative and, at the same time, the transaction volume is high.</span></span> <span data-ttu-id="279e5-123">Ez a beállítás segít enyhíteni a teljesítménnyel kapcsolatos problémákat.</span><span class="sxs-lookup"><span data-stu-id="279e5-123">This setting can help mitigate those performance issues.</span></span>

<span data-ttu-id="279e5-124">![Készletkönyvelési paraméterek](media/inventory-accounting-parameters.png "Készletkönyvelési paraméterek")</span><span class="sxs-lookup"><span data-stu-id="279e5-124">![Inventory accounting parameters](media/inventory-accounting-parameters.png "Inventory accounting parameters")</span></span>
