---
title: Vevői hűségkártyák és hűségpontok
description: Ez a témakör a vevői hűségkártyákkal kapcsolatos adatok integrációját írja le kettős írásban.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 39e1d5b0a73b198b164e51a18222dbd985192070
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568028"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="7a662-103">Vevői hűségkártyák és hűségpontok</span><span class="sxs-lookup"><span data-stu-id="7a662-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="7a662-104">A vállalatok osztályozzák vevőikert, és kifinomult szolgáltatásokat nyújtanak vevők vásárlási és költési szokásai alapján.</span><span class="sxs-lookup"><span data-stu-id="7a662-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="7a662-105">Például a Dynamics 365 Commerce rendelkezik a infrastruktúrával és a funkciókkal, amelyek segítik a vevői hűségprogramok, jutalompontok, a hűség alapú árazás és jutalomalapú vásárlási élményeket.</span><span class="sxs-lookup"><span data-stu-id="7a662-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="7a662-106">Amikor a Commerce rendszerbeli vevői hűségprogramok és jutalom pontok adatait a Dataverse ügyfélkapcsolati alkalmazásokkal szinkronizálja, az ügyfélkapcsolati alkalmazások használni tudják ezeket az adatokat.</span><span class="sxs-lookup"><span data-stu-id="7a662-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="7a662-107">Például a Dynamics 365 Customer Service felhasználói az adatok segítségével ugyanolyan kifinomult szolgáltatásokat nyújthatnak az ügyfélszolgálaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="7a662-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="7a662-108">Sablonok</span><span class="sxs-lookup"><span data-stu-id="7a662-108">Templates</span></span>

| <span data-ttu-id="7a662-109">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="7a662-109">Finance and Operations apps</span></span> | <span data-ttu-id="7a662-110">Modellvezérelt alkalmazások a Dynamics 365-ben</span><span class="sxs-lookup"><span data-stu-id="7a662-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="7a662-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="7a662-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="7a662-112">Hűségkártya</span><span class="sxs-lookup"><span data-stu-id="7a662-112">Loyalty card</span></span>                | <span data-ttu-id="7a662-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="7a662-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="7a662-114">Ez a sablon szinkronizálja a vevői hűségkártyák adatait.</span><span class="sxs-lookup"><span data-stu-id="7a662-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="7a662-115">Hűségpontok</span><span class="sxs-lookup"><span data-stu-id="7a662-115">Loyalty reward points</span></span>       | <span data-ttu-id="7a662-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="7a662-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="7a662-117">Ez a sablon szinkronizálja a vevői jutalompontok adatait.</span><span class="sxs-lookup"><span data-stu-id="7a662-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]