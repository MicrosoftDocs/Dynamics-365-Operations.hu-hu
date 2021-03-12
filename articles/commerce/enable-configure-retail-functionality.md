---
title: Kiindulási adatok inicializálása új Commerce-környezetben
description: A cikk a Dynamics 365 Commerce inicializálási folyamatának részeként létrehozott adatokat ismerteti.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 8fd0b2743deab758538922f312853b622a512c0a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000745"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a><span data-ttu-id="39b8c-103">Kiindulási adatok inicializálása új Commerce-környezetben</span><span class="sxs-lookup"><span data-stu-id="39b8c-103">Initialize seed data in new Commerce environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="39b8c-104">A cikk a Dynamics 365 Commerce inicializálási folyamatának részeként létrehozott adatokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="39b8c-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="39b8c-105">Miután megtörtént a Kereskedelem megoldás telepítése a Microsoft Dynamics Lifecycle Services (LCS) segítségével, inicializálni kell a kereskedelmi konfigurációt, hogy létrejöjjenek az alapvető konfigurációs adatok.</span><span class="sxs-lookup"><span data-stu-id="39b8c-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39b8c-106">A kereskedelmi konfiguráció inicializálása előtt, győződjön meg arról, hogy beállított egy nyelvet és egy postai címet minden jogi személyhez, amelynél kereskedelmi üzletet fog beállítani.</span><span class="sxs-lookup"><span data-stu-id="39b8c-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="39b8c-107">Ezt a lépést meg kell ismételni minden egyes jogi személy esetében, amelyet kereskedelemre akar használni.</span><span class="sxs-lookup"><span data-stu-id="39b8c-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="39b8c-108">A kereskedelmi konfiguráció inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="39b8c-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="39b8c-109">Indítsa el a Commerce ügyfelet.</span><span class="sxs-lookup"><span data-stu-id="39b8c-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="39b8c-110">Kattintson a **Kiskereskedelem és kereskedelem** &gt; **Központ beállítása** &gt; **Paraméterek** &gt; **Kiskereskedelmi paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39b8c-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="39b8c-111">Kattintson az **Inicializálás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="39b8c-111">Click **Initialize**.</span></span>

<span data-ttu-id="39b8c-112">Az inicializálási a következő alapértelmezett konfigurációs adatokat hozza létre:</span><span class="sxs-lookup"><span data-stu-id="39b8c-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="39b8c-113">Kereskedelmi tervezés és ütemezés feladatai és alfeladatai</span><span class="sxs-lookup"><span data-stu-id="39b8c-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="39b8c-114">Kereskedelmi csatorna sémája</span><span class="sxs-lookup"><span data-stu-id="39b8c-114">Commerce channel schema</span></span>
- <span data-ttu-id="39b8c-115">Kereskedelmi ütemezések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="39b8c-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="39b8c-116">Alapértelmezett képernyő-elrendezések, beleértve a gombrácsokat, képeket és témákat</span><span class="sxs-lookup"><span data-stu-id="39b8c-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="39b8c-117">Időzóna adatai</span><span class="sxs-lookup"><span data-stu-id="39b8c-117">Time zone information</span></span>
- <span data-ttu-id="39b8c-118">Pénztári (POS) műveletek</span><span class="sxs-lookup"><span data-stu-id="39b8c-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="39b8c-119">POS-engedélyek</span><span class="sxs-lookup"><span data-stu-id="39b8c-119">POS permissions</span></span>
- <span data-ttu-id="39b8c-120">Csatornajelentések</span><span class="sxs-lookup"><span data-stu-id="39b8c-120">Channel reports</span></span>
- <span data-ttu-id="39b8c-121">Attribútum metaadatai</span><span class="sxs-lookup"><span data-stu-id="39b8c-121">Attribute metadata</span></span>
- <span data-ttu-id="39b8c-122">Entitás-ellenőrzési sablonok</span><span class="sxs-lookup"><span data-stu-id="39b8c-122">Entity validation templates</span></span>
- <span data-ttu-id="39b8c-123">Kötegelt feladat a Commerce Data Exchange munkamenet-előzményeinek törlésére</span><span class="sxs-lookup"><span data-stu-id="39b8c-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="39b8c-124">Továbbá, a fizetésikártya-iparághoz (PCI) kapcsolódó naplózás engedélyezett a Commerce adatbázisa esetében.</span><span class="sxs-lookup"><span data-stu-id="39b8c-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="39b8c-125">Nincs lehetőség a Kereskedelmi tervezés és ütemezés külön konfigurálására.</span><span class="sxs-lookup"><span data-stu-id="39b8c-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="39b8c-126">Ez az opció lehetővé teszi a Kereskedelmi tervezés és ütemezés konfigurációjának visszaállítását az alapértelmezett beállításokra.</span><span class="sxs-lookup"><span data-stu-id="39b8c-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="39b8c-127">Az inicializálás befejezése után konfigurálni kell a kiegészítő kereskedelmi adatokat.</span><span class="sxs-lookup"><span data-stu-id="39b8c-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="39b8c-128">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="39b8c-128">Here are some examples:</span></span>

- <span data-ttu-id="39b8c-129">Kereskedelmi paraméterek</span><span class="sxs-lookup"><span data-stu-id="39b8c-129">Commerce parameters</span></span>
- <span data-ttu-id="39b8c-130">Kereskedelmi ütemezés paraméterei</span><span class="sxs-lookup"><span data-stu-id="39b8c-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="39b8c-131">Kereskedelmi csatornák</span><span class="sxs-lookup"><span data-stu-id="39b8c-131">Commerce channels</span></span>
- <span data-ttu-id="39b8c-132">Jegyzékek és eszközök</span><span class="sxs-lookup"><span data-stu-id="39b8c-132">Registers and devices</span></span>
- <span data-ttu-id="39b8c-133">Szortimentek</span><span class="sxs-lookup"><span data-stu-id="39b8c-133">Assortments</span></span>
