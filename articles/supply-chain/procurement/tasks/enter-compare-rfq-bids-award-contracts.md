---
title: Adja meg és hasonlítsa össze az Ajánlatkérés ajánlatait, és rendeljen hozzá szerződéseket
description: Ez az eljárás bemutatja az Ajánlatkérésre (RFQ) történő válaszadás, az ajánlatok pontozásának és összehasonlításának módját, és ezt követően bemutatja azt is, hogy hogyan rendelheti az szerződést egy szállítóhoz.
author: mkirknel
manager: AnnBe
ms.date: 02/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45ddab03810b331bcd8965f6a2ba699ffb138910
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1533352"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Adja meg és hasonlítsa össze az Ajánlatkérés ajánlatait, és rendeljen hozzá szerződéseket

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja az Ajánlatkérésre (RFQ) történő válaszadás, a kapott ajánlatok pontozásának és összehasonlításának módját, és ezt követően bemutatja azt is, hogy hogyan rendelheti az szerződést egy ajánlatot küldött szállítóhoz. Az **USMF** bemutatócég adataiban használhatja ezt az eljárást.

Mielőtt elkezdené ezt az eljárást, egy legalább két szállítónak elküldött, két sorral rendelkező Ajánlatkérésének kell lennie. Az Ajánlatkérés létrehozásához hajtsa végre az [Ajánlatkérés létrehozása](create-request-quotation.md) eljárást. A pontozási feltételeket is be kell állítania az eljárás végrehajtása előtt.

Az ajánlatot szállítóként vagy beszerzési szakemberként is beviheti. További információkért lásd: [Szállítói együttműködés beállítása és fenntartása](../set-up-maintain-vendor-collaboration.md).

## <a name="enter-a-reply-as-a-vendor"></a>Válasz megadása szállítóként

1. Az irányítópulton válassza a **Szállítói ajánlattétel** lehetőséget.
2. Az **Új ajánlati felhívások** listán keressen egy olyan ajánlatkérés, amely éppen el lett küldve. Válassza ki azt a ajánlatkérést, amelyben át szeretné tekinteni a kért elemeket.
3. Válassza ki az **Ajánlatkérés mellékletei** elemet a hozzáadott mellékletek áttekintéséhez.
4. Válassza ki az **Ajánlat** elemet, hogy szerkeszthetővé tegye a mezőket. Figyelje meg, hogy az **Ajánlati folyamat** mező értéke **A szállító frissítést végez**.
5. Adja meg az ajánlati válaszból származó értékeket a fejlécben és a sorokban.
6. Ha az ajánlathoz egy mellékletet kell adni, válassza az **Ajánlat mellékletei** lehetőséget.
7. Válassza az **Ajánlattételi útmutatóelemek** gyorslapot, ahol megtekintheti, hogy mely dokumentumok kötelezők.
8. A **Módosítások** gyorslap kiválasztásával megtekintheti, hogy a ajánlatkérés módosult-e.
9. Válassza a **Kérdőív** gyorslapot. Az itt megjelenő kérdőíveket meg kell válaszolni.
10. Válassza a **Sor részletei** gyorslapot, ahol bővebb információt tekinthet meg a sorról.
11. Csak akkor válassza a **Visszaállítás ajánlatkérésből** lehetőséget, ha vissza kell állítania a megadott értékeket az ajánlatkérés eredeti értékeire.
12. Az ajánlatot bármikor mentheti, és később további feldolgozást végezhet, feltéve, hogy a lejárati dátum és időpont nem telt még el. Ebben az esetben az ajánlatot a **Folyamatban lévő ajánlatok** listában találja a **Szállítói ajánlattétel** munkaterületen.
13. Ha készen áll az ajánlat elküldésére, válassza a **Küldés** parancsot. Ha nem szeretne ajánlatot tenni, válassza az **Elutasítás** elemet.

    Az elküldött ajánlatokhoz az **Elküldött ajánlatok** listában, a **Szállítói ajánlattétel** munkaterületen férhet hozzá.

