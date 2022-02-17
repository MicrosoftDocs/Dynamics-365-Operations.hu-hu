---
title: Figyelem a főkönyvi kiegyenlítés és az év végi zárás között
description: Ez a témakör a főkönyvi elszámolásokat és a főkönyvi év végi zárást érintő fejlesztésekről nyújt információkat.
author: kweekley
ms.date: 01/31/2022
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
ms.openlocfilehash: acfbcf1467363262769884063efbc1a6d6e21eb1
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075731"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Figyelem a főkönyvi kiegyenlítés és az év végi zárás között

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

A Microsoftban Dynamics 365 Finance 10.0.25 verzió, a **Tudatosság a főkönyvi elszámolás és az év végi zárás között** funkció elérhető a **Funkciókezelés** munkaterület. Ez a funkció két elsődleges fejlesztéssel egészíti ki a főkönyvi elszámolást és a főkönyvi év végi zárást.

A főkönyvi év végi zárás során a kiegyenlített főkönyvi tranzakciók már nem szerepelnek a következő pénzügyi év nyitó egyenlegében. Ez a fejlesztés biztosítja, hogy csak a kiegyenlítetlen főkönyvi tranzakciók szerepeljenek a nyitóegyenlegben. Ez fontos a főkönyvi deviza átértékeléskor. A deviza átértékelés csak a következő státuszú főkönyvi tranzakcióknál fut **Nem rendezett**. Mielőtt azonban a **Tudatosság a főkönyvi elszámolás és az év végi zárás között** A funkció megjelent, a nyitóegyenleg mindkét tranzakciót összegezte, amelyek állapota: **Letelepedett** és azok, amelyek állapota **Nem rendezett**, és az összesített összeg állapota a következőre lett állítva **Nem rendezett**.

A második fejlesztés lehetővé teszi a nyitóegyenleg-tranzakciók részletes könyvelését a főkönyvi év végi zárás során. Ha a **Tartsa meg a részleteket az év végi záráskor** opcióra van állítva **Igen**, külön nyitóegyenleg jön létre minden egyes ki nem számolt főkönyvi tranzakcióhoz. Ez a beállítás a főkönyvi kiegyenlítés beállításaiban minden fő számlához meg van határozva. A nyitóegyenleg részletes tranzakcióinak megtartásával nagymértékben javítja a kiegyenlítetlen főkönyvi tranzakciók kiegyenlítésének lehetőségét a következő pénzügyi évben.

Az új fejlesztések támogatására a főkönyvi elszámolásban és az év végi zárásban változások történtek.

### <a name="changes-to-ledger-settlement"></a>Változások a főkönyvi elszámolásban

- A főkönyvi elszámolást egy pénzügyi éven belül kell megtenni.
- A főkönyvi kiegyenlítést egyetlen főszámlán lévő tranzakciókhoz kell elvégezni. A főszámla mostantól kötelező szűrő a **Főkönyvi elszámolás** oldalon.
- A főkönyvi kiegyenlítés és a főkönyvi kiegyenlítés visszafordítása nem végezhető el lezárt pénzügyi éven belül feladott tranzakcióknál (vagyis az év végi zárás lefutott).

### <a name="changes-to-year-end-close"></a>Változások az év végi záráshoz

- Az év végi zárás nem vonható vissza, ha a következő pénzügyi évben bármely nyitóegyenleg-tranzakció kiegyenlítésre került. Ez a változás akkor érvényes, amikor az év végi zárást visszavonják, vagy amikor az év végi zárást újra lefuttatják, és a **Az év újrazárásakor törölje a meglévő év végi bejegyzéseket** opcióra van állítva **Igen** a Főkönyvi paraméterekben.
- Ha a **Tartsa meg a részleteket az év végi záráskor** opcióra van állítva **Igen** a főkönyvi elszámolásban szereplő bármely mérlegszámlához az adott főszámlához részletesebb nyitóegyenleg-tranzakciók jönnek létre.

## <a name="before-you-enable-the-feature"></a>Mielőtt engedélyezi a funkciót

A funkcionalitás és az adatmodell változásai miatt fontos, hogy a funkció engedélyezése előtt vegye figyelembe a következőket:

