---
title: Közel valós idejű adatintegráció a Common Data Service szolgáltatással
description: Ez a cikk a Finance and Operations és a Common Data Service közötti integrációt tekinti át.
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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019822"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Közel valós idejű adatintegráció a Common Data Service szolgáltatással

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Az aktuális digitális környezetben a vállalkozási ökoszisztémákban a Microsoft Dynamics 365 alkalmazásokat csomagban szokták használni. Mivel a személyektől, az ügyfelektől, a műveletekből és az eszközök internetes hálózatából (IoT-eszközök) származó adatok egy forrásba kerülnek bele, lehetőség van digitális visszacsatolási körök kialakítására. Ehhez alapvetően fontos a Finance and Operations alkalmazások és más Dynamics 365 alkalmazásainak az integrációja. Bizonyos alkalmazások a Common Data Service mellett érhetők el. A Finance and Operations alkalmazásadatok integrációja a Common Data Service megoldással lehetővé teszi más alkalmazások számára a koherens és folyékony kommunikációt a Finance and Operations programmal.

A Finance and Operations alkalmazások és a Common Data Service – kettős írású keretrendszerrel – majdnem valós idejű adatszinkronizálást tesz lehetővé a Finance and Operations alkalmazások és más Dynamics 365 alkalmazások között. A lefedettség nagy, az alkalmazás 28 felületére terjed ki. A célunk, hogy az üzleti folyamatokat az alkalmazásokon keresztül összekötő, zökkenőmentes adatfolyamokkal „egy Dynamics 365” felhasználói élményt kínáljunk.

![Az architektúra áttekintő ábrája](media/dual-write-overview.jpg)

A következő értékajánlatok érhetők el:

+ [Szervezeti hierarchia a Common Data Service rendszerben](organization-mapping.md)
+ [Vállalati koncepció a Common Data Service rendszerben](company-data.md)
+ [Vevő integrált alapadatai](customer-mapping.md)
+ [Integrált főkönyv](ledger-mapping.md)
+ [Egységes terméktapasztalat](product-mapping.md)
+ [Szállító integrált alapadatai](vendor-mapping.md)
+ [Integrált helyek és raktárak](sites-warehouses-mapping.md)
+ [Integrált adózási alapadatok](tax-mapping.md)

## <a name="system-requirements"></a>Rendszerkövetelmények

A szinkron, kétirányú, majdnem valós idejű adatmozgáshoz a következő verziókra van szükség:

+ Microsoft Dynamics 365 for Finance and Operations 10.0.4-es verzió (2019. július), 28-as vagy újabb platformfrissítéssel
+ Microsoft Dynamics 365 for Customer Engagement, 9.1-es (4.2-es) vagy újabb platformverzió

## <a name="setup-instructions"></a>Telepítési útmutató

A Finance and Operations alkalmazások és a Common Data Service közötti integráció beállításához tegye a következőket.
    
1. A kettős írású rendszer beállítása a kettős írás előnézetét bejelentő oldalon lévő [lépésenkénti útmutatóban](https://aka.ms/dualwrite-docs) található.
2. Töltse le és telepítse a megoldást a [Fin Ops és CDS/CE integráció a kettős írás segítségével](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer-csoportból. A csomag öt megoldást tartalmaz:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Kövesse a [kezdeti hivatkozási adatok szinkronizálásának](initial-sync.md) végrehajtási sorrendjét.
4. A dupla írású szinkronizálás problémáinak megoldásáról a [Hibaelhárítási útmutató – adatintegráció](dual-write-troubleshooting.md) részen talál további információt.

> [!IMPORTANT]
> Egyszerre nem használható kettős írás és a [Potenciális ügyfelek készpénzre váltása](../../../../supply-chain/sales-marketing/prospect-to-cash.md). Ha Potenciális ügyfelek készpénzre váltása megoldást használ, el kell távolítania. Ezenkívül a Potenciális ügyfelek készpénzre váltása megoldásban lévő kettős írású vevői és a szállítói sablonokat is le kell tiltani.
