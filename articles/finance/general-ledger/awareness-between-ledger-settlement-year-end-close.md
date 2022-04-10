---
title: Figyelem a főkönyvi kiegyenlítés és az év végi zárás között
description: Ez a témakör a főkönyvi kiegyenlítéseket és a főkönyv év végi zárát növelő fejlesztésekről nyújt tájékoztatást.
author: kweekley
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: e18f77d73239de23000b5310d9342c6db95bc524
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462352"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Figyelem a főkönyvi kiegyenlítés és az év végi zárás között

[!include [banner](../includes/banner.md)]


A Microsoft Dynamics 365 Finance 10.0.25-ös **·** **verziójában** a Funkciókezelés munkaterületén elérhető a Főkönyvi kiegyenlítés és az év végi lezárás közötti tudatosság. Ez a funkció két elsődleges fejlesztést ad hozzá, amelyek a főkönyvi kiegyenlítést és a főkönyv év végi zárást érintik.

A főkönyv év végi zárása során a kiegyenlített főkönyvi tranzakciók már nem fognak szerepelni a következő pénzügyi év nyitó egyenlegében. Ezzel a fejlesztéssel garantálható, hogy csak a még ki nem adott főkönyvi tranzakciókat tartalmazza a nyitó egyenleg. Fontos a főkönyvi devizaátértékelés futtatásakor. A devizaátértékelés csak a **Nem kiegyenlített állapotú főkönyvi tranzakciók esetében fut le**. **Ugyanakkor** a főkönyvi kiegyenlítés és az év végi zárási funkció közötti tudatosság feladása előtt a nyitó egyenleg összegzi mind a Kiegyenlített állapotú, mind **a** **Kiegyenlített** állapotú tranzakciókat, **és az összesített összeg állapotát Még nincs kiegyenlítve állapotra állítva.**

A második továbbfejlesztés segítségével a főkönyv év végi zárása során feladhatja a részletes nyitóegyenleg-tranzakciókat. Ha az **Év végi** **zárási** részletek megtartása beállítás Igen, a nem kiegyenlített főkönyvi tranzakciókhoz külön nyitó egyenleg jön létre. Ez a beállítás a főkönyvi kiegyenlítési beállításokban meghatározott fő számlákhoz van meghatározva. Ha részletes tranzakciókat tart be a nyitóegyenleghez, akkor nagy mértékben jobban ki tudja egyenlítni a nem egyenlített főkönyvi tranzakciókat a következő pénzügyi évben.

Az új fejlesztések támogatása érdekében módosításokat történt a főkönyvi kiegyenlítésben és az év végi lezárásban.

### <a name="changes-to-ledger-settlement"></a>Főkönyvi kiegyenlítés változásai

- A főkönyvi kiegyenlítést egy pénzügyi évben kell végezve.
- Egyetlen fő számla tranzakcióinak főkönyvi kiegyenlítését kell végezni. A fő számla így kötelező szűrő lesz a főkönyvi **kiegyenlítési** lapon.
- Lezárt pénzügyi évben feladott tranzakciók esetében (más szóval az év végi lezárás lefutott) nem lehet főkönyvi kiegyenlítést és főkönyvi kiegyenlítéstszétét futtatni.

### <a name="changes-to-year-end-close"></a>Év végi zárás módosításai

- Az év végi zárás nem sztornírozható, ha a nyitóegyenleg-tranzakciók a következő pénzügyi évben ki vannak egyenlítve. Ez a módosítás akkor érvényes, ha az év végi zárást sztornírozták, vagy ha az év végi zárást újrafuttatják, **és a Főkönyvi paramétereknél az Év zárása esetén a Létező év végi** **bejegyzések** törlése beállítás Igen beállításra van állítva.
- Ha a **főkönyvi** **kiegyenlítés** minden mérlegszámla esetében Igen az Év végi részletek nyilvántartása beállítás, az adott fő számlához részletesebb nyitóegyenleg-tranzakciók fognak létrejönni.

## <a name="before-you-enable-the-feature"></a>A funkció engedélyezése előtt

A funkciók és az adatmodell változásai miatt fontos, hogy a funkció engedélyezése előtt figyelembe kell venni az alábbi pontokat:

