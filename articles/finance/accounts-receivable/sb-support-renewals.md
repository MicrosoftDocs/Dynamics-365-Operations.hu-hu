---
title: Támogatás és megújítások
description: Ez a témakör bemutatja, hogy hogyan lehet az értékesítési rendeléseken a támogatási és megújítási folyamatot beállítani és használni a cikkek megújítása számlázási ütemezésének létrehozásához.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d59eee6e858c4f0051ec103adc4e1e99e79feec9
ms.sourcegitcommit: 4d7bc52e6cdf6afce3793893ba2aa07176302314
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560509"
---
# <a name="support-and-renewals"></a>Támogatás és megújítások 

Ez a témakör azt mutatja be, hogyan lehet megadni a támogatási cikkeket és a cikkek megújítását az értékesítési rendelések beíratása során. Ezek a cikkek az eredeti támogatási szerződés díjának és/vagy a megújítási összegnek a kiszámítására használhatók, amikor az előfizetési számlázásban számlázási ütemezést hoznak létre. Például a vállalat egy kiszolgálót ad el a vevőnek, és egy biztonsági másolati előfizetést ajánl fel az első évre, és minden évben lehetőséget nyújt annak az előfizetésnek a megújítására. A *támogatási tétel az* első év előfizetése, *a* megújítási cikk minden következő év megújítása.

Megadhatja a támogatási szerződés, a megújítási szerződés vagy mindkettő adatait. Amikor beírja a támogatási szerződés adatait, csak a támogatási cikk lesz hozzáadva az értékesítési rendeléshez. A megújítási szerződés adatokat a megújítási elem segítségével lehet számlázási ütemezést létrehozni.

## <a name="support-and-renewal-setup"></a>Támogatás és megújítás beállítása

A Támogatási **és megújítási szintek** lapon különböző támogatási szinteket állíthat be a cikkek támogatásához és megújításához. A támogatás vagy megújítás az eredeti cikkösszeg bizonyos százaléka, illetve szokásos összeg is lehet.

Az ismétlődő szerződés számlázási paraméterei lapon **kiválaszthatja az alapértelmezett támogatási szinteket**.

Egy vállalat például a következő támogatási és megújítási szinteket kínálhatja.

| Támogatási szint | Támogatási százalék | Megújítási százalék |
|---|---|---|
| Korlátlan | 40% | 30% |
| Arany | 25% | 18% |
| Ezüst | 20% | 14% |
| Bronz | 15% | 10% |

A következő lépések szerint hozhatja létre a támogatási vagy megújítási szintet.

1. Válassza az **Új lehetőséget a Támogatási és megújítási** szintek **lapon**.
2. A Támogatás **szintje mezőbe** írjon be egy egyedi nevet.
3. Adjon meg egy leírást a **Leírás** mezőben.
4. A Támogatás számítási **mód mezőben** válassza ki a támogatásszámítási módot. Ha a Százalék lehetőséget **választja**, adja meg a támogatás százalékos arányát a Támogatás százalékos **értéke** mezőben.
5. A Megújítás **számítási mód mezőjében** válassza ki a megújítás számítási módját. Ha a Százalék lehetőséget **választja**, adja meg a megújítási százalékértéket a Megújítási **százalék mezőben**.
6. Válassza a **Mentés** lehetőséget.

### <a name="fields"></a>Mezők

A **Támogatási és megújítási szintek** lap a következő mezőket tartalmazza.

