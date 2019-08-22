---
title: Eszközök és munkarendelések
description: Ez a témakör bemutatja az eszközöket és munkarendeléseket az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd55988578be2b0287b399549f17642bfb1693b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783316"
---
# <a name="assets-and-work-orders"></a>Eszközök és munkarendelések

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Ez a témakör bemutatja az eszközöket és munkarendeléseket az Eszközkezelés modulban. Az eszközök és a munkarendelések az Eszközkezelés központi részei. Az *eszköz* olyan gép vagy gépalkatrész, amely folyamatos karbantartást és szervizt igényel. Az eszközöket hierarchikus szerkezetben lehet létrehozni, és a munkavégzési helyszínekhez kapcsolódhatnak. A karbantartási munkákat az eszközstruktúra minden szintjéhez lehet tervezni.

Különböző adatok, például termékadatok és eszközspecifikációk, valamint a szükséges karbantartási tervek vannak beállítva az egyes eszközökhöz. A következő ábrán az eszközadatok áttekintése és az eszközök feladattípusokhoz való viszonya látható. Az öröklést és a függőségeket mutató példák vörös betűkkel jelzettek.

![1. ábra](media/05-overview-image.png)

Minden munkrendeléshez tartozik egy munkarendelés-típus, például megelőző karbantartás, javító karbantartás vagy vizsgálat. A munkarendelés egy vagy több munkarendelési feladatot tartalmaz. Minden munkrendelési feladat meghatároz egy feladatot, amelyet el kell végezni egy eszközön és egy kapcsolódó feladattípuson. A kapcsolódó feladattípusok lehetnek például 10 000 km, 50 000 km, éves nagyjavítás és biztonsági ellenőrzés. Egy munkarendelés több eszközhöz is tartozhat.

A következő ábrán egy munkarendelés legfontosabb adatainak áttekintése látható.

![2. ábra](media/06-overview-image.png)

Egy munkarendelés kapcsolódhat másik munkarendeléshez, a feladattípusok pedig tartalmazhatnak követőfeladatokat, amelyek munkarendelést hoznak létre. Általában nincsenek függőségek a munkarendelések között. Így megváltoztathatók a munkarendelések életciklus-állapota, és egymástól függetlenül ütemezhetők.

A munkarendeléseket többféle módon lehet létrehozni a javító, megelőző vagy reaktív karbantartással kapcsolatban. A munkarendelések manuálisan is létrehozhatók. A következő ábrán a munkarendelések automatikus vagy manuális létrehozására vonatkozó folyamat áttekintése látható.

![3. ábra](media/07-overview-image.png)

Több lépést is el kell végezni egy karbantartási feladat munkarendelésen való ütemezéséhez és futtatásához. A következő ábrán egy munkarendeléshez tartozó feldolgozás áttekintése látható.

![4. ábra](media/08-overview-image.png)

> [!NOTE]
> Általánosságban a Microsoft Dynamics 365 for Finance and Operations szolgáltatással és az **Eszközkezelés** modullal történő munkavégzés során válassza az **Új** lehetőséget új rekord létrehozásához, a **Szerkesztés** lehetőséget a meglévő rekord frissítéséhez, és a **Mentés** lehetőséget az új vagy szerkesztett adatok elmentéséhez.
