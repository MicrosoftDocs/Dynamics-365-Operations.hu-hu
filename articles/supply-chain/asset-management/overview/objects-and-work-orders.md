---
title: Eszközök és munkarendelések
description: Ez a témakör bemutatja az eszközöket és munkarendeléseket az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a2872dc84ec11ae7fad9fd5b225b9207f13280db334cc0d010a3d6749a591ee2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718107"
---
# <a name="assets-and-work-orders"></a>Eszközök és munkarendelések

[!include [banner](../../includes/banner.md)]

 

Ez a témakör bemutatja az eszközöket és munkarendeléseket az Eszközkezelés modulban. Az eszközök és a munkarendelések az Eszközkezelés központi részei. Az *eszköz* olyan gép vagy gépalkatrész, amely folyamatos karbantartást és szervizt igényel. Az eszközöket hierarchikus szerkezetben lehet létrehozni, és a munkavégzési helyszínekhez kapcsolódhatnak. A karbantartási munkákat az eszközstruktúra minden szintjéhez lehet tervezni.

Különböző adatok, például termékadatok és eszközspecifikációk, valamint a szükséges karbantartási tervek vannak beállítva az egyes eszközökhöz. A következő ábrán az eszközadatok áttekintése és az eszközök feladattípusokhoz való viszonya látható. Az öröklést és a függőségeket mutató példák vörös betűkkel jelzettek.

![A feladattípusokkal kapcsolatos eszközadatokat megjelenítő ábra.](media/05-overview-image.png)

Minden munkrendeléshez tartozik egy munkarendelés-típus, például megelőző karbantartás, javító karbantartás vagy vizsgálat. A munkarendelés egy vagy több munkarendelési feladatot tartalmaz. Minden munkrendelési feladat meghatároz egy feladatot, amelyet el kell végezni egy eszközön és egy kapcsolódó feladattípuson. A kapcsolódó feladattípusok lehetnek például 10 000 km, 50 000 km, éves nagyjavítás és biztonsági ellenőrzés. Egy munkarendelés több eszközhöz is tartozhat.

A következő ábrán egy munkarendelés legfontosabb adatainak áttekintése látható.

![A munkarendelésen szereplő kulcsfontosságú adatokat megjelenítő ábra.](media/06-overview-image.png)

Egy munkarendelés kapcsolódhat másik munkarendeléshez, a feladattípusok pedig tartalmazhatnak követőfeladatokat, amelyek munkarendelést hoznak létre. Általában nincsenek függőségek a munkarendelések között. Így megváltoztathatók a munkarendelések életciklus-állapota, és egymástól függetlenül ütemezhetők.

A munkarendeléseket többféle módon lehet létrehozni a javító, megelőző vagy reaktív karbantartással kapcsolatban. A munkarendelések manuálisan is létrehozhatók. A következő ábrán a munkarendelések automatikus vagy manuális létrehozására vonatkozó folyamat áttekintése látható.

![Munkarendelések automatikus vagy manuális létrehozását megjelenítő ábra.](media/07-overview-image.png)

Több lépést is el kell végezni egy karbantartási feladat munkarendelésen való ütemezéséhez és futtatásához. A következő ábrán egy munkarendeléshez tartozó feldolgozás áttekintése látható.

![A munkarendelés feldolgozásának áttekintését bemutató ábra.](media/08-overview-image.png)

> [!NOTE]
> Általánosságban a Dynamics 365 Supply Chain Management szolgáltatással és az **Eszközkezelés** modullal történő munkavégzés során válassza az **Új** lehetőséget új rekord létrehozásához, a **Szerkesztés** lehetőséget a meglévő rekord frissítéséhez, és a **Mentés** lehetőséget az új vagy szerkesztett adatok elmentéséhez.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]