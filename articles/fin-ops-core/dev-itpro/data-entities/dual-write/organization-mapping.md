---
title: Szervezeti hierarchia a Dataverse szolgáltatásban
description: Ez a témakör leírja a szervezeti adatok integrálását a pénzügyi és műveleti alkalmazások és a Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 48533dd104f62080d0ebd47389a4a829c772db13
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289046"
---
# <a name="organization-hierarchy-in-dataverse"></a>Szervezeti hierarchia a Dataverse szolgáltatásban

[!include [banner](../../includes/banner.md)]



Mivel a Dynamics 365 Pénzügy egy pénzügyi rendszer, *a* szervezet alapfogalma, és a rendszer beállítása egy szervezeti hierarchia konfigurációjában indul el. A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.

Bár a Dataverse nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel. A Dataverse integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Dataverse szolgáltatáshoz.

## <a name="data-flow"></a>Adatáramlás

Pénzügyi és műveleti alkalmazásokból áll üzleti hierarchiát Dataverse, amely továbbra is szervezeti hierarchiával működik. Ez a szervezeti hierarchia a pénzügyre és az üzemeltetésre vonatkozó alkalmazásokra épül, Dataverse de tájékoztató és extenzitási célokat szolgál. Az alábbi ábra a szervezeti hierarchia Dataverse azon adatait mutatja be, amelyek a pénzügyi és műveleti alkalmazásokból egy egy felé történő adatáramlásként megjelenik Dataverse.

![Architektúra képe.](media/dual-write-data-flow.png)

Szervezeti hierarchia tábla-leképezések állnak rendelkezésre a pénzügyi és műveleti alkalmazásokból származó adatok egy egy átszinkronizálására a következőbe:Dataverse

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

