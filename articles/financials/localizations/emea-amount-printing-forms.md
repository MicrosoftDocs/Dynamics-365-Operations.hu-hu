---
title: "Jelentések és dokumentumok összegformátumának megjelenítésének módosítása"
description: "Ez a témakör a jelentésekben és egyéb dokumentumokban megjelenített összegek frissítésének módjáról tartalmaz információkat Észtország, Lettország, Litvánia, Lengyelország, Csehország, Magyarország és Oroszország tekintetében."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264254
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a9e63af61b42ef3f5ef1d05a659cbec572e04a4f
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a><span data-ttu-id="c898e-103">Jelentések és dokumentumok összegformátumának megjelenítésének módosítása</span><span class="sxs-lookup"><span data-stu-id="c898e-103">Update how amounts are displayed on reports and documents</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c898e-104">Ez a témakör a jelentésekben és egyéb dokumentumokban megjelenített összegek frissítésének módjáról tartalmaz információkat Észtország, Lettország, Litvánia, Lengyelország, Csehország, Magyarország és Oroszország tekintetében.</span><span class="sxs-lookup"><span data-stu-id="c898e-104">This topic provides information about how to update how amounts are displayed on reports and other documents for Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia.</span></span>

<span data-ttu-id="c898e-105">Az Észtország, Lettország, Litvánia, Lengyelország, Csehország, Magyarország és Oroszország területén működő jogi személyeknél beállítható teljes név és rövid név a valutaegységekhez és alegységekhez.</span><span class="sxs-lookup"><span data-stu-id="c898e-105">For legal entities in Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia, you can set up full names and short names for currency units and subunits.</span></span> <span data-ttu-id="c898e-106">Ezek a nevek használhatók annak átalakításához, hogy hogyan hogyan jelennek meg az összegek a dokumentumokban és jelentésekben.</span><span class="sxs-lookup"><span data-stu-id="c898e-106">These names can be used to transform how amounts are represented on documents and reports.</span></span> <span data-ttu-id="c898e-107">Például: az **LTL 100.20** összeg megjeleníthető úgy, hogy **100 Litas 20 Centas**.</span><span class="sxs-lookup"><span data-stu-id="c898e-107">For example: The amount **LTL 100.20** can be displayed as **100 Litas 20 Centas**.</span></span>

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a><span data-ttu-id="c898e-108">Pénzegységek és részegységek teljes és rövid nevének beállítása</span><span class="sxs-lookup"><span data-stu-id="c898e-108">Set up full and short names for currency units and subunits</span></span>
<span data-ttu-id="c898e-109">Pénzegységek teljes és rövid nevének és nyelvek részegységeinek beállításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="c898e-109">To set up full and short names for currency units and subunits for a language, complete the following steps:</span></span>

