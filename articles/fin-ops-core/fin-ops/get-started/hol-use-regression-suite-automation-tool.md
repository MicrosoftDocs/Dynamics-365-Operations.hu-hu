---
title: Regression Suite Automation Tool-oktatóanyag használata
description: Ez a témakör bemutatja, hogy hogyan használható a Regression Suite Automation Tool (RSAT). Leírja a különböző funkciókat, és speciális parancsfájlkezelést használó példákat tartalmaz.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: cf3ca501efb4e540994b01e651eee5b8aab4ddbc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191086"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>A Regression Suite Automation Tool-oktatóanyag használata

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Az internetböngésző eszközeivel letöltheti és mentheti ezt a lapot PDF-formátumban. 

Ez az oktatóanyag végigvezet a Regression Suite Automation Tool (RSAT) néhány speciális funkcióján, tartalmaz bemutatófeladatot, és leírja a stratégiát és a fontos tanulási pontokat is.

## <a name="features-of-rsattask-recorder"></a>Az RSAT/Feladatrögzítő funkciói

### <a name="validate-a-field-value"></a>Egy mezőérték ellenőrzése

Ha további információra van szüksége a funkcióról, itt találhat: [Ellenőrzés funkciót tartalmazó új feladatrögzítés létrehozása](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).

### <a name="saved-variable"></a>Mentett változó

Ha további információra van szüksége a funkcióról, itt találhat: [Meglévő feladatrögzítés módosítása mentett változó létrehozásához](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).

### <a name="derived-test-case"></a>Származtatott teszteset

1. Nyissa meg a Regression Suite Automation Tool (RSAT) eszközt, és válassza ki a [A Regression Suite Automation Tool beállítása és telepítése](./hol-set-up-regression-suite-automation-tool.md) szakaszban létrehozott mindkét tesztesetet.
2. Válassza az **Új \> Származtatott teszteset létrehozása** elemet.

    ![Származtatott teszteset létrehozása parancs az Új menüben](./media/use_rsa_tool_01.png)