- A funkció engedélyezése esetén minden olyan tranzakció jelölése törlődik, amely meg van jelölve kiegyenlítésre, de még nincs kiegyenlítve. A munkaveszteség elkerülése érdekében a funkció engedélyezése előtt egyenlítsen ki minden megjelölt tranzakciót.
- Egyes szervezetek többször futtatják az év végi lezárásokat ugyanannak a pénzügyi évnek. Ne engedélyezze a funkciót, ha az év végi lezárás egyszer már lefutott, és ugyanannak a pénzügyi évnek újra lesz futtatva. A funkciót az első év végi zárás feldolgozása előtt vagy a pénzügyi év utolsó év végi zárása után kell engedélyezni.

  Ha engedélyezni szeretné a funkciót, de az év végi lezárás egyszer már lefutott, a funkció engedélyezése előtt sztornírozni kell az év végi zár funkciót.

- Mivel a pénzügyi éveken keresztüli elszámolás már nem engedélyezett, ajánlott engedélyezni ezt a funkciót, még az év végi zárási folyamat megkezdése előtt. Ezután annak érdekében, hogy a következő pénzügyi év nyitóegyenlegét ne érintik a korábbi, több pénzügyi évre vonatkozó kiegyenlítések, a nyitóegyenleg-tranzakciót ki kell egyenlíteni a lezárás alatt található pénzügyi évre.
- Mivel a fő számlákon keresztüli kiegyenlítés már nem engedélyezett, módosítsa a számlatükret vagy a folyamatokat úgy, hogy a főkönyvi kiegyenlítést ugyanazon a fő számlán is el lehet végezve.
- A funkció nem engedélyezhető az állami szektor év végi lezárási folyamatának használata esetén.

## <a name="set-up-ledger-settlement"></a>Főkönyvi kiegyenlítés beállítása

A funkció engedélyezése után, valamint a következő év végi zárás futtatása előtt minden szervezetnek meg kell határoznia, hogy megtartja-e a tranzakció részleteit az év végi zárás során. A választásnak nincs hatása az előző év végi zárási folyamatok nyitóegyenleg-feladásaira.

A **Főkönyvi kiegyenlítés beállítása lapon** **be van állítva a Részletek megtartva az év végi záráskor beállítás minden fő számlához**.

1.  Ugrás a **FőkönyvLedger** > **setupGeneral** > **főkönyvi paraméterekhez**.
2.  A Főkönyvi **kiegyenlítések** lapon válassza ki a főkönyvi **kiegyenlítési számlákat**.

– vagy –

1.  Ugrás a **főkönyvPeriodic** > **tasksLedger** > **kiegyenlítéseihez**.
2.  Válassza ki a **főkönyvi kiegyenlítési számlákat**.

Két oszlop lett hozzáadva a Főkönyvi **kiegyenlítések laphoz**:
    
- **Fő számlatípus** – ez az oszlop csak tájékoztatásra szolgál. A fő számlához rendelt típust jeleníti meg.
- **Részletes adatok megtartása az év végi zárás során** – alapértelmezés szerint a Nem beállítás van **megjelölve**. Csak akkor lehet Igen **értékűre** **állítani, ha a Fő számlatípus** **oszlop értéke Mérleg**,**·** **Eszköz vagy Kötelezettség.** Ha a beállítás **Nem**, a nyitó egyenlegek összegzésben lesznek feladva, ahogy az az év végi zárás tipikusan jellemző. Ha Igenre **van** állítva, a nyitóegyenlegek részletesen létrejönnek minden olyan főkönyvi tranzakcióhoz, amely nincs kiegyenlítve a fő számlával.

## <a name="year-end-close"></a>Év végi zárás

Amikor az **év** > **végi zárási folyamatot a FőkönyvPeriod** > **lezáró** év végi lezárási műveletével futtatja, a folyamat létrehozza a főkönyvi kiegyenlítésre meghatározott fő számlák nyitó egyenlegét. A nyitó egyenlegek a főkönyvi kiegyenlítés beállításától függően összegezve vagy részletesen is létrejönnek. A folyamat kizárja a kiegyenlített főkönyvi tranzakciókat, függetlenül attól, hogy összegezve vagy részletesen könyveli-e az egyes fő számlák nyitó egyenlegét.

A 2021-es pénzügyi 130100 feladott fő számlára például több tranzakciót ad fel.

| Napló száma | Bizonylat   | Dátum       | Típus      | Főkönyvi számla | Számla neve        | Leírás       | Pénznem | Összeg a tranzakció pénznemében. | Összeg  | Összeg a jelentési pénznemben |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 12/3/2021  | Működési | 130100-001-    | Kinnlevőségek | Szolgáltatási díj       | USD      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 12/5/2021  | Működési | 130100-002-    | Kinnlevőségek | Segédprogramok         | USD      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 12/16/2021 | Működési | 130100-001-    | Kinnlevőségek | Visszatérítés            | USD      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 12/20/2021 | Működési | 130100-002-    | Kinnlevőségek |                   | USD      | -0.88                          | -0.88   | -0.88                        |
| 20853          | ARPM0004 | 12/20/2021 | Működési | 130100-002-    | Kinnlevőségek |                   | EUR      | -127.11                        | -174.12 | -174.12                      |
| 20856          | CMV-4010 | 12/21/2021 | Működési | 130100-002-    | Kinnlevőségek | Követel - számlán | USD      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 12/28/2021 | Működési | 130100-001-    | Kinnlevőségek | Segédprogramok         | USD      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 12/29/2021 | Működési | 130100-002-    | Kinnlevőségek | Szolgáltatás           | USD      | 300                            | 300     | 300                          |

