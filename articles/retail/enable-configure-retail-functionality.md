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
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 80fa443fc235496a111a8a866d2e703202721268
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="a5247-103">A kiindulási adatok inicializálása új Retail-környezetekben</span><span class="sxs-lookup"><span data-stu-id="a5247-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a5247-104">A cikk a Microsoft Dynamics 365 for Retail inicializálási folyamatának részeként létrehozott adatokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="a5247-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="a5247-105">Miután megtörtént a Kiskereskedelem megoldás telepítése a Microsoft Dynamics Lifecycle Services (LCS) segítségével, inicializálni kell a kiskereskedelmi konfigurációt, hogy létrejöjjenek az alapvető konfigurációs adatok.</span><span class="sxs-lookup"><span data-stu-id="a5247-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span> <span data-ttu-id="a5247-106">**Fontos:** A kiskereskedelmi konfiguráció inicializálása előtt, győződjön meg arról, hogy beállított egy nyelvet és egy postai címet minden jogi személyhez, amelynél kiskereskedelmi üzletet fog beállítani.</span><span class="sxs-lookup"><span data-stu-id="a5247-106">**Important:** Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="a5247-107">Ezt a lépést meg kell ismételni minden egyes jogi személy esetében, amelyet kiskereskedelemre akar használni.</span><span class="sxs-lookup"><span data-stu-id="a5247-107">This step must be completed for each legal entity that you use for retail.</span></span> <span data-ttu-id="a5247-108">A kiskereskedelmi konfiguráció inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a5247-108">To initialize the retail configuration, follow these steps.</span></span>

1.  <span data-ttu-id="a5247-109">Indítsa el a Dynamics 365 for Retail klienst.</span><span class="sxs-lookup"><span data-stu-id="a5247-109">Start the Dynamics 365 for Retail client.</span></span>
2.  <span data-ttu-id="a5247-110">Kattintson a **Kiskereskedelem** &gt; **Központ beállítása** &gt; **Paraméterek** &gt; **Kiskereskedelmi paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a5247-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3.  <span data-ttu-id="a5247-111">Kattintson az **Inicializálás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a5247-111">Click **Initialize**.</span></span>

<span data-ttu-id="a5247-112">Az inicializálási a következő alapértelmezett konfigurációs adatokat hozza létre:</span><span class="sxs-lookup"><span data-stu-id="a5247-112">Initialization creates the following default configuration data:</span></span>

-   <span data-ttu-id="a5247-113">Kiskereskedelmi tervezés és ütemezés feladatai és alfeladatai</span><span class="sxs-lookup"><span data-stu-id="a5247-113">Retail scheduler jobs and subjobs</span></span>
-   <span data-ttu-id="a5247-114">Kiskereskedelmi csatornaséma</span><span class="sxs-lookup"><span data-stu-id="a5247-114">Retail channel schema</span></span>
-   <span data-ttu-id="a5247-115">Kiskereskedelmi elosztási ütemezések</span><span class="sxs-lookup"><span data-stu-id="a5247-115">Retail distribution schedules</span></span>
-   <span data-ttu-id="a5247-116">Alapértelmezett képernyő-elrendezések, beleértve a gombrácsokat, képeket és témákat</span><span class="sxs-lookup"><span data-stu-id="a5247-116">Default screen layouts, which include button grids, images, and themes</span></span>
-   <span data-ttu-id="a5247-117">Időzóna adatai</span><span class="sxs-lookup"><span data-stu-id="a5247-117">Time zone information</span></span>
-   <span data-ttu-id="a5247-118">Pénztári (POS) műveletek</span><span class="sxs-lookup"><span data-stu-id="a5247-118">Point-of-sale (POS) operations</span></span>
-   <span data-ttu-id="a5247-119">POS-engedélyek</span><span class="sxs-lookup"><span data-stu-id="a5247-119">POS permissions</span></span>
-   <span data-ttu-id="a5247-120">Csatornajelentések</span><span class="sxs-lookup"><span data-stu-id="a5247-120">Channel reports</span></span>
-   <span data-ttu-id="a5247-121">Attribútum metaadatai</span><span class="sxs-lookup"><span data-stu-id="a5247-121">Attribute metadata</span></span>
-   <span data-ttu-id="a5247-122">Entitás-ellenőrzési sablonok</span><span class="sxs-lookup"><span data-stu-id="a5247-122">Entity validation templates</span></span>
-   <span data-ttu-id="a5247-123">Kötegelt feladat a Commerce Data Exchange-munkamenet-előzmények törlésére</span><span class="sxs-lookup"><span data-stu-id="a5247-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="a5247-124">Továbbá, a fizetésikártya-iparághoz (PCI) kapcsolódó naplózás engedélyezett a Dynamics 365 for Retail adatbázis esetében.</span><span class="sxs-lookup"><span data-stu-id="a5247-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span> <span data-ttu-id="a5247-125">**Megjegyzés:** Nincs lehetőség a Kiskereskedelmi tervezés és ütemezés külön konfigurálására.</span><span class="sxs-lookup"><span data-stu-id="a5247-125">**Note:** There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="a5247-126">Ez az opció lehetővé teszi a Kiskereskedelmi tervezés és ütemezés konfigurációjának visszaállítását az alapértelmezett beállításokra.</span><span class="sxs-lookup"><span data-stu-id="a5247-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span> <span data-ttu-id="a5247-127">Az inicializálás befejezése után konfigurálni kell a kiegészítő kiskereskedelmi adatokat.</span><span class="sxs-lookup"><span data-stu-id="a5247-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="a5247-128">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="a5247-128">Here are some examples:</span></span>

-   <span data-ttu-id="a5247-129">Kiskereskedelmi paraméterek</span><span class="sxs-lookup"><span data-stu-id="a5247-129">Retail parameters</span></span>
-   <span data-ttu-id="a5247-130">Kiskereskedelmi tervezés és ütemezés paraméterei</span><span class="sxs-lookup"><span data-stu-id="a5247-130">Retail scheduler parameters</span></span>
-   <span data-ttu-id="a5247-131">Kiskereskedelmi csatornák</span><span class="sxs-lookup"><span data-stu-id="a5247-131">Retail channels</span></span>
-   <span data-ttu-id="a5247-132">Jegyzékek és eszközök</span><span class="sxs-lookup"><span data-stu-id="a5247-132">Registers and devices</span></span>
-   <span data-ttu-id="a5247-133">Szortimentek</span><span class="sxs-lookup"><span data-stu-id="a5247-133">Assortments</span></span>





