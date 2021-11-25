---
title: Vevői hűségkártyák és hűségpontok
description: Ez a témakör a vevői hűségkártyákkal kapcsolatos adatok integrációját írja le kettős írásban.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 919ce0d57fb306b39cdcdd8655ac9f0b9e26847e
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781664"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Vevői hűségkártyák és hűségpontok

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A vállalatok osztályozzák vevőikert, és kifinomult szolgáltatásokat nyújtanak vevők vásárlási és költési szokásai alapján. Például a Dynamics 365 Commerce rendelkezik a infrastruktúrával és a funkciókkal, amelyek segítik a vevői hűségprogramok, jutalompontok, a hűség alapú árazás és jutalomalapú vásárlási élményeket. Amikor a Commerce rendszerbeli vevői hűségprogramok és jutalom pontok adatait a Dataverse ügyfélkapcsolati alkalmazásokkal szinkronizálja, az ügyfélkapcsolati alkalmazások használni tudják ezeket az adatokat. Például a Dynamics 365 Customer Service felhasználói az adatok segítségével ugyanolyan kifinomult szolgáltatásokat nyújthatnak az ügyfélszolgálaton keresztül.

## <a name="templates"></a>Sablonok

Finance and Operations alkalmazások | Customer Engagement alkalmazások     | Leírás
|-----------------------------|-----------------------------------|-------------|
[Hűségkártya](mapping-reference.md#149) | msdyn_loyaltycards | Ez a sablon szinkronizálja a vevői hűségkártyák adatait. |
[Hűségszintek](mapping-reference.md#226) | msdyn_loyaltylevels | Ez a sablon szinkronizálja a vevői jutalompontok adatait. |
[Hűségpontok](mapping-reference.md#150) | msdyn_loyaltyrewardpoints | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
