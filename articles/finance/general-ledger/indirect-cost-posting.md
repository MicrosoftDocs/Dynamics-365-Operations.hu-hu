---
title: Közvetett költség feladása
description: Ez a témakör leírja, hogyan lehet közvetett költségeket fel adni, költségcsoportokat létrehozni, és csomópontokat hozzáadni a közvetett költségek költségszámítási táblázatában.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostSheetDesigner, BOMCostGroup, ProjCategory, CostingVersion, CostSheetCalculationFactor
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d7f4753f69d83d172993e1c9b04be2220fdf253f
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804639"
---
# <a name="indirect-cost-posting"></a>Közvetett költség feladása

A közvetett költségek olyan költségek, amelyek nem kapcsolódnak közvetlenül a termelési folyamat egyetlen tevékenységéhez sem. Adminisztratív költségek lehetnek például az alkalmazottak bére, a könyvelési részleg költségei és a járulékos költségek (például bérlet, közüzemi szolgáltatások és gépek költségei).

## <a name="calculating-indirect-costs"></a>Közvetett költségek számítása

Microsoft Dynamics 365 Pénzügy – nincs automatikus mód a közvetett költségek díjának kiszámítására. Meg kell határozni a közvetett költségeket, közvetettköltség-kódokat kell létrehozni, és a költségszámítási táblázatban meg kell tartani az egyes közvetett költségek díjszámítását.

A közvetett költségek kiszámítására használt pontos eljárás vállalatonként és vállalatonként kis mértékben eltérő lehet. A folyamat azonban általában a következő alapvető lépésekből áll:

1. A termelésben elismerhető közvetett költségek listájának létrehozása. Ez a lista lehet bérlet, adminisztratív költségek, könyvelési díjak és jogi díjak. Nem tartalmazhat a termelési útvonalakban elismert nyersanyag- vagy munkaköltségeket.
2. Összes közvetett költség összegzése. Csoportosíthatja a hasonló típusú közvetett költségeket, vagy elválaszthatja őket egymástól. Minden beállított közvetett költséghez különböző fő számlák is beállíthatók, amelyek a főkönyvbe való feladáshoz használatosak.
3. A közvetett költségek összehasonlítása egy tényezővel, amelynek más néven a költségelnyelés a alapja. A tényező bármi lehet, amit kiválaszt. Íme néhány példa:

    - Bevétel
    - Összes termelt mennyiség
    - Beállítási idő
    - Lefutási idő

    Kiválaszthatja, hogy milyen időszakra szeretné kiszámítani a közvetett költségeket, például havi, negyedéves vagy éves. A közvetett költségek és a tényezőösszegek összegének ugyanannak az időnek kell lennie. A közvetett költség díjának kiszámítása a következő képlettel történik:

    *Közvetett költségarány* = *Teljes közvetett költségköltség összesen tényezője*&divide;*·*

4. Közvetett költségcsoportok létrehozása.
5. Állítsa be a költségszámítási táblázatot a díjmértékekkel.
6. A költségszámítási verzióban a közvetett költségek költségének karbantartása.

> [!NOTE]
> A költségkönyvelési **modul** segítségével halmozott költségeket lehet felhalmozni, és különböző forrásokból, például termelésből, projektekből és a főkönyvből lehet meghatározni a többletköltségeket. A további tudnivalókat lásd: [Költségkönyvelés](/cost-accounting/cost-accounting-home-page.md).

> [!IMPORTANT]
> Különböző hatósági létesítményekben közzétették az olyan költségtípusokra vonatkozó útmutatást, amelyek közvetett költségként vagy járulékos költségként szerepeltetheti a késztermékek költségét. Mielőtt elkezdené konfigurálni a közvetett költségeket, javasoljuk, hogy ellenőrizze könyvelőjével és a helyi szabályozásokkal, hogy megfeleljenek a követelményeinek.

