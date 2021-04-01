---
title: A minősítések és ellenőrzések használatának kiválasztása
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6c54a8fa01badb6a383c41dc979e71d82a25ef97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251235"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="2d0f3-103">A minősítések és értékelések használatának bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="2d0f3-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2d0f3-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="2d0f3-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="2d0f3-105">Overview</span></span>

<span data-ttu-id="2d0f3-106">Az értékelések és a vélemények megoldása egy omnicsatornás megoldás, amelyet a Dynamics 365 Commerce megoldásban a Microsoft Dynamics Lifecycle Services (LCS) segítségével tehet elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-106">The ratings and reviews solution is an omni-channel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="2d0f3-107">Az LCS egy olyan felügyeleti portál, amelyet a kiskereskedők a környezeteik kezelésére használhatnak a telepítéstől egészen a megszüntetésig.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="2d0f3-108">Ha azt szeretné, hogy a minősítési és értékelési megoldást használhassa a Commerce webhelyén, akkor az e-Commerce webhely telepítését követően fel kell iratkoznia a minősítésekre és ellenőrzésekre a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-108">If you want to use the ratings and reviews solution on your Commerce website, you must opt in for ratings and reviews during deployment of your e-Commerce site on Dynamics 365 Commerce.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="2d0f3-109">A minősítések és ellenőrzések használatának bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="2d0f3-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="2d0f3-110">A következő lépések végrehajtásával választhatja ki azt, hogy használni szeretné az értékelések és vélemények funkciót.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="2d0f3-111">Kövesse az [Új e-commerce webhely telepítése](deploy-ecommerce-site.md) szakasz lépéseit.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="2d0f3-112">Amikor még az LCS-ben van nyissa meg a **Retail-telepítés beállítása \> Egyéb beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="2d0f3-113">Állítsa be az **Értékelések és vélemények szolgáltatás engedélyezése** értékét **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="2d0f3-114">Az **AAD biztonsági csoport értékelések és vélemények moderátora (biztonsági csoport-objektumazonosító)** mezőbe írja be annak a Microsoft Azure Active Directory (Azure AD) biztonsági csoportnak az azonosítóját, amely tartalmazza az értékelések és vélemények moderátorait.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![A minősítések és ellenőrzések használatának bekapcsolása](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="2d0f3-116">Az e-commerce inicializálási folyamat végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-116">Complete the e-Commerce initialization process.</span></span>

> [!NOTE] 
> <span data-ttu-id="2d0f3-117">Ha olyan meglévő Dynamics 365 Commerce ügyfél, aki már telepített e-Commerce webhelyet anélkül, hogy feliratkozott volna a minősítések és értékelések funkcióra, és most használni kívánja a minősítések és értékelések funkciót a Dynamics 365 Commerce csomagból, akkor küldjön egy szolgáltatáskérelmet.</span><span class="sxs-lookup"><span data-stu-id="2d0f3-117">If you are an existing Dynamics 365 Commerce customer who has already deployed an e-Commerce site without having opted in for ratings and reviews and now want to use ratings and reviews from the Dynamics 365 Commerce package, please submit a service request.</span></span> <span data-ttu-id="2d0f3-118">A szolgáltatáskérelem elküldésével kapcsolatos további tudnivalókat lásd: [Szolgáltatáskérelem küldésének folyamata](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="2d0f3-118">For information about how to submit a service request, see [Submit service requests process](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="2d0f3-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2d0f3-119">Additional resources</span></span>

[<span data-ttu-id="2d0f3-120">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="2d0f3-120">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="2d0f3-121">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="2d0f3-121">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="2d0f3-122">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="2d0f3-122">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="2d0f3-123">A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2d0f3-123">Sync product ratings in Dynamics 365 Commerce</span></span>](sync-product-ratings.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]