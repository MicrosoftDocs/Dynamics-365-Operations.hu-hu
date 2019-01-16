---
title: "A kiindulási adatok inicializálása új Retail-környezetekben"
description: "A cikk a Microsoft Dynamics 365 for Retail inicializálási folyamatának részeként létrehozott adatokat ismerteti."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 52f0c52748958f0bebb6c40df01cfac10c0ed427
ms.contentlocale: hu-hu
ms.lasthandoff: 01/04/2019

---

# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="05b5d-103">A kiindulási adatok inicializálása új Retail-környezetekben</span><span class="sxs-lookup"><span data-stu-id="05b5d-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="05b5d-104">A cikk a Microsoft Dynamics 365 for Retail inicializálási folyamatának részeként létrehozott adatokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="05b5d-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="05b5d-105">Miután megtörtént a Kiskereskedelem megoldás telepítése a Microsoft Dynamics Lifecycle Services (LCS) segítségével, inicializálni kell a kiskereskedelmi konfigurációt, hogy létrejöjjenek az alapvető konfigurációs adatok.</span><span class="sxs-lookup"><span data-stu-id="05b5d-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05b5d-106">A kiskereskedelmi konfiguráció inicializálása előtt, győződjön meg arról, hogy beállított egy nyelvet és egy postai címet minden jogi személyhez, amelynél kiskereskedelmi üzletet fog beállítani.</span><span class="sxs-lookup"><span data-stu-id="05b5d-106">Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="05b5d-107">Ezt a lépést meg kell ismételni minden egyes jogi személy esetében, amelyet kiskereskedelemre akar használni.</span><span class="sxs-lookup"><span data-stu-id="05b5d-107">This step must be completed for each legal entity that you use for retail.</span></span>

<span data-ttu-id="05b5d-108">A kiskereskedelmi konfiguráció inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="05b5d-108">To initialize the retail configuration, follow these steps.</span></span>

1. <span data-ttu-id="05b5d-109">Indítsa el a Dynamics 365 for Retail klienst.</span><span class="sxs-lookup"><span data-stu-id="05b5d-109">Start the Dynamics 365 for Retail client.</span></span>
2. <span data-ttu-id="05b5d-110">Kattintson a **Kiskereskedelem** &gt; **Központ beállítása** &gt; **Paraméterek** &gt; **Kiskereskedelmi paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="05b5d-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3. <span data-ttu-id="05b5d-111">Kattintson az **Inicializálás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="05b5d-111">Click **Initialize**.</span></span>

<span data-ttu-id="05b5d-112">Az inicializálási a következő alapértelmezett konfigurációs adatokat hozza létre:</span><span class="sxs-lookup"><span data-stu-id="05b5d-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="05b5d-113">Kiskereskedelmi tervezés és ütemezés feladatai és alfeladatai</span><span class="sxs-lookup"><span data-stu-id="05b5d-113">Retail scheduler jobs and subjobs</span></span>
- <span data-ttu-id="05b5d-114">Kiskereskedelmi csatornaséma</span><span class="sxs-lookup"><span data-stu-id="05b5d-114">Retail channel schema</span></span>
- <span data-ttu-id="05b5d-115">Kiskereskedelmi elosztási ütemezések</span><span class="sxs-lookup"><span data-stu-id="05b5d-115">Retail distribution schedules</span></span>
- <span data-ttu-id="05b5d-116">Alapértelmezett képernyő-elrendezések, beleértve a gombrácsokat, képeket és témákat</span><span class="sxs-lookup"><span data-stu-id="05b5d-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="05b5d-117">Időzóna adatai</span><span class="sxs-lookup"><span data-stu-id="05b5d-117">Time zone information</span></span>
- <span data-ttu-id="05b5d-118">Pénztári (POS) műveletek</span><span class="sxs-lookup"><span data-stu-id="05b5d-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="05b5d-119">POS-engedélyek</span><span class="sxs-lookup"><span data-stu-id="05b5d-119">POS permissions</span></span>
- <span data-ttu-id="05b5d-120">Csatornajelentések</span><span class="sxs-lookup"><span data-stu-id="05b5d-120">Channel reports</span></span>
- <span data-ttu-id="05b5d-121">Attribútum metaadatai</span><span class="sxs-lookup"><span data-stu-id="05b5d-121">Attribute metadata</span></span>
- <span data-ttu-id="05b5d-122">Entitás-ellenőrzési sablonok</span><span class="sxs-lookup"><span data-stu-id="05b5d-122">Entity validation templates</span></span>
- <span data-ttu-id="05b5d-123">Kötegelt feladat a Commerce Data Exchange-munkamenet-előzmények törlésére</span><span class="sxs-lookup"><span data-stu-id="05b5d-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="05b5d-124">Továbbá, a fizetésikártya-iparághoz (PCI) kapcsolódó naplózás engedélyezett a Dynamics 365 for Retail adatbázis esetében.</span><span class="sxs-lookup"><span data-stu-id="05b5d-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span>

> [!NOTE]
> <span data-ttu-id="05b5d-125">Nincs lehetőség a Kiskereskedelmi tervezés és ütemezés külön konfigurálására.</span><span class="sxs-lookup"><span data-stu-id="05b5d-125">There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="05b5d-126">Ez az opció lehetővé teszi a Kiskereskedelmi tervezés és ütemezés konfigurációjának visszaállítását az alapértelmezett beállításokra.</span><span class="sxs-lookup"><span data-stu-id="05b5d-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span>

<span data-ttu-id="05b5d-127">Az inicializálás befejezése után konfigurálni kell a kiegészítő kiskereskedelmi adatokat.</span><span class="sxs-lookup"><span data-stu-id="05b5d-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="05b5d-128">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="05b5d-128">Here are some examples:</span></span>

- <span data-ttu-id="05b5d-129">Kiskereskedelmi paraméterek</span><span class="sxs-lookup"><span data-stu-id="05b5d-129">Retail parameters</span></span>
- <span data-ttu-id="05b5d-130">Kiskereskedelmi tervezés és ütemezés paraméterei</span><span class="sxs-lookup"><span data-stu-id="05b5d-130">Retail scheduler parameters</span></span>
- <span data-ttu-id="05b5d-131">Kiskereskedelmi csatornák</span><span class="sxs-lookup"><span data-stu-id="05b5d-131">Retail channels</span></span>
- <span data-ttu-id="05b5d-132">Jegyzékek és eszközök</span><span class="sxs-lookup"><span data-stu-id="05b5d-132">Registers and devices</span></span>
- <span data-ttu-id="05b5d-133">Szortimentek</span><span class="sxs-lookup"><span data-stu-id="05b5d-133">Assortments</span></span>

