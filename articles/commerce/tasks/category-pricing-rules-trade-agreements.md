---
title: " Kategória-árazási szabályok kereskedelmi megállapodások létrehozásához"
description: Ez az eljárás bemutatja, hogyan hozhat létre eladási árra vonatkozó kereskedelmi megállapodásokat egy kategória-árazási szabály használatával.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPricingDiscountCategoryPriceRule, RetailCategoryPriceRule, EcoResCategorySingleLookup, RetailCategoryPriceWizard, PriceDiscAdm, PriceDiscAdmTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35c85e6e3bbdc913e9cd7aefdf6b143f3f03496f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022788"
---
# <a name="category-pricing-rules-to-create-trade-agreements"></a><span data-ttu-id="bf3f8-103"> Kategória-árazási szabályok kereskedelmi megállapodások létrehozásához</span><span class="sxs-lookup"><span data-stu-id="bf3f8-103">Category pricing rules to create trade agreements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="bf3f8-104">Ez az eljárás bemutatja, hogyan hozhat létre eladási árra vonatkozó kereskedelmi megállapodásokat egy kategória-árazási szabály használatával.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-104">This procedure demonstrates how to create sales price trade agreements using a category pricing rule.</span></span> <span data-ttu-id="bf3f8-105">A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="bf3f8-106">A feladat a Kereskedelmi termékkihelyezési vezető szerepkör számára készült.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-106">This task is intended for the Commerce merchandising manager role.</span></span>

1. <span data-ttu-id="bf3f8-107">Kattintson az Árképzés és engedmények kezelése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="bf3f8-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-108">Click New.</span></span>
3. <span data-ttu-id="bf3f8-109">Kattintson a Kategória árszabálya lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-109">Click Category price rule.</span></span>
4. <span data-ttu-id="bf3f8-110">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-110">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="bf3f8-111">A Számlakód mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-111">In the Account code field, select an option.</span></span>
    * <span data-ttu-id="bf3f8-112">A „Csoport” típusú számlakód adott Csatornákhoz, Hűségprogramokhoz, Katalógusokhoz és Fiókokhoz tartozó, eladási árra vonatkozó kereskedelmi megállapodások beállítására használható.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-112">A "Group" type account code is used to set up sales price trade agreements that are specific for Channels, Loyalty programs, Catalogs, and Affiliations.</span></span>  
6. <span data-ttu-id="bf3f8-113">A Számla kiválasztása mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-113">In the Account selection field, enter or select a value.</span></span>
7. <span data-ttu-id="bf3f8-114">A Kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-114">In the Category field, enter or select a value.</span></span>
8. <span data-ttu-id="bf3f8-115">Az Összeg/százalék mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-115">In the Amount/Percent field, enter a number.</span></span>
9. <span data-ttu-id="bf3f8-116">A Kerekítési verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-116">In the Rounding version field, enter or select a value.</span></span>
10. <span data-ttu-id="bf3f8-117">Kattintson a Kereskedelmi megállapodások előállítása gombra.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-117">Click Generate trade agreements.</span></span>
11. <span data-ttu-id="bf3f8-118">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-118">Click Next.</span></span>
12. <span data-ttu-id="bf3f8-119">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-119">In the From date field, enter a date.</span></span>
13. <span data-ttu-id="bf3f8-120">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-120">In the To date field, enter a date.</span></span>
14. <span data-ttu-id="bf3f8-121">Válassza ki az Igen lehetőséget a Következő keresése mezőben.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-121">Select Yes in the Find next field.</span></span>
15. <span data-ttu-id="bf3f8-122">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-122">Click Next.</span></span>
16. <span data-ttu-id="bf3f8-123">Kattintson a Finish gombra.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-123">Click Finish.</span></span>
    * <span data-ttu-id="bf3f8-124">Ez létrehoz egy Kereskedelmi megállapodási naplót, és megnyitja azt ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-124">This creates a Trade agreement journal and opens it for your review.</span></span>  
17. <span data-ttu-id="bf3f8-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bf3f8-126">A Kategória-árazási szabályokból létrehozott Kereskedelmi megállapodási naplók nem kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-126">The trade agreement journals created from the Category pricing rules aren't posted.</span></span> <span data-ttu-id="bf3f8-127">A feladás előtt ellenőrizheti és szerkesztheti a generált árakat.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-127">You can  review and edit the prices generated before posting them.</span></span>  
18. <span data-ttu-id="bf3f8-128">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-128">Click Edit.</span></span>
19. <span data-ttu-id="bf3f8-129">Az Összeg devizában mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-129">In the Amount in currency field, enter a number.</span></span>
20. <span data-ttu-id="bf3f8-130">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-130">Click Post.</span></span>
21. <span data-ttu-id="bf3f8-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-131">Click OK.</span></span>
22. <span data-ttu-id="bf3f8-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-132">Close the page.</span></span>
23. <span data-ttu-id="bf3f8-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-133">Close the page.</span></span>
24. <span data-ttu-id="bf3f8-134">Kattintson a Kategória árszabályai fülre.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-134">Click the Category price rules tab.</span></span>
    * <span data-ttu-id="bf3f8-135">Ebben a listában megjelennek a csatornaspecifikus Kategória-árazási szabályok.</span><span class="sxs-lookup"><span data-stu-id="bf3f8-135">Channel specific Category pricing rules will show in this list.</span></span>  
