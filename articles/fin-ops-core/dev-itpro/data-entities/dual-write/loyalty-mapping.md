---
title: Vevői hűségkártyák és hűségpontok
description: Ez a témakör a vevői hűségkártyákkal kapcsolatos adatok integrációját írja le kettős írásban.
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
ms.openlocfilehash: 28872e9510394cf3d5cee151798d4130b8b6fe27
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683498"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Vevői hűségkártyák és hűségpontok

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A vállalatok osztályozzák vevőikert, és kifinomult szolgáltatásokat nyújtanak vevők vásárlási és költési szokásai alapján. Például a Dynamics 365 Commerce rendelkezik a infrastruktúrával és a funkciókkal, amelyek segítik a vevői hűségprogramok, jutalompontok, a hűség alapú árazás és jutalomalapú vásárlási élményeket. Amikor a Commerce rendszerbeli vevői hűségprogramok és jutalom pontok adatait a Dataverse ügyfélkapcsolati alkalmazásokkal szinkronizálja, az ügyfélkapcsolati alkalmazások használni tudják ezeket az adatokat. Például a Dynamics 365 Customer Service felhasználói az adatok segítségével ugyanolyan kifinomult szolgáltatásokat nyújthatnak az ügyfélszolgálaton keresztül.

## <a name="templates"></a>Sablonok

| Finance and Operations-alkalmazásoknak | Modellvezérelt alkalmazások a Dynamics 365-ben | Leírás |
|-----------------------------|-----------------------------------|-------------|
| Hűségkártya                | msdyn\_loyaltycards               | Ez a sablon szinkronizálja a vevői hűségkártyák adatait. |
| Hűségpontok       | msdyn\_loyaltyrewardpoints        | Ez a sablon szinkronizálja a vevői jutalompontok adatait. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
