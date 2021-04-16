---
title: Adócsoportok és cikkáfacsoportok beállítása
description: Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 844eee7f81c64eb50ada44cbc151c8aa00c5ae98
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815068"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="0a7d8-103">Adócsoportok és cikkáfacsoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="0a7d8-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0a7d8-104">Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="0a7d8-105">Az áfacsoportok a vevőkhöz és szállítókhoz társított áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="0a7d8-106">Főkönyvi számlákhoz is hozzá vannak rendelve olyan tranzakcióknál, amelyek nem kerülnek feladásra konkrét szállítóra vagy vevőre.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="0a7d8-107">A Cikkáfacsoportok az erőforrásokhoz, például termékekhez rendelt áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="0a7d8-108">Az egyes tranzakciókra alkalmazandó áfakódok azok az áfakódok, amelyek mind az áfacsoportban, mind a tranzakció cikkáfacsoportjában szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="0a7d8-109">Az áfa kiszámításához szükséges, hogy minden olyan tranzakciónál, amelyre áfát kell számítani vagy rögzíteni, ki legyen választva egy áfacsoport és egy cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="0a7d8-110">Ugorjon a **Navigációs ablaktábla >Modulok > Adók > Közvetett adók > Áfa > Áfacsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="0a7d8-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-111">Click **New**.</span></span>
3. <span data-ttu-id="0a7d8-112">Az **Áfacsoport** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="0a7d8-113">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="0a7d8-114">Váltsa át a **Beállítás** szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="0a7d8-115">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-115">Click **Add**.</span></span>
7. <span data-ttu-id="0a7d8-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="0a7d8-117">Az **Áfakód** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="0a7d8-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="0a7d8-119">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-119">Click **Save**.</span></span>
11. <span data-ttu-id="0a7d8-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-120">Close the page.</span></span>
12. <span data-ttu-id="0a7d8-121">Ugorjon az **Adó > Közvetett adók > Áfa > Áfacsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="0a7d8-122">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-122">Click **New**.</span></span>
14. <span data-ttu-id="0a7d8-123">A **Cikkáfacsoport** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="0a7d8-124">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="0a7d8-125">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-125">Click **Add**.</span></span>
17. <span data-ttu-id="0a7d8-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="0a7d8-127">Az **Áfakód** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="0a7d8-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="0a7d8-129">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="0a7d8-129">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]