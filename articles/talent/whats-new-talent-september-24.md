---
title: "Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. szeptember 24.)"
description: "Ez a témakör a Microsoft Dynamics 365 for Talent Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le."
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 94950fbe5c1aad3dfbd3de59d1bcb47337ff68ea
ms.openlocfilehash: aeb75fe4c775b9003c6429de536498f495224098
ms.contentlocale: hu-hu
ms.lasthandoff: 09/24/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-24-2018"></a><span data-ttu-id="21dd5-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. szeptember 24.)</span><span class="sxs-lookup"><span data-stu-id="21dd5-103">What's new or changed in Dynamics 365 for Talent Core HR (September 24, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="21dd5-104">**Build 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="21dd5-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="21dd5-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="21dd5-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="21dd5-106">Pénznem hozzáadva a Juttatásokhoz</span><span class="sxs-lookup"><span data-stu-id="21dd5-106">Currency added to Benefits</span></span>

<span data-ttu-id="21dd5-107">A juttatáscsomagokat frissítettük, hogy tartalmazzák a juttatás pénznemét.</span><span class="sxs-lookup"><span data-stu-id="21dd5-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="21dd5-108">Ez az új mező a dolgozó regisztrált juttatásainál is megtalálható.</span><span class="sxs-lookup"><span data-stu-id="21dd5-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="21dd5-109">Ez az új mező a Juttatások karbantartása és a Juttatások listájának megtekintése biztonsági jogosultság része.</span><span class="sxs-lookup"><span data-stu-id="21dd5-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="21dd5-110">A prorációs folyamat frissítése – Szabadság- és távollét</span><span class="sxs-lookup"><span data-stu-id="21dd5-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="21dd5-111">A szervezetek eltérően ítélhetik oda a szabadságot attól függően, hogy mikor csatlakoznak az alkalmazottak a vállalathoz, illetve mikor hagyják el azt.</span><span class="sxs-lookup"><span data-stu-id="21dd5-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="21dd5-112">A szervezetet elhagyó alkalmazottak esetében egyeseknek esetleg be kell fejezniük a díjat a megszűnési időpontban, míg másoknak az utolsó napot is ki kell használniuk az elhatárolási folyamat leállítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="21dd5-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="21dd5-113">Ezek a módosítások lehetőséget biztosítanak a szervezetek számára, hogy kiválasszák, mikor szeretnék befejezni a regisztrációt a felmondási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="21dd5-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="21dd5-114">Ezek az új lehetőségek részei a Dolgozó elbocsátása és a Dolgozó elbocsátása a vezetői önkiszolgáló felületről jogosultságoknak.</span><span class="sxs-lookup"><span data-stu-id="21dd5-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="21dd5-115">Egyéb változások</span><span class="sxs-lookup"><span data-stu-id="21dd5-115">Other changes</span></span>

<span data-ttu-id="21dd5-116">Ebben a verzióban számos további hibajavítás is található.</span><span class="sxs-lookup"><span data-stu-id="21dd5-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="21dd5-117">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="21dd5-117">Known Issue</span></span>

-   <span data-ttu-id="21dd5-118">**Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői.</span><span class="sxs-lookup"><span data-stu-id="21dd5-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="21dd5-119">Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="21dd5-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="21dd5-120">(Ezt a problémát kijavítjuk a következő platformfrissítéssel.)</span><span class="sxs-lookup"><span data-stu-id="21dd5-120">(This issue will be fixed in the next platform update.)</span></span>

