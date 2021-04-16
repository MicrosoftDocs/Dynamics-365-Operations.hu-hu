---
title: Áfabevallás kódjainak beállítása
description: A áfajelentési kódok az áfajelentésben felsorolt mezőszámokra hivatkoznak.
author: twheeloc
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e040bac6ef9e950e8d7f97e3c136636acf1fe43
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813531"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="4d786-103">Áfabevallás kódjainak beállítása</span><span class="sxs-lookup"><span data-stu-id="4d786-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4d786-104">A áfajelentési kódok az áfajelentésben felsorolt mezőszámokra hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="4d786-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="4d786-105">Ezeket országspecifikus jelentéselrendezésekben használják.</span><span class="sxs-lookup"><span data-stu-id="4d786-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="4d786-106">Áfafizetés kód szerinti jelentéshez is használják őket.</span><span class="sxs-lookup"><span data-stu-id="4d786-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="4d786-107">Ez a jelentés az egyes jelentéskódokhoz összesített kiegyenlítési időszak áfaösszegeit mutatja.</span><span class="sxs-lookup"><span data-stu-id="4d786-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="4d786-108">A forgalmiadó-kódok létrehozása után hivatkozásként használhatja azokat az **Áfakód** oldalról elérhető Jelentéskészítési gyorslapjain.</span><span class="sxs-lookup"><span data-stu-id="4d786-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="4d786-109">Ez a felvétel az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4d786-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="4d786-110">A **Navigációs ablaktáblán**  ugorjon az **Adó > Beállítás > Áfa > Áfajelentési kódok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d786-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="4d786-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4d786-111">Click **New**.</span></span>
3. <span data-ttu-id="4d786-112">Annak az elrendezésnek a kiválasztása, amelyre a jelentési kód hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="4d786-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="4d786-113">Az elrendezés használatos az áfakód elérhető jelentési kódjának szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="4d786-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="4d786-114">Minden áfakód az adott kiegyenlítési időszakra vonatkozik, amely egy jelentésformátumot használó adóhatósághoz tartozik.</span><span class="sxs-lookup"><span data-stu-id="4d786-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="4d786-115">A **Jelentés kódja** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="4d786-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="4d786-116">A **Jelentés szövege** mezőbe írjon be egy, a jelentésekben megjelenítendő leírást.</span><span class="sxs-lookup"><span data-stu-id="4d786-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="4d786-117">A **Rövid leírás** mezőben adjon meg egy belső használatra szánt leírást.</span><span class="sxs-lookup"><span data-stu-id="4d786-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="4d786-118">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="4d786-118">Click **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]