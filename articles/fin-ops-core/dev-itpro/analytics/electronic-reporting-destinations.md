---
title: Elektronikus jelentéskészítés (ER) céljai
description: Ez a témakör az Elektronikus jelentéskészítés (ER) rendeltetési helyeinek kezelésével, a támogatott célhelyek típusaival, valamint a biztonsági szempontokkal kapcsolatban tartalmaz tájékoztatást.
author: nselin
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2e4c6951afbff367dc93072d20395c3a37fffbcb
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/07/2020
ms.locfileid: "3030773"
---
# <a name="electronic-reporting-er-destinations"></a>Elektronikus jelentéskészítés (ER) céljai

[!include [banner](../includes/banner.md)]

Konfigurálhatja az egyes Elektronikus jelentés (ER) formátum konfigurációjához tartozó célt és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. Ez a témakör ismerteti az ER célkezelés, a támogatott célok típusait és a biztonsági megfontolásokat.

Az ER-formátumkonfigurációk általában tartalmaznak legalább egy kimeneti összetevőt: egy fájlt. A konfigurációk általában több, különböző típusú eredménykomponensből állnak (pl. XML, TXT, XLSX, DOCX vagy PDF), amik egy, vagy több mappában kerülnek csoportosításra. Az ER célkezeléssel előre konfigurálható, hogy mi történjen, mikor a komponenseket futtatja. Alapértelmezés szerint a konfiguráció futtatásakor megjelenik egy párbeszédpanel, aminek segítségével mentheti vagy megnyithatja a fájlt. Ugyanez a viselkedésforma használatos, amikor egy ER konfigurációt importál, de nem konfigurál hozzá meghatározott célt. Miután létrehozta a célt a fő kimeneti komponens részére, a létrehozott cél felülírja az alapértelmezett viselkedést, és a mappa vagy fájl a cél beállításainak megfelelően kerül kiküldésre.

## <a name="availability-and-general-prerequisites"></a>Elérhetőség és általános előfeltételek

Az ER célok funkció a Microsoft Dynamics AX 7.0-ban (2016. február) nem elérhető. Ezért a következő típusú célhelyek használatához telepítenie kell a Microsoft Dynamics 365 for Operations 1611 (2016. november) vagy újabb verziót:

