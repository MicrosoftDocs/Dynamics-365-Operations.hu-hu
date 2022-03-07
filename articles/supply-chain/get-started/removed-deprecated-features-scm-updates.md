---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Supply Chain Management alkalmazásból.
author: kamaybac
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 785f9055c44110d88b9494b5066647511840b646
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909647"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör frissítve lesz a Dynamics 365 Supply Chain Management újonnan eltávolított vagy avultatott szolgáltatásaival.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](/dynamics/s-e/) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.18 kiadásában

### <a name="dynamics-365-for-finance-and-operations---warehousing-the-warehouse-app"></a>Dynamics 365 for Finance and Operations - Raktárkezelés (a raktár alkalmazás)

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | 2021 áprilisától a *Dynamics 365 for Finance and Operations – Raktárkezelés* (a raktár alkalmazás) elavult, és 2022 áprilisa után már nem támogatott. Ezt most felváltja a *Raktárkezelés mobilalkalmazás*, amelyet a Supply Chain Management 10.0.17-es verziójával adtunk ki. Az új alkalmazás egy teljeskörű helyettesítő alkalmazás, de ugyanazt a mögöttes keretrendszert használja, ami megkönnyíti az áttelepítést. Szükség esetén a két alkalmazás egymás mellett is használható, hogy a felhasználók fokozatosan alkalmazkodjanak az új alkalmazás használatához.<br><br>További információért az új Raktárkezelés mobilalkalmazásról lásd: [Raktárkezelés mobilalkalmazás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) és a [Raktárkezelés mobilalkalmazás telepítése és összekapcsolása](../warehousing/install-configure-warehouse-management-app.md). |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt az új Raktárkezelés mobilalkalmazás váltotta le. |
| **Érintett területek**         | Supply Chain Management – Raktár alkalmazás |
| **Telepítési beállítás**              | Felhőbeli és helyszíni |
| **Állapot**                         | Elavult. A raktáralkalmazás hibaüzenetekkel és biztonsági javításokkal kapcsolatban támogatást ka, de nem biztosít funkciófejlesztéseket. 2022 áprilisa után a régi raktáralkalmazást a továbbiakban nem támogatják, és az ügyfeleknek át kell települniük az új Raktárkezelés mobilalkalmazásra. A régi raktáralkalmazás ezután törlődik a Microsoft Store-ból és a Google Play Áruházból.  |

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
| **Állapot**                         | Elavult. 2022. április 1-e után a gyártási forgatókönyvek már nem lesznek támogatottak a beépített Dynamics 365 Supply Chain Management alaptervezési motorral. Gyártási esetekhez a vevőknek a Tervezési optimalizációt kell használniuk az alaptervezés számításaihoz. További tájékoztatás: [Tervezésoptimalizálás dokumentációja](../master-planning/planning-optimization/planning-optimization-overview.md). A Dynamics 365 Supply Chain Management helyszíni telepítését használó ügyfelek továbbra is használhatják a Supply Chain Management alaptervezés motorját a gyártási forgatókönyvekhez 2022 áprilisa után. Azonban nem lesz több funkciófejlesztés. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.11 kiadásában

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>A Supply Chain Management beépített tervezési motorjának használata elosztási forgatókönyvekhez

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítmény fokozása és az SQL-adatbázis terhelésének minimalizálása érdekében alaptervezés futtatásakor a Supply Chain Management alaptervezési motorját leváltja a Tervezési optimalizálás. A Tervezési optimalizálás lehetővé teszi a gyors tervezésfuttatásokat, amelyek munkaidőben is elvégezhetők. Ez lehetővé teszi a tervezők számára, hogy azonnal reagáljanak az igény- vagy a tervezési paraméterek változásaira. |
| **Felváltotta másik szolgáltatás?**   | Igen, a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management alaptervezési motorjának szerepét. |
| **Érintett területek**         | Supply Chain Management – Alaptervezés |
| **Telepítési beállítás**              | Csak felhő. A Tervezés optimalizálása nem támogatott helyszíni telepítések esetében. |
| **Állapot**                         | Elavult. 2021. április 1-e után az elosztási forgatókönyvek már nem lesznek támogatottak a beépített Dynamics 365 Supply Chain Management alaptervezési motorral. Terjesztési esetekhez a vevőknek a Tervezési optimalizációt kell használniuk az alaptervezés számításaihoz. További tájékoztatás: [Tervezésoptimalizálás dokumentációja](../master-planning/planning-optimization/planning-optimization-overview.md). A Dynamics 365 Supply Chain Management helyszíni telepítését használó ügyfelek továbbra is használhatják a Supply Chain Management alaptervezés motorját a terjesztési forgatókönyvekhez 2021. áprilisa után. Azonban nem lesz több funkciófejlesztés. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról

További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]