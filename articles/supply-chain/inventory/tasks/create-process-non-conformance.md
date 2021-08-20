---
title: Szabálytalanság létrehozása és feldolgozása
description: Ez a témakör leírja, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 933efff1be545816504ab31f7a3135bf79996d7b8a50dac9fcc5b994e57a8965
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747961"
---
# <a name="create-and-process-nonconformances"></a>Szabálytalanság létrehozása és feldolgozása

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján. A szabálytalanságok kezelését általában egy minőségi munkatárs végez. Előfeltételként rendelkeznie kell egy minőségi rendeléssel. (A minőségi rendelés létrehozásáról további tájékoztatásért lásd: [Az áruk minőségének vizsgálata](inspect-quality-goods.md).)

Ahhoz, hogy egy felhasználó feldolgozhassa a szabálytalanság jóváhagyását, hozzájuk kell rendelni egy dolgozót a **Személy** mezőben a **Felhasználók** oldalon. Ezenkívül ahhoz, hogy a felhasználó használni tudja a dokumentum megjegyzéseit, felhasználói beállításai között be kell állítani a **Dokumentumkezelés engedélyezése** beállítást *Igen* értékre.

## <a name="create-a-nonconformance"></a>Kattintson a Szabálytalanság létrehozása elemre.

Szabálytalanság létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Szabálytalanság létrehozása** párbeszédpanel **Problématípus** mezőjében válassza ki a vizsgálati folyamat során talált probléma típusát.
1. Válassza ki az **OK** lehetőséget.

## <a name="approve-or-reject-a-nonconformance"></a>Szabálytalanság jóváhagyása vagy elutasítása

Az alábbi lépésekkel jóváhagyhatja vagy elutasíthatja a szabálytalanságot.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.

    > [!NOTE]
    > Javítást csak jóváhagyott szabálytalansághoz lehet hozzáadni.

1. A műveletpanelen válassza a **Függvények \> Szabálytlaanság jóváhagyása** elemet a szabálytalanság jóváhagyásához, vagy a **Függvények \> Szabálytalanság elutasítása** elemet az elutasításhoz. A jóváhagyott szabálytalanságok a [kapcsolódó műveletekhez](../quality-operations.md) társíthatók. Ily módon rögzítheti a szabálytalanságok kezelésének és a javítás kezelésének részeként végzett munkát.
1. A rendszer felszólítja, hogy erősítse meg a kiválasztást. A folytatáshoz kattintson az **Igen** gombra.

## <a name="add-operations-and-other-details-to-nonconformances"></a>Műveletek és egyéb részletek hozzáadása a szabálytalanságokhoz

A szabálytalanság létrehozása után elkezdheti hozzáadni a kapcsolódó műveleteket, és további információkat adhat meg az ilyen műveletekről. Kapcsolódó műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni.

Az alapvető információk mellett a következő részleteket lehet hozzáadni egy művelethez:

- **Cikkek** – Létrehozhatja a javítás végrehajtásához felhasznált cikkek listáját. Például a cikkek olyan termékek lehetnek, amelyek szükségesek a berendezés javításához, vagy összetevők, amelyek szükségesek a kész termék átdolgozásához.
- **Minőségi költségek** – létrehozhatja a külső forrásoknál felmerült vagy nekik számlázott költségek listáját.
- **Időnyilvántartás** – Létrehozhat egy naplót arról az időről, amelyet az egyes dolgozók a művelettel töltöttek.

A fennmaradó beállítások megadása nem kötelező. Az egyes cikkek költsége, a minőségi költségek és az időnyilvántartások összegezve jelennek meg a műveletben. A művelet **Költség** mezője nem szerkeszthető közvetlenül.

### <a name="create-an-operation-for-a-nonconformance"></a>Művelet létrehozása szabálytalansághoz kapcsolódóan

Művelet szabálytalansághoz való létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.

    > [!NOTE]
    > Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.

1. A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.
1. A **Kapcsolódó műveletek** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához. Ezután új sorhoz állítsa be a következő mezőket:

    - **Művelet** – A szabálytalanság végrehajtásához szükséges művelet kódjának kiválasztása.
    - **Ok** – adjon meg egy részletes leírást, amely leírja, hogy miért van szükség a műveletre.
    - **Értékesítési rendelés** – ha a kiválasztott műveletkód az értékesítési rendelés típusával van kapcsolatban, válassza ki azt az értékesítési rendelést, amelyhez a műveletet csatolja.
    - **Beszerzési rendelés** – ha a kiválasztott műveletkód a beszerzési rendelés típusával van kapcsolatban, válassza ki azt a beszerzési rendelést, amelyhez a műveletet csatolja.

1. Zárja be a lapokat.

### <a name="add-items-to-an-operation"></a>Cikkek hozzáadása művelethez

A következő lépésekkel adhat hozzá cikkeket a műveletekhez.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.

    > [!NOTE]
    > Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.

1. A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.
1. A **Kapcsolódó műveletek** oldalon válassza ki azt a műveletet, amelybe cikkeket szeretne felvenni.
1. A Művelet ablaktáblán kattintson a **Cikkek** elemre.
1. A **Kapcsolódó műveletek** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához. Ezután új sorhoz állítsa be a következő mezőket:

    - **Cikkszám** – válassza ki azt a terméket, amely a kiválasztott művelet részeként fel lesz használva.
    - **Mennyiség** – adja meg a felhasználandó cikkek számát.

    > [!NOTE]
    > A cikk költségét az **Általános** lap **Költség** mezőjében lehet megtekinteni. Az itt látható költség a **Kiadott termék** oldalon beállított költségből származik. A költség nem frissíthető közvetlenül a **Kapcsolódó művelet cikkje** lapon. A **Kapcsolódó művelet cikkjei** oldalon hozzáadott összes cikk költségét a program automatikusan hozzáadja a **Költség** mezőhöz a **Kapcsolódó műveletek** oldalon.

1. Ismételje meg az előző lépést minden további hozzáadni kívánt cikkel.
1. Zárja be a lapokat.

### <a name="add-quality-charges-to-an-operation"></a>Minőségi költségek hozzáadása egy művelethez

A következő lépésekkel adhat hozzá minőségi költségeket a műveletekhez.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.

    > [!NOTE]
    > Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.

1. A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.
1. A **Kapcsolódó műveletek** oldalon válassza ki azt a műveletet, amelybe minőségi költségeket szeretne felvenni.
1. A Művelet ablaktáblán válassza ki a **Minőségi költségek** elemet.
1. A **Kapcsolódó műveletek költségei** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához. Ezután új sorhoz állítsa be a következő mezőket:

    - **Költségkód** – a hozzáadni kívánt minőségi költség kiválasztása.
    - **Leírás** – Adja meg a költség részletes leírását.
    - **Költségek értéke** – A költség összegének megadása.

1. Ismételje meg az előző lépést minden további hozzáadni kívánt költséggel.
1. Zárja be a lapokat.

> [!NOTE]
> A **Költségek értéke** mezőben található összeget a program automatikusan összegzi minden minőségi költséghez, és hozzáadja a **Kapcsolódó műveletek** oldal **Költség** mezőjében található egyéb összegekhez.

### <a name="create-a-timesheet-on-an-operation"></a>Időnyilvántartás létrehozása művelethez

A következő lépésekkel adhat hozzá időnyilvántartást a műveletekhez.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.

    > [!NOTE]
    > Műveleteket csak jóváhagyott szabálytalansághoz lehet hozzáadni vagy frissíteni.

1. A Művelet ablaktáblán válassza ki a **Kapcsolódó műveletek** elemet.
1. A **Kapcsolódó műveletek** oldalon válassza ki azt a műveletet, amelybe időnyilvántartást szeretne felvenni.
1. A Műveleti ablaktáblán kattintson a **Időnyilvántartás** elemre.
1. A **Kapcsolódó műveletek időnyilvántartásai** oldalon a műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához. Ezután új sorhoz állítsa be a következő mezőket:

    - **Dátum** – a munka befejezési dátumának megadása. Alapértelmezés szerint ez a mező az aktuális dátum.
    - **Dolgozó** – Válassza ki a dolgozót, aki a munkát elvégezte. Alapértelmezés szerint ez a mező az aktuális felhasználóhoz rendelt dolgozóra van beállítva.
    - **Művelet óraszáma** – adja meg a kijelölt műveletben ledolgozott órák számát.
    - **Számlázva** – akkor jelölje be ezt a jelölőnégyzetet, ha az időt kiszámlázták a vevőnek vagy szállítónak egy számlán.

    > [!NOTE]
    > A költséget az **Általános** lap **Költség** mezőjében lehet megtekinteni. A költség kiszámítása a **Készletkezelési paraméterek** oldalon megadott díj alapján történik.

1. Ismételje meg az előző lépést minden további hozzáadni kívánt időnyilvántartással.
1. Zárja be a lapokat.

> [!NOTE]
> A **Költség** mezőben található összeget a program automatikusan összegzi minden időnyilvántartási sorhoz, és hozzáadja a **Kapcsolódó műveletek** oldal **Költség** mezőjében található egyéb összegekhez.

## <a name="add-a-correction-to-a-nonconformance"></a>Szabálytalanság javításának hozzáadása

Javítás szabálytalansághoz való hozzáadásához tegye a következőket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.

    > [!NOTE]
    > Javítást csak jóváhagyott szabálytalansághoz lehet hozzáadni.

1. Válassza a Művelet panelen a **Javítások** lehetőséget.
1. A **Javítások** oldalon a Művelet panelen válassza az **Új** lehetőséget egy sor rácshoz való hozzáadásához. Ezután új sorhoz állítsa be a következő mezőket:

    - **Diagnosztika** – a most létrehozott javítás típusát azonosító diagnosztikai típus kiválasztása.
    - **Dolgozó** – A javításért pénzügyileg felelős személy kiválasztása.
    - **Javítás prioritása** – válassza ki az egyik lehetőséget annak jelzésére, hogy a javítás milyen prioritású legyen (*Alacsony*, *Normális* vagy *Magas*).
    - **Kért dátum** – Adja meg a dátumot, amikor a helyesbítő műveletet igényelték.
    - **Tervezett dátum** – Adja meg a javítás várható befejezésének dátumát.
    - **Rövid távú megoldás** – akkor jelölje be ezt a jelölőnégyzetet, ha a javító művelet csak rövid időre javítja ki a szabálytalanságot.

1. Zárja be a lapokat.

## <a name="mark-a-correction-as-completed"></a>Javítás megjelölése befejezettként

Szabálytalanság javításának befejezettként való megjelöléséhez tegye a következőket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.

    > [!NOTE]
    > Javítást csak jóváhagyott szabálytalansághoz lehet hozzáadni.

1. Válassza a Művelet panelen a **Javítások** lehetőséget.
1. A **Javítások** oldalon a rácson válassza ki a befejezettként megjelölni kívánt javítást.
1. A Műveleti ablaktáblán válassza ki a **Megjelölés befejezettként** lehetőséget.
1. A rendszer felszólítja, hogy erősítse meg a kiválasztást. A folytatáshoz válassza az **OK** lehetőséget. A **Befejezés dátuma és időpontja** mező az aktuális dátumra és időpontra van állítva, és a **Befejezve** jelölőnégyzet be van jelölve.
1. Zárja be a lapot.

## <a name="reopen-a-completed-correction"></a>Befejezett javítás újbóli megnyitása

BEfejezett javítás újbóli megnyitásához tegye a következőket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Szabálytalanságok** lehetőségre.
1. A listában keresse meg és válassza ki a frissíteni kívánt szabálytalanságot.
1. Válassza a Művelet panelen a **Javítások** lehetőséget.
1. A **Javítások** oldalon a rácson válassza ki a javítást, amit újból meg szeretne nyitni.
1. A Műveleti ablaktáblán kattintson az **Újranyitás** elemre.
1. A rendszer felszólítja, hogy erősítse meg a kiválasztást. A folytatáshoz válassza az **OK** lehetőséget. Az érték törlődik a **Befejezés dátuma és időpontja** mezőből, és a **Befejezve** jelölőnégyzetből is törli a jelölést.
1. Zárja be a lapot.

Most további módosításokat vagy frissítéseket lehet végezni a javításon. Ha végzett, a javítást újra befejezettként jelölheti meg.

## <a name="close-a-nonconformance"></a>Szabálytalanság lezárása

Szabálytalanság bezárásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.
1. Válasszon egy minőségi rendelést a rácsban.
1. A Műveleti ablaktáblán kattintson a **Lekérdezések \> Szabálytalanságok** elemre.
1. A **Szabálytalanságok** oldalon válassza ki a célként megadott szabálytalanságot a rácsban.
1. A Műveleti ablaktáblán kattintson a **Függvények \> Szabálytalanság bezárása** elemre.
1. A rendszer felszólítja, hogy erősítse meg a kiválasztást. A folytatáshoz kattintson az **Igen** gombra.
1. Zárja be a lapokat.

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](../quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](../enable-quality-management.md)
- [A szabálytalanságok jóváhagyásáért felelős dolgozók](../quality-responsible-workers.md)
- [A szabálytalanságok karanténzónái](../quality-quarantine-zones.md)
- [A szabálytalanságok diagnosztikai típusai](../quality-diagnostic-types.md)
- [Szabálytalanságok minőségi költségei](../quality-charges.md)
- [Műveletek szabálytalanságokhoz kapcsolódóan](../quality-operations.md)
- [Raktári folyamatok minőségkezelése](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
