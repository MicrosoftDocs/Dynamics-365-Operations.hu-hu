---
title: Termékkonfigurációs modell jóváhagyása
description: Ezen eljárás futtatásához szükség van legalább egy elérhető termékkonfigurációs modellre.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c196731046fa01059d61f2df08f47639ba839642
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568627"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="dffbe-103">Termékkonfigurációs modell jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="dffbe-103">Approve a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dffbe-104">Ezen eljárás futtatásához szükség van legalább egy elérhető termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="dffbe-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="dffbe-105">Ezen eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használja.</span><span class="sxs-lookup"><span data-stu-id="dffbe-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="dffbe-106">Fontos megjegyezni, hogy a modell már jóvá van hagyva, de az eljárás végigvezeti a teljes folyamaton.</span><span class="sxs-lookup"><span data-stu-id="dffbe-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="dffbe-107">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="dffbe-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="dffbe-108">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dffbe-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="dffbe-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="dffbe-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="dffbe-110">Válassza ki a Felső kategóriás modellt ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="dffbe-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="dffbe-111">Kattintson a Verziókra.</span><span class="sxs-lookup"><span data-stu-id="dffbe-111">Click Versions.</span></span>
5. <span data-ttu-id="dffbe-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dffbe-112">Click New.</span></span>
6. <span data-ttu-id="dffbe-113">A Termékszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dffbe-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="dffbe-114">A termékre mutató hivatkozás a termékkonfigurációs modell egy verziójának felel meg.</span><span class="sxs-lookup"><span data-stu-id="dffbe-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="dffbe-115">Ez a lista csak olyan alaptermékeket jelenít meg, amelyek a megszorításon alapuló konfigurációs technológiát alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="dffbe-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="dffbe-116">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="dffbe-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="dffbe-117">Válassza ki, hogy mikor lesz elérhető a termékmodell-verzió.</span><span class="sxs-lookup"><span data-stu-id="dffbe-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="dffbe-118">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="dffbe-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="dffbe-119">Válassza ki a záró dátumot, amikor a termékmodell-verzió lejár, vagy válassza a Soha lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dffbe-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="dffbe-120">A Jóváhagyás gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="dffbe-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="dffbe-121">A Jóváhagyó mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="dffbe-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="dffbe-122">Válassza ki a termékmodellek műveletekben történő használatának jóváhagyásáért felelős személyt.</span><span class="sxs-lookup"><span data-stu-id="dffbe-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="dffbe-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="dffbe-123">Click OK.</span></span>
12. <span data-ttu-id="dffbe-124">Válassza ki valamelyik lehetőséget az Árazási mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="dffbe-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="dffbe-125">Aktiválja a termékmodell-verziót.</span><span class="sxs-lookup"><span data-stu-id="dffbe-125">Activate the product model version.</span></span> <span data-ttu-id="dffbe-126">Egyszerre csak egy termék lehet aktív egy termékmodell esetében.</span><span class="sxs-lookup"><span data-stu-id="dffbe-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="dffbe-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="dffbe-127">Close the page.</span></span>