| Mező | Leírás |
|---|---|
| Támogatási szint | A támogatási vagy megújítási szint egyedi azonosítója (például **arany** vagy **ezüst**). |
| Leírás | A támogatás vagy megújítási szint leírása. |
| Támogatás számítási metódusa | Válassza ki a szint támogatásszámítási módszerét: **Százalék** vagy **Normál összeg**. |
| Támogatási százalék | Ha a Százalék **beállítást** választotta a támogatás számítási módjaként, adja meg a támogatási cikk árának kiszámításához használt százalékot. Ha a szokásos összeget **választotta** számítási módként, az összeget a tranzakció létrehozásakor adja meg a program. |
| Megújítás számítási módja | Válassza ki a szint megújítási számítási módját: **Százalék** vagy **Normál összeg**. |
| Megújítási százalék | Ha a Százalék **elemet** választotta a megújítási számítási módként, adja meg a megújítási cikk árának kiszámításához használt százalékos értéket. Ha a szokásos összeget **választotta** számítási módként, az összeget a tranzakció létrehozásakor adja meg a program. |

## <a name="support-and-renewal-process"></a>Támogatási és megújítási folyamat

A támogatási és megújítási funkciók különböző támogatási szinteket alkalmazhatnak a cikkekre, és frissítheti a megújítási adatokat az előfizetési számlázásban.

A támogatási és megújítási funkciók használata előtt a következő feladatokat kell elvégezni.

1. Hozzon létre **legalább egy támogatási vagy megújítási szintet a Támogatási és megújítási** szintek oldalon.
2. A Cikk beállítása **lapon** társítsa a cikkeket támogatáshoz és megújításhoz. Erre a feladatra csak akkor van szükség, ha alapértelmezett értékeket szeretne beállítani támogatás és/vagy megújítás érdekében.
3. Az Ismétlődő szerződés **számlázási paraméterei** oldalon adja meg az új számlázási ütemezések alapértelmezett támogatási és megújítási beállításait.

A következő lépésekkel különböző támogatási szinteket alkalmazhat a cikkekre, illetve frissítheti a megújítási információkat.

1. Hozzon létre **egy értékesítési rendelést** az Összes értékesítési rendelés lapon.
2. Adjon hozzá **egy cikket az Értékesítésirendelés-sorok** gyorsgombra.
3. Válassza a **Számla lapon** a Támogatás **\> és megújítás támogatás hozzáadása és megújítása lehetőséget**.
4. A Támogatás **és megújítás folyamatlap** fejlécszakasza **frissül az Ismétlődő szerződés számlázási paraméterei lapon található beállításokkal**. Ezek az értékek minden támogatásra és megújításra vonatkoznak. (Ha például a számlázási gyakoriság a következőre van beállítva: **Évente minden** olyan értékesítési sor, amely újítási cikket hoz létre, éves gyakorisággal fog létrejönni.) Ha az értékesítési rendelést egy meglévő számlázási ütemezéshez társítja, válasszon ki egy értéket a Számlázási **ütemezés száma mezőben**.
5. A támogatás vagy megújítás kezdő dátumának módosítása a Felülbírálás **kezdő** **dátumának beállítása Igen beállítással**.
6. A támogatási elem hozzáadásához vagy szerkesztéséhez jelölje **be** a Támogatás jelölőnégyzetet, majd adjon meg egy támogatási elemet a **Támogatási elem mezőben**. A cikk hozzá lesz adva az értékesítési rendeléshez.
7. A megújítási elem hozzáadásához vagy szerkesztéséhez jelölje **be** a Megújítás jelölőnégyzetet, majd adjon meg egy megújítási cikket a **Megújítás elem mezőben**. Az értékesítési rendelés számlázásakor létrejön egy számlázási ütemezés, amely tartalmazza a cikket.
8. Válassza ki az **OK** lehetőséget.
9. Válassza a **Számla** lehetőséget a Számla **lapon**. Az értékesítési rendelés feladása esetén létrejön a számlázási ütemezés. Az üzenet részleteiben megjelenik egy értesítés, amely tartalmazza a számlázási ütemezés adatait.
10. A Mind **/Aktív számlázási** ütemezések listáról válassza ki azt a számlázási ütemezést, **amely a Számlázási ütemezések lapon található számlázási ütemezés adatait áttekinti**.
11. A Számlázási **ütemezés sorai** gyors ablaktáblán válassza **a** Támogatás és a megújítás lehetőséget a létrehozott sorok részleteinek ellenőrzéshez.

