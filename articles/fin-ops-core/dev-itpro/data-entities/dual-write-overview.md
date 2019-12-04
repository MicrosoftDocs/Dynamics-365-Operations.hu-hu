---
title: Közel valós idejű adatintegráció a Common Data Service szolgáltatással
description: Ez a témakör a termékadatok integrációjával kapcsolatosan nyújt áttekintést a Finance and Operations és a Common Data Service között.
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
ms.openlocfilehash: 11a5792c9c039eb76337309ef2fdb2b994ce191a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772387"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Közel valós idejű adatintegráció a Common Data Service szolgáltatással

[!include [banner](../includes/banner.md)]

Az aktuális digitális környezetben a vállalkozási ökoszisztémákban a Microsoft Dynamics 365 alkalmazásokat csomagban szokták használni. Mivel a személyektől, az ügyfelektől, a műveletekből és az eszközök internetes hálózatából (IoT-eszközök) származó adatok egy forrásba kerülnek bele, lehetőség van digitális visszacsatolási körök kialakítására. Ehhez alapvetően fontos a Finance and Operations alkalmazások és más Dynamics 365 alkalmazásainak az integrációja. Bizonyos alkalmazások a Common Data Service mellett érhetők el. A Finance and Operations alkalmazások adatainak és a Common Data Service szolgáltatásnak az integrációja révén más alkalmazások koherensen és zökkenőmentesen kommunikálhatnak a Finance and Operations rendszerrel.

A Finance and Operations alkalmazások és a Common Data Service – kettős írású keretrendszerrel – majdnem valós idejű adatszinkronizálást tesz lehetővé a Finance and Operations alkalmazások és más Dynamics 365 alkalmazások között. A lefedettség nagy, az alkalmazás 28 felületére terjed ki. A célunk, hogy az üzleti folyamatokat az alkalmazásokon keresztül összekötő, zökkenőmentes adatfolyamokkal „egy Dynamics 365” felhasználói élményt kínáljunk.

![Az architektúra áttekintő ábrája](media/dual-write-overview.jpg)

A következő értékajánlatok érhetők el:

+ [Szervezeti hierarchia a Common Data Service rendszerben](dual-write-organization.md)
+ [Vállalati koncepció a Common Data Service rendszerben](dual-write-company.md)
+ [Vevő integrált alapadatai](dual-write-customer.md)
+ [Integrált főkönyv](dual-write-ledger.md)
+ [Egységes terméktapasztalat](dual-write-product.md)
+ [Szállító integrált alapadatai](dual-write-vendor.md)
+ [Integrált helyek és raktárak](dual-write-sites-and-warehouses.md)
+ [Integrált adózási alapadatok](dual-write-tax.md)

## <a name="system-requirements"></a>Rendszerkövetelmények

A szinkron, kétirányú, majdnem valós idejű adatmozgáshoz a következő verziókra van szükség:

+ Microsoft Dynamics 365 for Finance and Operations 10.0.4-es verzió (2019. július), 28-as vagy újabb platformfrissítéssel
+ Microsoft Dynamics 365 for Customer Engagement, 9.1-es (4.2-es) vagy újabb platformverzió

## <a name="setup-instructions"></a>Telepítési útmutató

A Finance and Operations alkalmazások és a Common Data Service közötti integráció az alábbi lépésekkel állítható be.
    
1. A kettős írású rendszer beállítása a kettős írás előnézetét bejelentő oldalon lévő [lépésenkénti útmutatóban](https://aka.ms/dualwrite-docs) található.
2. A megoldás [a Finance and Operations, a Common Data Service és a Customer Engagement integrációja](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer-csoportból tölthető le és telepíthető. A csomag öt megoldást tartalmaz:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Kövesse a [kezdeti hivatkozási adatok szinkronizálásának](dual-write-initial.md) végrehajtási sorrendjét.
4. A dupla írású szinkronizálás problémáinak megoldásáról a [Hibaelhárítási útmutató – adatintegráció](dual-write-troubleshooting.md) részen talál további információt.

> [!IMPORTANT]
> Egyszerre nem használható kettős írás és a [Potenciális ügyfelek készpénzre váltása](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct). Ha Potenciális ügyfelek készpénzre váltása megoldást használ, el kell távolítania. Ezenkívül a Potenciális ügyfelek készpénzre váltása megoldásban lévő kettős írású vevői és a szállítói sablonokat is le kell tiltani.
