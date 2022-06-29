---
title: Munkarendelések ütemezése
description: Ez a cikk bemutatja, hogyan lehet ütemezni a munkarendeléseket az Eszközkezelésben.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderSchdulePreviewPart, EntAssetWorkOrderScheduleExclusively, EntAssetWorkOrderSchduleInfoPart, EntAssetWorkOrderScheduleListPage, EntAssetWorkOrderSchedule, EntAssetWorkOrderScheduleDelete
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6592b94105777525c777950132d5099d1e8abb0e
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016739"
---
# <a name="schedule-work-orders"></a>Munkarendelések ütemezése

[!include [banner](../../includes/banner.md)]

 

Ez a cikk bemutatja, hogyan lehet ütemezni a munkarendeléseket az Eszközkezelésben. 

A munkarendeléshez szükséges óraszámot az előre jelzett munkaórák összege mínusz a feladott órák száma határozza meg. Ha több időre van szükség, az előrejelzést ennek megfelelően módosítani kell. Az **Eszközkezelés** > **munkarendelések** > **valamennyi munkarendelése** **vagy** aktív munkarendelése lapon a munkarendelésre vonatkozó előrejelzések megtekintéséhez vagy szerkesztéséhez jelölje ki **a** **munkarendelést**, és kattintson az Előrejelzés gombra a Munkarendelés lapon. A munkarendelések létrehozása és becslése után a munkarendelések következő lépése a szükséges karbantartási dolgozók és eszközök felosztása.

Csak azokat az életciklus-állapottal rendelkező munkarendeléseket lehet ütemezni, amelyeknél engedélyezett az ütemezés. Engedélyezze az ütemezést az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Életciklus-állapotok** > **Általános** gyorslapon > az **Ütemezés engedélyezése** váltógombra kattintva.

1. Kattintson az **Eszközkezelés munkarendelések** > **–** > **Minden munkarendelés elemre**.

2. Válassza ki az ütemezni kívánt munkarendeléseket a listában. Például rendezheti a listát az **Aktuális életciklus-állapot** szerint.

3. Az **Általános** lapon kattintson az **Ütemezés** lehetőségre.

4. Ha szükséges, a **Munkarendelések ütemezése** párbeszédpanelen hozzáadhatók a várt kezdő dátumhoz és szolgáltatási szinthez kapcsolódó beállítások. Ha az ütemezési folyamat figyelembe veszi a más feladatokra már ütemezett erőforrásokra vonatkozó kapacitási korlátozásokat, akkor győződjön meg róla, hogy az **Eszköz**, **Eszköz** és **Dolgozó** váltógomb „Igen” értékű.

    [!NOTE]
    Ha a **Tárgyi eszköz**, **Eszköz** és **Dolgozó** váltógombokat „Nem” értékűre állítja, akkor a program figyelmen kívül hagyja a létező foglalásokat. Az információs naplóban megjelenik az átfedésben lévő munkarendelés-ütemezések listája, az üzenetekre kattintva pedig megnyithatja az egyes munkarendeléseket, és szükség esetén újraütemezheti a munkát.

5. Az ütemezési folyamat részletes adatainak megtekintéséhez válassza az „Igen” beállítást a **Részletes** váltógombnál. Ez azt jelenti, hogy az információs naplóban megjelennek a munkarendelésekhez és a karbantartási dolgozókhoz tartozó számított pontszámokkal kapcsolatos részletes információk.

6. Kattintson az **OK** gombra az ütemezési folyamat elindításához.

7. Az ütemezés befejezésekor az információs napló az ütemezett munkarendelések számát jeleníti meg, valamint további részleteket, ha a **Részletes** váltógomb „Igen” értékűre van állítva.

>[!NOTE]
>A munkarendelések ütemezése munkarendelésenként egy ciklusban történik, nem pedig munkarendelési feladatonként. A **Munkarendelések ütemezése** párbeszédpanel közvetlenül az **Eszközök kezelése** > **Időszakos** > **Munkarendelések** > **Munkarendelések ütemezése** paranccsal is megnyitható. Végezze el a kívánt beállításokat, majd kattintson az **OK** gombra a munkarendelés-ütemezés megkezdéséhez. A munkarendelés-ütemezés kötegelt feladatként is beállítható a **Munkarendelések ütemezése** párbeszédpanel **Futtatás a háttérben** gyorslapján.

*Példa:* Az alábbi ábrán a **Várható kezdés** mezőbe beszúrt képlet minden olyan munkarendeléshez létrehoz egy munkarendelés-ütemezést, amely várhatóan egy hét múlva vagy később kezdődik. Ez a képlet akkor lehet hasznos, ha rendszeresen futtatja a munkarendelés-ütemezést, de azt szeretné, hogy a következő 5-6 napra ütemezett munkarendelések ne legyenek átütemezve.