E tranzakciók közül három kiegyenlítése a főkönyvi kiegyenlítés során történik.

175 dollárról (175 USD) van számla. Ezt a számlát euróban (EUR) fizették ki, és készpénzfizetési engedményt vett igénybe.

| Napló száma | Bizonylat   | Dátum       | Típus      | Főkönyvi számla | Számla neve        | Leírás | Pénznem | Összeg a tranzakció pénznemében. | Összeg  | Összeg a jelentési pénznemben |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 12/5/2021  | Működési | 130100-002-    | Kinnlevőségek | Segédprogramok   | USD      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 12/20/2021 | Működési | 130100-002-    | Kinnlevőségek |             | USD      | -0.88                          | -0.88   | -0.88                        |
| 20853          | ARPM0004 | 12/20/2021 | Működési | 130100-002-    | Kinnlevőségek |             | EUR      | -127.11                        | -174.12 | -174.12                      |

A fő számla eredményeinek 130100 attól függ, hogy ez a funkció engedélyezve van-e az év végi zárás futtatása előtt. Ha a funkció engedélyezve van, akkor az eredmény az év végi lezáráskor a Részletek megtartása beállításától is függ.

### <a name="the-feature-isnt-enabled"></a>A funkció nincs engedélyezve.
Az év végi lezárás három nyitóegyenleg-tranzakciót hoz létre 130100 2022-ben. A tranzakciók összege a könyvelési pénznemben USD 525.

| Napló száma | Bizonylat   | Dátum     | Típus    | Főkönyvi számla | Számla neve        | Leírás | Pénznem | Összeg a tranzakció pénznemében. | Összeg  | Összeg a jelentési pénznemben |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek |             | USD      | 299.12                         | 299.12  | 299.12                       |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek |             | USD      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek |             | EUR      | -127.11                        | -174.12 | -174.12                      |

Annak ellenére, hogy a kifizetés -127,11 eurós tranzakciója ki lett egyenlítve, a tranzakció továbbra is kezdő egyenlegként halad előre.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>A funkció engedélyezve van, és a Részletek megtartva az év végi záráskor = Nem

Az év végi lezárás két nyitóegyenleg-tranzakciót hoz létre a fő számla 130100 2022-ben. A tranzakciók összege a könyvelési pénznemben még mindig USD 525, de a főkönyvben kiegyenlített tranzakciók nem kerülnek bele a nyitó egyenlegbe. A130100-002- USD 125 számla végösszege nem USD 299.12, a 127,11 eurós tranzakció pedig teljesen ki van zárva 174,12 USD-ről.

| Napló száma | Bizonylat   | Dátum     | Típus    | Főkönyvi számla | Számla neve        | Leírás | Pénznem | Összeg a tranzakció pénznemében. | Összeg | Összeg a jelentési pénznemben |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek |             | USD      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek |             | USD      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>A funkció engedélyezve van, és a Részletek megtartva az év végi záráskor = Igen

Az év végi lezárás öt nyitóegyenleg-tranzakciót hoz létre a fő számla 130100 2022-ben. Külön nyitóegyenleg-tranzakció jön létre mind az öt kiegyenlített tranzakcióhoz. A tranzakciók összege a könyvelési pénznemben még mindig USD 525.

| Napló száma | Bizonylat   | Dátum     | Típus    | Főkönyvi számla | Számla neve        | Leírás       | Pénznem | Összeg a tranzakció pénznemében. | Összeg | Összeg a jelentési pénznemben |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek | Szolgáltatási díj       | USD      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek | Visszatérítés            | USD      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek | Követel - számlán | USD      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek | Segédprogramok         | USD      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek | Szolgáltatás           | USD      | 300                            | 300    | 300                          |

Ha megtartja a tranzakciók részleteit, akkor ez nem befolyásolja az eredeti részletes tranzakciókat. Feladásuk és háteletleneik maradnak a lezárt pénzügyi évben. Ezeknek a tranzakcióknak egy másolata jön létre a nyitó egyenleghez. Az eredeti tranzakciók következő értékeit másolja a program a nyitóegyenleg-tranzakciókba.

