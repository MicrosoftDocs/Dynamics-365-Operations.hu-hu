---
title: Majdnem valós idejű adatok integrálása a Finance and Operations és a Common Data Service között
description: Ez a cikk a Microsoft Dynamics 365 for Finance and Operations és a Common Data Service közötti integrációt tekinti át.
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
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797228"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a>Majdnem valós idejű adatok integrálása a Finance and Operations és a Common Data Service között

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Az aktuális digitális környezetben a vállalkozási ökoszisztémákban a Microsoft Dynamics 365 csomag egészét szokták használni. Mivel a személyektől, az ügyfelektől, a műveletekből és az eszközök internetes hálózatából (IoT-eszközök) származó adatok egy forrásba kerülnek bele, lehetőség van digitális visszacsatolási körök kialakítására. Ehhez alapvetően fontos a Dynamics 365 for Finance and Operations és a Dynamics 365 for Customer Engagement alkalmazásainak az integrációja. A Customer Engagement-alkalmazások a Common Data Service mellett érhetők el. A Finance and Operations adatainak és a Common Data Service szolgáltatásnak az integrációja révén a Customer Engagement-alkalmazások koherensen és zökkenőmentesen kommunikálhatnak a Finance and Operations rendszerrel.

A Finance and Operations és a Common Data Service – kettős írású keretrendszerrel – majdnem valós idejű adatszinkronizálást tesz lehetővé a Customer Engagement-alkalmazások és a Finance and Operations rendszer között. A lefedettség nagy, a Finance and Operations 28 támadási felületére terjed ki. A célunk, hogy az üzleti folyamatokat az alkalmazásokon keresztül összekötő, zökkenőmentes adatfolyamokkal „egy Dynamics 365” felhasználói élményt kínáljunk.

![Az architektúra áttekintő ábrája](media/dual-write-overview.jpg)

A következő értékajánlatok érhetők el az ügyfelek számára:

+ [Szervezeti hierarchia a Common Data Service rendszerben](dual-write-organization.md)
+ [Vállalati koncepció a Common Data Service rendszerben](dual-write-company.md)
+ [Vevő integrált alapadatai](dual-write-customer.md)
+ [Szállító integrált alapadatai](dual-write-vendor.md)
+ Egyesített alaptermék

## <a name="system-requirements"></a>Rendszerkövetelmények

A szinkron, kétirányú, majdnem valós idejű adatmozgáshoz a következő verziókra van szükség:

+ Microsoft Dynamics 365 for Finance and Operations 10.0.4-es verzió (2019. július), 28-as vagy újabb platformfrissítéssel
+ Microsoft Dynamics 365 for Customer Engagement, 9.1-es (4.2-es) vagy újabb platformverzió

## <a name="setup-instructions"></a>Telepítési útmutató

A Finance and Operations és a Common Data Service közötti integráció az alábbi lépésekkel állítható be.
    
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