![1. ábra](media/03-work-order-scheduling.png)

A munkarendelésekhez kapcsolódó munkarendelés-típus egy karbantartási dolgozóhoz is beállíthat ütemezést (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Munkarendelés típusai** > **Egy karbantartási dolgozó** váltógomb „Igen” értékre állítva). Ez azt jelenti, hogy amennyiben egy munkarendelésnél használatban van a munkarendelés-típusa, akkor az **Egy karbantartási dolgozó** váltógomb automatikusan „Igen” értékű lesz az **Összes munkarendelés** részletező lapjának **Fejléc** nézetében található **Ütemezés** gyorslapon. A munkarendelés ütemezése során a munkarendeléshez létrehozott összes munkarendelési feladatot ugyanahhoz a karbantartási dolgozóhoz ütemezi a program. Ha szükséges, szerkesztheti az **Egy karbantartási dolgozó** váltógomb beállítását az **Összes munkarendelés** lapon, hogy több dolgozó vagy egy dolgozó ütemezését engedélyezze a munkarendelési feladatoknál.

Az Eszközkezelés ütemezési folyamata több tényezőt is alkalmaz az ütemezési számításhoz:

- Pontszámok kiszámítása mind a munkarendelésekhez, mind a karbantartási dolgozókhoz. A munkarendelések és a karbantartási dolgozók pontszámait az **Eszközkezelés paraméterei** között lehet beállítani. 
- A feladat elvégzéséhez szükséges kompetenciák, vagyis szakértelmek és bizonyítványok keresése. A karbantartási dolgozók szakértelmeit és bizonyítványait az **Emberi erőforrások** modulban lehet beállítani (**Emberi erőforrások** > **Dolgozók** > **Dolgozók** > dolgozó kiválasztása a listából > **Dolgozó** lap > **Kompetenciák** szakasz > **Szakértelmek** és **Bizonyítványok** gomb). Ezenkívül a szakértelmek és a bizonyítványok a karbantartási feladattípusokhoz és a karbantartási szakmákhoz is hozzáadhatók. A kompetenciákról és a karbantartási feladatok típusairól a következő helyen olvashat bővebben: [Karbantartásifeladat-típusok kategóriái és karbantartásifeladat-típusok, karbantartásifeladat-típusok változatai, karbantartási szakmák és karbantartási ellenőrző listák](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>A munkarendelés-ütemezésben használt pontszámok

A munkarendelési feladathoz tartozó pontszámok számítása a várható kezdési dátum és a munkarendelés szolgáltatási szintje alapján történik.

**Kezdő dátum** számítása: A rendszer a várható kezdő dátum alapján kiszámított minden jövőbeli dátum esetében a kezdő dátum pontszámát kivonja és megszorozza a pontszámmal, amely az alábbi példákban „10”.

**Kritikusság** számítása: A kritikussági pontszám szorozva a munkarendelés kritikusságával.

**Szolgáltatási szint** kiszámítása: A szolgáltatási szint pontszáma osztva a munkarendelés szolgáltatási szintjével.

A lenti példákban a kritikussági pontszám „2”, a szolgáltatási szint pontszámai pedig „5” és „100”.

**1. példa:**

| Munkarendelés azonosítója | Várható kezdési dátum | Munkarendelés kritikussága | Munkarendelési szolgáltatás szintje | Számítás               | Pontszám      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | Holnap            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | Mától két napra   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | Mától két napra   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

A munkarendeléseket a következő sorrendben ütemezi a program: WO-000108 **16**, WO-000108 **18**, WO-000108 **17**.

**2. példa:**

| Munkarendelés azonosítója | Várható kezdési dátum | Munkarendelés kritikussága | Munkarendelési szolgáltatás szintje | Számítás                 | Pontszám    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | Holnap            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | Mától két napra   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | Mától két napra   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

Ha a szolgáltatási szint pontszáma „100”-ra nő „5” helyett, akkor az ütemezési sorrend a következő lesz: WO-000108 **18**, WO-000108 **16**, WO-000108 **17**.

A munkarendeléseken dolgozó karbantartási munkatársak meghatározásával kapcsolatos besorolási pontszámok számokként vannak beállítva, amelyeket a rendszer hozzáad az egyes karbantartási dolgozók számításaihoz a munkarendelés-ütemezés során. A legmagasabb pontszámmal rendelkező karbantartási dolgozó lesz kiválasztva a munkarendeléshez. A karbantartási dolgozók pontszámainak rövid leírása:

| Karbantartási dolgozó pontszáma| Leírás |
|---|---|
| Felelős dolgozó | Ha a karbantartási dolgozó felelős dolgozóként van kiválasztva a munkarendeléshez, akkor a program hozzáadja a pontszámot. |
| Felelős karbantartási dolgozói csoport | Ha a karbantartási dolgozó tagja a felelős dolgozók csoportjának, akkor a program hozzáadja a pontszámot. |
| Preferált karbantartási dolgozó         | Ha a dolgozó preferált karbantartási dolgozóként van kiválasztva az eszközhöz, akkor a program hozzáadja a pontszámot. |
| Preferált karbantartási dolgozói csoport   | Ha a dolgozó a preferált karbantartási dolgozók csoportjának tagja az eszköznél, akkor a program hozzáadja a pontszámot.  |
| Helyszín  | Amennyiben a cég munkavégzési helyszíneket használ, a karbantartási dolgozók teljes pontszámot kapnak, ha az eszközhöz tartozó munkavégzési helyszínen vannak. Ha az eszköz munkavégzési helyszíne rendelkezik fölérendelt helyszínnel, akkor a kérdéses munkavégzési helyszínen lévő dolgozók a pontszám felét kapják meg. Ha az a helyszín is rendelkezik fölérendelt helyszínnel, a kérdéses helyszínen lévő dolgozók a pontszám harmadát kapják meg. Ha az a hely is rendelkezik fölérendelt helyszínnel, a kérdéses helyszínen lévő dolgozók a pontszám negyedét kapják meg – és így tovább. Ha a cég helyeket használ az eszközökhöz (amit nem javaslunk), a rendszer a helyet, a területet és a zónát használja a hely pontszámainak kiszámításához. Ha a dolgozó az eszközzel összekapcsolt helyen, területen és zónában van, teljes pontszámot kap. Ha a dolgozó helye csak a hellyel és a területtel egyezik, a karbantartási dolgozó a teljes pontszám 2/3-át kapja meg értékelési pontszámként. Ha a karbantartási dolgozó helye csak a hellyel egyezik, a karbantartási dolgozó a teljes pontszám 1/3-át kapja meg értékelési pontszámként. |
| A dolgozó kezdési dátuma  | Minden olyan dátum esetében, ahol az ütemezett kezdő dátum későbbi a várt kezdő dátumnál, a rendszer kivonja a pontszámot.  |

>[!NOTE]
>Ha egy pontszám „0” értékre van állítva, akkor az a pontszám nem lesz kiszámítva. Ez akkor lehet hasznos, ha például nem kívánja szerepeltetni egy felelős dolgozót az ütemezésben.

## <a name="competencies-used-in-work-order-scheduling"></a>A munkarendelés-ütemezésben használt kompetenciák

A szakértelmekkel és bizonyítványokkal kapcsolatos követelmények beállíthatók a karbantartási feladattípusokhoz (**Eszközök kezelése** > **Beállítás** > **Feladatok** > **Karbantartási feladattípusok**) és a karbantartási szakterületekhez (**Eszközök kezelése** > **Beállítás** > **Feladatok** > **Karbantartási feladattípus szakterülete**). 

A karbantartási feladattípusok és a karbantartási szakterületek a munkarendelési feladatokban választhatók ki. Ha egy karbantartási feladattípushoz vagy szakterülethez szakértelmek vagy bizonyítványok vannak kiválasztva, és ezt a karbantartási feladattípust vagy szakterületet használják egy munkarendelésben, akkor a program csak a megfelelő szakértelemmel és bizonyítvánnyal rendelkező karbantartási dolgozókat ütemezi a munkarendelésen végzendő munkához.

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>Munka az ütemezett munkarendelésekkel Gantt-diagram használatával

Az **Ütemezett munkarendelésekkel Gantt-diagramja** egy grafikus felületet biztosít, amelyen megtekintheti és újraütemezheti a munkarendeléseket.

A Gantt-diagram megtekintése és használata:

1. Ugorjon az **Eszközkezelés> Munkarendelések> Ütemezett munkarendelések Gantt-diagramja** lehetőségre.

1. A **Beállítások** szakasz legördülő listái és mezői segítségével beállíthatja, hogy a Gantt-diagramon melyik munkavégzési helyszínt, időtartam és időskálát jelenítse meg a program.

1. Válassza az **Alkalmazás** lehetőséget.

    - A Gantt-diagram frissül, és a beállításoknak megfelelő ütemezett munkarendeléseket jeleníti meg. Minden munkarendelést egy kék téglalap jelöl.
    - A megjelenített munkarendelés újraütemezéséhez válassza ki azt, majd húzza át a megfelelő új dátumra és időpontra.

1. Ha módosításokat hajtott végre, a Művelet panelen válassza a **Mentés** parancsot a mentéshez.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]