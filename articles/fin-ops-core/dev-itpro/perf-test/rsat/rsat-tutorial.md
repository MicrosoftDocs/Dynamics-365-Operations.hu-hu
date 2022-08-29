---
title: Regression suite automation tool-oktatóanyag
description: Ez a cikk bemutatja a Regression suite automatizálási eszköz (RSAT) használatát. Leírja a különböző funkciókat, és speciális parancsfájlkezelést használó példákat tartalmaz.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: a270398ddebef0f47a2c31b0ffb022e3df6489c7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277404"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Regression Suite Automation Tool-oktatóanyag

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Az internetböngésző eszközeivel letöltheti és mentheti ezt a lapot PDF-formátumban.

Ez az oktatóanyag végigvezet a Regression Suite Automation Tool (RSAT) néhány speciális funkcióján, tartalmaz bemutatófeladatot, és leírja a stratégiát és a fontos tanulási pontokat is.

## <a name="notable-features-of-rsat-and-task-recorder"></a>A RSAT és a Feladatrögzítő fontos jellemzői

### <a name="validate-a-field-value"></a>Egy mezőérték ellenőrzése

A RSAT ellenőrzési lépéseket tesz lehetővé a tesztesetéhez a várt értékek érvényesítéséhez. Ha további tájékoztatást szeretne erről a funkcióról, olvassa el a [Várható értékek érvényesítése](rsat-validate-expected.md) című cikket.

A következő példa bemutatja, hogyan használható ez a funkció annak ellenőrzésére, hogy az aktuális készlet nagyobb mint 0 (nulla).

1. Hozzon létre egy olyan feladatrögzítést a **USMF** vállalat bemutató adatai között, amelynek a következő lépései vannak:

    1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
    2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön az **1000** értékre a **Cikkszám** mezőben.
    3. Válassza az **Aktuális készlet** elemet.
    4. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön az **1** értékre a **Telephely** mezőben.
    5. A listában jelölje meg a kiválasztott sort.
    6. Ellenőrizze, hogy az **Összes rendelkezésre álló** mező értéke **411,0000000000000000**.

2. A feladatrögzítés mentése fejlesztői rögzítésként, **és csatolása a** tesztesethez a következőben:Azure DevOps
3. Adja hozzá a tesztesetet a tesztelési tervhez, és töltse be a tesztesetet a RSAT-be.
4. Nyissa meg az Excel paraméterfájlt, és ugorjon a **TestCaseSteps** laphoz.
5. Ha ellenőrizni kell, hogy az aktuális készlet mindig nagyobb-e, mint **0**, lépjen az **Összes rendelkezésre álló** ellenőrzése lépéshez, és módosítsa az **411** értéket **0** értékre. Módosítsa a **Kezelő** mező értékét egyenlőség jelről (**=**) nagyobb, mint (**\>**) jelre.
6. Mentse és zárja be az Excel-paraméterfájlt.
7. A **Feltöltés** gombra kattintva mentheti a módosításokat az Azure DevOps rendszerbe, amelyeket az Excel-paraméterfájlban tett.

Ha most a megadott cikk **Összes rendelkezésre álló** mezője értéke meghaladja a 0 (nulla) értéket, akkor a tesztek sikeresek lesznek, függetlenül a tényleges aktuális készlet értékétől.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Mentett változók és a tesztesetek láncolása

A RSAT egyik alapvető funkciója a tesztesetek láncolása, tehát az a képesség, amellyel egy teszt változókat adhat át más teszteknek. A további tudnivalókat lásd a [Változók másolása tesztesetekre](rsat-chain-test-cases.md) című cikkben.

### <a name="derived-test-case"></a>Származtatott teszteset

A RSAT használatával több feladatrögzítést is felhasználhat több tesztesettel így a feladatok különböző adatkonfigurációkkal futtathatók. További tájékoztatás a [Származtatott tesztesetek](rsat-derived-test-cases.md) cikkben található.

### <a name="validate-notifications-and-messages"></a>Értesítések és üzenetek érvényesítése

Ez a funkció annak ellenőrzésére használható, hogy történt-e művelet. Például egy termelési rendelés létrehozása, becslése, majd elindítása történt, megjelenik a „Termelés – Indítás” üzenetet, amellyel értesíti, hogy a termelési rendelés elindult.

