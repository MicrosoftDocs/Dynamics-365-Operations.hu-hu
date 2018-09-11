--- 
title: "Adóelőleg beállítása"
description: "Az adóelőleg a szállítókra kirótt olyan adó, amely nem hoz létre áfatranzakciókat."
author: twheeloc
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: a2867bcbef7aa9e41b35603276742be448317221
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="e8a0f-103">Adóelőleg beállítása</span><span class="sxs-lookup"><span data-stu-id="e8a0f-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e8a0f-104">Az adóelőleg a szállítókra kirótt olyan adó, amely nem hoz létre áfatranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="e8a0f-105">A szállítói kifizetésekhez számított adóelőleg kötelezettség.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="e8a0f-106">Emiatt az adóelőlegeket csak mérlegszámlákra vagy forrásszámlákra lehet érvényesen feladni.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="e8a0f-107">Ez a feladatútmutató bemutatja, hogyan lehet adóelőleget beállítani.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="e8a0f-108">Ugorjon az Adó > Közvetett adók > Adóelőleg > Adóelőlegkódok elemre.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="e8a0f-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-109">Click New.</span></span>
3. <span data-ttu-id="e8a0f-110">Az Adóelőlegkód kód mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="e8a0f-111">Az Adóelőleg-név mezőben adja meg az adóelőlegkód nevét.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="e8a0f-112">A Fő számla mezőben válassza ki a fő számlát az adóelőleg-kötelezettség feladására.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="e8a0f-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-113">Click Save.</span></span>
7. <span data-ttu-id="e8a0f-114">Kattintson az Értékekre.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-114">Click Values.</span></span>
8. <span data-ttu-id="e8a0f-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="e8a0f-116">Az Érték mezőben adja meg az adóelőleg számításához használt százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="e8a0f-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-117">Click Save.</span></span>
11. <span data-ttu-id="e8a0f-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-118">Close the page.</span></span>
12. <span data-ttu-id="e8a0f-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-119">Click Save.</span></span>
13. <span data-ttu-id="e8a0f-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-120">Close the page.</span></span>
14. <span data-ttu-id="e8a0f-121">Ugorjon az Adó > Közvetett adók > Adóelőleg > Adóelőlegcsoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="e8a0f-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-122">Click New.</span></span>
16. <span data-ttu-id="e8a0f-123">Az Adóelőleg-csoport mezőben adja meg az adóelőlegcsoport azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="e8a0f-124">A Leírás mezőben adja meg az adóelőlegcsoport nevét.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="e8a0f-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="e8a0f-126">Az Adóelőlegkód mezőben válassza ki az adóelőlegkódot.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="e8a0f-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="e8a0f-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e8a0f-128">Click Save.</span></span>


