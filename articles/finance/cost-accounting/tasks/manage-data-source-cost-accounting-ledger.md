---
title: A költségkönyvelési főkönyv adatforrásának kezelése
description: Ezzel az eljárással kezelheti a költségkönyvelési főkönyv főkönyvi adatforrását.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMAXGeneralLedgerEntryProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7246d42b42404f0f1215bbf14b8ad168fe12691c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990717"
---
# <a name="manage-a-data-source-for-the-cost-accounting-ledger"></a><span data-ttu-id="44cbb-103">A költségkönyvelési főkönyv adatforrásának kezelése</span><span class="sxs-lookup"><span data-stu-id="44cbb-103">Manage a data source for the cost accounting ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="44cbb-104">Ezzel az eljárással kezelheti a költségkönyvelési főkönyv főkönyvi adatforrását.</span><span class="sxs-lookup"><span data-stu-id="44cbb-104">Use this procedure to manage the general ledger data source for a cost accounting ledger.</span></span> <span data-ttu-id="44cbb-105">A feladat végrehajtása előtt ellenőrizze, hogy lejátszotta-e a Költségkönyvelési főkönyv létrehozása és a Költség-ellenőrzőegységek meghatározása feladat-útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="44cbb-105">Before you complete this task, make sure that you play the "Create a cost accounting ledger" and "Define cost control units" task guides.</span></span> <span data-ttu-id="44cbb-106">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="44cbb-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="44cbb-107">Lépjen a Költségkönyvelés > Főkönyv beállításai > Költségkönyvelési főkönyvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-107">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="44cbb-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="44cbb-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="44cbb-109">Kattintson az Aktuális verziók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-109">Click Actual versions.</span></span>
4. <span data-ttu-id="44cbb-110">A Művelet panelen kattintson a Kezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-110">On the Action Pane, click Manage.</span></span>
5. <span data-ttu-id="44cbb-111">Kattintson a Főkönyv lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-111">Click General ledger.</span></span>
6. <span data-ttu-id="44cbb-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-112">Click New.</span></span>
7. <span data-ttu-id="44cbb-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="44cbb-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="44cbb-114">Az Adatszolgáltató mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="44cbb-114">In the Data provider field, enter or select a value.</span></span>
    * <span data-ttu-id="44cbb-115">Ebben a példában válassza a Dynamics 365 Finance – Főkönyvi bejegyzések lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="44cbb-115">For this example, select Dynamics 365 Finance - General ledger entries.</span></span>  
9. <span data-ttu-id="44cbb-116">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="44cbb-116">In the Cost element dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="44cbb-117">Ehhez a példához válassza ki a Költségösszetevők lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="44cbb-117">For this example, select Cost elements.</span></span>  
10. <span data-ttu-id="44cbb-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="44cbb-118">Click Save.</span></span>
11. <span data-ttu-id="44cbb-119">Kattintson az Adatszolgáltató konfigurálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-119">Click Configure data provider.</span></span>
12. <span data-ttu-id="44cbb-120">A Jogi személy mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="44cbb-120">In the Legal entity field, enter or select a value.</span></span>
    * <span data-ttu-id="44cbb-121">Ehhez a példához válassza ki a USP2 értéket.</span><span class="sxs-lookup"><span data-stu-id="44cbb-121">For this example, select USP2.</span></span>  
13. <span data-ttu-id="44cbb-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="44cbb-122">Click New.</span></span>
14. <span data-ttu-id="44cbb-123">Válassza az Aktuáls lehetőséget a Feladási réteg mezőben.</span><span class="sxs-lookup"><span data-stu-id="44cbb-123">In the Posting layer field, select Current.</span></span>
15. <span data-ttu-id="44cbb-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="44cbb-124">Click OK.</span></span>

