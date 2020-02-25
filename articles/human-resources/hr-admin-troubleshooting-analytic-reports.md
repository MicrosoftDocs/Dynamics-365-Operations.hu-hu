---
title: Elemzési jelentések hibaelhárítása
description: Ez a cikk bemutatja, hogy mi a teendő, ha a vevő adatainak módosításai nem jelennek meg a vevő munkaterületein.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 99d9eb3a16e6470820a2eb0a19c1d50e89bd3d36
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009227"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="ee0f7-103">Elemzési jelentések hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="ee0f7-103">Troubleshoot analytic reports</span></span>

<span data-ttu-id="ee0f7-104">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="ee0f7-104">**Issue**</span></span>

<span data-ttu-id="ee0f7-105">A vevő adatainak módosításai nem jelennek meg az **Elemzések** lapon a vevő egyik munkaterületén sem.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="ee0f7-106">**Ok**</span><span class="sxs-lookup"><span data-stu-id="ee0f7-106">**Cause**</span></span>

<span data-ttu-id="ee0f7-107">Alapértelmezés szerint a Microsoft Power BI jelentések négy óránként frissülnek, a Mérték telepítése kötegelt feladat ütemezése szerint.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="ee0f7-108">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="ee0f7-108">**Resolution**</span></span>

<span data-ttu-id="ee0f7-109">A probléma lehet, hogy csak az időzítésen múlik.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="ee0f7-110">Kövesse az alábbi lépéseket a kötegelt feladat megkezdéséhez és az Elemzések munkaterületek frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="ee0f7-111">Nyissa meg a **Kötegelt feladatok** oldalt a **Rendszerfelügyelet \> Hivatkozások \> Kötegelt feladatok \> Kötegelt feladatok** menüpontban.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="ee0f7-112">Azt is megteheti, hogy a Keresésben adja meg **Kötegelt feladatok** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="ee0f7-113">Keresse meg a **Mérték telepítése** feladatot a listában.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="ee0f7-114">Válassza a **Szerkesztés** lehetőséget az oldal felső részén, és állítsa az ütemezett kezdő dátumot/idépontot olyan értékre, amely a jelenlegi időhöz közelebb frissíti az elemzéseket.</span><span class="sxs-lookup"><span data-stu-id="ee0f7-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Kötegelt feladatok](media/batch-jobs.png)
