---
title: Tervezzen konfigurációkat a kimenő dokumentumok Excel-formátumban történő létrehozásához
description: Ez a témakör azt mutatja be, hogyan lehet az Elektronikus jelentéskészítés (ER) formátumát egy Excel-sablon kitöltéséhez tervezni, majd a kimenő Excel-formátumú dokumentumokat generálni.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b2f38aa9e5eff9366697afd57ceefd06f026096
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388263"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>(ER) Az Excel formátumban létrejövő dokumentumokra vonatkozó konfigurációk tervezése

[!include[banner](../includes/banner.md)]

Elektronikus jelentéskészítő [(ER)](general-electronic-reporting.md) formátumkonfigurációt tervezhet, amely egy ER Microsoft Excel formátumösszetevővel rendelkezik, és amely konfigurálható a kimenő dokumentumok munkafüzet formátumú előállítására. Erre a célra külön ER formátumú komponenseket kell használni.

Ha további tájékoztatást szeretne erről a funkcióról, kövesse a [Jelentések készítésének konfigurációja OPENXML formátumban](tasks/er-design-reports-openxml-2016-11.md) témakör lépéseit.

## <a name="add-a-new-er-format"></a>Új ER-formátum hozzáadása

Amikor egy új ER formátumú konfigurációt hoz létre egy kimenő dokumentum Excel-munkafüzet-formátumban történő generálásához, vagy ki kell választania a **Excel** értéket a **Formátumtípus** attribútumához vagy hagyja a **formátumtípus** attribútumot ütesen.

- Ha az **Excelt** választja, akkor a formátumot csak Excel formátumú kimenő dokumentumok generálásához állíthatja be.
- Ha üresen hagyja az attribútumot, konfigurálhatja azt a formátumot, amellyel a kimenő dokumentumok bármilyen formában elkészíthetők.

A konfiguráció ER formátumkomponensének konfigurálásához válassza **Tervező** lehetőséget a művelet panelen, majd nyissa meg az ER-formátumkomponenst az ER operációs tevezőben.

