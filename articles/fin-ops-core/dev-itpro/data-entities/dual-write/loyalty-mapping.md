---
title: Vevői hűségkártyák és hűségpontok
description: Ez a témakör a vevői hűségkártyákkal kapcsolatos adatok integrációját írja le a Finance and Operations alkalmazások és a Common Data Service között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998014"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="334b7-103">Vevői hűségkártyák és hűségpontok</span><span class="sxs-lookup"><span data-stu-id="334b7-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="334b7-104">A vállalatok osztályozzák vevőikert, és kifinomult szolgáltatásokat nyújtanak vevők vásárlási és költési szokásai alapján.</span><span class="sxs-lookup"><span data-stu-id="334b7-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="334b7-105">A Microsoft Dynamics 365 programcsomagban a Dynamics 365 Commerce rendelkezik a infrastruktúrával és a funkciókkal, amelyek segítik a vevői hűségprogramok, jutalompontok, a hűség alapú árazás és jutalomalapú vásárlási élményeket.</span><span class="sxs-lookup"><span data-stu-id="334b7-105">In the Microsoft Dynamics 365 suite of applications, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="334b7-106">Amikor a Commerce rendszerbeli vevői hűségprogramok és jutalom pontok adatait a Common Data Service szolgáltatással szinkronizálja, a Dynamics 365 modellvezérelt alkalmazásai használni tudják ezeket az adatokat.</span><span class="sxs-lookup"><span data-stu-id="334b7-106">When data about customer loyalty cards and reward points in Commerce is synced to Common Data service, model-driven apps in Dynamics 365 can use that data.</span></span> <span data-ttu-id="334b7-107">Például a Dynamics 365 Customer Service felhasználói az adatok segítségével ugyanolyan kifinomult szolgáltatásokat nyújthatnak az ügyfélszolgálaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="334b7-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="334b7-108">Sablonok</span><span class="sxs-lookup"><span data-stu-id="334b7-108">Templates</span></span>

| <span data-ttu-id="334b7-109">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="334b7-109">Finance and Operations apps</span></span> | <span data-ttu-id="334b7-110">Modellvezérelt alkalmazások a Dynamics 365-ben</span><span class="sxs-lookup"><span data-stu-id="334b7-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="334b7-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="334b7-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="334b7-112">Hűségkártya</span><span class="sxs-lookup"><span data-stu-id="334b7-112">Loyalty card</span></span>                | <span data-ttu-id="334b7-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="334b7-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="334b7-114">Ez a sablon szinkronizálja a vevői hűségkártyák adatait.</span><span class="sxs-lookup"><span data-stu-id="334b7-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="334b7-115">Hűségpontok</span><span class="sxs-lookup"><span data-stu-id="334b7-115">Loyalty reward points</span></span>       | <span data-ttu-id="334b7-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="334b7-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="334b7-117">Ez a sablon szinkronizálja a vevői jutalompontok adatait.</span><span class="sxs-lookup"><span data-stu-id="334b7-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
