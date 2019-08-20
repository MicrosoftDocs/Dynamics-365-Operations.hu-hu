---
title: Munkavégzési helyszínek és eszközök
description: Ez a cikk az Eszközkezelés munkavégzési helyszíneit és eszközeit ismerteti. Az Eszközkezelés az eszközök és a karbantartási feladatok Microsoft Dynamics 365 for Finance and Operations rendszerben történő kezelésére szolgáló speciális modul.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 351e27dfbbd5227a9642f14a48afe194c447a0f3
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783334"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="ad022-104">Munkavégzési helyszínek és eszközök</span><span class="sxs-lookup"><span data-stu-id="ad022-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="ad022-105">Ez a cikk az Eszközkezelés munkavégzési helyszíneit és eszközeit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="ad022-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="ad022-106">Az Eszközkezelés az eszközök és a karbantartási feladatok Microsoft Dynamics 365 for Finance and Operations rendszerben történő kezelésére szolgáló speciális modul.</span><span class="sxs-lookup"><span data-stu-id="ad022-106">Asset Management is an advanced module for managing assets and maintenance jobs in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="overview"></a><span data-ttu-id="ad022-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="ad022-107">Overview</span></span>

<span data-ttu-id="ad022-108">Az Eszközkezelés a Finance and Operations számos moduljával zökkenőmentesen együttműködik.</span><span class="sxs-lookup"><span data-stu-id="ad022-108">Asset Management is integrated seamlessly with several modules in Finance and Operations.</span></span> <span data-ttu-id="ad022-109">A következő ábra a más modulokkal való kapcsolatot mutatja be.</span><span class="sxs-lookup"><span data-stu-id="ad022-109">The following illustration shows the interfaces with other modules.</span></span>

![1. ábra](media/01-overview-image.png)

<span data-ttu-id="ad022-111">Az Eszközkezeléssel hatékonyan kezelhető és hajtható végre a cég különféle típusú felszerelésének kezelésére és szervizelésére szolgáló minden feladat.</span><span class="sxs-lookup"><span data-stu-id="ad022-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="ad022-112">Felszerelés lehet minden gép, gyártóeszköz vagy jármű.</span><span class="sxs-lookup"><span data-stu-id="ad022-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="ad022-113">Az Eszközkezelés több iparág megoldásait is támogatja.</span><span class="sxs-lookup"><span data-stu-id="ad022-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="ad022-114">A következő képen az Eszközkezelés fő funkcióinak az áttekintése látható.</span><span class="sxs-lookup"><span data-stu-id="ad022-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![2. ábra](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="ad022-116">Munkavégzési helyszínek és eszközök</span><span class="sxs-lookup"><span data-stu-id="ad022-116">Functional locations and assets</span></span>

<span data-ttu-id="ad022-117">A munkavégzési helyszínek a helyen lévő eszközök kezelésére szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="ad022-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="ad022-118">A kezelésbe az eszközök munkavégzési helyszíneken felmerülő költségek nyomon követése is beletartozik.</span><span class="sxs-lookup"><span data-stu-id="ad022-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="ad022-119">A munkavégzési helyszínek hierarchikusan tagoltak, és a helyszíneknek mellékhelyszínei lehetnek.</span><span class="sxs-lookup"><span data-stu-id="ad022-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="ad022-120">A munkavégzési helyszínek szerkezete statikus.</span><span class="sxs-lookup"><span data-stu-id="ad022-120">The structure of functional locations is static.</span></span> <span data-ttu-id="ad022-121">Más szavakkal a helyszínek helye nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="ad022-121">In other words, locations can't change place.</span></span> <span data-ttu-id="ad022-122">Az eszközök telepíthetők munkavégzési helyszíneken, és szükség esetén további munkavégzési helyszíneken.</span><span class="sxs-lookup"><span data-stu-id="ad022-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="ad022-123">Az eszközök költsége az eszköz helyét követi.</span><span class="sxs-lookup"><span data-stu-id="ad022-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="ad022-124">Más szóval, ha új munkavégzési helyszínen telepít egy eszközt, az eszköz automatikusan az új munkavégzési helyszínnel összekapcsolt pénzügyi dimenziókat használja.</span><span class="sxs-lookup"><span data-stu-id="ad022-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="ad022-125">Így az eszköz költségei mindig össze vannak kapcsolva azzal a munkavégzési helyszínnel, amelyen az eszköz pillanatnyilag telepítve van.</span><span class="sxs-lookup"><span data-stu-id="ad022-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="ad022-126">A pénzügyi dimenziók ilyen automatikus kezelésével garantálható a költségek teljes nyomon követése, amikor a cég projektellenőrzést végez a munkavégzési helyszíneken, illetve jelentést készít róluk.</span><span class="sxs-lookup"><span data-stu-id="ad022-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="ad022-127">A munkavégzési helyszínek hierarchiájának kialakítása attól függ, hogy a cég milyen követelményeket támaszt a belső vagy az ügyfeleknek szolgáltatott berendezésekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="ad022-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="ad022-128">A következő képen egy földrajzi helyeken alapuló munkavégzési helyszínre látható példa.</span><span class="sxs-lookup"><span data-stu-id="ad022-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![3. ábra](media/03-overview-image.png)

<span data-ttu-id="ad022-130">A következő képen egy ügyfeleken alapuló munkavégzési helyszínre látható példa.</span><span class="sxs-lookup"><span data-stu-id="ad022-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![4. ábra](media/04-overview-image.png)
