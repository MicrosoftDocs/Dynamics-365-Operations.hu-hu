---
title: Termékekben, megrendelésekben, szállítmányokban és rakományokban lévő veszélyes anyagok
description: Ez a témakör azt mutatja be, hogyan kell megadni a kiadott termékekhez tartozó veszélyes anyagok jellemzőit, a veszélyes cikkekre vonatkozó készlet korlátozását, valamint a veszélyes anyagok értékesítési rendelésbe, szállítmányba vagy rakományba történő felvételének módját.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 0bf4ff2188d98adb0052e40a77ff899d4da28063b042947bf124042dfa3fb8cd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758520"
---
# <a name="hazardous-materials-in-products-orders-shipments-and-loads"></a>Termékekben, megrendelésekben, szállítmányokban és rakományokban lévő veszélyes anyagok

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kell megadni a kiadott termékekhez tartozó veszélyes anyagok jellemzőit, a veszélyes cikkekre vonatkozó készlet korlátozását, valamint a veszélyes anyagok értékesítési rendelésbe, szállítmányba vagy rakományba történő felvételének módját.

## <a name="set-hazardous-material-specifications-for-products"></a>Termékekhez tartozó veszélyesanyag-specifikációk megadása

Miután meghatározott egy veszélyesanyag-előírást, és a kapcsolódó hivatkozási kódokat beállította a [Veszélyes anyagok beállítása](hazmat-setup.md) című témakörben leírtaknak megfelelően, ezeket az adatokat hozzárendelheti a kiadott cikkekhez. A szállítási dokumentumok szállítási szövege a közzétett cikkek veszélyes anyagokra vonatkozó adataiból fog készülni.

A kibocsátott cikkek veszélyes anyagokhoz való társításának részeként meg kell adnia az előírás kódját és az anyagot. Előfordulhat, hogy a szállítási módoktól függően különböző előíráskódok vannak társítva egy elemhez, és az egyes elemekhez több előírást és anyagkódot lehet társítani.

A kiadott termék veszélyes anyagként való beállításához hajtsa végre az alábbi lépéseket.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válasszon ki vagy hozzon létre egy terméket, és nyissa meg a **Kapcsolódó termékadatok** oldalát.
1. A **Készletkezelés** gyorslapon állítsa a **Veszélyes anyag** beállítást **Igen** értékre. Ez a beállítás veszélyes áruként azonosítja a tételt, és akkor használatos, ha a szállítási dokumentáció ki van nyomtatva.
1. A Műveleti panelen, a **Készletkezelés lapon** a **Megfelelés** csoportban válassza a **Cikk veszélyes anyag** lehetőséget.
1. Töltse ki a kiválasztott tételhez tartozó **Cikkek veszélyes anyagai** lapot a következő alszakaszokban ismertetett mezők használatával.

### <a name="item-hazardous-materials-header"></a>Cikk veszélyes anyagai fejléce

A következő táblázat felsorolja azokat a mezőket, amelyek a **Cikk veszélyes anyagai** lapjának tetején érhetők el.

| Mező | Leírás |
|---|---|
| Cikkszám | A közzétett termék, amellyel dolgozik. |
| Szabályozás kódja | A termékre vonatkozó veszélyes anyagokra vonatkozó előírás kiválasztása. Az előírás határozza meg, hogy hogyan jön létre a nyomtatott szállítási szöveg a cikkhez és a hozzá tartozó szállítási módok számára. A hozzárendelés után a kód nem szerkeszthető ezen a lapon. Új előíráskódot azonban úgy rendelhet hozzá, hogy kiválasztja az **Új** lehetőséget. |
| Anyag kódja | (Opcionális) A termékre vonatkozó veszélyes anyagokra vonatkozó kód kiválasztása. Az anyagkód tartalmaz egy sablont, amely a lap számos egyéb mezőjéhez tartalmaz alapértelmezett értékeket. Kód kiválasztása esetén a program az aktuális termékbe másolja a veszélyes anyagokra vonatkozó összes specifikációját. A rendszer azonban először azt kéri, hogy erősítse meg, hogy a cikk anyagadatait ki kell tölteni az anyagkódból. |
| Csoportkód | (Opcionális) A termékre vonatkozó veszélyes anyagokra vonatkozó osztályozási csoport kiválasztása. Az **Anyagkód mezőhöz** hasonlóan a kód kiválasztása esetén a program az aktuális termékbe másolja a veszélyes anyagokra vonatkozó összes specifikációját. A rendszer azonban először azt kéri, hogy erősítse meg, hogy az osztálycsoport anyagadatait ki kell tölteni a csoportkódból. |

