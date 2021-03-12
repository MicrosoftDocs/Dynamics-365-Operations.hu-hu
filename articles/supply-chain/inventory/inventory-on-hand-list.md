---
title: Aktuális készlet listája
description: Ez a témakör azt mutatja be, hogyan lehet az Aktuális készlet lapot használni az aktuális készlet részleteinek vizsgálatához. Néhány olyan módszert mutat be, amelyekkel a különböző szűrési és rendezési lehetőségek együtt dolgoznak, illetve azt, hogy miért hozhatnak ezek a lehetőségek időnként nem várt eredményeket.
author: sherry-zheng
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 94e54220a68889fd31ac3b269f7a7f6f8dd98c8e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005202"
---
# <a name="inventory-on-hand-list"></a>Aktuális készlet listája

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet az **Aktuális készlet** lapot használni az aktuális készlet részleteinek vizsgálatához. Néhány olyan módszert mutat be, amelyekkel a különböző szűrési és rendezési lehetőségek együtt dolgoznak, illetve azt, hogy miért hozhatnak ezek a lehetőségek időnként nem várt eredményeket.

## <a name="query-your-on-hand-inventory"></a>Kérdezze le az aktuális készletet

A készlet elérhetőségének ellenőrzéséhez menjen a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális lista** lehetőségre.

Az **Aktuális lista** lapja automatikusan frissül, ha a tranzakciókat a készletben hajtják végre. Ezeket a tranzakciók lehetnek előre jelzett, tényleges vagy pénzügyi tranzakciók.

A következő eszközök használatával találhatja meg a keresett termékeket:

- A Műveleti ablaktáblán válassza ki a [**Dimenziókat**](#dimensions) a párbeszédpanel megnyitásához, ahol az **Aktuális** rácsban megjelenő oszlopokat adhat hozzá vagy távolíthat el.
- A [**Szűrők** ablaktáblában](#filters-pane) adja meg az egyes mezők értékeit, hogy csak azok a rekordok jelenjenek meg, amelyek megfelelnek ezeknek az értékeknek. Ne felejtse el, hogy az itt megadott szűrők olyan forrástáblákra vonatkoznak, amelyek később összesítve lehetnek a megjelenítendőként kiválasztott dimenziók alapján. Ha további tájékoztatást szeretne arról, hogy ez a viselkedés milyen hatással lehet az eredményekre, tekintse meg a [Példák](#examples) lehetőséget a témakör későbbi részében.
- A **Szűrők** ablaktáblán válassza ki az **Alkalmaz** lehetőséget a megegyező aktuális készlet létrehozásához az **Aktuális** rácsban.
- Az **Aktuális** rácsban válassza ki bármelyik az oszlop fejlécét, hogy az oszlopban szereplő értékek alapján rendezzen vagy szűrjön. A rács felső részén található GyorsSzűrő további szűrési beállításokat biztosít. Ezek a szűrők az eredményekre vonatkoznak, nem pedig a forrástáblákra. Ha további tájékoztatást szeretne arról, hogy ez a viselkedés milyen hatással lehet az eredményekre, tekintse meg a [Példák](#examples) lehetőséget a témakör későbbi részében.

Az egyező cikkekhez az **Aktuális** rács minden a következő készletadatok oszlopait adja meg.

| Oszlop | Leírás |
|---|---|
| Tényleges készlet | A készletben elérhető tényleges mennyiség. |
| Ténylegesen fenntartott | A ténylegesen fenntartott teljes adagmennyiség. |
| Elérhető tényleges | A tényleges készletben elérhető (nem fenntartott) mennyiség.<p>Az **Elérhető tényleges** lehetőség egy kiszámított mező. Az érték megegyezik a **Tényleges készlet** értékkel, mínusz a **Ténylegesen lefoglalt** érték.</p> |
| Elérhető tényleges többletdimenziók | A rácsban megjelenő összes dimenzióhoz elérhető tényleges mennyiség. |
| Összes rendelés | A bejövő rendelésekben szereplő teljes pozitív mennyiség vagy azok, amelyek különböző készletnaplókban pozitív mennyiséggel rendelkeznek. |
| Megrendelt | A kimenő rendelésekben szereplő teljes pozitív mennyiség vagy azok, amelyek különböző készletnaplókban negatív mennyiséggel rendelkeznek. |
| Rendelt, lefoglalt | A megrendelt bevételezéseken lefoglalt teljes mennyiség. Az ebben a mezőben szereplő érték a kimenő tranzakciók azon cikkeinek teljes mennyiségét jeleníti meg, amelyek állapota _Rendelt, lefoglalt_. A rendelt, lefoglalt cikkek ténylegesen nem érhetők el a készletben. Ezért nem lehet őket közvetlenül kitárolni és szállítani. |
| Foglalásra elérhető | A lefoglalható aktuális készlet teljes mennyisége.<p>**Megjegyzés:** Ha a **Készlet-és raktárkezelési paraméterek** lapon be van jelölve a **Rendelt, lefoglalt cikkek** jelölőnégyzet, akkor a mező értéke a várható bevételezéseket is tartalmazza. Ha törli a jelet a jelölőnégyzetből, akkor az érték nem tartalmazza a várható bevételezéseket.</p> |
| Összes rendelkezésre álló | A teljes elérhető mennyiség.<p>A **Teljes elérhető** lehetőség egy kiszámított mező. összesenAz érték egyenlő az **Elérhető tényleges** értékkel, plusz a **Megrendelve összesen**, mínusz a **Rendelésben lévő** érték.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>Szűrők alkalmazása a keresett rekordok megtalálásához

Használja a **Szűrők** lehetőséget az ablaktáblán az aktuális készletlista szűréséhez, hogy csak olyan rekordokat tartalmazzon, amelyeknél a mezőértékek megfelelnek a szűrési feltételeknek. A szűrő meghatározásához tegye a következőket.

1. A **Szűrők** ablaktáblában keresse meg a szűrni kívánt mezőt.
2. A cél mező neve alatti mezőben válasszon ki egy logikai operátort (például *így kezdődik*, *egyenlő*, vagy *nagyobb, mint*).
3. Adja meg vagy válassza ki a keresendő értéket.

> [!IMPORTANT]
> Az **Aktuális lista** lap egy részletes aktuális készlettáblából van összeállítva, amely az összes elérhető dimenziót tartalmazza. A lap listája azonban összesítés jellegű. Így előfordulhat, hogy a forrástábla sorait egyesíti a megjelenített dimenzióknak megfelelő értékek összesítésével.
>
> A **Szűrők** ablaktáblában meghatározott szűrők a forrástáblára vonatkoznak, nem az összesített listára. Ez a viselkedés esetenként váratlan eredményeket hozhat. Ha további tájékoztatást szeretne arról, hogy ez a viselkedés milyen hatással lehet az eredményekre, tekintse meg a [Példák](#examples) lehetőséget a témakör későbbi részében.
> 
> A rácsban megadott [szűrők azonban](#grid-filters) *vonatkoznak* az összesített listára. Ezek a szűrők egyaránt tartalmazzák a rács felső részén található GyorsSzűrő, valamint az egyes oszlopok fejlécének szűrőjét.

A **Szűrők** ablaktáblában elérhető szűrőkészletet a következő lépésekkel módosíthatja.

- Ha törölni szeretne egy szűrőt az ablaktáblából, akkor válassza a **Bezárás** gombot (**X**).
- Szűrő hozzáadásához válassza a **Szűrők** ablaktábla felső részén lévő **Hozzáadás** lehetőséget. A megjelenő **Szűrőmezők hozzáadása** párbeszédpanel megjeleníti az elérhető mezők listáját. Illetve megjeleníti az egyes mezők adattípusának és táblájának adatait is. Az oszlopfejlécek segítségével szükség szerint szűrheti és rendezheti a listát, majd bejelölheti a jelölőnégyzetet minden olyan mezőnél, amelyet hozzá szeretne adni a **Szűrő** ablaktáblához. Ha befejezte, válassza a **Beszúrás** lehetőséget a módosítások alkalmazásához.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>Válassza ki, hogy mely dimenziók jelenjenek meg

A dimenziók ismertetik az aktuális készletlistán lévő egyes cikkeket, és több lehetőséget kínálnak a lista rendezésére és szűrésére. A megjelenítendőként kiválasztott dimenziók az **Aktuális lista** lapon lévő sorok összesítésének módját is befolyásolhatják. Ez az összesítés viszont hatással lehet arra, hogy a forrástáblák sorai hogyan lesznek összesítve a megjelenített eredményekben. Ha további tájékoztatást szeretne arról, hogy ez a viselkedés milyen hatással lehet az eredményekre, tekintse meg a [Példák](#examples) lehetőséget a témakör későbbi részében.

A megjelenő készletdimenziók beállításának személyre szabásához kövesse az alábbi lépéseket.

1. A Műveleti ablaktáblán válassza a **Dimenziók** elemet.

    A megjelenő **Dimenzió megjelenítése** párbeszédpanel minden dimenziót megjelenít.

2. Jelölje be mindegyik rácsban szerepeltetni kívánt dimenzió jelölőnégyzetét.
3. Ha azt szeretné, hogy a beállítást a rendszer alapértelmezés szerint használja az **Aktuális lista** lap következő megnyitásakor, akkor állítsa a **Beállítás mentése** lehetőséget **Igen** értékre. Ha ezt a lehetőséget **Nem** értékre állítja, akkor a program csak az aktuális munkamenet során fogja használni a beállítást. Ezért a lap következő megnyitásakor rendszer a jelenlegi alapértelmezett beállítást fogja használni.
4. Az **OK** gombra kattintva bezárja a párbeszédpanelt, és alkalmazza a módosítást.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>Szűrjön a készlet aktuális listájának kimenetére

Válassza ki bármelyik az oszlop fejlécét az **Aktuális** rácsban, hogy az oszlopban szereplő értékek alapján rendezzen vagy szűrjön. A rács felső részén található GyorsSzűrő további szűrési beállításokat biztosít. Ezek a szűrők az eredményekre vonatkoznak, nem pedig a forrástáblákra. Ha további tájékoztatást szeretne arról, hogy ez a viselkedés milyen hatással lehet az eredményekre, tekintse meg a [Példák](#examples) lehetőséget a témakör későbbi részében.

> [!NOTE]
> Nem szűrheti és rendezheti az összes oszlopot. A legtöbb mennyiségi oszlop nem tartalmaz rendezési és szűrési vezérlőket, mivel ezek kiszámított mezők. A **Rendelésben lévő** oszlop kivétel.

## <a name="examples"></a><a name="examples"></a>Példák

A rendszer tartalmaz egy részletes (nem összesített) készlettáblát, amely a következő aktuális készletet jeleníti meg.

| Cikkszám | Webhely | Raktár | Tényleges készlet | Elérhető tényleges |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>1. eset

Az **Aktuális lista** lap úgy van beállítva, hogy a következő végső dimenziókat jelenítse meg:

- Cikkszám
- Webhely
- Raktár

A **Szűrők** ablaktáblában a következő szűrési feltételek vannak beállítva:

- A **cikkszám** \| **pontosan** \| _IA0001_
- Az **Elérhető tényleges** \| **érték kevesebb, mint vagy egyenlő ezzel:** \| _1_

Ez az eredményül kapott kimenet.

| Cikkszám | Webhely | Raktár | Tényleges készlet | Elérhető tényleges |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>2. eset

Az **Aktuális lista** lap úgy van beállítva, hogy a következő végső dimenziókat jelenítse meg:

- Cikkszám
- Webhely

A **Szűrők** ablaktáblában a következő szűrési feltételek vannak beállítva:

- A **cikkszám** \| **pontosan** \| _IA0001_
- Az **Elérhető tényleges** \| **érték kevesebb, mint vagy egyenlő ezzel:** \| _1_

Ez az eredményül kapott kimenet.

| Cikkszám | Webhely | Tényleges készlet | Elérhető tényleges |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

Ne felejtse el, hogy a **Szűrők** ablaktábla beállításai a jelen szakasz elején látható részletes (nem összesített) készlettáblára vonatkoznak. Ezért az **Elérhető tényleges** \| **érték kevesebb, mint vagy egyenlő ezzel:** \| _1_ az ablaktábla két sorát találja meg (az első és a harmadik sorokat, amelyek mindegyike az _1_ értékű **Elérhető tényleges** lehetőséget mutatja). Ebben a forgatókönyvben azonban a **Tényleges lista** lap nem arra van beállítva, hogy a **Raktár** dimenziót megjelenítse. Ennek megfelelően összesíti a két eredeti sort egyetlen eredményként kapott sorba, mivel mindkét sorban ugyanaz a érték szerepel a megjelenített dimenzióknál. Ez a sor úgy tűnik, hogy sérti a szűrési feltételeket, mivel az **Elérhető tényleges** érték _2_. Az eredmény azonban helyes, mivel a **Szűrők** ablaktábla beállításai a forrástáblára vonatkoznak, nem pedig az **Aktuális lista** lapon megjelenített összesített táblára.