- Minden olyan tranzakció, amely kiegyenlítésre meg van jelölve, de még nem lett kiegyenlítve, automatikusan törlődik, amikor a funkció engedélyezve van. A munkavesztés elkerülése érdekében rendezze az összes megjelölt tranzakciót a funkció engedélyezése előtt.
- Egyes szervezetek az év végi zárást többször is lefuttatják ugyanarra a pénzügyi évre vonatkozóan. Ne engedélyezze a funkciót, ha az év végi zárást már egyszer lefuttatták, és ugyanabban a pénzügyi évben újra lefutják. A funkciót engedélyezni kell az első év végi zárás feldolgozása előtt, vagy a pénzügyi év utolsó év végi zárásának feldolgozása után.

  Ha engedélyezni szeretné a funkciót, de az év végi zárás már egyszer lefutott, akkor a funkció engedélyezése előtt meg kell fordítania az év végi zárást.

- Mivel a pénzügyi évek közötti elszámolás már nem engedélyezett, javasoljuk, hogy engedélyezze a funkciót az év végi zárási folyamat megkezdése előtt. Ezután annak biztosítása érdekében, hogy a következő pénzügyi év nyitó egyenlegét ne befolyásolják a korábbi, több pénzügyi évre vonatkozó elszámolások, a nyitóegyenleg-tranzakciót a lezárás alatt álló pénzügyi évre kell kiegyenlíteni.
- Mivel a főszámlák közötti kiegyenlítés már nem engedélyezett, szükség szerint módosítsa a számlatervét vagy folyamatokat, hogy biztosítsa, hogy a főkönyvi kiegyenlítés ugyanazon a főszámlán történjen.
- A funkció nem engedélyezhető, ha a közszféra év végi bezárási folyamata használatban van.

## <a name="set-up-ledger-settlement"></a>Főkönyvi elszámolás beállítása

A funkció engedélyezése után és a következő év végi zárás futtatása előtt minden szervezetnek meg kell határoznia, hogy megőrzi-e a tranzakció részleteit az év végi zárás során. A választás nincs hatással a korábbi év végi zárási folyamatok nyitóegyenleg-könyvelésére.

A **Tartsa meg a részleteket az év végi záráskor** opció minden fő fiókhoz be van állítva a **Főkönyvi elszámolás beállítása** oldalon.

1.  Menj **Főkönyvi** > **Főkönyvi beállítás** > **Főkönyvi paraméterek**.
2.  A **Főkönyvi elszámolások** lapon válassza ki **Főkönyvi elszámolási számlák**.

– vagy –

1.  Menj **Főkönyvi** > **Időszakos feladatok** > **Főkönyvi elszámolások**.
2.  Válassza ki **Főkönyvi elszámolási számlák**.

Két oszlop került hozzáadásra a **Főkönyvi elszámolások** oldal:
    
- **Fő számla típusa** – Ez az oszlop csak tájékoztató jellegű. A fő fiókhoz rendelt típust mutatja.
- **Tartsa meg a részleteket az év végi záráskor** – Alapértelmezés szerint az opció a következőre van állítva **Nem**. Be lehet állítani **Igen** csak akkor, ha az érték a **Fő számla típusa** oszlop az **Mérleg**, **·**, vagy **Felelősség**. Amikor az opció értékre van állítva **Nem**, a nyitó egyenlegek összefoglalóan kerülnek feladásra, ahogy az év végi záráskor jellemző. Ha be van állítva **Igen**, a nyitó egyenlegek részletesen létrejönnek minden olyan főkönyvi tranzakcióhoz, amely nincs kiegyenlítve a főszámlán.

## <a name="year-end-close"></a>Év végi zárás

Amikor fut az év végi közel megy **Főkönyvi** > **Időszak lezárása** > **Év végi zárás**, a folyamat létrehozza a főszámlák nyitó egyenlegeit, amelyek a főkönyvi elszámoláshoz vannak definiálva. A nyitó egyenlegek a főkönyvi kiegyenlítés beállításától függően összesítésben vagy részletben készülnek. A folyamat kizárja a kiegyenlített főkönyvi tranzakciókat, függetlenül attól, hogy az egyes főszámlák nyitóegyenlegét összesítve vagy részletesen könyveli-e el.

Például a 2021-es pénzügyi évben több tranzakció könyvelhető el a 130100 főszámlán.

