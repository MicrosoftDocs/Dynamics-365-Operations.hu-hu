---
title: Adóelőleg beállítása
description: Az adóelőleg a szállítókra kirótt olyan adó, amely nem hoz létre áfatranzakciókat.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 382b6332665af2491563960a75d498a4f007aba8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "337233"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="91b4c-103">Adóelőleg beállítása</span><span class="sxs-lookup"><span data-stu-id="91b4c-103">Set up withholding tax</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91b4c-104">Az adóelőleg a szállítókra kirótt olyan adó, amely nem hoz létre áfatranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="91b4c-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="91b4c-105">A szállítói kifizetésekhez számított adóelőleg kötelezettség.</span><span class="sxs-lookup"><span data-stu-id="91b4c-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="91b4c-106">Emiatt az adóelőlegeket csak mérlegszámlákra vagy forrásszámlákra lehet érvényesen feladni.</span><span class="sxs-lookup"><span data-stu-id="91b4c-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="91b4c-107">Ez a feladatútmutató bemutatja, hogyan lehet adóelőleget beállítani.</span><span class="sxs-lookup"><span data-stu-id="91b4c-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="91b4c-108">Ugorjon az Adó > Közvetett adók > Adóelőleg > Adóelőlegkódok elemre.</span><span class="sxs-lookup"><span data-stu-id="91b4c-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="91b4c-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91b4c-109">Click New.</span></span>
3. <span data-ttu-id="91b4c-110">Az Adóelőlegkód kód mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="91b4c-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="91b4c-111">Az Adóelőleg-név mezőben adja meg az adóelőlegkód nevét.</span><span class="sxs-lookup"><span data-stu-id="91b4c-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="91b4c-112">A Fő számla mezőben válassza ki a fő számlát az adóelőleg-kötelezettség feladására.</span><span class="sxs-lookup"><span data-stu-id="91b4c-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="91b4c-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="91b4c-113">Click Save.</span></span>
7. <span data-ttu-id="91b4c-114">Kattintson az Értékekre.</span><span class="sxs-lookup"><span data-stu-id="91b4c-114">Click Values.</span></span>
8. <span data-ttu-id="91b4c-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="91b4c-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="91b4c-116">Az Érték mezőben adja meg az adóelőleg számításához használt százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="91b4c-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="91b4c-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="91b4c-117">Click Save.</span></span>
11. <span data-ttu-id="91b4c-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="91b4c-118">Close the page.</span></span>
12. <span data-ttu-id="91b4c-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="91b4c-119">Click Save.</span></span>
13. <span data-ttu-id="91b4c-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="91b4c-120">Close the page.</span></span>
14. <span data-ttu-id="91b4c-121">Ugorjon az Adó > Közvetett adók > Adóelőleg > Adóelőlegcsoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="91b4c-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="91b4c-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91b4c-122">Click New.</span></span>
16. <span data-ttu-id="91b4c-123">Az Adóelőleg-csoport mezőben adja meg az adóelőlegcsoport azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="91b4c-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="91b4c-124">A Leírás mezőben adja meg az adóelőlegcsoport nevét.</span><span class="sxs-lookup"><span data-stu-id="91b4c-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="91b4c-125">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="91b4c-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="91b4c-126">Az Adóelőlegkód mezőben válassza ki az adóelőlegkódot.</span><span class="sxs-lookup"><span data-stu-id="91b4c-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="91b4c-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="91b4c-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="91b4c-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="91b4c-128">Click Save.</span></span>