> [!NOTE]
> Ha módosítani kell egy számlázási ütemezési sor megújításának kezdő dátumát, **·** **módosíthatja** a sor Kezdő dátum értékét a Számlázási ütemezések lapon. Amikor megnyitja a sorhoz **a** Számlázási adatok megtekintése lapot, **a Számlázás kezdő** dátuma mezőben az új dátum fog frissülni. A **számlázás záró dátuma** értékének újraszámolt értéke a számlázási gyakoriság alapján. A megújítás kezdő dátuma csak akkor frissíthető, ha a megújítási számlázási ütemezés első számlája még nincs létrehozva és feladva. Az első számla létrehozása és feladása után a kezdő dátum nem módosítható.

A támogatási és megújítási folyamat csak az értékesítési rendeléshez érhető el. Amikor támogatási és megújítási cikkeket ad hozzá egy értékesítési rendeléshez, létrehozhat új számlázási ütemezést, vagy hozzáadhatja a megújítási cikket egy meglévő számlázási ütemezéshez.

## <a name="support-and-renewal-audit"></a>Támogatás és megújítás auditálása

A Támogatás **és megújítás vizsgálati** lapon áttekintheti az értékesítési rendelés megújítási cikkből létrehozott számlázási ütemezési sorok adatait. Ez a lehetőség akkor érhető el, ha a számlázási ütemezés sortétele egy megújítási tétel.

A számlázási ütemezési sorok támogatási és megújítási információinak szerkesztéséhez kövesse ezeket a lépéseket.

1. A Minden **számlázási ütemezés lapon** válassza ki a számlázási ütemezés számát.
2. A Számlázási **ütemezés sorai szakaszban** válasszon ki egy sort, majd válassza a Támogatás **és megújítás lehetőséget**.
3. Tekintse át a támogatáshoz vagy megújításhoz szükséges összes információt.
4. Ha szükséges, módosítsa a támogatási szintet vagy a megújítási százalékértéket, majd adjon meg egy értéket a **Módosítás oka mezőben**.
5. Folyamat **kiválasztása**.

### <a name="fields"></a>Mezők

A **Támogatás és megújítás vizsgálati lap** a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------|
| Cikkszám | A számlázási ütemezési sor cikkszáma. |
| Termék neve | A termék neve. |
| Támogatási csomag szintje | A megújítási cikk támogatási szintjének megtekintése vagy módosítása. |
| Megújítási százalék | Annak a megújítási százaléknak a beírása, amely akkor használatos, amikor a számlázási ütemezésben a megújítási cikk egységárának számítása történik. |
| Megújítási összeg | Annak a megújítási összegnek a beírása, amely akkor használatos, amikor a számlázási ütemezésben a megújítási cikk egységárának számítása történik. |
| Változtatás oka | A támogatással és a megújítással kapcsolatos adatok módosításának indoklása. A Megújítási százalék, **a Megújítási összeg vagy a** **Támogatásterv szintérték módosításakor meg** kell adnia az okot **.** |
| Eredeti értékesítési cikk | Az eredeti értékesítési cikkszám az értékesítési rendelésből. |
| Eredeti nettó összeg | A cikk eredeti nettó összege. |
| Eredeti támogatási szint | A cikk eredeti támogatási szintje. |
| Eredeti megújítási százalék | A cikk eredeti megújítási százaléka. |
| Eredeti megújítási összeg | A cikk eredeti megújítási összege |
| **Rács** | |
| Eredeti támogatási szint | Az előző támogatási szint. |
| Eredeti megújítási százalék | Az előző megújítási százalék |
| Eredeti megújítási összeg | Az előző megújítási összeg |
| Módosította | A változtatást eló felhasználó neve. |
| Módosítás dátuma és időpontja | A módosítás dátuma. |
| OK | A változtatás oka. |
