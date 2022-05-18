---
title: Munkasor adatai
description: Ez a témakör a Munkasor adatai oldalról nyújt tájékoztatást, amely a rendszer egyes munkasorainak átfogó, csoportosítható és szűrhető listáját tartalmazza.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkLocationChange, WHSWorkLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4d7c6991c0171b0e09752b3305e0fa11a25b7833
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674110"
---
# <a name="work-line-details"></a>Munkasor adatai

[!include [banner](../includes/banner.md)]

A **Munkasor adatai** oldal a rendszer egyes munkasorainak átfogó, csoportosítható és szűrhető listáját jeleníti meg. Ez a művelet teljes áttekintést nyújt a raktárban tervezett és végrehajtandó munkáról. Egyszerűen válthat az összes munkasor megtekintése és a nyitott munkasorok megtekintése között. Az egyes sorokhoz megadott részletek között szerepel a munka állapota, a cikkszám, a hely, a munkamennyiség, a terhelés azonosítója és a szállítmány azonosítója.

## <a name="turn-on-the-work-line-details-feature"></a>A munkasor adatai funkció bekapcsolása

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák a Szolgáltatáskezelés [lapon ellenőrizhetik](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a funkció állapotát, és szükség esetén engedélyezhetik vagy letilthatják azt. Itt a funkció a következőként szerepel:

- **Modul:** *Raktárkezelés*
- **Szolgáltatás neve:** *Munkasor adatai*

## <a name="open-and-use-the-work-line-details-page"></a>A Munkasor adatai oldal megnyitása és használata

A munkasor adatainak megtekintéséhez nyissa meg a **Raktárkezelés \> Munka \> Munkasor adatai** részt. A következő műveleteket végezheti el innen:

- A **Szűrő** mező használatával megkeresheti azokat a sorokat, amelyek egy adott értékkel rendelkeznek bármilyen elérhető paraméter esetében. (A választható paraméterek számos olyan paramétert tartalmaznak, amelyek nem oszlopokként jelennek meg a rácsban.)
- A lezárt sorok megjelenítéséhez vagy elrejtéséhez használja a **Lezártak megjelenítése** jelölőnégyzetet.
- Válassza a **Dimenziók megjelenítése** lehetőséget a **Dimenziók megjelenítése** párbeszédpanel megnyitásához, ahol megjelenítheti és elrejtheti a különböző dimenziók oszlopait a rácsban.
- Válassza ki a kívánt oszlopfejlécet egy olyan menü megnyitásához, ahol megadhatja, hogy a listát az oszlopban szereplő értékek alapján rendezze vagy szűrje.
- Jelöljön ki egy munkasort, majd válassza a **Hely módosítása** lehetőséget a párbeszédpanel megnyitásához, ahol módosíthatja az adott munkasor helyét. A megadott hely felülírja a helyutasítások beállítását.
- Jelöljön ki egy munkasort, majd a **Munkasor visszavonása** kiválasztásával nyissa meg azt a párbeszédpanelt, amelyen részben vagy teljesen csökkentheti a munkasor mennyiségét.
- Mennyiségek helyesbítése.
- A munkasor mögötti tranzakciók megtekintése.

## <a name="try-out-the-feature"></a>A funkció kipróbálása

Ez a szakasz egy három részből álló bemutatót tartalmaz, amely bemutatja, hogy hogyan kezelheti a munkasor adatait.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a bemutatót az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

A bemutatót a gyártási rendszerben végzett munka során útmutatásként is használhatja. Azonban a saját értékeit kell behelyettesítenie, és előfordulhat, hogy bizonyos típusú kötelező rekordok hiányoznak, amelyeket a szabvány demóadatok biztosítanak.

### <a name="verify-that-the-scenario-setup-includes-enough-available-inventory"></a>Győződjön meg róla, hogy a forgatókönyv-beállítás elég elérhető készletet tartalmaz.

Ha az **USMF** bemutató adataival dolgozik, először győződjön meg róla, hogy a rendszer úgy van beállítva, hogy minden fontos kitárolási helyen elegendő készlet legyen. Ennél a bemutatónál azt feltételezzük, hogy a következő készlet áll a rendelkezésére:

- **M9200-as cikk:** 45 ea. (vagy több)
- **M9202-es cikk:** 10 ea. (vagy több)

Hajtsa végre az alábbi lépéseket, és győződjön meg arról, hogy elegendő készlet érhető el, és végezze el a szükséges módosításokat.

1. Nyissa meg a **Raktárkezelés \> Beállítás \> Helyutasítások** lehetőséget, és határozza meg, hogy mely kitárolási helyeket használja a program az értékesítési rendelés 51-es raktárból való kitárolásához. (További információkat lásd: [Raktári munka ellenőrzése munkasablonok és helyutasítások használatával](control-warehouse-location-directives.md).)
1. Ellenőrizze a készlet szintjét a megfelelő helyeken.
1. Módosítsa a készletet igény szerint. Ha módosítania kell a készletet, akkor manuális mozgásokat hozhat létre, felhasználhatja a feltöltést, vagy bármilyen egyéb folyamatot alkalmazhat.

### <a name="part-1-create-picking-work"></a>1. rész: Kitárolási munka létrehozása

A munka létrehozása előtt győződjön meg arról, hogy a raktár úgy van beállítva, hogy a várt módon válaszoljon a munkakérésekre.

Kitárolási munka létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Kattintson az **Új** gombra az **Értékesítési rendelés létrehozása** párbeszédpanel megnyitásához.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az _US-001_ számára.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az _51_ értéket.

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** rácsban. A következő értékeket állítsa be ehhez a rendeléssorhoz:

    - **Cikkszám:** _M9200_
    - **Mennyiség:** _20_
    - **Egység:** _ea_

1. Válassza ki az új rendelési sort, majd a **Készlet** menüben válassza a **Foglalás** elemet a **Foglalás** oldal megnyitásához.
1. A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget. A rendszer létrehoz egy szállítmányt, hozzáadja azt egy új terheléshez, és létrehozza a szükséges munkát.
1. Hozzon létre egy második értékesítési rendelést ugyanarra a vevői számlára és raktárra, amelyet az első rendeléshez használt. Adja hozzá a következő két rendelési sort ehhez a rendeléshez:

    - **1. sor:** Állítsa be a **Cikkszám** mezőt _M9200_ értékre, a **Mennyiség** mezőt _25_ értékre és az **Egység** mezőt _ea_ értékre.
    - **2. sor:** Állítsa be a **Cikkszám** mezőt _M9202_ értékre, a **Mennyiség** mezőt _10_ értékre és az **Egység** mezőt _ea_ értékre.

1. Ismételje meg a 6–8. lépést az egyes rendelési sorok készletének lefoglalásához (egyenként), majd ismételje meg a 9. lépést a rendelésnek a raktárba történő kiadásához.

### <a name="part-2-change-the-location-for-a-work-line"></a>2. rész: Egy munkasor helyének módosítása

1. Ugorjon a **Raktárkezelés \> Munka \> Munkasor adatai** pontra.
1. Keresse meg és válassza ki a bemutatóhoz létrehozott munkasorok egyikét.
1. Az **Új hely kiválasztása** párbeszédpanel megnyitásához jelölje be az **Hely módosítása** jelölőnégyzetet.
1. Az **Új hely kiválasztása** párbeszédpanel **Hely** mezőjében válassza ki a munkasor új helyét.
1. Az **OK** gombra kattintva alkalmazza a módosítást, és zárja be a párbeszédpanelt.

> [!IMPORTANT]
> Csak akkor küldhet helymódosításokat, ha az új hely elegendő készlettel rendelkezik (egy kitároláshoz), vagy ha a hely megfelel a helytípus ellenőrzésének (egy betárolásra).

### <a name="part-3-change-the-quantity-of-a-work-line-or-cancel-a-work-line"></a>3. rész: Egy munkasor mennyiségének módosítása vagy egy munkasor törlése

1. Ugorjon a **Raktárkezelés \> Munka \> Munkasor adatai** pontra.
1. Keresse meg és válassza ki a bemutatóhoz létrehozott munkasorok egyikét. Ne feledje, hogy csak olyan munkasorokhoz lehet törölni vagy módosítani a mennyiségeket, amelyeknél a munkatípus _kitárolás_.
1. A **Munkasor törlése** parancsra kattintva nyissa meg a **Törölni kívánt mennyiség** párbeszédpanelt.
1. A **Törölni kívánt mennyiség** párbeszédpanelen módosítsa a **Mennyiség** mező értékét, és adja meg azt a mennyiséget, amelyet *le kell vonni* sorhoz jelenleg meghatározott mennyiségből. Alapértelmezés szerint a **Mennyiség** mező a teljes mennyiséget jeleníti meg.

    - Ha törölte a teljes mennyiséget, akkor a **Munka állapota** érték _Érvénytelenítve_ állapotúra változik, de a **Munkamennyiség** mező továbbra is az eredeti értéket jeleníti meg.
    - Ha csak a mennyiség egy részét törölte, akkor a **Munka állapota** érték frissül, hogy az új értéket mutassa, de a **Munka állapota** érték nem változik.

1. Az **OK** gombra kattintva alkalmazza a módosítást, és zárja be a párbeszédpanelt.

> [!IMPORTANT]
> Ha a munkasor mennyiségének csak egy részét törli, akkor az elavult mennyiséget is el kell távolítania a terhelés sorból. Ellenkező esetben, hacsak a szállítási hiány nincs helyesen beállítva, a terhelési sor nem kaphat szállítási megerősítést.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]