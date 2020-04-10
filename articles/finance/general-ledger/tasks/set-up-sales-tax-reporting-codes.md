---
title: Áfabevallás kódjainak beállítása
description: A áfajelentési kódok az áfajelent mezőszámaira hivatkoznak.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 460e41d69a78cda664e0d3af828fdc482169ac52
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145075"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="60364-103">Áfabevallás kódjainak beállítása</span><span class="sxs-lookup"><span data-stu-id="60364-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="60364-104">A áfajelentési kódok az áfajelent mezőszámaira hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="60364-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="60364-105">Ezek országspecifikus jelentési elrendezéseken és a kódonkénti áfakifizetési jelentésen használatosak az áfaösszegek nyomtatásához jelentési kód szerinti kiegyenlítési időszak összegzéséhez.</span><span class="sxs-lookup"><span data-stu-id="60364-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="60364-106">A forgalmiadó-kódok létrehozása után hivatkozásként használhatja azokat az Áfakód oldal Jelentéskészítési gyorslapjain.</span><span class="sxs-lookup"><span data-stu-id="60364-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="60364-107">Ez a felvétel az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="60364-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="60364-108">A **Navigációs ablaktáblán**  ugorjon az **Adó > Beállítás > Áfa > Áfajelentési kódok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="60364-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="60364-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="60364-109">Click **New**.</span></span>
3. <span data-ttu-id="60364-110">Annak az elrendezésnek a kiválasztása, amelyre a jelentési kód hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="60364-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="60364-111">Az elrendezés használatos az áfakód elérhető jelentési kódjának szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="60364-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="60364-112">Minden áfakód az adott kiegyenlítési időszakra vonatkozik, amely egy jelentésformátumot használó adóhatósághoz tartozik.</span><span class="sxs-lookup"><span data-stu-id="60364-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="60364-113">A **Jelentés kódja** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="60364-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="60364-114">A **Jelentés szövege** mezőbe írjon be egy, a jelentésekben megjelenítendő leírást.</span><span class="sxs-lookup"><span data-stu-id="60364-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="60364-115">A **Rövid leírás** mezőben adjon meg egy belső használatra szánt leírást.</span><span class="sxs-lookup"><span data-stu-id="60364-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="60364-116">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="60364-116">Click **Save**.</span></span>

