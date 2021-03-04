---
title: Karbantartási kérések létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet a karbantartási kérést létrehozni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 22d5e371c386abc71946bf64ed8792647f78cf1b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429580"
---
# <a name="create-maintenance-requests"></a>Karbantartási kérések létrehozása

[!include [banner](../../includes/banner.md)]

 

A karbantartási kérések akkor használhatók, ha a karbantartás dolgozók vagy a termelési dolgozók felfedezik, hogy a felszerelés javítása szükséges, de a javítási feladat nem hajtható végre azonnal.

**Példa:** Amíg a karbantartó dolgozó javítási munkát végez, rájön, hogy egy másik eszközt is szervizelni kell ugyanazon a helyszínen. Azonban a karbantartási dolgozónak nincs ideje vagy a pótalkatrészek szükségesek a javítási feladat végrehajtásához. Ezért létrehoz egy karbantartási kérelmet a tárgyi eszközhöz, és beírja a probléma rövid leírását.

Az **Aktív karbantartási kérések** részben a **Kapcsolódó információk** ablaktáblán az **Összes eszköz** vagy **Összes eszköz** oldal jobb oldalán (**Eszközök kezelése** \> **Közös** \> **Eszközök** \> **Összes eszköz** vagy **Aktív eszközök**) láthatók a kijelölt eszközhöz csatolt karbantartási kérések.

1. Válassza az **Eszközkezelés** \> **Közös** \> **Karbantartási kérések** \> **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** lehetőséget.
2. Válassza az **Új** lehetőséget.
3. A **Kérelem létrehozása** párbeszédpanel **Karbantartási kérés típusa** mezőjében válassza ki a karbantartási kérés típusát. Egy alapértelmezett típus javasolva van.
4. A **Leírás** mezőben adjon meg egy nevet vagy egy címet, amely röviden leírja a karbantartási kérést.
5. A **Munkavégzési helyszín** és az **Eszköz** mezőben válasszon ki egy munkavégzési helyszínt vagy egy eszközt, vagy egy munkavégzési helyszín és egy eszköz kombinációját, ahogy szükséges. A karbantartási kérést egy eszköz kiválasztása nélkül is létre lehet hozni, és az eszköz később is hozzáadható a karbantartási kéréshez. Ha a karbantartási dolgozó, aki bejelentkezett egy eszközhöz kapcsolódó erőforráshoz kapcsolódik, akkor az **Eszköz** mező automatikusan be lesz állítva.

    Ha már van hozzárendelve egy karbantartási kérés a kiválasztott eszközhöz, akkor egy üzenetsáv jelenik meg a **Kérés létrehozása** párbeszédpanel tetején, amely tájékoztatja a meglévő karbantartási kérés azonosítójáról. Egy üzenetsáv azt is jelzi, ha az eszközhöz garancia tartozik.

6. A **Szolgáltatási szint** mezőben válassza ki azt a szolgáltatási szintet, amely a kérés sürgősségét jelzi.
7. Ha az 5. lépésben kiválasztott egy eszközt, akkor a **Hiba tünete**, **Hibás terület** és **Hiba típusa** mezőket használhatja a hiba regisztrálásának létrehozásához.
8. Ha a karbantartási kérés karbantartás miatti üzemkimaradást okozott, adja meg az üzemkimaradás kezdő dátumát és időpontját.

    A program automatikusan az Ön nevére állítja az **Elindította** mezőt.

10. A **Tényleges kezdés** mező értéke automatikusan az aktuális dátum és időpont lesz. A mező értéke azonban igény szerint módosítható.
11. A **Megjegyzések** mezőbe írja be a szükséges további megjegyzéseket.
12. Válassza ki az **OK** lehetőséget.

![Karbantartási kérés létrehozása](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>Karbantartási kérések utólagos feldolgozása

Miután létrehozta a karbantartási kérést, de még a munkarendeléssé történő átalakítás előtt, számos adatot frissíteni kell hozzá. Általában egy tervező vagy más adminisztratív alkalmazott hajtja végre ezt a feladatot.

- Az **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** lapon válassza ki a munkához használandó kérelmet, majd válassza a **Szerkesztés** parancsot .

A részleteket nézetben különböző információkat lehet frissíteni. Íme néhány példa:

- Az eszköz kiválasztása és ellenőrzése. Ha később egy másik eszközt kell kiválasztania, akkor az **Eszköz ellenőrizve** beállítást állítsa **Nem** értékre.
- Válassszon egy felelős karbantartásidolgozó-csoportot és/vagy egy felelős karbantartási dolgozót. A szükséges beállításokkal kapcsolatos további tudnivalókat lásd a [Felelős karbantartási dolgozók](../setup-for-maintenance-requests/responsible-workers.md) című részt.
- Válassza ki a karbantartási feladat típusát, és ha ez az információ releváns, akkor egy kapcsolódó karbantartási feladat változatát és a szakmát.
- A **Földrajzi szélesség** és **Földrajzi hosszúság** mezőkben adja meg a földrajzi koordinátákat. A karbantartási kéréshez hozzáadott koordinátákat a program automatikusan átviszi a kapcsolódó munkarendelésbe. 

![Karbantartási kérések frissítése](media/04-manage-maintenance-requests.png)

> [!NOTE]
> Ha a karbantartási kérés létrehozásakor kiválaszt egy eszközt, akkor egy hiba adható hozzá a tárgyi eszközhöz. A karbantartási kérés létrehozása után, igény esetén több hibát is megadhat. Hibák hozzáadásához válassza ki az **Eszköz hibája** lehetőséget az **Összes karbantartási kérés** oldalon.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]