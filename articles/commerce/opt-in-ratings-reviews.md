---
title: A minősítések és ellenőrzések használatának kiválasztása
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697980"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="1713d-103">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="1713d-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1713d-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.</span><span class="sxs-lookup"><span data-stu-id="1713d-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="1713d-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="1713d-105">Overview</span></span>

<span data-ttu-id="1713d-106">Az értékelések és a vélemények megoldása egy többcsatornás megoldás, amelyet a Dynamics 365 Commerce megoldásban a Microsoft Dynamics Lifecycle Services (LCS) segítségével tehet elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="1713d-106">The ratings and reviews solution is an omnichannel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="1713d-107">Az LCS egy olyan felügyeleti portál, amelyet a kiskereskedők a környezeteik kezelésére használhatnak a telepítéstől egészen a megszüntetésig.</span><span class="sxs-lookup"><span data-stu-id="1713d-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="1713d-108">Ha azt szeretné, használni az értékelések és vélemények megoldást használhassa a kereskedelmi webhelyén, először el kell fogadnia azt.</span><span class="sxs-lookup"><span data-stu-id="1713d-108">If you want to use the ratings and reviews solution on your Commerce website, you must first opt in.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="1713d-109">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="1713d-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="1713d-110">A következő lépések végrehajtásával választhatja ki azt, hogy használni szeretné az értékelések és vélemények funkciót.</span><span class="sxs-lookup"><span data-stu-id="1713d-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="1713d-111">Kövesse az [Új e-commerce webhely telepítése](deploy-ecommerce-site.md) szakasz lépéseit.</span><span class="sxs-lookup"><span data-stu-id="1713d-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="1713d-112">Amikor még az LCS-ben van nyissa meg a **Retail-telepítés beállítása \> Egyéb beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1713d-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="1713d-113">Állítsa be az **Értékelések és vélemények szolgáltatás engedélyezése** értékét **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="1713d-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="1713d-114">Az **AAD biztonsági csoport értékelések és vélemények moderátora (biztonsági csoport-objektumazonosító)** mezőbe írja be annak a Microsoft Azure Active Directory (Azure AD) biztonsági csoportnak az azonosítóját, amely tartalmazza az értékelések és vélemények moderátorait.</span><span class="sxs-lookup"><span data-stu-id="1713d-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![A minősítések és ellenőrzések használatának kiválasztása](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="1713d-116">Az e-commerce inicializálási folyamat végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="1713d-116">Complete the e-Commerce initialization process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1713d-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1713d-117">Additional resources</span></span>

[<span data-ttu-id="1713d-118">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="1713d-118">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="1713d-119">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="1713d-119">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="1713d-120">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1713d-120">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="1713d-121">A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="1713d-121">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
