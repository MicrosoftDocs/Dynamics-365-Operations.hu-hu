---
title: Elektronikus jelentéskészítés (ER) céljai
description: Ez a cikk az elektronikus jelentési célok kezelésével, a támogatott célok típusaival és a biztonsági szempontokkal kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 08/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: DocuType, ERSolutionTable
ms.openlocfilehash: b1bf6289e80769dfe8858f307cbb9b217b42dbb4
ms.sourcegitcommit: f2edc193003564c5bee1747f9c2b800feee342bd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/29/2022
ms.locfileid: "9360979"
---
# <a name="electronic-reporting-er-destinations"></a>Elektronikus jelentéskészítés (ER) céljai

[!include [banner](../includes/banner.md)]

Konfigurálhatja az egyes Elektronikus jelentés (ER) formátum konfigurációjához tartozó célt és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. Ez a cikk ismerteti az ER célkezelés, a támogatott célok típusait és a biztonsági megfontolásokat.

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

Létezik egy [Nyomtatás](er-destination-type-print.md) céltípus is. A használathoz telepítenie Microsoft Dynamics kell a 365 Finance 10.0.9-es verzióját (2020. április).

## <a name="overview"></a>Áttekintés

A célokat csak a jelenlegi Finance példányba [importált](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) ER konfigurációkhoz, és csak az **Elektronikus jelentéskonfigurációk** oldalon elérhető formátumokban állíthatja be. Az elektronikus jelentéstételi célkezelés funkció itt érhető el: **Szervezeti adminisztráció** \> **Elektronikus jelentés** \> **Elektronikus jelentéskészítés célja**.

### <a name="default-behavior"></a>Alapértelmezett viselkedés

Az ER formátumkonfiguráció alapértelmezett viselkedése attól függ, hogy milyen végrehajtási típust ad meg, amikor egy ER-formátum elindul.

Ha az **Intrastat-jelentés** párbeszédpanel **Futtatás a háttérben** gyorslapján a **Kötegelt feldolgozás** beállítást **Nem** értékre állítja egy ER-formátum azonnal lefut interaktív módban. Amikor a végrehajtás sikeresen befejeződött egy generált kimenő dokumentum elérhetővé válik letöltésre.

Ha az **Igen** értékre állítja be a **Kötegelt feldolgozás** beállítást, akkor a program [kötegelt](../sysadmin/batch-processing-overview.md) módban futtatja az ER-formátumot. A program létrehozta a megfelelő kötegelt feladatot, amely az **ER-paraméterek** **Futtatás hattérben** lapján létrehozott paraméterek alapján jön létre.

> [!NOTE]
> Egy feladatleírás tájékoztatja Önt egy ER-formátumleképezés futtatásáról. A futtatott ER-komponens nevét is tartalmazza.

