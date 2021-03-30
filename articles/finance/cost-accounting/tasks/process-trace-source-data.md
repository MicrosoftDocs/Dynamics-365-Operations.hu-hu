---
title: Folyamat- és nyomkövetési forrásadatok
description: Minden adatfeldolgozást feladatok végeznek.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12137c0d82109a8b757df6f6990922994d49c71a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208655"
---
# <a name="process-and-trace-source-data"></a><span data-ttu-id="74264-103">Folyamat- és nyomkövetési forrásadatok</span><span class="sxs-lookup"><span data-stu-id="74264-103">Process and trace source data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="74264-104">Minden adatfeldolgozást feladatok végeznek.</span><span class="sxs-lookup"><span data-stu-id="74264-104">All data processing is run by jobs.</span></span> <span data-ttu-id="74264-105">Minden feladat és adatszolgáltató naplót hoz létre annak dokumentálására, hogy a folyamat futtatása és a bejegyzések feldolgozása megtörtént az aktuális feladatban.</span><span class="sxs-lookup"><span data-stu-id="74264-105">For each job and data provider, a journal is created to document that the process has been run, and that the entries were processed in the current job.</span></span> <span data-ttu-id="74264-106">Ezzel az eljárással beállíthat egy adatforrást, majd visszakeresheti egy meghatározott költségbejegyzés eredetét.</span><span class="sxs-lookup"><span data-stu-id="74264-106">Use this procedure to set up a data source and then  trace the origin of a specific cost entry.</span></span> <span data-ttu-id="74264-107">Ez a felvétel az USP2 bemutatóvállalat adatait használja.</span><span class="sxs-lookup"><span data-stu-id="74264-107">This recording uses the USP2 demo data company USP2.</span></span> <span data-ttu-id="74264-108">A feladat végrehajtása előtt ellenőrizze, hogy lejátszotta-e a következő feladat-útmutatókat: Költségkönyvelési főkönyv létrehozása, Költség-ellenőrzőegységek meghatározása, valamint Költségkönyvelési főkönyv adatforrásának kezelése.</span><span class="sxs-lookup"><span data-stu-id="74264-108">Before you complete this task, make sure that you play the following task guides: "Create a cost accounting ledger," "Define cost control units," and "Manage data source for the cost accounting ledger."</span></span>

1. <span data-ttu-id="74264-109">Lépjen a Költségkönyvelés > Főkönyv beállításai > Költségkönyvelési főkönyvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="74264-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="74264-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="74264-111">Válassza ki a korábban létrehozott költségkönyvelési főkönyvet.</span><span class="sxs-lookup"><span data-stu-id="74264-111">Select the cost accounting ledger that you created earlier.</span></span>  
3. <span data-ttu-id="74264-112">Kattintson az Aktuális verziók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-112">Click Actual versions.</span></span>
4. <span data-ttu-id="74264-113">Kattintson a Műveletpanelen a Forrásadat feldolgozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-113">On the Action Pane, click Source data processing.</span></span>
5. <span data-ttu-id="74264-114">Kattintson a Főkönyvi bejegyzés átviteli naplói lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-114">Click General ledger entry transfer journals.</span></span>
6. <span data-ttu-id="74264-115">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="74264-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="74264-116">Kattintson a Naplóbejegyzések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-116">Click Journal entries.</span></span>
8. <span data-ttu-id="74264-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="74264-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="74264-118">Kattintson a Költségbejegyzésekre.</span><span class="sxs-lookup"><span data-stu-id="74264-118">Click Cost entries.</span></span>
10. <span data-ttu-id="74264-119">Kattintson a Forrásbejegyzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-119">Click Source entry.</span></span>
11. <span data-ttu-id="74264-120">Kattintson a Műveletpanelen a Forrásadat feldolgozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-120">On the Action Pane, click Source data processing.</span></span>
12. <span data-ttu-id="74264-121">Kattintson a Főkönyv lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="74264-121">Click General ledger.</span></span>
13. <span data-ttu-id="74264-122">A Pénzügyi naptári időszak mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="74264-122">In the Fiscal calendar period field, enter or select a value.</span></span>
    * <span data-ttu-id="74264-123">Ebben a példában válassza a 2017 9-es pénzügyi időszakot.</span><span class="sxs-lookup"><span data-stu-id="74264-123">For this example, select Fiscal 2017 Period 9.</span></span>  
14. <span data-ttu-id="74264-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="74264-124">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]