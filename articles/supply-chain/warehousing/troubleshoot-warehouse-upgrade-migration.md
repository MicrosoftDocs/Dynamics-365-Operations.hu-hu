---
title: Speciális raktárkezelésre való frissítés és áttelepítés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben frissíti és áttelepíti a speciális raktárkezelést.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f5bfee31ce27e919086f978fb3ff88ca61a65eba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208087"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="d042c-103">Speciális raktárkezelésre való frissítés és áttelepítés – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="d042c-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d042c-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben frissíti és áttelepíti a speciális raktárkezelést.</span><span class="sxs-lookup"><span data-stu-id="d042c-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="d042c-105">A következő hibaüzenet jelenik meg: „java.security.cert.certPathValidatorException: A tanúsítvány elérési útjának megbízhatósági horgonyzás nem található.”</span><span class="sxs-lookup"><span data-stu-id="d042c-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="d042c-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="d042c-106">Issue description</span></span>

<span data-ttu-id="d042c-107">Ez a hibaüzenet a raktári alkalmazásban jelenik meg, mert az önaláírt tanúsítványok nem Android megbízhatóak a helyszíni környezetekben 8+ felett.</span><span class="sxs-lookup"><span data-stu-id="d042c-107">You receive this error message in the warehouse app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d042c-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="d042c-108">Issue resolution</span></span>

<span data-ttu-id="d042c-109">Külső (nyilvános) tanúsító hatóság (CA) használata.</span><span class="sxs-lookup"><span data-stu-id="d042c-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="d042c-110">A probléma javítása a raktári alkalmazás 1.9.0.0 verziójában érhető el.</span><span class="sxs-lookup"><span data-stu-id="d042c-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="d042c-111">A problémáról és a probléma megoldásáról a [Raktári alkalmazás kapcsolódási hibáinak hibaelhárítása](troubleshoot-warehouse-app-connection.md) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="d042c-111">For more information about this issue and how to fix it, see [Troubleshoot warehouse app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="d042c-112">Mi a jóváhagyott folyamat az alapraktározásról a speciális raktározásra való áttérésre?</span><span class="sxs-lookup"><span data-stu-id="d042c-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="d042c-113">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="d042c-113">Issue description</span></span>

<span data-ttu-id="d042c-114">Jelenleg készletkezelés alatt fut, és alapvető készletfunkciókat használ, és a mobileszközök, a hullámok és a munka előnyeinek kihasználása érdekében speciális raktározásra szeretne áthelyezni.</span><span class="sxs-lookup"><span data-stu-id="d042c-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="d042c-115">Azonban problémákat tapasztal, amikor megpróbálja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="d042c-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="d042c-116">Például nem módosíthatja a termékeket úgy, hogy azok tárolási dimenziókat (hely, raktár és hely) használjanak, mert a termékek tranzakcióval rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="d042c-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="d042c-117">Ezért meg kell tanulnia a jóváhagyott folyamat alapraktározásról a speciális raktározásra való áttérést.</span><span class="sxs-lookup"><span data-stu-id="d042c-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d042c-118">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="d042c-118">Issue resolution</span></span>

<span data-ttu-id="d042c-119">Az alapraktározásról a speciális raktározásra való áttérés folyamatáról a következő blogbejegyzésekben és dokumentációban olvashat bővebben:</span><span class="sxs-lookup"><span data-stu-id="d042c-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="d042c-120">Tegye elérhetővé a meglévő cikknek és raktárnak a raktárkezelő folyamatot</span><span class="sxs-lookup"><span data-stu-id="d042c-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="d042c-121">A WMS áttelepítése Microsoft Dynamics AX új R3 raktárra és szállítási funkcióra</span><span class="sxs-lookup"><span data-stu-id="d042c-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="d042c-122">WMSI/WMS2 cikk áttelepítése</span><span class="sxs-lookup"><span data-stu-id="d042c-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="d042c-123">Raktárkezelés frissítése a Microsoft Dynamics AX 2012-ről a Supply Chain Management szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="d042c-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]