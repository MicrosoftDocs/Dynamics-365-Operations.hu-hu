---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban
description: Ez a témakör olyan funkciókat ismertet, amelyek már el vannak távolítva, illetve amelyek eltávolítását tervezik a funkcióban Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 722b34e89a54715db39259549c11a78d69d2b4d3
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739870"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a cikk frissülni fog, mert az új eltávolított vagy elavult funkciók dokumentálva vannak a következőben:Dynamics 365 Supply Chain Management

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.

> [!NOTE]
> A pénzügyi és műveletalkalmazások objektumaival kapcsolatos részletes információk a Műszaki hivatkozási [jelentésekben találhatók](/dynamics/s-e/). Ezeknek a jelentéseknek a különböző verzióit össze lehet hasonlítani, hogy megismerjük azokat az objektumokat, amelyek megváltoztak vagy el vannak távolítva a pénzügyi és műveleti alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10029-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.29 kiadásában

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Készletátmozgatási rendelések, ahol az átmozgatási ár adót tartalmaz

| &nbsp;  | &nbsp;  |
|---|---|
| **Elavulás/eltávolítás oka** | Az [áthozott ár funkcióra](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)[adózó készletátviteli rendeléseket felülírják az Indiai Készletátviteli](../../finance/localizations/apac-ind-stock-transfer.md) rendelések funkcióval. |
| **Felváltotta másik szolgáltatás?**   | Igen, az [áthozott](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)[ár funkció adóját adó készletátviteli rendelések helyére az Indiai Készletátviteli rendelések funkció](../../finance/localizations/apac-ind-stock-transfer.md) helyettesíti. |
| **Érintett területek** | Ellátásilánc-kezelés - készlet |
| **Telepítési beállítás** | Felhőbeli és helyszíni |
| **Állapot** | <p>Elavult. Az *áthozott ár* funkcióra adót adó készletátviteli rendelések nem támogatják a hibajavításokat és biztonsági javításokat.</p><p>2023 *áprilisa* után a vevőknek alapesetben az indiai készletátutalási funkciókat kell használni. 2023 *·*. október után az áthozott ár funkcióra adót adó készletátviteli rendelések többé nem lesznek elérhetők, *és* a vevőknek át kell lépniük az indiai készletátviteli funkciók továbbfejlesztett készletátviteli rendelésére.</p><p>A további tudnivalókat lásd az Indiai [Készletátviteli rendeléseknél](../../finance/localizations/apac-ind-stock-transfer.md).</p> |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.19 kiadásában

### <a name="job-card-device"></a>Feladatkártya eszköze

| &nbsp;  | &nbsp;  |
|---|---|
| **Elavulás/eltávolítás oka** | A [feladatkártya eszközét](../production-control/config-job-card-device.md) lecseréli az [termelési üzem végrehajtási felület](../production-control/production-floor-execution-configure.md). |
| **Felváltotta másik szolgáltatás?**   | Igen, a [feladatkártya eszközét](../production-control/config-job-card-device.md) lecseréli az [termelési üzem végrehajtási felület](../production-control/production-floor-execution-configure.md). |
| **Érintett területek** | Supply Chain Management – gyártásfelügyelet |
| **Telepítési beállítás** | Felhőbeli és helyszíni |
| **Állapot** | Elavult. A feladatkártya-eszköz hibaüzenetekkel és biztonsági javításokkal kapcsolatban támogatást kap, de nem biztosít funkciófejlesztéseket. 2022 áprilisa után a régi feladatkártya-eszköz a továbbiakban nem támogatják, és az ügyfeleknek át kell települniük az új termelési üzem végrehajtási felületre. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.18 kiadásában

