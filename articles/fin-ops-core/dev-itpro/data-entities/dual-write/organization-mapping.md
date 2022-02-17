---
title: Szervezeti hierarchia a Dataverse szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations alkalmazások és a Dataverse között.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: afc1b5996667835c460f467526493380aa2d6403
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062086"
---
# <a name="organization-hierarchy-in-dataverse"></a>Szervezeti hierarchia a Dataverse szolgáltatásban

[!include [banner](../../includes/banner.md)]



Mivel a Dynamics 365 Finance egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik. A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.

Bár a Dataverse nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel. A Dataverse integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Dataverse szolgáltatáshoz.

## <a name="data-flow"></a>Adatáramlás

Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Dataverse alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával. Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Dataverse szolgáltatásban is tájékoztatási és bővítési célból. A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Dataverse szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Dataverse között.

![Architektúra képe.](media/dual-write-data-flow.png)

Szervezeti hierarchia táblázattérképek állnak rendelkezésre az adatok egyirányú szinkronizálásához a Finance and Operations alkalmazásokból a következőbe Dataverse.

## <a name="templates"></a>Sablonok

A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat. A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott táblaleképezések gyűjteményét.

Finance and Operations alkalmazások | Customer Engagement alkalmazások     | Leírás
-----------------------|--------------------------------|---
[Jogi személyek](mapping-reference.md#102) | cdm_companies | A jogi személy (vállalat) adatainak kétirányú szinkronizálását teszi lehetővé.
[Jogi személyek](mapping-reference.md#142) | msdyn_internalorganizations |
[Üzemi egység](mapping-reference.md#143) | msdyn_internalorganizations |
[Szervezeti hierarchia – közzétéve](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Ez a sablon a Szervezeti hierarchia közzétéve tábla egyirányú szinkronizálását teszi lehetővé.
[Szervezeti hierarchiához kapcsolódó célok](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Ez a sablon a Szervezeti hierarchia célja tábla egyirányú szinkronizálását teszi lehetővé.
[Szervezeti hierarchia típusa](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Ez a sablon a Szervezeti hierarchia típusa tábla egyirányú szinkronizálását teszi lehetővé.

## <a name="internal-organization"></a>Belső szervezet

A Dataverse belső szervezeti adatai két táblából származnak: **Üzemi egység** és **Jogi személyek**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