14. Az ajánlat elküldése után bármikor visszahívhatja a lejárati dátum és időpont előtt. Ne feledje, hogy az ajánlat visszahívása esetén a program nem kezeli elküldöttként.

    Amikor a beszerzési osztály elfogad vagy elutasít egy ajánlatot, az megjelenik a **Megítélt ajánlatok** vagy az **Elveszített ajánlatok** listában a **Szállítói ajánlattétel** munkaterületen.

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>Adja meg a szállítótól kapott választ beszerzési szakemberként.

1. Győződjön meg arról, hogy a szállítói ajánlatok szerkesztésének engedélye be van állítva. Nyissa meg a **Beszerzés és forrás \> Beállítás \> Beszerzés és forrás paraméterei** pontot. Az **Ajánlatkérések** lapon állítsa a **A beszerző szerkesztheti a szállítók ajánlatát** beállítást **Igen** értékre.
2. Navigáljon a következő helyre: **Beszerzés és forrás \> Ajánlatkérések \> Összes ajánlatkérés**.
3. Válasszon ki egy **Elküldött** állapotú Ajánlatkérést, és válassza az **Ajánlatkérési eset** mezőben található hivatkozásra.
4. Válassza a **Válaszok kezelése** pontot. A megjelenő lap egy ajánlatkérést jelenít meg minden olyan szállító számára, amely meghívást kapott az ajánlatra.
5. Válassza ki azt a ajánlatkérést, amelyre még nem válaszolt. (A **Válasz állapota** mező értéke legyen **Még el nem kezdett**.)
6. Válassza a **Szerkesztés \> Ajánlatkérési válasz szerkesztése** lehetőséget.

    Megjelenik az **Ajánlatkérési válasz** oldal. Beszerzési szakemberként a szállító nevében is megadhatja a választ. Figyelje meg, hogy az **Ajánlati folyamat** mező értéke **A beszerző frissítést végez**.

7. Adja meg az ajánlati adatokat. Amikor elkészült, válassza a **Küldés** elemet.

## <a name="score-the-bids"></a>Ajánlatok pontozása

1. Az **Összes ajánlatkérés** lapon válassza ki azt a ajánlatkérési esetet, amelynek a válaszait pontozni szeretné.
2. Válassza a **Válaszok kezelése** pontot.
3. Válassza ki a pontozandó választ.
4. Válassza a **Fejléc** elemet, ahol megtekintheti az ajánlat pontozását.
5. Az **Ajánlat pontozása** gyorslapon adjon meg egy számot az egyik pontozási feltétel **Pontszám** mezőjében.

    Ha a mutatót egy pontozási feltétel fölé viszi, akkor az elemleírás megjeleníti azt a tartományt, amelyen belül a pontszám értékének lennie kell. Ebben a bemutatóban megadhat egy 1 és 5 közötti számot a pontozási feltételek bármelyikéhez.

6. Ismételje meg az 5. lépést egy másik értékelési feltételhez.
7. Ha az ajánlatkérés egy olyan kérdőívet tartalmaz, amelyet már elküldtek a szállítóknak, akkor megadhatja a szállítói válaszokat a **Kérdőív** gyorslapon.
8. Zárja be a lapot.
9. Ismételje meg az 1 – 8. lépést minden további ajánlat esetében.

## <a name="compare-the-replies"></a>Válaszok összehasonlítása

1. A Műveleti ablaktábla **Általános** lapján válassza a **Válaszok összehasonlítása** menüpontot.
2. A **Helyezés** mezőben adjon meg egy számot.

    Ez a lap megjeleníti az ajánlatokat, a fejléccel és soradatokkal, és a fejléc szintjén szereplő összpontszámot is. Összehasonlíthatja a sorokat a rácsba történő rendezéssel, ami által az összehasonlítható sorok egymás mellé kerülnek. Az alábbi információk is szerepelnek:

    - **Mennyiség** – Az ajánlatban a szállító által szerepeltetett mennyiség. Ez a mennyiség eltérhet az ajánlatkérésben megadott mennyiségtől.
    - **Nettó összeg**: A szállító által ajánlott ár a sor cikkeire, az engedmények levonása után.
    - **Eltérés** – Az ajánlat fejlécében vagy sorában megadott szállítási dátum ennyi nappal tér el az ajánlatkérés fejlécében vagy sorában kért szállítási dátumtól. Minden egyes ajánlat rangsorban elfoglalt helyét megadhatja.