| Napló száma | Bizonylat   | Dátum       | Típus      | Főkönyvi számla | Számla neve        | Leírás       | Pénznem | Összeg a tranzakció pénznemében. | Összeg  | Összeg a jelentési pénznemben |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 2021.12.03  | Működési | 130100-001-    | Kinnlevőségek | Szolgáltatási díj       | USD      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 2021.12.05  | Működési | 130100-002-    | Kinnlevőségek | segédprogramok         | USD      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 2021.12.16 | Működési | 130100-001-    | Kinnlevőségek | Visszatérítés            | USD      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 2021.12.20 | Működési | 130100-002-    | Kinnlevőségek |                   | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 2021.12.20 | Működési | 130100-002-    | Kinnlevőségek |                   | EUR      | -127.11                        | -174.12 | -174.12                      |
| 20856          | CMV-4010 | 2021.12.21 | Működési | 130100-002-    | Kinnlevőségek | Hitel a számlán | USD      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 2021.12.28 | Működési | 130100-001-    | Kinnlevőségek | segédprogramok         | USD      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 2021.12.29 | Működési | 130100-002-    | Kinnlevőségek | Szolgáltatás           | USD      | 300                            | 300     | 300                          |

Ezen tranzakciók közül három főkönyvi elszámolás során kerül elszámolásra.

Van egy számla 175 USD-ról (175 USD). Ezt a számlát euróban (EUR) történő fizetéssel fizették ki, és készpénzes engedményt vettek fel.

| Napló száma | Bizonylat   | Dátum       | Típus      | Főkönyvi számla | Számla neve        | Leírás | Pénznem | Összeg a tranzakció pénznemében. | Összeg  | Összeg a jelentési pénznemben |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 2021.12.05  | Működési | 130100-002-    | Kinnlevőségek | segédprogramok   | USD      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 2021.12.20 | Működési | 130100-002-    | Kinnlevőségek |             | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 2021.12.20 | Működési | 130100-002-    | Kinnlevőségek |             | EUR      | -127.11                        | -174.12 | -174.12                      |

A 130100 fő fiók eredményei attól függenek, hogy a funkció engedélyezve van-e az év végi zárás futtatása előtt. Ha a funkció engedélyezve van, az eredmény a Részlet megőrzése az év végi bezárás során beállítás beállításától is függ.

### <a name="the-feature-isnt-enabled"></a>A funkció nincs engedélyezve
Az év végi zárás három nyitóegyenleg-tranzakciót hoz létre a 130100 főszámlához 2022-ben. A tranzakciók összege a számviteli pénznemben USD 525.

| Napló száma | Bizonylat   | Dátum     | Típus    | Főkönyvi számla | Számla neve        | Leírás | Pénznem | Összeg a tranzakció pénznemében. | Összeg  | Összeg a jelentési pénznemben |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek |             | USD      | 299.12                         | 299.12  | 299.12                       |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek |             | USD      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek |             | EUR      | -127.11                        | -174.12 | -174.12                      |

Annak ellenére, hogy a -127,11 eurós fizetési tranzakció főkönyvi kiegyenlítésre került, a tranzakció továbbra is kezdő egyenlegként jelenik meg.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>A funkció engedélyezve van, és a részletek megtartása az év végi zárás során = Nem

Az év végi zárás két nyitóegyenleg-tranzakciót hoz létre a 130100 főszámlához 2022-ben. A tranzakciók összege a számviteli pénznemben továbbra is USD 525, de a főkönyvi kiegyenlítésű tranzakciók nem szerepelnek a nyitó egyenlegben. A 130100-002- számla végösszege USD 125 USD 299.12 helyett, és a 127,11 EUR/174,12 USD értékű tranzakció teljesen kizárt.

| Napló száma | Bizonylat   | Dátum     | Típus    | Főkönyvi számla | Számla neve        | Leírás | Pénznem | Összeg a tranzakció pénznemében. | Összeg | Összeg a jelentési pénznemben |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek |             | USD      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek |             | USD      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>A funkció engedélyezve van, és a részletek megtartása az év végi bezárás során = Igen

Az év végi zárás öt nyitóegyenleg-tranzakciót hoz létre a 130100 főszámlához 2022-ben. Mind az öt nem kiegyenlített tranzakcióhoz külön nyitóegyenleg-tranzakció jön létre. A tranzakciók összege a számviteli pénznemben továbbra is USD 525.

| Napló száma | Bizonylat   | Dátum     | Típus    | Főkönyvi számla | Számla neve        | Leírás       | Pénznem | Összeg a tranzakció pénznemében. | Összeg | Összeg a jelentési pénznemben |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek | Szolgáltatási díj       | USD      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek | Visszatérítés            | USD      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek | Hitel a számlán | USD      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-001-    | Kinnlevőségek | segédprogramok         | USD      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 2022.01.01. | Nyitás | 130100-002-    | Kinnlevőségek | Szolgáltatás           | USD      | 300                            | 300    | 300                          |

