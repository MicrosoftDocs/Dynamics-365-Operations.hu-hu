---
title: Adócsoportok és cikkáfacsoportok beállítása
description: Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.
author: twheeloc
manager: AnnBe
ms.date: 07-01-2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a5b539129e62b9b0b10df1f505cbfec5c1143138
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141626"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="1e022-103">Adócsoportok és cikkáfacsoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="1e022-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e022-104">Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.</span><span class="sxs-lookup"><span data-stu-id="1e022-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="1e022-105">Az áfacsoportok a vevőkhöz és szállítókhoz társított áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="1e022-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="1e022-106">Főkönyvi számlákhoz is hozzá vannak rendelve olyan tranzakcióknál, amelyek nem kerülnek feladásra konkrét szállítóra vagy vevőre.</span><span class="sxs-lookup"><span data-stu-id="1e022-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="1e022-107">A Cikkáfacsoportok az erőforrásokhoz, például termékekhez rendelt áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="1e022-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="1e022-108">Az egyes tranzakciókra alkalmazandó áfakódok azok az áfakódok, amelyek mind az áfacsoportban, mind a tranzakció cikkáfacsoportjában szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="1e022-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="1e022-109">Az áfa kiszámításához szükséges, hogy minden olyan tranzakciónál, amelyre áfát kell számítani vagy rögzíteni, ki legyen választva egy áfacsoport és egy cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="1e022-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="1e022-110">Ugorjon a **Navigációs ablaktábla >Modulok > Adók > Közvetett adók > Áfa > Áfacsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1e022-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="1e022-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1e022-111">Click **New**.</span></span>
3. <span data-ttu-id="1e022-112">Az **Áfacsoport** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1e022-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="1e022-113">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1e022-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="1e022-114">Váltsa át a **Beállítás** szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="1e022-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="1e022-115">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1e022-115">Click **Add**.</span></span>
7. <span data-ttu-id="1e022-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1e022-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="1e022-117">Az **Áfakód** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e022-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="1e022-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e022-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1e022-119">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1e022-119">Click **Save**.</span></span>
11. <span data-ttu-id="1e022-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1e022-120">Close the page.</span></span>
12. <span data-ttu-id="1e022-121">Ugorjon az **Adó > Közvetett adók > Áfa > Áfacsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="1e022-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="1e022-122">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="1e022-122">Click **New**.</span></span>
14. <span data-ttu-id="1e022-123">A **Cikkáfacsoport** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1e022-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="1e022-124">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1e022-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="1e022-125">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="1e022-125">Click **Add**.</span></span>
17. <span data-ttu-id="1e022-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1e022-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="1e022-127">Az **Áfakód** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="1e022-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="1e022-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="1e022-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="1e022-129">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="1e022-129">Click **Save**.</span></span>

