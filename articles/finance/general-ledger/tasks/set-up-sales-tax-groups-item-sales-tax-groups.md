---
title: Adócsoportok és cikkáfacsoportok beállítása
description: Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.
author: twheeloc
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxGroup,  TaxItemGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e97766be1207fb66b38f25b1e423fb21cec9e726
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222167"
---
# <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><span data-ttu-id="0c289-103">Adócsoportok és cikkáfacsoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="0c289-103">Set up sales tax groups and item sales tax groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0c289-104">Ez a feladatfelvétel végigvezeti az Áfa- és Cikkáfacsoportok létrehozásának lépésein.</span><span class="sxs-lookup"><span data-stu-id="0c289-104">This task recording walks you through the setup of Sales tax and Item sales tax groups.</span></span> <span data-ttu-id="0c289-105">Az áfacsoportok a vevőkhöz és szállítókhoz társított áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="0c289-105">Sales tax groups are groups of sales tax codes that are attached to customers and vendors.</span></span> <span data-ttu-id="0c289-106">Főkönyvi számlákhoz is hozzá vannak rendelve olyan tranzakcióknál, amelyek nem kerülnek feladásra konkrét szállítóra vagy vevőre.</span><span class="sxs-lookup"><span data-stu-id="0c289-106">They are also attached to ledger accounts for transactions that are not posted to a particular vendor or customer.</span></span>  <span data-ttu-id="0c289-107">A Cikkáfacsoportok az erőforrásokhoz, például termékekhez rendelt áfakódok csoportjai.</span><span class="sxs-lookup"><span data-stu-id="0c289-107">Item sales tax groups are groups of sales tax codes that are attached to resources like products.</span></span>  <span data-ttu-id="0c289-108">Az egyes tranzakciókra alkalmazandó áfakódok azok az áfakódok, amelyek mind az áfacsoportban, mind a tranzakció cikkáfacsoportjában szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="0c289-108">The sales taxes that apply to a particular transaction are determined by the sales tax codes that are included both in the sales tax group and in the item sales tax group of the transaction.</span></span>  <span data-ttu-id="0c289-109">Az áfa kiszámításához szükséges, hogy minden olyan tranzakciónál, amelyre áfát kell számítani vagy rögzíteni, ki legyen választva egy áfacsoport és egy cikkáfacsoport.</span><span class="sxs-lookup"><span data-stu-id="0c289-109">Sales tax can be calculated only if a sales tax group and an item sales tax group are selected for each transaction for which sales tax must be calculated or recorded.</span></span>  

1. <span data-ttu-id="0c289-110">Ugorjon a **Navigációs ablaktábla >Modulok > Adók > Közvetett adók > Áfa > Áfacsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0c289-110">Go to **Navigation pane > Modules > Tax > Indirect taxes > Sales tax > Sales tax groups**.</span></span>
2. <span data-ttu-id="0c289-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="0c289-111">Click **New**.</span></span>
3. <span data-ttu-id="0c289-112">Az **Áfacsoport** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0c289-112">In the **Sales tax group** field, type a value.</span></span>
4. <span data-ttu-id="0c289-113">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0c289-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="0c289-114">Váltsa át a **Beállítás** szakasz kibontását.</span><span class="sxs-lookup"><span data-stu-id="0c289-114">Toggle the expansion of the **Setup** section.</span></span>
6. <span data-ttu-id="0c289-115">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="0c289-115">Click **Add**.</span></span>
7. <span data-ttu-id="0c289-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0c289-116">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="0c289-117">Az **Áfakód** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0c289-117">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="0c289-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0c289-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="0c289-119">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="0c289-119">Click **Save**.</span></span>
11. <span data-ttu-id="0c289-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0c289-120">Close the page.</span></span>
12. <span data-ttu-id="0c289-121">Ugorjon az **Adó > Közvetett adók > Áfa > Áfacsoportok** pontra.</span><span class="sxs-lookup"><span data-stu-id="0c289-121">Go to **Tax > Indirect taxes > Sales tax > Item sales tax groups**.</span></span>
13. <span data-ttu-id="0c289-122">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="0c289-122">Click **New**.</span></span>
14. <span data-ttu-id="0c289-123">A **Cikkáfacsoport** mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0c289-123">In the **Item sales tax group** field, type a value.</span></span>
15. <span data-ttu-id="0c289-124">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0c289-124">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="0c289-125">Kattintson a **Hozzáadás** parancsra.</span><span class="sxs-lookup"><span data-stu-id="0c289-125">Click **Add**.</span></span>
17. <span data-ttu-id="0c289-126">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0c289-126">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="0c289-127">Az **Áfakód** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0c289-127">In the **Sales tax code** field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="0c289-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0c289-128">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="0c289-129">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="0c289-129">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]