![Termelés – Indítás értesítés.](./media/use_rsa_tool_05.png)

Ezt az üzenetet a RSAT programon keresztül ellenőrizni lehet, ha megadja az üzenet szövegét a megfelelő rögzítéshez tartozó Excel paraméterfájl **MessageValidation** lapján.

![Üzenet ellenőrzése lap.](./media/use_rsa_tool_06.png)

Miután lefutott a teszteset, az Excel-paraméterfájlban szereplő üzenetet a program összehasonlítja az üzenettel. Ha az üzenetek nem egyeznek, a teszteset nem fog sikerülni.

> [!NOTE]
> Az Excel-paraméterfájl **MessageValidation** lapján egynél több üzenetet is megadhat. Az üzenetek a tájékoztató üzenetek helyett hiba- vagy figyelmeztető üzenetek is lehetnek.

### <a name="snapshot"></a>Pillanatkép

Ez a funkció képernyőképeket készít a feladatrögzítés során végrehajtott lépésekről. Ez a ellenőrzés vagy hibakeresés céljából hasznos.

- A funkció használatához az RSAT futtatása során felhasználói felülettel nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elemet **hamis** értékről **igaz** értékre.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- A funkció használatához az RSAT futtatása CLI-n keresztül (például Azure DevOps) nyissa meg a **Microsoft.Dynamics.ConsoleApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elemet **hamis** értékről **igaz** értékre.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Tesztesetek futtatásakor az RSAT pillanatképeket (képeket) készít a lépésekről, és menti azokat a munkakönyvtárban található tesztesetek mappájában. Az mappában egy külön almappa jön létre **StepSnapshots** nevű mappában. Ez a mappa a futtatott tesztesetek pillanatképét tartalmazza.

## <a name="assignment"></a>Hozzárendelés

### <a name="scenario"></a>Forgatókönyv

1. A termék tervezője létrehoz egy új kiadott terméket.
2. A termelési vezető kezdeményez egy termelési rendelést, hogy a készlet szintje két darabra növekedjen.
3. A gyártás elindítja és befejezi a termelési rendelést, és ellenőrzi, hogy a készleten lévő mennyiség két darab.
4. Az értékesítési csoport rendelést kap négy darabra az új termékből. Ezért az értékesítési csoport frissíti a nettó szükségletet a dinamikus terven keresztül. Mivel nem áll rendelkezésre további kapacitás, az alapértelmezett rendelési irányelv beállítása „vásárlás gyártás helyett”. Így létrejön egy tervezett beszerzési rendelés.
5. A vevő hozzáadja a szállítót, megerősíti a tervezett beszerzési rendelést, majd megerősíti a beszerzési rendelést.
6. Amikor a megvásárolt áruk megérkeznek az üzletbe, az üzlet operátora megkeresi a kapcsolódó beszerzési rendelést, és bevételezi az árukat. Mivel a rendelést már befejeződött, az árukat az értékesítési rendeléshez lehet kitárolni és csomagolni.
7. A pénzügy felad egy beszerzési számlát és egy értékesítési számlát.

A következő ábra bemutatja az adott eset folyamatát.

![A bemutató eset folyamata.](./media/use_rsa_tool_14.png)

A következő ábra bemutatja az üzleti folyamatok hierarchiáját ehhez a forgatókönyvhöz az LCS Üzletifolyamat-modellező moduljában.

