--- 
title: " Kimutatások feladásához használt feladat konfigurálása és futtatása"
description: "Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport esetén kimutatásokat feladni."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 564f628ff082887a0f6476ded76c13d2824abf08
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="configure-and-run-a-job-to-post-statements"></a><span data-ttu-id="052bb-103"> Kimutatások feladásához használt feladat konfigurálása és futtatása</span><span class="sxs-lookup"><span data-stu-id="052bb-103">Configure and run a job to post statements</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="052bb-104">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport esetén kimutatásokat feladni.</span><span class="sxs-lookup"><span data-stu-id="052bb-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="052bb-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="052bb-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="052bb-106">Lépjen Az összes munkaterület > ..</span><span class="sxs-lookup"><span data-stu-id="052bb-106">Go to All workspaces > ..</span></span> <span data-ttu-id="052bb-107">> Kiskereskedelmi üzlet pénzügyei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="052bb-107">> Retail store financials.</span></span>
2. <span data-ttu-id="052bb-108">Kattintson a Kimutatások feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="052bb-108">Click Post statements.</span></span>
    * <span data-ttu-id="052bb-109">Válasszon ki egy szervezeti hierarchiát, majd a szervezeti csomópontok fastruktúrájában válasszon ki egy egyéni üzletet vagy egy csomópontot.</span><span class="sxs-lookup"><span data-stu-id="052bb-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="052bb-110">Válasszon ki egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="052bb-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="052bb-111">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="052bb-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="052bb-112">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="052bb-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="052bb-113">Jelölje be vagy törölje a jelölést a Kötegelt feldolgozás jelölőnégyzetben.</span><span class="sxs-lookup"><span data-stu-id="052bb-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="052bb-114">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="052bb-114">Click Recurrence.</span></span>
6. <span data-ttu-id="052bb-115">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="052bb-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="052bb-116">A Kezdés ideje mezőben adjon meg egy időt.</span><span class="sxs-lookup"><span data-stu-id="052bb-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="052bb-117">Válassza ki, hogy mikor kívánja befejezni az ismétlődést: egy bizonyos számú lefutás után, egy meghatározott dátum elérésekor, vagy soha.</span><span class="sxs-lookup"><span data-stu-id="052bb-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="052bb-118">Majd a különféle lehetőségek segítségével adja meg, hogy milyen gyakran szeretné futtatni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="052bb-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="052bb-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="052bb-119">Click OK.</span></span>
9. <span data-ttu-id="052bb-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="052bb-120">Click OK.</span></span>


