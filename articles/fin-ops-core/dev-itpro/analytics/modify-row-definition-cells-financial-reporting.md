---
title: Sor definiáló cellák módosítása
description: A cikk ismerteti azokat az információkat, amelyek szükségesek egy pénzügyi jelentés sordefiníciójához tartozó cellákban, és bemutatja ezen információk megadását.
author: aprilolson
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1c125369a5b2134759bf3650175276acf42b69e0
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802823"
---
# <a name="modify-row-definition-cells"></a>Sor definiáló cellák módosítása

[!include [banner](../includes/banner.md)]

A cikk ismerteti azokat az információkat, amelyek szükségesek egy pénzügyi jelentés sordefiníciójához tartozó cellákban, és bemutatja ezen információk megadását.

## <a name="specify-a-row-code-in-a-row-definition"></a>Határozzon meg egy sor kódot a sor definícióban

A sordefiníciókban **a sorkód cellában lévő számok vagy** címkék a sordefiníció minden sorát azonosítják. A sorkód megadásával lehet hivatkozni az adatokra a számításokban és az összesítésekben.

### <a name="row-code-requirements"></a>A sorkódokkal kapcsolatos követelmények

Mindegyik sorhoz szükség van egy sorkódra. Vegyítheti a numerikus, az alfanumerikus és a nem beállított (üres) sorkódokat a sor definícióban. A sorkód lehet bármilyen pozitív egész szám (100 000 000 alatt), vagy egy leíró címke amely azonosítja az adott sort. A leíró címkének ezeknek a szabályoknak kell megfelelnie:

- A címkének (a és z között vagy A és Z között) egy alfabetikus karakterrel kell kezdődnie, és legfeljebb 16 karakterig a számoknak és a betűknek bármely kombinációja lehet.

    > [!NOTE]
    > A címke tartalmazhat aláhúzás jelet (\_), de semmilyen más speciális karakterek nem megengedett.

- A címke a következő foglalt szavak egyikét sem használhatja: AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO, vagy RPO.

Az alábbi példák érvényes sorkódok:

- 320
- TL\_NET\_INCOME
- TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Sorkód változtatása a sor definícióban

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg a módosítani szeretné a sordefiníciót.
2. Írja be az új értéket **a megfelelő sorba a Sorkód oszlop cellába** .

### <a name="reset-numeric-row-codes"></a>Numerikus sorkódok alaphelyzetbe állítása

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg a módosítani szeretné a sordefiníciót.
2. Kattintson a **Szerkesztés** menü Sorok újraszámozása **parancsára**.
3. A Sorok **újraszámozása** párbeszédpanelen adja meg az új értékeket a kezdő sorkódhoz és a sorkód növekményhez. A numerikus sorkódokat visszaállíthatja egyenlően elosztott értékre. Azonban a jelentéstervező csak a számokkal (például 130 vagy 246) kezdődő sorkódokat számozza újra. A betűkkel kezdődő sorkódokat (például INCOME\_93 vagy TP0693) nem számozza újra.

> [!NOTE]
> Amikor sorkódokat számoz újra, a jelentéstervező automatikusan frissíti a **TOT** és a **CAL** hivatkozásokat. Például, ha egy **TOT** sor olyan sorozatra hivatkozik, amely a 100-as sorkóddal kezdődik, és az újraszámozás a 90-es sortól kezdődik, a kezdő **TOT** hivatkozás 100-ról 90-re változik.

## <a name="add-a-description"></a>Leírás hozzáadása
A leírás cella biztosítja a pénzügyi adat leírását a jelentés olyan sorába, mint például „Bevétel” vagy „Nettó árbevétel.” A szöveg a **Leírás** cellában pontosan úgy jelenik meg, ahogyan a sordefinícióban megadta.

> [!NOTE]
> A leírás oszlop szélessége a jelentésben az oszlopdefinícióban van megadva. Ha a szöveg a **Leírás** oszlopban a sordefinícióban hosszú, ellenőrizze a **Leírás** oszlop szélességét. Amikor a **Sor Beszúrása Valahonnan** párbeszédpanelt használja, a **Leírás** oszlopban szereplő értékek szegmensértékek vagy dimenzióértékek a pénzügyi adatokból. Sorok beszúrásával leíró jellegű szöveget, például szakaszfejlécet vagy szakaszösszesítőt, illetve formázást, például összegsor előtti sort helyezhet el a jelentésben. Ha a jelentés tartalmazza egy jelentési fát, akkor beleveheti a kiegészítő szöveget is, ami a jelentési egységeknek van definiálva a jelentési fában. Korlátozhatja is a kiegészítő szöveget egy adott jelentési egységhez.

### <a name="add-the-description-for-a-line-on-a-report"></a>Adjon leírást egy sorhoz a jelentésben

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg a módosítani szeretné a sordefiníciót.
2. Válassza ki a **Leírás** cellát, és adja meg a jelentés sorának nevét.
3. Formázás alkalmazása.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Adjon kiegészítő szöveget a jelentési fából a leírásba

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg a módosítani szeretné a sordefiníciót.
2. Írja be a kiegészítő szöveg kódot és a többi szöveget a megfelelő **Leírás** cellába.
3. Formázás alkalmazása.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Korlátozza a kiegészítő szöveget egy adott jelentési egységhez

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg a módosítani szeretné a sordefiníciót.
2. Keresse meg azt a sort, amelyen kiegészítő szöveget kell létrehozni, majd kattintson duplán a cellára a **Kapcsolódó Képletek/Sorok/Egységek** oszlopban.
3. A Jelentési **egység kiválasztása** párbeszédpanel **Jelentési fa** mezőjében válasszon ki egy jelentési fát.
4. A **Válasszon jelentési egységet korlátozáshoz** mezőben, bontsa ki vagy csukja össze a jelentési fát, majd válasszon ki egy jelentési egységet.

## <a name="add-a-format-code"></a>Formátum kód hozzáadása
A **Formátumkód** cella az előre formázásnak megfelelő választási lehetőségeket kínál a sor tartalmához. Ha a **Formátumkód** cella üres, a sor pénzügyi adatadat-részletsorként lesz értelmezve.

> [!NOTE]
> Ha a jelentés olyan nem-összeg sorokat tartalmaz, amik kapcsolódnak rejtett összeg sorokhoz (például, mert az egyenlege nulla), használhatja a **Kapcsolódó Képletek/Sorok/Egységek** oszlopot, hogy megakadályozza a cím és a formátum sorok kinyomtatását.

