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
# <a name="customer-loyalty-cards-and-reward-points"></a>Vevői hűségkártyák és hűségpontok

[!include [banner](../../includes/banner.md)]



A vállalatok osztályozzák vevőikert, és kifinomult szolgáltatásokat nyújtanak vevők vásárlási és költési szokásai alapján. A Microsoft Dynamics 365 programcsomagban a Dynamics 365 Commerce rendelkezik a infrastruktúrával és a funkciókkal, amelyek segítik a vevői hűségprogramok, jutalompontok, a hűség alapú árazás és jutalomalapú vásárlási élményeket. Amikor a Commerce rendszerbeli vevői hűségprogramok és jutalom pontok adatait a Common Data Service szolgáltatással szinkronizálja, a Dynamics 365 modellvezérelt alkalmazásai használni tudják ezeket az adatokat. Például a Dynamics 365 Customer Service felhasználói az adatok segítségével ugyanolyan kifinomult szolgáltatásokat nyújthatnak az ügyfélszolgálaton keresztül.

## <a name="templates"></a>Sablonok

| Finance and Operations-alkalmazásoknak | Modellvezérelt alkalmazások a Dynamics 365-ben | Leírás |
|-----------------------------|-----------------------------------|-------------|
| Hűségkártya                | msdyn\_loyaltycards               | Ez a sablon szinkronizálja a vevői hűségkártyák adatait. |
| Hűségpontok       | msdyn\_loyaltyrewardpoints        | Ez a sablon szinkronizálja a vevői jutalompontok adatait. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
