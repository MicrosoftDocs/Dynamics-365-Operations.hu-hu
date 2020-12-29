---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Supply Chain Management alkalmazásból.
author: kamaybac
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: d4d2805e36f132660152370cbeee856862ad6faa
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689526"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör frissítve lesz a Dynamics 365 Supply Chain Management újonnan eltávolított vagy avultatott szolgáltatásaival.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.15 kiadásában

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 támogatás a Dynamics 365-höz elavult

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 2020 decemberétől hatályos Microsoft Internet Explorer 11 támogatás az összes Dynamics 365 termékre elavulttá válik, ezért az Internet Explorer 11 nem lesz támogatott 2021. augusztus után.<br><br>Ez hatással lesz azokra, akik Dynamics 365 termékeket használnak, amelyeket a Internet Explorer 11 interfészen való használatra terveztek. 2021. augusztus után az Internet Explorer 11 nem lesz támogatott az ilyen Dynamics 365 termékek esetében. |
| **Felváltotta másik szolgáltatás?**   | Azt ajánljuk, hogy a vevők térjenek át a Microsoft Edgere.|
| **Érintett területek**         | Az összes Dynamics 365 termék |
| **Telepítési beállítás**              | Összes|
| **Állapot**                         | Elavult. Az Internet Explorer 11 támogatottsága 2021. augusztus után megszűnik.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>A Supply Chain Management beépített tervezési motorjának használata gyártási forgatókönyvekhez

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítmény fokozása és az SQL-adatbázis terhelésének minimalizálása érdekében alaptervezés futtatásakor a Supply Chain Management alaptervezési motorját leváltja a Tervezési optimalizálás. A Tervezési optimalizálás lehetővé teszi a gyors tervezésfuttatásokat, amelyek munkaidőben is elvégezhetők. Ez lehetővé teszi a tervezők számára, hogy azonnal reagáljanak az igény- vagy a tervezési paraméterek változásaira. |
| **Felváltotta másik szolgáltatás?**   | Igen, a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management alaptervezési motorjának szerepét. |
| **Érintett területek**         | Supply Chain Management – Alaptervezés |
| **Telepítési beállítás**              | Csak felhő. A Tervezés optimalizálása nem támogatott helyszíni telepítések esetében. |
| **Állapot**                         | Elavult. 2021. október 1-én a gyártási forgatókönyvek már nem lesznek támogatottak a beépített Dynamics 365 Supply Chain Management alaptervezési motorral. Gyártási esetekhez a vevőknek a Tervezési optimalizációt kell használniuk az alaptervezés számításaihoz. További tájékoztatás: [Tervezésoptimalizálás dokumentációja](https://go.microsoft.com/fwlink/?linkid=2105830). A Dynamics 365 Supply Chain Management helyszíni telepítését használó ügyfelek továbbra is használhatják a Supply Chain Management alaptervezés motorját a gyártási forgatókönyvekhez 2021 októbere után. Azonban nem lesz több funkciófejlesztés. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.11 kiadásában

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>A Supply Chain Management beépített tervezési motorjának használata elosztási forgatókönyvekhez

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítmény fokozása és az SQL-adatbázis terhelésének minimalizálása érdekében alaptervezés futtatásakor a Supply Chain Management alaptervezési motorját leváltja a Tervezési optimalizálás. A Tervezési optimalizálás lehetővé teszi a gyors tervezésfuttatásokat, amelyek munkaidőben is elvégezhetők. Ez lehetővé teszi a tervezők számára, hogy azonnal reagáljanak az igény- vagy a tervezési paraméterek változásaira. |
| **Felváltotta másik szolgáltatás?**   | Igen, a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management alaptervezési motorjának szerepét. |
| **Érintett területek**         | Supply Chain Management – Alaptervezés |
| **Telepítési beállítás**              | Csak felhő. A Tervezés optimalizálása nem támogatott helyszíni telepítések esetében. |
| **Állapot**                         | Elavult. 2021. április 1-e után az elosztási forgatókönyvek már nem lesznek támogatottak a beépített Dynamics 365 Supply Chain Management alaptervezési motorral. Terjesztési esetekhez a vevőknek a Tervezési optimalizációt kell használniuk az alaptervezés számításaihoz. További tájékoztatás: [Tervezésoptimalizálás dokumentációja](https://go.microsoft.com/fwlink/?linkid=2105830). A Dynamics 365 Supply Chain Management helyszíni telepítését használó ügyfelek továbbra is használhatják a Supply Chain Management alaptervezés motorját a terjesztési forgatókönyvekhez 2021. áprilisa után. Azonban nem lesz több funkciófejlesztés. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról

További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