- [E-mail-cím](er-destination-type-email.md)
- [Archiválás](er-destination-type-archive.md)
- [Fájl](er-destination-type-file.md)
- [Képernyő](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

Másik lehetőségként telepíthet egyet a következő előfeltételek közül: Azonban ne feledje, hogy ezek az alternatívák az Elektronikus jelentéstétel célok korlátozottabb használatát teszik lehetővé.

- Microsoft Dynamics AX alkalmazás 7.0.1 verzió (2016. május)
- [Elektronikus jelentéskészítési cél kezelési alkalmazás gyorsjavítása](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Létezik egy [Nyomtatás](er-destination-type-print.md) céltípus is. A használatához telepíteni kell a Microsoft Dynamics 365 Finance 10.0.9 verziót (2020. április).

## <a name="overview"></a>Áttekintés

A célokat csak a jelenlegi Finance példányba [importált](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) ER konfigurációkhoz, és csak az **Elektronikus jelentéskonfigurációk** oldalon elérhető formátumokban állíthatja be. Az elektronikus jelentéstételi célkezelés funkció itt érhető el: **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítés célja**. Az **Elektronikus jelentéskészítés célja** lapon felül lehet bírálni a konfiguráció alapértelmezett működését. Az importált konfigurációk az **Új** gombra kattintva, majd a **Hivatkozás** mezőben a létrehozandó célbeállításokhoz használni kívánt konfiguráció kiválasztásával jeleníthetők meg, korábban nem láthatók.

[![Konfiguráció kiválasztása a Hivatkozás mezőben](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

A hivatkozás létrehozása után létrehozható egy célhely a hivatkozott ER-formátum mindegyik **Mappa** vagy **Fájl** kimeneti összetevőjéhez.

[![Fájlcél létrehozása](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Ezután be- és kikapcsolhatja a fájl egyes céljai az **Elérési út beállításai** párbeszédpanelen. A **Beállítások** gombbal egy kiválasztott fájl elérési útjának minden célja vezérelhető. Az **Útvonalbeállítások** párbeszédpanelen minden elérési utat külön vezérelhet a **Bekapcsolva** opcióval.

A Finance **10.0.9 előtti verzióiban** ugyanazon formátumú egyes eredménykomponensek számára csak **egy elérési utat** adhat meg, ami a **Fájlnév** mezőben kiválasztott fájl vagy mappa. A **10.0.9 és későbbi verziókban** azonban **több olyan célhelyet** is létre lehet hozni, amelyek azonos formátumú kimeneti összetevőkhöz szükségesek.

Ezzel a lehetőséggel beállíthatja például, hogy az Excel-formátumú kimenő dokumentumok létrehozásához használt fájltípusok számára milyen célhelyek létezzenek. Egy cél ([Archív](er-destination-type-archive.md)) beállítható, hogy az eredeti Excel-fájlt az ER-feladatok arcihumában tároljon, és egy másik cél ([E-mail](er-destination-type-email.md)) konfigurálható, hogy egyidejűleg [konvertálja](#OutputConversionToPDF) az Excel-fájlt PDF formátumra, és elküldje a PDF-fájlt e-mailben.

[![Több cél konfigurálása egyetlen formátumú elemhez](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

## <a name="destination-types"></a>Céltípusok

A következő célok támogatottak jelenleg az ER-formátumokhoz. Minden típust egyszerre kapcsolhat ki és be. Ezzel a módszerrel mindent úgy hagyhat, ahogy van, vagy elküldheti a komponenseket minden konfigurált célra.

- [E-mail-cím](er-destination-type-email.md)
- [Archiválás](er-destination-type-archive.md)
- [Fájl](er-destination-type-file.md)
- [Képernyő](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Nyomtatás](er-destination-type-print.md)

## <a name="applicability"></a>Alkalmazhatóság

A célokat csak importált ER konfigurációkhoz, és csak az **Elektronikus jelentéskonfigurációk** oldalon elérhető formátumokban állíthatja be.

> [!NOTE]
> A konfigurált célhelyek vállalatra jellemzőek. Ha azt tervezi, hogy az aktuális Finance példány különböző vállalkozásaiban az ER-formátumot kívánja használni, akkor mindegyik vállalat esetében konfigurálnia kell az ER-formátum céljait.

Ha egy kiválasztott formátumhoz a fájlok célhelyeit konfigurálja, akkor az egész formátumra konfigurálja őket.

[![Konfiguráció hivatkozás](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

Ugyanakkor előfordulhat, hogy az aktuális Palermo példányba importált formátumnak több [verziója](general-electronic-reporting.md#component-versioning) van. Megtekintheti őket, ha kiválasztja a **Konfiguráció** hivatkozást, amelyet a rendszer a **Referencia** mező kiválasztásakor ajánl fel.

[![Konfigurációverziók](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Alapértelmezésként a konfigurált célhelyeket a rendszer csak akkor alkalmazza, ha olyan ER-formátumverziókat futtat, amelyeknek az állapota **Kész** vagy **Megosztott**. Előfordulhat azonban, hogy a konfigurált célhelyeket kell használni, amikor a program futtatja az ER- formátumának piszkozatát. Módosíthatja például a formátum piszkozatát, és a konfigurált célhelyek alapján tesztelni tudja a létrejövő kimenetet. Hajtsa végre az alábbi lépéseket, ha alkalmazni szeretné a célokat az ER-formátumra a piszkozat verzió futtatásakor.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Célok használata piszkozat állapothoz** beállítása legyen **Igen**értékű.

[![Célok használata piszkozat állapothoz](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Ha egy ER-formátum piszkozat verzióját kívánja használni, ennek megfelelően be kell jelölnie az ER-formátumot.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. Állítsa a **Beállítás futtatása** beállítást **Igen** lehetőségre.

[![Beállítás futtatása opció](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Miután befejezte ezt a beállítást, elérhetővé válik a **Piszkozat futtatása** lehetőség a módosítható ER-formátumok esetében. Ennek a beállításnak az **Igen** értékre állítása esetén a formátum futtatásakor a formátum piszkozat verzióját használja a rendszer.

[![Piszkozat futtatása opció](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="DestinationFailure"></a>Rendeltetési hely meghibásodásának kezelése

A program általában egy adott üzleti folyamat hatókörén belül futtatja az ER-formátumot. Előfordulhat azonban, hogy egy ER-formátum végrehajtása során létrejövő kimenő dokumentumok szállítását esetenként az üzleti folyamat részének kell tekinteni. Ebben az esetben, ha a létrejövő kimenő dokumentumnak egy konfigurált rendeltetési helyre történő szállítása sikertelen, akkor az üzleti folyamat végrehajtását meg kell szakítani. A megfelelő ER-cél konfigurálásához jelölje be a **Feldolgozás leállítása meghibásodáskor** beállítást.

Beállíthatja például a szállítói kifizetések feldolgozását úgy, hogy az **ISO20022-átutalás** ER-formátum fusson a kifizetési fájlok és a kiegészítő dokumentumok (például a kísérőlevél és az ellenőrzési jelentés) létrehozásához. Ha egy fizetést csak akkor kell figyelembe venni sikeres feldolgozásúként, ha a kísérőlevélet sikeresen kézbesítik e-mailben, be kell jelölnie a **Feldolgozás leállítása meghibásodáskor** jelölőnégyzetet a **CoveringLetter** összetevőnél a megfelelő célhelyen, a következő ábrán látható módon. Ebben az esetben a feldolgozásra kiválasztott kifizetés állapotát csak akkor állítja **Nem** állapotról **Elküldve** állapotra a program, ha a létrejövő kísérőlevél sikeresen elfogadásra kerül egy olyan e-mail szolgáltató esetében, amely a Finance példányban be van állítva.

[![A fájlok rendeltetési helyének meghibásodásával kapcsolatos folyamatkezelés konfigurálása](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Ha nem jelöli be a **Feldolgozás leállítása meghibásodáskor** jelölőnégyzetet a **CoveringLetter** összetevőnél a célhelyen, fizetést akkor is sikeres feldolgozásúként jelöli meg a rendszer, ha a kísérőlevélet nem kézbesítik sikeresen e-mailben. A kifizetés állapota **Nem** állapotról **Elküldve** állapotra módosul, még akkor is, ha a kísérőlevél nem küldhető el, mert például hiányzik vagy helytelen a címzett vagy a feladó e-mail-címe.

## <a name="OutputConversionToPDF"></a>Kimenet átalakítása PDF-formátumba

A PDF-átalakítási beállítással a kimenetet Microsoft Office formátumból (Excel/Word) konvertálhatja PDF-formátumba.

### <a name="make-pdf-conversion-available"></a>A PDF-átalakítás elérhetővé tétele

Ha azt szeretné, hogy a PDF-átalakítási beállítás elérhető legyen az aktuális Finance példányban, nyissa meg a **Funkciókezelés** munkaterületet, és kapcsolja be az **Elektronikus jelentéskészítési kimenő dokumentumok átalakítása Microsoft Office-formátumból PDF-formátumba** funkciót.

[![A kimenő dokumentumok PDF-be konvertálási funkciójának bekapcsolása a Funkciókezelés modulban](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Alkalmazhatóság

A PDF-átalakítási beállítás csak azon fájlösszetevők esetében kapcsolható be, amelyeknél a kimenet Microsoft Office Excel vagy Word formátumú (**Excel-fájl**) létrehozásához használatosak. Ha ez a beállítás be van kapcsolva, a program automatikusan PDF-formátumra alakítja az Office formátumú kimenetet.

### <a name="limitations"></a>Korlátozások

> [!NOTE]
> Ez a funkció egy előnézeti funkció, azok a felhasználási feltételek vonatkoznak rá, amelyek itt olvashatók: [Kiegészítő felhasználási feltételek a Microsoft Dynamics 365 előnézetek esetén](https://go.microsoft.com/fwlink/?linkid=2105274).

> [!NOTE]
> A PDF-átalakítási beállítás csak felhőtelepítések esetén érhető el.
>
> A létrehozott PDF-fájl legfeljebb 300 oldalas lehet.
>
> A THS-időszakban csak a fekvő laptájolást támogatja a program az Excel-kimenetből előállított PDF-dokumentumban.
>
> Csak a Windows operációs rendszer közös rendszerbetűkészletei használhatók olyan kimenet átalakításához, amely nem tartalmaz beágyazott betűtípusokat.

### <a name="use-the-pdf-conversion-option"></a>A PDF-konverzió lehetőség használata

Ha be kívánja kapcsolni a PDF-konverziót egy célhelyre, jelölje be a **Konvertálás PDF formátumba** jelölőnégyzetet.

[![A PDF-konverzió bekapcsolása fájl célhelyére](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

## <a name="security-considerations"></a>Biztonsági megfontolások

Az ER célokhoz kétféle jog és kötelezettség létezik. Az egyik típus felügyeli a felhasználó képességét azon célok összességének karbantartására, melyek egy jogi személy számára lettek konfigurálva (vagyis vezérli az **Elektronikus jelentés céljai** oldalhoz való hozzáférést). A másik típus szabályozza az alkalmazás felhasználóját abban, hogy a futtatás során felülírja az ER-fejlesztők vagy ER-funkciótanácsadók által konfigurált célbeállításokat.

| Szerepkör (AOT-név)                     | Szerepkör neve                                  | Feladat (AOT-név)                     | Feladat neve                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Elektronikus jelentések fejlesztője             | ERFormatDestinationConfigure        | Elektronikus jelentéskészítési formátum céljának konfigurálása                |
| ERFunctionalConsultant              | Elektronikus jelentések funkcióival foglalkozó konzulens | ERFormatDestinationConfigure        | Elektronikus jelentéskészítési formátum céljának konfigurálása                |
| PaymAccountsPayablePaymentsClerk    | Kötelezettségkifizetési adminisztrátor            | ERFormatDestinationRuntimeConfigure | Elektronikus jelentéskészítési formátum céljának konfigurálása futásidőben |
| PaymAccountsReceivablePaymentsClerk | Kinnlevőség-kifizetési adminisztrátor         | ERFormatDestinationRuntimeConfigure | Elektronikus jelentéskészítési formátum céljának konfigurálása futásidőben |

> [!NOTE]
> A megelőző feladatokban két jogosultság kerül alkalmazásra. Ezeknek a jogosultságoknak a neve megegyezik a hozzájuk tartozó feladatokkal: **ERFormatDestinationConfigure** és **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Rendelkezem importált elektronikus konfigurációkkal, és látom azokat az Elektronikus jelentési konfigurációk oldalon. De miért nem látom őket az Elektronikus jelentési célok oldalon?

Győződjön meg arról, hogy az **Új** gombra kattintott, majd kiválasztott egy konfigurációt a **Hivatkozás** mezőben. Az **Elektronikus jelentési célok** oldalon csak azokat a konfigurációkat láthatja, melyekhez a célok konfigurálva vannak.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>Meg lehet határozni, hogy melyik Microsoft Azure Storage-fiókot és Azure Blob-tárhelyet használja a rendszer?

Szám A dokumentumkezelőben meghatározott és használt, alapértelmezett Microsoft Azure Blob-tárhely lesz használva.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Mi a célja a Fájl cél lehetőségnek a célbeállításoknál? Mire jó ez a beállítás?

A **Fájl** cél a párbeszédpanel irányítására szolgál. Ha bekapcsolja ezt a célt, vagy ha a konfigurációhoz nincs cél megadva, egy eredményfájl létrehozása után megjelenik a megnyitás vagy mentés párbeszédpanel.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Létezik példa egy olyan receptúrára, ami egy szállítói fiókra utaló receptúrát tartalmaz, ahová emaileket küldhetek?

A formula ER-konfigurációspecifikus. Például, ha az ISO 20022 Jóváírás Átutalása konfigurációt használja, használhatja az **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** vagy **model.Payments.Creditor.Identification.SourceID** karakterláncokat egy társított szállítói fiók eléréséhez.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Valamelyik formátumkonfigurációmban több fájl is van, melyek egy mappába lettek csoportosítva (Például Mappa1 tartalma Fájl1, Fájl2, és Fájl3). Hogyan állíthatom be úgy a célokat, hogy a Mappa1.zip ne legyen létrehozva, Fájl1 legyen emailben elküldve, Fájl2 legyen a SharePoint-ra küldve, és Fájl3-at egyből a konfiguráció lefutása után megnyithassam?

Az Ön formátumának először elérhetőnek kell lennie az ER-konfigurációknál. Ha teljesül ez az előfeltétel, nyissa meg az **Elektronikus jelentés célja** oldalt, majd hozzon létre új hivatkozást erre a konfigurációra. Ekkor négy fájlcélra lesz szüksége, egyre mindegyik eredménykomponenshez. Hozza létre az első fájlcélt, nevezze el pl. úgy, hogy **Mappa**, majd válassza ki a fájlnevet, ami a konfigurációban a mappát reprezentálja. Kattintson a **Beállítások** gombra, és győződjön meg róla, hogy minden cél ki van kapcsolva. Ehhez a fájlcélhoz nem lesz mappa létrehozva. A fájlok és szülőmappák közötti hierarchikus viszonyok miatt alapértelmezés szerint a fájlok ugyanúgy fognak viselkedni. Más szóval nem lesznek sehová elküldve. Ezen alapértelmezett viselkedés felülbírálásához három másik fájlcélt kell létrehoznia, egyet mindegyik fájlhoz. Az egyes célbeállításoknál be kell kapcsolnia azt a célt, ahová a fájlt küldeni kívánja.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