A tranzakció részleteinek megőrzése az eredeti részletes tranzakciókat nem érinti. A lezárás alatt álló pénzügyi évben továbbra is kifüggesztettek és rendezetlenek. A tranzakciók másolata létrejön a nyitóegyenleghez. Az eredeti tranzakciók következő értékeit a rendszer a nyitóegyenleg-tranzakciókba másolja.

- Főkönyvi számla (a főszámla és az összes pénzügyi dimenzió)
- Összegek a tranzakció, a könyvelés és a jelentési pénznemekben
- Leírás
- Feladási réteg
- Feladás típusa

   > [!NOTE]
   > Nincs más nyitóegyenleg-tranzakció hozzárendelve könyvelési típushoz. Ezért a könyvelési típus felhasználható a részletesen előrehozott nyitási tranzakciók megkülönböztetésére.

Az eredeti tranzakciók egyes mezőit módosítani kell a nyitóegyenleg részletező tranzakciókban. A nyitóegyenleg-tranzakciók dátuma mindig a következő pénzügyi év első napja. A naplószámnak meg kell változnia, a bizonylat száma pedig az év végi bezárás párbeszédpanelen megadott értékre változik.

Az eredeti tranzakciókkal kapcsolatos információk megtalálhatók a **Főkönyvi elszámolás** oldalon. Minden részletes nyitóegyenleg-tranzakció megmutatja a **Eredeti tranzakció dátuma** oszlop a rácsban. Ez az oszlop segíthet az új pénzügyi év tranzakcióinak egyeztetésében. Választhat **Az eredeti utalvány megtekintése** hogy visszafúrja a teljes eredeti utalványt.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Tranzakciók kiegyenlítése
Főkönyvi tranzakciók kiegyenlítéséhez kövesse az alábbi lépéseket.

1. Menj **Főkönyvi** > **Időszakos feladatok** > **Főkönyvi elszámolások**.
2.  Állítsa be a szűrőket az oldal tetején.

    1. Válasszon ki egy dátumtartományt. Alternatív megoldásként válasszon egy dátumintervallum kódot a dátumtartomány automatikus kitöltéséhez.

       - A dátumtartomány nem haladhatja meg a pénzügyi éveket. Ha a dátumtartomány átlépi a pénzügyi éveket, a kiválasztásakor nem jelennek meg tranzakciók **Tranzakciók megjelenítése**.
       - Ha a dátumtartomány nyitott pénzügyi évre esik, a tranzakciók kiegyenlíthetők, és az elszámolás visszavonható. Ha a dátumtartomány lezárt pénzügyi évbe esik, vagy ha az év végi zárás befejeződött, a tranzakciók megjelennek, de nem rendezhetők vagy nem rendezhetők. A tranzakciók jelölését csak lezárt pénzügyi évben törölheti. Ha a dátumtartomány lezárt pénzügyi évbe esik, a **Jelölje meg kiválasztottként**, **megjelölt tranzakciók rendezése**, és **Fordított megjelölt tranzakciók** gombok nem elérhetők.

    2. Válassza ki a fő számlát a tranzakciók megjelenítéséhez. A mező kitöltése kötelező. A keresés csak azokat a fő fiókokat jeleníti meg, amelyek kiválasztottak a **Főkönyvi elszámolás** oldalon található a cég számlatüköre.
    3. Válassza ki a közzétételi réteget. A különböző feladási rétegekben lévő tranzakciók nem rendezhetők.
    4. A fő számla és a dimenziók külön oszlopokban történő megjelenítéséhez válasszon ki egy pénzügyi dimenziókészletet.

3.  Válassza ki **Tranzakciók megjelenítése** az összes olyan tranzakció megjelenítéséhez, amely megfelel a beállított szűrőknek. Ha módosítja a szűrők vagy a dimenziókészletek bármelyikét, ki kell választania a **Tranzakciók megjelenítése** lehetőséget újra.
4.  Válasszon vonalakat az elszámoláshoz. Az érték a **Kiválasztott mennyiség** Az oldal tetején lévő mező növekszik vagy csökken, hogy tükrözze a kiválasztott sorok teljes összegét.
5.  Ha végzett a tranzakciók kiválasztásával, válassza a lehetőséget **Jelölje meg kiválasztottként**. Minden kiválasztott tranzakciónál egy pipa jelenik meg a **Megjelölt** oszlop. Ezenkívül az érték a **Megjelölt összeg** A rács feletti mező növekszik vagy csökken, hogy tükrözze a megjelölt vonalakon lévő teljes összeget.
6.  Amikor az érték a **Megjelölt összeg** mező az **0** (nulla), válassza ki **A megjelölt tranzakciók rendezése**.

    - A részleges elszámolás nem megengedett. Például egy $100 terhelési tranzakciót nem számolhat ki $90 jóváírási tranzakcióval. A fennmaradó $10 jóváírási tranzakciót is meg kell jelölni az elszámolásban való szerepeltetéshez.
    - Adja meg az elszámolás dátumát. A dátumnak az elszámolásra megjelölt ügyletek legkésőbbi dátumának kell lennie, vagy azt követően kell lennie.

