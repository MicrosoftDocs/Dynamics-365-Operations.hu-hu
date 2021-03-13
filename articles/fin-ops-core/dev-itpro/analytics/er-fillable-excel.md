---
title: Tervezzen konfigurációkat a kimenő dokumentumok Excel-formátumban történő létrehozásához
description: Ez a témakör azt mutatja be, hogyan lehet az Elektronikus jelentéskészítés (ER) formátumát egy Excel-sablon kitöltéséhez tervezni, majd a kimenő Excel-formátumú dokumentumokat generálni.
author: NickSelin
manager: AnnBe
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: c8d6a18741d57829d1929fb8362dc4ba8e03a1bd
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094029"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>(ER) Az Excel formátumban létrejövő dokumentumokra vonatkozó konfigurációk tervezése

[!include[banner](../includes/banner.md)]

Tervezhet egy [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) formátumú konfiguráció, aminek olyan ER [formátumkomponense](general-electronic-reporting.md#FormatComponentOutbound) van, amit a kimenő dokumentumok Microsoft Excel munkafüzet-formátumban való konfigurálására használhat. Erre a célra külön ER formátumú komponenseket kell használni.

Ha további tájékoztatást szeretne erről a funkcióról, kövesse a [Jelentések készítésének konfigurációja OPENXML formátumban](tasks/er-design-reports-openxml-2016-11.md) témakör lépéseit.

## <a name="add-a-new-er-format"></a>Új ER-formátum hozzáadása

Amikor egy új ER formátumú konfigurációt hoz létre egy kimenő dokumentum Excel-munkafüzet-formátumban történő generálásához, vagy ki kell választania a **Excel** értéket a **Formátumtípus** attribútumához vagy hagyja a **formátumtípus** attribútumot ütesen.

- Ha az **Excelt** választja, akkor a formátumot csak Excel formátumú kimenő dokumentumok generálásához állíthatja be.
- Ha üresen hagyja az attribútumot, konfigurálhatja azt a formátumot, amellyel a kimenő dokumentumok bármilyen formában elkészíthetők.

A konfiguráció ER formátumkomponensének konfigurálásához válassza **Tervező** lehetőséget a művelet panelen, majd nyissa meg az ER-formátumkomponenst az ER operációs tevezőben.

![Konfigurációk oldala](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Excelfájl-komponens

### <a name="manual-entry"></a>Manuális bejegyzés

Ahhoz, hogy a kimenő dokumentumokat Excel-formátumban hozza létre, egy **Excel\\fájl** komponenst kell hozzáadnia a konfigurált ER-formátumhoz.

![Excel\fájl-komponens](./media/er-excel-format-add-file-component.png)

A kimenő dokumentumok elrendezésének megadásához csatolnia kell egy olyan Excel-munkafüzetet, amelynek .xlsx kiterjesztéssel rendelkezik az **Excel\\fájlt** tartalmazó komponense, mint a kimenő dokumentumok sablonja.

> [!NOTE]
> A sablon manuális csatolása esetén olyan [dokumentumtípust](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) dokumentumtípust kell használnia, amely az adott célra be van állítva az [ER paramétereiben](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Melléklet hozzáadása a Excel\fál-komponenshez](./media/er-excel-format-add-file-component2.png)

Ha meg szeretné adni, hogy a rendszer hogyan töltse ki a csatolt sablont a konfigurált ER-formátum futtatásakor, akkor hozzá kell adnia a beágyazott **Lapok**, **Tartomány** és **Cella** komponenseket az **Excel\\fájl** komponenshez. Minden beágyazott komponenshez társítani kell egy elem elnevezésű Excelt.

### <a name="template-import"></a>Sablon importálása

Kiválaszthatja az **Importálás Excelből** lehetőséget a Műveleti panel **Importálás** lapfülén, ha egy új sablont üres ER-formátumba importál. Ebben a példában a program automatikusan létrehoz egy **Excel\\fájl** komponenst, és az importált sablont hozzárendeli a program. A program az összes szükséges ER-komponenst automatikusan létrehozza a felismert Excel nevű tételek listájának alapján.

![Az Importálás az Excelből lehetőség kiválasztása](./media/er-excel-format-import-template.png)

> [!NOTE]
> Ha létre szeretné hozni az opcionális **Lap** elemet szerkeszthető ER-formában, akkor állítsa az **Excel lapformátum elem létrehozása** lehetőséget **Igen** értékűre.

## <a name="sheet-component"></a>Lapkomponens

A **Lap** komponens azt jelzi, hogy a csatolt Excel-munkafüzet munkalapját ki kell tölteni. A munkalap Excel-sablonban megadott név a **Lap** komponens tulajdonságában van meghatározva.

> [!NOTE]
> Ez a komponens nem kötelező olyan Excel-munkafüzetekhez, amelyek egyetlen munkalapot tartalmaznak.

Az ER műveleti tervező **Leképezés** lapján beállíthatja az **Engedélyezés** tulajdonságot egy **Lap** komponenshez annak meghatározására, hogy a komponenst egy generált dokumentumban kell-e elhelyezni:

- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Igaz** értéket ad vissza, vagy ha nincs megadva a kifejezés, akkor a rendszer a megfelelő munkalapot helyezi a létrejövő dokumentumba.
- Ha az **Engedélyezve** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Hamis** értéket ad vissza, akkor a létrejövő dokumentum nem tartalmaz munkalapot.

![Példa a lap komponensére](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Tartomány-összetevő

A **Tartomány**-összetevő egy olyan Excel-tartományt jelöl, amelyet ennek az ER-komponensnek kell vezérelni. Az **Excel-tartományban** megadott kiterjedés neve a komponens tulajdonságában van meghatározva.

A **Replikációs irány** tulajdonság határozza meg, hogy a rendszer hogyan fogja megismételni a tartományt a létrejövő dokumentumban:

- Ha a **Replikációs irány** tulajdonsága **Nem replikálásra** van állítva, akkor a megfelelő Excel-tartomány nem fog megismétlődni a létrejövő dokumentumban.
- Ha a **Replikációs irány** tulajdonsága **Függőleges** értékre van állítva, akkor a megfelelő Excel-tartomány nem fog megismétlődni a létrejövő dokumentumban. Minden replikált tartomány egy Excel-sablonban az eredeti tartomány alá kerül. Az ismétlések számát a **Rögzítési lista** típus adatforrásainak rögzítéseinek számának meghatározása határozza meg, amely az típusú ER-komponenshez kötődik.
- Ha a **Replikációs irány** tulajdonsága **Vízszintes** értékre van állítva, akkor a megfelelő Excel-tartomány nem fog megismétlődni a létrejövő dokumentumban. Minden replikált tartomány egy Excel-sablonban az eredeti tartomány jobb oldalára kerül. Az ismétlések számát a **Rögzítési lista** típus adatforrásainak rögzítéseinek számának meghatározása határozza meg, amely az típusú ER-komponenshez kötődik.

Ha további tájékoztatást szeretne a vízszintes replikálásról, hajtsa végre a [Vízszintesen kibontható tartományok az Excel-jelentések oszlopainak dinamikus hozzáadásához](tasks/er-horizontal-1.md) dokumentum lépéseit.

A **Tartomány**-összetevő más beágyazott ER-összetevőkkel is rendelkezhet, amelyek a megfelelő Excel-tartományokban szereplő értékek megadására szolgálnak.

- Ha a **Szöveges** csoport bármely összetevője az értékek megadására szolgál, akkor az érték egy Excel-tartományban jelenik meg szöveges értékként.

    > [!NOTE]
    > Ez a minta a megadott értékek formátumára használható a pályázatban megadott területi beállítás alapján.

- Ha a **Cella** komponens az **Excel**-csoportban értékek megadására szolgál, akkor az Excel-tartományban megadott érték a **Cella** összetevő (például **Karakterlánc**, **Tényleges** vagy **Egész**) kötése által meghatározott adattípus.

    > [!NOTE]
    > Ennek a mintának a használatával engedélyezheti az Excel-alkalmazás számára a megadott értékek formátumát a kimenő dokumentumot megnyitó helyi számítógép területi beállításai alapján.

Az ER műveleti tervező **Leképezés** lapján beállíthatja az **Engedélyezés** tulajdonságot egy **Tartomány** komponenshez annak meghatározására, hogy a komponenst egy generált dokumentumban kell-e elhelyezni:

- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Igaz** értéket ad vissza, vagy ha nincs megadva a kifejezés, akkor a rendszer a megfelelő tartománnyal tölti ki a létrejövő dokumentumot.
- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Hamis** értéket ad vissza, és ez a tartomány nem az összes sort vagy oszlopot reprezentálja, akkor a rendszer a megfelelő tartománnyal tölti ki a létrejövő dokumentumot.
- Ha az **Engedélyezés** tulajdonság kifejezése úgy van beállítva, hogy futás közben **Hamis** értéket ad vissza, és ez a tartomány az összes sort vagy oszlopot reprezentálja, akkor a létrejövő dokumentum ezeket a sorokat és oszlopokat rejtett sorokként és oszlopokként fogja tartalmazni.

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

## <a name="edit-an-added-er-format"></a>Hozzáadott ER-formátum szerkesztése

### <a name="update-a-template"></a>Sablon frissítése

Kiválaszthatja az **Frissítés Excelből** lehetőséget a Műveleti panel **Importálás** lapfülén, ha egy frissített sablont egy szerkeszthető ER-formátumba importál. A folyamat során a kiválasztott **Excel\\fájl** komponens egy sablonját a program felülírja egy új sablonnal. A szerkeszthetővé tett ER-formátum tartalmát a program szinkronizálja a frissített ER-sablon tartalmával.

- Minden Excel-névhez automatikusan létrejön egy új ER-formátum-összetevő, ha az ER-formátum összetevője nem található a szerkeszthető formában.
- Ha nem találja meg a megfelelő Excel-nevet, akkor minden ER-formátum-összetevő törlődik a szerkeszthető ER-formátumból.

> [!NOTE]
> Állítsa az **Excel lapformátum elem létrehozása** lehetőséget **Igen** értékűre, ha létre szeretné hozni az opcionális **Lap** elemet szerkeszthető ER-formában.
>
> Ha a szerkeszthetővé teszi az ER-formátumot eredetileg tartalmazó **Lap** elemeit, akkor javasolt az **Excel lapformátum elem létrehozása** beállítás **Igen** értékre állítása a frissített sablonok importálásakor. Ellenkező esetben a program az eredeti **Lap** elemének minden beágyazott elemét a semmiből hozza létre. Ennek megfelelően az újra létrehozott formátumú elemek összes kötése elvész a frissített ER-formátumban.

![Az Excel lapformátum létrehozása elemopció az Excel párbeszédpanel frissítésében](./media/er-excel-format-update-template.png)

Ha további tájékoztatást szeretne erről a funkcióról, kövesse az [Elektronikus jelentéskészítési formátumok módosítása az Excel-sablonok újraalkalmazásával](modify-electronic-reporting-format-reapply-excel-template.md) dokumentum lépéseit.

## <a name="validate-an-er-format"></a>ER-formátum érvényesítése

Ha érvényesít egy módosítható ER-formátumot, akkor következetesség-ellenőrzéssel győződjön meg arról, hogy a jelenleg használt Excel-sablonban szerepel az Excel-név. A program értesíti a következetlenségekről. Bizonyos következetlenségek esetén a program felajánlja a problémák automatikus javítását.

![Ellenőrzési hibaüzenet](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Excel-képletek számításának ellenőrzése

Az Microsoft Excel munkafüzet formátumú kimenő dokumentumok létrehozásakor előfordulhat, hogy a dokumentum egyes cellái Excel-képleteket tartalmaznak. Ha az **EPPlus könyvtár használatának engedélyezése az elektronikus jelentési keretrendszerben** funkció engedélyezve van, akkor a képletek kiszámítását szabályozhatja, ha módosítja **Számítási beállítások** [paraméter](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) értékét a használt Excel-sablonban:

- Válassza az **Automatikus** lehetőséget az összes függő képlet újraszámításához minden olyan alkalommal, amikor a létrejövő dokumentumhoz új tartományokat, cellákat stb. fűznek hozzá.
    >[!NOTE]
    > Ennek hatására előfordulhat, hogy a több kapcsolódó képletet tartalmazó Excel sablonok teljesítménye romlik.
- A dokumentum létrehozásakor a képlet újraszámításának elkerüléséhez válassza a **Manuális** lehetőséget.
    >[!NOTE]
    > A képlet-újraszámítást kézzel kell végrehajtani, amikor a generált dokumentumot előnézetre megnyitják az Excel alkalmazással.
    > Ne használja ezt a lehetőséget, ha olyan ER-célt állított be, amely az Excel előnézete nélkül (PDF-átalakítás, e-mailek stb.) a létrejövő dokumentumok használatát feltételezi, mivel előfordulhat, hogy a létrejövő dokumentum nem tartalmaz értékeket a képleteket tartalmazó cellákban.

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése](tasks\er-design-reports-openxml-2016-11.md)

[Elektronikus jelentések formátumának módosítása Excel-sablonok újbóli alkalmazásával](modify-electronic-reporting-format-reapply-excel-template.md)

[Vízszintesen bővíthető tartományok használata oszlopok Excel-jelentésekbe történő dinamikus hozzáadásához](tasks/er-horizontal-1.md)

[Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)

[Elektronikus jelentéskészítés (ER) konfigurálása az adatok Power BI-be való lehívásához](general-electronic-reporting-report-configuration-get-data-powerbi.md)
