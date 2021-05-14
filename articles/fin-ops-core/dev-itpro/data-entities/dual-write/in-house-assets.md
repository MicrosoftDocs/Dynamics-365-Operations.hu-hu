---
title: Házon belüli eszközök szervizelése
description: Ez a témakör azt ismerteti, hogyan használhatja a Microsoft Dynamics 365 Field Service szolgáltatást mind a vevői, mind a saját eszközökben.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
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
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: ebda6b5679ec601513fb6d046725b396e69fe0f3
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941414"
---
# <a name="in-house-assets-for-servicing"></a>Házon belüli eszközök szervizelése

[!include [banner](../../includes/banner.md)]



A Microsoft Dynamics 365 Field Service a vevői eszközök szervizelésére szolgál. A Dynamics 365 Supply Chain Management tárgyieszköz kezelője belső eszközök karbantartása céljából van kialakítva. Ennek a két alkalmazásnak az integrációja lehetővé teszi a Field Service szolgáltatás használatát a vevői tárgyi eszközök és a belső tárgyi eszközök szervizelésére. A tárgyi eszközöket a funkcionális hely vagy hierarchia alapján is osztályozhatja, és részletes szinten nyomon követheti a szervizelést.

További információ:[A Dynamics 365 Field Service és a Supply Chain Management integrációja](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Sablonok

A saját tárgyi eszközök tartalmazza azokat a központi táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

| Finance and Operations-alkalmazásoknak | Modellvezérelt alkalmazások a Dynamics 365-ben | Leírás |
|-----------------------------|-----------------------------------|-------------|
| Tárgyieszközkezelés eszközéletciklus modelljei | msdyn\_assetlifecyclemodels | |
| Tárgyieszközkezelés eszközéletciklus állapotai | msdyn\_assetlifecyclestates | |
| Tárgyieszköz-kezelő eszközök | msdyn\_customerassets | |
| Tárgyieszköz-kezelő eszköztípusok | msdyn\_customerassetcategories | |
| Eszközkezelés munkavégési helyszín életciklusmodellek | msdyn\_functionallocationlifecyclemodels | |
| Eszközkezelés munkavégési helyszín életciklusállapotok | msdyn\_functionallocationlifecyclestates | |
| Tárgyieszköz-kezelés munkavégzési helyszínek | msdyn\_functionallocations | |
| Tárgyieszköz-kezelés munkavégzési helyszíntípusok | msdyn\_functionallocationtypes | |
| Tárgyieszközök gyártói | msdyn\_manufacturers | |
| Tárgyieszköz-kezelési modellek | msdyn\_models | |
| Tárgyeszköz-kezelés garancia | msdyn\_warranties | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]