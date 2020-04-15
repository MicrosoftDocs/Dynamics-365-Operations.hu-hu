---
title: Szervezeti hierarchia a Common Data Service szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations alkalmazás és a Common Data Service között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fc5db8d04a2860df0c917816e2910c6fbda941ff
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173154"
---
# <a name="organization-hierarchy-in-common-data-service"></a>Szervezeti hierarchia a Common Data Service szolgáltatásban

[!include [banner](../../includes/banner.md)]



Mivel a Dynamics 365 Finance egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik. A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.

Bár a Common Data Service nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel. A Common Data Service integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Common Data Service szolgáltatáshoz.

## <a name="data-flow"></a>Adatáramlás

Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Common Data Service alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával. Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Common Data Service szolgáltatásban is tájékoztatási és bővítési célból. A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Common Data Service szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Common Data Service között.

![Architektúra képe](media/dual-write-data-flow.png)

## <a name="templates"></a>Sablonok

A szervezeti hierarchiához tartozó entitásleképezések a Finance and Operations alkalmazások és a Common Data Service szolgáltatás közötti egyirányú adatáramlást szolgálják.

## <a name="templates"></a>Sablonok

A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat. A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott entitás-leképezések gyűjteményét.

Finance and Operations-alkalmazásoknak | Egyéb Dynamics 365 alkalmazások | Leírás
-----------------------|--------------------------------|---
Szervezeti hierarchiához kapcsolódó célok | msdyn_internalorganizationhierarchypurposes | Ez a sablon a Szervezeti hierarchia célja entitás egyirányú szinkronizálását teszi lehetővé.
Szervezeti hierarchia típusa | msdyn_internalorganizationhierarchytypes | Ez a sablon a Szervezeti hierarchia típusa entitás egyirányú szinkronizálását teszi lehetővé.
Szervezeti hierarchia – közzétett | msdyn_internalorganizationhierarchies | Ez a sablon a Szervezeti hierarchia közzétéve entitás egyirányú szinkronizálását teszi lehetővé.
Üzemi egység | msdyn_internalorganizations | 
Jogi személyek | msdyn_internalorganizations | 
Jogi személyek | cdm_companies | A jogi személy (vállalat) adatainak kétirányú szinkronizálását teszi lehetővé.


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Belső szervezet

A Common Data Service belső szervezeti adati két entitásból származnak: **üzemi egység** és **jogi személyek**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]