### <a name="add-a-format-code-to-a-report-row"></a>Formátum kód hozzáadása jelentés sorhoz

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd válassza ki a módosítani kívánt sordefiníciót.
2. Kattintson duplán a Formátumkód **cellára** .
3. Jelöljön ki egy formátumkódot a listában. Az következő táblázat leírja a formátumkódokat és a szerepüket.

    | Formátumkód                   | Formátumkód magyarázata | Művelet |
    |-------------------------------|-----------------------------------|--------|
    | (Nincs)                        |                                   | A Formátumkód **cella kóddal való adatokat törli** . |
    | TOT                           | Teljes                             | Azonosítja a matematikai operátorokat használó sorokat a **Kapcsolódó Képletek/Sorok/Egységek** oszlopban. Az összegezők mindössze egyszerű műveleteket tartalmazhat, mint például **+** vagy **-**. |
    | CAL                           | Számítás                       | Azonosítja a matematikai operátorokat használó sorokat a **Kapcsolódó Képletek/Sorok/Egységek** oszlopban. A számítások tartalmazhatnak összetett műveleteket, mint például **+**, **-**, **\**_, _*/** és **IF/THEN/ELSE** utasítások. |
    | DES                           | Leírás                       | Egy fejléc sort, vagy egy üres sort azonosít a jelentésben. |
    | LFT RGT CEN                   | Bal Jobb Közép                 | A sor leíró szöveget jelentéslapra helyezi, függetlenül a szöveg igazításától az oszlopdefinícióban. |
    | CBR                           | Alapsor Módosítása                   | Azonosítja a sort, ami az alapsor lesz az oszlom számításokhoz. |
    | OSZLOP                        | Oszlop szünet                      | Új oszlopot kezd a jelentésben. |
    | OLDAL                          | Oldaltörés                        | Új oldalt kezd a jelentésben. |
    | \---                          | Egyszeres aláhúzás                  | Egyszeres aláhúzást tesz minden összeg oszlop alá a jelentésben. |
    | ===                           | Kétszeres aláhúzás                  | Kétszeres aláhúzást tesz minden összeg oszlop alá a jelentésben. |
    | LINE1                         | Vékony vonal                         | Egyetlen vékony vonalat rajzol keresztbe a lapra. |
    | LINE. sor                         | Vastag vonal                        | Egy vastag vonalat húz végig az oldalon. |
    | LINE3                         | Pontozott vonal                       | Egyetlen szaggatott vonalat rajzol keresztbe a lapra. |
    | LINE4                         | Vastag vonal és vékony vonal          | Dupla vonalat rajzol keresztbe a lapra. A felső vonal vastag, az alsó vonal pedig vékony. |
    | LINE5                         | Vékony vonal és vastag vonal          | Dupla vonalat rajzol keresztbe a lapra. A felső vonal vékony, az alsó vonal pedig vastag. |
    | BXB BXC                       | Keretezett sor                         | Keretet rajzol a **BXB**-al kezdődő sor és a **BXC**-al végződő sor köré. |
    | REM                           | Megjegyzés                            | Azokat a sorokat azonosítja, amelyek megjegyzéseket tartalmaznak, és amelyeket nem kell kinyomtatni a jelentés nyomtatásakor. Például a megjegyzéssor tartalmazhatja a formázási megoldások magyarázatát. |
    | SORT ASORT SORTDESC ASORTDESC | Rendezés                              | Rendezi a kiadásokat vagy a bevételeket, rendezi az aktuális költségvetést vagy költségvetés eltérés jelentést a legnagyobb eltérés szerint, vagy betűrendbe rendezi a sorokat. |

## <a name="specify-related-formulasrowsunits"></a>Kapcsolódó képletek/sorok/egységek megadása
A **kapcsolódó képletek/sorok/egységek** cella több célt is szolgál. Attól függően, hogy milyen típusú sor, a **Kapcsolódó Képletek/Sorok/Egységek** cella az alábbi műveletekre képes:

- Definiálja a számításba beleszámítandó sorokat amikor a **TOT** formátumkódot, vagy **CAL** formátumkódot használja.
- Formázási sor csatolása egy összeg sorhoz úgy, hogy a formázást a rendszer csak akkor kerül nyomtatja ki, ha a kapcsolódó összeg is nyomtatásra kerül.
- Egy meghatározott kimutatási egységre korlátozza a sort.
- Számításokhoz definiálja az alapsort, amikor a **BASEROW** kód formátumot használja.
- Definiálja a rendezendő sorokat, amikor bármelyik rendező formátumkódot használja.

### <a name="use-a-row-total-in-a-row-definition"></a>Sorösszegező használata sordefinícióban

Használja a sorösszegező formulát, hogy hozzáadjon vagy kivonjon összegeket más sorokban. Egy sorösszegező formula tartalmazhat + és - műveleteket, hogy egyéni sorkódokkal és tartományokkal is számolhasson. A tartományokat kettőspont (:) jelöli. A képlet legfeljebb 1,024 karakterből állhat. Íme egy példa az alap összegező képletre: 400 + 420 + 430 + 450 + 460LIABILITIES + EQUITY520:546520:546-LIABILITIES

### <a name="components-of-a-row-total-formula"></a>Sorösszesítő képlet részei

Sorösszesítő képlet létrehozásakor sorkódokkal kell meghatározni az aktuális sordefiníción belül összeadandó vagy kivonandó sorokat, illetve műveleti jeleket kell használni az elvégzendő műveletek jelöléséhez. Az összesítő sorok és az összegeket tartalmazó sorok tetszőlegesen kombinálhatók.

> [!NOTE]
> A tartományon belüli összegző sorokat kizárja a rendszer. Egy végösszeg létrehozásához, megadhatja a sorok tartományát. Ha a tartomány első sora összegező sor, akkor az a sor beleszámít az új összegbe. A következő táblázat leírja a műveletjelek használatát az összegző képletekben.

| Kezelő | Példa képlet | Leírás                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Hozzáadja a 100-ik sorban lévő összeget a 330-ik sorban lévő összeghez.        |
| :        | 100:330         | Összead minden sorösszeget a 100-ik és a 330-ik sor között.    |
| -        | 100-330         | Kivonja a 100-ik sorban lévő összeget a 330-ik sor összegéből. |

### <a name="create-a-row-total"></a>Sorösszesítés létrehozása

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg a módosítani szeretné a sordefiníciót.
2. Kattintson duplán a sordefiníció **formázási** kódcellájára, és válassza a **TOT kódot**.
3. A **Kapcsolódó Képletek/Sorok/Egységek** cellába írja be az összegző képletet.

### <a name="relate-a-format-row-to-an-amount-row"></a>Formátumsor összekapcsolása összegsorhoz

Egy sordefiníció Formátumkód oszlopában **a DES,ROWT,RGT,CEN**  **·** **·** **·** **és** a formátumkódok a nem összegsorok formázására vonatkoznak. **---** **===**  Annak érdekében, hogy ez a formázás ne kerüljön nyomtatásra, ha a kapcsolódó összegsorok rejtettek (például, mert az összegsor null értékű, vagy nem aktív az időszakban), akkor kapcsolja össze a formátumsorokat a megfelelő összegsorokkal. Ez a funkció akkor hasznos, ha el akarja kerülni részösszegekre vonatkozó fejlécek és formátumok nyomtatását, mert az adott időszak nem tartalmaz nyomtatandó információt.

> [!NOTE]
> Megakadályozhatja a részletes összegsorok nyomtatását az összeg nélküli sorok megjelenítése opció törlésével. Ez a beállítás a jelentésdefiníció **Beállítások** lapján található. Azok a tranzakció részletező számlák, amelyek egyenlege nulla és az időszakban nem aktívak, alapértelmezés szerint rejtettek a jelentésekben. Ezeknek a tranzakció részletező számláknak a megjelenítéséhez válassza az **Összegek nélküli sorok megjelenítése** jelölőnégyzetet a jelentésdefiníció **Beállítások** lapján.

### <a name="relate-a-format-row-to-an-amount-row"></a>Formátumsor összekapcsolása összegsorhoz

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd válassza ki a módosítani kívánt sordefiníciót.
2. A formázósor **Kapcsolódó képletek/Sorok/Egységek** cellájában, adja meg az összegsor sor kódját, hogy elrejtse.

    > [!NOTE]
    > Ahhoz, hogy egy összegsort ki lehessen hagyni, annak egyenlege 0 (nulla) kell, hogy legyen. Azok az összegsorok melyeknek egyenlege nem nulla, nem rejthetők el.

3. A **Fájl** menüben, kattintson a **Mentés** parancsra.

### <a name="example-of-preventing-printing-of-rows"></a>Példa a sorok nyomtatásának megelőzésére

A következő példában a **felhasználó** meg szeretné akadályozni a jelentés fejlécének és aláhúzásának nyomtatását, mivel egyik készpénzszámlán sem volt tevékenység. Ezért, a 220-ik sorban (amely, ahogy azt a **---** formátumkód jelzi, egy formázási sor), a **Kapcsolódó Képletek/Sorok/Egységek** cellába beír **250**-et, ami az elrejteni kívánt összegsor sorkódja.

[![RelatedRowsRowDefinition.](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Oszlop számítás alap sorának kiválasztása
A relációs jelentésekben, egy vagy több alap sort is hozzárendelhet sordefinícióban, a **CBR** (alap sor módosítása) formátumkód használatával. Az alap sorra ebben az esetben az oszlopdefinícióban található számítás hivatkozik. Íme néhány általános példa CBR számításokra:

- A teljes bevétel százaléka az egyes bevételi cikkek vonatkozásában
- A teljes költség százaléka az egyes költség cikkek vonatkozásában
- A bruttó nyereség százaléka a részleg vagy osztály vonatkozásában.

Egy vagy több alapsor van megadva a sordefinícióban, és ezután az oszlopdefiníció határozza meg a hivatkozott alapsort. Az oszlopképletben használt kód a **ALAPSOR**. A következő matematikai alapműveletek **ALAPSOR**-al használatosak: osztás, szorzás, összeadás vagy kivonás. A leggyakrabban használt művelet az osztás **ALAPSOR**-ral, ahol az eredmény százalékban jelenik meg. A képletben az **ALAPSOR**-t használó oszlopszámítások, a kapcsolt alapsor sordefinícióját használják. A **CBR** sorok az alábbi tulajdonságokkal rendelkeznek:

- A **CBR** sorok nincsenek kinyomtatva a befejeződött jelentésben.
- A **CBR** formátumkód és a kapcsolódó sorkód azon sor vagy a szakasz fölött van elhelyezve, amely a kapcsolódó számításokat jeleníti meg.

Az oszlopdefinícióban a **CALC** oszloptípus olyan oszlopot jelez, amely a **Képlet** sorban képletet határoz meg. Ez a képlet dolgozik ennek az jelentésoszlopnak az adataival, és a Baserow kulcsszót használja a számítások alapjául a **CBR** formátumkódokra a sorban. A sordefinícióban, a **CBR** formátumkód határozza meg az alapsort azoknak az oszlopoknak, amik százalékát vagy szorzatát számítják a jelentés összes sorának, az alapsor alapján. Több **CBR** formátumkód is szerepelhet a sorformátumban, mint például egy a nettó értékesítésnek, egy a bruttó értékesítésnek, és egy az összes költségnek. Általában a **CBR** formátumkód számlák százalékos részesedésének létrehozására használatos, amiket az összegzéssel hasonlítanak össze. Egy adott alapsort használunk minden számításhoz egészen addig, amíg egy másik alapsort nem definiálunk. Meg kell adnia egy kezdő **CBR** formátumkódot és egy záró **CBR** formátumkódot. Például ahhoz, hogy meghatározza a nettó értékesítés százalékában a költségeket, eloszthatja a értéket minden egyes költségsorban, a nettó értékesítés sorában szereplő értékkel. Ebben az esetben, a nettó értékesítési sor az alap sor. Megadhat egy oszlopdefiníciót, ami jelenti a jelenlegi eredményt és a folyó évben a mai dátumig elért eredményt, minden eredmény alapszázalékával, mint ahogy az látható a következő példában. Kezdjen a részletes bevétel-kimutatással.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Válassza ki az alapsort a sordefinícióban oszlopszámításhoz

1. A Jelentéstervezőben kattintson az Oszlopdefiníciók **elemre**, majd nyissa meg a kimutatás oszlopdefinícióját.
2. Adjon hozzá egy új oszlopot az oszlopdefinícióhoz, és állítsa be az oszlop típusát **CALC**-ra.
3. Az új oszlop **Képlet** cellájában, írja be a **X/ALAPSOR** képletet, ahol az **X** az **FD** oszloptípus a százalékos megjelenítéshez.
4. Kattintson duplán a Formátum **/pénznem felülbírálása cellára** .
5. A Formátum **felülbírálása** párbeszédpanel **Kategóriaformátum listájában** válassza ki a Százalék **lehetőséget**, majd kattintson az **OK gombra**.
6. A **Fájl** menüben, kattintson a **Mentés másként** parancsra, hogy új név alatt mentse az oszlopdefiníciót. Egy **CBR** hozzáfűzése az aktuális fájl névhez (például **CUR\_YTD\_CBR**). Ez az oszlopdefiníció lesz az Ön alaposzlop-definíciója.
7. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg azt a sordefiníciót, amelyet módosítani kell az alapsor-számítás segítségével.
8. Szúrjon be egy sort azon sor fölé, ahol az alapsor számításnak kezdődnie kell.
9. Kattintson duplán a sordefiníció **Formázási** kódcellájára, majd válassza a **CBR kódot**.
10. A **Kapcsolódó Képletek/Sorok/Egységek** cellában, adja meg az alapsor sorkód számát.

