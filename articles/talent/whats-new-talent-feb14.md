---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. február 14.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5f96dd60652705de820e0661d417dcaee8143561
ms.sourcegitcommit: 5384200c3e33510c5b3ac31f2b22443e1076251f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2019
ms.locfileid: "390664"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-14-2019"></a><span data-ttu-id="492df-103">Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. február 14.)</span><span class="sxs-lookup"><span data-stu-id="492df-103">What's new or changed in Dynamics 365 for Talent (February 14, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="492df-104">Ez a témakör a Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="492df-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="492df-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="492df-105">Changes in Attract</span></span>
<span data-ttu-id="492df-106">Vannak kisebb hibajavítások ebben a verzióban.</span><span class="sxs-lookup"><span data-stu-id="492df-106">There are minor bug fixes included with this release.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="492df-107">Változások az Onboarding alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="492df-107">Changes in Onboarding</span></span>
<span data-ttu-id="492df-108">Vannak kisebb hibajavítások ebben a verzióban.</span><span class="sxs-lookup"><span data-stu-id="492df-108">There are minor bug fixes included with this release.</span></span>
 
## <a name="changes-in-core-hr"></a><span data-ttu-id="492df-109">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="492df-109">Changes in Core HR</span></span> 
<span data-ttu-id="492df-110">**Build 8.1.2146**</span><span class="sxs-lookup"><span data-stu-id="492df-110">**Build 8.1.2146**</span></span>

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a><span data-ttu-id="492df-111">Alkalmazott fix kompenzációs entitás nem exportálja az összes rekordot</span><span class="sxs-lookup"><span data-stu-id="492df-111">Employee fixed compensation entity doesn't export all records</span></span>
<span data-ttu-id="492df-112">Ezzel a módosítással az **Alkalmazotti fix kompenzáció** entitás exportálja az összes rekordot.</span><span class="sxs-lookup"><span data-stu-id="492df-112">With this change, the **Employee fixed compensation** entity will now export all records.</span></span> <span data-ttu-id="492df-113">Az entitás használható alkalmazottakhoz tartozó meglévő fix kompenzációs rekord létrehozására és frissítésére.</span><span class="sxs-lookup"><span data-stu-id="492df-113">The entity can be used to create and update existing fixed compensation records for employees.</span></span> 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a><span data-ttu-id="492df-114">Munkaviszony záró dátuma nem figyelembe veszi az alkalmazott preferált időzóna-beállításait</span><span class="sxs-lookup"><span data-stu-id="492df-114">Employment end date doesn't honor employee preferred time zone settings</span></span>
<span data-ttu-id="492df-115">Munkaviszony záró dátumai mostantól figyelembe veszik a felhasználó által előnyben részesített időzónát munkaviszony létrehozásakor vagy befejezésekor a vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="492df-115">Employment end dates are now honoring the user-preferred time zone when creating or ending employment with a company.</span></span>
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a><span data-ttu-id="492df-116">Egyesült Királysági címek közép-kelet-Svájc címként jelennek meg az analitikában</span><span class="sxs-lookup"><span data-stu-id="492df-116">UK addresses display in Analytics as Eastern Switzerland addresses</span></span>
<span data-ttu-id="492df-117">Ebben a verzióban, a változtatás történt a címekben rossz hozzárendelésének megoldására a **Személyzeti kezelése** "Létszám hely alapján" jelentésben.</span><span class="sxs-lookup"><span data-stu-id="492df-117">In this release, a change has been made to correct misalignment in addresses in the **Personnel Management** "Headcount by location" report.</span></span>
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a><span data-ttu-id="492df-118">Felmondási kód nem lett kitöltve a dolgozó beosztáshozzárendelési rekordján a beosztás befejezésekor.</span><span class="sxs-lookup"><span data-stu-id="492df-118">Termination code is not populated on the worker position assignment record when ending the position</span></span>
<span data-ttu-id="492df-119">Módosítás történt a „Felmondás oka” kód alapértelmezett feltűntetése érdekében, amikor az alkalmazott beosztáshozzárendelése megszűnik.</span><span class="sxs-lookup"><span data-stu-id="492df-119">A change has been made to default the "Termination reason" code when ending the employees position assignment.</span></span>

### <a name="new-entity-created-for-job-compensation-levels"></a><span data-ttu-id="492df-120">Új entitiás lett létrehozva a feladatkompenzációs szintekhez</span><span class="sxs-lookup"><span data-stu-id="492df-120">New entity created for job compensation levels</span></span>
<span data-ttu-id="492df-121">Új datamanagement framework (DMF) entitás lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="492df-121">A new data management framework (DMF) entity was created.</span></span> <span data-ttu-id="492df-122">Az entitás lehetőséget biztosít kompenzációs szintek, a piaci érték és felmérési adatok létrehozására és frissítésére a rendszerben definiált egyes munkákhoz.</span><span class="sxs-lookup"><span data-stu-id="492df-122">The entity provides for creation and updates to compensation levels, market values, and survey information for each job defined in the system.</span></span>