### <a name="supply-chain-management--warehousing-the-warehouse-app"></a><a name="wma"></a> Ellátásilánc-kezelés – Raktárkezelés (a raktári alkalmazás)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 2021 *. áprilisi hatályos Ellátásilánc-kezelés –* Raktárkezelés (a raktári alkalmazás) elavult, ezért 2022 áprilisa után nem lesz támogatott. Ezt most felváltja a *Raktárkezelés mobilalkalmazás*, amelyet a Supply Chain Management 10.0.17-es verziójával adtunk ki. Az új alkalmazás egy teljeskörű helyettesítő alkalmazás, de ugyanazt a mögöttes keretrendszert használja, ami megkönnyíti az áttelepítést. Szükség esetén a két alkalmazás egymás mellett is használható, hogy a felhasználók fokozatosan alkalmazkodjanak az új alkalmazás használatához.<br><br>További információért az új Raktárkezelés mobilalkalmazásról lásd: [Raktárkezelés mobilalkalmazás](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) és a [Raktárkezelés mobilalkalmazás telepítése és összekapcsolása](../warehousing/install-configure-warehouse-management-app.md). |
| **Felváltotta másik szolgáltatás?**   | Igen, ezt az új Raktárkezelés mobilalkalmazás váltotta le. |
| **Érintett területek**         | Supply Chain Management – Raktár alkalmazás |
| **Telepítési beállítás**              | Felhőbeli és helyszíni |
| **Állapot**                         | Elavult. A raktáralkalmazás hibaüzenetekkel és biztonsági javításokkal kapcsolatban támogatást ka, de nem biztosít funkciófejlesztéseket. 2022 áprilisa után a régi raktáralkalmazást a továbbiakban nem támogatják, és az ügyfeleknek át kell települniük az új Raktárkezelés mobilalkalmazásra. A régi raktáralkalmazás ezután törlődik a Microsoft Store-ból és a Google Play Áruházból.  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.15 kiadásában

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11 támogatás a Dynamics 365-höz elavult

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A 2020 decemberétől hatályos Microsoft Internet Explorer 11 támogatás az összes Dynamics 365 termékre elavulttá válik, ezért az Internet Explorer 11 nem lesz támogatott 2021. augusztus után.<br><br>Ez hatással lesz azokra, akik Dynamics 365 termékeket használnak, amelyeket a Internet Explorer 11 interfészen való használatra terveztek. 2021. augusztus után az Internet Explorer 11 nem lesz támogatott az ilyen Dynamics 365 termékek esetében. |
| **Felváltotta másik szolgáltatás?**   | Azt ajánljuk, hogy a vevők térjenek át a Microsoft Edgere.|
| **Érintett területek**         | Az összes Dynamics 365 termék |
| **Telepítési beállítás**              | Összes|
| **Állapot**                         | Elavult. Az Internet Explorer 11 támogatottsága 2021. augusztus után megszűnik.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>A Supply Chain Management beépített tervezési motorjának használata gyártási forgatókönyvekhez

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítmény fokozása és az SQL-adatbázis terhelésének minimalizálása érdekében alaptervezés futtatásakor a Supply Chain Management alaptervezési motorját leváltja a Tervezési optimalizálás. A Tervezési optimalizálás lehetővé teszi a gyors tervezésfuttatásokat, amelyek munkaidőben is elvégezhetők. Ez lehetővé teszi a tervezők számára, hogy azonnal reagáljanak az igény- vagy a tervezési paraméterek változásaira. |
| **Felváltotta másik szolgáltatás?**   | Igen, a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management alaptervezési motorjának szerepét. |
| **Érintett területek**         | Supply Chain Management – Alaptervezés |
| **Telepítési beállítás**              | Csak felhő. A Tervezés optimalizálása nem támogatott helyszíni telepítések esetében. |
| **Állapot**                         | Elavult. 2022. április 1-ig a gyártási helyzetek már nem lesznek támogatottak a beépített ellátásilánc-kezelési alaptervezési motorban. A Microsoft ezzel a dátummal leállítja a beépített tervezőmotor gyártási helyzetekkel kapcsolatos összes aktív fejlesztési tervét, nem ad ki új funkciókat, és csak a kritikus hibajavításokat fogja kiadni. A dátum után minden vállalatnak, amely a gyártási esetekhez támogatást igényel, az alaptervezési számításaiban a tervezési optimalizálást kell használnia. A tervezési optimalizálás várhatóan 2022 októberére teljes mértékben támogatja a gyártási helyzeteket. További tájékoztatás az [Elavult alaptervezés áttekintésében található](../master-planning/deprecated-master-planning-overview.md).<br><br>Előfordulhat, hogy a vállalatok, ahol az Ellátásilánc-kezelés telepítések vannak, 2022 áprilisa után is a beépített alaptervezési motort használják a gyártási helyzetek kezelésére. Azonban nem lesz több funkciófejlesztés. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.11 kiadásában

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>A Supply Chain Management beépített tervezési motorjának használata elosztási forgatókönyvekhez

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A teljesítmény fokozása és az SQL-adatbázis terhelésének minimalizálása érdekében alaptervezés futtatásakor a Supply Chain Management alaptervezési motorját leváltja a Tervezési optimalizálás. A Tervezési optimalizálás lehetővé teszi a gyors tervezésfuttatásokat, amelyek munkaidőben is elvégezhetők. Ez lehetővé teszi a tervezők számára, hogy azonnal reagáljanak az igény- vagy a tervezési paraméterek változásaira. |
| **Felváltotta másik szolgáltatás?**   | Igen, a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management alaptervezési motorjának szerepét. |
| **Érintett területek**         | Supply Chain Management – Alaptervezés |
| **Telepítési beállítás**              | Csak felhő. A Tervezés optimalizálása nem támogatott helyszíni telepítések esetében. |
| **Állapot**                         | Elavult. 2021. április 1-e után az elosztási forgatókönyvek már nem lesznek támogatottak a beépített Dynamics 365 Supply Chain Management alaptervezési motorral. Terjesztési esetekhez a vevőknek a Tervezési optimalizációt kell használniuk az alaptervezés számításaihoz. További tájékoztatás az [Elavult alaptervezés áttekintésében található](../master-planning/deprecated-master-planning-overview.md). A Dynamics 365 Supply Chain Management helyszíni telepítését használó ügyfelek továbbra is használhatják a Supply Chain Management alaptervezés motorját a terjesztési forgatókönyvekhez 2021. áprilisa után. Azonban nem lesz több funkciófejlesztés. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról

További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