![A bemutató eset üzleti folyamatai.](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Stratégia – Kulcsfontosságú tanulási pontok

### <a name="data"></a>Adatok

- Győződjön meg róla, hogy rendelkezik reprezentatív adatmennyiséggel (termelési/arany konfigurációs adatok másolata és áttelepített adatok).
- Amikor a feladatrögzítőn keresztül új adatokat hoz létre, olyan tesztneveket hozzon létre, amelyek nem ütköznek a meglévő nevekkel (például használjon **RSATxxx** előtagot).
- Az Azure Időponthoz kötött visszaállítás használatával futtassa újra a teszteket a nem 1. szintű környezetekben.
- Annak ellenére, hogy a **RANDOM** és **NOW** Excel-funkciók segítségével egyedi kombinációt generálhat, az erőfeszítés jelentősen magas. Íme, egy példa.

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Feladatrögzítő

- Forgatókönyvek meghatározása a rögzítés megkezdése előtt. A jól kezelt projekt előre meghatározott teszt-forgatókönyveket tartalmaz. Egy teszteset létrehozásakor vegye figyelembe, hogy mennyire kiszámítható a tesztesetek kimenete.
- Ossza fel a rögzítéseket, ha különböző szerepkörök hajtják őket végre, vagy ha várakozási idő van, vagy külső esemény történik a következő lépés előtt.
- Ne válassza ki listákban szereplő értékeket. Ehelyett használjon szöveges formátumokat, mint **FIFO**, **AudioRM**, és **SiteWH**. Ha listából választ, az érték listában elfoglalt pozícióját rögzíti, nem magát az értéket. Ha elemeket adnak hozzá az adott listához, az adott érték pozíciója megváltozhat. Emiatt a rögzítés más paramétert fog használni, és ez a többi forgatókönyvet is érintheti.
- Gondoljon a többfelhasználós viselkedésre is. Például ne feltételezze, hogy mindig az újonnan létrehozott értékesítési rendelést jelöli ki automatikusan a rendszer. Ehelyett mindig használjon szűrőket a helyes rendelés megkereséséhez.
- A Feladatrögzítő Másolás funkciójával mentse el az újonnan létrehozott termék nevét, így használhatja láncolt tesztesetekben.
- A Feladatrögzítő Ellenőrzés funkciójával határozzon meg ellenőrzési pontokat, amelyek ellenőrzik, hogy a lépések megfelelően futottak le.

### <a name="rsat"></a>RSAT

- Ha egy másik vállalatnál szeretné futtatni a tesztet, módosíthatja a vállalatot az Excel-paraméterfájl **Általános** lapján. Győződjön meg róla, hogy a beállítások és az adatok elérhetők az újonnan kiválasztott vállalatnál.
- A tesztfelhasználót az Excel-paraméterfájl **általános** lapján lehet módosítani. Adja meg annak a felhasználónak az e-mail-azonosítóját, aki futtatja a tesztesetet. Ily módon a teszteset a megadott felhasználó biztonsági engedélyeinek használatával futtatható.
- Ha szeretne várni a teszt elindítása előtt, akkor az Excel-paraméterfájl **Általános** lapján megadhat egy szünetet. Ez a szünet kötegelt feladatban is használható (például akkor, ha egy munkafolyamatot a következő lépés végrehajtása előtt futtatni kell.)

## <a name="advanced-scripting"></a>Speciális parancsfájlkezelés

### <a name="cli"></a>CLI

Az RSAT-ot a **Parancssor** vagy a **PowerShell** ablakból is be lehet hívni.

> [!NOTE]
> Győződjön meg róla, hogy a **TestRoot** környezeti változó az RSAT telepítési útvonalára van állítva. (Microsoft Windows rendszerben nyissa meg a **Vezérlőpult** elemet, válassza a **Rendszer és biztonság \> Rendszer \> Speciális rendszerbeállítások** menüpontot, majd válassza a **Környezet változók** lehetőséget.)

1. Nyissa meg a **Parancssor** vagy **PowerShell** ablakot rendszergazdaként.
2. Keresse meg a RSAT telepítési könyvtárat.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Listázza az összes parancsot.

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        downloadsuite
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitebyid
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        playbacksuitebyid
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

Felsorolja a parancsokat, illetve megjeleníti egy adott parancshoz a súgót, valamint a rendelkezésre álló paramétereket.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?: Nem kötelező paraméterek

`command`– hol ``[command]`` található az előző lista egyik parancsa.

#### <a name="about"></a>névjegy

A telepített RSAT verziójának megjelenítése.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

Törli az adatokat a képernyőről.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>letöltés

A megadott teszteset mellékletének (Rögzítés, Végrehajtás és Paraméterfájlok) letöltése a Azure DevOps kimeneti könyvtárból. Ezzel a paranccsal ``list`` lehet az összes elérhető tesztesetet behozni, **és az első oszlop bármely értékét használni test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="download-optional-switches"></a>letöltés: választható kapcsolók

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a letöltési folyamat a megadott számú másodpercet várakozik, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.

##### <a name="download-required-parameters"></a>letöltés: szükséges paraméterek

+ `test_case_id`: A teszteset azonosítóját jeleníti meg.

##### <a name="download-optional-parameters"></a>letöltés: nem kötelező paraméterek

+ `output_dir`– a kimeneti munkakönyvtárat jelöli. A könyvtárnak léteznie kell. A beállítások munkakönyvtárát használja a rendszer, ha ez a paraméter nincs megadva.

##### <a name="download-examples"></a>letöltés: példák

`download 123 c:\temp\rsat`

`download /retry=240 765`

#### <a name="downloadsuite"></a>downloadsuite

A megadott tesztcsomagban található összes teszteset mellékletének (rögzítés, végrehajtás és paraméterfájlok) letöltése a Azure DevOps kimeneti könyvtárból. Ezzel a paranccsal ``listtestsuitenames`` lehet az összes elérhető tesztcsomagot behozni, és bármilyen értéket használni test_suite_name **paraméterként**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``downloadsuite``**``[/retry[=<seconds>]] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="downloadsuite-optional-switches"></a>downloadsuite: választható kapcsolók

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a letöltési folyamat a megadott számú másodpercet várakozik, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/byid`– ez a kapcsoló azt jelzi Azure DevOps, hogy a kívánt tesztcsomagot az azonosítója azonosítja a tesztcsomag neve helyett.

##### <a name="downloadsuite-required-parameters"></a>downloadsuite: szükséges paraméterek

+ `test_suite_name`: A tesztcsomag nevét jeleníti meg. Ha nincs megadva a /byid kapcsoló, kötelező megadni ezt a **paramétert**. Ez a név a tesztcsomag Azure DevOps neve.
+ `test_suite_id`: A tesztcsomag azonosítóját jeleníti meg. Ezt a paramétert kötelező megadni, ha meg van adva **a** /byid kapcsoló. Ez az azonosító tesztcsomag-azonosító Azure DevOps.

##### <a name="downloadsuite-optional-parameters"></a>downloadsuite: nem kötelező paraméterek

+ `output_dir`– a kimeneti munkakönyvtárat jelöli. A könyvtárnak léteznie kell. A beállítások munkakönyvtárát használja a rendszer, ha ez a paraméter nincs megadva.

##### <a name="downloadsuite-examples"></a>downloadsuite: példák

`downloadsuite NameOfTheSuite c:\temp\rsat`

`downloadsuite /byid 123 c:\temp\rsat`

`downloadsuite /retry=240 /byid 765`

`downloadsuite /retry=240 /byid 765 c:\temp\rsat`

#### <a name="edit"></a>szerkesztés

Lehetővé teszi a paraméterek fájl megnyitását Excel programban, és annak szerkesztését.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>szerkesztés: kötelező paraméterek

+ `excel_file`: Egy meglévő Excel-fájl teljes elérési útját kell tartalmaznia.

##### <a name="edit-examples"></a>szerkesztés: példák

`edit c:\RSAT\123\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>létrehozás

Létrehozza a tesztvégrehajtási és paraméterfájlokat a megadott tesztesethez a kimeneti könyvtárban. A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet. Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] [test_case_id] [output_dir]``

