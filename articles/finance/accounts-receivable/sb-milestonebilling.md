---
title: Mérföldkősablonok
description: Ez a cikk bemutatja, hogyan lehet beállítani a mérföldkőhöz tartozó számlázási funcationalitást az előfizetéses számlázásban.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d3c2cf751e4998c73bc3816e5b81e8d5963c8e53
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856770"
---
# <a name="milestone-billing"></a>Mérföldkőszámlázás

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja az előfizetéses számlázás mérföldkőszámlázás funkció sablonjainak a beállítását. A mérföldkősablon minden sorában megadhatja a felosztási százalékot vagy összeget. Ezt követően hozzárendelheti a mérföldkősablont olyan számlázási ütemezési elemekhez, amelyek a mérföldkőhöz tartozó számlázási funkciókat használják.

## <a name="add-a-template"></a>Sablon hozzáadása

A következő lépések szerint adhat hozzá mérföldkősablont.

1. Ugrás az előfizetéses **számlázás \> ismétlődő szerződés számlázási beállításának \> mérföldkősablonjaihoz \>**
2. Válassza az **Új** lehetőséget.
3. A Mérföldkősablon **mezőbe** írja be az új sablon egyedi azonosítóját.
4. Adjon meg egy leírást a **Leírás** mezőben.
5. A Felosztási **mód mezőben** válasszon ki egy felosztási módszert.
6. Nem kötelező: A Teljes **összeg** mezőben adja meg a sablon teljes összegét.
7. Sor hozzáadásához válassza a Hozzáadás **lehetőséget**. Ezután a Cikkszám **mezőben** válassza ki az új sor cikkszámát.
8. Kövesse az alábbi lépéseket attól függően, **hogy milyen értéket választott a Felosztási mód mezőben**:

    - Ha a Százalék felosztási **módként** van kiválasztva, **a** Százalék mezőben határozza meg az egyes sorok százalékos felosztási százalékát. Ha százalékokat ad meg, **·** **az Összes százalék mezőben látható százalékok összegének 100-nak kell lennie.**
    - Ha felosztási módként **a** Változó összeget választotta, **az Összeg** mezőben határozza meg az egyes sorok összegét.
    - Ha az Egyenlő **összeget** választotta felosztási módként, nem kell összeget megadnia. A program minden sort frissít a megfelelő százalékkal és összeggel, a sablonhoz hozzáadott cikkek száma alapján.

9. Válassza a **Mentés** lehetőséget.

## <a name="delete-a-template"></a>Sablon törlése

A következő lépések szerint törölhet egy mérföldkősablont.

1. Jelöljön ki egy vagy több törölni kívánt sort, majd válassza a Törlés **lehetőséget**.
2. Amikor a program kéri a művelet megerősítését, válassza az Igen **lehetőséget**.

## <a name="milestone-template-fields"></a>Mérföldkősablon mezői

