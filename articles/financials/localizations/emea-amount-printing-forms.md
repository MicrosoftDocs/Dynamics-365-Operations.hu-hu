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
ms.search.form: Currency
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264254
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: daa9443c5676189a771dc3af745e7d26aa0b32f3
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a><span data-ttu-id="93a90-103">Jelentések és dokumentumok összegformátumának megjelenítésének módosítása</span><span class="sxs-lookup"><span data-stu-id="93a90-103">Update how amounts are displayed on reports and documents</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="93a90-104">Ez a témakör a jelentésekben és egyéb dokumentumokban megjelenített összegek frissítésének módjáról tartalmaz információkat Észtország, Lettország, Litvánia, Lengyelország, Csehország, Magyarország és Oroszország tekintetében.</span><span class="sxs-lookup"><span data-stu-id="93a90-104">This topic provides information about how to update how amounts are displayed on reports and other documents for Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia.</span></span>

<span data-ttu-id="93a90-105">Az Észtország, Lettország, Litvánia, Lengyelország, Csehország, Magyarország és Oroszország területén működő jogi személyeknél beállítható teljes név és rövid név a valutaegységekhez és alegységekhez.</span><span class="sxs-lookup"><span data-stu-id="93a90-105">For legal entities in Estonia, Latvia, Lithuania, Poland, Czech Republic, Hungary, and Russia, you can set up full names and short names for currency units and subunits.</span></span> <span data-ttu-id="93a90-106">Ezek a nevek használhatók annak átalakításához, hogy hogyan hogyan jelennek meg az összegek a dokumentumokban és jelentésekben.</span><span class="sxs-lookup"><span data-stu-id="93a90-106">These names can be used to transform how amounts are represented on documents and reports.</span></span> <span data-ttu-id="93a90-107">Például: az **LTL 100.20** összeg megjeleníthető úgy, hogy **100 Litas 20 Centas**.</span><span class="sxs-lookup"><span data-stu-id="93a90-107">For example: The amount **LTL 100.20** can be displayed as **100 Litas 20 Centas**.</span></span>

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a><span data-ttu-id="93a90-108">Pénzegységek és részegységek teljes és rövid nevének beállítása</span><span class="sxs-lookup"><span data-stu-id="93a90-108">Set up full and short names for currency units and subunits</span></span>
<span data-ttu-id="93a90-109">Pénzegységek teljes és rövid nevének és nyelvek részegységeinek beállításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="93a90-109">To set up full and short names for currency units and subunits for a language, complete the following steps:</span></span>

