---
title: "Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. november 15.)"
description: "Ez a témakör a Microsoft Dynamics 365 for Talent Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le."
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
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
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 3cc19a8e5f726495e698a3a2f4ccce7460a61657
ms.openlocfilehash: 0e9de5e36e67941ab09c773a63b0e7045105a07e
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a><span data-ttu-id="3c08b-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. november 15.)</span><span class="sxs-lookup"><span data-stu-id="3c08b-103">What's new or changed in Dynamics 365 for Talent Core HR (November 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3c08b-104">**Build 8.1.2045**</span><span class="sxs-lookup"><span data-stu-id="3c08b-104">**Build 8.1.2045**</span></span>

<span data-ttu-id="3c08b-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="3c08b-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="other-changesfixes"></a><span data-ttu-id="3c08b-106">Egyéb változtatások/javítások</span><span class="sxs-lookup"><span data-stu-id="3c08b-106">Other changes/fixes</span></span>

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a><span data-ttu-id="3c08b-107">Nem lehet módosítani az alkalmazott aktuális beosztását egy jövőbeli nyitott pozícióra</span><span class="sxs-lookup"><span data-stu-id="3c08b-107">Unable to change employee´s current position to a future open position</span></span>

<span data-ttu-id="3c08b-108">Módosítás történt a beosztástranszferek módosítása érdekében, amikor a beosztás csak a jövőben válik elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="3c08b-108">A change has been made to enable position transfers when the position is only available in the future.</span></span> 

### <a name="position-does-not-display-when-creating-a-new-employee"></a><span data-ttu-id="3c08b-109">A beosztás nem jelenik meg az új alkalmazott létrehozásakor</span><span class="sxs-lookup"><span data-stu-id="3c08b-109">Position does not display when creating a new employee</span></span>

<span data-ttu-id="3c08b-110">Módosítás történt, és ezentúl az összes nyitott pozíció megjelenik, amelyek társításra elérhetők, amikor új alkalmazottat vesznek fel a Talent alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="3c08b-110">A change has been made to display all open positions that are available for assignment when hiring new employees in Talent.</span></span> <span data-ttu-id="3c08b-111">Ez a korábbi beosztásokat is, és a jövőre dátumozott beosztásokat is tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="3c08b-111">This includes historical positions or if the postitions have been future dated.</span></span> <span data-ttu-id="3c08b-112">A beosztások most helyesen jelennek meg az alkalmazotti jogviszony kezdési dátum alapján.</span><span class="sxs-lookup"><span data-stu-id="3c08b-112">Positions will now appear correctly based on the employment start date.</span></span> 

### <a name="termination-date-is-displaying-based-on-user-settings"></a><span data-ttu-id="3c08b-113">A munkaviszony megszűnésének dátuma a felhasználói beállításoktól függően jelenik meg</span><span class="sxs-lookup"><span data-stu-id="3c08b-113">Termination date is displaying based on user settings</span></span>

<span data-ttu-id="3c08b-114">Módosítás történt, és ezentúl a múltbéli alkalmazottak listája tükrözni fogja a felhasználó előnyben részesített időzónájához való eltolódást a munkaviszony megszűnésének dátumának megtekintésekor.</span><span class="sxs-lookup"><span data-stu-id="3c08b-114">A change has been made to the past employees list to account for any time zone offsets for the employees preferred time zone when viewing the termination date.</span></span>

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a><span data-ttu-id="3c08b-115">Hozzám rendelt munkaelemek hivatkozásai nem a helyes információt jelenítik meg</span><span class="sxs-lookup"><span data-stu-id="3c08b-115">Work items assigned to me links not displaying the correct information</span></span>

<span data-ttu-id="3c08b-116">A módosítással után a listában található egyéni munkaelemek részleteire való navigáció a helyes információt jeleníti meg a kiválasztott elemhez.</span><span class="sxs-lookup"><span data-stu-id="3c08b-116">With this change, navigation to the details of the individual work items in the list will display the correct information for the item selected.</span></span> <span data-ttu-id="3c08b-117">A probléma csak speciális biztonsági beállítások esetén fordult elő.</span><span class="sxs-lookup"><span data-stu-id="3c08b-117">This issue only occurred with advanced security options.</span></span>


## <a name="known-issue"></a><span data-ttu-id="3c08b-118">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="3c08b-118">Known issue</span></span>

- <span data-ttu-id="3c08b-119">**Probléma**:Egy új csatolmány hozzáadásakor egy dolgozóhoz az **Új** és **Szerkesztés** gombok szürkén jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="3c08b-119">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="3c08b-120">**Megoldás:** A melléklet lap megnyitása, előtt ellenőrizze, hogy az adatterületek a **Dolgozó** lapon le vannak-e zárva.</span><span class="sxs-lookup"><span data-stu-id="3c08b-120">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="3c08b-121">Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="3c08b-121">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="3c08b-122">(Ezt a problémát kijavítjuk a következő platformfrissítéssel.)</span><span class="sxs-lookup"><span data-stu-id="3c08b-122">(This issue will be fixed in the next platform update.)</span></span>

