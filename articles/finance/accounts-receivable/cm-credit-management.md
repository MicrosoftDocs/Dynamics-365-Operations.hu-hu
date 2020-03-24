---
title: Vevői hitelkezelés
description: A vevői hitelkezelés lehetővé teszi a hitelkeretek kezelését, valamint az értékesítési rendelések áramlásának szabályozását a feladási folyamaton keresztül, az Ön által létrehozott hitelszabályok alapján.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1e7d3325587d7cfc876e8f8c7b9207d44046ccd4
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124277"
---
# <a name="customer-credit-management-overview"></a><span data-ttu-id="b947d-103">Vevői hitelkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="b947d-103">Customer credit management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b947d-104">A vevői hitelkezelés lehetővé teszi a hitelkeretek kezelését, valamint az értékesítési rendelések áramlásának szabályozását a feladási folyamaton keresztül, az Ön által létrehozott hitelszabályok alapján.</span><span class="sxs-lookup"><span data-stu-id="b947d-104">Customer credit management allows you to manage credit limits and control the flow of sales orders through the posting process based on credit rules that you create.</span></span> 

<span data-ttu-id="b947d-105">A hitelkezelési folyamat a következő lépések bármelyikét vagy mindegyikét tartalmazhatja:</span><span class="sxs-lookup"><span data-stu-id="b947d-105">The process for using credit management can include some or all of the following steps:</span></span>
- <span data-ttu-id="b947d-106">Hitelattribútumok frissítése a vevők számára további információk megadásához hitelképességükről</span><span class="sxs-lookup"><span data-stu-id="b947d-106">Update customers with credit attributes that provide additional information about their credit worthiness</span></span> 
- <span data-ttu-id="b947d-107">Hitelkeretek létrehozása ügyefelekhez hitelkeret-kiigazítások használatával</span><span class="sxs-lookup"><span data-stu-id="b947d-107">Create credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="b947d-108">Ideiglenes hitelkeretek létrehozása a hitelkeret-korrekciókat használó vevők esetében, ha az üzleti szükségletek alapján ideiglenesen növelni vagy csökkenteni szeretné a hitelkeretet</span><span class="sxs-lookup"><span data-stu-id="b947d-108">Create temporary credit limits for customers using credit limit adjustments when you want to increase or decrease their credit limit temporarily based on business needs</span></span>
- <span data-ttu-id="b947d-109">A hitelkeretet befolyásoló további adatok, például a biztosítással és a garanciával kapcsolatos információk hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b947d-109">Add additional information that can affect the credit limit such as insurance and guarantees</span></span>
- <span data-ttu-id="b947d-110">Vevői hitelcsoportok létrehozása, amelyekkel a vevők összekapcsolhatók úgy, hogy egyetlen hitelkeretet osszanak meg egymással</span><span class="sxs-lookup"><span data-stu-id="b947d-110">Create customer credit groups that link customers together so they can share a single credit limit</span></span>
- <span data-ttu-id="b947d-111">Kockázati pontszámok hozzárendelése a vevőkhöz, majd a pontszámok használatával hitelkereteket hozhat létre a vevőkhöz a hitelkeret-módosítások használatával</span><span class="sxs-lookup"><span data-stu-id="b947d-111">Assign risk scores to customers and then use those scores to automatically generate credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="b947d-112">Zárolási szabályok létrehozása, amelyek egy vagy több feladási folyamat során várakoztatnak egy rendelést, olyan tényezők alapján, mint a kockázat, a fizetési feltételek, a hitelkeretek, a lejárt tartozások és felhasznált hitelkeret százaléka</span><span class="sxs-lookup"><span data-stu-id="b947d-112">Create blocking rules that will place an order on hold during one or more posting processes based on factors such as risk, payment terms, credit limits, overdue amounts, and percentage of credit limit used</span></span>
- <span data-ttu-id="b947d-113">A várakoztatott értékesítési rendelések listájának kezelése, a várakoztatási okok áttekintése, valamint a problémák megoldása</span><span class="sxs-lookup"><span data-stu-id="b947d-113">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate the issues</span></span>
- <span data-ttu-id="b947d-114">Értékesítési rendelések felszabadítása, és annak engedélyezése, hogy a feladási folyamatban továbbhaladhassanak</span><span class="sxs-lookup"><span data-stu-id="b947d-114">Release sales orders and allow it to continue through the posting process</span></span>
- <span data-ttu-id="b947d-115">Munkafolyamat beállítás a hitelkeret-módosítások és az értékesítési rendelés felszabadítások jóváhagyásának kezelésére</span><span class="sxs-lookup"><span data-stu-id="b947d-115">Set up workflow to manage the approval of credit limit changes and sales order releases</span></span>


<a name="additional-resources"></a><span data-ttu-id="b947d-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b947d-116">Additional resources</span></span>
--------
[<span data-ttu-id="b947d-117">Vásárlói hitelkezelési pereméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="b947d-117">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="b947d-118">Vásárlói hitelkezelési pereméterek beállításával kapcsolatos információk</span><span class="sxs-lookup"><span data-stu-id="b947d-118">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="b947d-119">Hitelkezelési információk hozzáadása egy ügyfélhez</span><span class="sxs-lookup"><span data-stu-id="b947d-119">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="b947d-120">Vevői hitelcsoportok</span><span class="sxs-lookup"><span data-stu-id="b947d-120">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="b947d-121">Vevői hitelkeret helyesbítései</span><span class="sxs-lookup"><span data-stu-id="b947d-121">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="b947d-122">Hitelkeret felfüggesztése értékesítési rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="b947d-122">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="b947d-123">Vevői hitelkockázatkezelés – időszakos feladatok</span><span class="sxs-lookup"><span data-stu-id="b947d-123">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