##### <a name="generate-optional-switches"></a>generálás: választható kapcsolók

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a generálási folyamat a megadott számú másodpercet várja, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/dllonly`: Csak a teszt-végrehajtási fájlok létrehozása. Ne újragenerálja az Excel paraméterfájlt.
+ `/keepcustomexcel`– a meglévő paraméterfájl frissítése. A végrehajtási fájlok újragenerálása.

##### <a name="generate-required-parameters"></a>generálás: szükséges paraméterek

+ `test_case_id`: A teszteset azonosítóját jeleníti meg.

##### <a name="generate-optional-parameters"></a>generálás: választható paraméterek

+ `output_dir`– a kimeneti munkakönyvtárat jelöli. A könyvtárnak léteznie kell. A beállítások munkakönyvtárát használja a rendszer, ha ez a paraméter nincs megadva.

##### <a name="generate-examples"></a>generálás: példák

`generate 123 c:\temp\rsat`

`generate /retry=240 765 c:\rsat\last`

`generate /retry=240 /dllonly 765`

`generate /retry=240 /keepcustomexcel 765`

#### <a name="generatederived"></a>generatederived

A megadott teszteset új származtatott tesztesetének (gyermek tesztesetnek) a létrehozása. Az új teszteset a megadott tesztcsomaghoz is hozzáadódik. Ezzel a paranccsal ``list`` lehet az összes elérhető tesztesetet behozni, **és az első oszlop bármely értékét használni test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[/retry[=<seconds>]] [parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-optional-switches"></a>generatederived: választható kapcsolók

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a generálási folyamat a megadott számú másodpercet várja, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.

##### <a name="generatederived-required-parameters"></a>generatederived: szükséges paraméterek

+ `parent_test_case_id`: A szülő teszteset azonosítóját jeleníti meg.
+ `test_plan_id`: A tesztkonstrukció azonosítóját jeleníti meg.
+ `test_suite_id`: A tesztcsomag azonosítóját jeleníti meg.

##### <a name="generatederived-examples"></a>generatederived: példák

`generatederived 123 8901 678`

`generatederived /retry 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

