---
title: "A költségek munkafolyamata"
description: "Ez a témakör bemutatja, hogyan használhatja a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition munkafolyamat-rendszerét a költségjelentések felülvizsgálati folyamatának beállítására a Költséggazdálkodás modulban."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2c2e01d4da04cd24c2df1690e6e354e1c03cb50d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="expense-workflow"></a>A költségek munkafolyamata

[!include[banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Finance and Operations, Enterprise edition munkafolyamat-rendszerét a költségjelentések felülvizsgálati folyamatának beállítására használhatja a Költséggazdálkodás modulban. Olyan munkafolyamat adható meg, amely a következő feltételek használatával határozza meg, ki hagyja jóvá a költségjelentéseket:

- Az alkalmazott jelentési hierarchiája, és az előre meghatározott jóváhagyási korlátok
- Köztes jóváhagyókat és végleges jóváhagyót támogató többszintű jóváhagyás
- Pénzügyi dimenziók és projektfelelősség
- Hozzárendelés adott felhasználókhoz vagy felhasználói csoportokhoz

Munkafolyamat-jóváhagyásokat lehet létrehozni a költségjelentésekhez, az utazási igénylésekhez, a készpénzelőlegekhez és az általános forgalmi adó (áfa) visszaigényléséhez.

**példa**

A következő folyamat példaként illusztrálja a költségjelentésekre vonatkozó költségkezelési munkafolyamatot.

1. Egy alkalmazott létrehoz és ment egy költségjelentést.
2. Az alkalmazott benyújtja a költségjelentést jóváhagyásra. A munkafolyamat beállításakor meghatározott szabályok alapján a rendszer azonosítja a jóváhagyót.
3. A jóváhagyó értesítést kap a jóváhagyásra váró költségjelentésről. A jóváhagyó ellenőrzi a költségjelentést, és ellenőrzi, hogy a következő feltételek teljesülnek:

    - A költségek nem sértik a költségszabályokat. Ha egy költség megsért egy szabályt, a jóváhagyó ellenőrzi, hogy a költségjelentésben szerepel-e érvényes üzleti indoklás.
    - A költségjelentéshez csatolják az elektronikus nyugtákat.

4. A jóváhagyó jóváhagyja a költségjelentést.
5. A költségjelentést feladásra a kötelezettségek koordinátorához rendeli a rendszer.
6. A következő lépések valamelyike történik, attól függően, hogy be van-e állítva az automatikus feladás:

    - Ha az automatikus feladás be van állítva, megtörténik a költségjelentés feldolgozása feladásra, és a költségjelentés állapota frissül.
    - Ha az automatikus feladás nincs konfigurálva, a kötelezettségek koordinátora ellenőrzi, hogy minden eredeti nyugtát benyújtottak-e, és hogy a nyugták megfelelnek-e a költségjelentés költségeinek. A költségjelentésben megadott összes adókód helyességét is ellenőrizni kell.

A követelmények ellenőrzését követően megtörténik a költségjelentés feladása.

A költségjelentés feladása után megtörténik a fizetés engedélyzése a költségjelentéshez, és az alkalmazott számára megtörténik a költségei megtérítése.

