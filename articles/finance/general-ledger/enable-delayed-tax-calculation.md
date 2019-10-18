---
title: Késleltetett adó számításának engedélyezése a naplón
description: Ez a témakör azt mutatja be, hogyan lehet a **Késleltetett adó számításának engedélyezése a naplón** funkciót az adószámítás hatékonyságának növelésére használni, ha a naplósorok mennyisége hatalmas.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178058"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a><span data-ttu-id="bbd19-103">Késleltetett adó számításának engedélyezése a naplón</span><span class="sxs-lookup"><span data-stu-id="bbd19-103">Enable delayed tax calculation on journal</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="bbd19-104">Ez a témakör azt mutatja be, hogyan lehet a **Késleltetett adó számításának engedélyezése a naplón** funkciót az adószámítás hatékonyságának növelésére használni, ha a naplósorok mennyisége hatalmas.</span><span class="sxs-lookup"><span data-stu-id="bbd19-104">This topic explains how to use the **Enable delayed tax calculation on journal** feature to improve tax calculation performance when the volume of journal lines is huge.</span></span>

<span data-ttu-id="bbd19-105">A napló jelenlegi ÁFA-számítási viselkedése valós idejű, akkor indul el, amikor a felhasználó az adóval kapcsolatos mezőket, például a áfacsoportok vagy a cikkáfacsoport csoportját frissíti.</span><span class="sxs-lookup"><span data-stu-id="bbd19-105">Current sales tax calculation behavior on journal is real-time triggered when user updates tax related fields, e.g. sales tax group/item sales tax group.</span></span> <span data-ttu-id="bbd19-106">A naplósorban szereplő bármilyen frissítés újraszámítja az összes naplósorban szereplő adóösszeg értékét.</span><span class="sxs-lookup"><span data-stu-id="bbd19-106">Any update at journal line level will re-calculate tax amount on all journal lines.</span></span> <span data-ttu-id="bbd19-107">Segít a felhasználó számára a valós idejű kiszámított adó összegének megjelenítésében, de a teljesítményproblémákat is okozhat, ha a naplósorok száma magas.</span><span class="sxs-lookup"><span data-stu-id="bbd19-107">It helps user to see real-time calculated tax amount but it could also bring performance issue if  the volume of journal lines is huge.</span></span>

<span data-ttu-id="bbd19-108">Ez a funkció lehetőséget ad az adószámítás késleltetésére a teljesítmény-probléma megoldása érdekében.</span><span class="sxs-lookup"><span data-stu-id="bbd19-108">This feature provides an option to delay tax calculation to solve performance issue.</span></span> <span data-ttu-id="bbd19-109">Ha ez a funkció be van kapcsolva, akkor az adó összegét csak akkor számítja ki a rendszer, amikor a felhasználó az „ÁFA” parancsra kattint vagy feladja a naplót.</span><span class="sxs-lookup"><span data-stu-id="bbd19-109">If this feature is turned on, tax amount will only be calculated when user clicks "Sales Tax" command or posts the journal.</span></span>

<span data-ttu-id="bbd19-110">A felhasználó a paramétereket három szinten kapcsolja be/ki:</span><span class="sxs-lookup"><span data-stu-id="bbd19-110">User can turn on/off the parameter at three levels:</span></span>
- <span data-ttu-id="bbd19-111">Jogi személy szerint</span><span class="sxs-lookup"><span data-stu-id="bbd19-111">By legal entity</span></span>
- <span data-ttu-id="bbd19-112">Napló neve szerint</span><span class="sxs-lookup"><span data-stu-id="bbd19-112">By journal name</span></span>
- <span data-ttu-id="bbd19-113">Napló fejléce szerint</span><span class="sxs-lookup"><span data-stu-id="bbd19-113">By journal header</span></span>