Csak a megadott tesztesethez szükséges Teszt-végrehajtási fájlokat generálja. Nem generálja az Excel paraméterfájlt. A fájlok a megadott kimeneti könyvtárban jönnek létre. Ezzel a paranccsal ``list`` lehet az összes elérhető tesztesetet behozni, **és az első oszlop bármely értékét használni test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="generatetestonly-optional-switches"></a>generatetestonly: választható kapcsolók

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a generálási folyamat a megadott számú másodpercet várja, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.

##### <a name="generatetestonly-required-parameters"></a>generatetestonly: szükséges paraméterek

+ `test_case_id`: A teszteset azonosítóját jeleníti meg.

##### <a name="generatetestonly-optional-parameters"></a>generatetestonly: választható paraméterek

+ `output_dir`– a kimeneti munkakönyvtárat jelöli. A könyvtárnak léteznie kell. A beállítások munkakönyvtárát használja a rendszer, ha ez a paraméter nincs megadva.

##### <a name="generatetestonly-examples"></a>generatetestonly: példák

`generatetestonly 123 c:\temp\rsat`

`generatetestonly /retry=240 765`

#### <a name="generatetestsuite"></a>generatetestsuite

Tesztautomatizálási fájlokat generál a megadott tesztcsomagban található összes tesztesethez. Ezzel a paranccsal ``listtestsuitenames`` lehet az összes elérhető tesztcsomagot behozni, és bármilyen értéket használni test_suite_name **paraméterként**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="generatetestsuite-optional-switches"></a>generatetestsuite: választható kapcsolók

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a generálási folyamat a megadott számú másodpercet várja, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/dllonly`: Csak a teszt-végrehajtási fájlok létrehozása. Ne újragenerálja az Excel paraméterfájlt.
+ `/keepcustomexcel`: Meglévő paraméterfájl frissítése. A végrehajtási fájlok újragenerálása.
+ `/byid`– ez a kapcsoló azt jelzi Azure DevOps, hogy a kívánt tesztcsomagot az azonosítója azonosítja a tesztcsomag neve helyett.

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite: szükséges paraméterek

+ `test_suite_name`: A tesztcsomag nevét jeleníti meg. Ha nincs megadva a /byid kapcsoló, kötelező megadni ezt a **paramétert**. Ez a név a tesztcsomag Azure DevOps neve.
+ `test_suite_id`: A tesztcsomag azonosítóját jeleníti meg. Ezt a paramétert kötelező megadni, ha meg van adva **a** /byid kapcsoló. Ez az azonosító tesztcsomag-azonosító Azure DevOps.

##### <a name="generatetestsuite-optional-parameters"></a>generatetestsuite: választható paraméterek

+ `output_dir`– a kimeneti munkakönyvtárat jelöli. A könyvtárnak léteznie kell. A beállítások munkakönyvtárát használja a rendszer, ha ez a paraméter nincs megadva.

##### <a name="generatetestsuite-examples"></a>generatetestsuite: példák

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite /retry Purchase c:\rsat\last`

`generatetestsuite /dllonly /byid 121`

`generatetestsuite /keepcustomexcel /byid 121`

#### <a name="help"></a>súgó

