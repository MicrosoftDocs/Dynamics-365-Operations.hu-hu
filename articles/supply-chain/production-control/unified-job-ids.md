---
title: Egyesített számsorozat a feladatazonosítók esetén
description: Ez a funkció egyetlen, egységes számsorozatot biztosít, amely feladatazonosítókat hoz létre a Gyártásvezérlés, a Gyártásvégrehajtás és a Munkaidő és jelenlét modulokhoz.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824942"
---
# <a name="unified-number-sequence-for-job-ids"></a><span data-ttu-id="a450b-103">Egyesített számsorozat a feladatazonosítók esetén</span><span class="sxs-lookup"><span data-stu-id="a450b-103">Unified number sequence for job IDs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a450b-104">Ez a funkció egyetlen, egységes számsorozatot biztosít, amely feladatazonosítókat hoz létre a Gyártásvezérlés, a Gyártásvégrehajtás és a Munkaidő és jelenlét modulokhoz.</span><span class="sxs-lookup"><span data-stu-id="a450b-104">This feature provides a single, unified number sequence that generates job IDs for the Production control, Manufacturing execution, and Time and attendance modules.</span></span> <span data-ttu-id="a450b-105">Korábban mindegyik modulhoz más számsorozatot választhatott, ami ütköző feladatazonosítókat eredményezhet, ha két vagy több ilyen sorozat azonos formátumot használt.</span><span class="sxs-lookup"><span data-stu-id="a450b-105">Previously, you were able to choose a different number sequence for each of these modules, which could result in conflicting job IDs if two or more of these sequences used an identical format.</span></span> <span data-ttu-id="a450b-106">Egy ilyen ütközés adatsérülést okozhat.</span><span class="sxs-lookup"><span data-stu-id="a450b-106">Such a conflict can cause data corruption.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="a450b-107">A funkció bekapcsolása a rendszerhez</span><span class="sxs-lookup"><span data-stu-id="a450b-107">Turn on this feature for your system</span></span>

<span data-ttu-id="a450b-108">Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciót, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és a kapcsolja be az *Egyesített számsorozat a feladatazonosítók esetén* funkciót.</span><span class="sxs-lookup"><span data-stu-id="a450b-108">If your system doesn't already include the feature described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Unified number sequence for job IDs* feature.</span></span>

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a><span data-ttu-id="a450b-109">Egyesített számsorozat beállíítása a feladatazonosítók esetén</span><span class="sxs-lookup"><span data-stu-id="a450b-109">Set up the unified number sequence for job IDs</span></span>

<span data-ttu-id="a450b-110">A funkció engedélyezése után a Gyártásvezérlés, a Gyártásvégrehajtás, valamint a Munkaidő és jelenlét modulok paraméteroldalán található meglévő **Feladatazonosító** számsorozat-beállítások elavultak lesznek, és egy új **Egyesített feladatazonosító** mező kerül hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="a450b-110">After enabling this feature, the existing **Job identification** number-sequence settings located on the parameters pages for the Production control, Manufacturing execution, and Time and attendance modules will be deprecated and a new **Unified job ID** field will be added.</span></span> <span data-ttu-id="a450b-111">Az **Egyesített feladatazonosító** értéket mindhárom modulban közös, így biztosítva, hogy minden modul ugyanerre a számsorozatra hivatkozzon.</span><span class="sxs-lookup"><span data-stu-id="a450b-111">The **Unified job ID** value is shared by all three modules, thus ensuring that all modules reference the same number sequence.</span></span> <span data-ttu-id="a450b-112">A feladatazonosítók ezért mindhárom modulban egyediek lesznek, és soha nem fordul elő ütközés.</span><span class="sxs-lookup"><span data-stu-id="a450b-112">Job IDs will therefore be unique across all three modules and a conflict will never occur.</span></span>

<span data-ttu-id="a450b-113">Egyesített számsorozat beállíítása a feladatazonosítók esetén:</span><span class="sxs-lookup"><span data-stu-id="a450b-113">To set up the unified number sequence for job IDs:</span></span>

1. <span data-ttu-id="a450b-114">Kapcsolja be a funkciót az előző szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="a450b-114">Turn on the feature as described in the previous section.</span></span>
1. <span data-ttu-id="a450b-115">Azonosítsa az egyesített feladatazonosítókhoz használni kívánt számsorozatot, vagy hozzon létre egy újat.</span><span class="sxs-lookup"><span data-stu-id="a450b-115">Either identify the number sequence you want to use for your unified job IDs, or create a new one.</span></span> <span data-ttu-id="a450b-116">További információkért lásd: [Számsorozatok áttekintése](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a450b-116">For more information, see [Number sequences overview](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span></span>
1. <span data-ttu-id="a450b-117">Lépjen a **Gyártásvezérlés paraméterei**, a **Gyártásvégrehajtás paraméterei** vagy a **Munkaidő és jelenlét paraméterei** oldalra.</span><span class="sxs-lookup"><span data-stu-id="a450b-117">Go to the **Production control parameters**, **Manufacturing execution parameters**, or **Time and attendance parameters** page.</span></span> <span data-ttu-id="a450b-118">Nem számít, melyiket választja, mert amikor ezt a beállítást bármelyik oldalon megteszi, az összes többi oldal automatikusan frissül.</span><span class="sxs-lookup"><span data-stu-id="a450b-118">It doesn't matter which one you choose because when you make this setting on any of those pages, all of the other pages will update automatically.</span></span>
1. <span data-ttu-id="a450b-119">Nyissa meg a **Számsorozatok** lapot a kiválasztott paraméterek lapon.</span><span class="sxs-lookup"><span data-stu-id="a450b-119">Open the **Number sequences** tab on your selected parameters page.</span></span>
1. <span data-ttu-id="a450b-120">Rendelje hozzá a korábban azonosított **Számsorozatkódot** a rács **Egyesített feladatazonosítók** sorához.</span><span class="sxs-lookup"><span data-stu-id="a450b-120">Assign the **Number sequence code** that you identified previously to the **Unified job IDs** row of the grid.</span></span>
