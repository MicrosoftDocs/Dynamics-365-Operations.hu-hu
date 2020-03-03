---
title: Kimutatások számításához használt feladat konfigurálása és futtatása
description: Ez az eljárás végigveszi az ismétlődő kötegelt feladatok konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport számára kimutatásokat tudjon létrehozni és kiszámítani.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52798303ef5d96a44270f971703928d0c6c4c2c1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022759"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="7e222-103">Kimutatások számításához használt feladat konfigurálása és futtatása</span><span class="sxs-lookup"><span data-stu-id="7e222-103">Configure and run job to calculate statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="7e222-104">Ez az eljárás végigveszi az ismétlődő kötegelt feladatok konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport számára kimutatásokat tudjon létrehozni és kiszámítani.</span><span class="sxs-lookup"><span data-stu-id="7e222-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="7e222-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="7e222-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="7e222-106">Ugorjon az Összes munkaterület > Áruház pénzügyei oldalra.</span><span class="sxs-lookup"><span data-stu-id="7e222-106">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="7e222-107">Kattintson a Kimutatások számítása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e222-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="7e222-108">Válasszon ki egy bizonyos üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="7e222-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="7e222-109">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="7e222-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="7e222-110">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="7e222-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="7e222-111">A Kötegelt feldolgozás területen válassza az „Igen” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e222-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="7e222-112">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="7e222-112">Click Recurrence.</span></span>
6. <span data-ttu-id="7e222-113">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="7e222-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="7e222-114">A Kezdés ideje mezőben adjon meg egy időt.</span><span class="sxs-lookup"><span data-stu-id="7e222-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="7e222-115">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e222-115">Select the No end date option.</span></span>
9. <span data-ttu-id="7e222-116">A Mintaegység mezőbe írjon be egy számot „Napokban” megadva.</span><span class="sxs-lookup"><span data-stu-id="7e222-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="7e222-117">A / mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="7e222-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="7e222-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7e222-118">Click OK.</span></span>
12. <span data-ttu-id="7e222-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7e222-119">Click OK.</span></span>
