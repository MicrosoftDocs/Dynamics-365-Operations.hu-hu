---
title: Kimutatások feladásához használt feladat konfigurálása és futtatása
description: Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport esetén kimutatásokat feladni.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bed4cfb4875231d11ad76e4403c7995519d56e73
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003678"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="79d5b-103">Kimutatások feladásához használt feladat konfigurálása és futtatása</span><span class="sxs-lookup"><span data-stu-id="79d5b-103">Configure and run job to post statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="79d5b-104">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, hogy egy kiválasztott üzlet vagy üzletcsoport esetén kimutatásokat feladni.</span><span class="sxs-lookup"><span data-stu-id="79d5b-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="79d5b-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="79d5b-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="79d5b-106">Lépjen Az összes munkaterület > ..</span><span class="sxs-lookup"><span data-stu-id="79d5b-106">Go to All workspaces > ..</span></span> <span data-ttu-id="79d5b-107">> Üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="79d5b-107">> Store financials.</span></span>
2. <span data-ttu-id="79d5b-108">Kattintson a Kimutatások kötegelt feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="79d5b-108">Click Post statements in batch.</span></span>
    * <span data-ttu-id="79d5b-109">Válasszon ki egy szervezeti hierarchiát, majd a szervezeti csomópontok fastruktúrájában válasszon ki egy egyéni üzletet vagy egy csomópontot.</span><span class="sxs-lookup"><span data-stu-id="79d5b-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="79d5b-110">Válasszon ki egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="79d5b-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="79d5b-111">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="79d5b-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="79d5b-112">Kattintson a Futtatás a háttérben lapra. ![Futtatás a háttérben](../dev-itpro/media/runbackground.png "Futtatás a háttérben")</span><span class="sxs-lookup"><span data-stu-id="79d5b-112">Click the Run in the background tab. ![Run in the background](../dev-itpro/media/runbackground.png "Run in the background")</span></span> 
4. <span data-ttu-id="79d5b-113">Jelölje be vagy törölje a jelölést a Kötegelt feldolgozás jelölőnégyzetben.</span><span class="sxs-lookup"><span data-stu-id="79d5b-113">Check or uncheck the Batch processing checkbox.</span></span>
<span data-ttu-id="79d5b-114">![Kötegelt feldolgozás](../dev-itpro/media/batchprocessing.png "Kötegelt feldolgozás és ismétlődés")</span><span class="sxs-lookup"><span data-stu-id="79d5b-114">![Batch Processing](../dev-itpro/media/batchprocessing.png "Batch Processing & Recurrance")</span></span> 
5. <span data-ttu-id="79d5b-115">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="79d5b-115">Click Recurrence.</span></span>
6. <span data-ttu-id="79d5b-116">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="79d5b-116">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="79d5b-117">A Kezdés ideje mezőben adjon meg egy időt.</span><span class="sxs-lookup"><span data-stu-id="79d5b-117">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="79d5b-118">Válassza ki, hogy mikor kívánja befejezni az ismétlődést: egy bizonyos számú lefutás után, egy meghatározott dátum elérésekor, vagy soha.</span><span class="sxs-lookup"><span data-stu-id="79d5b-118">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="79d5b-119">Majd a különféle lehetőségek segítségével adja meg, hogy milyen gyakran szeretné futtatni a feladatot.</span><span class="sxs-lookup"><span data-stu-id="79d5b-119">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="79d5b-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="79d5b-120">Click OK.</span></span>
9. <span data-ttu-id="79d5b-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="79d5b-121">Click OK.</span></span>

