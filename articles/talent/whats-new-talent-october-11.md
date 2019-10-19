---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. október 15.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/15/2018
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
ms.search.validFrom: 2018-10-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 642df0dd413f4ab5a181a18c79f13aa334f9c158
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010153"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-october-15-2018"></a><span data-ttu-id="bea37-103">Új vagy módosult elemek a Dynamics 365 Talent: Core HR szolgáltatásban (2018. október 15.)</span><span class="sxs-lookup"><span data-stu-id="bea37-103">What's new or changed in Dynamics 365 Talent: Core HR (October 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bea37-104">**Build 8.1.1056**</span><span class="sxs-lookup"><span data-stu-id="bea37-104">**Build 8.1.1056**</span></span>

<span data-ttu-id="bea37-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="bea37-105">This topic describes features that are either new or changed in Core HR.</span></span>


## <a name="changes"></a><span data-ttu-id="bea37-106">Változások</span><span class="sxs-lookup"><span data-stu-id="bea37-106">Changes</span></span>
<span data-ttu-id="bea37-107">Az egyéb javításokon kívül ebben a verzióban a következő frissítések történtek:</span><span class="sxs-lookup"><span data-stu-id="bea37-107">In addition to miscellanous fixes, the following updates have been made in this release:</span></span>
- <span data-ttu-id="bea37-108">Az Utolsó ledolgozott nap most beállításara kerül egy munkaviszony megszűnési dátumának megadásakor.</span><span class="sxs-lookup"><span data-stu-id="bea37-108">Last Day worked now set when hiring or setting an employment end date.</span></span>
- <span data-ttu-id="bea37-109">Egyesült Államokbeli megfelelési hivatkozások eltávolítása ha a vállalat nem az Egyesült Államokban van (KTB ADA és I9).</span><span class="sxs-lookup"><span data-stu-id="bea37-109">US compliance references removed when in non US companies (ACA, ADA, and I9).</span></span>
- <span data-ttu-id="bea37-110">Az érvénytelen dátumok (1/1/1900) analitika lapokon el vannak rejtve.</span><span class="sxs-lookup"><span data-stu-id="bea37-110">Invalid dates (1/1/1900) are now hidden on analytics pages.</span></span>

## <a name="known-issue"></a><span data-ttu-id="bea37-111">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="bea37-111">Known issue</span></span>

<span data-ttu-id="bea37-112">**Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői.</span><span class="sxs-lookup"><span data-stu-id="bea37-112">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="bea37-113">Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="bea37-113">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="bea37-114">(Ezt a problémát kijavítjuk a következő platformfrissítéssel.)</span><span class="sxs-lookup"><span data-stu-id="bea37-114">(This issue will be fixed in the next platform update.)</span></span>
