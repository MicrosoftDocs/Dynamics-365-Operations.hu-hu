---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Finance szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Finance alkalmazásban.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: ec13076e6a05c3402af566487f7921f6971da215
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127977"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Eltávolított vagy elavult funkciók a Dynamics 365 Finance szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Finance alkalmazásban.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.12 kiadásában

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Lengyel SSRS-jelentések: Kimeneti áfajegyzék, Beszerzési áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Jogi okból nem szükséges.  |
| **Felváltotta másik szolgáltatás?**   | Igen (Az alapértelmezett ellenőrzési fájlok Excel-formátumban, áfabevallással-JPK_VDEK) |
| **Érintett területek**         | Pályázat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2021. július 1-től már nem tervezzük az SSRS-jelentések támogatását **Kimeneti áfajegyék, Bemeneti áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014**. A (JPK_VDEK) alapértelmezett ellenőrzési fájljához tartozó Excel formátumú példa lesz bevezetve. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Eltávolított vagy elavult szolgáltatások a Finance 10.0.7 kiadásában

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A csoportfiók kiválasztásához tartozó funkció módosult.  |
| **Felváltotta másik szolgáltatás?**   | Igen |
| **Érintett területek**         | Munkafolyamat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Elavult: 2020. december 1-túl a program nem támogatja a kínai bizonylattípus-beállításokat a Számalcsoportok kiválasztása nélkül. További részleteket az új kialakításról lásd: [A 10.0.7 újdonságai](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
