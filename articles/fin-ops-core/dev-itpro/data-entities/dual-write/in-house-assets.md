---
title: Házon belüli eszközök szervizeléshez
description: Ez a témakör azt mutatja be, hogyan használható a Microsoft Dynamics 365 Field Service szolgáltatás a vevői eszközök és a belső eszközök szervizelésére.
author: RamaKrishnamoorthy
manager: AnnBe
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
ms.openlocfilehash: d4d681b2362c90b69007ea44c01c886f96cc1db1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568078"
---
# <a name="in-house-assets-for-servicing"></a>Házon belüli eszközök szervizelése

[!include [banner](../../includes/banner.md)]



A Microsoft Dynamics 365 Field Service a vevői eszközök szervizelésére szolgál. A Dynamics 365 Supply Chain Management tárgyieszköz kezelője belső eszközök karbantartása céljából van kialakítva. Ennek a két alkalmazásnak az integrációja lehetővé teszi a Field Service szolgáltatás használatát a vevői tárgyi eszközök és a belső tárgyi eszközök szervizelésére. A tárgyi eszközöket a funkcionális hely vagy hierarchia alapján is osztályozhatja, és részletes szinten nyomon követheti a szervizelést.

További információ:[A Dynamics 365 Field Service és a Supply Chain Management integrációja](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).

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