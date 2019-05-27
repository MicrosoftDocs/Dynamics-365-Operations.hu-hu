---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. augusztus)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-08-27
ms.dyn365.ops.version: Talent August 2018 update
ms.openlocfilehash: be76f29dc9d38cdf3c2d56120a830acae69937a4
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518148"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-august-2018"></a><span data-ttu-id="76e3f-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. augusztus)</span><span class="sxs-lookup"><span data-stu-id="76e3f-103">What's new or changed in Dynamics 365 for Talent Core HR (August 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="76e3f-104">**Build 8.1.104**</span><span class="sxs-lookup"><span data-stu-id="76e3f-104">**Build 8.1.104**</span></span>

<span data-ttu-id="76e3f-105">Ez a témakör a Dynamics 365 for Talent Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="76e3f-105">This topic describes features that are either new or changed in Dynamics 365 for Talent Core HR.</span></span>

## <a name="view-expiring-records-in-manager-self-service"></a><span data-ttu-id="76e3f-106">Lejáró rekordok megtekintése a Vezetői önkiszolgáló szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="76e3f-106">View expiring records in Manager self service</span></span>

<span data-ttu-id="76e3f-107">Mostantól megtekintheti a lejáró rekordokat a Vezetői önkiszolgáló szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="76e3f-107">You can now view expiring records in Manager self-service.</span></span> <span data-ttu-id="76e3f-108">Az új lehetőségek a lehetővé teszik annak beállítását, hogy milyen információk lesznek elérhetők megtekintésre a vezetők számára.</span><span class="sxs-lookup"><span data-stu-id="76e3f-108">New options are allow you to configure what information will be available for managers to view.</span></span> <span data-ttu-id="76e3f-109">Ezek közé az adatok közé tartoznak a következők:</span><span class="sxs-lookup"><span data-stu-id="76e3f-109">These include:</span></span>

-   <span data-ttu-id="76e3f-110">Diplomák</span><span class="sxs-lookup"><span data-stu-id="76e3f-110">Certificates</span></span>

-   <span data-ttu-id="76e3f-111">Azonosítószámok</span><span class="sxs-lookup"><span data-stu-id="76e3f-111">Identification numbers</span></span>

-   <span data-ttu-id="76e3f-112">Próbaidőszakok</span><span class="sxs-lookup"><span data-stu-id="76e3f-112">Probation periods</span></span>

-   <span data-ttu-id="76e3f-113">Szűrések</span><span class="sxs-lookup"><span data-stu-id="76e3f-113">Screenings</span></span>

-   <span data-ttu-id="76e3f-114">Tesztek</span><span class="sxs-lookup"><span data-stu-id="76e3f-114">Tests</span></span>

<span data-ttu-id="76e3f-115">Ez a funkció arra is lehetőséget nyújt, hogy megadja a tartományt, amelyben lejáró rekordokat keres.</span><span class="sxs-lookup"><span data-stu-id="76e3f-115">This feature also gives you the ability to specify the range of days in which to look for expiring records.</span></span>

## <a name="configurable-transfer-actions"></a><span data-ttu-id="76e3f-116">Konfigurálható átviteli műveletek</span><span class="sxs-lookup"><span data-stu-id="76e3f-116">Configurable transfer actions</span></span>

<span data-ttu-id="76e3f-117">Beállítható szerepkörönként, hogy milyen beállítások legyenek elérhetők az átmozgatási kérelem bevitelekor.</span><span class="sxs-lookup"><span data-stu-id="76e3f-117">You can configure by role the options that will be available during the entry of a transfer request.</span></span> <span data-ttu-id="76e3f-118">Ez a funkció további rugalmasságot tesz lehetővé egy szervezet szerepkörei között.</span><span class="sxs-lookup"><span data-stu-id="76e3f-118">This feature provides additional flexibility across the roles in an organization.</span></span>

<span data-ttu-id="76e3f-119">Ha például az alkalmazott átvitelét kérő vezetőknek lehet, hogy nincs hozzáférése ahhoz hogy kompenzációs összegeket javasoljanak vagy adjanak meg vagy kiválasszák a feladatlistákat, amelyek társítva lesznek az átviteli kérelemhez.</span><span class="sxs-lookup"><span data-stu-id="76e3f-119">For example, managers requesting employee transfers may not have access to suggest or enter compensation amounts or select the task lists that will be associated with the transfer request.</span></span> <span data-ttu-id="76e3f-120">Ebben az esetben a vezetők létrehozáshatnak és beküldhetnek étviteli kérelmeket de nem adhatnak meg kompenzációs vagy feladatlista hozzárendeléseket.</span><span class="sxs-lookup"><span data-stu-id="76e3f-120">In this case, managers can create and submit transfer requests but are not allowed to enter compensation or task list assignments.</span></span> <span data-ttu-id="76e3f-121">Ugyanebben a konfigurációban a HR hozzá tudja rendelni az új kompenzációs értékeket, valamint, valamit hozzá tud rendelni minden olyan további ellenőrzőlistát, amelyet ki kell tölteni az átvitel befejezése eredményeképpen.</span><span class="sxs-lookup"><span data-stu-id="76e3f-121">In this same configuration, HR will be able to assign the new compensation values as well as assign any additional checklists to be completed as a result of the transfer completing.</span></span>