Azonos a következővel: [?](#section) parancs.

#### <a name="list"></a>lista

Felsorolja az aktuális teszttervben rendelkezésre álló teszteseteket.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

Felsorolja az összes elérhető tesztkonstrukciót.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

Felsorolja a megadott tesztcsomag teszteseteit. Ezzel a paranccsal ``listtestsuitenames`` lehet az összes elérhető tesztcsomagot behozni, és a **listából bármely értéket suite_name** használni.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[test_suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite: szükséges paraméterek

+ `test_suite_name`– a kívánt csomag neve.

##### <a name="listtestsuite-examples"></a>listtestsuite: példák

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitebyid"></a>listtestsuitebyid

Felsorolja a megadott tesztcsomag teszteseteit.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitebyid``**``[test_suite_id]``

##### <a name="listtestsuitebyid-required-parameters"></a>listtestsuitebyid: szükséges paraméterek

+ `test_suite_id`– a kívánt suite azonosítója.

##### <a name="listtestsuitebyid-examples"></a>listtestsuitebyid: példák

`listtestsuitebyid 12345`

#### <a name="listtestsuitenames"></a>listtestsuitenames

Felsorolja az aktuális teszttervben elérhető összes tesztcsomagot.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>visszajátszás

A megadott Excel-paraméterfájlhoz társított teszteset visszahozassza. Ez a parancs a meglévő helyi automatizálási fájlokat használja, és nem tölt le fájlokat innen Azure DevOps. Ez a parancs a POS kereskedelmi tesztesetek esetében nem támogatott.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file]``

##### <a name="playback-optional-switches"></a>playback: optional switches

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a folyamat a megadott számú másodpercet várakozik, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/comments[="comment"]`– adjon meg egy egyéni információs karakterláncot, **·** Azure DevOps amely szerepelni fog a teszteset-futtatásokat összefoglaló és teszteredményeket összefoglaló oldal Megjegyzés mezőjében.

##### <a name="playback-required-parameters"></a>lejátszás: szükséges paraméterek

+ `excel_parameter_file`– egy Excel-paraméterfájl teljes elérési útja. A fájlnak léteznie kell.

##### <a name="playback-examples"></a>lejátszás: példák

`playback c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playback /retry e:\temp\test.xlsx`

`playback /retry=300 e:\temp\test.xlsx`

`playback /comments="Payroll solution 10.0.0" e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

Több teszteset egyszerre lejátssza. A teszteseteket azonosítójuk azonosítja. Ez a parancs fájlokat fog le tölteni Azure DevOps innen. Ezzel a paranccsal ``list`` lehet az összes elérhető tesztesetet behozni, **és az első oszlop bármelyik értékét használni test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[/retry[=<seconds>]] [/comments[="comment"]] [test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-optional-switches"></a><a2/<a2/<a2/<a

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a folyamat a megadott számú másodpercet várakozik, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/comments[="comment"]`– adjon meg egy egyéni információs karakterláncot, **·** Azure DevOps amely szerepelni fog a teszteset-futtatásokat összefoglaló és teszteredményeket összefoglaló oldal Megjegyzés mezőjében.

##### <a name="playbackbyid-required-parameters"></a>playbackbyid: szükséges paraméterek

+ `test_case_id1`– egy meglévő teszteset azonosítója.
+ `test_case_id2`– egy meglévő teszteset azonosítója.
+ `test_case_idN`– egy meglévő teszteset azonosítója.

##### <a name="playbackbyid-examples"></a>playbackbyid: példák

`playbackbyid 878`

`playbackbyid 2345 667 135`

`playbackbyid /comments="Payroll solution 10.0.0" 2345 667 135`

`playbackbyid /retry /comments="Payroll solution 10.0.0" 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Sok tesztesetet egyszerre tesztel. A teszteseteket Excel-paraméterfájlok azonosítják. Ez a parancs a meglévő helyi automatizálási fájlokat használja, és nem tölt le fájlokat innen Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file1] [excel_parameter_file2] ... [excel_parameter_fileN]``

##### <a name="playbackmany-optional-switches"></a><a1/<a1/<a2/<a2

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a folyamat a megadott számú másodpercet várakozik, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/comments[="comment"]`– adjon meg egy egyéni információs karakterláncot, **·** Azure DevOps amely szerepelni fog a teszteset-futtatásokat összefoglaló és teszteredményeket összefoglaló oldal Megjegyzés mezőjében.

##### <a name="playbackmany-required-parameters"></a>playbackmany: szükséges paraméterek

+ `excel_parameter_file1`– az Excel paraméterfájl teljes elérési útja. A fájlnak léteznie kell.
+ `excel_parameter_file2`– az Excel paraméterfájl teljes elérési útja. A fájlnak léteznie kell.
+ `excel_parameter_fileN`– az Excel paraméterfájl teljes elérési útja. A fájlnak léteznie kell.

##### <a name="playbackmany-examples"></a>playbackmany: példák

`playbackmany c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playbackmany e:\temp\test.xlsx f:\RSAT\sample1.xlsx c:\RSAT\sample2.xlsx`

`playbackmany /retry=180 /comments="Payroll solution 10.0.0" e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

Az összes teszteset visszahozassza egy vagy több meghatározott tesztcsomagból. Ha a /local kapcsoló meg van adva, akkor a helyi mellékleteket használja a program a csatolások cseréihez. Ellenkező esetben a mellékletek innen lesznek letöltve Azure DevOps. Ezzel a paranccsal ``listtestsuitenames`` lehet az összes elérhető tesztcsomagot behozni, **és az első oszlop bármely értékét használni suite_name** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] ([test_suite_name1] .. [test_suite_nameN] | [/byid] [test_suite_id1] .. [test_suite_idN])``