- Főkönyvi számla (a fő számla és az összes pénzügyi dimenzió)
- Összegek a tranzakció, könyvelés és jelentési pénznemekben
- Leírás
- Feladási réteg
- Feladás típusa

   > [!NOTE]
   > Nincs feladási típus más nyitóegyenleg-tranzakcióhoz rendelve. Ennek megfelelően a feladási típus a részletesen áthozott nyitó tranzakciók megkülönböztetésére használható.

Az eredeti tranzakciók egyes mezőinek meg kell változtatniuk a nyitóegyenleg részletes tranzakcióit. A nyitóegyenleg-tranzakciók dátuma mindig a következő pénzügyi év első napja. A napló számát meg kell változtatni, és a bizonylatszám módosul az év végi zárása párbeszédpanelen megadott értékre.

Az eredeti tranzakciók adatai a Főkönyvi kiegyenlítés oldalon **találhatók**. Minden részletes nyitóegyenleg-tranzakció a **rács eredeti tranzakciódátum-oszlopát** jeleníti meg. Ez az oszlop segít megfeleltetni az új pénzügyi év tranzakcióit. Az eredeti bizonylat megtekintése **lehetőséget választva** a teljes eredeti bizonylathoz lehet visszaásni.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Tranzakciók kiegyenlítése
Főkönyvi tranzakciók kiegyenlítéséhez kövesse az alábbi lépéseket.

1. Ugrás a **főkönyvPeriodic** > **tasksLedger** > **kiegyenlítéseihez**.
2.  Állítsa be a szűrőket a lap tetején.

    1. Válasszon ki egy dátumtartományt. Másik lehetőségként válasszon egy dátumtartománykódot, amely automatikusan kitölti a dátumtartományt.

       - A dátumtartomány nem lehet több pénzügyi évnél. Ha a dátumtartomány pénzügyi éveket is átfed, a Tranzakciók megjelenítése beállításnál nem **jelennek meg tranzakciók**.
       - Ha a dátumtartomány nyitott pénzügyi évben van, akkor kiegyenlítheti a tranzakciókat, és sztornírozhatja a kiegyenlítést. Ha a dátumtartomány lezárt pénzügyi évben van, vagy ha az év végi lezárás befejeződött, akkor a tranzakciók megjelennek, de nem egyenlíthetetlenek vagy kiegyenlítetlenek. Csak lezárt pénzügyi évben lehet a tranzakciók jelölését lezárni. Ha a dátumtartomány lezárt pénzügyi évben van, **nem érhető el a Megjelölés bejelölve**, **a** Megjelölt tranzakciók egyenlítve és **a Megjelölt** tranzakciók sztornírozása gomb.

    2. Válassza ki azt a fő számlát, amely tranzakcióit megmutatja. A mező kitöltése kötelező. A keresés csak azokat **a** fő számlákat mutatja, amelyek ki vannak jelölve a vállalat számlatükre főkönyvi kiegyenlítési lapján.
    3. Válassza ki a feladási réteget. Nem egyenlíthet ki különböző feladási rétegekben tranzakciókat.
    4. Ha a fő számlát és a dimenziókat külön oszlopokban is megmutatja, válasszon ki egy pénzügyi dimenziókészletet.

3.  Válassza a **Tranzakciók megjelenítése** lehetőséget a beállított szűrőknek megfelelő összes tranzakció megjelenítéséhez. Ha módosítja a szűrők vagy a dimenziókészletek bármelyikét, ki kell választania a **Tranzakciók megjelenítése** lehetőséget újra.
4.  Válassza ki a kiegyenlítés sorait. A lap tetején **található** Kiválasztott összeg mező értéke a kijelölt sorok végösszegének megfelelően nő vagy csökken.
5.  Ha befejezte a tranzakciók kijelölését, válassza a Megjelölés **lehetőséget**. Minden kijelölt tranzakciónál megjelenik egy pipa a Megjelölt **oszlopban**. Ezenkívül a rács **fölötti Megjelölt** összeg mező értéke a megjelölt sorok teljes összegének megfelelően nő vagy csökken.
6.  Ha a Megjelölt **összeg** **mezőben 0** (nulla) érték van megjelölve, **válassza a Megjelölt tranzakciók egyenlítő értékét.**

    - A részleges elszámolás nem engedélyezett. Nem lehet például olyan jóváírási tranzakcióval szemben $100 a terhelési tranzakciót, $90 tartozik tranzakciót. A $10 jóváírási tranzakciót is meg kell jelölni az elszámolásba való felvételre.
    - Adja meg a kiegyenlítés dátumát. A dátumnak a kiegyenlítésre megjelölt tranzakciók legkésőbbi dátumán vagy utána kell lennie.

