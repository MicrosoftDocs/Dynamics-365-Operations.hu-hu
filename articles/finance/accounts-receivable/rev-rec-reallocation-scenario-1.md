---
title: Bevételelszámolás újbóli felosztása – 1. eset
description: Ebben a cikkben az újbóli felosztásnak azt az esetét mutatjuk be, amelyben két értékesítési rendelést adnak meg, de ezeket csak visszaigazolják. Ugyanez a forgatókönyv hasonló eredményekkel jár, ha kettőnél több értékesítési rendelés van visszaigazolt állapotban.
author: bking
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 92af49d9446fd9ed3310d8d0d50af902e7a7e693
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348317"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>Bevételelszámolás újbóli felosztása – 1. eset

[!include [banner](../includes/banner.md)]

Ebben a cikkben az újbóli felosztásnak azt az esetét mutatjuk be, amelyben két értékesítési rendelést adnak meg, de ezeket csak visszaigazolják. Ugyanez a forgatókönyv hasonló eredményekkel jár, ha kettőnél több értékesítési rendelés van visszaigazolt állapotban.

Ennél az esetnél a **Számlajavítások feladása a Kinnlevőségekbe** beállítás a **Nem** értékre van állítva. Ez a beállítás a **Bevételelszámolás** lapon, a **Főkönyvi paraméterek** oldalon található. (**Bevételelszámolás \> Beállítás \> Főkönyvi paraméterek**).

[![Számlajavítások feladása a Kinnlevőségekbe beállítva a Nem értékre.](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

Létrehoznak egy értékesítési rendelt az US\_SI\_0003 nevű vevőhöz. A vevő vásárol egy laptopot (cikkszám: S0012) és hozzá egy támogatási csomagot (cikkszám: S0008, „Sustained Engineering Service” (Folyamatos mérnöki szolgáltatás)). A rendszer azonnal felismeri a laptophoz tartozó bevételt (nincs bevételelszámolási ütemezés). A rendszer a támogatási csomagra vonatkozó bevételt késlelteti, és 12 hónapra lebontva számolja el, a szerződés dátumtartományának megfelelően.

[![Az értékesítési rendelés sorai a laptophoz és a támogatási csomaghoz.](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

Az értékesítési rendelést visszaigazolták. Mivel mindkét cikk esetében be van állítva a bevételi ár felosztása, a rendszer az értékesítési rendelés visszaigazolásakor kiszámítja a bevételi árat. A **Bevételi ár felosztása** oldalon megtekintheti a rendszer által könyvelt bevételt (a Műveletpanel **Értékesítési rendelés** oldalán, a **Kezelés** lapon, a **Bevételelszámolás** csoportban válassza a **Bevételi ár felosztása** lehetőséget). A laptopra vonatkozó 1008,01 $ bevételt a rendszer feladja a Bevétel számlára. A támogatási csomagra vonatkozó 190,99 $ bevételt a rendszer feladja a Halasztott bevétel számlára. A bevételi árak összegének meg kell egyeznie a bevételi ár felosztásának rögzítésére beállított sorok összegével (1199,00 $).

[![Bevételi ár felosztása oldal.](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

A vevő úgy döntött, hogy a vásárlás időpontjában nem vásárol telepítési szolgáltatásokat (cikkszám: S0001), de később meggondolta magát. Ezért ugyanehhez a vevőhöz egy második értékesítési rendelés is létrejön.

[![Az értékesítési rendelés sora a telepítési szolgáltatásokhoz.](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

A második értékesítési rendelést is visszaigazolják. Mivel ez az értékesítési rendelés csak egy sort tartalmaz, az értékesítési rendelés visszaigazolásakor nem kerül sor a bevételi ár felosztására. A rendszer csak akkor végzi el a bevételi ár felosztását, ha két vagy több egyedi tételről van szó, és ha ezeknél a tételeknél be van állítva a bevételi ár felosztása.

Ha ez az új értékesítési rendelés a vevő szerződését érintő egyetlen módosítás, most már le lehet futtatni az újbóli felosztás folyamatát. A két értékesítési rendelés egyikében válassza az **Ár újbóli felosztása új rendelési sorokba** lehetőséget az **Ár újbóli felosztása új rendelési sorokba** oldal megnyitásához. Másik lehetőségként lépjen a **Bevételelszámolás \> Időszakos feladatok \>Ár újbóli felosztása új rendelési sorokba** lehetőségre. Válassza ki a két értékesítési rendelést és a megfelelő értékesítésirendelés-sorokat, majd válassza az **Újbóli felosztás frissítése** lehetőséget. Az **Újból felosztott összeg** oszlopban megjelenik az egyes értékesítésirendelés-sorok új bevételi ára.

[![Új bevételi árak az Ár újbóli felosztása új rendelési sorokba oldalon.](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

Ha a **Várható bizonylat** lehetőséget választja, semmi nem jelenik meg, mivel egyetlen számlát sem adtak fel.

Az újbóli felosztás befejezéséhez válassza a **Feldolgozás** lehetőséget. A program kéri, hogy adja meg a feladás dátumát, akkor is, ha nem adott fel semmit. Az újbóli felosztás befejezése után az egyes értékesítési rendelések **Bevételi ár felosztása** oldalán megjelenik a két értékesítési rendelés összes tételére vonatkozó felosztás. Más szóval minden értékesítési rendelés **Bevételi ár felosztása** oldalán szerepelni fog egy cikk, amely nem létezik az adott értékesítési rendelésben, mert ez ugyanannak a szerződésnek a része, de egy másik értékesítési rendeléshez tartozik.

> [!TIP]
> Ha szeretne magyarázatot arról, hogy miért jelennek meg itt ezek a cikkek, további oszlopokat adhat a rácshoz, például: **Újrafelosztási azonosító** és **Értékesítési rendelés**.
> 
> [![További oszlopok a Bevételi ár felosztása oldalon.](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