A **Mérföldkő sablonlap** a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------| 
| Mérföldkősablon | A mérföldkősablon egyedi azonosítója |
| Leírás | A mérföldkősablon leírása. |
| Felosztási mód | <p>Válassza ki a felosztási módot:</p><ul><li>**Százalékos teljesítési** érték – minden sorhoz egy összesített teljesítési értéket használ a program.</li><li>**Százalék** – a felosztáshoz egy százalékos összeg is meghatározható. A százalékok összegének 100-nak kell lennie.</li><li>**Változó összeg** – egy összeget lehet megadni a felosztáshoz. A felosztási összeg a tranzakció szintjén van meghatározva.</li><li>**Egyenlő összeg** – a felosztási százalékokat a program automatikusan kiszámítja, és egyenlően osztja fel a sablonban lévő cikkek között.</li></ul> |
| Teljes időtartam | A sablon mérföldkőhöz tartozó összegének megadása. |
| **Sorok** | |
| Cikkszám | Válassza ki a cikkszámot a mérföldkősablonhoz. |
| Termék neve | A cikk neve. |
| Százalék | <p>Adja meg a sor felosztási százalékát:</p><ul><li>Ha a **Felosztási mód** mező értéke **Százalék**, adja meg a sor százalékos kulcsát.</li><li>Ha a **Felosztási mód** **mező** értéke Egyenlő összeg, a program automatikusan egyenlő százalékértékekre oszlik a sablonban található cikkek száma alapján.</li></ul><p>Az összes százalék összegének 100-nak kell lennie.</p><p>Ha a **fejlécben** meg van adva a Teljes összeg érték, **és** a sor százalékos értékét módosítja, **akkor a program frissíti az Összeg** értékét. Fordítva, ha módosítja az Összeg **értékét**, **akkor** a százalékérték is frissül.</p> |
| Összeg | <p>A sor felosztási összege:</p><ul><li>Ha a **Felosztási mód** mező értéke Változó **összeg**, adja meg a sor összegét.</li><li>**Ha a Felosztási** **mód** mező értéke Egyenlő összeg, a program automatikusan egyenlő összegekre bontja az összeget, **a** sablonban található cikkek száma és a fejlécben megadott teljes összeg alapján.</li></ul><p>Az összes összeg összegének egyenlőnek kell lennie **a** fejlécben megadott Teljes összeg értékével.</p><p>Ha a **fejlécben** meg van adva a Teljes összeg érték, **és** módosítja a sor Összeg értékét, **akkor** a program frissíti a Százalék értéket. Fordított esetben a Százalék érték módosítása **esetén** a program az **Összeg** értékét is frissíti.</p> |
| **Összegek** | |
| Százalékarány összesen | A százalékok összege. A százalékok összegének 100-nak kell lennie. |
| Teljes időtartam | Az összes sor **összegének** összege. Ennek az összegnek meg kell egynie **a** fejlécben megadott teljes összeg értékével. |
| Fennmaradó összeg | A fennmaradó összeg. Az érték számítása **a** **fejléc** teljes összegének az összes sor összegének összegével csökkentve történik.|

## <a name="milestone-allocation"></a>Mérföldkő felosztás

Mielőtt elkezdené használni a mérföldkőhöz tartozó funkciókat, végre kell ezeket a feladatokat.

1. Egy vagy több mérföldkősablon hozzáadása.
2. Számlázási ütemezési csoport létrehozása. Adja meg **a mérföldkő** típusát, és válasszon egy sablont.
3. A Cikk beállítása **lapon** (**Ismétlődő \>\> előfizetéses számlázás számlázása – Beállítási \>** cikkek) válasszon egy cikk-kapcsolatot és egy mérföldkősablont a cikkbeállításhoz.

Miután létrehozta a mérföldkő-sablonokat, a számlázási ütemezési csoportokat és a cikkeket, létrehozhat egy számlázási ütemezést, amely a mérföldkő funkciókat használja.

A mérföldköveket használó számlázási ütemezések beállításához kövesse ezeket a lépéseket.

