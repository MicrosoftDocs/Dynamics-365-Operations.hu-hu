---
title: Szervezeti hierarchia a Dataverse szolgáltatásban
description: Ez a témakör leírja a szervezeti adatok integrálását a Pénzügy és a Műveletek alkalmazások és a Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a4edaf5b9c50e9d8781ff703328ac786d71ee782
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884732"
---
# <a name="organization-hierarchy-in-dataverse"></a>Szervezeti hierarchia a Dataverse szolgáltatásban

[!include [banner](../../includes/banner.md)]



Mivel a Dynamics 365 Pénzügy egy pénzügyi rendszer, *a* szervezet alapfogalma, és a rendszer beállítása egy szervezeti hierarchia konfigurációjában indul el. A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.

Bár a Dataverse nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel. A Dataverse integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Dataverse szolgáltatáshoz.

## <a name="data-flow"></a>Adatáramlás

Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Dataverse alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával. Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Dataverse szolgáltatásban is tájékoztatási és bővítési célból. A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Dataverse szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Dataverse között.

![Architektúra képe.](media/dual-write-data-flow.png)

Szervezeti hierarchia tábla-leképezések állnak rendelkezésre a Pénzügy és műveletek alkalmazásból a következőbe történő adatok egy egy átszinkronizálásához Dataverse.

## <a name="templates"></a>Sablonok

Egy szervezet olyan emberek csoportja, akik valamely üzleti folyamat végrehajtása vagy egy cél elérése érdekében együtt dologoznak Szervezeti hierarchiák a vállalkozását alkotó szervezetek közötti kapcsolatotat jelölik. A következő típusú belső szervezeteket adhatja meg: jogi személyek operatív egységek és csoportok. Ahogy a következő táblázat mutatja, a rendszer létrehoz egy táblatérkép-gyűjteményt, amely szinkronizálja a jogi személyeket, az üzemi egységet, valamint a kapcsolódó és a kapcsolódó orgnization hierarchiaadatokat.

Finance and Operations alkalmazások | Customer Engagement alkalmazások     | Leírás
-----------------------|--------------------------------|---
[Jogi személyek](mapping-reference.md#102) | cdm_companies | 
[Jogi személyek](mapping-reference.md#142) | msdyn_internalorganizations |
[Üzemi egység](mapping-reference.md#143) | msdyn_internalorganizations |
[Szervezeti hierarchia – közzétéve](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Ez a sablon a Szervezeti hierarchia közzétéve tábla egyirányú szinkronizálását teszi lehetővé.
[Szervezeti hierarchiához kapcsolódó célok](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Ez a sablon a Szervezeti hierarchia célja tábla egyirányú szinkronizálását teszi lehetővé.
[Szervezeti hierarchia típusa](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Ez a sablon a Szervezeti hierarchia típusa tábla egyirányú szinkronizálását teszi lehetővé.

## <a name="internal-organization"></a>Belső szervezet

A Dataverse belső szervezeti adatai két táblából származnak: **Üzemi egység** és **Jogi személyek**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