3. Egy üzenet jelenik meg, amely jelzi, hogy az aktuális tesztcsomag mindegyik kiválasztott tesztesetéhez származtatott tesztesetet hoz létre, és minden egyes származtatott tesztesetnek saját másolata lesz az Excel-paraméterfájlból. Válassza ki az **OK** lehetőséget.

    > [!NOTE]
    > Származtatott teszteset futtatásakor a program a fölérendelt feladatrögzítést, valamint az Excel-paraméterfájlból származó saját másolatát használja. Ily módon ugyanazon tesztet különböző paraméterekkel futtathatja, anélkül, hogy egynél több feladatrögzítést kellene karbantartania. Egy származtatott tesztesetnek nem kell ugyanahhoz a tesztcsomaghoz tartoznia, mint a fölérendelt tesztesetnek.

    ![Üzenetpanel](./media/use_rsa_tool_02.png)

    Két további származtatott teszteset jön létre, és a **Származtatott?** jelölőnégyzet be van jelölve.

    ![Származtatott tesztesetek létrehozva](./media/use_rsa_tool_03.png)

    A származtatott teszteset automatikusan létrejön az Azure DevOps rendszerben. Ez az **Új termék létrehozása** teszteset alárendelt eleme, és speciális kulcsszóval van felcímkézve: **RSAT:DerivedTestSteps**. Ezeket a teszteseteket a program automatikusan hozzáadja az Azure DevOps tesztelési tervbe.

    ![RSAT:DerivedTestSteps kulcsszó](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > Ha valamilyen oknál fogva a létrejövő származtatott tesztesetek nem megfelelő sorrendben vannak, akkor lépjen az Azure DevOps felületére, és rendezze át a teszteseteket a tesztcsomagban, hogy az RSAT megfelelő sorrendben futtassa őket.

4. Válassza ki csak a származtatott teszteseteket, majd a **Szerkesztés** parancsot a kapcsolódó Excel-paraméterfájlok megnyitásához.
5. Szerkessze ezeket az Excel-paraméterfájlokat ugyanúgy, mint a fölérendelt fájlokat. Más szóval győződjön meg arról, hogy a termékazonosító be van állítva úgy, hogy automatikusan létrejön. Győződjön meg arról is, hogy a mentett változót a megfelelő mezőkbe másolja át a program.
6. Az Excel-paraméterfájlok **Általános** lapján frissítse a **Vállalat** mező értékét az **USSI** értékre, hogy a származtatott teszteseteket egy másik jogi személyre futtassa, mint a fölérendelt tesztesetet. Ha a teszteseteket egy megadott felhasználóra (vagy egy megadott felhasználóhoz társított szerepkörre) futtatja, akkor frissítheti a **Tesztfelhasználó** mező értékét.
7. Válassza a **Futtatás** parancsot, és ellenőrizze, hogy a termék a USMF jogi személyben és a USSI jogi személyben egyaránt létrejött-e.

### <a name="validate-notifications"></a>Értesítések ellenőrzése

Ez a funkció annak ellenőrzésére használható, hogy történt-e művelet. Például egy termelési rendelés létrehozása, becslése, majd elindítása történt, megjelenik a „Termelés – Indítás” üzenetet, amellyel értesíti, hogy a termelési rendelés elindult.

![Termelés – Indítás értesítés](./media/use_rsa_tool_05.png)

Ezt az üzenetet a RSAT programon keresztül ellenőrizni lehet, ha megadja az üzenet szövegét a megfelelő rögzítéshez tartozó Excel paraméterfájl **MessageValidation** lapján.

![Üzenet ellenőrzése lap](./media/use_rsa_tool_06.png)

Miután lefutott a teszteset, az Excel-paraméterfájlban szereplő üzenetet a program összehasonlítja az üzenettel. Ha az üzenetek nem egyeznek, a teszteset nem fog sikerülni.

> [!NOTE]
> Az Excel-paraméterfájl **MessageValidation** lapján egynél több üzenetet is megadhat. Az üzenetek a tájékoztató üzenetek helyett hiba- vagy figyelmeztető üzenetek is lehetnek.

### <a name="validate-values-by-using-operators"></a>Értékek ellenőrzése operátorok segítségével

Az RSAT korábbi verzióiban csak akkor lehet ellenőrizni az értékeket, ha egy ellenőrzési érték egy várt értékkel egyenlő volt. Az új funkció segítségével ellenőrizhető, hogy egy változó nem egyenlő, kisebb, vagy nagyobb mint a megadott érték.

- A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elemet **hamis** értékről **igaz** értékre.

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    Az Excel-paraméterfájlban megjelenik egy új **Operátor** mező.

    > [!NOTE]
    > Ha egy korábbi RSAT-verziót használt, új Excel-paraméterfájlokat kell létrehoznia.

    ![Operátor mező](./media/use_rsa_tool_07.png)

A következő példa bemutatja, hogyan használható ez a funkció annak ellenőrzésére, hogy az aktuális készlet nagyobb mint 0 (nulla).

1. Hozzon létre egy olyan feladatrögzítést a **USMF** vállalat bemutató adatai között, amelynek a következő lépései vannak:

    1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
    2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön az **1000** értékre a **Cikkszám** mezőben.
    3. Válassza az **Aktuális készlet** elemet.
    4. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön az **1** értékre a **Telephely** mezőben.
    5. A listában jelölje meg a kiválasztott sort.
    6. Ellenőrizze, hogy az **Összes rendelkezésre álló** mező értéke **411,0000000000000000**.

2. Mentse a feladatrögzítést az LCS-ben a BPM-tárba, majd szinkronizálja az Azure DevOps rendszerbe.
3. Adja hozzá a tesztesetet a tesztelési tervhez, és töltse be a tesztesetet a RSAT-be.
4. Nyissa meg az Excel-paraméterfájlt. Az **InventOnhandItem** lapon látható az **InventOnhandItem ellenőrzése** szakasz, amelyben szerepel egy **Operátor** mező.

    ![Operátor mező](./media/use_rsa_tool_08.png)

5. Ha ellenőrizni szeretné, hogy az aktuális készlet mindig nagyobb, mint 0, akkor módosítsa az **Érték** mező értékét **411**-ről **0** értékre, és az **Operátor** mező értékét egyenlőségjelről (**=**) a nagyobb mint jelre (**\>**).

    ![Az Érték és az Operátor mező értéke megváltozott](./media/use_rsa_tool_09.png)

6. Mentse és zárja be az Excel-paraméterfájlt.
7. A **Feltöltés** gombra kattintva mentheti a módosításokat az Azure DevOps rendszerbe, amelyeket az Excel-paraméterfájlban tett.

Ha most a megadott cikk **Összes rendelkezésre álló** mezője értéke meghaladja a 0 (nulla) értéket, akkor a tesztek sikeresek lesznek, függetlenül a tényleges aktuális készlet értékétől.

### <a name="generator-logs"></a>Generátornaplók

Ez a funkció létrehoz egy mappát, amely a futtatott tesztesetek naplóit tartalmazza.

- A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elemet **hamis** értékről **igaz** értékre.

    ```
    <add key="LogGeneration" value="false" />
    ```

A tesztek futtatása után a fájlok a **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs** helyen találhatók.

![GeneratorLogs mappa](./media/use_rsa_tool_10.png)

> [!NOTE]
> Ha már léteznek tesztesetek, mielőtt a .config fájlban megváltoztatta a értéket, akkor a naplók nem jönnek létre azokhoz a tesztesetekhez addig, amíg nem hoz létre új teszt-végrehajtási fájlokat.
> 
> ![Csak tesztvégrehajtási fájlok létrehozása parancs az Új menüben](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a>Pillanatkép

Ez a funkció képernyőképeket készít a feladatrögzítés során végrehajtott lépésekről.

- A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elem értékét **hamis** értékről **igaz** értékre.

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

A **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback** helyen a program külön mappát hoz létre mindegyik futó tesztesethez.

![Pillanatkép mappa a tesztesethez](./media/use_rsa_tool_12.png)

Ezekben a mappákban megtalálhatja azokat a lépések pillanatképeit, amelyeket a tesztesetek futtatásakor végrehajtott.

![Pillanatfelvétel-fájlok](./media/use_rsa_tool_13.png)

## <a name="assignment"></a>Hozzárendelés

### <a name="scenario"></a>Eset

1. A termék tervezője létrehoz egy új kiadott terméket.
2. A termelési vezető kezdeményez egy termelési rendelést, hogy a készlet szintje két darabra növekedjen.
3. A gyártás elindítja és befejezi a termelési rendelést, és ellenőrzi, hogy a készleten lévő mennyiség két darab.
4. Az értékesítési csoport rendelést kap négy darabra az új termékből. Ezért az értékesítési csoport frissíti a nettó szükségletet a dinamikus terven keresztül. Mivel nem áll rendelkezésre további kapacitás, az alapértelmezett rendelési irányelv beállítása „vásárlás gyártás helyett”. Így létrejön egy tervezett beszerzési rendelés.
5. A vevő hozzáadja a szállítót, megerősíti a tervezett beszerzési rendelést, majd megerősíti a beszerzési rendelést.
6. Amikor a megvásárolt áruk megérkeznek az üzletbe, az üzlet operátora megkeresi a kapcsolódó beszerzési rendelést, és bevételezi az árukat. Mivel a rendelést már befejeződött, az árukat az értékesítési rendeléshez lehet kitárolni és csomagolni.
7. A pénzügy felad egy beszerzési számlát és egy értékesítési számlát.

A következő ábra bemutatja az adott eset folyamatát.

![A bemutató eset folyamata](./media/use_rsa_tool_14.png)

A következő ábra bemutatja az adott eset üzleti folyamatait RSAT-ban.

![A bemutató eset üzleti folyamatai](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Stratégia – Kulcsfontosságú tanulási pontok

### <a name="data"></a>Adat

- Győződjön meg róla, hogy rendelkezik reprezentatív adatmennyiséggel (termelési/arany konfigurációs adatok másolata és áttelepített adatok).
- Amikor a feladatrögzítőn keresztül új adatokat hoz létre, olyan tesztneveket hozzon létre, amelyek nem ütköznek a meglévő nevekkel (például használjon **RSATxxx** előtagot).
- Az Azure Időponthoz kötött visszaállítás használatával futtassa újra a teszteket a nem 1. szintű környezetekben.
- Annak ellenére, hogy a **RANDOM** és **NOW** Excel-funkciók segítségével egyedi kombinációt generálhat, az erőfeszítés jelentősen magas. Íme, egy példa.

    ```
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

### <a name="command-line"></a>Parancssor

Az RSAT-ot a **Parancssor** ablakból is be lehet hívni.

> [!NOTE]
> Győződjön meg róla, hogy a **TestRoot** környezeti változó az RSAT telepítési útvonalára van állítva. (Microsoft Windows rendszerben nyissa meg a **Vezérlőpult** elemet, válassza a **Rendszer és biztonság \> Rendszer \> Speciális rendszerbeállítások** menüpontot, majd válassza a **Környezet változók** lehetőséget.)

1. Nyissa meg a **Parancssor** ablakot rendszergazdaként.
2. Futtassa az eszközt a telepítési könyvtárból.

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Listázza az összes parancsot.

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a>Windows PowerShell-példák

#### <a name="run-a-test-case-in-a-loop"></a>Teszteset futtatása egy hurokban

Van egy tesztparancsfájl, amely új vevőt hoz létre. A parancsfájlkezeléssel ezt a tesztesetet egy hurokban futtathatja, ha minden egyes iteráció futtatása előtt a következő adatokat véletlenszerűvé teszi:

- Vevő azonosítója
- Vevő neve
- Vevő címe

Az ügyfélazonosító formátuma a következő lesz: *ATCUS\<number\>*, ahol \<number\> egy érték **000000001** és **999999999** között.

A következő példában a program egy paramétert, az **indítás** paramétert használja az először használt szám meghatározásához. Egy második paramétert (**nr**) a létrehozni kívánt ügyfelek számának meghatározására használ. Minden iteráció esetében az Excel-paraméterfájl paraméterei egy UpdateCustomer-funkcióval változtathatók. Ezt követően a RSAT parancssor lehívása RunTestCase-funkcióban történik.

Nyissa meg a Microsoft Windows PowerShell integrált parancsfájl-kezelési környezetet (ISE) rendszergazdai módban, majd illessze be az alábbi kódot az **Untitled1.ps1** elnevezésű ablakba.

```
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
$excelFilename = "full path to excel file parameter file"
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

```
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