A megjelölt tranzakciók állapota **Kiegyenlített** értékre frissül.

> [!IMPORTANT]
> Minden olyan tranzakció elszámolásra lesz kiegyenlítve, amely meg van jelölve az aktív jogi személy és a kijelölt fő számla kiegyenlítésére. A tranzakcióknak nem kell megjelenniük a lapon. Akkor is kiegyenlíti őket a rendszer, ha egy szűrő miatt rejtettek.

Egyes folyamatok, például egy tranzakciószétsz., automatikusan egyenlítik ki a főkönyvi tranzakciókat. Egy kifizetés és egy számla például a Kinnlevőségek számlán van kiegyenlítve, és a kiegyenlítés realizált nyereséget/veszteséget generál. A kifizetés és a számla kiegyenlítése nem egyenlít ki főkönyvi tranzakciókat, például a Kinnlevőségek főkönyvi számlához tartozó tranzakciókat. Ha viszont a Kinnlevőségek modulban kiegyenlítetlen a kifizetés és a számla, akkor a Kinnlevőségek kiegyenlítésének a megfordítása során feladott könyvelési bejegyzés esetén az eredeti és a fordított könyvelési tételek kiegyenlítése a főkönyvben történik. Ha engedélyezve **van** a főkönyvi kiegyenlítés és az év végi lezárás közötti tudatosság, akkor nem történik meg automatikusan a fordított kiegyenlítés főkönyvi kiegyenlítése, ha a dátum másik pénzügyi évben van.

## <a name="use-excel-for-ledger-settlement"></a>Főkönyvi kiegyenlítés az Excelben

A főkönyvi kiegyenlítési **oldalon** megjelenő tranzakciók exportálhatók az Excel programba. Az Excel programban tovább szűrheti a tranzakciókat, hogy megállapítsa, mely tranzakciókat szeretné kiegyenlítésre megjelölni.
Mindkét főkönyvi kiegyenlítési entitás csak arra a főkönyvi számlára exportálja a főkönyvi tranzakciókat, amely ki van választva a Főkönyvi **kiegyenlítés oldalon**. Bár a lezárt pénzügyi évek tranzakcióit az Excel segítségével még meg lehet jelölni vagy ki lehet jelölni, nem lehet őket kiegyenlíteni. Ezenkívül az adott pénzügyi évre nem lehet sztornírozni a kiegyenlített tranzakciókat.

## <a name="make-transactions-easier-to-find"></a>Tranzakciók megkeresésének egyszerűbbé tétele

A **Főkönyvi kiegyenlítések** lap olyan funkciókat tartalmaz, amelyek segítségével egyszerűbben megtekinthetők a kiegyenlítéshez szükséges tranzakciók.

A Megjelölt szűrő **használatával** a tranzakciók annak alapján szűrhetők, hogy be **van**-e jelölve a Megjelölt jelölőnégyzet.
– az Állapot szűrő **használata** a tranzakciók állapotuk alapján való szűrésére.
• Válassza az abszolút **érték alapján rendezést** az összegek abszolút érték alapján való rendezéshez. Ily módon csoportosíthatja az azonos összegű tartozik és követel tételeket.

## <a name="reverse-a-settlement"></a>Kiegyenlítés sztornírozása

A tévedésből létrehozott kiegyenlítések sztornírozhatók.

1.  Hajtsa végre a Tranzakciók rendezésének szakasz 1–3 [...](#settle-transactions). lépését, hogy a tranzakciót érdeklődésére mutassa.
2.  Az **Állapot** szűrőben válassza ki a **Kiegyenlített** lehetőséget.
3.  Válassza ki a sorokat a megfordításhoz.
4.  Jelölje ki a **Megjelölt tranzakciók sztornírozása lehetőséget**. Az azonos kiegyenlítési azonosítójú tranzakciók állapota Nincs kiegyenlítve **állapotúra módosul**.

> [!IMPORTANT]
> Minden olyan tranzakció sztornírozva lesz, amelyek kiegyenlítési azonosítója megegyezik, még akkor is, ha nincsenek megjelölve. Például négy sort jelöltek meg és egyenlíttek ki. Mind a négy sor kiegyenlítési azonosítója megegyezik. Ha kijelöli a négy sor valamelyikét, és a **Megjelölt** tranzakciók sztornírozása lehetőséget választja, mind a négy sort sztornírozni fogja a tranzakció.






