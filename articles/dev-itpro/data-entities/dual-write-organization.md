---
title: Szervezeti hierarchia a Common Data Service szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789198"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Szervezeti hierarchia a Common Data Service szolgáltatásban

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Mivel a Microsoft Dynamics 365 for Finance and Operations egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik. A vállalati pénzügyei és műveletei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.

Bár a Common Data Service nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel. A Common Data Service integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Common Data Service szolgáltatáshoz.

## <a name="data-flow"></a>Adatáramlás

Egy olyan üzleti ökoszisztéma, amely a Finance and Operations és Common Data Service alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával. Ez a szervezeti hierarchia a Finance and Operations alkalmazásra épül, de látható a Common Data Service szolgáltatásban is tájékoztatási és bővítési célból. A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Common Data Service szolgáltatásban egyirányú adatáramlásként a Finance and Operations és a Common Data Service között.

![Architektúra képe](media/dual-write-data-flow.png)

## <a name="templates"></a>Sablonok

A szervezeti hierarchiához tartozó entitásleképezések a Finance and Operations és a Common Data Service szolgáltatás közötti egyirányú adatáramlást szolgálják.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Szervezeti hierarchia céljának karbantartása

Ez a sablon a Szervezeti hierarchia célja entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a Dynamics 365 for Customer Engagement között.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Belső Szervezeti hierarchia típusa

Ez a sablon a Szervezeti hierarchia típusa entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a Customer Engagement között.

<!-- ![architecture image](media/dual-write-type.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
NÉV | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Belső Szervezeti hierarchia

Ez a sablon a Szervezeti hierarchia közzétéve entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a Customer Engagement között.

<!-- ![architecture image](media/dual-write-organization.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
VALIDTO | \> | msdyn\_validto
VALIDFROM | \> | msdyn\_validfrom
HIERARCHYTYPE | \> | msdyn\_hierarchytypename
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentpartyid
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childpartyid
HIERARCHYTYPE | \> | msdyn\_hierarchytypeid.msdyn\_name
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childid.msdyn\_partynumber
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentid.msdyn\_partynumber

## <a name="internal-organization"></a>Belső szervezet

A Common Data Service belső szervezeti adati két Finance and Operations entitásból származnak: **üzemi egység** és **jogi személyek**.

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a>Üzemi egység

Forrásmező | Térkép típusa | Célmező
---|---|---
LANGUAGEID | \> | msdyn\_languageid
NAMEALIAS | \> | msdyn\_namealias
NÉV | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
OPERATINGUNITTYPE | \>\> | msdyn\_type

### <a name="legal-entity"></a>Jogi személy

Forrásmező | Térkép típusa | Célmező
---|---|---
NAMEALIAS | \> | msdyn\_namealias
LANGUAGEID | \> | msdyn\_languageid
NÉV | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
nincs | \>\> | msdyn\_type
LEGALENTITYID | \> | msdyn\_companycode

## <a name="company"></a>Cég

Kétirányú szinkronizálás biztosít a jogi személyre (vállalat) vonatkozó adatokhoz a Finance and Operations és a Customer Engagement között.

<!-- ![architecture image](media/dual-write-company.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
NÉV | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode
