---
title: Köteg intézkedéskódokkal megjelölhető, hogy a kötegek rendelkezésre állnak-e vagy sem.
description: Ez a témakör azt ismerteti, hogyan lehet köteg-intézkedéskódokat beállítani és használni a kötegek elérhetőként való megjelölésére vagy az alaptervezésben, foglalásban, kitárolásban és/vagy szállításban való használatra.
author: t-benebo
ms.date: 09/16/2022
ms.topic: article
ms.search.form: PdsDispositionMaster, InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-16
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cfb0743a573550de93d75063df517e0c143f2568
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542906"
---
# <a name="use-batch-disposition-codes-to-mark-batches-as-available-or-unavailable"></a>Köteg intézkedéskódokkal megjelölhető, hogy a kötegek rendelkezésre állnak-e vagy sem.

Ez a témakör a köteg intézkedéskódok *beállítását és használatát ismerteti*. Minden köteg intézkedéskódja *Elérhető* *vagy Nem elérhető állapotú*. A köteg intézkedéskódokkal jelezhető, hogy az egyes kötegek elérhetők-e alaptervezésre, foglalásra, kitárolásra és/vagy szállításra.

A köteg intézkedési kódjai csak akkor használhatók, ha beállítják a kódokat, és hozzárendelik őket a kezelni kívánt kötegekhez.

## <a name="set-up-batch-disposition-codes"></a>Köteg intézkedési kódjainak beállítása

Minden köteg intézkedéskódját be kell állítania, amit a rendszerben használni szeretne. Annyi kódot hozhat létre, amennyit csak szeretne. (Például létrehozhat kódokat, amelyek azonosítják azokat a különböző okokat, amelyek miatt egy köteg elérhető vagy nem áll rendelkezésre). Gyakran azonban csak két kód lesz: *az* egyik a rendelkezésre álló, a másik a nem *elérhető kód*. Olyan egyéni kódokat is létre lehet hozni, amelyek bizonyos műveletekhez engedélyezik a kötegek felhasználhatóját, másokét azonban nem.

A következő lépések szerint állíthatja be a köteg intézkedési kódjait.

1. Ugrás a Készletkezelés **– Köteg kötegbeállítási \>\> intézkedési alapbeállításához \>**.
1. A **Köteg intézkedési mesterlap** felsorolja az aktuális köteg intézkedéskódját, valamint lehetővé teszi a kötegek létrehozására, törlésére és szerkesztésére. Tegye a következők egyikét:

    - Meglévő kód szerkesztéséhez jelölje ki a listaablakban.
    - Új kód létrehozásához válassza az Új **lehetőséget** a munkaablakban.

1. Állítsa be a következő mezőket az új vagy kiválasztott kód fejlécében:

    - **Köteg intézkedéskódja** – adja meg a kód megjelenítendő nevét.
    - **Leírás** – leírja, hogyan kell használni a kódot.
    - **Köteg intézkedési állapota** – a kódhoz rendelt kötegek állapotának kiválasztása:

        - *Nem érhető* el – a kötegek nem használhatók alaptervezésre, foglalásra, kitárolásra és szállításra. Ha ezt az értéket választja, **·** **·** *a* beállítási gyorsáb minden Blokkolás beállítása Igen értékre lesz állítva, **és minden Nettótable** *beállítás Értéke Nem.* A beállítások egy része azonban úgy is megváltoztatható, hogy kivételeket adjon hozzá.
        - *Elérhető* – a kötegek alaptervezésre, foglalásra, kitárolásra és/vagy szállításra használhatók. Ha ezt az értéket választja, **·** **·** *a* beállítási gyorsáb minden Blokkolás beállítása Nem értékre lesz állítva, **és minden Nettable** *beállítás Igen értékre lesz állítva.* Ezek a beállítások csak olvashatóak lesznek, ha a **Köteg intézkedési állapota** mező beállítása *Elérhető*.

1. Ha a Köteg **intézkedési** *állapot* mezőjében a Nem elérhető állapotot adja meg, akkor minden egyes rendeléstípus (értékesítés, átvitel és termelés) esetén testreszabhatja az egyes műveletek (foglalás, kiválasztás és szállítás) blokkolási állapotát. Termelési rendelésekhez választani lehet a termelési kitárolási napló zárolása vagy a zárolás feloldása között. Az alaptervezés zárolását vagy zárolásának feloldását is választhatja. A beállítási gyorsáb beállításaival **tiltsa** le vagy oldja fel az egyes műveletek zárolását. **A Nettable beállítása** Igen beállítással *engedélyezze* az alaptervezést, *vagy* állítsa Nem beállításra az alaptervezés blokkolása érdekében.

## <a name="assign-batch-disposition-codes-to-batches"></a>Köteg intézkedéskódok hozzárendelése a kötegekhez

Miután meghatározta a köteghez szükséges intézkedési kódokat, kövesse ezeket a lépéseket, és rendelje kötegekhez.

1. Ugrás a Raktárkezelés **beállítása \> készletkötelyek \>\> beállításához**
1. Jelöljön ki egy vagy több köteget, amelyekhez köteg intézkedési kódot szeretne hozzárendelni.
1. A Művelet ablakTábla Alaphelyzet **lapján** válassza a Köteg intézkedési **kód visszaállítása lehetőséget**.
1. A Készletkötemező **korlátozásának** **módosítása** párbeszédpanelen állítsa be az Új köteg intézkedéskód mezőjét a hozzárendelni kívánt kód nevére.
1. Az **új beállítás alkalmazáshoz és a változtatás mentéshez kattintson az OK** gombra.

    A Kötegek **lapon** **·** **a** program frissíti a Köteg intézkedéskódja és a Köteg intézkedési állapot oszlopainak értékeit, hogy tükrözzék a kiválasztott kötegek új beállításait.

## <a name="master-planning-example"></a>Alaptervezés – példa

Ez a példa bemutatja, hogy a köteg intézkedéskódja hogyan befolyásolhatja az alaptervezést.

Ebben a példában a köteg intézkedéskódokat a következő módon lehet beállítani:

- *P-elérhető:*

    - **Köteg intézkedési állapota:** *Elérhető*
    - **Nettós:** *Igen*

- *P-nem érhető el:*

    - **Köteg intézkedési állapota:** *Nem érhető el*
    - **Nettós:** *Nem*

Van egy (*1*. termék) *termék, amely két köteget, az A* és a *köteg-B köteget rendelkezik*. Ezek a kötegek a következő módon vannak beállítva:

- *A köteg:*

    - **Köteg intézkedéskódja:** *P-elérhető*
    - **Tényleges készlet mennyisége:** 1

- *B köteg:*

    - **Köteg intézkedéskódja:** *P-nem érhető el*
    - **Tényleges készlet mennyisége:** 1

2 termék-1 termékre egy értékesítési rendelés (*SO1*) *van.* A szállítási dátum három nappal a mai naptól.

Futtatja az alaptervezést, és beállítja a példához kapcsolódó következő értékeket:

- **Tervezett rendelés:** *Beszerzési rendelés*
- **Feltöltési stratégia:** *követelmény*
- **Átfutási idő:** *0*

A rendszer a tervezés futtatásának eredményeként a rendelkezésre álló köteget (*A köteg) használja fel az SO1 értékesítési rendeléshez szükséges 1* termékmennyiség *fedezésére* *.* Nem használhatja azonban a *B* köteget, mert a köteg nincs tervezésre elérhetőként megjelölve. Ennek megfelelően a fennmaradó mennyiség fedezete érdekében a rendszer létrehoz egy tervezett beszerzési rendelést (*PPO1) az* 1 *. termék új kötegéhez*.

A következő ábra a tervezés eredményének időrendját mutatja be.

![Példa, amely bemutatja, hogy a köteg intézkedéskódja hogyan befolyásolhatja az alaptervezést.](media/batch-codes-planning-example.png "Példa, amely bemutatja, hogy a köteg intézkedéskódja hogyan befolyásolhatja az alaptervezést")
