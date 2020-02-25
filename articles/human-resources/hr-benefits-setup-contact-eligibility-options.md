---
title: A személyes kapcsolattartó jogosultsági beállításainak konfigurálása
description: A Microsoft Dynamics 365 Human Resources rendszerben konfigurálhatja a személyes kapcsolattartók jogosultsági beállításait. A személyes kapcsolattartók lehetnek kedvezményezettek vagy függő felek.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a50c5e54d224a2f8607284eb105381ffb6ef7ad9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009301"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="ebd85-104">A személyes kapcsolattartó jogosultsági beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ebd85-104">Configure personal contact eligibility options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="ebd85-105">Ez a cikk bemutatja, hogyan lehet konfigurálni a Microsoft Dynamics 365 Human Resources rendszer juttatásaiban használt személyes kapcsolattartók típusait.</span><span class="sxs-lookup"><span data-stu-id="ebd85-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ebd85-106">A személyes kapcsolattartók lehetnek kedvezményezettek vagy függő felek.</span><span class="sxs-lookup"><span data-stu-id="ebd85-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="ebd85-107">A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Személyes kapcsolattartó jogosultsági beállításai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebd85-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="ebd85-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebd85-108">Select **New**.</span></span>

3. <span data-ttu-id="ebd85-109">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="ebd85-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="ebd85-110">Mező</span><span class="sxs-lookup"><span data-stu-id="ebd85-110">Field</span></span> | <span data-ttu-id="ebd85-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="ebd85-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="ebd85-112">**Jogosultsági beállítás**</span><span class="sxs-lookup"><span data-stu-id="ebd85-112">**Eligibility option**</span></span> | <span data-ttu-id="ebd85-113">Az egyedi jogosultsági beállítást azonosító egyedi név vagy kód.</span><span class="sxs-lookup"><span data-stu-id="ebd85-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="ebd85-114">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="ebd85-114">**Description**</span></span> | <span data-ttu-id="ebd85-115">A jogosultsági beállítás rövid leírása.</span><span class="sxs-lookup"><span data-stu-id="ebd85-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="ebd85-116">**Kapcsolattartói jogosultság kódja**</span><span class="sxs-lookup"><span data-stu-id="ebd85-116">**Contact eligibility code**</span></span> | <span data-ttu-id="ebd85-117">A személyes jogosultsági beállítást legjobban leíró rendszerkód.</span><span class="sxs-lookup"><span data-stu-id="ebd85-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="ebd85-118">A következő lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="ebd85-118">You can choose from:</span></span> <ul><li><span data-ttu-id="ebd85-119">Kapcsolat</span><span class="sxs-lookup"><span data-stu-id="ebd85-119">Relationship</span></span></li><li><span data-ttu-id="ebd85-120">Diák</span><span class="sxs-lookup"><span data-stu-id="ebd85-120">Student</span></span></li><li><span data-ttu-id="ebd85-121">Felnőtt korú függő fél</span><span class="sxs-lookup"><span data-stu-id="ebd85-121">Overage dependent</span></span></li><li><span data-ttu-id="ebd85-122">Nagykorú fogyatékossággal élő függő fél</span><span class="sxs-lookup"><span data-stu-id="ebd85-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="ebd85-123">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="ebd85-123">**Status**</span></span> | <span data-ttu-id="ebd85-124">A jogosultsági beállítás állapota.</span><span class="sxs-lookup"><span data-stu-id="ebd85-124">The status of the eligibility option.</span></span> <span data-ttu-id="ebd85-125">Ha a jogosultsági beállítás állapota inaktív értékre van állítva, akkor nem lehet kiválasztani a személyes kapcsolattartókra vonatkozó jogosultsági beállításként.</span><span class="sxs-lookup"><span data-stu-id="ebd85-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="ebd85-126">**Kapcsolat**</span><span class="sxs-lookup"><span data-stu-id="ebd85-126">**Relationship**</span></span> | <span data-ttu-id="ebd85-127">A személyes kapcsolattartó és az alkalmazott közötti kapcsolatot határozza meg.</span><span class="sxs-lookup"><span data-stu-id="ebd85-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="ebd85-128">Ez a mező csak akkor aktív, ha a kapcsolattartó jogosultsági kódja a Kapcsolat értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="ebd85-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="ebd85-129">**Kor**</span><span class="sxs-lookup"><span data-stu-id="ebd85-129">**Age**</span></span> | <span data-ttu-id="ebd85-130">A juttatási konstrukció jogosult személyes kapcsolattartójának maximális életkora.</span><span class="sxs-lookup"><span data-stu-id="ebd85-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="ebd85-131">Ez a mező csak akkor aktív, ha választ egy kapcsolatot.</span><span class="sxs-lookup"><span data-stu-id="ebd85-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="ebd85-132">A rendszer összehasonlítja ezt az életkort a személyes kapcsolattartó számított életkorával.</span><span class="sxs-lookup"><span data-stu-id="ebd85-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="ebd85-133">Számított életkor: (fedezeti dátum – személyes kapcsolattartó születési dátuma / 365).</span><span class="sxs-lookup"><span data-stu-id="ebd85-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="ebd85-134">Ez a szám mindig egész szám.</span><span class="sxs-lookup"><span data-stu-id="ebd85-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="ebd85-135">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ebd85-135">Select **Save**.</span></span> 
