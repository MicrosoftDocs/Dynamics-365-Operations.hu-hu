---
title: Házon belüli eszközök szervizelése
description: Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Field Service lehet a vevői és a saját eszközök szolgáltatást is használni.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: c946af11737a77c4dadd824893e6cc1e4c77b587
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858622"
---
# <a name="in-house-assets-for-servicing"></a>Házon belüli eszközök szervizelése

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Field Service a vevői eszközök szervizelésére szolgál. A Dynamics 365 Supply Chain Management tárgyieszköz kezelője belső eszközök karbantartása céljából van kialakítva. Ennek a két alkalmazásnak az integrációja lehetővé teszi a Field Service szolgáltatás használatát a vevői tárgyi eszközök és a belső tárgyi eszközök szervizelésére. A tárgyi eszközöket a funkcionális hely vagy hierarchia alapján is osztályozhatja, és részletes szinten nyomon követheti a szervizelést.

További információ:[A Dynamics 365 Field Service és a Supply Chain Management integrációja](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Sablonok

A saját tárgyi eszközök tartalmazza azokat a központi táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

| Finance and Operations alkalmazások | Customer Engagement alkalmazások | Leírás |
|-----------------------------|-----------------------------------|-------------|
[Tárgyieszközkezelés eszközéletciklus modelljei](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[Tárgyieszközkezelés eszközéletciklus állapotai](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[Tárgyieszköz-kezelő eszköztípusok](mapping-reference.md#124) | msdyn_customerassetcategories | |
[Tárgyieszköz-kezelő eszközök](mapping-reference.md#125) | msdyn_customerassets | |
[Eszközkezelés munkavégési helyszín életciklusmodellek](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[Eszközkezelés munkavégési helyszín életciklusállapotok](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[Tárgyieszköz-kezelés munkavégzési helyszíntípusok](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[Tárgyieszköz-kezelés munkavégzési helyszínek](mapping-reference.md#136) | msdyn_functionallocations | |
[Tárgyieszközök gyártói](mapping-reference.md#153) | msdyn_manufacturers | |
[Tárgyieszköz-kezelési modellek](mapping-reference.md#154) | msdyn_models | |
[Tárgyeszköz-kezelés garancia](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