### <a name="descriptions-fasttab"></a><a name="hazmat-description"></a>Leírások gyorslap

Az alábbi táblázat bemutatja a **Leírások** gyorslapon rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Megfelelő szállítási név | Írja be az anyag szokásos leírását a vonatkozó rendeletben meghatározott módon. Ennek az értéknek a fordítását a következő szakaszban leírtak szerint lehet megadni a **Cikkek szállítási szövegének fordítása** gyorslapon. |
| Technikai név | Az anyag köznapi vagy általános nevének kiválasztása. Ez a név lehet egy név, amelyet a vállalat belső célokra használ az anyaghoz. |
| Más módon nem specifikus | Ennek a jelölőnégyzetnek a bejelölésével jelezheti, hogy a **Megfelelő szállítási név** értéke más módon nem specifikus szállítási név a cikkhez. Más módon nem specifikus A szállítási neveket olyan hasonló vegyszerek és anyagok csoportjai használják, amelyeknek van meghatározott végfelhasználásuk, de nem szerepelnek név szerint a veszélyesanyag-táblában egy adott előírásban. |

### <a name="item-ship-text-translation-fasttab"></a>Cikk szállítási szövegének fordítása gyorslap

A **Cikk szállítási szövegének fordítása** gyorslap egy rácsot tartalmaz, amely a **Leírás** gyorslap elsődleges nyelvén megadott **Megfelelő szállítási név** értékek fordítását jeleníti meg. Ezek a fordítások a szállítási nyomtatott szövegben egy vagy több további nyelvhez használhatók.

Az alábbi táblázat bemutatja a **Cikk szállítási szövegének fordítása** gyorslapon rendelkezésre álló mezőket.


| Mező | Leírás |
|---|---|
| Nyelv | A sor által használt nyelvkód. A **pt-br** például azt jelzi, hogy a szöveg brazíliai portugál. |
| Szállítás szövege | A lefordított **Megfelelő szállítási név** értéke a sor által használt nyelven. |

Fordítás hozzáadásához vagy szerkesztéséhez válassza a rács feletti **Fordítások** elemet a **Szövegfordítások** oldal megnyitásához. Majd tegye a következők egyikét:

- Új fordítás hozzáadásához a műveleti ablaktáblában válassza ki az **Hozzáadás** lehetőséget. Válassza ki a hozzáadni kívánt nyelvet, majd a **Lefordított szöveg** mezőbe írja be a lefordított szöveget.
- Egy meglévő fordítás szerkesztéséhez válassza ki a kívánt nyelvet a **Nyelv** mezőben, és szükség szerint szerkessze a lefordított szöveget a **Lefordított szöveg** mezőben.

### <a name="material-management-fasttab"></a><a name="material-management"></a>Anyagkezelés gyorslap

