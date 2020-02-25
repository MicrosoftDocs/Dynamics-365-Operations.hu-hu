---
title: Vevői hitelkezelés
description: ''
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
ms.openlocfilehash: 11da8b7fb59bc8f3e2568ada27db753cc815b9c2
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015248"
---
# <a name="customer-credit-management-overview"></a><span data-ttu-id="175e5-102">Vevői hitelkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="175e5-102">Customer credit management overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="175e5-103">A vevői hitelkezelés lehetővé teszi a hitelkeretek kezelését, valamint az értékesítési rendelések áramlásának szabályozását a feladási folyamaton keresztül, az Ön által létrehozott hitelszabályok alapján.</span><span class="sxs-lookup"><span data-stu-id="175e5-103">Customer credit management allows you to manage credit limits and control the flow of sales orders through the posting process based on credit rules that you create.</span></span> 

<span data-ttu-id="175e5-104">A hitelkezelési folyamat a következő lépések bármelyikét vagy mindegyikét tartalmazhatja:</span><span class="sxs-lookup"><span data-stu-id="175e5-104">The process for using credit management can include some or all of the following steps:</span></span>
- <span data-ttu-id="175e5-105">Hitelattribútumok frissítése a vevők számára további információk megadásához hitelképességükről</span><span class="sxs-lookup"><span data-stu-id="175e5-105">Update customers with credit attributes that provide additional information about their credit worthiness</span></span> 
- <span data-ttu-id="175e5-106">Hitelkeretek létrehozása ügyefelekhez hitelkeret-kiigazítások használatával</span><span class="sxs-lookup"><span data-stu-id="175e5-106">Create credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="175e5-107">Ideiglenes hitelkeretek létrehozása a hitelkeret-korrekciókat használó vevők esetében, ha az üzleti szükségletek alapján ideiglenesen növelni vagy csökkenteni szeretné a hitelkeretet</span><span class="sxs-lookup"><span data-stu-id="175e5-107">Create temporary credit limits for customers using credit limit adjustments when you want to increase or decrease their credit limit temporarily based on business needs</span></span>
- <span data-ttu-id="175e5-108">A hitelkeretet befolyásoló további adatok, például a biztosítással és a garanciával kapcsolatos információk hozzáadása</span><span class="sxs-lookup"><span data-stu-id="175e5-108">Add additional information that can affect the credit limit such as insurance and guarantees</span></span>
- <span data-ttu-id="175e5-109">Vevői hitelcsoportok létrehozása, amelyekkel a vevők összekapcsolhatók úgy, hogy egyetlen hitelkeretet osszanak meg egymással</span><span class="sxs-lookup"><span data-stu-id="175e5-109">Create customer credit groups that link customers together so they can share a single credit limit</span></span>
- <span data-ttu-id="175e5-110">Kockázati pontszámok hozzárendelése a vevőkhöz, majd a pontszámok használatával hitelkereteket hozhat létre a vevőkhöz a hitelkeret-módosítások használatával</span><span class="sxs-lookup"><span data-stu-id="175e5-110">Assign risk scores to customers and then use those scores to automatically generate credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="175e5-111">Zárolási szabályok létrehozása, amelyek egy vagy több feladási folyamat során várakoztatnak egy rendelést, olyan tényezők alapján, mint a kockázat, a fizetési feltételek, a hitelkeretek, a lejárt tartozások és felhasznált hitelkeret százaléka</span><span class="sxs-lookup"><span data-stu-id="175e5-111">Create blocking rules that will place an order on hold during one or more posting processes based on factors such as risk, payment terms, credit limits, overdue amounts, and percentage of credit limit used</span></span>
- <span data-ttu-id="175e5-112">A várakoztatott értékesítési rendelések listájának kezelése, a várakoztatási okok áttekintése, valamint a problémák megoldása</span><span class="sxs-lookup"><span data-stu-id="175e5-112">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate the issues</span></span>
- <span data-ttu-id="175e5-113">Értékesítési rendelések felszabadítása, és annak engedélyezése, hogy a feladási folyamatban továbbhaladhassanak</span><span class="sxs-lookup"><span data-stu-id="175e5-113">Release sales orders and allow it to continue through the posting process</span></span>
- <span data-ttu-id="175e5-114">Munkafolyamat beállítás a hitelkeret-módosítások és az értékesítési rendelés felszabadítások jóváhagyásának kezelésére</span><span class="sxs-lookup"><span data-stu-id="175e5-114">Set up workflow to manage the approval of credit limit changes and sales order releases</span></span>


<a name="additional-resources"></a><span data-ttu-id="175e5-115">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="175e5-115">Additional resources</span></span>
--------
[<span data-ttu-id="175e5-116">Vásárlói hitelkezelési pereméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="175e5-116">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="175e5-117">Vásárlói hitelkezelési pereméterek beállításával kapcsolatos információk</span><span class="sxs-lookup"><span data-stu-id="175e5-117">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="175e5-118">Hitelkezelési információk hozzáadása egy ügyfélhez</span><span class="sxs-lookup"><span data-stu-id="175e5-118">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="175e5-119">Vevői hitelcsoportok</span><span class="sxs-lookup"><span data-stu-id="175e5-119">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="175e5-120">Vevői hitelkeret helyesbítései</span><span class="sxs-lookup"><span data-stu-id="175e5-120">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="175e5-121">Hitelkeret felfüggesztése értékesítési rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="175e5-121">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="175e5-122">Vevői hitelkockázatkezelés – időszakos feladatok</span><span class="sxs-lookup"><span data-stu-id="175e5-122">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