3. Válassza ki az azokra az ajánlatokra vonatkozó fejlécet, amelyeket rangsorolni kíván.
4. A **Helyezés** mezőben adjon meg egy számot.
5. Válassza a **Mentés** lehetőséget.

## <a name="reject-a-bid"></a>Ajánlat elutasítása

1. Válassza ki az azokra az ajánlatokra vonatkozó fejlécet, amelyeket el akar utasítani.

    Egyszerre csak egy ajánlatot vagy csak egy ajánlaton belül szereplő sorokat fogadhatja el, utasíthatja el, vagy küldheti vissza.

2. Jelölje be a **Megjelölés** jelölőnégyzetet.

    Ha bejelölte a **Megjelölés** jelölőnégyzetet az ajánlat fejlécén, azzal az összes sort is megjelöli. Ha csak az ajánlat néhány sorát szeretné elutasítani vagy elfogadni, akkor csak az adott sorokat jelölje be. Ezenkívül elfogadhatja egy szállító ajánlatát az ajánlatkérés egyes sorain, majd a többi ajánlatkérési sort egy másik szállítónak ítélheti. Azonban egyszerre csak egy ajánlaton dolgozhat.

    Ha alternatív sorok elérhetőek, akkor vagy az eredeti ajánlat sorát, vagy annak alternatíváját fogadhatja el, de mindkettőt egyszerre nem.

3. Válassza az **Elutasítás** lehetőséget.
4. Válassza a **Paraméterek** elemet, majd az **Elutasítás oka** mezőben adja meg az ajánlat elutasításának okát.

    Az okot a válasszal együtt tárolja a rendszer.

5. Válassza ki az **OK** lehetőséget.
6. Válassza ki az **OK** lehetőséget.

## <a name="accept-a-bid"></a>Válasz elfogadása

1. Válassza ki azt az elfogadni kívánt ajánlatot, majd kattintson az **Ajánlatkérés** mezőjében szereplő hivatkozásra.

    Ha az **Ajánlatkérési válaszok összehasonlítása** lapon van, a kiemelt, fókuszált ajánlat az, amelyet a rendszer figyelembe vesz az Elfogadás művelet során. Egyszerre csak egy ajánlat sorait lehet elfogadni.

2. A Műveleti ablaktáblán kattintson a **Válasz** elemre.
3. Válassza az **Elfogadás** lehetőséget.

    Ha csak meghatározott sorokat jelölt meg, akkor az Elfogadás művelet csak azokat a sorokat fogja tartalmazni. Ha elfogadja az ajánlat összes sorát, akkor nem kell bejelölni a sorokat.

4. Válassza a **Paraméterek** elemet, majd az **Elfogadás oka** mezőben adja meg az ajánlat elfogadásának okát.

    Az okot az ajánlattal együtt tárolja a rendszer.

5. Válassza ki az **OK** lehetőséget.
6. Válassza ki az **OK** lehetőséget.

    Amikor az **OK** gombra kattint, a rendszer az Ajánlatkérés-elfogadásban szereplő sorok alapján létrehoz egy beszerzési rendelést. Más ajánlatok esetén, amelyek még nincsenek feldolgozva (elfogadva, elutasítva vagy visszaküldve), a rendszer figyelmezteti Önt az elutasításukra.

## <a name="view-the-purchase-order-that-is-generated"></a>A létrejött beszerzési rendelés megtekintése

- A Műveleti ablaktábla **Általános** lapján válassza a **Beszerzési rendelés** menüpontot.

    Itt megjelenő oldalon látható az ajánlat elfogadásakor létrehozott beszerzési rendelés.
