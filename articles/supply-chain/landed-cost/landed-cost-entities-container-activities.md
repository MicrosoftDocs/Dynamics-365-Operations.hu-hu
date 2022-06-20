---
title: Konténertevékenységek entitása
description: Ez a cikk a tárolótevékenységekkel kapcsolatban tartalmaz tájékoztatást, amelyek a szállítási tárolók haladásának nyomon követésére használhatók.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: b69d26ee8abaa403f6a0ef3b03d9015fe507dd5b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873956"
---
# <a name="container-activities-entity"></a>Konténertevékenységek entitása

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

A tárolótevékenységekkel nyomon követhető a szállítási tárolók haladása. A szállítási tároló létrehozásakor kiválasztott utazássablonhoz hozzárendelt mindegyik szakaszhoz egy rekord jön létre. A rekordok akkor is létrejönnek, ha a szállítási tárolót egy adatentitás segítségével hozták létre.

Az átszállításon lévő szállítási tárolók folyamatával kapcsolatos információkat gyakran külső forrásból is bevételeik. A tárolótevékenység-entitás lehetővé teszi egy külső forrás, például egy szállítmányozó számára a rekord közvetlen frissítését. Emiatt nem szükséges manuálisan frissíteni az adatokat.

## <a name="container-activities-itmcontaineractivityentity"></a>Tárolótevékenységek (ITMContainerActivityEntity)

A tárolótevékenység-entitás (`ITMContainerActivityEntity`) további tevékenységrekordok létrehozására használható. Másik lehetőségként a szállítmányozó át tudja adni a visszaigazolt tényleges záródátum-érték **frissítéseit**.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Tényleges befejezési dátum | ITMContainerActivityTable.ActualEndDate | Dátum és idő | Nem | Nem |
| Szállítás módja | ITMContainerActivityTable.DlvModeId | Nvarchar(10) | Nem | Nem |
| Becsült záró dátum | ITMContainerActivityTable.EsizedDate | Dátum és idő | Nem | Nem |
| Sor száma | ITMContainerActivityTable.LineNum | Numerikus (32, 16) | **Igen** | Nem |
| Megjegyzések | ITMContainerActivityTable.Megjegyzések | nvarchar(MAX) | Nem | Nem |
| Tevékenység | ITMContainerActivityTable.ShipActivityId | Nvarchar(10) | Nem | **Igen** |
| Szállítási konténer | ITMContainerActivityTable.ShipContainerId | Nvarchar(20) | **Igen** | **Igen** |
| Út | ITMContainerActivityTable.ShipId | Nvarchar(20) | **Igen** | **Igen** |
| Szakasz | ITMContainerActivityTable.ShipLegId | Nvarchar(20) | Nem | **Igen** |
| Szolgáltató | ITMContainerActivityTable.ShipServiceProvider | Nvarchar(20) | Nem | Nem |
| Hőmérséklet | ITMContainerActivityTable.ShipTemperature | Numerikus (32, 6) | Nem | Nem |
| Hajó | ITMContainerActivityTable.ShipVesselId | Nvarchar(20) | Nem | Nem |
| Kezdés dátuma | ITMContainerActivityTable.StartDate | Dátum és idő | Nem | Nem |

## <a name="tracking-control"></a>Nyomon követési vezérlő

A nyomon követési vezérlőközpont lehetővé teszi egy adott forrásmező frissítését egy adott célmező frissítése által kiváltva. Ha a forrásmező és a cél mező értéke is frissül a tároló tevékenységek entitás használatával, akkor a cél mezőben az entitás értéke fog frissülni. Ez a viselkedés az átfutási **idő Create típusú** *vezérlőrekordokkal kapcsolatos*.

Az **Állapotfrissítés** *·* *vagy* üres (felhasználó által definiált érték) Létrehozás típusú költségterületek esetén a rendszer a követési vezérlő konfigurációja szerint frissíti az hajóút állapotát vagy a célmezőt.

## <a name="calculated-fields"></a>Számított mezők

A tárolótevékenység-rekord következő mezőiben található értékek számítása a többi mező értékei alapján történik. Bár ezek a számított mezők nem szerepelnek az adatentitásban, akkor lesznek beállítva, ha meg vannak állítva azok a mezők, amelyeken a számítások alapulnak.

- **Becsült napok** = **becsült záró dátuma** – **Kezdő dátum**
- **Tényleges napok** = **tényleges záró dátuma** – **Kezdő dátum**
