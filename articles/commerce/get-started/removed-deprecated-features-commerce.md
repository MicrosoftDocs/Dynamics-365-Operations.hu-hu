---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Commerce alkalmazásban.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335276"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Commerce alkalmazásban.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.10 kiadásában
### <a name="pos-operation-803---picking-and-receiving"></a>803-as pénztári művelet – Kitárolás és bevételezés
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A kitárolási és bevételezési műveletek új művelet-újratervezés miatt elavulnak. |
| **Felváltotta másik szolgáltatás?**   | Igen. A két új pénztári-művelet helyettesíti: bejövő művelet (804) és kimenő művelet (805).|
| **Érintett területek**         | Pénztár (POS) alkalmazás |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 10.0.10 kiadástól kezdve a kitárolási és bevételezési művelet már nem fog új szolgáltatási frissítéseket kapni. Csak a kritikus hibajavítások lesznek végrehajtva ehhez a művelethez a későbbi kiadásokban. Minden ügyfelünket arra bíztatjuk, hogy álljanak át új [Bejövő műveletek](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) és [Kimenő műveletekre](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) lehetőségekre, amelyek továbbra is a hosszú távú termékfejlesztési program részei. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Eltávolított vagy elavult szolgáltatások a Commerce 10.0.7 kiadásában
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>Commerce GetProductAvailabilities és GetAvailableInventoryNearby API-k
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Új, optimalizált API-k lettek létrehozva, ezek váltják le a GetProductAvailabilities és GetAvailableInventoryNearby API-kat. |
| **Felváltotta másik szolgáltatás?**   | Igen: Leváltották a GetEstimatedAvailability és a GetEstimatedProductWarehouseAvailability API-k. |
| **Érintett területek**         | e-Commerce alkalmazás SDK |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: A 10.0.7-es kiadástól a továbbiakban nem fordítunk figyelmet a GetProductAvailabilities és GetAvailableInventoryNearby fejlesztésére. Azok a szervezetek, amelyek ezeket az API-kat használják az e-Commerce telepítések során, át kell álljanak az új GetEstimatedAvailability és GetEstimatedProductWarehouseAvailability API-k használatára, és engedélyezniük kell az [Optimalizált termékelérhetőség-számítás funkciót](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).