1. Válassza az **Új lehetőséget a Számlázási ütemezések lap** **Mind**/**Aktív számlázási ütemezések listájából.**
2. Hozzon létre **egy új számlázási ütemezést a Minden számlázási ütemezés** lapon, és adja meg a vevőszámlát és a kezdő dátumot.
3. A Számlázási ütemezés **sorai szakaszban** válassza a Sor **hozzáadása lehetőséget**. Ezután adjon meg egy cikkszámot, és állítsa **a Cikktípus mezőt** Mérföldkő **típusúra**.

    Ha a cikkhez be van állítva alapértelmezett mérföldkősablon, a rendszer automatikusan hozzáadja a mérföldkőhöz az eseményeket a számlázási ütemezés soraihoz. A mérföldkőhöz tartozó sorokban üresek a záró dátumok.

    Ha nincs beállítva mérföldkősablon a cikkhez, válassza a Mérföldkő foglalása **lehetőséget**. Ezután a Mérföldkő-felosztás **lapon** válasszon ki egy mérföldkősablont, és készítse el a szükséges módosításokat. Ezután a számlázás **ütemezésére** való visszatéréshez válassza a Bezárás lehetőséget, és fejezze be a számlázási ütemezés létrehozását.

4. Ahhoz, hogy számlákat hozzon létre a számlázási ütemezéshez, frissítenie kell az egyes mérföldkő-események záró dátumát. Egyetlen számlázási ütemezés esetén a számlázási ütemezés sorainál frissítheti a mérföldkő eseményének záró dátumát. Ha több számlázási ütemezést is frissíteni kell, válassza a Befejezési dátum **frissítése folyamatot**.
5. A záró dátum frissítése után létrehozhatja a számlát. Egyetlen számlázási ütemezéshez válassza a Számla **létrehozása** a Minden számlázási **ütemezés lapon**. Ha több számlázási ütemezéshez is létre kell hoznia számlákat, válassza a **Számla** **létrehozása vagy a Számla kötegelt feldolgozásának létrehozása** **az Időszakos feladatok csoportban lehetőséget.**

## <a name="edit-milestone-allocation-on-a-billing-schedule-line"></a>Mérföldkő-felosztás szerkesztése számlázási ütemezési sorban

A számlázási ütemezési sorok mérföldkőhöz való foglalásának szerkesztéséhez kövesse ezeket a lépéseket.

1. A Számlázási **ütemezések** lapon > Összes **·** **vagy** aktív számlázási ütemezések mezőjében válassza ki a számlázási ütemezés ütemezésének számát.
2. A Számlázási **ütemezés sorai szakaszban** adjon meg egy cikket, **adja** meg cikkként a Mérföldkő értéket, és válassza a Mérföldkő foglalás **lehetőséget**.
3. A Mérföldkősablon **mezőben** válasszon ki egy mérföldkősablont.
4. Folyamat **kiválasztása**. A rendszer automatikusan hozzáadja a mérföldkősablon-sorokat a számlázási ütemezés soraihoz.

## <a name="milestone-allocation-fields"></a>Mérföldkő-felosztási mezők

A **Mérföldkő-felosztási** lap a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------|
| Szülő cikk | A szülő cikkszáma. |
| Kiterjesztett ár | <p>A cikk kiterjesztett ára. Az érték a számlázási ütemezési **sor** nettó összegének felel meg.</p></p>Mérföldkőhöz tartozó szülőcikk esetén **az** alapértelmezett érték a mérföldkősablonhoz megadott Teljes összeg érték. Ha a teljes összeg 0 (nulla), **az** alapértelmezett érték a számlázási ütemezési sor nettó összegének értéke.</p> |
| Mérföldkősablon | A sorcikk mérföldkősablon-azonosítója |
| Sablon leírása | A mérföldkősablon leírása. |
| Felosztási mód | A mérföldkősablonhoz használt felosztási módszer. |
| **Sorok** | Az összes sor alapértelmezett értékei a kiválasztott mérföldkősablonon alapulnak. Szükség szerint módosíthatja őket. |
| Cikkszám | A mérföldkőhöz tartozó felosztási sablon cikkszáma. |
| Termék neve | A termék neve. |
| Százalék | <p>A sor felosztási százaléka. Az összes százalék összegének 100-nak kell lennie.</p><p>Ha módosítja a sor **Százalékos** értékét, **a nettó összeg** értéke frissül. Fordítva, ha a nettó összeg értékét **módosítja**, **akkor** a százalék is frissül.</p> |
| Nettó összeg | <p>A sor felosztási összege. A sorok nettó összegének meg kell egynie a **fejlécben** megadott kiterjesztett ár értékével.</p><p>Ha módosítja a **sor** nettó összegének értékét, **a** százalékérték módosul. Fordított esetben a Százalék érték módosítása **esetén** **a nettó összeg** is frissül.</p> |
| **Összegek** | |
| Százalék összesen | A százalékértékek **összege** az összes sorra. Ennek az összegnek 100-nak kell lennie. |
| Teljes időtartam | Az összes sor **nettó összegének** összege. Ennek az összegnek meg kell egynie **a** fejlécben megadott kiterjesztett ár értékével. |
| Fennmaradó összeg | A fennmaradó összeg. Az érték számítása a **fejlécben található kiterjesztett ár** **értékével**, az összes sor nettó összegének összegével csökkentve történik. A végső összegnek 0 (nulla) kell lennie. |