[![ER-formátum futtatása.](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

A feladattal kapcsolatos információk több helyen is megtalálhatók:

- Nyissa meg az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** az ütemezett feladat állapotának ellenőrzéséhez.
- Nyissa meg a **Szervezeti felügyelet** \> **Elektronikus jelentéskészítés** \> **Elektronikus jelentéskészítési feladatok**, hogy ellenőrizze az ütemezett feladat állapotát és a teljesített feladat végrehajtási eredményeit. Amikor a feladat végrehajtása sikeresen befejeződött, válassza a **Fájlok megjelenítése** lehetőséget az **Elektronikus jelentéskészítési feladatok** lapon a létrejövő kimenő dokumentum lekéréséhez.

    > [!NOTE]
    > Ez a dokumentum az aktuális feladatrekordhoz tartozó mellékletként tárolódik, és a [Dokumentumkezelési](../../fin-ops/organization-administration/configure-document-management.md) keretrendszer vezérli. Az ilyen típusú műtárgyak tárolásához használt [dokumentumtípus](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) beállítása az [ER paraméterek](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) között történik.

- Az **Elektronikus jelentéskészítési feladatok** lapon jelölje be a **Fájlok megjelenítése** a feladatok végrehajtása során létrejövő hibák és figyelmeztetések listájának megtekintéséhez.

    [![ER-feladatok listájának áttekintése.](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>Konfigurált viselkedés használata

Az **Elektronikus jelentéskészítés célja** lapon felül lehet bírálni a konfiguráció alapértelmezett működését. Az importált konfigurációk az **Új** gombra kattintva, majd a **Hivatkozás** mezőben a létrehozandó célbeállításokhoz használni kívánt konfiguráció kiválasztásával jeleníthetők meg, korábban nem láthatók.

[![Konfiguráció kiválasztása a Hivatkozás mezőben.](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

A hivatkozás létrehozása után létrehozható egy célhely a hivatkozott ER-formátum mindegyik **Mappa** vagy **Fájl** kimeneti összetevőjéhez.

[![Fájlcél létrehozása.](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Ezután be- és kikapcsolhatja a fájl egyes céljai az **Elérési út beállításai** párbeszédpanelen. A **Beállítások** gombbal egy kiválasztott fájl elérési útjának minden célja vezérelhető. Az **Útvonalbeállítások** párbeszédpanelen minden elérési utat külön vezérelhet a **Bekapcsolva** opcióval.

A Finance **10.0.9 előtti verzióiban** ugyanazon formátumú egyes eredménykomponensek számára csak **egy elérési utat** adhat meg, ami a **Fájlnév** mezőben kiválasztott fájl vagy mappa. A **10.0.9 és későbbi verziókban** azonban **több olyan célhelyet** is létre lehet hozni, amelyek azonos formátumú kimeneti összetevőkhöz szükségesek.

Ezzel a lehetőséggel beállíthatja például, hogy az Excel-formátumú kimenő dokumentumok létrehozásához használt fájltípusok számára milyen célhelyek létezzenek. Egy cél ([Archív](er-destination-type-archive.md)) beállítható, hogy az eredeti Excel-fájlt az ER-feladatok arcihumában tároljon, és egy másik cél ([E-mail](er-destination-type-email.md)) konfigurálható, hogy egyidejűleg [konvertálja](#OutputConversionToPDF) az Excel-fájlt PDF formátumra, és elküldje a PDF-fájlt e-mailben.

[![Több cél konfigurálása egyetlen formátumú elemhez.](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

ER-formátum futtatásakor a rendszer mindig futtat minden célt, amely a formátum összetevőihez van konfigurálva. Emellett a Finance **10.0.17-es és újabb verziókban** az ER-célokkal kapcsolatos funkciók tovább tökéletesítettek, és így különböző célkészleteket lehet konfigurálni egyetlen ER-formátumhoz. Ez a konfiguráció egy-egy adott felhasználói művelethez beállítottként jelöli meg a készleteket. Az ER API-t [kibővítettük](er-apis-app10-0-17.md), így a felhasználó által az ER-formátum futtatásával rendelkezésre áll egy művelet. A megadott műveletkód át van adni az ER-céloknak. A megadott műveletkódtól függően az ER-formátum különböző célokat futtathat. További tájékoztatás: [Műveletfüggő ER-célok konfigurálása](er-action-dependent-destinations.md).

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

[![Konfigurációs hivatkozás.](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

Ugyanakkor előfordulhat, hogy az aktuális Palermo példányba importált formátumnak több verziója van. Megtekintheti őket, ha kiválasztja a **Konfiguráció** hivatkozást, amelyet a rendszer a **Referencia** mező kiválasztásakor ajánl fel.

[![Konfigurációverziók.](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Alapértelmezésként a konfigurált célhelyeket a rendszer csak akkor alkalmazza, ha olyan ER-formátumverziókat futtat, amelyeknek az állapota **Kész** vagy **Megosztott**. Előfordulhat azonban, hogy a konfigurált célhelyeket kell használni, amikor a program futtatja az ER- formátumának piszkozatát. Módosíthatja például a formátum piszkozatát, és a konfigurált célhelyek alapján tesztelni tudja a létrejövő kimenetet. Hajtsa végre az alábbi lépéseket, ha alkalmazni szeretné a célokat az ER-formátumra a piszkozat verzió futtatásakor.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Célok használata piszkozat állapothoz** beállítása legyen **Igen** értékű.

[![Célok használata piszkozat állapothoz.](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Ha egy ER-formátum piszkozat verzióját kívánja használni, ennek megfelelően be kell jelölnie az ER-formátumot.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. Állítsa a **Beállítás futtatása** beállítást **Igen** lehetőségre.

[![Beállítás futtatása opció.](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Miután befejezte ezt a beállítást, elérhetővé válik a **Piszkozat futtatása** lehetőség a módosítható ER-formátumok esetében. Ennek a beállításnak az **Igen** értékre állítása esetén a formátum futtatásakor a formátum piszkozat verzióját használja a rendszer.

[![Piszkozat futtatása opció.](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>Rendeltetési hely meghibásodásának kezelése

A program általában egy adott üzleti folyamat hatókörén belül futtatja az ER-formátumot. Előfordulhat azonban, hogy egy ER-formátum végrehajtása során létrejövő kimenő dokumentumok szállítását esetenként az üzleti folyamat részének kell tekinteni. Ebben az esetben, ha a létrejövő kimenő dokumentumnak egy konfigurált rendeltetési helyre történő szállítása sikertelen, akkor az üzleti folyamat végrehajtását meg kell szakítani. A megfelelő ER-cél konfigurálásához jelölje be a **Feldolgozás leállítása meghibásodáskor** beállítást.

Beállíthatja például a szállítói kifizetések feldolgozását úgy, hogy az **ISO20022-átutalás** ER-formátum fusson a kifizetési fájlok és a kiegészítő dokumentumok (például a kísérőlevél és az ellenőrzési jelentés) létrehozásához. Ha egy fizetést csak akkor kell figyelembe venni sikeres feldolgozásúként, ha a kísérőlevélet sikeresen kézbesítik e-mailben, be kell jelölnie a **Feldolgozás leállítása meghibásodáskor** jelölőnégyzetet a **CoveringLetter** összetevőnél a megfelelő célhelyen, a következő ábrán látható módon. Ebben az esetben a feldolgozásra kiválasztott kifizetés állapotát csak akkor állítja **Nem** állapotról **Elküldve** állapotra a program, ha a létrejövő kísérőlevél sikeresen elfogadásra kerül egy olyan e-mail szolgáltató esetében, amely a Finance példányban be van állítva.

[![A fájlok rendeltetési helyének meghibásodásával kapcsolatos folyamatkezelés konfigurálása.](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Ha nem jelöli be a **Feldolgozás leállítása meghibásodáskor** jelölőnégyzetet a **CoveringLetter** összetevőnél a célhelyen, fizetést akkor is sikeres feldolgozásúként jelöli meg a rendszer, ha a kísérőlevélet nem kézbesítik sikeresen e-mailben. A kifizetés állapota **Nem** állapotról **Elküldve** állapotra módosul, még akkor is, ha a kísérőlevél nem küldhető el, mert például hiányzik vagy helytelen a címzett vagy a feladó e-mail-címe.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>Kimenet átalakítása PDF-formátumba

A PDF-átalakítási beállítással a Microsoft Office (Excel vagy Word) formátumú kimenetet konvertálhatja PDF-formátumba.

### <a name="make-pdf-conversion-available"></a>A PDF-átalakítás elérhetővé tétele

Ha azt szeretné, hogy a PDF-átalakítási beállítás elérhető legyen az aktuális Finance példányban, nyissa meg a **Funkciókezelés** munkaterületet, és kapcsolja be az **Elektronikus jelentéskészítési kimenő dokumentumok átalakítása Microsoft Office-formátumból PDF-formátumba** funkciót.

[![A kimenő dokumentumok PDF-be konvertálási funkciójának bekapcsolása a Funkciókezelés modulban.](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Alkalmazhatóság

A Finance-szolgáltatás **10.0.18 előtti verzióiban** a PDF-konverzió beállítás csak az olyan **Excel\\Fájl** komponensekhez állítható be, amelyek Office-formátumú (Excel vagy Word) kimenet generálásához használatosak. Ha ez a beállítás be van kapcsolva, a program automatikusan PDF-formátumra alakítja az Office formátumú kimenetet. A **10.0.18-as és újabb verziókban** azonban a **közös\\fájltípus** összetevőihez is be lehet kapcsolni ezt a beállítást.

> [!NOTE]
> Ügyeljen arra a figyelmeztető üzenetre, amely akkor jelenik meg, ha a PDF-konverziós lehetőséget a **közös\\fájltípus** egyik ER-összetevőjére vonatkozóan kapcsolja be. Ez az üzenet arról tájékoztat, hogy a tervezés során nem garantálható, hogy a kiválasztott fájlösszetevő futásidőben elérhetővé teszi a PDF-formátumot vagy PDF konvertálható tartalmat. Ezért csak akkor kapcsolja be ezt a beállítást, ha biztos benne, hogy a kiválasztott fájlösszetevő úgy van beállítva, hogy futásidőben elérhetővé tegye a PDF-formátumot vagy a PDF konvertálható tartalmat.
> 
> Ha a egy formátum összetevőjéhez bekapcsolja a PDF-konverziós beállítást, akkor az összetevő PDF-formátumtól különböző formátumban teszi elérhetővé a tartalmat, és ha a megjelenített tartalom nem konvertálható PDF-formátumra, kivétel lép fel futásidőben. A kapott üzenet arról tájékoztat, hogy a létrehozott tartalom nem konvertálható PDF-formátumra.

### <a name="limitations"></a>Korlátozások

A Pénzügy 10.0.9 **szerint** a PDF-konverziós beállítás csak a felhőalapú telepítés esetén érhető el. A Pénzügy **10.0.27-es** verziójától kezdve a PDF-átváltási [lehetőség minden olyan létesítményben elérhető, amely internetkapcsolattal](../user-interface/client-disconnected.md) rendelkezik.

A létrehozott PDF-fájl legfeljebb 300 oldalas lehet.

A Pénzügyi verzió **10.0.9** szerint az Excel-kimenetből előállított PDF-dokumentum csak a tájolást támogatja a tájolással. A Pénzügy 10.0.10 **·**[verziótól](#SelectPdfPageOrientation) kezdve megadhatja az Excel-kimenetből előállított PDF-dokumentum oldal tájolását az ER-cél konfigurálása során.

Csak a Windows operációs rendszer közös rendszerbetűkészletei használhatók olyan kimenet konvertálásához, amely nem tartalmaz beágyazott betűtípusokat.

### <a name="resources"></a>Erőforrások

A PÉNZÜGY 10.0.29-es verziója előtt a PDF-konverzió csak az aktuális Pénzügyi példányon kívülre ható. A generált fájlt elküldték a Pénzügy rendszerből az átalakítási szolgáltatásnak, és az a szolgáltatás ezután visszaküldte az átalakított dokumentumot. **A 10.0.29-es** **Microsoft Office és újabb verziókban azonban az Elektronikus jelentés formátumból PDF** **formátumba való konvertálása funkción kívül az alkalmazás-erőforrások használata lehetővé teszi a CBD-dokumentumok Word formátumról PDF** formátumra történő konvertálását is. Ez a funkció lehetővé teszi a létrehozott Word-dokumentumok PDF-formátumúvá konvertálását az aktuális pénzügyi példány alkalmazáskiszolgáló-erőforrásainak használatával. 

Itt vannak a helyi PDF-átalakítás **előnyei**, amikor az alkalmazás-erőforrások használata a CBD-dokumentumok Word-formátumra konvertálásának elvégzéséhez engedélyezve van:

- Az előállított PDF-dokumentum nem korlátozódik [a](#limitations) lapok maximális számára.
- Az átalakított Word-dokumentum nagy [számú tartalomvezérlőt tartalmazhat](https://fix.lcs.dynamics.com/Issue/Details?bugId=647877&dbType=3).
- A létesítményben való telepítéshez nem szükséges internetkapcsolat.

### <a name="use-the-pdf-conversion-option"></a>A PDF-konverzió lehetőség használata

Ha be kívánja kapcsolni a PDF-konverziót egy célhelyre, jelölje be a **Konvertálás PDF formátumba** jelölőnégyzetet.

[![A PDF-konverzió bekapcsolása fájl célhelyére.](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">Lap tájolásának kiválasztása PDF-konverzióhoz</a>

Ha Excel-formátumban generál egy Elektronikus jelenrés konfigurációt, és PDF-formátumra szeretné átalakítani, akkor kifejezetten megadhatja a PDF-dokumentum tájolását. Ha bejelöli a **Konvertálás PDF formátumba** jelölőnégyzetet, hogy egy célhelyre bekapcsolja a PDF-konverziót egy Excel formátumú kimeneti fájl létrehozásához, akkor a **Lap tájolása** mező elérhetővé válik a **PDF-konverzió beállításai** gyorslapon. A **Lap tájolása** mezőben válassza ki a preferált tájolást.

[![Lap tájolásának kiválasztása PDF-konverzióhoz.](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

Ha azt szeretné, hogy a PDF laptájolása kiválasztható legyen, telepítse a Finance 10.0.10 vagy újabb verzióját. A Finance **10.0.23 előtti verzióiban** ez a beállítás a következő tájolási beállításokat kínálja fel:

- Álló
- Fekvő

A kiválasztott laptájolás a kimeneti dokumentum minden oldalára vonatkozik, amely Excel-formátumban jön létre, majd PDF formátumra lesz konvertálva.

A **10.0.23-as és újabb verziókban** azonban a lap tájolási beállításainak listája a következőképpen módosult:

- Álló
- Fekvő
- Munkalaphoz kapcsolódó

Ha kiválasztja a **Munkalaphoz kapcsolódó** beállítást, a létrehozott Excel-munkafüzet minden munkalapja PDF-formátumba lesz konvertálva a használt Excel-sablonban a munkalaphoz beállított oldaltájolás alapján. Tehát lehet, hogy egy végső olyan PDF-dokumentumot kap, amely álló és fekvő oldalakat tartalmaz. 

Ha egy Word-formátumú ER-konfigurációt konvertálnak PDF-formátumban, akkor a program mindig a Word-dokumentumból veszi át a PDF-dokumentum laptájolását.

## <a name="output-unfolding"></a>Kimenet kibontása

Amikor az elektronikus jelentéskészítési formátum **Mappa** összetevőjéhez konfigurál egy célhelyet, megadhatja, hogy az összetevő kimenete hogyan legyen kézbesítve a konfigurált célhelyre.

### <a name="make-output-unfolding-available"></a>Kimenet kibontásának elérhetővé tétele

A kimenet kibontására szolgáló aktuális Finance-példányban való elérhetővé tételéhez nyissa meg a **Funkciókezelés** munkaterületet, és kapcsolja be **Az elektronikus jelentéskészítés célhelyeinek engedélyezése a mappák tartalmának külön fájlba való küldéséhez** funkciót.

### <a name="applicability"></a>Alkalmazhatóság

A kimenet kibontása beállítás csak a **Mappa** típus formátumösszetevőihez konfigurálható. Amikor megkezdi egy **Mappa** összetevő konfigurálását, az **Általános** gyorslap elérhetővé válik az **Elektronikus jelentéskészítés célja** oldalon. 

### <a name="use-the-output-unfolding-option"></a>A kimenet kibontásának használata

Az **Általános** gyorslap **Mappa küldése a következőként** mezőjében válassza ki a következő értékek valamelyikét:

- **ZIP-archívum** – A létrehozott fájl zip-fájlként kézbesíti.
- **Külön fájlok** – Egy létrehozott zip-fájl összes létrehozott fájlját külön fájlként kézbesíti.

    > [!NOTE]
    > Ha a **Külön fájlok** beállítást választja, a létrehozott kimenetet tömörített állapotban tárolja a rendszer a memóriában. Emiatt a rendszer maximális [fájlméretet](er-compress-outbound-files.md) alkalmaz a tömörített kimenetre, ha a valós fájlméret meghaladhatja ezt a maximális korlátot. Javasoljuk, hogy akkor válassza ezt az értéket, ha a generált kimenet nagy méretére számít.

[![Célhely konfigurálása Mappa formátum-összetevőhöz.](./media/er_destinations-set-unfolding-option.png)](./media/er_destinations-set-unfolding-option.png)

### <a name="limitations"></a>Korlátozások

Ha a **Mappa küldése a következőként** mezőben a **Külön fájlok** értéket adja meg a más beágyazott **Mappa** összetevőket tartalmazó **Mappa** összetevőhöz, akkor a rendszer nem alkalmazza a beállítást rekurzív módon a többi **Mappa** összetevőre.

## <a name="change-page-layout-properties-of-a-template"></a><a name="change-page-layout-properties-of-a-template"></a> Sablon lapelrendezés-tulajdonságainak módosítása

Az ER-célokat olyan ER Microsoft Office formátumösszetevők számára konfigurálhatja, amelyek a jelentések generálása egy sablonjának (Excel vagy Word) formátumban való használatára vannak kialakítva. Ha nem Ön ennek a formátumnak a tulajdonosa, és módosítania kell a formátumsablon lapelrendezés-tulajdonságait, a Pénzügy verziókban a 10.0.29-es verzió előtt létre kell hoznia egy származtatott formátumot, és módosítania kell a sablon tulajdonságait. Ezután meg kell tartani a származtatott formátumkonfigurációt. A 10.0.29-es és későbbi verziókban azonban futásidőben módosíthatja a sablon oldalelrendezés-tulajdonságait, hogy elkerülje a származtatott formátumkonfiguráció létrehozását és karbantartását. Ehhez állítsa be a kívánt tulajdonságokat a konfigurált ER-cél beállításainak részeként. Ha ER-formátumot futtat, és olyan ER-célt hajt végre, amely bizonyos lapelrendezés-tulajdonságok használatára van konfigurálva, akkor a program a használt sablonra alkalmazza a végrehajtott cél oldalelrendezés-tulajdonságainak értékeit, lecserélve az eredeti sablon tulajdonságait. Ugyanannak a formátumnak különböző célhelyeket is be lehet állítani, amelyek a használatban vannak a sablon különböző lapelrendezés-tulajdonságainak konfigurálásához.

A következő tulajdonságok konfigurálhatók ER-célként olyan formátumösszetevők számára, amelyek az Excel- és Word-formátumok sablonjának használatára vannak kialakítva:

- Oldal tájolása
    - Álló
    - Fekvő
- Papírméret
    - A3
    - A4
    - A5
    - B4
    - B5
    - Executive
    - Jogi információ
    - Betű
    - Statement
    - Tabloid
- Oldal margói
    - Fent
        - Fejléc
    - Lent
        - Lábléc
    - Balra
    - Jobb

> [!NOTE]
> Az így konfigurált [sablon oldal tájolását a PDF-konverzió](#select-a-page-orientation-for-pdf-conversion) oldal tájolásának megfelelően kell igazítani, amennyiben a PDF-átalakítás be van állítva.

Az oldal margóihoz ki kell választani a hosszegységet:

- Hüvelyk
- Centiméter
- Milliméter

![Lapelrendezés tulajdonságainak beállítása az Elektronikus jelentési cél oldalon.](./media/er_destinations-set-page-layout-properties.png)

> [!TIP]
> Ha centiméteres margót jelölnek, és több tizedesjegyet is meghatároznak, futásidőben kerekíteni kell arra a legközelebbi értékre, amelynél 1 tizedesjegy van.
>
> Ha az árrés értékét ezredmásodpermben jelennek meg, és tizedesjegyekkel jelölik, akkor az Excel futásidejű kerekítése a legközelebbi egész értékre lesz kerekítve tizedesjegy nélkül.
>
> Ha az árrés értékét ezredmásodpermben jelennek meg, és több tizedesjegyet is meghatároznak, futásidőben a Word értéke a legközelebbi értékre lesz kerekítve egy tizedesjegy pontossággal.

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

A célként használt **Fájl** a webböngésző párbeszédpaneljének szabályozására használható, amikor ER-formátumot futtat interaktív módban. Ha bekapcsolja ezt a célt, vagy ha a konfigurációhoz nincs cél megadva, egy eredményfájl létrehozása után megjelenik a megnyitás vagy mentés párbeszédpanel a webböngészőjében.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Létezik példa egy olyan receptúrára, ami egy szállítói fiókra utaló receptúrát tartalmaz, ahová emaileket küldhetek?

A formula ER-konfigurációspecifikus. Például, ha az ISO 20022 Jóváírás Átutalása konfigurációt használja, használhatja az **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** vagy **model.Payments.Creditor.Identification.SourceID** karakterláncokat egy társított szállítói fiók eléréséhez.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Valamelyik formátumkonfigurációmban több fájl is van, melyek egy mappába lettek csoportosítva (Például Mappa1 tartalma Fájl1, Fájl2, és Fájl3). Hogyan állíthatom be úgy a célokat, hogy a Mappa1.zip ne legyen létrehozva, Fájl1 legyen emailben elküldve, Fájl2 legyen a SharePoint-ra küldve, és Fájl3-at egyből a konfiguráció lefutása után megnyithassam?

Az Ön formátumának először elérhetőnek kell lennie az ER-konfigurációknál. Ha teljesül ez az előfeltétel, nyissa meg az **Elektronikus jelentés célja** oldalt, majd hozzon létre új hivatkozást erre a konfigurációra. Ekkor négy fájlcélra lesz szüksége, egyre mindegyik eredménykomponenshez. Hozza létre az első fájlcélt, nevezze el pl. úgy, hogy **Mappa**, majd válassza ki a fájlnevet, ami a konfigurációban a mappát reprezentálja. Kattintson a **Beállítások** gombra, és győződjön meg róla, hogy minden cél ki van kapcsolva. Ehhez a fájlcélhoz nem lesz mappa létrehozva. A fájlok és szülőmappák közötti hierarchikus viszonyok miatt alapértelmezés szerint a fájlok ugyanúgy fognak viselkedni. Más szóval nem lesznek sehová elküldve. Ezen alapértelmezett viselkedés felülbírálásához három másik fájlcélt kell létrehoznia, egyet mindegyik fájlhoz. Az egyes célbeállításoknál be kell kapcsolnia azt a célt, ahová a fájlt küldeni kívánja.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)

[Műveletfüggő ER-célok konfigurálása](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