Az alábbi táblázat bemutatja a **Anyagkezelés** gyorslapon rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Osztály | Válassza ki, hogy melyik veszélyesanyag-osztályba tartozik a termék ahogyan azt a rendelet meghatározza, amelynek megfelel. A veszélyes anyagokat tartalmazó összes termékhez társítani kell egy divíziót és egy osztályt. |
| Leírás | Az **Osztály** mezőben kiválasztott osztályhoz megadott leírás. Ez a mező csak olvasható. |
| Osztály | Válassza ki, hogy melyik veszélyesanyag-divízióba tartozik a termék ahogyan azt a rendelet meghatározza, amelynek megfelel. A divízió az osztály egy részhalmaza. A veszélyes anyagokat tartalmazó összes termékhez társítani kell egy divíziót és egy osztályt. |
| Azonosítás | A veszélyes anyag azonosítókódjának kiválasztása. Ez a kód általában az Egyesült Nemzetek (ENSZ) szabványán alapuló kód. |
| Csomagolási csoport | Az aktuális cikkre vonatkozó csomagolási csoport kiválasztása. |
| Leírás | Az **Csaomagolási csoport** mezőben kiválasztott csoporthoz megadott leírás. Ez a mező csak olvasható. |
| Csomagolási leírások | Válassza ki a megfelelő csomagolási leírás kódját. Ez a kód olyan leírásra hivatkozik, amely azt jelzi, hogy hogyan kell a terméket csomagolni. |
| Veszélyesanyag-címkék | Válassza ki azt a kódot, amely hivatkozik a termékre alkalmazandó veszélyesáru-címkéjére. |
| Korlátozott mennyiség | Ennek a beállításnak az **Igen** értékre állításával jelentheti az egyes rakományok és az egyes sorokban szereplő teljes termék súlyát. |
| Mennyiség | A veszélyes anyag mennyiségének megadása a termékben, a meghatározott mértékegységben. Ezt az értéket fogja használni a termékhez tartozó rakományok és szállítmányok teljes veszélyességi pontszámának kiszámítására. |
| Szorzó | Adja meg azt a szorzót, amelyet akkor alkalmaz a rendszer, amikor a program a veszélyes anyag pontszámát kiszámítja az egyes, a terméket tartalmazó rakománysorokhoz. Ezt az értéket a vonatkozó rendelet határozza meg a termékben található veszélyes anyag típusának megfelelően. |
| Egység | Válassza ki azt a mértékegységet, amely a termékben található veszélyes anyagok mennyiségére vonatkozik, a **Mennyiség** mezőben meghatározottak szerint. Ezt az értéket fogja használni a termékhez tartozó rakományok és szállítmányok teljes veszélyességi pontszámának kiszámítására. |

#### <a name="how-the-hazardous-material-score-is-calculated"></a>A veszélyesanyag-pontszám kiszámítása

A termék **Anyagkezelés** gyorslapon megadott értékek közül több a termékhez kapcsolódó minden egyes rakományhoz tartozó *veszélyesanyag-pontszám* kiszámítására szolgál. A rendszer a következő képlettel számítja ki a pontszámot:

Veszélyesanyag-pontszám = *&lt;LineQty&gt;* × *&lt;HazmatQty&gt;* × *&lt;UnitConversion&gt;* × *&lt;Szorzó&gt;*

A képlet jelmagyarázata:

- A *&lt;LineQty&gt;* a rakománysorhoz megadott termékmennyiség.
- A *&lt;A HazmatQty&gt;* az a mennyiség, amely a termékhez meg van adva az **Anyagkezelés** gyorslap **Mennyiség** mezőjében.
- A *&lt;UnitConversion&gt;* egy átváltási tényező a rakománysor mennyiségéhez használt mértékegység és a termékhez megadott mértékegység között az **Anyagkezelés** gyorslap **Mértékegység** mezőjében.
- A *&lt;Szorzó&gt;* az a szorzó, amely a termékhez meg van adva az **Anyagkezelés** gyorslap **Szorzó** mezőjében.

