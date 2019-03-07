---
title: Elemzési jelentések nem frissültek
description: Ez a témakör bemutatja, mit tegyen, ha a vevő adatainak módosításai nem jelennek meg a vevő munkaterületek valamelyikén.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 46f426a4b0012e87b4d9d21032870ac7fc33c4ae
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304649"
---
# <a name="analytic-reports-are-not-updated"></a><span data-ttu-id="e9fa5-103">Elemzési jelentések nem frissültek</span><span class="sxs-lookup"><span data-stu-id="e9fa5-103">Analytic reports are not updated</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e9fa5-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="e9fa5-104">**Issue**</span></span>

<span data-ttu-id="e9fa5-105">A vevő adatainak módosításai nem jelennek meg az **Elemzések** lapon a vevő egyik munkaterületén sem.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="e9fa5-106">**Ok**</span><span class="sxs-lookup"><span data-stu-id="e9fa5-106">**Cause**</span></span>

<span data-ttu-id="e9fa5-107">Alapértelmezés szerint a Microsoft Power BI jelentések négy óránként frissülnek, a Mérték telepítése kötegelt feladat ütemezése szerint.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="e9fa5-108">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="e9fa5-108">**Resolution**</span></span>

<span data-ttu-id="e9fa5-109">A probléma lehet, hogy csak az időzítésen múlik.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="e9fa5-110">Kövesse az alábbi lépéseket a kötegelt feladat megkezdéséhez és az Elemzések munkaterületek frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="e9fa5-111">Nyissa meg a **Kötegelt feladatok** oldalt a **Rendszerfelügyelet \> Hivatkozások \> Kötegelt feladatok \> Kötegelt feladatok** menüpontban.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="e9fa5-112">Azt is megteheti, hogy a Keresésben adja meg **Kötegelt feladatok** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="e9fa5-113">Keresse meg a **Mérték telepítése** feladatot a listában.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="e9fa5-114">Válassza a **Szerkesztés** lehetőséget az oldal felső részén, és állítsa az ütemezett kezdő dátumot/idépontot olyan értékre, amely a jelenlegi időhöz közelebb frissíti az elemzéseket.</span><span class="sxs-lookup"><span data-stu-id="e9fa5-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Kötegelt feladatok](media/batch-jobs.png)
