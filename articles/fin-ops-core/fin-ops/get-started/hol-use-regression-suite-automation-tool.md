---
title: A Regression Suite Automation Tool-oktatóanyag használata
description: Ez a témakör bemutatja, hogy hogyan használható a Regression Suite Automation Tool (RSAT). Leírja a különböző funkciókat, és speciális parancsfájlkezelést használó példákat tartalmaz.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 2d3dde69b102ce161e5c1f1dd393ffceca608bcb
ms.sourcegitcommit: 4fdee254649a751d46632fb4d0d48698e112fa72
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248736"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>A Regression Suite Automation Tool-oktatóanyag használata

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Az internetböngésző eszközeivel letöltheti és mentheti ezt a lapot PDF-formátumban. 

Ez az oktatóanyag végigvezet a Regression Suite Automation Tool (RSAT) néhány speciális funkcióján, tartalmaz bemutatófeladatot, és leírja a stratégiát és a fontos tanulási pontokat is. 

## <a name="notable-features-of-rsat-and-task-recorder"></a>A RSAT és a Feladatrögzítő fontos jellemzői

### <a name="validate-a-field-value"></a>Egy mezőérték ellenőrzése

A RSAT ellenőrzési lépéseket tesz lehetővé a tesztesetéhez a várt értékek érvényesítéséhez. Ha további tájékoztatást szeretne erről a funkcióról, olvassa el a [Várható értékek érvényesítése](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md) című cikket.

A következő példa bemutatja, hogyan használható ez a funkció annak ellenőrzésére, hogy az aktuális készlet nagyobb mint 0 (nulla).

1. Hozzon létre egy olyan feladatrögzítést a **USMF** vállalat bemutató adatai között, amelynek a következő lépései vannak:

    1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
    2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön az **1000** értékre a **Cikkszám** mezőben.
    3. Válassza az **Aktuális készlet** elemet.
    4. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön az **1** értékre a **Telephely** mezőben.
    5. A listában jelölje meg a kiválasztott sort.
    6. Ellenőrizze, hogy az **Összes rendelkezésre álló** mező értéke **411,0000000000000000**.

2. Mentse a feladatrögzítést, és csatolja a tesztesetéhez az Azure Devops-ban.
3. Adja hozzá a tesztesetet a tesztelési tervhez, és töltse be a tesztesetet a RSAT-be.
4. Nyissa meg az Excel-paraméterfájlt. Az **InventOnhandItem** lapon látható az **InventOnhandItem ellenőrzése** szakasz, amelyben szerepel egy **Operátor** mező.

    ![Operátor mező](./media/use_rsa_tool_08.png)

5. Ha ellenőrizni szeretné, hogy az aktuális készlet mindig nagyobb, mint 0, akkor módosítsa az **Érték** mező értékét **411**-ről **0** értékre, és az **Operátor** mező értékét egyenlőségjelről (**=**) a nagyobb mint jelre (**\>**).

    ![Az Érték és az Operátor mező értéke megváltozott](./media/use_rsa_tool_09.png)

6. Mentse és zárja be az Excel-paraméterfájlt.
7. A **Feltöltés** gombra kattintva mentheti a módosításokat az Azure DevOps rendszerbe, amelyeket az Excel-paraméterfájlban tett.

Ha most a megadott cikk **Összes rendelkezésre álló** mezője értéke meghaladja a 0 (nulla) értéket, akkor a tesztek sikeresek lesznek, függetlenül a tényleges aktuális készlet értékétől.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Mentett változók és a tesztesetek láncolása

A RSAT egyik alapvető funkciója a tesztesetek láncolása, tehát az a képesség, amellyel egy teszt változókat adhat át más teszteknek. A további tudnivalókat lásd a [Változók másolása tesztesetekre](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md) című cikkben.

### <a name="derived-test-case"></a>Származtatott teszteset

A RSAT használatával több feladatrögzítést is felhasználhat több tesztesettel így a feladatok különböző adatkonfigurációkkal futtathatók. További tájékoztatás a [Származtatott tesztesetek](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) cikkben található.

### <a name="validate-notifications-and-messages"></a>Értesítések és üzenetek érvényesítése

