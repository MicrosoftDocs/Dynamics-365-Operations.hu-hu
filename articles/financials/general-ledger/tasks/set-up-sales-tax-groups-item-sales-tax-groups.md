---
title: Adócsoportok és cikkáfacsoportok beállítása
description: Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec5bbe37aa06f18172c417e903538cadc8a6f312
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559411"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="9d979-103">Adócsoportok és cikkáfacsoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="9d979-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9d979-104">Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.</span><span class="sxs-lookup"><span data-stu-id="9d979-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="9d979-105">Az áfacsoportok a vevőkhöz és szállítókhoz társított áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="9d979-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="9d979-106">Főkönyvi számlákhoz is hozzá vannak rendelve olyan tranzakcióknál, amelyek nem kerülnek feladásra konkrét szállítóra vagy vevőre.</span><span class="sxs-lookup"><span data-stu-id="9d979-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="9d979-107">A Cikkáfacsoportok az erőforrásokhoz, például termékekhez rendelt áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="9d979-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="9d979-108">Az egyes tranzakciókra alkalmazandó áfakódok azok az áfakódok, amelyek mind az áfacsoportban, mind a tranzakció cikkáfacsoportjában szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="9d979-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="9d979-109">Az áfa kiszámításához szükséges, hogy minden olyan tranzakciónál, amelyre áfát kell számítani vagy rögzíteni, ki legyen választva egy áfacsoport és egy cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="9d979-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="9d979-110">Ugorjon az Adó > Közvetett adók > Áfa > Áfakódcsoportok pontra.</span><span class="sxs-lookup"><span data-stu-id="9d979-110">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="9d979-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9d979-111">Click New.</span></span>
3. <span data-ttu-id="9d979-112">Az Áfacsoport kód mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9d979-112">In the Sales tax group field, type a value.</span></span>
4. <span data-ttu-id="9d979-113">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9d979-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9d979-114">Váltsa át a Beállítás szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="9d979-114">Toggle the expansion of the Setup section.</span></span>
6. <span data-ttu-id="9d979-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9d979-115">Click Add.</span></span>
7. <span data-ttu-id="9d979-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9d979-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="9d979-117">Az Áfakód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9d979-117">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="9d979-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9d979-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="9d979-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9d979-119">Click Save.</span></span>
11. <span data-ttu-id="9d979-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9d979-120">Close the page.</span></span>
12. <span data-ttu-id="9d979-121">Ugorjon az Adó > Közvetett adók > Áfa > Áfakódcsoportok pontra.</span><span class="sxs-lookup"><span data-stu-id="9d979-121">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
13. <span data-ttu-id="9d979-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9d979-122">Click New.</span></span>
14. <span data-ttu-id="9d979-123">A Cikkáfacsoport kód mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9d979-123">In the Item sales tax group field, type a value.</span></span>
15. <span data-ttu-id="9d979-124">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9d979-124">In the Description field, type a value.</span></span>
16. <span data-ttu-id="9d979-125">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="9d979-125">Click Add.</span></span>
17. <span data-ttu-id="9d979-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="9d979-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="9d979-127">Az Áfakód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9d979-127">In the Sales tax code field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="9d979-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9d979-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="9d979-129">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9d979-129">Click Save.</span></span>

