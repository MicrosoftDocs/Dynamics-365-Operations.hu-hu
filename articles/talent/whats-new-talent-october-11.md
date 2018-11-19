---
title: "Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 15.)"
description: "Ez a témakör a Microsoft Dynamics 365 for Talent Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le."
author: Darinkramer
manager: AnnBe
ms.date: 10/15/2018
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
ms.search.validFrom: 2018-10-11
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 2eb46f436305a4c81ea99553e4dc07288ee74008
ms.openlocfilehash: 1d48bc4bad795611ce322b5f09b78886a50c415c
ms.contentlocale: hu-hu
ms.lasthandoff: 10/22/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-15-2018"></a><span data-ttu-id="2864a-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 15.)</span><span class="sxs-lookup"><span data-stu-id="2864a-103">What's new or changed in Dynamics 365 for Talent Core HR (October 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2864a-104">**Build 8.1.1056**</span><span class="sxs-lookup"><span data-stu-id="2864a-104">**Build 8.1.1056**</span></span>

<span data-ttu-id="2864a-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="2864a-105">This topic describes features that are either new or changed in Core HR.</span></span>


## <a name="changes"></a><span data-ttu-id="2864a-106">Változások</span><span class="sxs-lookup"><span data-stu-id="2864a-106">Changes</span></span>
<span data-ttu-id="2864a-107">Az egyéb javításokon kívül ebben a verzióban a következő frissítések történtek:</span><span class="sxs-lookup"><span data-stu-id="2864a-107">In addition to miscellanous fixes, the following updates have been made in this release:</span></span>
- <span data-ttu-id="2864a-108">Az Utolsó ledolgozott nap most beállításara kerül egy munkaviszony megszűnési dátumának megadásakor.</span><span class="sxs-lookup"><span data-stu-id="2864a-108">Last Day worked now set when hiring or setting an employment end date.</span></span>
- <span data-ttu-id="2864a-109">Egyesült Államokbeli megfelelési hivatkozások eltávolítása ha a vállalat nem az Egyesült Államokban van (KTB ADA és I9).</span><span class="sxs-lookup"><span data-stu-id="2864a-109">US compliance references removed when in non US companies (ACA, ADA, and I9).</span></span>
- <span data-ttu-id="2864a-110">Az érvénytelen dátumok (1/1/1900) analitika lapokon el vannak rejtve.</span><span class="sxs-lookup"><span data-stu-id="2864a-110">Invalid dates (1/1/1900) are now hidden on analytics pages.</span></span>

## <a name="known-issue"></a><span data-ttu-id="2864a-111">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="2864a-111">Known issue</span></span>

<span data-ttu-id="2864a-112">**Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői.</span><span class="sxs-lookup"><span data-stu-id="2864a-112">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="2864a-113">Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="2864a-113">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="2864a-114">(Ezt a problémát kijavítjuk a következő platformfrissítéssel.)</span><span class="sxs-lookup"><span data-stu-id="2864a-114">(This issue will be fixed in the next platform update.)</span></span>