Ez a funkció annak ellenőrzésére használható, hogy történt-e művelet. Például egy termelési rendelés létrehozása, becslése, majd elindítása történt, megjelenik a „Termelés – Indítás” üzenetet, amellyel értesíti, hogy a termelési rendelés elindult.

![Termelés – Indítás értesítés](./media/use_rsa_tool_05.png)

Ezt az üzenetet a RSAT programon keresztül ellenőrizni lehet, ha megadja az üzenet szövegét a megfelelő rögzítéshez tartozó Excel paraméterfájl **MessageValidation** lapján.

![Üzenet ellenőrzése lap](./media/use_rsa_tool_06.png)

Miután lefutott a teszteset, az Excel-paraméterfájlban szereplő üzenetet a program összehasonlítja az üzenettel. Ha az üzenetek nem egyeznek, a teszteset nem fog sikerülni.

> [!NOTE]
> Az Excel-paraméterfájl **MessageValidation** lapján egynél több üzenetet is megadhat. Az üzenetek a tájékoztató üzenetek helyett hiba- vagy figyelmeztető üzenetek is lehetnek.

### <a name="snapshot"></a>Pillanatkép

Ez a funkció képernyőképeket készít a feladatrögzítés során végrehajtott lépésekről. Ez a ellenőrzés vagy hibakeresés céljából hasznos.

- A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elem értékét **hamis** értékről **igaz** értékre.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Amikor futtatja a tesztesetet, az RSAT pillanatképeket (képeket) fog generálni a lépésekről a visszajátszási mappában munkakönyvtárban. Ha egy korábbi RSAT-verziót használ a képek a **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a mappába lesznek mentve, és minden futtatott tesztesethez egy külön mappa jön létre.

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

![A bemutató eset folyamata](./media/use_rsa_tool_14.png)

A következő ábra bemutatja az üzleti folyamatok hierarchiáját ehhez a forgatókönyvhöz az LCS Üzletifolyamat-modellező moduljában.