Ez a pontszám minden olyan rakománysor esetében jelentve van, amely tartalmaz egy terméket, ahol ezek az értékek meg vannak adva. A további tudnivalókat lásd a [Veszélyes anyagokat tartalmazó szállítmányok](#hazmat-shipments) és a [Veszélyes anyagok szakaszait tartalmazó rakományok](#hazmat-loads) részben a témakör további részében.

#### <a name="how-the-hazardous-material-weight-is-calculated"></a>A veszélyesanyag tömegének kiszámítása

Azon rakományoknál és rakománysoroknál, ahol a **Korlátozott menyiség** beállítás az **Anyagkezelés** gyorslapon **Igen** értékre van állítva, meg lesz jelenítve a veszélyes anyag teljes tömege a [Veszélyes anyagokat tartalmazó szállítmányok](#hazmat-shipments) és [Veszélyes anyagokat tartalmazó rakományok](#hazmat-loads) című későbbi szakaszokban leírtak szerint. A rendszer a következő képlettel számítja ki a veszélyes anyag tömegét:

Veszélyes anyag tömege = *&lt;LineQty&gt;* × *&lt;ProductWeight&gt;* × *&lt;UnitConversion&gt;*

A képlet jelmagyarázata:

- A *&lt;LineQty&gt;* a rakománysorhoz megadott termékmennyiség.
- A *&lt;ProductWeight&gt;* a termékhez megadott nettó tömeg a termékhez megadott készletegységben.
- A *&lt;UnitConversion&gt;* egy átváltási tényező a rakománysornál használt egység és a *&lt;ProductWeight&gt;* helyen használ termékegység között.

### <a name="transport-information-fasttab"></a>Szállítási információk gyorslap

Az alábbi táblázat bemutatja a **Szállítási információk** gyorslapon rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szállítási kategória | Válassza ki a kapcsolódó szállítási kategóriát. |
| Alagútkód | A kapcsolódó alagút-korlátozási kód kiválasztása a cikkhez. |
| Veszélyes anyag rakodása | Válassza ki a tengeri fuvarozáshoz használt hivatkozási kódot, ha a cikk szállítása tengeri fuvarozással történik. |
| Repülőgép típusa | Válassza ki azt a légijármű-korlátozást, amely az anyag légi fuvarozással történő szállítása esetén érvényes. |
| Csomagolás – kizárólag teherszállító repülőgépek | A **Légijármű típusa** mezőben kiválasztott érték alapján válassza ki azt a csomagolási utasítást, amelyet akkor kell alkalmazni, ha a terméket csak teherszállító repülőgépek tudják szállítani. |
| Csomagolás – utasszállító és teherszállító repülőgépek | A **Légijármű típusa** mezőben kiválasztott érték alapján válassza ki azt a csomagolási utasítást, amelyet akkor kell alkalmazni, ha a terméket teherszállító és utasszállító repülőgépek is szállíthatják. |
| IATA-csillag | A beállítás **Igen** értékre állításával jelezheti, hogy az ezen a gyorslapon megadott légiközlekedési specifikációk a Nemzetközi Légifuvarozási Szervezet (IATA) veszélyes áruk szabványához kapcsolódnak. Ez a mező csak tájékoztatásra szolgál. |
| Vészhelyzeti válasz | Válassza ki azt a kódot, amely az anyag vészhelyzetben történő kezeléséhez szükséges utasításokra hivatkozik. |

### <a name="environmental-information-fasttab"></a>Környezeti információk gyorslap

Az alábbi táblázat bemutatja a **Környezeti információk** gyorslapon rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Környezetre veszélyes | Ez a beállítás **Igen** értékre állítható annak jelzésére, hogy a termék veszélyes a környezetre. Ezt a mezőt saját jelentéskészítési célokra használhatja. |
| Tengeri szennyezőanyag | Ez a beállítás **Igen** értékre állítható annak jelzésére, hogy a termék tengeri szennyezőanyag. Ezt a mezőt saját jelentéskészítési célokra használhatja. |

## <a name="set-stock-limits-for-hazardous-products"></a><a name="stock-limits"></a>A veszélyes termékek raktárkészletkorlátainak megadása

Biztonsági okokból előfordulhat, hogy korlátozni kell egy adott termék teljes mennyiségét, amelyet egyetlen helyen lehet tárolni. A kiadott termékekhez tartozó raktározási korlátok beállításához kövesse az alábbi lépéseket.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válasszon ki vagy hozzon létre egy terméket, és nyissa meg a **Kiadott termékadatok** oldalt.
1. A Műveleti panelen, a **Készletkezelés lapon** a **Megfelelés** csoportban válassza a **Jelentés részletei** lehetőséget.
1. A **Veszélyes készlet korlátja** és a **Veszélyes figyelmeztetési határérték** mezőkben adja meg a kiválasztott termék megfelelő értékeit.

A **Veszélyes anyagok készletkorlátozása** jelentéssel nyomon követheti a veszélyes anyagok készletének szintjét a raktári helyeken, hogy az itt meghatározott biztonsági korlátok között maradjon. A további tudnivalókat lásd: [Veszélyes anyagok készletkorlátozása jelentés](hazmat-reports.md#stock-limit-report).

## <a name="sales-order-transactions-that-include-hazardous-materials"></a>A veszélyes anyagokat tartalmazó értékesítési rendelési tranzakciók

Ha egy értékesítési rendelésben veszélyes anyagként minősített terméket szeretne szerepeltetni, akkor a kapcsolódó szállítmányozót az értékesítési rendeléshez kell társítania. Nyissa meg az értékesítési rendelést, majd a **Szállítás** gyorslapon szükség szerint állítsa be a **Szállítmányozó** és **Szállítmányozói szolgáltatás** mezőit.

A szállítmányozó a szállítási módhoz is társítva van. Ezért gondoskodni kell arról, hogy ez az információ a veszélyes anyagokkal kapcsolatos rendelethez igazodjon. Más szóval a veszélyes anyagokkal kapcsolatos rendeletben megadott szállítási módnak egyeznie kell az értékesítési rendelés fejlécében szereplő adatokkal. Ily módon a rendelet, a szállítmányozó és a szolgáltatás az értékesítési rendelésen használt szállítási sorokhoz kapcsolódik.

Miután egy értékesítési rendelést véglegesítettek, és készen áll a szállításra, fel lehet adni a raktárba, hogy jelezze az értékesítési és raktári műveletek közötti átmozgatást.

## <a name="shipments-that-include-hazardous-materials"></a><a name="hazmat-shipments"></a>Veszélyes anyagokat tartalmazó szállítmányok

### <a name="view-hazardous-material-scores-for-each-shipment-line"></a>Az egyes szállítási sorokhoz tartozó veszélyesanyag-pontszám megtekintése

A szállítmány **Szállítmány részletei** lapján látható a szállítmányban szereplő minden egyes rakománysorhoz kiszámított teljes veszélyesanyag-tömeg és -pontszám. A pontszámok és tömegek megtekintéséhez kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Válasszon ki egy szállítmányt a **Szállítmány részletei** lapjának megnyitáshoz.
1. A **Rakománysorok** gyorslapon ellenőrizze a sorokat. Mindegyik sorhoz a veszélyes anyagokkal kapcsolatos számításokat a következő mezőkben tekintheti meg:

    - **Veszélyesanyag-pontszám** – Ez a mező a rakománysorhoz tartozó veszélyesanyag-pontszámot jeleníti meg. Az érték számítása a vonatkozó rendeletnek és a kiadott termék beállításaihoz meghatározott szabályok és értékek alapján történik. A számítás a terhelési sorban szereplő mennyiséget veszi figyelembe, és a szorzót használja az [anyagkezelés beállítása](#material-management) szakaszból a kiadott termékhez.
    - **Korlátozott mennyiség nettó tömege** – A veszélyesanyag-tartalmuk miatt korlátozott mennyiségű termékekként megjelölt termékek esetében ez a mező megjeleníti a veszélyes anyag teljes tömegét, amit a rakománysor tartalmaz. A számítás a kiadott termék beállításaiban a veszélyes anyagokként feltüntetett termékek alapján történik. Ha egy cikk korlátozott mennyiségű cikkként van megjelölve, akkor a számítás figyelembe veszi a mennyiséget minden egyes rakománysorban, és hivatkozik a kiadott termékhez tartozó tömegre az [anyagkezelés beállítása](#material-management) részben.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-shipment"></a>Szállítmányban található veszélyes anyagok kompatibilitásának ellenőrzése

A rendszer képes értékelni, hogy a szállítmányban szereplő összes veszélyes anyag szállítható-e együtt. A kompatibilitás kiértékelése érdekében a rendszer ellenőrzi a szállítmányban szereplő egyes termékekhez rendelt kompatibilitási csoportot. A további tudnivalókat lásd: [Veszélyes anyagok kompatibilitási csoportjai](hazmat-setup.md#compatibility-groups).

A kompatibilitási ellenőrzés futtatásához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Válasszon ki egy szállítmányt a **Szállítmány részletei** lapjának megnyitáshoz.
1. A műveleti ablakban a **Szállítmányok** lapon a **Műveletek** csoportban válassza a **Kompatibilitás ellenőrzése** lehetőséget.

Egy üzenet jelenik meg, amely tájékoztat az ellenőrzés eredményeiről.

## <a name="loads-that-include-hazardous-materials"></a><a name="hazmat-loads"></a>Veszélyes anyagokat tartalmazó rakományok

### <a name="view-hazardous-material-scores-for-each-load-line"></a>Az egyes rakománysorokhoz tartozó veszélyesanyag-pontszám megtekintése

A rakomány **Rakomány részletei** lapján látható a rakományban szereplő minden egyes rakománysorhoz kiszámított teljes veszélyesanyag-tömeg és -pontszám. A pontszámok és tömegek megtekintéséhez kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden rakomány** elemhez.
1. Válasszon ki egy rakományt a **Rakomány részletei** lapjának megnyitáshoz. (A rakomány adatait úgy is megnyithatja, hogy kijelöl egy hivatkozást a kapcsolódó szállítmányból.)
1. A **Rakomány** gyorslapon a teljes rakomány teljes veszélyesanyag-pontszámát és -tömegét a következő mezők vizsgálatával ellenőrizheti:

    - **Veszélyesanyag-pontszám** – Ez a mező a rakományhoz tartozó veszélyesanyag-pontszámot jeleníti meg. Az érték számítása a vonatkozó rendeletnek és a kiadott termék beállításaihoz meghatározott szabályok és értékek alapján történik. A számítás a rakományban szereplő mennyiséget veszi figyelembe, és a szorzót használja az [anyagkezelés beállítása](#material-management) szakaszból a kiadott termékhez.
    - **Korlátozott mennyiség nettó tömege** – A veszélyesanyag-tartalmuk miatt korlátozott mennyiségű termékekként megjelölt termékek esetében ez a mező megjeleníti a veszélyes anyag teljes tömegét, amit a rakomány tartalmaz. A számítás a kiadott termék beállításaiban a veszélyes anyagokként feltüntetett termékek alapján történik. Ha egy cikk korlátozott mennyiségű cikkként van megjelölve, akkor a számítás figyelembe veszi a mennyiséget minden egyes rakományban, és hivatkozik a kiadott termékhez tartozó tömegre az [anyagkezelés beállítása](#material-management) részben.

1. Az egyes sorokhoz tartozó pontszámok és súlyok áttekintéséhez válassza a **Rakománysorok** gyorslapot. Az egyes sorokhoz megadott értékek hasonlítanak a teljes rakományhoz megadott értékekre, az előző lépésben leírtak szerint.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-load"></a>A Rakományban található veszélyes anyagok kompatibilitásának ellenőrzése

A rendszer képes értékelni, hogy a rakományban szereplő összes veszélyes anyag szállítható-e együtt. A kompatibilitás kiértékelése érdekében a rendszer ellenőrzi a rakományban szereplő egyes termékekhez rendelt kompatibilitási csoportot. A további tudnivalókat lásd: [Veszélyes anyagok kompatibilitási csoportjai](hazmat-setup.md#compatibility-groups).

A kompatibilitási ellenőrzés futtatásához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden rakomány** elemhez.
1. Válasszon ki egy szállítmányt a **Rakomány részletei** lapjának megnyitáshoz. (A rakomány adatait úgy is megnyithatja, hogy kijelöl egy hivatkozást a kapcsolódó szállítmányból.)
1. A műveleti ablakban a **Rakományok** lapon a **Műveletek** csoportban válassza a **Kompatibilitás ellenőrzése** lehetőséget.

Egy üzenet jelenik meg, amely tájékoztat az ellenőrzés eredményeiről.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]