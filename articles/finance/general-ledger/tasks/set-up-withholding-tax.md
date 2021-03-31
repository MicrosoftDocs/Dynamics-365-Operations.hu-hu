---
title: Adóelőleg beállítása
description: Ez a témakör bemutatja, hogyan állíthatja be az adóelőlegeket.
author: twheeloc
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ae7b13f743336e01f17248c8d6492b31e8044ef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222311"
---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="335fd-103">Adóelőleg beállítása</span><span class="sxs-lookup"><span data-stu-id="335fd-103">Set up withholding tax</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="335fd-104">Ez a témakör bemutatja, hogyan állíthatja be az adóelőlegeket.</span><span class="sxs-lookup"><span data-stu-id="335fd-104">This topic explains how to set up withholding tax.</span></span> <span data-ttu-id="335fd-105">Az *Adóelőleg* a szállítókra kirótt olyan adó, amely nem hoz létre áfatranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="335fd-105">*Withholding tax* is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="335fd-106">A szállítói kifizetésekhez számított adóelőleg kötelezettség.</span><span class="sxs-lookup"><span data-stu-id="335fd-106">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="335fd-107">Emiatt az adóelőlegeket csak mérlegszámlákra vagy forrásszámlákra lehet érvényesen feladni.</span><span class="sxs-lookup"><span data-stu-id="335fd-107">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="335fd-108">Ez a feladatútmutató bemutatja, hogyan lehet adóelőleget beállítani.</span><span class="sxs-lookup"><span data-stu-id="335fd-108">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="335fd-109">Ugorjon a **Navigációs ablaktábla > Modulok > Adó > Közvetett adók > Adóelőleg > Adóelőlegkódok elemre.**</span><span class="sxs-lookup"><span data-stu-id="335fd-109">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax codes**.</span></span>
2. <span data-ttu-id="335fd-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="335fd-110">Select **New**.</span></span>
3. <span data-ttu-id="335fd-111">Az **Adóelőlegkód kód** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="335fd-111">In the **Withholding tax code** field, type a value.</span></span>
4. <span data-ttu-id="335fd-112">Az **Adóelőleg-név mezőben** adja meg az adóelőlegkód nevét.</span><span class="sxs-lookup"><span data-stu-id="335fd-112">In the **Withholding tax name** field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="335fd-113">A **Fő számla mezőben** válassza ki a fő számlát az adóelőleg-kötelezettség feladására.</span><span class="sxs-lookup"><span data-stu-id="335fd-113">In the **Main account** field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="335fd-114">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="335fd-114">Select **Save**.</span></span>
7. <span data-ttu-id="335fd-115">Válassza ki az **Értékek** elemet, és jelölje ki a kívánt rekordot a listában.</span><span class="sxs-lookup"><span data-stu-id="335fd-115">Select **Values** and mark the desired record in the list.</span></span>
8. <span data-ttu-id="335fd-116">Az **Érték** mezőben adja meg az adóelőleg számításához használt százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="335fd-116">In the **Value** field, enter a percentage used for the calculation of the withholding tax.</span></span>
9. <span data-ttu-id="335fd-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="335fd-117">Select **Save**.</span></span>
10. <span data-ttu-id="335fd-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="335fd-118">Close the page.</span></span>
11. <span data-ttu-id="335fd-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="335fd-119">Select **Save**.</span></span>
12. <span data-ttu-id="335fd-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="335fd-120">Close the page.</span></span>
13. <span data-ttu-id="335fd-121">Ugorjon a **Navigációs ablaktábla > Modulok > Adó > Közvetett adók > Adóelőleg > Adóelőleg-csoportok elemre.**</span><span class="sxs-lookup"><span data-stu-id="335fd-121">Go to **Navigation pane > Modules > Tax > Indirect taxes > Withholding tax > Withholding tax groups**.</span></span>
14. <span data-ttu-id="335fd-122">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="335fd-122">Select **New**.</span></span>
15. <span data-ttu-id="335fd-123">Az **Adóelőleg-csoport** mezőben adja meg az adóelőleg-csoport azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="335fd-123">In the **Withholding tax group** field, enter the identifier of the withholding tax group.</span></span>
16. <span data-ttu-id="335fd-124">A **Leírás** mezőben adja meg az adóelőleg-csoport nevét.</span><span class="sxs-lookup"><span data-stu-id="335fd-124">In the **Description** field, enter the name of the withholding tax group.</span></span>
17. <span data-ttu-id="335fd-125">Az **Adóelőlegkód** mezőben válassza ki az adóelőlegkódot.</span><span class="sxs-lookup"><span data-stu-id="335fd-125">In the **Withholding tax code** field, select the withholding tax code.</span></span>
18. <span data-ttu-id="335fd-126">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="335fd-126">Select **Save**.</span></span>
19. <span data-ttu-id="335fd-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="335fd-127">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]