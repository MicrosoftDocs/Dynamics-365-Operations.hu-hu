---
title: Projekt beszerzési rendelésének létrehozása
description: Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy projekt beszerzési rendelését.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, PurchCreateOrder, PurchTable, PurchTablePart, InventItemIdLookupPurchase
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 85079a843de02a8c8d5ae0ec291fa77464dd2dff
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018121"
---
# <a name="create-project-purchase-order"></a><span data-ttu-id="0f4f6-103">Projekt beszerzési rendelésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="0f4f6-103">Create project purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0f4f6-104">Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy projekt beszerzési rendelését.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-104">This procedure shows you how to create a project purchase order.</span></span> <span data-ttu-id="0f4f6-105">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="0f4f6-106">Ugorjon a Projektvezetés és könyvelés > Projektek > Minden projekt pontra.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-106">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="0f4f6-107">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-107">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="0f4f6-108">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-108">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="0f4f6-109">Kattintson a Cikkfeladatra.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-109">Click Item task.</span></span>
5. <span data-ttu-id="0f4f6-110">Kattintson a Beszerzési rendelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-110">Click Purchase order.</span></span>
6. <span data-ttu-id="0f4f6-111">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-111">In the Vendor account field, enter or select a value.</span></span>
7. <span data-ttu-id="0f4f6-112">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-112">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="0f4f6-113">Ezeket a lépéseket nem kötelező végrehajtani, de valóban leegyszerűsítik a beszerzési rendelést azzal, hogy beállítanak egy alapértelmezett telephelyet és raktárat a beszerzési rendeléssorokhoz.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-113">These steps aren't required, but they do simplify the purchase order by setting up a default site and warehouse for the purchase order lines.</span></span>  
8. <span data-ttu-id="0f4f6-114">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-114">In the Warehouse field, enter or select a value.</span></span>
9. <span data-ttu-id="0f4f6-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-115">Click OK.</span></span>
10. <span data-ttu-id="0f4f6-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-116">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="0f4f6-117">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="0f4f6-118">Ez lehet a cikkszám vagy egy beszerzési kategória.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-118">This can be the item number or a procurement category.</span></span>  
12. <span data-ttu-id="0f4f6-119">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-119">Expand the Line details section.</span></span>
13. <span data-ttu-id="0f4f6-120">Kattintson a Projekt fülre.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-120">Click the Project tab.</span></span>
    * <span data-ttu-id="0f4f6-121">Győződjön meg arról, hogy az értékesítési és az önköltségi árak rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-121">Verify that the sales and cost prices are available.</span></span> <span data-ttu-id="0f4f6-122">Ha nem állnak rendelkezésre, de szükségesek, adja meg az adatokat.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-122">If they are not available but needed, enter the information.</span></span>  
14. <span data-ttu-id="0f4f6-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0f4f6-123">Click Save.</span></span>

