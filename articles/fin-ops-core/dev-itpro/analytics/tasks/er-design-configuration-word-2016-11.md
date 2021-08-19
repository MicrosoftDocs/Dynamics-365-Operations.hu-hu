---
title: ER-konfigurációk újrafelhasználása Excel-sablonokkal Word-formátumú jelentések generálásához
description: Ez a témakör azt mutatja be, hogyan lehet jelentések Excel-munkafüzetként való előállítására használható jelentésformátumokat beállítani úgy, hogy a jelentéseket Word-dokumentumként hozza létre.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83e75eee54516539be939e9547a8b637bbf2ab107ae96c07c4bbefaad75f1022
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768441"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>ER-konfigurációk újrafelhasználása Excel-sablonokkal Word-formátumú jelentések generálásához

[!include [banner](../../includes/banner.md)]

A jelentések Microsoft Word dokumentumokként történő létrehozásához [konfigurálhat](../er-design-configuration-word.md) egy új [elektronikus jelentéskészítési (ER)](../general-electronic-reporting.md) [formátumot](../general-electronic-reporting.md#FormatComponentOutbound). Arra is lehetőség van, hogy egy eredetileg Excel-munkafüzetként generált jelentéseket készítő ER-formátumot újrafelhasználjon. Ebben az esetben az Excel-sablont Word-sablonra kell cserélnie.

A következő eljárások bemutatják, hogyan konfigurálhat egy ER-formátumot a Rendszergazda szerepkör vagy az Elektronikus jelentések fejlesztője szerepkör egy felhasználója úgy, hogy a jelentések Word-fájlként való generálása során egy jelentések Excel-fájlként való generálására tervezett ER-formátumot használ fel újra.

Ezen eljárásokat a GBSI vállalatban hajthatja végre.

## <a name="prerequisites"></a>Előfeltételek

Az eljárás végrehajtásához kövesse a lépéseket a [Konfiguráció tervezése az OPENXML formátumban létrejövő jelentésekre létrehozásához](er-design-reports-openxml-2016-11.md) feladat-útmutatót.

Le kell tölteni és helyileg menteni a következő sablonokat is a mintajelentéshez:

- [Kifizetési jelentés mintája (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Kifizetési jelentés bekötött sablonja (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

Ezek az eljárások a Dynamics 365 for Operations 1611-es verzióban (2016. november) hozzáadott funkciókra vonatkozóak.

## <a name="select-the-existing-er-report-configuration"></a>Válassza ki a meglévő ER-jelentéskonfigurációt

1. A Dynamics 365 Finance alkalmazásban lépjen a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Győződjön meg arról, hogy a **Litware, Inc.** konfigurációszolgáltató **Aktív** állapottal van megjelölve. Ha nem, kövesse a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) feladat-útmutatót.
3. Válassza a **Jelentéskészítési konfigurációk** elemet. Újrahasznosítja a meglévő ER-konfigurációt, amelyet a jelentés OPENXML-formátumban történő előállítására terveztek.
4. A **Konfigurációk** oldalon, a bal oldali panelen található konfigurációk fájában bontsa ki a **Fizetési modell** elemet, majd válassza a **Minta munkalap jelentés** lehetőséget.

    > [!NOTE]
    > A **Verziók** gyorslapon szerkesztheti a kijelölt ER-formátum piszkozatverzióját.

5. Válassza a **Tervező** lehetőséget.
6. A **Formátumtervező** lapon figyelje meg, hogy a gyökérformátum-elem címe jelzi, hogy jelenleg egy Excel-sablon van használatban.

![A meglévő konfiguráció kiválasztása.](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>A letöltött Word-sablon áttekintése

1. Az asztali Word-alkalmazásban nyissa meg a korábban letöltött **SampleVendPaymDocReport.docx** sablonfájlt.
2. Ellenőrizze, hogy a sablon csak az ER-kimenetként létrehozandó dokumentum elrendezését tartalmazza.

![A Word-sablon elrendezése az asztali alkalmazásban.](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Az Excel-sablon cseréje Word-sablonra és egyéni XML-rész hozzáadása

Jelenleg az Excel-dokumentum használatos sablonként a kimenet OPENXML-formátumú előállításához. Ezt a sablont cserélje le a korábban letöltött SampleVendPaymDocReport.docx Word-sablonfájlra. Terjessze ki a Word-sablont egy egyéni XML-rész hozzáadásával is.

1. A Finance **Formátumtervező** oldalának **Formátum** lapján válassza ki a **Mellékletek** lehetőséget.
2. A meglévő Excel-sablon eltávolításához válassza a **Törlés** lehetőséget a **Mellékletek** lapon. A módosítás jóváhagyásához válassza az **Igen** lehetőséget.
3. Válassza az **Új** \> **Fájl** lehetőséget.

    > [!NOTE]
    > Az ER-formátumok sablonjainak tárolásához ki kell választania egy ER-paraméterekben [konfigurált](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dokumentumtípust.

4. Válassza a **Tallózás** lehetőséget, majd tallózással keresse meg és válassza ki a korábban letöltött **SampleVendPaymDocReport.docx** fájlt.
5. Válassza ki az **OK** lehetőséget.
6. Zárja be a **Mellékletek** lapot.
7. A **Formátumtervező** oldal **Sablon** mezőjében adja meg vagy válassza ki azt a **SampleVendPaymDocReport.docx** fájlt, amelyet Word-sablonként használni kíván a korábban használt Excel-sablon helyett.
8. Válassza a **Mentés** lehetőséget.

    A konfigurációs módosítások tárolása mellett a **Mentés** művelet a csatolt Word-sablont is frissíti. A tervezett formátum hierarchikus szerkezete **Jelentés** néven, új egyéni XML-részként kerül hozzáadásra a csatolt Word-dokumentumhoz. A csatolt Word-sablon nem csak az ER-kimentként létrehozandó dokumentum elrendezését tartalmazza, hanem azt az adatszerkezetet is, amelyet az ER futásidőben ad meg a sablonban.

9. Figyelje meg, hogy a gyökérformátum-elem címe jelzi, hogy jelenleg egy Word-sablon van használatban.

    ![Az Excel-sablon cseréje Word-sablonra és egyéni XML-rész hozzáadása.](../media/er-design-configuration-word-2016-11-image03.gif)

10. Válassza a **Formátum** lap **Mellékletek** elemét.

Most már leképezheti a **Jelentés** egyéni XML-rész elemeinek leképezését a Word-dokumentum tartalomvezérlőire.

Ha megfelelő ismeretekkel rendelkezik a Word-dokumentumok tervezéséről [egyéni XML-részek](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) elemeire leképezett [tartalomvezérlőket](/office/client-developer/word/content-controls-in-word) tartalmazó űrlapokként, akkor hajtsa végre a következő eljárás minden lépését a dokumentum létrehozásához. A további információk: [A felhasználó által Wordben kitölthető vagy kinyomtatható űrlapok létrehozása](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b). Ellenkező esetben hagyja ki a következő eljárást.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>Egyéni XML-résszel rendelkező Word-dokumentum beszerzése adatleképezés végrehajtásához

1. A Finance alkalmazás **Mellékletek** oldalán válassza a **Megnyitás** lehetőséget a kiválasztott sablon Finance alkalmazásból való letöltéséhez és helyi tárolásához Word-dokumentumként.
3. Az asztali Word alkalmazásban nyissa meg az éppen letöltött dokumentumot.
4. Válassza a **Fejlesztő** lap **XML-megfeleltetés munkaablak** elemét.

    > [!NOTE]
    > Ha a **Fejlesztő** lap nem jelenik meg a menüsávon, a hozzáadáshoz szabja testre a menüsávot.

5. Az **XML-leképezés** panel **Egyéni XML-rész** mezőjében válassza ki a **Jelentés** egyéni XML-részt.
6. Képezze le a kiválasztott **Jelentés** egyéni XML-rész elemeit és a Word-dokumentum tartalomvezérlőt.
7. Mentse a frissített Word-dokumentumot helyileg **SampleVendPaymDocReportBounded.docx** néven.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Annak a Word-sablonnak az áttekintése, ahol az egyéni XML-rész tartalomvezérlőkre van leképezve

1. Az asztali Word-alkalmazásban nyissa meg a **SampleVendPaymDocReportBounded.docx** sablonfájlt.
2. Ellenőrizze, hogy a sablon az ER-kimenetként létrehozandó dokumentum elrendezését tartalmazza. Az ER által futásidőben ebbe a sablonba beírt adatok helyőrzőjeként használt tartalomvezérlők a **Jelentés** egyéni XML-része és a Word dokumentum tartalomvezérlői között beállított leképezéseken alapulnak.

![A Word-sablon előnézete az asztali alkalmazásban.](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Annak a Word-sablonnak a feltöltése, ahol az egyéni XML-rész tartalomvezérlőkre van leképezve

1. A Finance alkalmazás **Mellékletek** oldalának **Törlés** elemét választva távolítsa el azt a Word-sablont, amely nem rendelkezik leképezéssel a **Jelentés** egyéni XML-részei és a tartalomvezérlők között. A módosítás jóváhagyásához válassza az **Igen** lehetőséget.
2. Válassza az **Új** \> **Fájl** lehetőséget, ha új sablonfájlt szeretne hozzáadni, amely a **Jelentés** egyéni XML-részei és a tartalomvezérlők közötti megfeleltetéseket tartalmazza.

    > [!NOTE]
    > Az ER-formátumok sablonjainak tárolásához ki kell választania egy ER-paraméterekben [konfigurált](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dokumentumtípust.

3. Válassza a **Tallózás** lehetőséget, majd tallózással keresse meg és válassza ki azt a **SampleVendPaymDocReportBounded.docx** fájlt, amelyet az [Egyéni XML-résszel rendelkező Word-dokumentum beszerzése adatleképezés végrehajtásához](#get-word-doc) eljárás elvégzésével letöltött vagy készített.
4. Válassza ki az **OK** lehetőséget.
5. Zárja be a **Mellékletek** lapot.
6. A **Formátumtervező** oldal **Sablon** mezőjében válassza ki a most letöltött dokumentumot.
7. Válassza a **Mentés** lehetőséget.
8. Zárja be a **Formátumtervező** lapot.

## <a name="mark-the-configured-format-as-runnable"></a>A konfigurált formátum megjelölése futtathatóként

Ahhoz, hogy a szerkeszthető formátum vázlatverzióját futtatni tudja, [futtathatóra](../er-quick-start2-customize-report.md#MarkFormatRunnable) kell tennie.

1. A Finance alkalmazásban a **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
2. A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Futtatási beállítások** beállítását **Igen** értékre, majd kattintson az **OK** gombra.
3. Ha szükséges, a **Szerkesztés** gombbal az aktuális lapot szerkeszthetőre állíthatja.
4. A jelenleg kiválasztott **Minta munkalap jelentés** konfiguráció esetében állítsa **Igen** beállításra a **Vázlat futtatása** beállítást.
5. Válassza a **Mentés** lehetőséget.

## <a name="run-the-format-to-create-output-in-word-format"></a>A kimenet Word formátumban való létrehozásához használt formátum futtatása

1. A Finance alkalmazásban lépjen a **Kötelezettségek** \> **Fizetések** \> **Fizetési napló** lehetőségre.
2. A korábban megadott fizetési naplóban válassza a **Sorok** lehetőséget.
3. A **Szállítói kifizetések** lapon jelölje ki a rács összes sorát.
4. Válassza ki a **Fizetési állapot** \> **Nincs** lehetőséget.

    ![A feldolgozandó kifizetések hozzáadva a Szállítói fizetések lapon.](../media/er-design-configuration-word-2016-11-image05.png)

5. A Művelet ablaktáblán válassza ki a **Kifizetések generálása** elemet.
6. A megjelenő párbeszédpanelen hajtsa végre a következő lépéseket:

    1. A **Fizetési mód** mezőben válassza az **Elektronikus** lehetőséget.
    2. A **Bankszámla** mezőben válassza a **GBSI OPER** lehetőséget.
    3. Válassza ki az **OK** lehetőséget.

7. Az **Elektronikus jelentési paraméterek** párbeszédablakban válassza az **OK** lehetőséget.
8. A létrehozott kimenet Word-formátumban jelenik meg, és a feldolgozott kifizetések adatait tartalmazza. Elemezze a létrehozott kimenetet.

    ![Létrehozott kimenet Word-formátumban.](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>További erőforrások

- [Új ER-konfiguráció tervezése Word formátumú jelentések generálásához](../er-design-configuration-word.md)
- [Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
