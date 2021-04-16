---
title: Word tartalmi vezérlőelemek figyelmen kívül hagyása a létrehozott jelentésekben
description: Ez a témakör bemutatja, hogyan kell konfigurálni egy elektronikus jelentéskészítési (ER) formátumot úgy, hogy az a jelentéseket olyan Microsoft Word formátumú fájlokként generálja, amelyekben a tartalomvezérlők el vannak rejtve.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 8c99203110cfdc7f8123c30488611d55f48e8f67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753601"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>Word tartalmi vezérlőelemek figyelmen kívül hagyása a létrehozott jelentésekben

[!include [banner](../includes/banner.md)]

Ahhoz, hogy Microsoft Word-dokumentumként hozzon létre jelentéseket, meg kell terveznie egy sablont Word-dokumentumként a jelentésekhez. Ennek a sablonnak Word-tartalomvezérlőket kell tartalmaznia helyőrzőkként a futásidőben kitöltendő adatokhoz. Ha a létrehozott Word-dokumentumot szeretné használni a jelentések sablonjaként, egy új [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) [megoldást](er-quick-start1-new-solution.md) is [konfigurálhat](er-design-configuration-word.md). A megoldásnak egy ER [konfigurációt](general-electronic-reporting.md#Configuration) kell tartalmaznia egy ER [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevővel. Ezt az ER-formátumot úgy kell konfigurálnia, hogy a jelentés generálásához a meghatározott sablont használja.

A Dynamics 365 Finance 10.0.6-os és újabb verzióiban konfigurálhatja az ER-formátumban található képleteket annak érdekében, hogy mellőzzön néhány Word-tartalomvezérlőt a létrehozott dokumentumokban.

A következő lépések bemutatják, hogy a Rendszergazdához vagy az Elektronikus jelentések funkcióival foglalkozó konzulenshez rendelt felhasználó hogyan konfigurálhatja az ER-formátumot, amely Word-fájlként generálja a jelentéseket, és elnyomja a létrehozott jelentésekben lévő, a Word-sablon használatával konfigurált tartalomvezérlőket.

Ezeket a lépéseket a GBSI vállalatban hajthatja végre.

## <a name="prerequisites"></a>Előfeltételek

A lépések végrehajtásához először hajtsa végre a következő feladat-útmutatókban található lépéseket:

- [Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése](./tasks/er-design-reports-openxml-2016-11.md)
- [ER-konfigurációk újrafelhasználása Excel-sablonok segítségével Word formátumú jelentések generálásához](./tasks/er-design-configuration-word-2016-11.md)

A feladat-útmutatókban található lépések végrehajtása után létrejönnek a következő fájlok:

- Egy **minta munkalap jelentés** ER-formátum, amely a dokumentumok Word formátumú előállítására van konfigurálva
- A **minta munkalap jelentés** ER-formátumának [piszkozat](general-electronic-reporting.md#component-versioning) verziója, amely **futtathatóként** van megjelölve
- A kifizetések **elektronikus** módszere, amely a szállítói kifizetések feldolgozásához a **minta munkalap jelentés** ER-formátumának használatára van konfigurálva

Le kell tölteni és menteni a következő sablont is a mintajelentéshez:

- [Kifizetési jelentés bekötött sablonja 2 (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>A letöltött Word-sablon áttekintése

1. Az asztali Word-alkalmazásban nyissa meg a korábban letöltött **SampleVendPaymDocReportBounded2.docx** sablonfájlt.
2. Ellenőrizze, hogy a sablonfájl tartalmaz-e egy összegző szakaszt, amely megjeleníti a feldolgozott kifizetésekben teljesült összes pénznemkód esetében a teljes kifizetések összegét.

    - Az összegző szakasz a Word-dokumentum egy külön táblájában található.
    - A tábla első sorában a tábla oszlopfejlécei láthatók szakaszfejlécként.
    - A tábla második sorában az ismétlődő tartalomellenőrző található a szakasz részleteiként.
    - Ez a tartalomvezérlő a **Jelentés** egyéni XML-rész **Összefoglaló sorok** mezőjéhez van hozzárendelve.
    - A leképezés alapján a tartalomvezérlő a szerkeszthető ER-formátum **Összefoglaló sorok** eleméhez van társítva.

    > [!NOTE]
    > Az ismétlődő tartalomvezérlőt az **Összefoglaló sorok** kulcs címkézi, amely megfelel annak az egyéni XML-rész mezőjének, amelyben lekérdezték.

    ![Word-sablon elrendezés](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>Válassza ki a meglévő ER-jelentéskonfigurációt

A következő lépésekben újra használja majd a meglévő ER-konfigurációt, amelyet a korábban említett feladat-útmutatók lépéseinek végrehajtása során konfigurált.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A **Konfigurációk** oldalon, a konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **Minta munkalap jelentés** lehetőséget.
4. Válassza a **Tervező** lehetőséget, ha szerkeszteni szeretné a kiválasztott ER-formátum piszkozatverzióját.

## <a name="replace-the-current-template-with-the-new-template"></a>Cserélje ki a jelenlegi sablont az új sablonra

Jelenleg a SampleVendPaymDocReportBounded.docx fájl használatos sablonként a kimenet Word-formátumú előállításához. A következő lépésekben ezt a Word-sablont cserélje le a korábban letöltött SampleVendPaymDocReportBounded2.docx nevű új Word-sablonra.

1. A **Formátumtervező** oldalon válassza a **Mellékletek** elemet.
2. A meglévő sablon eltávolításához válassza a **Törlés** lehetőséget a **Mellékletek** lapon.
3. A törlés jóváhagyásához válassza az **Igen** lehetőséget.
4. Válassza az **Új** \> **Fájl** lehetőséget.
5. Válassza a **Tallózás** lehetőséget, majd tallózással keresse meg és válassza ki a korábban letöltött **SampleVendPaymDocReportBounded2.docx** fájlt.
6. Válassza ki az **OK** lehetőséget.
7. Zárja be a **Mellékletek** lapot.
8. A **Formátumtervező** lap **Sablon** mezőjében adja meg vagy válassza ki a **SampleVendPaymDocReportBounded2.docx** fájlt.

## <a name="run-the-format-to-create-word-output"></a>Formátum futtatása Word-kimenet létrehozásához

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Fizetési napló** pontra.
2. A **Szállítói kifizetések** lapon, a **Lista** lapfülön jelölje ki az összes kifizetést.
3. Válassza ki a **Fizetési állapot** \> **Nincs** lehetőséget.
4. **Kifizetések létrehozása** kiválasztása.
5. A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.
6. A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.
7. Válassza ki az **OK** lehetőséget.
8. Az **Elektronikus jelentés paraméterei** párbeszédablakban kattintson az **OK** gombra, és elemezze a létrehozott kimenetet.

    ![A feldolgozandó kifizetések hozzáadva a Szállítói fizetések lapon](./media/er-design-configuration-word-suppress-controls-image2.gif)

    A kimenet Word-formátumban tekinthető meg, és tartalmazza az összegző szakaszt.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>A szerkeszthető formátum konfigurálása az összegző szakasz elrejtésére

Ha az ER-formátumot futtató felhasználó kérése alapján el szeretné rejteni az összesítő szakaszt egy létrehozott dokumentumban, akkor módosítania kell a szerkeszthető ER-formátumot.

1. Nyissa meg a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentéskészítés** menüpontot, majd nyissa meg a szerkeszteni kívánt ER-formátum piszkozatverzióját.
2. Válassza a **Jelentéskészítési konfigurációk** elemet. 
3. A **Konfigurációk** oldalon, a konfigurációk fájában bontsa ki a **Fizetési modell** \> **Minta munkalap jelentés** elemet.
4. Válassza a **Tervező** lehetőséget.
5. A **Formátumtervező** oldalon bontsa ki a **Word** elemet, és válassza ki az **Összefoglaló sorok** lehetőséget.
6. A **Hozzárendelés** lapfülön adjon hozzá egy új adatforrást, amely futásidőben megkérdezi a felhasználót, hogy el kell-e rejteni az összegző szakaszt:

    1. Válassza a **Gyökér hozzáadása** elemet.
    2. Az **Adatforrás hozzáadása** párbeszédpanelen válassza az **Általános\Felhasználói beviteli paraméter** lehetőséget a **Felhasználói beviteli paraméter adatforrás tulajdonságai** párbeszédpanel megnyitásához.
    3. A **Név** mezőbe írja be az **uipSuppress** szót.
    4. A **Címke** mezőben írja be a következőt: **Összegző szakasz figyelmen kívül hagyása**.
    5. A **Műveletek adattípus neve** mezőben válassza ki vagy írja be a **NoYes** kifejezést.
    6. Válassza ki az **OK** lehetőséget.

7. Adjon hozzá egy új adatforrást a **NoYes** alkalmazás-felsorolási típusból:

    1. Válassza a **Gyökér hozzáadása** elemet.
    2. Az **Adatforrás hozzáadása** párbeszédpanelen válassza a **Dynamics 365 for Operations\Felsorolás** lehetőséget a **Felsorolás adatforrás tulajdonságai** párbeszédpanel megnyitásához.
    3. A **Név** mezőbe írja be az **enumNoYes** kifejezést.
    4. A **Címke** mezőben írja be a következőt: **Lehetőséget figyelmen kívül hagyása**.
    5. A **Műveletek adattípus neve** mezőben válassza ki vagy írja be a **NoYes** kifejezést.
    6. Válassza ki az **OK** lehetőséget.

8. Állítsa be a képletet a kiválasztott **SummaryLines** formátumelemhez, hogy meghatározza, mikor legyen figyelmen kívül hagyva a kijelölt formátumelemhez társított Word-tartalomvezérlő:

    1. A **Leképezés** lap **Eltávolítva** szakaszában a **Szerkesztés** gombra kattintva nyissa meg a **[Képletszerkesztő](general-electronic-reporting-formula-designer.md)** oldalt.
    2. A **Képlet** mezőben adja meg a következő képletet: `uipSuppress = enumNoYes.Yes`.
    3. Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.

        > [!NOTE]
        > A program ezt a képletet alkalmazza egy generált dokumentumra **az összes többi formátumelem futtatása** után. A képlet alkalmazásához a létrehozott dokumentumban megtalálható egy Word-tartalomvezérlő, amely olyan formátumelemként van megjelölve, amelyhez a képlet konfigurálva van (ebben az esetben **SummaryLines**). Ez a tartalomvezérlő ezután teljesen törlődik, együtt az azzal rendelkező Word-tábla sorával. Az összegző szakasz részletező sorát a program eltávolítja a generált dokumentumból.
        >
        > A tervezés során előfordulhat, hogy egy formátumelemhez konfigurálja az **Eltávolítva** képletet, még akkor is, ha a használt Word-sablonban nincs olyan tartalomvezérlő, amely megfelel azon formátumelem nevének, amelyhez az **Eltávolítva** tulajdonságot konfigurálták. Amikor a formátumot a tervezési időpontban ellenőrzi, egy [figyelmeztetés](er-components-inspections.md#i14) jelenik meg erről az inkonzisztenciáról.
        >
        > Futásidőben kivétel áll elő, ha a használt Word-sablon egyetlen tartalomvezérlője sem tartalmaz olyan címkét, amely megfelel annak a formátumelemnek, amelyhez be van állítva az **Eltávolítva** tulajdonság.

    4. A **Leképezés** lap **Eltávolítva** szakaszában állítsa a **Szülővel** beállítást **Igen** értékre.

        > [!NOTE]
        > Ha az összesítő szakasz részleteit tartalmazó sor szülőobjektumaként az egész Word-táblát el szeretné távolítani, állítsa ezt a beállítást **Igen** értékre. Ha a **Nem** értéket választja, a szakaszfejléc sora a generált dokumentumban marad.

9. A szerkeszthető formátum módosításainak mentéséhez válassza a **Mentés** elemet.

    ![A létrehozott kimenet Word-formátumban](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>Módosított formátum futtatása Word-kimenet létrehozásához

1. Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Fizetési napló** pontra.
2. Válassza ki a létrehozott kifizetési naplót, majd válassza a **Sorok** lehetőséget.
3. A **Szállítói kifizetések** oldalon jelölje ki az összes sort, majd válassza a **Kifizetési állapot** \> **Nincs** lehetőséget.
4. **Kifizetések létrehozása** kiválasztása.
5. A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.
6. A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.
7. Válassza ki az **OK** lehetőséget.
8. Az **Elektronikus jelentés paraméterei** párbeszédpanelben az **Összefoglaló szakasz figyelmen kívül hagyása** mezőben válassza az **Igen** lehetőséget.
9. Kattintson az **OK** gombra, és elemezze a létrehozott kimenetet.

    ![Létrehozott kimenet Word-formátumban](./media/er-design-configuration-word-suppress-controls-image4.gif)

    A kimenet nem tartalmazza az összesítő szakaszt, mert figyelmen kívül hagyta.

## <a name="additional-resources"></a>További erőforrások

- [Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése](./tasks/er-design-reports-openxml-2016-11.md)
- [Új ER-konfiguráció tervezése Word formátumú jelentések generálásához](er-design-configuration-word.md)
- [ER-konfigurációk újrafelhasználása Excel-sablonok segítségével Word formátumú jelentések generálásához](./tasks/er-design-configuration-word-2016-11.md)
- [A konfigurált ER-összetevő ellenőrzése a futásidejű problémák megelőzése érdekében](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]