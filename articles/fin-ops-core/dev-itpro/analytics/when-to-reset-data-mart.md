---
title: Mikor kell alaphelyzetbe állítani az adatpiacot?
description: Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók és azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093212"
---
# <a name="when-to-reset-a-data-mart"></a>Mikor kell alaphelyzetbe állítani az adatpiacot?

Az adatpiac alaphelyzetbe állítása sok időt vehet igénybe. A körülményektől függően előfordulhat, hogy ez a művelet nem a szükséges megoldás. Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók, valamint azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a>Mikor kell alaphelyzetbe állítani az adatpiacot?
Az adatpiac alaphelyzetbe állítása előtt vegye figyelembe a következő kérdéseket. Ha egy vagy több kérdésre igen a válasz, azt jelezheti, hogy a szervezet számára előnyös lehet az adatpiac alaphelyzetbe állítása.

- Az alkalmazás adatbázisát visszaállították, de az adatpiac adatbázis visszaállítására nem került sor.
- Helytelen adatok láthatók egy könyvelési időszaknál, ami nem a jelentéstervvel kapcsolatos probléma eredménye.
- Egy könyvelési időszaknál helytelen adatok láthatók, és a rekordok a Jelentéstervező **Integrációs kísérletek** lapján vannak felsorolva (indítsa el a Jelentéstervezőt, és válassza ki az **Eszközök > Integráció állapota** lehetőséget).
- Egy támogatási eseményt nyitott meg, és egy ügyfélszolgálati szakértő arra utasítja, hogy állítsa vissza az adatpiacot egy hibaelhárítási lépés részeként.
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a>Mikor nem célszerű alaphelyzetbe állítani az adatpiacot?
Bizonyos körülmények között nem ajánljuk az adatpiac alaphelyzetbe állítását. Ezek közé tartoznak a következők. 

- Bármikor, amikor az ok nem szerepel ebben a témakörben.
- Adatszinkronizálással összefüggő teljesítményproblémákat tapasztal. Ebben a helyzetben az adatpiac alaphelyzetbe állítása valószínűleg nem segít.
- Ha a következő okok valamelyike miatt ismétlődik az alaphelyzetbe állítás: 
  - **Hiányzó adatok** – Először küszöbölje ki a jelentésterv-problémákat és az adatszinkronizálási időmérési problémákat, például figyelje meg, hogy a hiányzó adatok feladása óta nem futott a ténytérkép.
  - **Elakadt integrációs állapot** – Ha az integráció lassú vagy úgy tűnik, hogy elakadt, akkor nem valószínű, hogy az adatpiac alaphelyzetbe állítása oldja meg a problémát.
  - **Az alaphelyzetbe állítási kísérletek sikertelenek voltak** – Ha az adatok visszaállítását több ízben is megpróbálta, és azok a hiányzó adatok miatt sikertelenek voltak, akkor javasoljuk, hogy nyissa meg a támogatási eseményt, és egy ügyfélszolgálati szakemberrel együtt elemezze az adott helyzetet, és csak ezt követően próbálja meg újból alaphelyzetbe állítani az adatpiacot.
  - **Elavult rekordok** – Az elavult rekordok önmagukban nem feltétlenül igazolják az adatpiac alaphelyzetbe állítását. Ha nagy adathalmaz van beállítva, az alaphelyzetbe állítási folyamat futása időt fog igénybe venni, de nem valószínű, hogy ez javulást eredményez.
 
## <a name="what-a-data-mart-reset-does-not-do"></a>Amire az adatpiac alaphelyzetbe állítása nem alkalmas  
- A visszaállítás csak akkor indul el, ha a meglévő feladatok befejeződnek. Így garantálható, hogy a régi adatok nem lesznek beillesztve. Ezen a ponton olyan üzenetet láthat, mint például: "Az adatpiac visszaállítását egy aktív feladat miatt nem sikerült feldolgozni. Próbálkozzon újra később."
- A visszaállítás letiltja az integrációs feladatokat, és törli az adatpiac összes adatát. Az integráció újra engedélyezve van.

> [!NOTE]
> A következő pontok két olyan dolgot határoznak meg, amelyek *nem* érhetők el az adatpiac alaphelyzetbe állításával. <br>
> - A alaphelyzetbe állítások nem törlik a jelentésterveket. <br>
> - Az alaphelyzetbe állítás csak akkor törli a vállalati vagy a felhasználói adatokat, ha be vannak jelölve.