## <a name="create-cost-groups-for-indirect-costs"></a>Költségcsoportok létrehozása közvetett költségekhez

A közvetett költségekhez legalább egy költségcsoportot létre kell hoznia. Nincs korlátozva a használható költségcsoportok száma. Fontolja meg a költségek kiszámításának a mikéntjét, és azt, hogy a különböző típusú költségekre eltérő díjak vannak-e megszabadulva. A szervezet például élelmiszertermékeket gyárt. Egyes nyersanyagok és késztermékek szárítási áruk, és közvetett költséggel készülnek a raktározáshoz. Az egyéb nyersanyagok és késztermékek költségei magasabbak, ezért magasabb a költségük. Ebben az esetben érdemes két költségcsoportot létrehozni: **·** **a szárítási anyag-járulékos és az áttolt anyag-járulékos költségeket.**

A következő lépések szerint hozhatja létre a közvetett költségek költségcsoportját.

1. Ugrás a Gyártásvezérlés beállítási **útvonalai &gt;&gt; költségcsoporthoz&gt;.**
2. Csoport **létrehozásához válassza az Új** lehetőséget.
3. A Költségcsoport **mezőbe** írja be a költségcsoport egyedi nevét, **például MAT MATH**.
4. A Név **mezőbe** írja be a költségcsoport leírását, például: **Anyagköltségek**.
5. A Költségcsoport **típusa mezőben** válassza a Közvetett **lehetőséget**.
6. Nem kötelező: A Viselkedés mezőben **válassza** a Fix **költség** vagy a Változó **költség lehetőséget**.

## <a name="configure-the-costing-sheet-for-indirect-costs"></a>A közvetett költségek költségszámítási táblázatának konfigurálása

Miután létrehozott egy vagy több költségcsoportot, konfigurálhatja a költségszámítási táblázatot a közvetett költségekkel, és meghatározhatja a számítást. Előfordulhat, hogy csoportosítja a közvetett költségeket a költségszámítási táblázatban. A közvetett költségek csoportosítása érdekében létrehozhat egy tetszőleges fejlécet a költségszámítási táblázatban. A költségszámítási táblázatban minden költségcsoporthoz létre kell hoznia legalább egy csomópontot. A közvetett költségek mindegyik költségcsoportja számára hozzá lehet adni még egy közvetett költségszámítást.

### <a name="indirect-cost-node-types"></a>Közvetettköltség-csomópont típusai

Ez a szakasz a közvetett költségek csomópontjainak különböző típusait írja le.

#### <a name="surcharge"></a>Pótdíj

**A** pótdíj az egyik leggyakoribb közvetettköltség-típus. A költség százalékos hányadát a termelési rendelés költségeinek teljes költségszámítása alapján számítja ki. A teljes költségösszetevő a költségszámítási táblázatban az anyag- vagy időösszetevőkhöz kapcsolt költségcsoportok kiválasztásával határozható meg.

Például egy termelési rendelés minden nyersanyagának termelési költségére egy 3 százalékos pótdíjat lehet hozzáadni.

#### <a name="rate"></a>Díj

A Díj típusú **közvetett** költségek segítségével a termelési rendeléshez hozzáadható egy rögzített költségösszeg a termelési rendelés költségeinek teljes költségösszege alapján. A díj három altípuson alapulhat:

- **Folyamat** – a díj az útvonal futási ideje alapján történik.
- **Beállítás** – a díj az útvonal beállítási ideje alapján történik.
- **Mennyiség** – a díj a termelt mennyiségen alapul.

A teljes költségszámítás alapja a költségszámítási táblázatban az anyag- vagy időösszetevőkhöz kapcsolt költségcsoportok kiválasztásával határozható meg.

Például minden termelési rendeléshez hozzáadnak egy 2,00 usd értékű rögzített összeget, amely a költségszámítási táblázat munkaköltségcsoportja útvonalán lefutott idő alapján áll rendelkezésre.