1.  <span data-ttu-id="c898e-110">Nyissa meg a **Pénznemek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="c898e-110">Open the **Currencies** page.</span></span>
2.  <span data-ttu-id="c898e-111">Válassza ki a pénznemet.</span><span class="sxs-lookup"><span data-stu-id="c898e-111">Select a currency.</span></span>
3.  <span data-ttu-id="c898e-112">A Művelet panelen kattintson a **Ragozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="c898e-112">On the Action Pane, click **Declension**.</span></span>
4.  <span data-ttu-id="c898e-113">Egy nyelvhez teljes név és rövid név hozzáadásához kattintson a **Új** elemre, és töltse ki a következő mezőket.</span><span class="sxs-lookup"><span data-stu-id="c898e-113">To add full name and short name for a language, click **New** and complete the following fields.</span></span>
    |                                                           |                                                                                                                                                                                                                    |
    |-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="c898e-114">**Mező**</span><span class="sxs-lookup"><span data-stu-id="c898e-114">**Field**</span></span>                                                 | <span data-ttu-id="c898e-115">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="c898e-115">**Description**</span></span>                                                                                                                                                                                                    |
    | <span data-ttu-id="c898e-116">**Nyelv**</span><span class="sxs-lookup"><span data-stu-id="c898e-116">**Language**</span></span>                                              | <span data-ttu-id="c898e-117">Adja meg az aktuális szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="c898e-117">Select the language for the current text.</span></span>                                                                                                                                                                          |
    | <span data-ttu-id="c898e-118">**Egyes szám alanyeset (Egységek mezőcsoport neve)**</span><span class="sxs-lookup"><span data-stu-id="c898e-118">**Singular nominative (Name of units field group)**</span></span>       | <span data-ttu-id="c898e-119">Adja meg a pénznem egyes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="c898e-119">Enter the singular form of the currency.</span></span> <span data-ttu-id="c898e-120">Például a Litas egyes számának formája Litas.</span><span class="sxs-lookup"><span data-stu-id="c898e-120">For example, the singular form of Litas is Litas.</span></span>                                                                                                                         |
    | <span data-ttu-id="c898e-121">**Többes szám alanyeset (Egységek mezőcsoport neve)**</span><span class="sxs-lookup"><span data-stu-id="c898e-121">**Plural nominative (Name of units field group)**</span></span>         | <span data-ttu-id="c898e-122">Adja meg a pénznem többes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="c898e-122">Enter the plural form of the currency.</span></span> <span data-ttu-id="c898e-123">Például írja be azt, hogy Litai.</span><span class="sxs-lookup"><span data-stu-id="c898e-123">For example, enter Litai.</span></span> <span data-ttu-id="c898e-124">**Megjegyzés:**: az **Egyes szám birtokos eset** és a **Többes szám birtokos eset** mezők a **Nyelv** mezőben kiválasztott nyelv alapján állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="c898e-124">**Note**: The **Singular genitive** and **Plural genitive** fields are available based on the language that you select in the **Language** field.</span></span> |
    | <span data-ttu-id="c898e-125">**Egyes szám alanyeset mező (Részek mezőcsoport neve)**</span><span class="sxs-lookup"><span data-stu-id="c898e-125">**Singular nominative field (Name of parts field group)**</span></span> | <span data-ttu-id="c898e-126">Adja meg a pénznem alegységének egyes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="c898e-126">Enter the singular form of the subunit of the currency.</span></span>                                                                                                                                                            |
    | <span data-ttu-id="c898e-127">**Többes szám alanyeset (Részek mezőcsoport neve)**</span><span class="sxs-lookup"><span data-stu-id="c898e-127">**Plural nominative (Name of parts field group)**</span></span>         | <span data-ttu-id="c898e-128">Adja meg a pénznem alegységének többes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="c898e-128">Enter the plural form of the subunit of the currency.</span></span>                                                                                                                                                              |
    | <span data-ttu-id="c898e-129">**Egységek rövidített neve (Mezőcsoport rövid neve)**</span><span class="sxs-lookup"><span data-stu-id="c898e-129">**Shortcut name of units (Short name field group)**</span></span>       | <span data-ttu-id="c898e-130">Adja meg a pénznem azonosítására szolgáló ISO-kódot.</span><span class="sxs-lookup"><span data-stu-id="c898e-130">Enter the ISO code to identify the currency.</span></span> <span data-ttu-id="c898e-131">Például a litván litas azonosítására az LTL karaktersort adja meg.</span><span class="sxs-lookup"><span data-stu-id="c898e-131">For example, enter LTL to identify Litas.</span></span>                                                                                                                             |
    | <span data-ttu-id="c898e-132">**Részek rövidített neve (Mezőcsoport rövid neve)**</span><span class="sxs-lookup"><span data-stu-id="c898e-132">**Shortcut name for parts (Short name field group)**</span></span>      | <span data-ttu-id="c898e-133">Adja meg a pénznem alegységének megnevezését.</span><span class="sxs-lookup"><span data-stu-id="c898e-133">Enter the denomination of the currency subunit.</span></span> <span data-ttu-id="c898e-134">Például írja be azt, hogy Centas.</span><span class="sxs-lookup"><span data-stu-id="c898e-134">For example, enter Centas.</span></span>                                                                                                                                         |
    | <span data-ttu-id="c898e-135">**„És” kapcsolat az egységek és részek között**</span><span class="sxs-lookup"><span data-stu-id="c898e-135">**Conjunction 'and' between units and parts**</span></span>             | <span data-ttu-id="c898e-136">Jelölje be a pénzegységek és egységrészek közötti „és” kapcsolat kinyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="c898e-136">Select to print the conjunction “and” between the currency units and unit parts.</span></span> <span data-ttu-id="c898e-137">A 100,20 LTL összeg például így „100 litas és 20 centas” formában jelenik meg a számlákon és jelentéseken.</span><span class="sxs-lookup"><span data-stu-id="c898e-137">For example, on invoices or reports, the amount for LTL 100.20 will be displayed as 100 Litas and 20 Centas.</span></span>                      |

5.  <span data-ttu-id="c898e-138">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="c898e-138">Click **Save**.</span></span>