1. <span data-ttu-id="93a90-110">Nyissa meg a **Pénznemek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="93a90-110">Open the **Currencies** page.</span></span>
2. <span data-ttu-id="93a90-111">Válassza ki a pénznemet.</span><span class="sxs-lookup"><span data-stu-id="93a90-111">Select a currency.</span></span>
3. <span data-ttu-id="93a90-112">A Művelet panelen kattintson a **Ragozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="93a90-112">On the Action Pane, click **Declension**.</span></span>
4. <span data-ttu-id="93a90-113">Egy nyelvhez teljes név és rövid név hozzáadásához kattintson a **Új** elemre, és töltse ki a következő mezőket.</span><span class="sxs-lookup"><span data-stu-id="93a90-113">To add full name and short name for a language, click **New** and complete the following fields.</span></span>

   |                                                                        |                                                                                                                                                                                                                                                                        |
   |------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                         <span data-ttu-id="93a90-114"><strong>Mező</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-114"><strong>Field</strong></span></span>                         |                                                                                                                      <span data-ttu-id="93a90-115"><strong>Leírás</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-115"><strong>Description</strong></span></span>                                                                                                                      |
   |                       <span data-ttu-id="93a90-116"><strong>Nyelv</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-116"><strong>Language</strong></span></span>                        |                                                                                                               <span data-ttu-id="93a90-117">Adja meg az aktuális szöveg nyelvét.</span><span class="sxs-lookup"><span data-stu-id="93a90-117">Select the language for the current text.</span></span>                                                                                                                |
   |    <span data-ttu-id="93a90-118"><strong>Egyes szám alanyeset (Egységek mezőcsoport neve)</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-118"><strong>Singular nominative (Name of units field group)</strong></span></span>    |                                                                                       <span data-ttu-id="93a90-119">Adja meg a pénznem egyes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="93a90-119">Enter the singular form of the currency.</span></span> <span data-ttu-id="93a90-120">Például a Litas egyes számának formája Litas.</span><span class="sxs-lookup"><span data-stu-id="93a90-120">For example, the singular form of Litas is Litas.</span></span>                                                                                       |
   |     <span data-ttu-id="93a90-121"><strong>Többes szám alanyeset (Egységek mezőcsoport neve)</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-121"><strong>Plural nominative (Name of units field group)</strong></span></span>     | <span data-ttu-id="93a90-122">Adja meg a pénznem többes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="93a90-122">Enter the plural form of the currency.</span></span> <span data-ttu-id="93a90-123">Például írja be azt, hogy Litai.</span><span class="sxs-lookup"><span data-stu-id="93a90-123">For example, enter Litai.</span></span> <span data-ttu-id="93a90-124"><strong>Megjegyzés:</strong>: az <strong>Egyes szám birtokos eset</strong> és a <strong>Többes szám birtokos eset</strong> mezők a <strong>Nyelv</strong> mezőben kiválasztott nyelv alapján állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="93a90-124"><strong>Note</strong>: The <strong>Singular genitive</strong> and <strong>Plural genitive</strong> fields are available based on the language that you select in the <strong>Language</strong> field.</span></span> |
   | <span data-ttu-id="93a90-125"><strong>Egyes szám alanyeset mező (Részek mezőcsoport neve)</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-125"><strong>Singular nominative field (Name of parts field group)</strong></span></span> |                                                                                                        <span data-ttu-id="93a90-126">Adja meg a pénznem alegységének egyes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="93a90-126">Enter the singular form of the subunit of the currency.</span></span>                                                                                                         |
   |     <span data-ttu-id="93a90-127"><strong>Többes szám alanyeset (Részek mezőcsoport neve)</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-127"><strong>Plural nominative (Name of parts field group)</strong></span></span>     |                                                                                                         <span data-ttu-id="93a90-128">Adja meg a pénznem alegységének többes számú formáját.</span><span class="sxs-lookup"><span data-stu-id="93a90-128">Enter the plural form of the subunit of the currency.</span></span>                                                                                                          |
   |    <span data-ttu-id="93a90-129"><strong>Egységek rövidített neve (Mezőcsoport rövid neve)</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-129"><strong>Shortcut name of units (Short name field group)</strong></span></span>    |                                                                                         <span data-ttu-id="93a90-130">Adja meg a pénznem azonosítására szolgáló ISO-kódot.</span><span class="sxs-lookup"><span data-stu-id="93a90-130">Enter the ISO code to identify the currency.</span></span> <span data-ttu-id="93a90-131">Például a litván litas azonosítására az LTL karaktersort adja meg.</span><span class="sxs-lookup"><span data-stu-id="93a90-131">For example, enter LTL to identify Litas.</span></span>                                                                                         |
   |   <span data-ttu-id="93a90-132"><strong>Részek rövidített neve (Mezőcsoport rövid neve)</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-132"><strong>Shortcut name for parts (Short name field group)</strong></span></span>    |                                                                                               <span data-ttu-id="93a90-133">Adja meg a pénznem alegységének megnevezését.</span><span class="sxs-lookup"><span data-stu-id="93a90-133">Enter the denomination of the currency subunit.</span></span> <span data-ttu-id="93a90-134">Például írja be azt, hogy Centas.</span><span class="sxs-lookup"><span data-stu-id="93a90-134">For example, enter Centas.</span></span>                                                                                               |
   |       <span data-ttu-id="93a90-135"><strong>„És” kapcsolat az egységek és részek között</strong></span><span class="sxs-lookup"><span data-stu-id="93a90-135"><strong>Conjunction 'and' between units and parts</strong></span></span>       |                                     <span data-ttu-id="93a90-136">Jelölje be a pénzegységek és egységrészek közötti „és” kapcsolat kinyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="93a90-136">Select to print the conjunction “and” between the currency units and unit parts.</span></span> <span data-ttu-id="93a90-137">A 100,20 LTL összeg például így „100 litas és 20 centas” formában jelenik meg a számlákon és jelentéseken.</span><span class="sxs-lookup"><span data-stu-id="93a90-137">For example, on invoices or reports, the amount for LTL 100.20 will be displayed as 100 Litas and 20 Centas.</span></span>                                      |


5. <span data-ttu-id="93a90-138">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="93a90-138">Click **Save**.</span></span>