#### <a name="output-unit-based"></a>Kimeneti egységen alapuló

A Kimeneti egység **alapú** **közvetett** költség kiszámítása a költségszámítási táblázat Díj gyorslapján megadott összeg és a kiválasztott altípus szorzószámával történik. A késztermék mennyisége, súlya és térfogata választható ki a közvetett költség szorzójaként.

A mennyiséget például az egyes termelt 1.50 USD gépi értékcsökkenés kiszámítására használhatja. Másik példaként a térfogat segítségével kiszámítható 2.00 USD térfogata arra a térfogatra, a helyet, amit a késztermékek a leásási egységekben kivesznek.

#### <a name="input-unit-based"></a>Bemeneti egységen alapuló

A Bemeneti egység típusú **közvetett** költség a termelési rendelésben felhasznált nyersanyagok összegének és egy összegnek a szorzója. A teljes számításhoz a termelési rendelés bemenetei súlyát vagy térfogatát használhatja. A számítást egy **rész** anyagkészletre korlátozhatja, ha kiválaszt egy vagy több költségcsoportot a költségszámítási táblázat Teljes költséglapján.

Például egy olyan költségcsoport bejövő mennyiségének használata esetén, amely leselkedt termékekhez kapcsolódik, 1.00 USD termelési rendeléshez.

### <a name="create-a-total-node-for-indirect-costs-in-the-costing-sheet"></a>Összcsomópont létrehozása a közvetett költségekhez a költségszámítási táblázatban

A költségszámítási táblázatban a közvetett költségek csomópontjának létrehozásához kövesse ezeket a lépéseket.

1. Ugrás a Költséggazdálkodás **közvetettköltség-könyvelési &gt; irányelveinek beállításához: &gt; Költségszámítási táblázat**.
2. A fában válasszon ki egy csomópontot, amely a legyártott áruk költségét ábrázolja.
3. Csomópont **létrehozásához válassza az Új** lehetőséget.
4. A Csomóponttípus **kiválasztása mezőben** válassza az Összesen **lehetőséget**.
5. A Kód **mezőbe** írja be a csomópont egyedi azonosítóját, **például a termelési járulékos költségeket**.
6. Jelölje be a **Fejléc** jelölőnégyzetet.
7. Jelölje be az **Összesítés** jelölőnégyzetet.
8. Válassza ki az **OK** lehetőséget.

### <a name="create-an-indirect-cost-group-node-in-the-costing-sheet"></a>Közvetett költségcsoport csomópontjának létrehozása a költségszámítási táblázatban

A következő lépésekkel lehet közvetettköltségcsoport-csomópontot létrehozni a költségszámítási táblázatban.

1. Ugrás a Költséggazdálkodás **közvetettköltség-könyvelési &gt; irányelveinek beállításához: &gt; Költségszámítási táblázat**.
2. A fában válassza ki azt a csomópontot, amely alá közvetett költséget szeretne létrehozni. Például válassza ki a termelési többlet összesítő **csomópontját**.
3. Csomópont **létrehozásához válassza az Új** lehetőséget.
4. A Csomóponttípus **kiválasztása mezőben** válassza a Költségcsoport **lehetőséget**.
5. A Kód **mezőbe** írja be a csomópont egyedi azonosítóját, például **a TRANSP azonosítót**.
6. A Leírás **mezőbe** írja be a rövid leírást, például Szállítási **többlet**.
7. Válassza ki az **OK** lehetőséget.
8. A Költségcsoport **mezőben** válassza ki a költségcsoportot, **például IVANH1: Szállítási többlet**.

### <a name="create-a-surcharge-indirect-cost"></a>Pótdíj közvetett költségének létrehozása

A költségszámítási táblázatban pótdíj közvetett költségének létrehozásához kövesse ezeket a lépéseket.

