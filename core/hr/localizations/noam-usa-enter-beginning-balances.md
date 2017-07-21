---
title: "Adja meg a bérlista nyitó egyenlegeit"
description: "A témakör a nyitó egyenlegek bevitelének lépéseit ismerteti a kereseti kódok, levonások, juttatások és adók esetében. Ez az információ értékes a partnerek számára az adatok áttelepítéséhez vagy átviteléhez egy új Bérlista rendszerbe egy másik rendszerből."
author: kherr
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 911a51e2498800e7ee7b1562b66c56967eef0505
ms.openlocfilehash: e6213d2e01445b78c6d8f98fc6a55f7c551231b5
ms.contentlocale: hu-hu
ms.lasthandoff: 06/19/2017


---

# <a name="enter-payroll-beginning-balances"></a>Adja meg a bérlista nyitó egyenlegeit

[!include[banner](../../includes/banner.md)]]

A témakör a nyitó egyenlegek bevitelének lépéseit ismerteti a kereseti kódok, levonások, juttatások és adók esetében. Ez az információ értékes az olyan partnerek számára, akik adatokat telepítenek át vagy visznek át egy új Bérlista rendszerbe egy másik rendszerből. A nyitó bérlistaegyenlegek bevitelének előkészítéseként ellenőrizzük az alábbi információkat:

> * Az alkalmazotti rekordok meg vannak adva és elérhetők a rendszerben
> * Az alábbi adatok be vannak állítva és hozzá vannak rendelve az alkalmazottakhoz:

> > * Fizetési ciklusok és fizetési időszakok
> > * Bevételkódok
> > * Adók
> > * Juttatások és levonások

> * A vállalatnak ki kellett volna választania egy dátumot, amelyen megadhatók a nyitó bérlistaegyenlegek.

> * A korábbi rendszerből összegyűjtött adatok minden bevételről, juttatásról és levonásról, juttatások hozzájárulásairól, alkalmazott által fizetendő adóról, munkáltatói adóról és ezek folyó évi összegeiről.

A nyitó egyenleg bevitelének tervezésekor fontolja meg, hogy mennyire kell részletesnek lenniük az adatoknak. A vállalkozások többsége egyetlen, összevont, a folyó évben az adott dátumig számolt összeget ad meg. Ha azonban részletesebb információkra van szükség, az egyenlegek negyedéves lépésekben is bevihetők. A szükséges részletességi szinttel kapcsolatos döntés határozza meg, hogy hány manuális fizetési kimutatást kell létrehozni minden dolgozóhoz. Csak egy manuális kimutatásra van szükség minden egyes alkalmazott esetében, ha egyetlen év az aktuális dátumig összeget visznek be. Ehhez a korábbi rendszerből származó végső fizetési kimutatás év az aktuális dátumig összegeit kell bevinni az új bérszámfejtő rendszerbe.

A következő példa bemutatja, hogyan lehet bevinni az alkalmazotti bérlista-nyitóegyenlegeket, beleértve a kereseti kódokat, a juttatásokat és levonásokat, valamint az adókat. Egy való életből vett példában minden egyes bevitt kereseti kódról, juttatás levonásairól, juttatás hozzájárulásairól, alkalmazott által fizetendő adóról és munkáltatói adóról lenne egy sortétel az év az aktuális dátumig összeggel. Használja a kódok és az összegek listáját, és kövesse a kereseti és kifizetési kimutatás manuális létrehozásának lépéseit kikapcsolt könyvelés mellett a nyitó egyenlegek bérszámfejtés céljára való átviteléhez.  A könyvelést le kell tiltani, mivel nem szeretnénk feladni a főkönyvbe a nyitó egyenleg fizetési kimutatását. Ez a korábbi rendszerben készült, és az új rendszerbe a nyitó egyenlegeknek a főkönyvben való beállításakor kerül át.

