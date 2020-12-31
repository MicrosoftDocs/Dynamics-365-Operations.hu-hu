---
title: Értékcsökkenési szabály módosítása több tárgyi eszközre
description: Ez a feladat frissíti a konkrét tárgyi eszközcsoport értékcsökkenési szabályát.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39930134782b40de05a92a6ad51c4f628f304a78
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443834"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="4f99f-103">Értékcsökkenési szabály módosítása több tárgyi eszközre</span><span class="sxs-lookup"><span data-stu-id="4f99f-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4f99f-104">Ez a feladat frissíti a konkrét tárgyi eszközcsoport értékcsökkenési szabályát.</span><span class="sxs-lookup"><span data-stu-id="4f99f-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="4f99f-105">Ez az útmutató-feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4f99f-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="4f99f-106">Ugorjon a Tárgyi eszközök > Időszakos feladatok > Tömeges frissítés pontra.</span><span class="sxs-lookup"><span data-stu-id="4f99f-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="4f99f-107">Az Értékcsökkenési könyv mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f99f-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4f99f-108">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f99f-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4f99f-109">Az Aktiválás kezdete mezőbe írjon be egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="4f99f-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="4f99f-110">Az Aktiválás vége mezőbe írjon be egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="4f99f-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="4f99f-111">A program csak azokat az eszközöket frissíti, amelyek részei a kiválasztott értékcsökkenés könyvnek és a megadott dátumok között lettek aktiválva.</span><span class="sxs-lookup"><span data-stu-id="4f99f-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="4f99f-112">Válassza ki valamelyik lehetőséget a Jelenlegi értékcsökkenési szabály mezőben.</span><span class="sxs-lookup"><span data-stu-id="4f99f-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="4f99f-113">Csak az aktuális értékcsökkenési szabályok szerinti eszközök frissülnek.</span><span class="sxs-lookup"><span data-stu-id="4f99f-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="4f99f-114">Válassza ki valamelyik lehetőséget az Új értékcsökkenési szabály mezőben.</span><span class="sxs-lookup"><span data-stu-id="4f99f-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="4f99f-115">Ellenőrizze, hogy a jelentés nyomtatása a kiválasztott célhelyre történik-e.</span><span class="sxs-lookup"><span data-stu-id="4f99f-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="4f99f-116">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4f99f-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="4f99f-117">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="4f99f-117">Click Filter.</span></span>
10. <span data-ttu-id="4f99f-118">A listából válassza ki a Tárgyi eszköz csoportot.</span><span class="sxs-lookup"><span data-stu-id="4f99f-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="4f99f-119">A Kritériumok mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4f99f-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="4f99f-120">Válassza ki a kívánt Tárgyi eszköz csoportot.</span><span class="sxs-lookup"><span data-stu-id="4f99f-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="4f99f-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4f99f-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="4f99f-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4f99f-122">Click OK.</span></span>
15. <span data-ttu-id="4f99f-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4f99f-123">Click OK.</span></span>
    *  <span data-ttu-id="4f99f-124">A folyamat eredményei a Tömeges frissítés jelentésen jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="4f99f-124">Results of the process are shown on the Mass update report.</span></span>     