![A bemutató eset üzleti folyamatai](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Stratégia – Kulcsfontosságú tanulási pontok

### <a name="data"></a>Adat

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
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>? 
A rendelkezésre álló parancsokkal és a paraméterekkel kapcsolatos súgó megjelenítése.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a>Nem kötelező paraméterek

**``command``**


A ``[command]`` az alább megadott parancsok egyike.


#### <a name="about"></a>névjegy
Az aktuális verziót jeleníti meg.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls
Törli az adatokat a képernyőről.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a>letöltés
Letölti a megadott tesztesethez tartozott mellékleteket a kimeneti környvtárba. A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet. Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``test_case_id``** A teszteset azonosítóját jeleníti meg.  
**``output_dir``** A kimeneti könyvtárat jelöli. A könyvtárnak léteznie kell.

##### <a name="examples"></a>Példák

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a>szerkesztés
Lehetővé teszi a paraméterek fájl megnyitását Excel programban, és annak szerkesztését.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``excel_file``** Egy meglévő Excel-fájl teljes elérési útját kell tartalmaznia.

##### <a name="examples"></a>Példák
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a>létrehozás
Létrehozza a tesztvégrehajtási és paraméterfájlokat a megadott tesztesethez a kimeneti könyvtárban.
A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet. Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``test_case_id``** A teszteset azonosítóját jeleníti meg.  
**``output_dir``** A kimeneti könyvtárat jelöli. A könyvtárnak léteznie kell.

##### <a name="examples"></a>Példák
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a>generatederived
Új tesztesetet hoz létre, amely a megadott tesztesetből származik. A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet. Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``parent_test_case_id``** A fölérendelt teszteset azonosítóját jeleníti meg.  
**``test_plan_id``** A tesztkonstrukció azonosítóját jeleníti meg.  
**``test_suite_id``** A tesztcsomag azonosítóját jeleníti meg.

##### <a name="examples"></a>Példák
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a>generatetestonly
Csak a tesztvégrehajtási fájlt hozza létre a megadott tesztesethez a kimeneti könyvtárban. A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet. Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``test_case_id``** A teszteset azonosítóját jeleníti meg.  
**``output_dir``** A kimeneti könyvtárat jelöli. A könyvtárnak léteznie kell.

##### <a name="examples"></a>Példák
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a>generatetestsuite
Létrehozza az összes tesztesetet a megadott csomaghoz a kimeneti könyvtárban.
A ``listtestsuitenames`` paranccsal lekérheti az összes rendelkezésre álló tesztcsomagot. Az oszlopból bármelyik értéket használhatja **test_suite_name** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``test_suite_name``** A tesztcsomag nevét jeleníti meg.  
**``output_dir``** A kimeneti könyvtárat jelöli. A könyvtárnak léteznie kell.

##### <a name="examples"></a>Példák
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a>súgó
Azonos a következővel: [?](#section) parancs


#### <a name="list"></a>listában
Felsorolja az összes elérhető teszt esetet.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a>listtestplans
Felsorolja az összes elérhető tesztkonstrukciót.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a>listtestsuite
Felsorolja a megadott tesztcsomag teszteseteit. A ``listtestsuitenames`` paranccsal lekérheti az összes rendelkezésre álló tesztcsomagot. Az első oszlopból bármelyik értéket használhatja **suite_name** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``suite_name``** A kívánt csomag neve.

##### <a name="examples"></a>Példák
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a>listtestsuitenames
Felsorolja az összes elérhető tesztcsomagot.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a>visszajátszás
Visszajátszik egy tesztesetet Excel-fájl segítségével.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``excel_file``** Az Excel-fájl teljes elérési útja. A fájlnak léteznie kell. 

##### <a name="examples"></a>Példák
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a>playbackbyid
Egyszerre több tesztesetet játszik le.
A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet. Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``test_case_id1``** A meglévő teszteset azonosítója.  
**``test_case_id2``** A meglévő teszteset azonosítója.  
**``test_case_idN``** A meglévő teszteset azonosítója.  

##### <a name="examples"></a>Példák
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a>playbackmany
Több tesztesetet játszik le egyszerre, Excel-fájlok használatával.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``excel_file1``** Az Excel-fájl teljes elérési útja. A fájlnak léteznie kell.  
**``excel_file2``** Az Excel-fájl teljes elérési útja. A fájlnak léteznie kell.  
**``excel_fileN``** Az Excel-fájl teljes elérési útja. A fájlnak léteznie kell.  

##### <a name="examples"></a>Példák
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a>playbacksuite
A megadott tesztcsomagból minden tesztesetet lejátszik. A ``listtestsuitenames`` paranccsal lekérheti az összes rendelkezésre álló tesztcsomagot. Az első oszlopból bármelyik értéket használhatja **suite_name** paraméterként.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``suite_name``** A kívánt csomag neve.

##### <a name="examples"></a>Példák
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a>kilépés
Bezárja az alkalmazást.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a>feltöltés
A megadott tesztcsomaghoz vagy tesztesetekhez tartozó összes fájlt feltölti.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a>Kötelező paraméterek
**``suite_name``** A megadott tesztcsomaghoz tartozó összes fájlt feltölti.
**``testcase_id``** A megadott teszteset(ek)hez tartozó összes fájlt feltölti.

##### <a name="examples"></a>Példák
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a>uploadrecording
Csak a megadott tesztesetekhez tartozó rögzítési fájlt tölti fel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a>Kötelező paraméterek
**``testcase_id``** Csak a megadott tesztesetekhez tartozó rögzítési fájlt tölti fel.

##### <a name="examples"></a>Példák
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a>használat
Kétféle módszert mutat be az alkalmazás meghívására: az egyik alapértelmezett beállítási fájlt használ, a másik egy beállítási fájlt ad meg.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a>Windows PowerShell-példák

[!IMPORTANT] A lenti forgatókönyvek a következők JELEN ÁLLAPOTUKBAN érhetők el, és a Microsoft nem támogatja ezeket.

#### <a name="run-a-test-case-in-a-loop"></a>Teszteset futtatása egy hurokban

Van egy tesztparancsfájl, amely új vevőt hoz létre. A parancsfájlkezeléssel ezt a tesztesetet egy hurokban futtathatja, ha minden egyes iteráció futtatása előtt a következő adatokat véletlenszerűvé teszi:

- Vevő azonosítója
- Vevő neve
- Vevő címe

Az ügyfélazonosító formátuma a következő lesz: *ATCUS\<number\>*, ahol \<number\> egy érték **000000001** és **999999999** között.

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

```xpp
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
