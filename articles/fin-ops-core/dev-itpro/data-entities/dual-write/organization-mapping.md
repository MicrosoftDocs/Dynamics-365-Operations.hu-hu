---
title: Szervezeti hierarchia a Dataverse szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations alkalmazás és a Dataverse között.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 5132fd85fdf2c08ccded9db590328c394a2f984e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744693"
---
# <a name="organization-hierarchy-in-dataverse"></a>Szervezeti hierarchia a Dataverse szolgáltatásban

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Mivel a Dynamics 365 Finance egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik. A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.

Bár a Dataverse nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel. A Dataverse integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Dataverse szolgáltatáshoz.

## <a name="data-flow"></a>Adatáramlás

Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Dataverse alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával. Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Dataverse szolgáltatásban is tájékoztatási és bővítési célból. A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Dataverse szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Dataverse között.

![Architektúra képe](media/dual-write-data-flow.png)

A szervezeti hierarchiához tartozó táblaleképezések a Finance and Operations alkalmazások és a Dataverse szolgáltatás közötti egyirányú adatáramlást szolgálják.

## <a name="templates"></a>Sablonok

A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat. A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott táblaleképezések gyűjteményét.

Finance and Operations-alkalmazásoknak | Egyéb Dynamics 365 alkalmazások | Leírás
-----------------------|--------------------------------|---
Szervezeti hierarchiához kapcsolódó célok | msdyn_internalorganizationhierarchypurposes | Ez a sablon a Szervezeti hierarchia célja tábla egyirányú szinkronizálását teszi lehetővé.
Szervezeti hierarchia típusa | msdyn_internalorganizationhierarchytypes | Ez a sablon a Szervezeti hierarchia típusa tábla egyirányú szinkronizálását teszi lehetővé.
Szervezeti hierarchia – közzétéve | msdyn_internalorganizationhierarchies | Ez a sablon a Szervezeti hierarchia közzétéve tábla egyirányú szinkronizálását teszi lehetővé.
Üzemi egység | msdyn_internalorganizations |
Jogi személyek | msdyn_internalorganizations |
Jogi személyek | cdm_companies | A jogi személy (vállalat) adatainak kétirányú szinkronizálását teszi lehetővé.

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Belső szervezet

A Dataverse belső szervezeti adati két táblából származnak: **üzemi egység** és **jogi személyek**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