##### <a name="playbacksuite-optional-switches"></a>playbacksuite: optional switches

+ `/updatedriver`– ha ez a kapcsoló meg van adva, akkor a folyamat futtatása előtt a program szükség szerint frissíti az internet-böngésző webkiszolgálóját.
+ `/local`: Ez a kapcsoló azt jelzi, hogy helyi mellékleteket kell használni az adatokat a innen való fájlletöltés helyett Azure DevOps.
+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a folyamat a megadott számú másodpercet várakozik, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/comments[="comment"]`– adjon meg egy egyéni információs karakterláncot, **·** Azure DevOps amely szerepelni fog a teszteset-futtatásokat összefoglaló és teszteredményeket összefoglaló oldal Megjegyzés mezőjében.
+ `/byid`– ez a kapcsoló azt jelzi Azure DevOps, hogy a kívánt tesztcsomagot az azonosítója azonosítja a tesztcsomag neve helyett.

##### <a name="playbacksuite-required-parameters"></a>playbacksuite: szükséges paraméterek

+ `test_suite_name1`: A tesztcsomag nevét jeleníti meg. Ha nincs megadva a /byid kapcsoló, kötelező megadni ezt a **paramétert**. Ez a név a tesztcsomag Azure DevOps neve.
+ `test_suite_nameN`: A tesztcsomag nevét jeleníti meg. Ha nincs megadva a /byid kapcsoló, kötelező megadni ezt a **paramétert**. Ez a név a tesztcsomag Azure DevOps neve.
+ `test_suite_id1`: A tesztcsomag azonosítóját jeleníti meg. Ezt a paramétert kötelező megadni, ha meg van adva **a** /byid kapcsoló. Ez az azonosító a tesztcsomag Azure DevOps azonosítója.
+ `test_suite_idN`: A tesztcsomag azonosítóját jeleníti meg. Ezt a paramétert kötelező megadni, ha meg van adva **a** /byid kapcsoló. Ez az azonosító a tesztcsomag Azure DevOps azonosítója.

##### <a name="playbacksuite-examples"></a>playbacksuite: példák

`playbacksuite suiteName`

`playbacksuite suiteName suiteNameToo`

`playbacksuite /updatedriver /local /retry=180 /byid 151 156`

`playbacksuite /updatedriver /local /comments="Payroll solution 10.0.0" /byid 150`

#### <a name="playbacksuitebyid"></a>playbacksuitebyid

A megadott tesztcsomagban található összes teszteset Azure DevOps futtatása.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuitebyid``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] [test_suite_id]``

##### <a name="playbacksuitebyid-optional-switches"></a>a<a2/<a2/<a2/<a2/<a3

+ `/retry[=seconds]`– ha ez a kapcsoló meg van adva, és az esetteszt eseteket más RSAT-példányok zárolják, akkor a folyamat a megadott számú másodpercet várakozik, majd újra próbálkozik. A másodperc alapértelmezett \[értéke\] 120 másodperc. E kapcsoló nélkül a folyamat azonnal megszakad, ha a tesztesetek blokkolva vannak.
+ `/comments[="comment"]`– adjon meg egy egyéni információs karakterláncot, **·** Azure DevOps amely szerepelni fog a teszteset-futtatásokat összefoglaló és teszteredményeket összefoglaló oldal Megjegyzés mezőjében.
+ `/byid`– ez a kapcsoló azt jelzi Azure DevOps, hogy a kívánt tesztcsomagot az azonosítója azonosítja a tesztcsomag neve helyett.

##### <a name="playbacksuitebyid-required-parameters"></a>binebyid: szükséges paraméterek

+ `test_suite_id`: A tesztcsomag-azonosítónak megfelelő azonosító a létezik a következőben Azure DevOps:

##### <a name="playbacksuitebyid-examples"></a>a<a2/<a2/<a2/<

`playbacksuitebyid 2900`

`playbacksuitebyid /retry 2099`

`playbacksuitebyid /retry=200 2099`

`playbacksuitebyid /retry=200 /comments="some comment" 2099`

#### <a name="quit"></a>kilépés

Bezárja a pályázatot. Ez a parancs csak akkor hasznos, ha az alkalmazások interaktív módban futnak.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

##### <a name="quit-examples"></a>kilépés: példák

`quit`

#### <a name="upload"></a>feltöltés

Feltölti a megadott tesztcsomaghoz vagy tesztesethez tartozó mellékletfájlokat (rögzítés, végrehajtás és paraméterfájlok Azure DevOps).

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``([test_suite_name] | [test_case_id1] .. [test_case_idN])``

##### <a name="upload-required-parameters"></a>feltöltés: szükséges paraméterek

+ `test_suite_name`– a rendszer a megadott tesztcsomaghoz tartozó összes fájlt feltölti.
+ `test_case_id1`– az első feltöltendő teszteset-azonosítót jelöli. Ezt a paramétert csak akkor használja, ha nincs megadva tesztcsomag-név.
+ `test_case_idN`– az utolsó teszteset-azonosítót jelöli, amely feltöltődik. Ezt a paramétert csak akkor használja, ha nincs megadva tesztcsomag-név.

##### <a name="upload-examples"></a>feltöltés: példák

`upload sample_suite`

`upload 2900`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

Csak annak a rögzítési fájlnak a feltöltése, amelybe egy vagy több megadott teszteset tartozik Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[test_case_id1] .. [test_case_idN]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording: szükséges paraméterek

+ `test_case_id1`– annak a rögzítésnek az első teszteset-azonosítóját jelöli, amelybe feltölthetők Azure DevOps.
+ `test_case_idN`– annak a rögzítésnek az utolsó teszteset-azonosítóját jelöli, amelybe fel kell tölteni Azure DevOps.

##### <a name="uploadrecording-examples"></a>uploadrecording: példák

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>használat

Az alkalmazás három használati módja.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

Az alkalmazás interaktív futtatása:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``

Az alkalmazás futtatása parancs megadásával:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp ``**``[command]``**

Az alkalmazás futtatása a következő beállítási fájllal:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``/settings [drive:\Path to\file.settings] [command]``**

### <a name="windows-powershell-examples"></a>Windows PowerShell-példák

#### <a name="run-a-test-case-in-a-loop"></a>Teszteset futtatása egy hurokban

Van egy tesztparancsfájl, amely új vevőt hoz létre. A parancsfájlkezeléssel ezt a tesztesetet egy hurokban futtathatja, ha minden egyes iteráció futtatása előtt a következő adatokat véletlenszerűvé teszi:

- Vevő azonosítója
- Vevő neve
- Vevő címe

Az ügyfélazonosító formátuma a következő lesz: *ATCUS\<number\>*, ahol a \<number\> egy érték **000000001** és **999999999** között.

A következő példában a program egy paramétert, az **indítás** paramétert használja az először használt szám meghatározásához. Egy második paramétert (**nr**) a létrehozni kívánt ügyfelek számának meghatározására használ. Minden iteráció esetében az Excel-paraméterfájl paraméterei egy UpdateCustomer-funkcióval változtathatók. Ezt követően a RSAT parancssor lehívása RunTestCase-funkcióban történik.

Nyissa meg a Microsoft Windows PowerShell integrált parancsfájl-kezelési környezetet (ISE) rendszergazdai módban, majd illessze be az alábbi kódot az **Untitled1.ps1** elnevezésű ablakba.

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Parancsfájl futtatása, amely a Microsoft Dynamics 365 adataitól függ

A következő példa egy Open Data protokoll (OData) hívással keresi meg a beszerzési rendelések rendelési állapotát. Ha az állapot nem **számlázott**, akkor például lehívhat egy RSAT-tesztet, amely feladja a számlát.

```powershell
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