<span data-ttu-id="bbd19-114">A rendszer a napló fejlécében szereplő paraméterértékét használja véglegesként.</span><span class="sxs-lookup"><span data-stu-id="bbd19-114">System will take the parameter value on journal header as final.</span></span> <span data-ttu-id="bbd19-115">A napló fejlécének paraméter-értéke a napló nevéből származik.</span><span class="sxs-lookup"><span data-stu-id="bbd19-115">Parameter value on journal header will be defaulted from journal name.</span></span> <span data-ttu-id="bbd19-116">A napló nevének paraméter-értéke a főkönyvi paraméterből lesz származtatva a naplónév létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="bbd19-116">Parameter value on journal name will be defaulted from general ledger parameter when the journal name is created.</span></span>

<span data-ttu-id="bbd19-117">A „tényleges áfaösszeg” és a „számított áfaösszeg" mező a naplóban elrejtésre kerül, ha a paraméter be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="bbd19-117">"Actual sales tax amount" and "Calculated sales tax amount" fields on journal will be hided if this parameter is turned on.</span></span> <span data-ttu-id="bbd19-118">A cél nem tévesztendő össze a felhasználóval, mert a két mező értéke mindig 0 lesz, mielőtt a felhasználó elindítja az adószámítást.</span><span class="sxs-lookup"><span data-stu-id="bbd19-118">The purpose is not to confuse user because the value of these two fields will always show 0 before user trigger the tax calculation.</span></span>

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a><span data-ttu-id="bbd19-119">A késleltetett adószámítás engedélyezése jogi személy szerint</span><span class="sxs-lookup"><span data-stu-id="bbd19-119">Enable delayed tax calculation by legal entity</span></span>

1. <span data-ttu-id="bbd19-120">Ugorjon a **Főkönyv > Főkönyv beállítás > Főkönyv paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="bbd19-120">Go to **General ledger > Ledger setup > General ledger parameters**</span></span>
2. <span data-ttu-id="bbd19-121">Kattintson az **Áfa** fülre.</span><span class="sxs-lookup"><span data-stu-id="bbd19-121">Click **Sales tax** tab</span></span>
3. <span data-ttu-id="bbd19-122">Az **Általános** gyorslap alatt megkeresheti a **Késleltetett adószámítás** paramétert, hogy be- vagy kikapcsolja azt.</span><span class="sxs-lookup"><span data-stu-id="bbd19-122">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a><span data-ttu-id="bbd19-123">Késleltetett adószámítás engedélyezése a naplónév szerint</span><span class="sxs-lookup"><span data-stu-id="bbd19-123">Enable delayed tax calculation by journal name</span></span>

1. <span data-ttu-id="bbd19-124">Ugorjon a **Főkönyv > Naplóbeállítások > Naplónevek** pontra.</span><span class="sxs-lookup"><span data-stu-id="bbd19-124">Go to **General ledger > Journal setup > Journal names**</span></span>
2. <span data-ttu-id="bbd19-125">Az **Általános** gyorslap alatt megkeresheti a **Késleltetett adószámítás** paramétert, hogy be- vagy kikapcsolja azt.</span><span class="sxs-lookup"><span data-stu-id="bbd19-125">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a><span data-ttu-id="bbd19-126">Késleltetett adó számításának engedélyezése napló szerint</span><span class="sxs-lookup"><span data-stu-id="bbd19-126">Enable delayed tax calculation by journal</span></span>

1. <span data-ttu-id="bbd19-127">Ugorjon a **Főkönyv > Naplóbejegyzések > Általános naplók** pontra.</span><span class="sxs-lookup"><span data-stu-id="bbd19-127">Go to **General ledger > Journal entries > General journals**</span></span>
2. <span data-ttu-id="bbd19-128">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="bbd19-128">Click **New**</span></span>
3. <span data-ttu-id="bbd19-129">Válasszon egy naplónevet.</span><span class="sxs-lookup"><span data-stu-id="bbd19-129">Select a journal name</span></span>
4. <span data-ttu-id="bbd19-130">Kattintson a **Beállítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="bbd19-130">Click **Setup**</span></span>
5. <span data-ttu-id="bbd19-131">Keresse meg a **Késleltetett adószámítás** paramétert, hogy be- vagy kikapcsolja azt.</span><span class="sxs-lookup"><span data-stu-id="bbd19-131">Find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-header.png)