> [!NOTE] 
> Ha szeretné megismételni az alábbi lépéseket, használhatja a bemutató adatokat. A bemutató adatok letöltésére a PartnerSource nyújt lehetőséget

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a>A. Hogyan kell beállítani a bevételkódokat nyitó bérlista egyenlegekhez való használathoz
Amikor megadja a nyitó bérlistaegyenlegeket, győződjön meg arról, hogy a használni kívánt bevételkódok a „Kereseti kimutatási mértékek szerkesztésének engedélyezése” beállítás engedélyezésével vannak konfigurálva. Ez lehetővé teszi, hogy manuálisan írja be az összeget a korábbi rendszerből. 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a>B. Kereseti kimutatás létrehozása az alkalmazotthoz a nyitó egyenleg létrehozásához
Ez a lépés manuálisan hoz létre kereseti kimutatást minden dolgozóhoz a korábbi rendszer utolsó fizetési időszakához, ami létrehozza a kereseti kimutatási sorokat az új bérszámfejtő rendszerben. Adjon meg egy sort bevételkódonként, valamint a folyó évi összeget és órákat. A minta lépések a következők:

1. Nyissa meg az **Összes kereseti kimutatás** lapot, és kattintson az **Új** lehetőségre.  

Adja meg a következő adatokat: 

| Mező      | Érték                 |
|------------|-----------------------|
| Dolgozó     | Michael Redmond       |
| Fizetési ciklus  | sm                    |
| Fizetési időszak | 2017/06/16 - 2017/6/30 |

2. A **Kereseti kimutatás sorai** lapon írja be a következőket:

1. sor: **Kereseti kimutatás sorai** lap

| Mező            | Érték       |
|------------------|-------------|
| Bevételkód    | Rendszeres fizetés |
| Mennyiség         | 1.00        |
| Árfolyam             | 30 000      |
| Sor részletei lap |             |
| Manuális           | (megjelölve)    |

2. sor: **Kereseti kimutatás sorai** lap

| Mező            | Érték    |
|------------------|----------|
| Bevételkód    | Jutalom    |
| Mennyiség         | 1.0000   |
| Árfolyam             | 4250.00  |
| Sor részletei lap |          |
| Manuális           | (megjelölve) |

3. sor: **Kereseti kimutatás sorai** lap

| Mező           | Érték      |
|-----------------|------------|
| Bevételkód   | Jutalék |
| Mennyiség        | 1.0000     |
| Árfolyam            | !,299.00   |
| Árfolyam            | 1,299.00   |
| Sor részletei lap |            |
| Manuális          | (megjelölve)   |

> [!NOTE]
> A Manuális jelölőnégyzet bejelölése a **Sor részletei** lapon minden egyes keresetikimutatás-sornál kulcsfontosságú ahhoz, hogy minden dolgozónál be lehessen vinni a nyitó bérlistaegyenlegeket.

3. A **Művelet** ablaktáblán kattintson a következőre: **Kereseti kimutatás kiadása** USA-FED-ER-FICA.

4. A **Művelet** ablaktáblán kattintson a **Fizetési kimutatás** lehetőségre a **Fizetési kimutatások létrehozása** lap megnyitásához, és állítsa be a következőket:

| Mező              | Érték     |
|--------------------|-----------|
| Fizetés dátuma       | 2017/30/6 |
| Kifizetés típusa   | Manuális    |
| Könyvelés letiltása | (megjelölve)  |

> [!NOTE] 
> Ez csak akkor érhető el, ha a kifizetési típus kézi, és a felhasználó le szeretné tiltani a könyvelést a fizetési időszakra.

Kattintson az **OK** lehetőségre, és zárja be az **Információs napló** elemet.

#### <a name="why-disable-accounting-checkbox-needs-to-be-turned-on-when-generating-pay-statements"></a>Miért kell bejelölni a Könyvelés letiltása jelölőnégyzetet a fizetési kimutatások létrehozásakor?
Ezzel megelőzhető, hogy megtörténjen a fizetési kimutatás sorainak kiosztása és feladása a főkönyvbe. Nem szeretnénk feladni a nyitó egyenleg fizetési kimutatását, mert az értékei már bent vannak a főkönyvben a korábbi rendszerből. Ez az egyenlegbetöltés csak jelentési és korlátozási célokat szolgál.

### <a name="c-create-pay-statements-for-employees"></a>C. Fizetési kimutatások létrehozása az alkalmazottak számára
A nyitó egyenlegekkel rendelkező fizetési kimutatások létrehozása után ellenőriznie kell, hogy a fizetési kimutatások pontosan tükrözik-e a bérlistaadatokat. Emellett manuálisan kell frissíteni a juttatásokra és az adókra vonatkozó adatokat, hogy megfeleljenek az előző bérszámfejtő rendszer értékeinek. Miután meggyőződött arról, hogy a korábbi bérszámfejtő rendszer összegei megfelelnek az aktuális fizetési kimutatások összegeinek, a fizetési kimutatásokat véglegesíteni kell.