### <a name="example-of-base-row-calculation"></a>Alapsor számítási példa

A következő sordefiníció-példában, a 100. sor azt mutatja, hogy a számításokhoz használt alapsor a 280. sor.

[![Alapsor-számítási példa.](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png)

A következő egy oszlopdefiníció példában, a számítások a **CBR** kódformátumot használják. A számítás a C oszlopban elosztja a B oszlopban található jelentés értékét, a B oszlop 280-ik sorában lévő értékkel. A formátum felülírása a B oszlopban százalékként nyomtatja kis a számítás eredményét. Ehhez hasonlóan, minden összeg az E oszlopban a D oszlop összege, mint a nettó értékesítések százalékai.

[![Oszlopdefiníció-példa](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png)

A következő példa bemutat egy jelentést, ami az előző számítás alapján létrehozható.

[![Példajelentés az előző példa számítások alapján.](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Rendező kód kiválasztása sordefinícióhoz.
A rendezőkód rendezi a számlákat, vagy értékeket, rendezi az aktuális költségvetést vagy költségvetés eltérés jelentést a legnagyobb eltérés szerint, vagy betűrendbe rendezi a sorokat. Az alábbi rendezési kódok használhatók:

- **SORT** – A jelentést növekvő sorrendbe rendezi, az adott oszlopban szereplő értékek alapján.
- **ASORT** – A jelentést növekvő sorrendbe rendezi, az adott oszlopban szereplő értékek abszolút értékeinek alapján. Magyarul az előjelek nincsenek figyelembe véve az értékek sorba rendezésénél. Ez a formátumkód az értékeket az eltérés nagysága szerint rendezi, függetlenül attól, hogy az eltérés pozitív vagy negatív.
- **SORTDESC** – A jelentést csökkenő sorrendbe rendezi, az adott oszlopban szereplő értékek alapján.
- **ASORTDESC** – A jelentést csökkenő sorrendbe rendezi, az adott oszlopban szereplő értékek abszolút értékeinek alapján.

### <a name="select-a-sorting-code"></a>Rendezéskód választása

1. A Jelentéstervezőben kattintson a Sordefiníciók **elemre**, majd nyissa meg a módosítani szeretné a sordefiníciót.
2. Kattintson duplán a Formátumkód **cellára**, majd válasszon egy rendezési kódot.
3. A **Kapcsolódó Képletek/Sorok/Egységek** cellában, adja meg a rendezendő tartománysort. Tartomány megadásához, adja meg az első sorkódot, kettőspont (:), majd adja meg az utolsó sorkódot. Például, írja be a **160:490** kódot, amivel meghatározza a tartományt a 160-ik sortól a 490-ik sorig.
4. Az Oszlop korlátozási **cellában** adja meg a jelentésoszlopnak a rendezéshez használt betűét.

    > [!NOTE]
    > Csak összegsorokat vegyen bele a rendezési számításba.

### <a name="examples-of-ascending-and-descending-column-values"></a>Példák növekvő és csökkenő oszlop értékekre

A következő példában, a jelentés D oszlopában lévő értékek növekvő sorrendbe lesznek rendezve a 160. sortól a 490. sorig. Emellett a jelentés G oszlopának abszolút értékei csökkenő sorrendbe lesznek rendezve a 610. sortól a 940. sorig.

| Sorkód | Leírás                             | Formátumkód | Kapcsolódó képletek/Sorok/Egységek | Normál egyenleg | Oszlopkorlátozás | Csatolás pénzügyi dimenziókhoz |
|----------|-----------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Növekvő Sorrendbe Rendezve Havi Eltérés Szerint       | DES         |                |                |                    |                              |
| 130      |                                        | SORT        | 160:490                     |                | D                  |                              |
| 160      | Értékesítés                                   |             |                             | C              |                    | 4100                         |
| 190      | Értékesítési Visszáruk                        |             |                             |                |                    | 4110                         |
|          | ...                             |             |                             |                |                    |                              |
| 490      | Kamatbevétel              |             |                             | C              |                    | 7000                         |
| 520      |                                     | DES         |                             |                |                    |                              |
| 550      | Növekvő Sorrendbe Rendezve az Idei Abszolút Eltérés Szerint | DES         |             |                |                    |                              |
| 580      |                              | ASORTDESC   | 610:940                     |                | G:                  |                              |
| 610      | Értékesítés                     |             |                             | t              |                    | 4100                         |
| 640      | Értékesítési Visszáruk                |             |                             |                |                    | 4110                         |
|          | ...                       |             |                             |                |                    |                              |
| 940      | Kamatbevétel               |             |                             | K              |                    | 7000                         |


## <a name="specify-a-format-override-cell"></a>Formátum-felülbírálási cella megadása
A **Formátum felülbírálata** cella megadja a sorra vonatkozó formátumot a jelentés nyomtatása során. Ez a formázás felülírja az oszlopdefinícióban meghatározott és a jelentésdefinícióban meghatározott formátumot. Alapértelmezés szerint, pénznem a formázás megadott definíciókban. Ha a jelentés egyik sora az eszközök számát listázza, mint például az épületek számát, és egy másik sor az eszközöket pénzben kifejezett értékét listázza, akkor felülírhatod a pénznem formázást és átállíthatod az épületek számának sorát numerikus formázásra. Ezt az információt a Formátum felülbírálása **párbeszédpanelen** adhatja meg. A rendelkezésre álló beállítások a kijelölt formátum kategóriától függnek. A **Minta** része a párbeszédpanelnek a példa formátumokat mutatja. A következő formátum típusok érhetők el:

- Pénznem formázás
- Numerikus formázás
- Százalék formázás
- Egyéni formátum

### <a name="override-cell-formatting"></a>Cellák formázásnak felülírása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sordefiníciót.
2. A formátum felülbírálatának sorában kattintson duplán a cellára a **Formátum felülbírálása oszlopban** .
3. A Formátum **felülbírálása** párbeszédpanelen válassza ki a jelentés sorához használni kívánt formázási beállításokat.
4. Kattintson az **OK** gombra.

### <a name="currency-formatting"></a>Pénznem formázás

A Pénznem formázás a pénzügyi összegekre vonatkozik és tartalmazza a pénznem szimbólumát. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Pénznem jele** – A jelentésben használandó pénznemszimbólum. Ez az érték felülbírálja a **Területi Beállítások** vállalati információ beállításait.
- **Negatív számok** – A negatív számok rendelkezhetnek mínusz előjellel (-), szerepelhetnek zárójelben, vagy jelölhetőek háromszöggel (∆).
- **Tizedes jegyek** – A tizedesjel után megjelenítendő számjegyek száma.
- **Nullérték felülíró szövege** – Az a szöveg, amelyet 0 (nulla) értékeknél szeretne megjeleníteni a jelentésben. Ez a szöveg jelenik meg utolsó sorként a **Minta** területen.

    > [!NOTE]
    > Ha a nullértékek vagy a tevékenység nélküli időszakok nyomtatása le van tiltva, akkor ez a szöveg nem jelenik meg.

### <a name="numeric-formatting"></a>Numerikus formázás

A numerikus formázás minden összegre vonatkozik, és nem tartalmazza a pénznem szimbólumát. Az alábbi lehetőségek közül választhat:

- **Negatív számok** – A negatív számok rendelkezhetnek mínusz előjellel (-), szerepelhetnek zárójelben, vagy jelölhetőek háromszöggel (∆).
- **Tizedes jegyek** – A tizedesjel után megjelenítendő számjegyek száma.
- **Nullérték felülíró szövege** – Az a szöveg, amelyet 0 (nulla) értékeknél szeretne megjeleníteni a jelentésben. Ez a szöveg jelenik meg utolsó sorként a **Minta** területen.

    > [!NOTE]
    > Ha a nullértékek vagy a tevékenység nélküli időszakok nyomtatása le van tiltva, akkor ez a szöveg nem jelenik meg.

### <a name="percentage-formatting"></a>Százalék formázás

A százalékos formázás magában foglalja a százalékjelet (%). Az alábbi lehetőségek közül választhat:

- **Negatív számok** – A negatív számok rendelkezhetnek mínusz előjellel (-), szerepelhetnek zárójelben, vagy jelölhetőek háromszöggel (∆).
- **Tizedes jegyek** – A tizedesjel után megjelenítendő számjegyek száma.
- **Nullérték felülíró szövege** – Az a szöveg, amelyet 0 (nulla) értékeknél szeretne megjeleníteni a jelentésben. Ez a szöveg jelenik meg utolsó sorként a **Minta** területen.

    > [!NOTE]
    > Ha a nullértékek vagy a tevékenység nélküli időszakok nyomtatása le van tiltva, akkor ez a szöveg nem jelenik meg.

### <a name="custom-formatting"></a>Egyéni formázás

Az egyéni formázási kategória segítségével egyéni formátum-felülírást hozhat létre. Az alábbi lehetőségek közül választhat:

- **Típus** – Itt adható meg az egyéni formátum.
- **Nullérték felülíró szövege** – Az a szöveg, amelyet 0 (nulla) értékeknél szeretne megjeleníteni a jelentésben. Ez a szöveg jelenik meg utolsó sorként a **Minta** területen.

    > [!NOTE]
    > Ha a nullértékek vagy a tevékenység nélküli időszakok nyomtatása le van tiltva, akkor ez a szöveg nem jelenik meg.

A típus adja meg a pozitív értéket, majd a negatív értéket. Általában olyan, hasonló formátumot ad meg, amely különbséget tesz a pozitív és a negatív értékek között. Például, ha szeretné megadni, hogy a pozitív és a negatív értékek egyaránt két tizedesjeggyel jelenjenek meg, de a negatívak legyenek zárójelben, akkor a következőt írja be: **0.00;(0.00)**. Az alábbi táblázat bemutatja azokat az egyéni formázásokat, amelyekkel irányíthatja az értékek formázásait. A példák mind az 1234,56 értéktől indulnak.

| Formátum                         | Pozitív   | Negatív     | Nulla    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);""       | 1,235      | (1,235)      | (Üres) |
| \#,\#\#0.00;(\#,\#\#0.00);zero | 1,234.56   | (1,234.56)   | nulla    |
| 0.00%;(0.00%)                  | 123456.00% | (123456.00%) | 0.00%   |

## <a name="specify-a-normal-balance-cell"></a>Normál egyenleg cella megadása
A **Normál Egyenleg** cella a sordefinícióban, az adott sorban szereplő összegek előjelét szabályozza. Sor előjelének megfordítása, vagy ha egy számla normál egyenlege követel, írjon egy "C **·**  **" jelet az ahhoz a** sorhoz a Normál egyenleg cellába. A Jelentéstervező megfordítja az előjelét minden követelési egyenlegszámlának a sorban. Ha a jelentéstervező konvertálja ezeket a számlákat, akkor eltávolítja az összes összeg terhelési/jóváírási jellemzőit, ezáltal egyértelművé teszi az összesítést. Például, a nettó jövedelem kiszámításához ki kell vonni a kiadásokat a bevételből. Általában az összegzett és számított sorokra nincs hatással a **C** kód. Az oszlopdefinícióban található XCR-nyomtatási **vezérlő azonban megfordítja minden olyan sor előjelét, amely C**  **jelet tartalmaz a** Normál egyenleg oszlopban **.**  Ez a formázás különösen akkor fontos, ha negatív összegeként kívánja megjeleníteni az összes kedvezőtlen eltérést. Ha egy összegző vagy számított szám előjele nem megfelelő, írjon be egy **C**  **jelet a Normál egyenleg cellába, hogy a** sor megfordítsa az előjelet.

## <a name="specify-a-row-modifier-cell"></a>Sormódosító cella megadása
A sordefiníció **sormódosítócella**-tartalma felülbírálja az adott sor pénzügyi évét, időszakát és egyéb adatait. A kijelölt módosító minden számlára vonatkozik a sorban. Bármely sort módosíthat az alábbi módosítók közül egy vagy több használatával:

- Számlamódosítók
- Könyvelési kód módosítók
- Számla és tranzakció attribútumok

### <a name="override-a-column-definition"></a>Oszlopdefiníció felülírása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sordefiníciót.
2. Annak a sornak a sorában, ahol felül szeretné írni az oszlopdefiníciót, **kattintson duplán a Sormódosító cellára** .
3. A Sor **módosító párbeszédpanelen** válasszon egy beállítást az **Számlamódosító mezőben** . A lehetőségek leírását lásd a „Számlamódosítók” részben.
4. A **Könyvelés kód módosító** mezőben, válassza ki a sorra használandó könyvelési kódot.
5. Az **Attribútumok** részen végezze el az alábbi lépéseket minden olyan attribútumnál, amelyet hozzá kíván adni a sorkódhoz:

    1. Kattintson duplán az **Attribútum** cellára, és válassza ki az attribútum nevét.

        > [!IMPORTANT]
        > Cserélje ki a számot jelölő kettős keresztet (\#) egy számértékre.

    2. Kattintson duplán a **Kezdő érték** cellára, majd írja be a tartomány első értékét.
    3. Kattintson duplán a **Záró érték** cellára, majd írja be a tartomány utolsó értékét.

6. Kattintson az **OK** gombra.

### <a name="account-modifiers"></a>Számlamódosítók

Ha kiválaszt egy adott számlát, a jelentéstervező általában összekombinálja azt a pénzügyi évvel, az időszakokkal és azon egyéb információkkal, amelyeket a oszlopdefinícióban megadott. Adott sorokhoz, használhat különböző információkat, mint például különböző pénzügyi időszakokat. A következő táblázat az elérhető számlamódosítókat mutatja. A kettős kereszt (\#) szimbólumot cserélje le olyan számra, amely egyenlő vagy kisebb a pénzügyi év időszakainak számánál.

| Számlamódosító | A nyomtatott                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | Egy számla kezdő egyenlege.                                                     |
| /\#              | A megadott időszak egyenlege.                                                     |
| /-\#             | Azon időszak egyenlege, amely \# időszakkal megelőzi az aktuális időszakot.                  |
| /+\#             | Azon időszak egyenlege, amely \# időszakkal az aktuális időszak után következik.                   |
| /C               | A jelenlegi időszak egyenlege.                                                       |
| /C-\#            | Azon időszak egyenlege, amely \# időszakkal megelőzi az aktuális időszakot.                  |
| /C+\#            | Azon időszak egyenlege, amely \# időszakkal az aktuális időszak után következik.                   |
| /Y               | Az aktuális év eddigi egyenlege a jelenlegi időszakban.                                      |
| /Y-\#            | Az aktuális év eddigi egyenlege addig az időszakig, ami \# periódussal van a jelenlegi periódus előtt. |
| /Y+\#            | Az aktuális év eddigi egyenlege addig az időszakig, ami \# periódussal van a jelenlegi periódus után.  |

### <a name="book-code-modifiers"></a>Könyvelési kód módosítók

Korlátozhatja a sort egy meglévő könyvelési kódra. A oszlopdefiníciónak tartalmaznia kell legalább egy könyv kódot tartalmazó **FD** oszlopot.

> [!NOTE]
> A könyvelési kód sorhoz tartozó korlátozása felülírja az oszlopdefiníció könyvelési kódjának korlátozásait az adott sorra.

### <a name="account-and-transaction-attributes"></a>Számla és tranzakció attribútumai

Néhány könyvelési rendszer támogatja a számla attribútumokat és a tranzakció attribútumokat a pénzügyi adatokban. Ezek az attribútumok virtuális fiók szegmensekként működnek, és kiegészítő információt hordozhatnak a számláról vagy a tranzakcióról. Ezek a kiegészítő információk lehetnek számla azonosítók, kötegelt azonosítók, irányítószámok vagy más jellemzők. Ha a könyvelési rendszer támogatja az attribútumokat, használhat számla attribútumokat vagy tranzakció attribútumokat sor módosítókként a sordefinícióban. A sor információ felülbírálásával kapcsolatos tudnivalókat a „Oszlopdefiníció felülírása” korábban ismertetett részében találja.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>A pénzügyi dimenziók cellára mutató hivatkozás megadása
A **Hivatkozás a pénzügyi dimenziókra** cella hivatkozásokat tartalmaz a pénzügyi adatokra, amelyek a jelentés minden sorában szerepelniük kell. Ez a cella dimenzióértékeket tartalmaz. A Dimenziók párbeszédpanel **megnyitásához** kattintson duplán **a Pénzügyi dimenziókhoz kapcsolás cellára** .

> [!NOTE]
> A jelentéstervező nem választhat olyan számlákat, Microsoft Dynamics dimenziókat és mezőket a 365-ös pénzügyi rendszerből, amelyek a következő foglalt karaktereket tartalmazzák: &, \*, \[, \], { vagy }. Ha olyan sor adatait szeretne megadni, amelyek már a sordefinícióban vannak, **adja hozzá az adatokat a Hivatkozás pénzügyi dimenziókhoz cellába** . Pénzügyi adatokra hivatkozó új sorok hozzáadásához,használja a **Sor Beszúrása a** párbeszédpanelt, új sorok létrehozásához a jelentés definícióban. A következő táblázat bemutatja, hogy az oszlop címe attól függően változik, hogy hogyan konfigurálta az oszlopot.

| A kiválasztott hivatkozás típusa       | A Hivatkozás oszlop leírása erre változik |
|----------------------------------|----------------------------------------------------|
| Pénzügyi Dimenziók             | Hivatkozás pénzügyi dimenziókra                       |
| Munkalapjelentés                 | Pénzügyi jelentéskészítési jelentés                         |

### <a name="specify-a-dimension-or-range"></a>Dimenzió vagy tartomány megadása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sordefiníciót.
2. Kattintson duplán a Pénzügyi dimenziókhoz kapcsolás **oszlop egyik cellára** .
3. A **Dimenziók** párbeszédpanelen kattintson duplán egy cellára a dimenzió neve alatt.
4. A dimenzióhoz a párbeszédpanelen, válassza az **Egyéni vagy tartomány**-t.
5. A **Kezdő** mezőben adja meg a kezdő dimenziót, vagy kattintson a ![Tallózás.](media/browse.gif "Tallózás") elemre a rendelkezésre álló dimenziók kereséséhez. Dimenziók tartományának megadásához adja meg az utolsó dimenziót az **Idáig** mezőben.
6. Kattintson az **OK** gombra, a dimenziók párbeszédpaneljának bezárásához. A **Dimenziók** párbeszédpanel a frissített dimenziókészletet vagy tartományt jeleníti meg.
7. Kattintson az **OK** gombra hogy bezárja a **Dimenziók** párbeszédpanelt.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Megjeleníti a nulla egyenlegű számlákat a sordefinícióban
Alapértelmezés szerint a jelentéstervező nem nyomtat ki olyan sorokat, amelyekhez nem tartozik egyenleg a pénzügyi adatok között. Ezért létrehozhat egy olyan sordefiníciót, amely minden természetes szegmensértéket vagy minden dimenzióértéket tartalmaz, majd ezt a sordefiníciót bármely részlegre alkalmazhatja.

### <a name="modify-zero-balance-settings"></a>Nulla egyenleg beállításainak módosítása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges jelentésdefiníciót.
2. A **Beállítások** lap **Egyéb formázás** részén válassza ki a sordefinícióhoz a jelentésdefinícióban használt beállításokat.
3. A módosítások mentéséhez kattintson a **Fájl** menü **Mentés** parancsára.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Helyettesítő karakterek és a tartományok használata a sordefinícióban
Ha természetes szegmensértéket ír be a **Dimenziók** párbeszédpanelen, helyettesítő karaktereket (? vagy \*) is elhelyezhet a szegmens bármely részén. A Jelentéstervező a meghatározott karakterekre vonatkozóan minden értéket előhív, a helyettesítő karakterek figyelembevétele nélkül. Például, a sordefiníció csak természetes szegmensértékeket tartalmaz, és a természetes szegmensek négy karakteresek. **6???** megadásával egy sorban arra utasítja a jelentéstervezőt, hogy minden olyan számlát hívjon elő, amelynek természetes szegmensértéke 6-os számmal kezdődik. Ha a **6\**_ kódot írja be, ugyanezeket a számlákat kapja meg, de ebben az esetben a rendszer minden hosszúságú értéket ki fog keresni, így a _* 60** és **600000** számút is. A jelentéstervező minden (?) helyettesítő karakter helyére a lehetséges értékek teljes tartományát behelyettesíti, ide értve a betűket és a különleges karaktereket is. Például ha a tartomány kezdete a **12?0**, a vége pedig **12?4**, akkor a **12?0** kód helyettesítő karaktere helyére behelyettesíti a karakterkészlet legalacsonyabb érétkét, a **12?4** kódban pedig a legmagasabb értéket.

> [!NOTE]
> A számlatartományok kezdő és záró értékeinél lehetőség szerint ne használjon helyettesítő karaktert. Ha a kezdő számlánál vagy a záró számlánál helyettesítő karaktert használ, előfordulhat, hogy nem a várt eredményt kapja.

### <a name="single-segment-or-single-dimension-ranges"></a>Egyetlen-szegmenses vagy egyetlen-dimenziós tartományok

Megadhat egy tartományt a szegmens értékekhez vagy a dimenzió értékekhez. Egy értéktartomány meghatározásának az az előnye, hogy nem kell minden alkalommal frissítenie a sordefiníciót, valahányszor új szegmensértéket vagy dimenzióértéket adnak hozzá a pénzügyi adatokhoz. Például ha a tartomány értéke **+Számla=\[6100:6900\]** =, akkor a rendszer a 6100-tól 6900-ig tartó számlák értékeit tölti be a sorösszegbe. Ha egy tartomány tartalmaz egy helyettesítő karaktert (?), akkor a jelentéstervező nem értékeli ki a tartományt karakterenként. Ehelyett a tartomány alsó és felső végét állapítja meg, majd ezt a kettőt és a köztük levő összes értéket figyelembe veszi.

> [!NOTE]
> A jelentéstervező nem választhat olyan számlákat, Microsoft Dynamics dimenziókat és mezőket a 365-ös pénzügyi rendszerből, amelyek a következő foglalt karaktereket tartalmazzák: &, \*, \[, \], { vagy }. És (&) **csak akkor adhat hozzá és csak akkor, ha a sordefiníciók automatikus létrehozása a Sorok beszúrása a dimenziókból** párbeszédpanelen történik.

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Több-szegmenses vagy több-dimenziós tartományok

Ha több dimenzióérték kombinálásával adja meg a tartományt, akkor a tartomány-összehasonlítást a rendszer ..\\financial-dimensions\\dimension-by-dimension végzi el. A tartomány-összehasonlítás nem hajtható végre karakterenkénti módszerrel, sem részleges szegmens alapján. Például, a **+Számla=\[5000:6000\], Részleg=\[1000:2000\], Költséghely=\[00\]** tartomány csak azokat a számlákat tartalmazza, amelyek minden egyes szegmenssel megegyeznek. Ebben a példában, az első dimenziónak az 5000-től 6000-ig terjedő tartományba, a második dimenziónak az 1000 és a 2000 közötti tartományba kell esnie, az utolsó dimenziónak pedig 00-nak kell lennie. Ezért például a **+Számla=\[5100\], Részleg=\[1100\], Költséghely=\[01\]** kombináció nem fog bekerülni a jelentésbe, mivel az utolsó szegmens a megadott tartományon kívül esik. Ha egy szegmensérték szóközt is tartalmaz, ezt a karaktert tegye szögletes zárójelbe (\[ \]). A következő értékek érvényesek egy négy karakterből álló szegmensnek: **\[ 234\], \[123 \], \[1 34\]**. A dimenzióértékeket is szögletes zárójelben (\[ \]) kell megadni, a jelentéstervező pedig automatikusan hozzáadja ezeket a zárójeleket. Ha több szegmenst vagy több dimenziót magába foglaló tartomány helyettesítő karaktereket (? vagy \*) is tartalmaz, akkor a rendszer meghatározza a teljes többszegmenses vagy többdimenziós tartomány alsó és felső értékét, majd hozzáveszi az ezek között található összes értéket. Nagyméretű tartomány esetén ( amilyen például az összes számla 40000-től 99999-ig) lehetőleg minden esetben érvényes kezdő és záró számlát adjon meg.

> [!NOTE] 
> A jelentéstervező nem választhat olyan számlákat, Microsoft Dynamics dimenziókat és mezőket a 365-ös pénzügyi rendszerből, amelyek a következő foglalt karaktereket tartalmazzák: &, \*, \[, \], { vagy }. És (&) **csak akkor adhat hozzá és csak akkor, ha a sordefiníciók automatikus létrehozása a Sorok beszúrása a dimenziókból** párbeszédpanelen történik.

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Hozzáadás vagy kivonás sordefinícióban más számlákhoz
Ha szeretné hozzáadni vagy kivonni egy számla pénzösszegét egy másikhoz, akkor a plusz (+) és mínusz (-) jeleket is használhatja a **Hivatkozás a pénzügyi dimenziókhoz** cellában. Az alábbi táblázat elfogadható formátumokat mutat, hozzáadás és kivonás hivatkozásokra a pénzügyi adatokban.

| Művelet                                            | Használja ezt a formátumot                                                                                              |
|----------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Adjon hozzá két teljesen minősített számlát.      | +Osztály=\[000\], Számla=\[1205\], Részleg=\[00\]+Osztály=\[100\], Számla=\[1205\], Részleg=\[00\] |
| Adjon hozzá két szegmensértéket.                    | +Számla=\[1205\]+Számla=\[1210\]                                                                           |
| Adjon hozzá olyan szegmensértékeket, amelyek helyettesítő karaktereket is tartalmaznak.  | +Számla=\[120?+Számla=\[11??\]                                                                     |
| Adjon hozzá egy minősített számlák tartományt.              | +Osztály=\[000:100\], Számla=\[1205\], Részleg=\[00\]                                           |
| Adja hozzá szegmensértékek tartományát.                | +Számla=\[1200:1205\]                                                                                       |
| Adja hozzá olyan szegmensértékek tartományát, amelyek helyettesítő karaktereket is tartalmaznak.         | +Számla=\[120?:130?\]                                                           |
| Egy teljesen minősített számla kivonása egy másikból.              | +Osztály=\[000\], Számla=\[1205\], Részleg=\[00\]-Osztály=\[100\], Számla=\[1205\], Részleg=\[00\] |
| Egy szegmensérték kivonása egy másikból.          | +Account=\[1205\]-Account=\[1210\]                                                               |
| Egy helyettesítő karaktert is tartalmazó szegmensérték kivonása egy másikból. | +Számla=\[1200\]-Számla=\[11??\]                                        |
| Teljesen minősített számlák tartományának kivonása.                               | -Osztály=\[000:100\], Számla=\[1200:1205\], Részleg=\[00:01\]                   |
| Szegmensértékek tartományának kivonása.                   | -Számla=\[1200:1205\]                                                                                       |
| Helyettesítő karaktereket is tartalmazó szegmensértékek tartományának kivonása.                    | -Számla=\[120?:130?\]                                               |

Annak ellenére, hogy közvetlenül módosíthatja a számlákat, használhatja a **Dimenziók** párbeszédpanelt, hogy a helyes formátumot alkalmazza a pénzügyi adat hivatkozásokra. Bármely értékek tartalmazhatnak helyettesítő karaktereket (? vagy \*). Azonban a Jelentéstervező nem tud olyan számlákat, dimenziókat vagy mezőket választani a Microsoft Dynamics ERP rendszerből, melyek nevében szerepelnek a következő különleges karakterek: &,\*, \[, \], {, vagy }.

> [!NOTE]
> Kivonás esetén az értékeket zárójelbe kell helyeznie. Ha például a **450?-(4509)** képletet adja meg, az a következőképpen jelenik meg: **+Számla=\[4509\]-Számla=\[450?\]**, ezzel pedig arra utasítja a jelentéstervezőt, hogy vonja ki a 4509 számlaszegmens összegét bármely azon számlaszegmens összegéből, amelynek száma 450-nel kezdődik.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Számlák hozzáadása vagy kivonása más számlákból

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sordefiníciót.
2. A megfelelő sorban kattintson duplán a Pénzügyi dimenziókhoz oszlopban **található cellára** .
3. A **Dimenziók** párbeszédpanel első sorában, kövesse az alábbi lépéseket:

    1. Az első mezőben válasszon ki minden dimenziót (alapértelmezett), **vagy** kattintson ide a Dimenziókészletek kezelése párbeszédpanel megnyitásához, ahol létrehozhat, módosíthat, másolhat vagy törölhet egy készletet.
    2. Kattintson duplán a **+/- műveleti jel** cellára, és válassza a plusz (**+**) vagy a mínusz (**-**) jelet, amelyet a sor egy vagy több dimenzióértékére vagy készleteire alkalmazni kíván.
    3. A vonatkozó dimenzióérték-oszlopban kattintson duplán a cellára, hogy megnyissa a **Dimenziók** párbeszédablakot, majd válassza ki, hogy az adott dimenzióérték egyedi vagy tartomány, dimenzióérték-készlet, vagy összesítő számla. A **Dimenziók** párbeszédpanelen a mezők leírásához lásd „A dimenzió párbeszédpanel leírása” című részt.
    4. Adjon meg szegmensértékeket a **Kezdő érték** és a **Záró érték** oszlopban.

4. További műveleti jelek hozzáadásához ismételje meg a 2–3. lépéseket.

> [!NOTE]
> A műveleti jel a sorban szereplő összes dimenzióra vonatkozik.

## <a name="description-of-the-dimensions-dialog-box"></a>A Dimenziók párbeszédpanel leírása
Az alábbi táblázat bemutatja a **Dimenziók** párbeszédpanelben megjelenő mezőket.

| Cikk                | Leírás |
|---------------------|-------------|
| Egyéni vagy tartományi | A **Kezdő érték** mezőben adja meg egy számla nevét, vagy kattintson a **Tallózás** gombra ![Tallózás.](media/browse.gif "Tallózás") , ha tallózással szeretné megkeresni a számlát. Tartomány kiválasztásához, adjon meg, vagy keressen egy értéket a **Záró érték** mezőben. |
| Dimenzióérték Beállítása | A **Név** mezőbe írja be a dimenzióérték-készlet nevét. Készlet létrehozásához, módosításához, másolásához, vagy törléséhez, kattintson a **Dimenziókészletek Értékének Kezelése** gombra. A **receptúra** mezőjébe **a** sordefinícióban beállított dimenzióérték Hivatkozás pénzügyi dimenziókhoz cellájában található képlettel van feltöltve. |
| Számlák összesítése   | A **Név** mezőbe írja be vagy tallózással keresse meg az összesítő számlákra vonatkozó dimenziót. A **jelentésdefinícióban**  **a** Receptúra mezőt a pénzügyi dimenziókhoz kapcsolás cellában lévő képlet tölti fel a jelentésdefinícióban az összegszámla számára. |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Dimenzióérték készletek hozzáadása sordefinícióban
A dimenzióérték-készlet dimenzióértékeket elnevezett csoportja. Egy dimenzióérték-készlet csakis egy dimenziós értékeket tartalmazhat, de egy dimenzió-érték készletet használhat többszörös sordefiníciókban, oszlop definíciókban, jelentésfa definíciókban és jelentés definíciókban. Ezenkívül, a jelentés definícióban kombinálhat dimenzióérték-készleteteket. Amikor a pénzügyi adatok módosítása megköveteli, a dimenzióérték-készlet változtatását, frissítheti a dimenzióérték-készlet definíciót, és ez a frissítés minden területre alkalmazva lesz, amik ezt a dimenzióérték-készletet használják. Például ha gyakran használ értéktartományt a pénzügyi adatokra való hivatkozáshoz, például a 5100-5600 közötti értékeket, akkor ezt a tartományt hozzárendelheti például egy olyan számlakészlethez, amelynek az Értékesítés nevet adja. Miután létrehozott egy dimenzióérték-készletet, hozzákapcsolhatja ezt a készletet a pénzügyi adatokhoz. Egy másik példa: ha az 5100-től 5600-ig terjedő értéktartományt hozzárendeli az Értékesítés készlethez, a 4175-öt pedig a Kedvezményekhez, akkor a teljes értékesítés összegét meghatározhatja úgy, hogy a Kedvezmények értékét kivonja az Értékesítés értékéből. Ezt a műveletet a **(5100:5600)-4175** kód jelöli.

### <a name="create-a-set-of-dimension-values"></a>Dimenzióérték készlet létrehozása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sort, oszlopot vagy fadefiníciót.
2. Kattintson a **Szerkesztés** menü Dimenzióérték-készletek **kezelése parancsára**.
3. A Dimenzióérték-készletek kezelése párbeszédpanel Dimenzió mezőjében válassza ki a létrehozni kívánt dimenzióérték-készlet típusát, majd kattintson az Új **gombra** . **·**  **·**
4. Az **Új** párbeszédpanelen adja meg a készlet nevét és leírását.
5. A **Kezdő érték** oszlopban kattintson duplán a cellában.
6. A **Számla** párbeszédpanelen a listában válassza ki a számla nevét, vagy keressen ki egy bejegyzést a **Keresés** mezőben. Ezután kattintson az **OK** gombra.
7. Ismételje meg a 5–6. lépést a **Záró érték** oszlopban is, így összeállíthatja a művelet képletét.
8. Amikor a képlet kész, kattintson az **OK** gombra.
9. A Dimenziókészletek **kezelése párbeszédpanelen** kattintson a Bezárás **gombra**.

### <a name="update-a-set-of-dimension-values"></a>Dimenzióérték-készlet frissítése

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sort, oszlopot vagy fadefiníciót.
2. Kattintson a **Szerkesztés** menü Dimenzióérték-készletek **kezelése parancsára**.
3. A Dimenzióérték-készletek **·**  **kezelése** párbeszédpanel Dimenzió mezőjében válassza ki a dimenzió típusát.
4. A listában válassza ki a frissíteni kívánt dimenzióérték-készletet, majd kattintson a **Módosítás** gombra.
5. A **Módosítás** párbeszédpanelben, módosítsa a készletben szerepeltetendő képlet értékét.

    > [!NOTE]
    > Ha új számlákat vagy dimenziókat ad hozzá, akkor ügyeljen, hogy módosítsa a már meglévő dimenzióérték-készleteket, hogy azok a módosításokat is magukba foglalják.

6. Kattintson duplán a cellára, majd válassza ki a megfelelő műveleti jelet, a **Kezdő érték** és a **Záró érték** számlát.
7. Kattintson az **OK** gombra, ezzel bezárja a **Módosítás** párbeszédablakot, és menti a változtatásokat.

### <a name="copy-a-dimension-set"></a>Dimenzióérték-készlet másolása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sort, oszlopot vagy fadefiníciót.
2. Kattintson a **Szerkesztés** menü Dimenzióérték-készletek **kezelése parancsára**.
3. A Dimenzióérték-készletek **·**  **kezelése** párbeszédpanel Dimenzió mezőjében válassza ki a dimenzió típusát.
4. Válassza ki a másolni kívánt készletet a listán, majd kattintson a Mentés másként **gombra**.
5. Adjon meg egy új nevet a másolt készletnek, és kattintson az **OK** gombra.

### <a name="delete-a-dimension-set"></a>Dimenziókészlet törlése

1. A Jelentéstervezőben nyissa meg a módosítani szükséges sort, oszlopot vagy fadefiníciót.
2. Kattintson a **Szerkesztés** menü Dimenzióérték-készletek **kezelése parancsára**.
3. A Dimenzióérték-készletek **·**  **kezelése** párbeszédpanel Dimenzió mezőjében válassza ki a dimenzió típusát.
4. Jelölje ki a törölni kívánt készletet, és kattintson a **Törlés** gombra. Kattintson az **Igen** gombra a dimenzióérték-készlet végleges törléséhez.

## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