<span data-ttu-id="76e3f-122">Alapértelmezés szerint az új beállítási lehetőségek nem módosítják a szolgáltatásokat ezen frissítés előtt.</span><span class="sxs-lookup"><span data-stu-id="76e3f-122">By default, the new configuration options are set to not change the capabilities prior to this update.</span></span>

## <a name="leave-and-absence"></a><span data-ttu-id="76e3f-123">Szabadság és távollét</span><span class="sxs-lookup"><span data-stu-id="76e3f-123">Leave and absence</span></span>

<span data-ttu-id="76e3f-124">További dátummezők érhetők el a Szabadság és távollét szakaszban.</span><span class="sxs-lookup"><span data-stu-id="76e3f-124">There are now additional Date fields available in Leave and Absence.</span></span>

<span data-ttu-id="76e3f-125">Ezzel a szolgáltatással beállíthatja a halmozódási időszak alapját a terv szintjén, hogy bizonyos alkalmazotti dátumokat használjon.</span><span class="sxs-lookup"><span data-stu-id="76e3f-125">With this feature you can set the accrual period basis at the plan level to use specific employee dates.</span></span> <span data-ttu-id="76e3f-126">Ez lehetővé teszi a terv kezdési dátumától eltérő dátumok használatát a távollét halmozódási folyamatánál.</span><span class="sxs-lookup"><span data-stu-id="76e3f-126">This allows for dates other than the plan start date to be used during the leave accrual process.</span></span> <span data-ttu-id="76e3f-127">Alkalmazottspecifikus dátumok vonatkozóan lehetőségek a következő értékeket tartalmazzák:</span><span class="sxs-lookup"><span data-stu-id="76e3f-127">Options for employee specific dates include the following values:</span></span>

-   <span data-ttu-id="76e3f-128">Egyéni (jelen frissítés előtt is elérhető)</span><span class="sxs-lookup"><span data-stu-id="76e3f-128">Custom (available prior to this update)</span></span>

-   <span data-ttu-id="76e3f-129">Évforduló dátuma</span><span class="sxs-lookup"><span data-stu-id="76e3f-129">Anniversary date</span></span>

-   <span data-ttu-id="76e3f-130">Eredeti felvételi dátum</span><span class="sxs-lookup"><span data-stu-id="76e3f-130">Original hire date</span></span>

-   <span data-ttu-id="76e3f-131">Szolgálati idő dátuma</span><span class="sxs-lookup"><span data-stu-id="76e3f-131">Seniority date</span></span>

-   <span data-ttu-id="76e3f-132">A dolgozó helyesbített kezdési dátuma</span><span class="sxs-lookup"><span data-stu-id="76e3f-132">Worker’s adjusted start date</span></span>

-   <span data-ttu-id="76e3f-133">A dolgozó kezdési dátuma</span><span class="sxs-lookup"><span data-stu-id="76e3f-133">Worker’s start date</span></span>

<span data-ttu-id="76e3f-134">Ha úgy van konfigurálva, hogy az egyik alkalmazottspecifikus dátumot használja , a belépési folyamat a megadott dátumot használja a halmozódási időszakok kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="76e3f-134">When configured to use one of the employee specific dates, the enrollment process will use the specified date to calculate the accrual periods.</span></span> <span data-ttu-id="76e3f-135">A halmozódási időszak alapja megjelenik az alkalmazott belépési konstrukciójában, így megtudhatja, mi van használatban a halmozódási folyamatban.</span><span class="sxs-lookup"><span data-stu-id="76e3f-135">The accrual period basis is also displayed on the employee’s plan enrollment to help you understand what’s being used during the accrual process.</span></span>

## <a name="microsoft-word-integration"></a><span data-ttu-id="76e3f-136">Microsoft Word-integráció</span><span class="sxs-lookup"><span data-stu-id="76e3f-136">Microsoft Word integration</span></span>

<span data-ttu-id="76e3f-137">Dokumentumsablonok az egész Core HR-ben engedélyezve vannak.</span><span class="sxs-lookup"><span data-stu-id="76e3f-137">Document templates have been enabled throughout Core HR.</span></span> <span data-ttu-id="76e3f-138">Ezzel a funkcióval létrehozhat leveleket és jelentéseket az Ón által létrehozott Word-sablonok alapján.</span><span class="sxs-lookup"><span data-stu-id="76e3f-138">This feature allows you to create letters and reports based on Word templates that you create.</span></span>

<span data-ttu-id="76e3f-139">Ezzel a funkcióval kapcsolatos további információk az [Office integrációs oktatóanyagban](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json) érhetők el.</span><span class="sxs-lookup"><span data-stu-id="76e3f-139">Additional information about this feature is available in the [Office integration tutorial](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span></span>


## <a name="other-fixes"></a><span data-ttu-id="76e3f-140">Egyéb javítások</span><span class="sxs-lookup"><span data-stu-id="76e3f-140">Other fixes</span></span>

<span data-ttu-id="76e3f-141">Ez a verzió számos hibajavítást is tartalmaz, új entitások hozzáadása, meglévő entitások javításai és lokalizált címkemódosítások</span><span class="sxs-lookup"><span data-stu-id="76e3f-141">This release also includes a number of bug fixes, the addition of new entities, fixes to existing entities, and localized label changes.</span></span>
