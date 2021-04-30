---
title: Dynamics 365 globalizációs szolgáltatások
description: Ez a témakör a Microsoft Dynamics 365 globalizációs szolgáltatásairól nyújt áttekintést.
author: JaneA07
manager: AnnBe
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8c6f3b7fb4dec0dffe55014e9e2d60620dc3b193
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893048"
---
# <a name="dynamics-365-globalization-services"></a><span data-ttu-id="2c100-103">Dynamics 365 globalizációs szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="2c100-103">Dynamics 365 globalization services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c100-104">A következő globalizációs szolgáltatások úgy konfigurálhatók, hogy bővítsék a Microsoft Dynamics 365 online szolgáltatásokban meglévő lehetőségeket:</span><span class="sxs-lookup"><span data-stu-id="2c100-104">The following globalization services can be configured to extend the capabilities that exist in some Microsoft Dynamics 365 online services:</span></span>

- <span data-ttu-id="2c100-105">A **Regulatory Configuration Service (RCS)** lehetővé teszi a különféle elektronikus dokumentumok és jelentések konfigurálást.</span><span class="sxs-lookup"><span data-stu-id="2c100-105">**Regulatory Configuration Service (RCS)** supports the configuration of different types of electronic documents and reports.</span></span> <span data-ttu-id="2c100-106">Az RCS az elektronikus jelentéskészítő (ER) tervező továbbfejlesztett verzióját biztosítja, ahol a konfigurációs adattár önálló szolgáltatás.</span><span class="sxs-lookup"><span data-stu-id="2c100-106">RCS provides an enhanced version of the Electronic reporting (ER) designer where the configuration repository is a standalone service.</span></span> <span data-ttu-id="2c100-107">A további tudnivalókat lásd: [Regulatory Configuration Service](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c100-107">For more information, see [Regulatory Configuration Service](rcs-overview.md).</span></span>
- <span data-ttu-id="2c100-108">Az **elektronikus számlázásban** az átalakítások, a digitális aláírások és a külső webes szolgáltatásokkal való kapcsolatának konfigurálható integrációja található, beleértve a tanúsítvány- és válaszkezelést.</span><span class="sxs-lookup"><span data-stu-id="2c100-108">**Electronic Invoicing** brings together configurable formats for transformations, digital signatures, and configurable integrations for connectivity with external web services, including certification and response handling.</span></span> <span data-ttu-id="2c100-109">További tájékoztatásért lásd: [Elektronikus számlázás](e-invoicing-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c100-109">For more information, see [Electronic Invoicing](e-invoicing-service-overview.md).</span></span>
- <span data-ttu-id="2c100-110">Az **adószámítás** nagyobb rugalmasságot biztosít a több adókód, az adókód meghatározása, az adószámítás tervezője és a futásidejű motor segítségével, hogy az egész világra kiterjedően megfeleljen az összetett adótörvények alkalmazásának.</span><span class="sxs-lookup"><span data-stu-id="2c100-110">**Tax Calculation** provides enhanced flexibility by supporting multiple tax IDs, tax code determination, the tax calculation designer, and a runtime engine to comply with complex tax regulations worldwide.</span></span> <span data-ttu-id="2c100-111">További információ: [adószámítás](global-tax-calcuation-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c100-111">For more information, see [Tax Calculation](global-tax-calcuation-service-overview.md).</span></span>

<span data-ttu-id="2c100-112">Ezek a globalizációs szolgáltatások gyárilag beépített integrációt biztosítanak a Dynamics 365 online szolgáltatásaival.</span><span class="sxs-lookup"><span data-stu-id="2c100-112">These globalization services provide out-of-box integration with the following Dynamics 365 online services.</span></span>

| <span data-ttu-id="2c100-113">Online szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="2c100-113">Online service</span></span> | <span data-ttu-id="2c100-114">RCS</span><span class="sxs-lookup"><span data-stu-id="2c100-114">RCS</span></span> | <span data-ttu-id="2c100-115">Elektronikus számlázás</span><span class="sxs-lookup"><span data-stu-id="2c100-115">Electronic Invoicing</span></span> | <span data-ttu-id="2c100-116">Áfaszámítás (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="2c100-116">Tax Calculation (Preview)</span></span> |
|----------------|-----|----------------------|---------------------------|
| <span data-ttu-id="2c100-117">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="2c100-117">Dynamics 365 Finance</span></span> | <span data-ttu-id="2c100-118">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-118">Yes</span></span> | <span data-ttu-id="2c100-119">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-119">Yes</span></span> | <span data-ttu-id="2c100-120">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-120">Yes</span></span> | 
| <span data-ttu-id="2c100-121">Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2c100-121">Dynamics 365 Supply Chain Management</span></span> | <span data-ttu-id="2c100-122">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-122">Yes</span></span> | <span data-ttu-id="2c100-123">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-123">Yes</span></span> | <span data-ttu-id="2c100-124">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-124">Yes</span></span> | 
| <span data-ttu-id="2c100-125">Dynamics 365 Project Operations</span><span class="sxs-lookup"><span data-stu-id="2c100-125">Dynamics 365 Project Operations</span></span> | <span data-ttu-id="2c100-126">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-126">Yes</span></span> | <span data-ttu-id="2c100-127">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-127">Yes</span></span> | <span data-ttu-id="2c100-128">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="2c100-128">Not applicable</span></span> | 
| <span data-ttu-id="2c100-129">Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2c100-129">Dynamics 365 Commerce</span></span> | <span data-ttu-id="2c100-130">Igen</span><span class="sxs-lookup"><span data-stu-id="2c100-130">Yes</span></span> | <span data-ttu-id="2c100-131">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="2c100-131">Not applicable</span></span> | <span data-ttu-id="2c100-132">Nem alkalmazható</span><span class="sxs-lookup"><span data-stu-id="2c100-132">Not applicable</span></span> | 

> [!NOTE]
> <span data-ttu-id="2c100-133">Az RCS Azure földrajzi helyeinek (földrajzi helyek) elérhetőségi eltérése miatt a szolgáltatás konfigurálása a megfelelő Dynamics 365 online szolgáltatáshoz kiválasztott földrajzi helyen kívülre továbbíthatja az ügyféladatokat.</span><span class="sxs-lookup"><span data-stu-id="2c100-133">Because of differences in the availability of Azure geographic locations (geos) for RCS, configuration of this service might cause customer data to be transferred outside the geo that is selected for the applicable Dynamics 365 online service.</span></span> <span data-ttu-id="2c100-134">A további tudnivalókat lásd: [Dynamics 365 és Power Platform: Elérhetőség, adatok helye, nyelv és honosítás](https://aka.ms/rcs/D365Productavailabilityguide).</span><span class="sxs-lookup"><span data-stu-id="2c100-134">For more information, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/rcs/D365Productavailabilityguide).</span></span>