1. Ugrás a Költséggazdálkodás **közvetettköltség-könyvelési &gt; irányelveinek beállításához: &gt; Költségszámítási táblázat**.
2. A fában válassza ki azt a közvetett költségcsoport-csomópontot, amely alá közvetett költséget szeretne létrehozni. Például válassza ki a TRANSP - Szállítási többlet összesítő **csomópontját**.
3. Csomópont **létrehozásához válassza az Új** lehetőséget.
4. A Csomóponttípus **kiválasztása mezőben** válassza a Pótdíj **lehetőséget**.
5. A Kód **mezőbe** írja be a csomópont egyedi azonosítóját, **például Szállítási pótdíj**.
6. Válassza ki az **OK** lehetőséget.
7. Az Altípus **mezőben** válassza az Összesítés **lehetőséget**.
8. Költségkód **létrehozásához válassza** az Új **lehetőséget** a Teljes költségkönyvelési alap gyorsgombra.
9. A Kód **mezőben** válassza ki a pótdíj kiszámításához használni kívánt költségcsoportot.
10. Nem kötelező: Ismételje meg a 8–9. lépést minden további költségcsoportra, amely a számításhoz szükséges.
11. Díj létrehozásához **válassza** a Pótdíj gyorstárat az Új **gombra**.
12. A Verzió **mezőben** válassza ki azt a költségszámítási verziót, amelybe fel kell adni a pótdíjat.
13. Nem kötelező: A Hely **mezőben** adja meg azt a helyet,re alkalmazni kell a pótdíjat.
14. A Százalék **mezőben** adja meg, **hogy** a program hány százalékot számítson a termelési rendeléseken a Teljes költség alapja gyorstáraban megadott költségcsoportok alapján.
15. A Főkönyvi feladások gyorsoldalon válassza ki a fő számlát a becsült közvetett költség által felhasználva, **a felhasznált közvetett költségek becsült költségéhez,** a folyamatban lévő költségekkel, **·** **a** közvetett költségek felhasználva és a felhasznált közvetett költségek költségével kapcsolatos mezőkhöz.**·** **·**
16. Nem kötelező: A Pénzügyi dimenziók **gyors** oldalon adja meg azokat a pénzügyi dimenziókat, amelyet alapértelmezés szerint meg kell adni a tranzakciókhoz a főkönyvbe való feladáskor.

Az előző művelet bemutatja, hogyan lehet közvetett költséget létrehozni a Pótdíj **típushoz**. Hasonló lépések segítségével más típusú közvetett költségeket hozhat létre. Az alábbi szakaszok leírják a különbségeket az egyes típusokkal.

#### <a name="rate"></a>Díj

- A 4. lépésben ne **pótdíjat**, hanem díjat **válasszon**.
- A 7. lépésben az Összes helyett válassza **a Folyamat,** **a Beállítás** vagy a **Mennyiség** lehetőséget **.**
- A 11. lépésben a **Pótdíj** gyorsab helyett használja a **Díj** gyorsattintát.
- A 14 **. lépésben adjon meg egy összeget az Összeg** mezőben, nem pedig a Százalék **mezőben**.

#### <a name="output-unit-based"></a>Kimeneti egységen alapuló

- A 4. lépésben pótdíj helyett válassza **ki** a Kimeneti egység **beállítását**.
- A 7. lépésben az Összes helyett válassza **a** Mennyiség, **a** **Súly vagy a Térfogat** **lehetőséget**.
- 8–10. lépés kihagyása.
- A 11. lépésben a **Pótdíj** gyorsab helyett használja a **Díj** gyorsattintát.

#### <a name="input-unit-based"></a>Bemeneti egységen alapuló

- A 4. lépésben pótdíj helyett válassza **ki** a Bemeneti egység **beállítását**.
- A 7. lépésben az Összesítés **helyett** **válassza** a Súly vagy a **Térfogat lehetőséget.**
- A 11. lépésben a **Pótdíj** gyorsab helyett használja a **Díj** gyorsattintát.