1. Nyissa meg az **Összes fizetési kimutatás** oldalt.

2. Jelölje ki a legutóbb Michael Redmond számára létrehozott fizetési kimutatást

3. Kattintson a **Szerkesztés** elemre a **Fizetési kimutatás** oldal megnyitásához.

4. Nyissa meg a **Juttatás levonásai** lapot, és írja be a következőt:

| Mező                           | Érték            |
|---------------------------------|------------------|
| Juttatás                         | Levonás összege |
| 401K | Résztvétel              | 3000.00          |
| Fogászati | SubSp                  | 495,00           |
| Elt. ellátási kiadások | Résztvétel | 2500.00          |
| Látás | SupSp                  | 500.00           |

5. A **Juttatás levonásai** lapon írja be a következőt: 

| Mező                           | Érték            |
|---------------------------------|------------------|
| Juttatás                         | Levonás összege |
| 401K | Résztvétel              | 3000.00          |
| Fogászati | SubSp                  | 495,00           |
| Elt. ellátási kiadások | Résztvétel | 2500.00          |
| Látás | SupSp                  | 500.00           |

6. A **Juttatás hozzájárulásai** lapon írja be a következőt:

| Mező              | Érték               |
|--------------------|---------------------|
| Juttatás            | Hozzájárulási összeg |
| 401K | Résztvétel | 3000,00             |
| Fogászati | SubSp     | 495,00              |
| Látás | SubSp     | 500.00              |

7. Az **Adólevonások** lapon írja be a következőt:

| Mező           | Érték            |
|-----------------|------------------|
| Adókód        | Levonás összege |
| USA-FED-ER-FICA | 1600.00          |
| USA-FED-ER-MEDI | 825.75           |

8. Az **Adó-hozzájárulások** lapon írja be a következőt:

9. Kattintson a **Számítás** lehetőségre.
> [!IMPORTANT] 
> Ellenőrizze a fizetési kimutatás összegeit, hogy megfeleljenek a régi rendszerből hozott folyó évi összegnek a dolgozó esetében. A következő lépésben még nem kell végrehajtani a véglegesítést, hogy általános érvényesítést hajthasson végre az összes fizetési kimutatás összesített értékén. Az ellenőrzést követően fusson végig az összes fizetési kimutatáson és véglegesítse őket.

Ugyanez az eljárás szükség esetén negyedéves lépésekben is elvégezhető, az összes korábbi negyedévre, minden évben. Erre csak akkor van szükség, ha az ügyfélnek negyedéves bontásban kell megtekintenie az adatokat anélkül, hogy visszalépne a korábbi rendszerbe.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>Ha hibázik a nyitó egyenlegek alkalmazotthoz való bevitele közben
Lehetőség van a tranzakciók sztornírozására és ismételt bevitelére. A tranzakció sztornírozásához mindössze a következő lépéseket kell végrehajtani az **Összes fizetési kimutatás** oldalon.

1. Kattintson a **Sztornírozás** lehetőségre.

2. Kattintson az **Igen** lehetőségre, amikor a következő üzenet: „Ha sztornírozza ezt a fizetési kimutatást, sztornírozó fizetési kimutatás kerül létrehozásra ezen fizetési kimutatás ellentételezésére. Egyik fizetési kimutatás sem szerkeszthető. Kívánja sztornírozni ezt a fizetési kimutatást?" jelenik meg. 

A fizetési kimutatás sztornírozását követően új fizetési kimutatást hozhat létre a dolgozóhoz abból a kereseti kimutatásból, amelyet a jelen témakör „Nyitó egyenlegekkel rendelkező kereseti kimutatások és fizetési kimutatások létrehozása” eljárásában hozott létre korábban. Ne felejtsen el kijavítani minden hibás sort a kereseti kimutatáson az új fizetési kimutatás létrehozása előtt, majd ismételje meg az ebben a témakörben található „A juttatásokhoz és az adókhoz nyitó egyenleggel rendelkező fizetési kimutatások frissítése” eljárást.