![Konfigurációk oldala.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Excelfájl-komponens

### <a name="manual-entry"></a>Manuális bejegyzés

Ahhoz, hogy a kimenő dokumentumokat Excel-formátumban hozza létre, egy **Excel\\fájl** komponenst kell hozzáadnia a konfigurált ER-formátumhoz.

![Excel\fájl-komponens.](./media/er-excel-format-add-file-component.png)

A kimenő dokumentumok elrendezésének megadásához csatolnia kell egy olyan Excel-munkafüzetet, amelynek .xlsx kiterjesztéssel rendelkezik az **Excel\\fájlt** tartalmazó komponense, mint a kimenő dokumentumok sablonja.

> [!NOTE]
> A sablon manuális csatolása esetén olyan [dokumentumtípust](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types) dokumentumtípust kell használnia, amely az adott célra be van állítva az [ER paramétereiben](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Melléklet hozzáadása az Excel\fál-komponenshez.](./media/er-excel-format-add-file-component2.png)

Ha meg szeretné adni, hogy a rendszer hogyan töltse ki a csatolt sablont a konfigurált ER-formátum futtatásakor, akkor hozzá kell adnia a beágyazott **Lapok**, **Tartomány** és **Cella** komponenseket az **Excel\\fájl** komponenshez. Minden beágyazott komponenshez társítani kell egy elem elnevezésű Excelt.

### <a name="template-import"></a>Sablon importálása

Kiválaszthatja az **Importálás Excelből** lehetőséget a Műveleti panel **Importálás** lapfülén, ha egy új sablont üres ER-formátumba importál. Ebben a példában a program automatikusan létrehoz egy **Excel\\fájl** komponenst, és az importált sablont hozzárendeli a program. A program az összes szükséges ER-komponenst automatikusan létrehozza a felismert Excel nevű tételek listájának alapján.

![Az Importálás az Excelből lehetőség kiválasztása.](./media/er-excel-format-import-template.png)

> [!NOTE]
> Ha létre szeretné hozni az opcionális **Lap** elemet szerkeszthető ER-formában, akkor állítsa az **Excel lapformátum elem létrehozása** lehetőséget **Igen** értékűre.

## <a name="sheet-component"></a>Lapkomponens

A **Lap** komponens azt jelzi, hogy a csatolt Excel-munkafüzet munkalapját ki kell tölteni. A munkalap Excel-sablonban megadott név a **Lap** komponens tulajdonságában van meghatározva.

> [!NOTE]
> Ez a komponens nem kötelező olyan Excel-munkafüzetekhez, amelyek egyetlen munkalapot tartalmaznak.

Az ER műveleti tervező **Leképezés** lapján beállíthatja az **Engedélyezés** tulajdonságot egy **Lap** komponenshez annak meghatározására, hogy a komponenst egy generált dokumentumban kell-e elhelyezni:

- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Igaz** értéket ad vissza, vagy ha nincs megadva a kifejezés, akkor a rendszer a megfelelő munkalapot helyezi a létrejövő dokumentumba.
- Ha az **Engedélyezve** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Hamis** értéket ad vissza, akkor a létrejövő dokumentum nem tartalmaz munkalapot.

![Példa a Lap összetevőre.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Tartomány-összetevő

### <a name="nested-components"></a>Beágyazott összetevők

#### <a name="data-typing"></a>Adatok beírása

A **Tartomány** összetevőnek más beágyazott ER-összetevői is lehet, amelyek a megfelelő tartományok értékeinek a beírása során használatosak.

- Ha a **Szöveges** csoport bármely összetevője az értékek megadására szolgál, akkor az érték egy Excel-tartományban jelenik meg szöveges értékként.

    > [!NOTE]
    > Ez a minta a megadott értékek formátumára használható a pályázatban megadott területi beállítás alapján.

- Ha az Excel-csoport Cella **összetevőjét használja az értékek bevitelére, akkor az értéket Excel-tartományban kell megadni értékként az** adott Cella összetevő kötése által meghatározott adattípusként **.** **·** Az adattípus lehet például **String**, **Real** **vagy Egész**.

    > [!NOTE]
    > Ennek a mintának a használatával engedélyezheti az Excel-alkalmazás számára a megadott értékek formátumát a kimenő dokumentumot megnyitó helyi számítógép területi beállításai alapján.

#### <a name="row-handling"></a>Sorkezelés

A **Tartomány** összetevő függőlegesen replikálható úgy, hogy több sort generáljon egy Excel-munkalapon. A sorokat a **szülő** **tartomány összetevő vagy a tartománybe ágyazott összetevők alapján lehet** generálni.

A 10.0.26-os és újabb verziókban egy generált munkalapon kényszerítheti, hogy a létrehozott sorok ugyanazon az oldalon tartsanak. Az ER-formátumtervezőben **·** **·** **állítsa** Igen beállításra a Sorok megtartása lehetőséget a szerkeszthető ER formátumban szülő tartomány-összetevő esetén. Az ER ekkor megpróbálja ugyanazon az oldalon tartani a tartomány által létrehozott összes tartalmat. Ha a tartalom magassága meghaladja az aktuális lapon fennmaradó területet, akkor egy oldaltörést ad hozzá a program, és a tartalom a következő új lap tetejétől indul.

> [!NOTE]
> Javasoljuk, hogy **a Sorok megtartása együtt** beállítás csak olyan tartományokra legyen konfigurálva, amelyek a létrehozott dokumentumok teljes szélességére átfogják.
>
> A **Sorok megtartása beállítás** csak excel-munkafüzetsablon **használatára beállított Excel-fájlösszetevőkre \>** érvényes.
>
> A **Sorok megtartása együtt** **beállítás csak akkor használható, ha engedélyezve van az Elektronikus jelentési keretrendszer EPGra** tárhasználatának engedélyezése.
>
> Ez a funkció az oldalösszetevő **alatt** található tartományösszetevőkhöz **használható**. Ugyanakkor nincs garancia arra, hogy [a](er-paginate-excel-reports.md#add-data-sources-to-calculate-page-footer-totals) lap láblécösszegei helyesen ki lesznek számítva az [adatforrások](er-data-collection-data-sources.md) használatával.

A beállítás használatának [elsajátítása érdekében kövesse az ER-formátum megtervezése példáját, ha egy Excel-lapon szeretne sorokat együtt tartani](er-keep-excel-rows-together.md).

### <a name="replication"></a>Replikáció

A **Replikációs irány** tulajdonság határozza meg, hogy a tartomány ismétlődik-e a generált dokumentumban, és ha igen, hogyan:

- **Nincs replikáció** – a program nem fogja megismételni a megfelelő Excel-tartományt a generált dokumentumban.
- **Függőleges** – a megfelelő Excel-tartomány függőlegesen fog ismétlődni a generált dokumentumban. Minden replikált tartomány az Eredeti tartomány alá lesz ásva egy Excel-sablonban. Az ismétlések számát a **Rögzítési lista** típus adatforrásainak rögzítéseinek számának meghatározása határozza meg, amely az típusú ER-komponenshez kötődik.
- **Vízszintes** – a program vízszintesen megismétli a megfelelő Excel-tartományt a generált dokumentumban. A rendszer minden replikált tartományt az Eredeti tartománytól jobbra, egy Excel-sablonban fog tartalmazni. Az ismétlések számát a **Rögzítési lista** típus adatforrásainak rögzítéseinek számának meghatározása határozza meg, amely az típusú ER-komponenshez kötődik.

    Ha további tájékoztatást szeretne a vízszintes replikálásról, hajtsa végre a [Vízszintesen kibontható tartományok az Excel-jelentések oszlopainak dinamikus hozzáadásához](tasks/er-horizontal-1.md) dokumentum lépéseit.

### <a name="enabling"></a>Engedélyezés folyamatban

Az ER műveleti tervező **Leképezés** lapján beállíthatja az **Engedélyezés** tulajdonságot egy **Tartomány** komponenshez annak meghatározására, hogy a komponenst egy generált dokumentumban kell-e elhelyezni:

- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Igaz** értéket ad vissza, vagy ha nincs megadva a kifejezés, akkor a rendszer a megfelelő tartománnyal tölti ki a létrejövő dokumentumot.
- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Hamis** értéket ad vissza, és ez a tartomány nem az összes sort vagy oszlopot reprezentálja, akkor a rendszer a megfelelő tartománnyal tölti ki a létrejövő dokumentumot.
- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Hamis** értéket ad vissza, és ez a tartomány az összes sort vagy oszlopot reprezentálja, akkor a létrejövő dokumentum ezeket a sorokat és oszlopokat rejtett sorokként és oszlopokként fogja tartalmazni.

### <a name="resizing"></a>Átméretezés

Az Excel-sablont úgy is beállíthatja, hogy cellákat használjon a szöveges adatokhoz. Annak érdekében, hogy a cella teljes szövege látható legyen egy generált dokumentumban, be lehet állítani, hogy a cella automatikusan becsomagolja a szöveget a szövegbe. Beállíthatja azt is, hogy a cellát tartalmazó sor automatikusan módosítsa a magasságát, ha a szöveg nem látható teljesen. A további tudnivalókat lásd a "Szöveg csomagolása cellában" [szakasz a cellákban levágott adatok kijavítása című részében](https://support.microsoft.com/office/fix-data-that-is-cut-off-in-cells-e996e213-6514-49d8-b82a-2721cef6144e).

> [!NOTE]
> Az Excel [egy ismert korlátozása miatt még akkor is, ha a cellákat a szöveg csomagolására konfigurálja, és úgy konfigurálja a cellákat tartalmazó sorokat, hogy azok automatikusan módosítják a magasságukat, hogy elférjen a](https://support.microsoft.com/topic/you-cannot-use-the-autofit-feature-for-rows-or-columns-that-contain-merged-cells-in-excel-34b54dd7-9bfc-6c8f-5ee3-2715d7db4353) szövegbe illesztésében, előfordulhat, **hogy az egyesített cellákhoz és az őket tartalmazó sorokhoz nem tudja használni az AutoFit** **és a Csomagoló** szöveg Excel szolgáltatást. 

Dynamics 365 Finance A 10.0.23-as verziótól az ER-t kényszerítheti arra, hogy egy generált dokumentumban kiszámítsa minden olyan sor magasságát, amely úgy volt beállítva, hogy automatikusan elférjen az egymásba ágyazott cellák tartalmához, valahányszor ez a sor legalább egy olyan egyesített cellát tartalmaz, amely úgy van beállítva, hogy a szöveget a fájlba csomagolja. A kiszámított magasság segítségével átméretezheti a sort, hogy a létrehozott dokumentumban a sor minden cellája látható legyen. Ha elkezdi használni ezt a funkciót, amikor bármilyen OLYAN ER-formátumot futtat, amely a kimenő dokumentumok előállításához Excel-sablonokat használt, kövesse ezeket a lépéseket.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.
3. Az Elektronikus jelentés paraméterei lap Futási **idő** lapján állítsa Az Automatikus illesztés **sor magassága beállítást Igen beállításra** **.** **·**

Ha egyetlen ER-formátumban szeretné módosítani ezt a szabályt, a következő lépések szerint frissítse annak vázlatverzióját.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. A **Lokalizációs konfigurációk** oldalon, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.
3. A Konfigurációk **lap** bal oldali konfigurációs fájában válasszon ki egy ER-konfigurációt, amely Egy Excel-sablont használ a kimenő dokumentumok előállítására.
4. A **Verziók** gyorslapon válassza ki azt a konfigurációverziót, amelynek az állapota **Piszkozat**.
5. A Műveleti ablaktáblán kattintson a **Tervező** elemre.
6. A Formátumtervező **lap** bal oldali formátumfában válassza ki azt az Excel-összetevőt, amely Excel-sablonhoz van kapcsolva.
7. **·** **A** Formátum lap Sor magasságának módosítása mezőjében válassza ki azt az értéket, amely meghatározza, hogy futásidőben az ER kötelező legyen-e a sorok magasságának módosítására a szerkesztett ER-formátum által létrehozott kimenő dokumentumban:

    - **Alapértelmezett** – az Elektronikus jelentés paraméterei **oldal Automatikus illesztés** **sor magassága mezőjében beállított általános beállítás** használata.
    - **Igen** – az általános beállítás felülbírálása és a sor magasságának módosítása futásidőben.
    - **Nem** – felülbírálja az általános beállítást, és futásidőben nem módosítja a sor magasságát.

## <a name="cell-component"></a>Cellaösszetevő

A **Cella**-összetevő az Excelben névvel ellátott cellák, alakzatok és képek kitöltéséhez használatos. Ha azt szeretné, hogy egy olyan Excel névvel ellátott objektumot adjon meg, amelyet a **Cella** ER-összetevőnek ki kell töltenie, meg kell adnia az objektum nevét a **Cella** komponens **Excel-tartomány** tulajdonságában.

Az ER műveleti tervező **Leképezés** lapján beállíthatja az **Engedélyezés** tulajdonságot egy **Cella** komponenshez annak meghatározására, hogy az objektumnak kitöltöttnek kell lennie egy generált dokumentumban:

- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Igaz** értéket ad vissza, vagy ha nincs megadva a kifejezés, akkor a rendszer a megfelelő objektummal tölti ki a létrejövő dokumentumot. A **cella** összetevő kötése egy olyan értéket határoz meg, amely a megfelelő tárgyban szerepel.
- Ha az **Engedélyezve** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Hamis** értéket ad vissza, akkor a megfelelő tárgy nem lesz kitöltve a llétrejövő dokumentumban.

Ha egy **Cella**-összetevő úgy van beállítva, hogy a cellában értéket adjon meg, akkor egy olyan adatforrás is köthető, amely egy primitív adattípus értékét (például **Karakterlánc**, **Tényleges** vagy **Egész**) adja eredményül. Ebben az esetben az érték a cellában ugyanolyan típusú értékként szerepel.

Ha egy **Cella**-összetevő úgy van beállítva, hogy egy Excel-alakzatban értéket adjon meg, akkor egy olyan adatforrás is köthető, amely egy primitív adattípus értékét (például **Karakterlánc**, **Tényleges** vagy **Egész**) adja eredményül. Ebben az esetben az érték az Excel-forma megadott érték az alakzat szövegeként szerepel. A nem **Karakterlánc** típusú értékek esetében a program automatikusan átváltja a szöveggé történő konverziót.

> [!NOTE]
> A **Cella**-összetevőt csak akkor lehet kitölteni, ha egy alakzatszöveg tulajdonsága támogatott.

Ha egy **Cella**-összetevő úgy van beállítva, hogy egy Excel-képben értéket adjon meg, akkor egy olyan adatforrás is köthető, amely egy **Tároló** adattípus értékét adja eredményül. Ebben az esetben a program képként írja be az értéket az Excel-képben.

> [!NOTE]
> Minden Excel-kép és -alakzat a bal felső sarkától egy adott Excel-cellához vagy -tartományhoz van rögzítve. Ha Excel-képet vagy -alakzatot szeretne replikálni, konfigurálnia kell azt a cellát vagy tartományt, amelyhez a replikált cella vagy tartomány van rögzítve.

Ha további tájékoztatást szeretne arról, hogyan lehet beágyazni a képeket és az alakzatokat, akkor a következő témakör tartalmaz további tájékoztatást: [Képek és alakzatok beágyazása a létrehozott dokumentumokban](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Oldaltörés-összetevő

A **PageBreak** összetevő az Excelt új lap létrehozására kényszeríti. Ezt az összetevőt nem szükséges használni az Excel alapértelmezett lapozásához, de akkor kell használni, ha azt szeretné, hogy az Excel kövesse a saját formátumát a lapozás felépítéséhez.

## <a name="page-component"></a><a name="page-component"></a>Lapösszetevő

### <a name="overview"></a>Áttekintés

A **Lap** összetevőt akkor használhatja, ha azt szeretné, hogy az Excel kövesse az ER-formátumot és a struktúra lapozását egy generált kimenő dokumentumban. Amikor az ER-formátum futtatja az **Oldal** összetevő alatt található összetevőket, a program automatikusan hozzáadja a szükséges oldaltöréseket. A folyamat során figyelembe kell venni a létrehozott tartalom méretét, az Excel-sablon oldalbeállítását és az Excel-sablonban kiválasztott papírméretet.

Ha egy létrehozott dokumentumot különböző szakaszokra kell felosztani, amelyek mindegyikének más a lapozása, akkor minden [Lap](er-fillable-excel.md#sheet-component) összetevőben konfigurálhat több **Oldal** összetevőt.

### <a name="structure"></a><a name="page-component-structure"></a>Szerkezet

Ha az **Oldal** összetevő alatt az első összetevő egy [Tartomány](er-fillable-excel.md#range-component) összetevő, ahol a **Replikáció iránya** tulajdonság **Nincs replikáció** értékre van állítva, ez a tartomány az aktuális **Oldal** összetevő beállításain alapuló lapfejlécnek számít. Az ehhez a formátumösszetevőhöz társított Excel-tartomány minden olyan lap tetején meg van ismételve, amelyet az aktuális **Oldal** összetevő beállításainak használatával generál a program.

> [!NOTE]
> A helyes oldalakra törés érdekében, ha a [Felsül ismételni kívánt sorok](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409) tartomány van állítva az Excel-sablonban, ennek az Excel-tartománynak a címének meg kell egyeznie a korábban leírt **Tartomány** összetevőhöz társított Excel-tartomány címével.

Ha az **Oldal** összetevő alatt az utolsó összetevő egy **Tartomány** összetevő, ahol a **Replikáció iránya** tulajdonság **Nincs replikáció** értékre van állítva, ez a tartomány az aktuális **Oldal** összetevő beállításain alapuló lapláblécnek számít. Az ehhez a formátumösszetevőhöz társított Excel-tartomány minden olyan lap alján meg van ismételve, amelyet az aktuális **Oldal** összetevő beállításainak használatával generál a program.

> [!NOTE]
> A helyes oldalakra tördelés érdekében a **Tartomány** összetevőihez társított Excel-tartományokat nem szabad futásidőben átméretezni. Nem ajánlott az ilyen tartományba írt cellák formázása a **Szöveg tördelése cellában** és a **Sormagasság automatikus kitöltése** Excel [beállítások](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84) használatával.

A választható **Tartomány** összetevők között több más **Tartomány** összetevőt is hozzáadhat, amelyek meghatározzák a létrehozott dokumentumok kitöltését.

Ha az **Oldal** összetevő alatt egymásba ágyazott **Tartomány** összetevők halmaza nem felel meg a korábban leírt struktúrának, az ER formátumtervező tervezési idejében érvényesítési [hiba](er-components-inspections.md#i17) merül fel. A hibaüzenet arról ad tájékoztatást, hogy a probléma futásidőben problémákat okozhat.

> [!NOTE]
> A helyes kimenet létrehozásához ne adjon meg kötést az **Oldal** összetevő alatt egyetlen **Tartomány** összetevőhöz sem, ha a **Tartomány** összetevő **Replikáció iránya** tulajdonsága **Nincs replikáció**, és a tartomány úgy van beállítva, hogy oldalfejléceket vagy oldallábléceket generáljon.

Ha azt szeretné, hogy a lapszámozással kapcsolatos összegzés és számozás kiszámítsa a laponként a görgetett összegeket és összegeket, javasoljuk, hogy konfigurálja a szükséges [Adatgyűjtés](er-data-collection-data-sources.md) adatforrásokat. Ha meg szeretne ismerkedni az **Oldal** összetevő használatával egy generált Excel-dokumentum oldalakra töréséhez, végezze el az [ER formátum tervezése a létrehozott dokumentum oldalakra töréséhez Excel-formátumban](er-paginate-excel-reports.md).

### <a name="limitations"></a><a name="page-component-limitations"></a>Korlátozások

Ha az **Oldal** összetevőt használja az Excel oldalakra töréséhez, a generált dokumentum végső oldalszámát nem fogja tudni a program, amíg be nem fejeződik az oldalakra tördelés. Ennek megfelelően nem tudja kiszámítani az oldalak összesített számát az ER-képletek használatával, és nem tudja kinyomtatni a létrehozott dokumentumok helyes oldalszámát az utolsó oldal előtti bármelyik oldalra.

> [!TIP]
> Ennek az eredménynek az eléréséhez egy Excel-fejlécben vagy láblécben, használjon különleges Excel [formázást](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) a fejlécekhez és láblécekhez.

Ha egy Excel-sablont a Dynamics 365 Finance 10.0.22-es verzióban szerkeszthető formátumban frissít, akkor a program nem figyelembe venni a konfigurált **Oldal** összetevők használatát. Ez a funkció a Finance további kiadásai során tervezett.

Ha [feltételes formázásra](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting) használatára konfigurálja az Excel-sablont, bizonyos esetekben előfordulhat, hogy az nem a várt módon működik.

### <a name="applicability"></a>Alkalmazhatóság

A **Oldal** összetevő csak akkor működik az [Excel fájl](er-fillable-excel.md#excel-file-component) formátumösszetevővel, ha az összetevő egy Excel-sablonban való használatra van konfigurálva. Ha az Excel-sablont Word-sablonra [cseréli](tasks/er-design-configuration-word-2016-11.md), és futtatja a szerkeszthető ER-formátumot, a rendszer figyelmen kívül hagyja az **Oldal** összetevőt.

Az **Oldal** összetevő csak akkor működik, ha engedélyezve van az **EPPlus könyvtár használatának engedélyezése az elektronikus jelentési keretrendszerben** funkció. Futásidőben kivétel történik amikor az ER megpróbálja feldolgozni az **Oldal** összetevőt, miközben ez a funkció le van tiltva.

> [!NOTE]
> Kivétel merül fel futásidőben, ha az ER-formátum feldolgozza egy olyan Excel-sablon **Oldal** összetevőjét, amely legalább egy érvénytelen cellára hivatkozik. A futásidejű hibák elkerülése érdekében javítsa ki az Excel-sablont a következőben leírtak szerint: [Hogyan javítható ki a #HIV! hiba](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be).

## <a name="footer-component"></a>Lábléc összetevő

A **Lábléc** összetevő segítségével kitölthető a lábléc egy Excel-munkafüzetben létrehozott munkalap alján.

> [!NOTE]
> Ezt az összetevőt minden **Lap** összetevő számára hozzáadhatja, hogy különböző lábléceket adjon meg a létrehozott Excel-munkafüzetek különböző munkalapjaihoz.

Ha egy egyedi **Lábléc** összetevőt konfigurál, akkor a **Fejléc/lábléc megjelenése** tulajdonsággal meghatározhatja, hogy az összetevő mely lapokhoz használható. A következő értékek állnak rendelkezésre:

- **Bármelyik** – a konfigurált **Lábléc** összetevő futtatása a szülő Excel-munkalap bármelyik lapjára vonatkozóan.
- **Első** – a konfigurált **Lábléc** összetevő futtatása a szülő Excel-munkalap kizárólag első lapjára vonatkozóan.
- **Páros** – a konfigurált **Lábléc** összetevő futtatása a szülő Excel-munkalap kizárólag páros lapjaira vonatkozóan.
- **Páratlan** – a konfigurált **Lábléc** összetevő futtatása a szülő Excel-munkalap kizárólag páratlan lapjaira vonatkozóan.

Egyetlen **Lap** összetevőhöz több **Lábléc** összetevőt is hozzáadhat, amelyek mindegyikének más az értéke a **Fejléc/lábléc megjelenése** tulajdonságban. Ily módon különböző lábléceket lehet létrehozni az Excel-munkalap különböző típusú lapjaihoz.

> [!NOTE]
> Győződjön meg arról, hogy az egyes **Lap** összetevőkhöz hozzáadott **Lábléc** összetevőnek más értéke legyen a **Fejléc/lábléc megjelenése** tulajdonságban. Ellenkező esetben [ellenőrzési hiba](er-components-inspections.md#i16) lép fel. A kapott hibaüzenet az inkonzisztenciáról tájékoztatja.

A hozzáadott **Lábléc** összetevőnél adja hozzá a **Szöveg\\Sztring**, **Szöveg\\DátumIdő** vagy egyéb típusú beágyazott összetevőit. Konfigurálja ezen összetevők kötését a lábléc kitöltési módjának beállítására.

Speciális [formázási kódokat](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) is használhat a létrehozott lábléc tartalmának megfelelő formázása érdekében. A megközelítés használatának elsajátításához kövesse a témakör [1. példájában](#example-1) leírt lépéseket.

> [!NOTE]
> Az ER-formátumok konfigurálásakor figyelembe kell venni az Excel-[korlátot](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3) és az egyes fejlécek és láblécek maximális karakterszámát.

## <a name="header-component"></a>Fejléc összetevő

A **Fejléc** összetevő segítségével kitölthető a fejléc egy Excel-munkafüzetben létrehozott munkalap tetején. Használata megegyezik a **Lábléc** összetevőével.

## <a name="edit-an-added-er-format"></a>Hozzáadott ER-formátum szerkesztése

### <a name="update-a-template"></a>Sablon frissítése

Kiválaszthatja az **Frissítés Excelből** lehetőséget a Műveleti panel **Importálás** lapfülén, ha egy frissített sablont egy szerkeszthető ER-formátumba importál. A folyamat során a kiválasztott **Excel\\fájl** komponens egy sablonját a program felülírja egy új sablonnal. A szerkeszthetővé tett ER-formátum tartalmát a program szinkronizálja a frissített ER-sablon tartalmával.

- Minden Excel-névhez automatikusan létrejön egy új ER-formátum-összetevő, ha az ER-formátum összetevője nem található a szerkeszthető formában.
- Ha nem találja meg a megfelelő Excel-nevet, akkor minden ER-formátum-összetevő törlődik a szerkeszthető ER-formátumból.

> [!NOTE]
> Állítsa az **Excel lapformátum elem létrehozása** lehetőséget **Igen** értékűre, ha létre szeretné hozni az opcionális **Lap** elemet szerkeszthető ER-formában.
>
> Ha a szerkeszthetővé teszi az ER-formátumot eredetileg tartalmazó **Lap** elemeit, akkor javasolt az **Excel lapformátum elem létrehozása** beállítás **Igen** értékre állítása a frissített sablonok importálásakor. Ellenkező esetben a program az eredeti **Lap** elemének minden beágyazott elemét a semmiből hozza létre. Ennek megfelelően az újra létrehozott formátumú elemek összes kötése elvész a frissített ER-formátumban.

![Az Excel lapformátum létrehozása elemopció a Frissítés az Excel programból párbeszédpanelen.](./media/er-excel-format-update-template.png)

Ha további tájékoztatást szeretne erről a funkcióról, kövesse az [Elektronikus jelentéskészítési formátumok módosítása az Excel-sablonok újraalkalmazásával](modify-electronic-reporting-format-reapply-excel-template.md) dokumentum lépéseit.

## <a name="validate-an-er-format"></a>ER-formátum érvényesítése

Ha érvényesít egy módosítható ER-formátumot, akkor következetesség-ellenőrzéssel győződjön meg arról, hogy a jelenleg használt Excel-sablonban szerepel az Excel-név. A program értesíti a következetlenségekről. Bizonyos következetlenségek esetén a program felajánlja a problémák automatikus javítását.

![Ellenőrzési hibaüzenet.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Excel-képletek számításának ellenőrzése

Az Microsoft Excel munkafüzet formátumú kimenő dokumentumok létrehozásakor előfordulhat, hogy a dokumentum egyes cellái Excel-képleteket tartalmaznak. Ha az **EPPlus könyvtár használatának engedélyezése az elektronikus jelentési keretrendszerben** funkció engedélyezve van, akkor a képletek kiszámítását szabályozhatja, ha módosítja **Számítási beállítások** [paraméter](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) értékét a használt Excel-sablonban:

- Válassza az **Automatikus** lehetőséget az összes függő képlet újraszámításához minden olyan alkalommal, amikor a létrejövő dokumentumhoz új tartományokat, cellákat stb. fűznek hozzá.

    > [!NOTE]
    > Ennek hatására előfordulhat, hogy a több kapcsolódó képletet tartalmazó Excel sablonok teljesítménye romlik.

- A dokumentum létrehozásakor a képlet újraszámításának elkerüléséhez válassza a **Manuális** lehetőséget.

    > [!NOTE]
    > A képlet-újraszámítást kézzel kell végrehajtani, amikor a generált dokumentumot előnézetre megnyitják az Excel alkalmazással.
    > Ne használja ezt a lehetőséget, ha olyan ER-célt állított be, amely az Excel előnézete nélkül (PDF-átalakítás, e-mailek stb.) a létrejövő dokumentumok használatát feltételezi, mivel előfordulhat, hogy a létrejövő dokumentum nem tartalmaz értékeket a képleteket tartalmazó cellákban.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>1. példa: Lábléc tartalmának formázása

1. A megadott ER-konfigurációk segítségével nyomtatható szabadszöveges számlát (FTI) [generálhat](er-generate-printable-fti-forms.md).
2. Ellenőrizze a létrehozott dokumentum láblécét. A dokumentum az aktuális oldalszámmal és a dokumentumok összesített oldalszámával kapcsolatos információkat tartalmaz.

    ![Excel-formátumban létrehozott dokumentum láblécének felülvizsgálata.](./media/er-fillable-excel-footer-1.gif)

3. Az ER-formátumtervezőben [nyissa meg](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) felülvizsgálatra az ER mintaformátumot.

    A **Számla** munkalap láblécét a program a **Lábléc** összetevő alatt található két **Sztring** típusú összetevő beállításai alapján generálja.

    - Az első **Sztring** összetevő beírja a következő speciális formázási kódokat, hogy az Excel alkalmazást az adott formátum alkalmazására kényszerítse:

        - **&C** – a lábléc szövegének középre igazítása.
        - **&"Segoe UI,Regular"&8** – a lábléc szövegének the "Segoe UI Regular" betűtípusban, 8 pontos méretben való megjelenítése.

    - A második **Sztring** összetevő kitölti az aktuális oldalszámot és az aktuális dokumentum összesített oldalszámát tartalmazó szöveget.

    ![A Lábléc ER-formátum-összetevő felülvizsgálata a Formátumtervező lapon.](./media/er-fillable-excel-footer-2.png)

4. Az ER-mintaformátum testreszabása az aktuális lábléc módosításához:

    1. [Hozzon létre](er-quick-start2-customize-report.md#DeriveProvidedFormat) egy származtatott **Szabadszöveges számla (Excel) egyedi** ER-formátumot, amely az ER mintaformátumon alapul.
    2. Adja hozzá az első új **String** összetevőpárost a **Lábléc** összetevőhöz a **Számla** munkalapon:

        1. Adjon hozzá egy **Sztring** összetevőt, amely a vállalat nevét balra igazítja, és 8 pontos "Segoe UI Regular" betűtípussal (**"&L&"Segoe UI,Regular"&8"**) jeleníti meg.
        2. Adja hozzá a vállalat nevét beíró **Sztring** összetevőt (**model.InvoiceBase.CompanyInfo.Name**).

    3. Adja hozzá a második új **String** összetevőpárost a **Lábléc** összetevőhöz a **Számla** munkalapon:

        1. Adjon hozzá egy **Sztring** összetevőt, amely a jobbra igazítja a feldolgozási dátumot, és 8 pontos "Segoe UI Regular" betűtípussal (**"&R&"Segoe UI,Regular"&8"**) jeleníti meg.
        2. Adjon hozzá egy **Sztring** összetevőt, amely egyéni formátumban tölti ki a feldolgozási dátumot (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**).

        ![A Lábléc ER-formátum-összetevő felülvizsgálata a Formátumtervező lapon.](./media/er-fillable-excel-footer-3.png)

    4. [Töltse ki](er-quick-start2-customize-report.md#CompleteDerivedFormat) a származtatott **Szabadszöveges számla (Excel) egyéni** ER-formátum vázlatverzióját.

5. [Konfigurálja](er-generate-printable-fti-forms.md#configure-print-management) a Nyomtatáskezelés lehetőséget a származtatott **Szabadszöveges számla (Excel) egyéni** ER-formátum használatával az ER-mintaformátum helyett.
6. Hozzon létre egy nyomtatható FTI-dokumentumot, és vizsgálja felül a létrehozott dokumentum láblécét.

    ![Excel-formátumban létrehozott dokumentum láblécének felülvizsgálata.](./media/er-fillable-excel-footer-4.gif)

## <a name="example-2-fixing-the-merged-cells-epplus-issue"></a><a name="example-2"></a> 2. példa: Az egyesített cellák EPGra kiadásának kijavítása

Az ER-formátum futtatásával Egy kimenő dokumentumot Excel-munkafüzet-formátumban generálhat. Ha az **Elektronikus jelentési keretrendszer EPGra** **tárhasználatának** engedélyezése a Szolgáltatáskezelési munkaterületen engedélyezve van, [akkor az EPGra](https://www.nuget.org/packages/epplus/4.5.2.1) függvénytár az Excel kimenetének létrehozásához használható. Az Ismert [Excel-viselkedés](https://answers.microsoft.com/msoffice/forum/all/deleting-a-range-of-cells-that-includes-merged/8601462c-4e2c-48e0-bd23-848eecb872a9) és az EPGra függvénytár korlátozása miatt azonban a következő kivétel előfordulhat: "Egyesített cellákat nem lehet törölni/felülírni. Egy tartományt részben egyesít a másik egyesített tartománysal." A következő példában olvashatja, hogy milyen Excel-sablonok okozhatják ezt a kivételt, és hogyan javíthatja ki a problémát.

1. Hozzon létre egy új Excel-munkafüzetet az Excel asztali alkalmazásban.
2. A munkalap **1.** munkalapján adja hozzá **a ReportTitle nevét** az A2 **cellhoz**.
3. Az A1 **és** az A2 cellák **egyesítése**

    ![Az A1 és az A2 celláknak az Excel asztali alkalmazásban tervezett Excel-munkafüzetben való összefésülésének áttekintése.](./media/er-fillable-excel-example2-1.png)

3. A Konfigurációk **lapon** adjon [hozzá egy új ER-formátumot](er-fillable-excel.md#add-a-new-er-format), hogy egy Excel-munkafüzet formátumú kimenő dokumentumot generáljon.
4. A Formátumtervező **lapon** importálja [a](er-fillable-excel.md#template-import) tervezett Excel-munkafüzetet a hozzáadott ER-formátumba, mint a kimenő dokumentumok új sablonját.
5. A Leképezés **lapon** állítsa be a cell típusú **ReportTitle** összetevő [kötését](er-fillable-excel.md#cell-component).
6. A konfigurált ER-formátum futtatása. A következő kivétel történt: "Egyesített cellákat nem lehet törölni/felülírni. Egy tartományt részben egyesít a másik egyesített tartománysal."

    ![A konfigurált ER-formátum futtatásának eredményeinek áttekintése a Formátumtervező lapon.](./media/er-fillable-excel-example2-2.png)

A probléma a következőképpen javítható ki:

- **Egyszerűbb, de nem ajánlott:** A **·** **Szolgáltatáskezelés munkaterületen kapcsolja ki az EPGra függvénytár használatának engedélyezése az elektronikus jelentési keretrendszerben** funkciót. Bár ez a megközelítés egyszerűbb, használata esetén más problémákat is tapasztalhat, mivel az ER **egyes funkcióit csak akkor támogatja a rendszer, ha engedélyezve van az ELEKTRONIKUS jelentési keretrendszer EPGra** tárhasználatának engedélyezése.
- **Ajánlott:** Kövesse a következő lépéseket:

    1. Az Excel asztali alkalmazásban a következőképpen módosíthatja az Excel-munkafüzetet:

        - Az A1 **és** az A2 cella egyesítésének **az 1**. munkalapon **·**
        - Módosítsa a **ReportTitle** név hivatkozását a következőről: **=Sheet1!$A$2** to **=Sheet1!$A$1**.

        ![Az Excel asztali alkalmazásban tervezett Excel-munkafüzetben a hivatkozás módosításának eredményeiről áttekintést ad.](./media/er-fillable-excel-example2-3.png)

    2. A Formátumtervező **lapon** importálja [a](er-fillable-excel.md#template-import) módosított Excel-munkafüzetet a szerkeszthető ER-formátumba, hogy frissítse a meglévő sablont.
    3. A módosított ER-formátum futtatása.

        ![A létrehozott dokumentum áttekintése az Excel asztali alkalmazásban.](./media/er-fillable-excel-example2-4.png)

## <a name="limitations"></a>Korlátozások

### <a name="known-epplus-library-limitations"></a>Az EPGra tár ismert korlátai

#### <a name="external-data-sources"></a>Külső adatforrások

Ha valamelyik sablon olyan kimutatást tartalmaz, amely egy külső adatforrásra hivatkozó modellen alapul, PowerPivot és engedélyezve van az EPGra [tár használatának engedélyezése az elektronikus jelentési keretrendszerben funkció, akkor a következő hibaüzenet jelenik meg, amikor olyan ER-formátumot futtat, amely ezt a](https://support.microsoft.com/office/create-a-pivottable-with-an-external-data-source-db50d01d-2e1c-43bd-bfb5-b76a818a927b)**sablont** használja kimenő dokumentum Excel formátumú előállítására: "A gyorsítótárforrás nem munkalap." A probléma megoldásához a következő lehetőségek állnak rendelkezésre:

- **Ajánlott:** Tervezd újra a használt Excel-megoldást:

    1. Tássa ki a kimutatásokat tartalmazó részt egy különálló Excel-munkafüzetben (A munkafüzet). 
    2. Az ER segítségével elő lehet hozni egy másik Excel-munkafüzetet (B-munkafüzetet) a Pénzügyben, amely tartalmazza a szükséges adatokat. 
    3. A B munkafüzet generálása után nézze meg a B munkafüzetet.

- A funkció kikapcsolása: **Az EPGra tár használatának engedélyezése az elektronikus** jelentési keretrendszerben az EPGra beállítástól különböző beállítás használatához. 

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése](tasks\er-design-reports-openxml-2016-11.md)

[Elektronikus jelentések formátumának módosítása Excel-sablonok újbóli alkalmazásával](modify-electronic-reporting-format-reapply-excel-template.md)

[Vízszintesen bővíthető tartományok használata oszlopok Excel-jelentésekbe történő dinamikus hozzáadásához](tasks/er-horizontal-1.md)

[Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)

[Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI-be való lehívásához](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
