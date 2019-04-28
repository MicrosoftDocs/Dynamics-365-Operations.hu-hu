---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. november 27.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 11/27/2018
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
ms.search.validFrom: 2018-11-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 81ea0e4f4878d1967234c597504071ce464a22c5
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "857799"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-27-2018"></a><span data-ttu-id="bde7f-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. november 27.)</span><span class="sxs-lookup"><span data-stu-id="bde7f-103">What's new or changed in Dynamics 365 for Talent Core HR (November 27, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bde7f-104">**Build 8.1.2064**</span><span class="sxs-lookup"><span data-stu-id="bde7f-104">**Build 8.1.2064**</span></span>

<span data-ttu-id="bde7f-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="bde7f-105">This topic describes features that are either new or changed in Core HR.</span></span>


## <a name="changes"></a><span data-ttu-id="bde7f-106">Változások</span><span class="sxs-lookup"><span data-stu-id="bde7f-106">Changes</span></span>

### <a name="unable-to-create-a-note-in-case-management"></a><span data-ttu-id="bde7f-107">Nem sikerült megjegyzés létrehozása a Case Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="bde7f-107">Unable to create a note in Case Management</span></span>

<span data-ttu-id="bde7f-108">Módosítás történt egy problémával kapcsolatban, amely akkor merül fel, amikor az Esetkezelés esetnaplójában megjegyzést hoznak létre vagy szerkesztenek.</span><span class="sxs-lookup"><span data-stu-id="bde7f-108">A change has been made for an issue when attempting to edit or create a note in the case log of Case Management.</span></span>

### <a name="misspelled-word-on-the-analytics-tab-in-the-compensation-workspace"></a><span data-ttu-id="bde7f-109">Elírt szó a kompenzációs munkaterület Elemzések lapján</span><span class="sxs-lookup"><span data-stu-id="bde7f-109">Misspelled word on the analytics tab in the compensation workspace</span></span> 

<span data-ttu-id="bde7f-110">Módosítás történt a kompenzációs munkaterület kompenzációs elemzés diagramján, a helytelenül írt 'Ethnic Origin' szó helyesírását javítottuk.</span><span class="sxs-lookup"><span data-stu-id="bde7f-110">A change has been made to correct the spelling of 'Ethnic Origin' in the compensation analytics chart in the compensation workspace.</span></span>

### <a name="employee-self-service-workspace-not-displaying-when-a-user-isnt-assigned-to-a-worker"></a><span data-ttu-id="bde7f-111">Az alkalmazott önkiszolgáló munkaterülete nem jelenik meg, amikor a felhasználó nincs hozzárendelve egy dolgozóhoz</span><span class="sxs-lookup"><span data-stu-id="bde7f-111">Employee self-service workspace not displaying when a user isn't assigned to a worker</span></span> 

<span data-ttu-id="bde7f-112">Módosítás történt a következő problémával kapcsolatban: amikor az **Alkalmazotti önkiszolgáló rendszer** munkaterületet kiválasztják, mint az indításkor megjelenő jezdőoldal egy olyan felhasználó esetén, aki nincs hozzárendelve egy dolgozóhoz.</span><span class="sxs-lookup"><span data-stu-id="bde7f-112">A change has been made when the **Employee self-service** workspace is selected as the initial page on startup for a user who is not assigned to a worker.</span></span> <span data-ttu-id="bde7f-113">Ebben az esetben az alapértelmezett irányítópult fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="bde7f-113">In this situation, the default dashboard will be displayed.</span></span>

### <a name="leave-and-absence-error-object-reference-not-set-to-an-instance-of-an-object"></a><span data-ttu-id="bde7f-114">Szabadság és távollét hibája: Az objektumhivatkozás nincs beállítva egy objektum példányához</span><span class="sxs-lookup"><span data-stu-id="bde7f-114">Leave and Absence error: Object reference not set to an instance of an object</span></span>

<span data-ttu-id="bde7f-115">Módosítások történtek a Szabadság és távollét funkcióban, a szabadság és távollét rekordok **Hozzám rendelt munkatételek** menüpontban való jóváhagyása után felmerülő hibát javították.</span><span class="sxs-lookup"><span data-stu-id="bde7f-115">Changes have been made to Leave and Absence to correct this error after approving leave and absence records in the **Work items assigned to me** list.</span></span>

### <a name="unable-to-recall-an-image-workflow"></a><span data-ttu-id="bde7f-116">Nem lehet egy képmunkafolyamatot visszahívni</span><span class="sxs-lookup"><span data-stu-id="bde7f-116">Unable to recall an image workflow</span></span>

<span data-ttu-id="bde7f-117">Egy képmunkafolyamat visszahívása után a munkafolyamat „visszavonva” beállítást kap, és a létező kérést törölni lehet az alkalmazotti önkiszolgáló rendszer munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="bde7f-117">After recalling an image workflow, the workflow will be set to "cancelled" and the existing request can be deleted in the employee self-service workspace.</span></span>

### <a name="rehired-employees-or-contractors-show-up-multiple-times-after-termination"></a><span data-ttu-id="bde7f-118">Újra felvett alkalmazottak vagy alvállalkozók többször jelennek meg a munkaviszony megszűnése után</span><span class="sxs-lookup"><span data-stu-id="bde7f-118">Rehired employees or contractors show up multiple times after termination</span></span> 

<span data-ttu-id="bde7f-119">Ezzel a frissítéssel azok az alkalmazottak, akiknek megszűnt a munkaviszonyuk, majd újra felvették őket, csak egyszer jelennek majd meg a kilépettek listájában.</span><span class="sxs-lookup"><span data-stu-id="bde7f-119">With this update, terminated employees that are rehired will only display one time in the exited list.</span></span> 

## <a name="known-issue"></a><span data-ttu-id="bde7f-120">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="bde7f-120">Known issue</span></span>

- <span data-ttu-id="bde7f-121">**Probléma**:Egy új csatolmány hozzáadásakor egy dolgozóhoz az **Új** és **Szerkesztés** gombok szürkén jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="bde7f-121">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="bde7f-122">**Megoldás:** A melléklet lap megnyitása, előtt ellenőrizze, hogy az adatterületek a **Dolgozó** lapon le vannak-e zárva.</span><span class="sxs-lookup"><span data-stu-id="bde7f-122">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="bde7f-123">Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="bde7f-123">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="bde7f-124">(Ezt a problémát kijavítjuk a következő platformfrissítéssel.)</span><span class="sxs-lookup"><span data-stu-id="bde7f-124">(This issue will be fixed in the next platform update.)</span></span>
