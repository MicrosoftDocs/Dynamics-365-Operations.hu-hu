---
title: Termékkonfigurációs modell jóváhagyása
description: Ezen eljárás futtatásához szükség van legalább egy elérhető termékkonfigurációs modellre.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920507"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="765e6-103">Termékkonfigurációs modell jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="765e6-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="765e6-104">Ezen eljárás futtatásához szükség van legalább egy elérhető termékkonfigurációs modellre.</span><span class="sxs-lookup"><span data-stu-id="765e6-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="765e6-105">Ezen eljárás az USMF bemutatócég felső kategóriás hangszóró modelljét használja.</span><span class="sxs-lookup"><span data-stu-id="765e6-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="765e6-106">Fontos megjegyezni, hogy a modell már jóvá van hagyva, de az eljárás végigvezeti a teljes folyamaton.</span><span class="sxs-lookup"><span data-stu-id="765e6-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="765e6-107">Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.</span><span class="sxs-lookup"><span data-stu-id="765e6-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="765e6-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="765e6-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="765e6-109">Válassza ki a Felső kategóriás modellt ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="765e6-109">Select the High end speaker model for this procedure.</span></span>  
1. <span data-ttu-id="765e6-110">Válassza a **Verziók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="765e6-110">Select **Versions**.</span></span>
1. <span data-ttu-id="765e6-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="765e6-111">Select **New**.</span></span>
1. <span data-ttu-id="765e6-112">A **Termékszám** mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="765e6-112">In the **Product number** field, enter or select a value.</span></span>
    * <span data-ttu-id="765e6-113">A termékre mutató hivatkozás a termékkonfigurációs modell egy verziójának felel meg.</span><span class="sxs-lookup"><span data-stu-id="765e6-113">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="765e6-114">Ez a lista csak olyan alaptermékeket jelenít meg, amelyek a megszorításon alapuló konfigurációs technológiát alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="765e6-114">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
1. <span data-ttu-id="765e6-115">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="765e6-115">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="765e6-116">Válassza ki, hogy mikor lesz elérhető a termékmodell-verzió.</span><span class="sxs-lookup"><span data-stu-id="765e6-116">Select when the product model version will be available.</span></span>  
1. <span data-ttu-id="765e6-117">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="765e6-117">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="765e6-118">Válassza ki a záró dátumot, amikor a termékmodell-verzió lejár, vagy válassza a Soha lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="765e6-118">Select an end date when this product model version will expire, or select Never.</span></span>  
1. <span data-ttu-id="765e6-119">A **Jóváhagyás** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="765e6-119">Select **Approve** to open the drop dialog.</span></span>
1. <span data-ttu-id="765e6-120">A **Jóváhagyó** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="765e6-120">In the **Approved by** field, enter or select a value.</span></span>
    * <span data-ttu-id="765e6-121">Válassza ki a termékmodellek műveletekben történő használatának jóváhagyásáért felelős személyt.</span><span class="sxs-lookup"><span data-stu-id="765e6-121">Select the person who is responsible for approving product models for use in operations.</span></span>  
1. <span data-ttu-id="765e6-122">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="765e6-122">Select **OK**.</span></span>
1. <span data-ttu-id="765e6-123">Válassza ki valamelyik lehetőséget az **Árazási mód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="765e6-123">In the **Pricing method** field, select an option.</span></span>
    * <span data-ttu-id="765e6-124">Aktiválja a termékmodell-verziót.</span><span class="sxs-lookup"><span data-stu-id="765e6-124">Activate the product model version.</span></span> <span data-ttu-id="765e6-125">Egyszerre csak egy termék lehet aktív egy termékmodell esetében.</span><span class="sxs-lookup"><span data-stu-id="765e6-125">It is only possible to have one product active for one product model at a time.</span></span>  
1. <span data-ttu-id="765e6-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="765e6-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]