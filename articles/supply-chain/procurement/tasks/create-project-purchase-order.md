---
title: Projekt beszerzési rendelésének létrehozása
description: Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy projekt beszerzési rendelését.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, PurchCreateOrder, PurchTable, PurchTablePart, InventItemIdLookupPurchase
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1eef6f4e0ef4b0c33572156b702c182456e3360d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237227"
---
# <a name="create-project-purchase-order"></a><span data-ttu-id="cb918-103">Projekt beszerzési rendelésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="cb918-103">Create project purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cb918-104">Ez az eljárás bemutatja, hogy hogyan lehet létrehozni egy projekt beszerzési rendelését.</span><span class="sxs-lookup"><span data-stu-id="cb918-104">This procedure shows you how to create a project purchase order.</span></span> <span data-ttu-id="cb918-105">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="cb918-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="cb918-106">Ugorjon a Projektvezetés és könyvelés > Projektek > Minden projekt pontra.</span><span class="sxs-lookup"><span data-stu-id="cb918-106">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="cb918-107">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="cb918-107">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="cb918-108">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="cb918-108">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="cb918-109">Kattintson a Cikkfeladatra.</span><span class="sxs-lookup"><span data-stu-id="cb918-109">Click Item task.</span></span>
5. <span data-ttu-id="cb918-110">Kattintson a Beszerzési rendelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="cb918-110">Click Purchase order.</span></span>
6. <span data-ttu-id="cb918-111">A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cb918-111">In the Vendor account field, enter or select a value.</span></span>
7. <span data-ttu-id="cb918-112">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cb918-112">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="cb918-113">Ezeket a lépéseket nem kötelező végrehajtani, de valóban leegyszerűsítik a beszerzési rendelést azzal, hogy beállítanak egy alapértelmezett telephelyet és raktárat a beszerzési rendeléssorokhoz.</span><span class="sxs-lookup"><span data-stu-id="cb918-113">These steps aren't required, but they do simplify the purchase order by setting up a default site and warehouse for the purchase order lines.</span></span>  
8. <span data-ttu-id="cb918-114">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cb918-114">In the Warehouse field, enter or select a value.</span></span>
9. <span data-ttu-id="cb918-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="cb918-115">Click OK.</span></span>
10. <span data-ttu-id="cb918-116">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="cb918-116">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="cb918-117">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="cb918-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="cb918-118">Ez lehet a cikkszám vagy egy beszerzési kategória.</span><span class="sxs-lookup"><span data-stu-id="cb918-118">This can be the item number or a procurement category.</span></span>  
12. <span data-ttu-id="cb918-119">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="cb918-119">Expand the Line details section.</span></span>
13. <span data-ttu-id="cb918-120">Kattintson a Projekt fülre.</span><span class="sxs-lookup"><span data-stu-id="cb918-120">Click the Project tab.</span></span>
    * <span data-ttu-id="cb918-121">Győződjön meg arról, hogy az értékesítési és az önköltségi árak rendelkezésre állnak.</span><span class="sxs-lookup"><span data-stu-id="cb918-121">Verify that the sales and cost prices are available.</span></span> <span data-ttu-id="cb918-122">Ha nem állnak rendelkezésre, de szükségesek, adja meg az adatokat.</span><span class="sxs-lookup"><span data-stu-id="cb918-122">If they are not available but needed, enter the information.</span></span>  
14. <span data-ttu-id="cb918-123">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="cb918-123">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]