A megjelölt tranzakciók állapota **Kiegyenlített** értékre frissül.

> [!IMPORTANT]
> Minden olyan tranzakció kiegyenlítésre kerül, amelyet az aktív jogi személyhez és a kiválasztott főszámlához kiegyenlítésre jelölt meg. A tranzakcióknak nem kell megjelenniük az oldalon. Akkor is rendeződnek, ha egy szűrő miatt rejtve vannak.

Egyes folyamatok, például egy tranzakció visszavonása, automatikusan rendezik a főkönyvi tranzakciókat. Például a fizetés és a számla kiegyenlítése a vevőállományban történik, és az elszámolás realizált nyereséget/veszteséget generál. A fizetés és a számla kiegyenlítése nem rendezi a főkönyvi tranzakciókat, például a kintlévőség főkönyvi számlára vonatkozó tranzakciókat. Ha azonban a befizetés és a számla kiegyenlítetlen a kintlévőségben, akkor a kintlévőség-elszámolás sztornírozása során feladott sztornó könyvelési tétel az eredeti és a sztornó könyvelési tételek főkönyvi kiegyenlítését eredményezi. Amikor az **Tudatosság a főkönyvi elszámolás és az év végi zárás között** A funkció engedélyezve van, a sztornó főkönyvi kiegyenlítése nem történik meg automatikusan, ha a sztornírozás dátuma egy másik pénzügyi évben van.

## <a name="use-excel-for-ledger-settlement"></a>A főkönyvi elszámoláshoz használja az Excelt

Tranzakciók, amelyek megjelennek a **Főkönyvi elszámolás** oldal exportálható Excelbe. Az Excelben tovább szűrheti a tranzakciókat annak meghatározásához, hogy mely tranzakciókat jelölje meg elszámolásra.
Mindkét főkönyvi elszámolási entitás csak a főszámlán kiválasztott főszámlához exportálja a főkönyvi tranzakciókat **Főkönyvi elszámolás** oldalon. Bár a lezárt pénzügyi évekre vonatkozó tranzakciók továbbra is megjelölhetők vagy törölhetők az Excel használatával, nem rendezhetők. Ezenkívül az elszámolt tranzakciók nem vonhatók vissza az adott pénzügyi évben.

## <a name="make-transactions-easier-to-find"></a>Tranzakciók megkeresésének egyszerűbbé tétele

A **Főkönyvi elszámolások** oldal olyan lehetőségeket tartalmaz, amelyek megkönnyítik az elszámoláshoz szükséges tranzakciók megtekintését.

• Használja a **Megjelölt** szűrő a tranzakciók szűréséhez az alapján, hogy a **Megjelölt** jelölőnégyzet be van jelölve.
• Használja a **Állapot** szűrő a tranzakciók állapotuk alapján történő szűréséhez.
• Válassza ki **Rendezés abszolút összeg szerint** az összegek abszolút érték szerinti rendezéséhez. Ily módon csoportosíthatja az azonos összegű terheléseket és jóváírásokat.

## <a name="reverse-a-settlement"></a>Kiegyenlítés sztornírozása

A tévedésből létrehozott kiegyenlítések sztornírozhatók.

1.  Kövesse az 1–3. lépéseket a [A tranzakciók rendezése](#settle-transactions) szakaszban megtekintheti az Önt érdeklő tranzakciókat.
2.  Az **Állapot** szűrőben válassza ki a **Kiegyenlített** lehetőséget.
3.  Válassza ki a sorokat a visszafordításhoz.
4.  Válassza ki **Fordított megjelölt tranzakciók**. Az azonos elszámolási azonosítóval rendelkező összes tranzakció állapota a következőre frissül **Nem rendezett**.

> [!IMPORTANT]
> Minden olyan tranzakció, amelynek elszámolási azonosítója megegyezik, visszavonásra kerül, még akkor is, ha nincsenek megjelölve. Például négy sort jelöltek ki és rendeztek el. Mind a négy sornak ugyanaz a településazonosítója. Ha kijelöli a négy sor egyikét, majd kiválasztja **Fordított megjelölt tranzakciók**, mind a négy sor megfordul.






